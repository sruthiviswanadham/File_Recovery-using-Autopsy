# File_Recovery-using-Autopsy

## Aim
The objective of this guide is to demonstrate how to:  
 - Create a **Virtual Hard Disk (VHD)**.  
 - Add images to the disk, delete them, and recover them using **Autopsy**.  
 - Understand the forensic recovery process for deleted files.  
 - Learn how to remove the virtual disk after completing the experiment.

## Virtual Disk Creation & File Recovery using Autopsy 


## Step 1: 
   Create a Virtual Hard Disk (VHD) 

### **1. Open Disk Management**  
- Press **Windows + X** → Click **Disk Management** 

 ![](./images/disk1.png)

### **2. Create a New VHD**  
- Click **Action** (top menu) → **Create VHD**.  

![](./images/disk2.png)

### **3. Choose File Location & Size**  
- Click **Browse** and select where to save the VHD file (e.g, `C:\new VHD.vhd`)
- Set the **size** (e.g: `1GB`) 
- Choose **VHD (Fixed Size)** and Click **OK**

![](./images/disk3.png)

### **4. Initialize the Disk**  
- In **Disk Management**, find your new disk (marked as "Not Initialized").  

![](./images/disk4.png) 

- Right-click the disk → Click **Initialize Disk**.

![](./images/disk5.png)

- Select **MBR (Master Boot Record)**. 

![](./images/disk6.png)

### **6. Create & Format the Partition**  
- Right-click the **Unallocated Space** → Click **New Simple Volume**.  
![](./images/disk7.png)
![](./images/disk8.png)
![](./images/disk9.png)


- Click **Next** → **Click on Mount in the following empty NTFS folder** → **Browse** → **Assign a drive letter (e.g., `C: or D:`)** → **New folder** → **OK**

![](./images/disk10.png)
![](./images/disk12.png)
![](./images/disk11.png)

- Click **next** → **Finish**. 

---

## **Step 2: Add & Delete Files for Recovery** 

### **1. Copy Files to the Virtual Disk**  
- Open **File Explorer** → Go to the new drive (`C: or D:`), where the folder created in the previous step
- Create a new folder (`TestFolder`) and copy **images or files** into it.  

### **2. Delete the Files**  
- Select any one or two images → Press **Delete**.  
- Empty the **Recycle Bin** to permanently delete them.  

---

## **Step 3: Recover Deleted Files Using Autopsy**  
### **1. Open Autopsy & Create a New Case** 

- Launch **Autopsy** and **Run as a administrator**  
- Click **Create New Case**.  

![](./images/a1.png)

- Enter a **Case Name** (e.g., `Autopsy1`).  
- Choose a **Case Folder** location.  
- Click **Next** → Click **Finish**.  

![](./images/a2.png)

### **2. Add the Virtual Disk as an Evidence Source**  
- Click **Add Data Source**  → **Select Host**

![](./images/a3.png)

- Select **Local Disk** → **next** 

![](./images/a4.png)

- Select Disk → **Choose the VHD drive (`Drive1`)**

![](./images/a5.png)

- Click **Next** → Keep default settings → Click **Finish**.  
- Wait for Autopsy to process the disk.  

### **3. Recover Deleted Files**  
- Go to **File Views** (left panel).  

![](./images/a6.png)

- Click **Deleted Files** → Find your deleted images.  
- Right-click an image → Click **Extract File**.  

![](./images/a7.png)

- Select a folder to see the recovered files (e.g., `C:\image_recovery`).  

**Your deleted images are now recovered!**  

---

## **Step 4: Delete the Virtual Disk (Optional Cleanup)** 

### **1. Detach the VHD**  
- Open **Disk Management** (`Win + X` → Disk Management).  
- Find the **virtual disk** (`C: or D:`).  
- Right-click the disk (not the partition) → Click **Detach VHD**.  

### **2. Delete the VHD File**  
- Open **File Explorer**.  
- Go to the location where you saved the `.vhd` file (e.g., `C:\new VHD.vhd`).  
- **Delete** the `.vhd` file.  
- Empty the **Recycle Bin**.  

**Your virtual disk is completely removed!**  
 
---
 

## Result :
 This guide covers creating a Virtual Hard Disk (VHD), adding, deleting, and recovering images using Autopsy, and safely deleting the virtual disk after the experiment.