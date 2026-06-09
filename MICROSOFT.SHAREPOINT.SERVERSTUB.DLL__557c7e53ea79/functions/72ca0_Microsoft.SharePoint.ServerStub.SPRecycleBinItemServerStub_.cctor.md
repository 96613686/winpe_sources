# Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::.cctor

- ea: `0x72ca0`
- end: `0x72d6e`
- name: `Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::.cctor`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x72d3d`: `DeletedBy`
- `0x72cba`: `DeletedByEmail`
- `0x72cc2`: `DeletedByName`
- `0x72cca`: `DeletedDate`
- `0x72cd2`: `DeletedDateLocalFormatted`
- `0x72ce2`: `DirNamePath`
- `0x72d0e`: `LeafNamePath`

## pseudocode

```c

```

## disassembly

```asm
0x72ca0  ldc.i4.s 0xF
0x72ca2  newarr   [mscorlib]System.String
0x72ca7  stloc.0
0x72ca8  ldloc.0
0x72ca9  ldc.i4.0
0x72caa  ldstr    aAuthoremail// "AuthorEmail"
0x72caf  stelem.ref
0x72cb0  ldloc.0
0x72cb1  ldc.i4.1
0x72cb2  ldstr    aAuthorname// "AuthorName"
0x72cb7  stelem.ref
0x72cb8  ldloc.0
0x72cb9  ldc.i4.2
0x72cba  ldstr    aDeletedbyemail// "DeletedByEmail"
0x72cbf  stelem.ref
0x72cc0  ldloc.0
0x72cc1  ldc.i4.3
0x72cc2  ldstr    aDeletedbyname// "DeletedByName"
0x72cc7  stelem.ref
0x72cc8  ldloc.0
0x72cc9  ldc.i4.4
0x72cca  ldstr    aDeleteddate// "DeletedDate"
0x72ccf  stelem.ref
0x72cd0  ldloc.0
0x72cd1  ldc.i4.5
0x72cd2  ldstr    aDeleteddateloc// "DeletedDateLocalFormatted"
0x72cd7  stelem.ref
0x72cd8  ldloc.0
0x72cd9  ldc.i4.6
0x72cda  ldstr    aDirname// "DirName"
0x72cdf  stelem.ref
0x72ce0  ldloc.0
0x72ce1  ldc.i4.7
0x72ce2  ldstr    aDirnamepath// "DirNamePath"
0x72ce7  stelem.ref
0x72ce8  ldloc.0
0x72ce9  ldc.i4.8
0x72cea  ldstr    aId_0// "Id"
0x72cef  stelem.ref
0x72cf0  ldloc.0
0x72cf1  ldc.i4.s 9
0x72cf3  ldstr    aItemstate// "ItemState"
0x72cf8  stelem.ref
0x72cf9  ldloc.0
0x72cfa  ldc.i4.s 0xA
0x72cfc  ldstr    aItemtype// "ItemType"
0x72d01  stelem.ref
0x72d02  ldloc.0
0x72d03  ldc.i4.s 0xB
0x72d05  ldstr    aLeafname_0// "LeafName"
0x72d0a  stelem.ref
0x72d0b  ldloc.0
0x72d0c  ldc.i4.s 0xC
0x72d0e  ldstr    aLeafnamepath// "LeafNamePath"
0x72d13  stelem.ref
0x72d14  ldloc.0
0x72d15  ldc.i4.s 0xD
0x72d17  ldstr    aSize_0// "Size"
0x72d1c  stelem.ref
0x72d1d  ldloc.0
0x72d1e  ldc.i4.s 0xE
0x72d20  ldstr    aTitle// "Title"
0x72d25  stelem.ref
0x72d26  ldloc.0
0x72d27  stsfld   string[] Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::s_valueProperties
0x72d2c  ldc.i4.2
0x72d2d  newarr   [mscorlib]System.String
0x72d32  stloc.1
0x72d33  ldloc.1
0x72d34  ldc.i4.0
0x72d35  ldstr    aAuthor_0// "Author"
0x72d3a  stelem.ref
0x72d3b  ldloc.1
0x72d3c  ldc.i4.1
0x72d3d  ldstr    aDeletedby// "DeletedBy"
0x72d42  stelem.ref
0x72d43  ldloc.1
0x72d44  stsfld   string[] Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::s_refProperties
0x72d49  ldstr    a5ebf462e9e9a44// "{5ebf462e-9e9a-440c-992b-abbb3916563d}"
0x72d4e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x72d53  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::s_targetTypeId
0x72d58  ldc.i4.1
0x72d59  newarr   [mscorlib]System.String
0x72d5e  stloc.2
0x72d5f  ldloc.2
0x72d60  ldc.i4.0
0x72d61  ldstr    aId_0// "Id"
0x72d66  stelem.ref
0x72d67  ldloc.2
0x72d68  stsfld   string[] Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::s_keyProperties
0x72d6d  ret
```
