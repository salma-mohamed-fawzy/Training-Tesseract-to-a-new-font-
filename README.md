# Training-Tesseract-to-a-new-font-
___________suppose we are training a font which is called "Blade"__________ 

follow the following steps: 

1- download jTessBox Editor from the rar file in this repository
2- from tools- merge tiff to convert the image to a tiff file
3- open cmd from the path of the tiff file
4- write "  tesseract blade.tif blade batch.nochop makebox   " to make box files for images that we want to train
5- go to the program: from box editor ... edit box and corresponding character to be correct
6- return to cmd again
7- write " tesseract blade.tif blade box.train " to  create .tr file (Compounding image file and box file)
8- write " unicharset_extractor blade.box " to extract the charset from the box files (Output for this command is unicharset file)
9- write " echo " blade0 0 1 0 0" >  font_properties " to create a font_properties file based on our needs.
10- write " mftraining -F font_properties -U unicharset -O blade.unicharset blade.tr " for Training the data.
11- write " cntraining blade.tr "  and four files will be created (shapetable,inttemp,pffmtable,normproto) }
12-Rename four files  as following 
    "  rename shapetable train.shapetable
       rename inttemp train.inttemp
       rename pffmtable train.pffmtable
       rename normproto train.normproto  "
13- write " combine_tessdata blade. " to get afile called blade.traineedata
14- Move .traineddata file to tesseract programs tessdata directory
    C:\Program Files\Tesseract-OCR\tessdata
15- Run tesseract for trained fronts
and dont forget to replace "Blade" with the name of the font you want 

