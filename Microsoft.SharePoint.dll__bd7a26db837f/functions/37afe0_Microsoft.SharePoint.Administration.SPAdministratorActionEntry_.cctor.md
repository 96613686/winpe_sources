# Microsoft.SharePoint.Administration.SPAdministratorActionEntry::.cctor

- ea: `0x37afe0`
- end: `0x37b3ca`
- name: `Microsoft.SharePoint.Administration.SPAdministratorActionEntry::.cctor`
- size: `1002`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x37b2af`: `.Repair`
- `0x37aff4`: `Administration.Security.`
- `0x37b00c`: `Administration.Farm.ConfigurationDatabase.`
- `0x37b03d`: `Administration.ServiceApplication.`
- `0x37b046`: `Administration.FormTemplate.`
- `0x37b074`: `.Copy`
- `0x37b0c0`: `.Move`
- `0x37b0d2`: `.Open`
- `0x37b0ff`: `.Remove`
- `0x37b108`: `.Rename`
- `0x37b198`: `.Read`
- `0x37b1b3`: `.Write`
- `0x37b1ce`: `.Compare`
- `0x37b1d7`: `.Compress`
- `0x37b1fb`: `.Dismount`
- `0x37b24c`: `.Mount`
- `0x37b28b`: `.Update`
- `0x37b2e5`: `.Complete`
- `0x37b312`: `.Install`
- `0x37b36c`: `.Uninstall`

## pseudocode

```c

```

## disassembly

```asm
0x37afe0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x37afe5  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Administration.SPAdministratorActionEntry::verifiedActions
0x37afea  ldc.i4.s 0xB
0x37afec  newarr   [mscorlib]System.String
0x37aff1  stloc.0
0x37aff2  ldloc.0
0x37aff3  ldc.i4.0
0x37aff4  ldstr    aAdministration_46// "Administration.Security."
0x37aff9  stelem.ref
0x37affa  ldloc.0
0x37affb  ldc.i4.1
0x37affc  ldstr    aAdministration_47// "Administration.Farm.BackupRestore."
0x37b001  stelem.ref
0x37b002  ldloc.0
0x37b003  ldc.i4.2
0x37b004  ldstr    aAdministration_48// "Administration.Farm.Server."
0x37b009  stelem.ref
0x37b00a  ldloc.0
0x37b00b  ldc.i4.3
0x37b00c  ldstr    aAdministration_49// "Administration.Farm.ConfigurationDataba"...
0x37b011  stelem.ref
0x37b012  ldloc.0
0x37b013  ldc.i4.4
0x37b014  ldstr    aAdministration_50// "Administration.SiteCollection."
0x37b019  stelem.ref
0x37b01a  ldloc.0
0x37b01b  ldc.i4.5
0x37b01c  ldstr    aAdministration_51// "Administration.Quota."
0x37b021  stelem.ref
0x37b022  ldloc.0
0x37b023  ldc.i4.6
0x37b024  ldstr    aAdministration_52// "Administration.Feature."
0x37b029  stelem.ref
0x37b02a  ldloc.0
0x37b02b  ldc.i4.7
0x37b02c  ldstr    aAdministration_53// "Administration.WebApplication."
0x37b031  stelem.ref
0x37b032  ldloc.0
0x37b033  ldc.i4.8
0x37b034  ldstr    aAdministration_54// "Administration.ContentDatabase."
0x37b039  stelem.ref
0x37b03a  ldloc.0
0x37b03b  ldc.i4.s 9
0x37b03d  ldstr    aAdministration_55// "Administration.ServiceApplication."
0x37b042  stelem.ref
0x37b043  ldloc.0
0x37b044  ldc.i4.s 0xA
0x37b046  ldstr    aAdministration_56// "Administration.FormTemplate."
0x37b04b  stelem.ref
0x37b04c  ldloc.0
0x37b04d  stsfld   string[] Microsoft.SharePoint.Administration.SPAdministratorActionEntry::approvedHighLevelFeatures
0x37b052  ldc.i4.s 0x62
0x37b054  newarr   [mscorlib]System.String
0x37b059  stloc.1
0x37b05a  ldloc.1
0x37b05b  ldc.i4.0
0x37b05c  ldstr    aAdd_1// ".Add"
0x37b061  stelem.ref
0x37b062  ldloc.1
0x37b063  ldc.i4.1
0x37b064  ldstr    aClear_0// ".Clear"
0x37b069  stelem.ref
0x37b06a  ldloc.1
0x37b06b  ldc.i4.2
0x37b06c  ldstr    aClose_1// ".Close"
0x37b071  stelem.ref
0x37b072  ldloc.1
0x37b073  ldc.i4.3
0x37b074  ldstr    aCopy// ".Copy"
0x37b079  stelem.ref
0x37b07a  ldloc.1
0x37b07b  ldc.i4.4
0x37b07c  ldstr    aEnter// ".Enter"
0x37b081  stelem.ref
0x37b082  ldloc.1
0x37b083  ldc.i4.5
0x37b084  ldstr    aExit// ".Exit"
0x37b089  stelem.ref
0x37b08a  ldloc.1
0x37b08b  ldc.i4.6
0x37b08c  ldstr    aFind// ".Find"
0x37b091  stelem.ref
0x37b092  ldloc.1
0x37b093  ldc.i4.7
0x37b094  ldstr    aFormat// ".Format"
0x37b099  stelem.ref
0x37b09a  ldloc.1
0x37b09b  ldc.i4.8
0x37b09c  ldstr    aGet_1// ".Get"
0x37b0a1  stelem.ref
0x37b0a2  ldloc.1
0x37b0a3  ldc.i4.s 9
0x37b0a5  ldstr    aHide// ".Hide"
0x37b0aa  stelem.ref
0x37b0ab  ldloc.1
0x37b0ac  ldc.i4.s 0xA
0x37b0ae  ldstr    aJoin// ".Join"
0x37b0b3  stelem.ref
0x37b0b4  ldloc.1
0x37b0b5  ldc.i4.s 0xB
0x37b0b7  ldstr    aLock_0// ".Lock"
0x37b0bc  stelem.ref
0x37b0bd  ldloc.1
0x37b0be  ldc.i4.s 0xC
0x37b0c0  ldstr    aMove// ".Move"
0x37b0c5  stelem.ref
0x37b0c6  ldloc.1
0x37b0c7  ldc.i4.s 0xD
0x37b0c9  ldstr    aNew_1// ".New"
0x37b0ce  stelem.ref
0x37b0cf  ldloc.1
0x37b0d0  ldc.i4.s 0xE
0x37b0d2  ldstr    aOpen// ".Open"
0x37b0d7  stelem.ref
0x37b0d8  ldloc.1
0x37b0d9  ldc.i4.s 0xF
0x37b0db  ldstr    aOptimize// ".Optimize"
0x37b0e0  stelem.ref
0x37b0e1  ldloc.1
0x37b0e2  ldc.i4.s 0x10
0x37b0e4  ldstr    aPop// ".Pop"
0x37b0e9  stelem.ref
0x37b0ea  ldloc.1
0x37b0eb  ldc.i4.s 0x11
0x37b0ed  ldstr    aPush// ".Push"
0x37b0f2  stelem.ref
0x37b0f3  ldloc.1
0x37b0f4  ldc.i4.s 0x12
0x37b0f6  ldstr    aRedo// ".Redo"
0x37b0fb  stelem.ref
0x37b0fc  ldloc.1
0x37b0fd  ldc.i4.s 0x13
0x37b0ff  ldstr    aRemove_1// ".Remove"
0x37b104  stelem.ref
0x37b105  ldloc.1
0x37b106  ldc.i4.s 0x14
0x37b108  ldstr    aRename_0// ".Rename"
0x37b10d  stelem.ref
0x37b10e  ldloc.1
0x37b10f  ldc.i4.s 0x15
0x37b111  ldstr    aReset// ".Reset"
0x37b116  stelem.ref
0x37b117  ldloc.1
0x37b118  ldc.i4.s 0x16
0x37b11a  ldstr    aResize// ".Resize"
0x37b11f  stelem.ref
0x37b120  ldloc.1
0x37b121  ldc.i4.s 0x17
0x37b123  ldstr    aSearch_1// ".Search"
0x37b128  stelem.ref
0x37b129  ldloc.1
0x37b12a  ldc.i4.s 0x18
0x37b12c  ldstr    aSelect_4// ".Select"
0x37b131  stelem.ref
0x37b132  ldloc.1
0x37b133  ldc.i4.s 0x19
0x37b135  ldstr    aSet_0// ".Set"
0x37b13a  stelem.ref
0x37b13b  ldloc.1
0x37b13c  ldc.i4.s 0x1A
0x37b13e  ldstr    aShow// ".Show"
0x37b143  stelem.ref
0x37b144  ldloc.1
0x37b145  ldc.i4.s 0x1B
0x37b147  ldstr    aSkip// ".Skip"
0x37b14c  stelem.ref
0x37b14d  ldloc.1
0x37b14e  ldc.i4.s 0x1C
0x37b150  ldstr    aSplit// ".Split"
0x37b155  stelem.ref
0x37b156  ldloc.1
0x37b157  ldc.i4.s 0x1D
0x37b159  ldstr    aStep// ".Step"
0x37b15e  stelem.ref
0x37b15f  ldloc.1
0x37b160  ldc.i4.s 0x1E
0x37b162  ldstr    aSwitch// ".Switch"
0x37b167  stelem.ref
0x37b168  ldloc.1
0x37b169  ldc.i4.s 0x1F
0x37b16b  ldstr    aUndo// ".Undo"
0x37b170  stelem.ref
0x37b171  ldloc.1
0x37b172  ldc.i4.s 0x20
0x37b174  ldstr    aUnlock// ".Unlock"
0x37b179  stelem.ref
0x37b17a  ldloc.1
0x37b17b  ldc.i4.s 0x21
0x37b17d  ldstr    aWatch// ".Watch"
0x37b182  stelem.ref
0x37b183  ldloc.1
0x37b184  ldc.i4.s 0x22
0x37b186  ldstr    aConnect// ".Connect"
0x37b18b  stelem.ref
0x37b18c  ldloc.1
0x37b18d  ldc.i4.s 0x23
0x37b18f  ldstr    aDisconnect// ".Disconnect"
0x37b194  stelem.ref
0x37b195  ldloc.1
0x37b196  ldc.i4.s 0x24
0x37b198  ldstr    aRead_0// ".Read"
0x37b19d  stelem.ref
0x37b19e  ldloc.1
0x37b19f  ldc.i4.s 0x25
0x37b1a1  ldstr    aReceive// ".Receive"
0x37b1a6  stelem.ref
0x37b1a7  ldloc.1
0x37b1a8  ldc.i4.s 0x26
0x37b1aa  ldstr    aSend// ".Send"
0x37b1af  stelem.ref
0x37b1b0  ldloc.1
0x37b1b1  ldc.i4.s 0x27
0x37b1b3  ldstr    aWrite_0// ".Write"
0x37b1b8  stelem.ref
0x37b1b9  ldloc.1
0x37b1ba  ldc.i4.s 0x28
0x37b1bc  ldstr    aBackup_2// ".Backup"
0x37b1c1  stelem.ref
0x37b1c2  ldloc.1
0x37b1c3  ldc.i4.s 0x29
0x37b1c5  ldstr    aCheckpoint// ".Checkpoint"
0x37b1ca  stelem.ref
0x37b1cb  ldloc.1
0x37b1cc  ldc.i4.s 0x2A
0x37b1ce  ldstr    aCompare// ".Compare"
0x37b1d3  stelem.ref
0x37b1d4  ldloc.1
0x37b1d5  ldc.i4.s 0x2B
0x37b1d7  ldstr    aCompress// ".Compress"
0x37b1dc  stelem.ref
0x37b1dd  ldloc.1
0x37b1de  ldc.i4.s 0x2C
0x37b1e0  ldstr    aConvert_0// ".Convert"
0x37b1e5  stelem.ref
0x37b1e6  ldloc.1
0x37b1e7  ldc.i4.s 0x2D
0x37b1e9  ldstr    aConvertfrom// ".ConvertFrom"
0x37b1ee  stelem.ref
0x37b1ef  ldloc.1
0x37b1f0  ldc.i4.s 0x2E
0x37b1f2  ldstr    aConvertto// ".ConvertTo"
0x37b1f7  stelem.ref
0x37b1f8  ldloc.1
0x37b1f9  ldc.i4.s 0x2F
0x37b1fb  ldstr    aDismount// ".Dismount"
0x37b200  stelem.ref
0x37b201  ldloc.1
0x37b202  ldc.i4.s 0x30
0x37b204  ldstr    aEdit_1// ".Edit"
0x37b209  stelem.ref
0x37b20a  ldloc.1
0x37b20b  ldc.i4.s 0x31
0x37b20d  ldstr    aExpand// ".Expand"
0x37b212  stelem.ref
0x37b213  ldloc.1
0x37b214  ldc.i4.s 0x32
0x37b216  ldstr    aExport// ".Export"
0x37b21b  stelem.ref
0x37b21c  ldloc.1
0x37b21d  ldc.i4.s 0x33
0x37b21f  ldstr    aGroup_3// ".Group"
0x37b224  stelem.ref
0x37b225  ldloc.1
0x37b226  ldc.i4.s 0x34
0x37b228  ldstr    aImport_0// ".Import"
0x37b22d  stelem.ref
0x37b22e  ldloc.1
0x37b22f  ldc.i4.s 0x35
0x37b231  ldstr    aInitialize// ".Initialize"
0x37b236  stelem.ref
0x37b237  ldloc.1
0x37b238  ldc.i4.s 0x36
0x37b23a  ldstr    aLimit_0// ".Limit"
0x37b23f  stelem.ref
0x37b240  ldloc.1
0x37b241  ldc.i4.s 0x37
0x37b243  ldstr    aMerge_0// ".Merge"
0x37b248  stelem.ref
0x37b249  ldloc.1
0x37b24a  ldc.i4.s 0x38
0x37b24c  ldstr    aMount// ".Mount"
0x37b251  stelem.ref
0x37b252  ldloc.1
0x37b253  ldc.i4.s 0x39
0x37b255  ldstr    aOut_0// ".Out"
0x37b25a  stelem.ref
0x37b25b  ldloc.1
0x37b25c  ldc.i4.s 0x3A
0x37b25e  ldstr    aPublish_0// ".Publish"
0x37b263  stelem.ref
0x37b264  ldloc.1
0x37b265  ldc.i4.s 0x3B
0x37b267  ldstr    aRestore_0// ".Restore"
0x37b26c  stelem.ref
0x37b26d  ldloc.1
0x37b26e  ldc.i4.s 0x3C
0x37b270  ldstr    aSave// ".Save"
0x37b275  stelem.ref
0x37b276  ldloc.1
0x37b277  ldc.i4.s 0x3D
  ... truncated ...
```
