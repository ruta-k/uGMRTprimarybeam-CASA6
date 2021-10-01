# uGMRTprimarybeam-CASA6

Please follow the procedure to incorporate new task in CASA 6 given over here:
https://casadocs.readthedocs.io/en/stable/api/casashell/buildmytasks.html

Once the task is ready to be used, follow the example given below to run the task for your image.
-----------------------------------------------------------------------------------------------------
Example 1:
Suppose test.ms is the visibility file containing 4 spectral windows (0, 1, 2 and 3) containing 20 channels each. An image with the name "target" (prefix) is produced using nterms = 2 in tclean. 
Following will be the inputs for the task.

vis           = 'test.ms'                      # Name of measurement set.
imagename     = 'target'                      # Name-prefix of multi-termimages to operate on.
nterms        = 2                       # Number of taylor terms to use
threshold     = ''                      # Intensity above which to re-calculate spectral index
action        = 'pbcor'                 # PB-correction (pbcor) or only calc spectral-index (calcalpha)
reffreq    = ''                      # Reference frequency (if specified in clean)
pbmin      = 0.1                     # PB threshold below which to not correct
field      = ''                      # Fields to include in the PB calculation
spwlist    = [0,1,2,3]                      # List of N spw ids
chanlist   = [10,10,10,10]                      # List of N channel ids
weightlist = [1,1,1,1]         

-----------------------------------------------------------------------------------------------------
Example 2:
Suppose test.ms is the visibility file containing a single spectral window (0) containing 160 channels. An image with the name "target" (prefix) is produced using nterms = 2 in tclean. Given the width of the spectral window, you may choose to sample it at some n points to get the primary beam shape. In this example I have chosen n=5.
Following will be the inputs for the task.

vis           = 'test.ms'                      # Name of measurement set.
imagename     = 'target'                      # Name-prefix of multi-termimages to operate on.
nterms        = 2                       # Number of taylor terms to use
threshold     = ''                      # Intensity above which to re-calculate spectral index
action        = 'pbcor'                 # PB-correction (pbcor) or only calc spectral-index (calcalpha)
reffreq    = ''                      # Reference frequency (if specified in clean)
pbmin      = 0.1                     # PB threshold below which to not correct
field      = ''                      # Fields to include in the PB calculation
spwlist    = [0,0,0,0,0]                      # List of N spw ids
chanlist   = [40,80,120,140]                      # List of N channel ids
weightlist = [1,1,1,1,1]         
