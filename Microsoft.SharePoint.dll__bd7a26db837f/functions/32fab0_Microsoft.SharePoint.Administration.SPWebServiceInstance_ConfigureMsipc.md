# Microsoft.SharePoint.Administration.SPWebServiceInstance::ConfigureMsipc

- ea: `0x32fab0`
- end: `0x32fece`
- name: `Microsoft.SharePoint.Administration.SPWebServiceInstance::ConfigureMsipc`
- size: `1054`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x32f900`

## callees

- `0x19f830`
- `0x29d0f0`
- `0x32fab0`
- `0x32fed0`
- `0x93dab0`
- `0x957530`

## string_xrefs

- `0x32fb5a`: `InstallLocation`
- `0x32fb31`: `No need to configure MSIPC - target environment: {0}, target environment subtype: {1} `
- `0x32fb55`: `SOFTWARE\Microsoft\MSIPC\CurrentVersion`
- `0x32fb6b`: `C:\Program Files\Active Directory Rights Management Services Client 2.1\`
- `0x32fb7a`: `C:\Program Files\Active Directory Rights Management Services Client 2.1\`
- `0x32fb8f`: `C:\Program Files\Active Directory Rights Management Services Client 2.1\`
- `0x32fba0`: `C:\Program Files\Active Directory Rights Management Services Client 2.1\`
- `0x32fd27`: `C:\Program Files\Active Directory Rights Management Services Client 2.1\`
- `0x32fd37`: `C:\Program Files\Active Directory Rights Management Services Client 2.1\`
- `0x32fb7f`: `MsipcHostNameRedirection.dat`
- `0x32fd3c`: `MsipcHostNameRedirection.dat`
- `0x32fd56`: `MsipcHostNameRedirection.dat`
- `0x32fb94`: `MsipcHostNameRedirection.dat.prod`
- `0x32fba5`: `MsipcHostNameRedirection.dat.edog`
- `0x32fbc2`: `Trying to copy {0} to {1}`
- `0x32fc96`: `Trying to copy {0} to {1}`
- `0x32fd73`: `Trying to copy {0} to {1}`
- `0x32fe33`: `Trying to copy {0} to {1}`
- `0x32fc35`: `Skipping MSIPC installation folder: C:\Program Files\Active Directory Rights Management Services Client 2.1\`
- `0x32fc3f`: `C:\Program Files\Active Directory Rights Management Services Client 2.0\`
- `0x32fc4e`: `C:\Program Files\Active Directory Rights Management Services Client 2.0\`
- `0x32fc63`: `C:\Program Files\Active Directory Rights Management Services Client 2.0\`
- `0x32fc74`: `C:\Program Files\Active Directory Rights Management Services Client 2.0\`
- `0x32fd15`: `C:\Program Files\Active Directory Rights Management Services Client 2.0\`
- `0x32fdf7`: `C:\Program Files\Active Directory Rights Management Services Client 2.0\`
- `0x32fc53`: `msipcextension.dll`
- `0x32fdfc`: `msipcextension.dll`
- `0x32fe16`: `msipcextension.dll`
- `0x32fc68`: `msipcextension.dll.prod`
- `0x32fc79`: `msipcextension.dll.edog`
- `0x32fd09`: `Skipping MSIPC installation folder: C:\Program Files\Active Directory Rights Management Services Client 2.0\`
- `0x32fde6`: `Skipping MSIPC config file: `
- `0x32fea5`: `Skipping MSIPC config file: `
- `0x32fec3`: `Failed to get grid information (target environment). Do not configure MSIPC.`

## pseudocode

```c

```

## disassembly

```asm
0x32fab0  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x32fab5  ldloca.s 0
0x32fab7  ldloca.s 1
0x32fab9  ldloca.s 2
0x32fabb  ldloca.s 3
0x32fabd  ldloca.s 4
0x32fabf  call     bool Microsoft.SharePoint.Utilities.SPUtility::TryGetGridInformation(class Microsoft.SharePoint.Administration.SPFarm farm, [out] string& environmentType, [out] string& environmentSubtype, [out] int32& networkId, [out] int32& farmId, [out] bool& dogfoodFarmConnectedToProdAAD)
0x32fac4  brfalse  loc_32FEB7
0x32fac9  ldloc.0
0x32faca  ldstr    aDatacenter// "DataCenter"
0x32facf  ldc.i4.5
0x32fad0  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x32fad5  brfalse.s loc_32FAF6
0x32fad7  ldloc.1
0x32fad8  ldstr    aProdbubble// "ProdBubble"
0x32fadd  ldc.i4.5
0x32fade  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x32fae3  brtrue.s loc_32FAF3
0x32fae5  ldloc.1
0x32fae6  ldstr    aProd// "Prod"
0x32faeb  ldc.i4.5
0x32faec  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x32faf1  br.s     loc_32FAF7
0x32faf3  ldc.i4.1
0x32faf4  br.s     loc_32FAF7
0x32faf6  ldc.i4.0
0x32faf7  stloc.s  5
0x32faf9  ldloc.0
0x32fafa  ldstr    aDatacenter// "DataCenter"
0x32faff  ldc.i4.5
0x32fb00  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x32fb05  brfalse.s loc_32FB15
0x32fb07  ldloc.1
0x32fb08  ldstr    aEdog_0// "EDog"
0x32fb0d  ldc.i4.5
0x32fb0e  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x32fb13  br.s     loc_32FB16
0x32fb15  ldc.i4.0
0x32fb16  stloc.s  6
0x32fb18  ldloc.s  5
0x32fb1a  brtrue.s loc_32FB55
0x32fb1c  ldloc.s  6
0x32fb1e  brtrue.s loc_32FB55
0x32fb20  ldc.i4   0x5D439D
0x32fb25  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fb2a  ldc.i4.s 0x32
0x32fb2c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32fb31  ldstr    aNoNeedToConfig// "No need to configure MSIPC - target env"...
0x32fb36  ldc.i4.2
0x32fb37  newarr   [mscorlib]System.Object
0x32fb3c  stloc.s  0x10
0x32fb3e  ldloc.s  0x10
0x32fb40  ldc.i4.0
0x32fb41  ldloc.0
0x32fb42  stelem.ref
0x32fb43  ldloc.s  0x10
0x32fb45  ldc.i4.1
0x32fb46  ldloc.1
0x32fb47  stelem.ref
0x32fb48  ldloc.s  0x10
0x32fb4a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32fb4f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fb54  ret
0x32fb55  ldstr    aSoftwareMicros_6// "SOFTWARE\\Microsoft\\MSIPC\\CurrentVers"...
0x32fb5a  ldstr    aInstalllocatio// "InstallLocation"
0x32fb5f  ldstr    asc_C00000// ""
0x32fb64  call     T0x2B0000E3
0x32fb69  stloc.s  7
0x32fb6b  ldstr    aCProgramFilesA// "C:\\Program Files\\Active Directory Rig"...
0x32fb70  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x32fb75  brfalse  loc_32FC29
0x32fb7a  ldstr    aCProgramFilesA// "C:\\Program Files\\Active Directory Rig"...
0x32fb7f  ldstr    aMsipchostnamer// "MsipcHostNameRedirection.dat"
0x32fb84  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32fb89  stloc.s  8
0x32fb8b  ldloc.s  6
0x32fb8d  brtrue.s loc_32FBA0
0x32fb8f  ldstr    aCProgramFilesA// "C:\\Program Files\\Active Directory Rig"...
0x32fb94  ldstr    aMsipchostnamer_0// "MsipcHostNameRedirection.dat.prod"
0x32fb99  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32fb9e  br.s     loc_32FBAF
0x32fba0  ldstr    aCProgramFilesA// "C:\\Program Files\\Active Directory Rig"...
0x32fba5  ldstr    aMsipchostnamer_1// "MsipcHostNameRedirection.dat.edog"
0x32fbaa  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32fbaf  stloc.s  9
0x32fbb1  ldc.i4   0x8C5394
0x32fbb6  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fbbb  ldc.i4.s 0x32
0x32fbbd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32fbc2  ldstr    aTryingToCopy0T// "Trying to copy {0} to {1}"
0x32fbc7  ldc.i4.2
0x32fbc8  newarr   [mscorlib]System.Object
0x32fbcd  stloc.s  0x11
0x32fbcf  ldloc.s  0x11
0x32fbd1  ldc.i4.0
0x32fbd2  ldloc.s  9
0x32fbd4  stelem.ref
0x32fbd5  ldloc.s  0x11
0x32fbd7  ldc.i4.1
0x32fbd8  ldloc.s  8
0x32fbda  stelem.ref
0x32fbdb  ldloc.s  0x11
0x32fbdd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32fbe2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fbe7  ldarg.0
0x32fbe8  ldloc.s  9
0x32fbea  ldloc.s  8
0x32fbec  call     instance void Microsoft.SharePoint.Administration.SPWebServiceInstance::CopyFile(string sourceFilePath, string destFilePath)
0x32fbf1  ldc.i4   0x8C5395
0x32fbf6  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fbfb  ldc.i4.s 0x32
0x32fbfd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32fc02  ldstr    aSuccessfullyCo// "Successfully copied {0} to {1}"
0x32fc07  ldc.i4.2
0x32fc08  newarr   [mscorlib]System.Object
0x32fc0d  stloc.s  0x12
0x32fc0f  ldloc.s  0x12
0x32fc11  ldc.i4.0
0x32fc12  ldloc.s  9
0x32fc14  stelem.ref
0x32fc15  ldloc.s  0x12
0x32fc17  ldc.i4.1
0x32fc18  ldloc.s  8
0x32fc1a  stelem.ref
0x32fc1b  ldloc.s  0x12
0x32fc1d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32fc22  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fc27  br.s     loc_32FC3F
0x32fc29  ldc.i4   0x8C5396
0x32fc2e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fc33  ldc.i4.s 0xA
0x32fc35  ldstr    aSkippingMsipcI// "Skipping MSIPC installation folder: C:"...
0x32fc3a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fc3f  ldstr    aCProgramFilesA_0// "C:\\Program Files\\Active Directory Rig"...
0x32fc44  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x32fc49  brfalse  loc_32FCFD
0x32fc4e  ldstr    aCProgramFilesA_0// "C:\\Program Files\\Active Directory Rig"...
0x32fc53  ldstr    aMsipcextension// "msipcextension.dll"
0x32fc58  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32fc5d  stloc.s  0xA
0x32fc5f  ldloc.s  6
0x32fc61  brtrue.s loc_32FC74
0x32fc63  ldstr    aCProgramFilesA_0// "C:\\Program Files\\Active Directory Rig"...
0x32fc68  ldstr    aMsipcextension_0// "msipcextension.dll.prod"
0x32fc6d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32fc72  br.s     loc_32FC83
0x32fc74  ldstr    aCProgramFilesA_0// "C:\\Program Files\\Active Directory Rig"...
0x32fc79  ldstr    aMsipcextension_1// "msipcextension.dll.edog"
0x32fc7e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32fc83  stloc.s  0xB
0x32fc85  ldc.i4   0x8C5397
0x32fc8a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fc8f  ldc.i4.s 0x32
0x32fc91  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32fc96  ldstr    aTryingToCopy0T// "Trying to copy {0} to {1}"
0x32fc9b  ldc.i4.2
0x32fc9c  newarr   [mscorlib]System.Object
0x32fca1  stloc.s  0x13
0x32fca3  ldloc.s  0x13
0x32fca5  ldc.i4.0
0x32fca6  ldloc.s  0xB
0x32fca8  stelem.ref
0x32fca9  ldloc.s  0x13
0x32fcab  ldc.i4.1
0x32fcac  ldloc.s  0xA
0x32fcae  stelem.ref
0x32fcaf  ldloc.s  0x13
0x32fcb1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32fcb6  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fcbb  ldarg.0
0x32fcbc  ldloc.s  0xB
0x32fcbe  ldloc.s  0xA
0x32fcc0  call     instance void Microsoft.SharePoint.Administration.SPWebServiceInstance::CopyFile(string sourceFilePath, string destFilePath)
0x32fcc5  ldc.i4   0x8C5398
0x32fcca  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fccf  ldc.i4.s 0x32
0x32fcd1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32fcd6  ldstr    aSuccessfullyCo// "Successfully copied {0} to {1}"
0x32fcdb  ldc.i4.2
0x32fcdc  newarr   [mscorlib]System.Object
0x32fce1  stloc.s  0x14
0x32fce3  ldloc.s  0x14
0x32fce5  ldc.i4.0
0x32fce6  ldloc.s  0xB
0x32fce8  stelem.ref
0x32fce9  ldloc.s  0x14
0x32fceb  ldc.i4.1
0x32fcec  ldloc.s  0xA
0x32fcee  stelem.ref
0x32fcef  ldloc.s  0x14
0x32fcf1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32fcf6  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fcfb  br.s     loc_32FD13
0x32fcfd  ldc.i4   0x8C5399
0x32fd02  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fd07  ldc.i4.s 0xA
0x32fd09  ldstr    aSkippingMsipcI_0// "Skipping MSIPC installation folder: C:"...
0x32fd0e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fd13  ldloc.s  7
0x32fd15  ldstr    aCProgramFilesA_0// "C:\\Program Files\\Active Directory Rig"...
0x32fd1a  ldc.i4.3
0x32fd1b  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x32fd20  brtrue   loc_32FECD
0x32fd25  ldloc.s  7
0x32fd27  ldstr    aCProgramFilesA// "C:\\Program Files\\Active Directory Rig"...
0x32fd2c  ldc.i4.3
0x32fd2d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x32fd32  brtrue   loc_32FECD
0x32fd37  ldstr    aCProgramFilesA// "C:\\Program Files\\Active Directory Rig"...
0x32fd3c  ldstr    aMsipchostnamer// "MsipcHostNameRedirection.dat"
0x32fd41  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32fd46  stloc.s  0xC
0x32fd48  ldloc.s  0xC
0x32fd4a  call     bool [mscorlib]System.IO.File::Exists(string)
0x32fd4f  brfalse  loc_32FDDA
0x32fd54  ldloc.s  7
0x32fd56  ldstr    aMsipchostnamer// "MsipcHostNameRedirection.dat"
0x32fd5b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32fd60  stloc.s  0xD
0x32fd62  ldc.i4   0x8C539A
0x32fd67  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fd6c  ldc.i4.s 0x32
0x32fd6e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32fd73  ldstr    aTryingToCopy0T// "Trying to copy {0} to {1}"
0x32fd78  ldc.i4.2
0x32fd79  newarr   [mscorlib]System.Object
0x32fd7e  stloc.s  0x15
0x32fd80  ldloc.s  0x15
0x32fd82  ldc.i4.0
0x32fd83  ldloc.s  0xC
0x32fd85  stelem.ref
0x32fd86  ldloc.s  0x15
0x32fd88  ldc.i4.1
0x32fd89  ldloc.s  0xD
0x32fd8b  stelem.ref
0x32fd8c  ldloc.s  0x15
0x32fd8e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32fd93  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fd98  ldarg.0
0x32fd99  ldloc.s  0xC
0x32fd9b  ldloc.s  0xD
0x32fd9d  call     instance void Microsoft.SharePoint.Administration.SPWebServiceInstance::CopyFile(string sourceFilePath, string destFilePath)
0x32fda2  ldc.i4   0x8C539B
0x32fda7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fdac  ldc.i4.s 0x32
0x32fdae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32fdb3  ldstr    aSuccessfullyCo// "Successfully copied {0} to {1}"
0x32fdb8  ldc.i4.2
0x32fdb9  newarr   [mscorlib]System.Object
0x32fdbe  stloc.s  0x16
0x32fdc0  ldloc.s  0x16
0x32fdc2  ldc.i4.0
0x32fdc3  ldloc.s  0xC
0x32fdc5  stelem.ref
0x32fdc6  ldloc.s  0x16
0x32fdc8  ldc.i4.1
0x32fdc9  ldloc.s  0xD
0x32fdcb  stelem.ref
0x32fdcc  ldloc.s  0x16
0x32fdce  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32fdd3  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fdd8  br.s     loc_32FDF7
0x32fdda  ldc.i4   0x8C539C
0x32fddf  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fde4  ldc.i4.s 0xA
0x32fde6  ldstr    aSkippingMsipcC// "Skipping MSIPC config file: "
0x32fdeb  ldloc.s  0xC
0x32fded  call     string [mscorlib]System.String::Concat(string, string)
0x32fdf2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fdf7  ldstr    aCProgramFilesA_0// "C:\\Program Files\\Active Directory Rig"...
0x32fdfc  ldstr    aMsipcextension// "msipcextension.dll"
0x32fe01  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32fe06  stloc.s  0xE
0x32fe08  ldloc.s  0xE
0x32fe0a  call     bool [mscorlib]System.IO.File::Exists(string)
0x32fe0f  brfalse  loc_32FE99
0x32fe14  ldloc.s  7
0x32fe16  ldstr    aMsipcextension// "msipcextension.dll"
0x32fe1b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32fe20  stloc.s  0xF
0x32fe22  ldc.i4   0x8C539D
0x32fe27  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32fe2c  ldc.i4.s 0x32
0x32fe2e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32fe33  ldstr    aTryingToCopy0T// "Trying to copy {0} to {1}"
0x32fe38  ldc.i4.2
0x32fe39  newarr   [mscorlib]System.Object
0x32fe3e  stloc.s  0x17
0x32fe40  ldloc.s  0x17
0x32fe42  ldc.i4.0
0x32fe43  ldloc.s  0xE
0x32fe45  stelem.ref
0x32fe46  ldloc.s  0x17
0x32fe48  ldc.i4.1
0x32fe49  ldloc.s  0xF
0x32fe4b  stelem.ref
0x32fe4c  ldloc.s  0x17
0x32fe4e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x32fe53  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x32fe58  ldarg.0
  ... truncated ...
```
