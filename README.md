# Digital Image Carving Using Scalpel

-   On ubuntu ran the following command:

    -   sudo apt install p7zip-full hashdeep sleuthkit scalpel tree -y

<!-- -->

-   Following command did not work (file was downloaded as an html):
    wget -q
    [[https://github.com/yaukacheung/csci352/blob/main/A1/120M.7z]{.underline}](https://github.com/yaukacheung/csci352/blob/main/A1/120M.7z)

    -   Had to download manually from github website and ran the
        following command:

        -   mv /mnt/c/Users/tyler/Downloads/120M.7z \~/

-   Ran:

    -   7z l 120M.7z

    -   ![](images/media/image11.png)

<!-- -->

-   To extract file, Ran :

    -   7z e 120M.7z

    -   ![](images/media/image5.png)

<!-- -->

-   To verify hashes, Ran:

    -   hashdeep -c md5, sha1 usb_fat_carving.001

    -   And

    -   Cat usb_fat_carving.001.txt

    -   ![](images/media/image7.png)

    -   ![](images/media/image6.png)

<!-- -->

-   To display and look at partitions:

    -   Fdisk -l usb_fat_carving.001

    -   ![](images/media/image8.png)

<!-- -->

-   To find deleted files (\* mean deleted files):

    -   Fls -o 128 usb_fat_carving.001

    -   ![](images/media/image1.png)

-   To decide which files to carve:

    -   Sudo leafpad /etc/scalpel/scalpel.conf

    -   ![](images/media/image9.png)

-   To carve the image:

    -   scalpel usb_fat_carving.001 -o output

    -   ![](images/media/image3.png)

-   To see carved files:

    -   Tree output

    -   ![](images/media/image2.png)

-   Show audit logs:

    -   Cat output/audit.txt

    -   ![](images/media/image10.png)

-   Displayed images with

    -   Display output/jpg-0-0/file_name.jpg

    -   ![](images/media/image12.png)

    -   ![](images/media/image4.png)

    -   Had to download the display package with : sudo apt install
        graphicsmagick-imagemagick-compat \# version 1.4+really1.3.42-1
