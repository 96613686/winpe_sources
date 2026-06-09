# Microsoft.SharePoint.Taxonomy.Internal.Sandbox::CommitSandbox

- ea: `0x2b020`
- end: `0x2b08c`
- name: `Microsoft.SharePoint.Taxonomy.Internal.Sandbox::CommitSandbox`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x53f80`

## callees

- `0x26950`
- `0x2b020`
- `0x2b3c0`
- `0x2b930`
- `0x2ba10`

## string_xrefs

- `0x2b02c`: `Begin committing sandbox`
- `0x2b081`: `Committed sandbox successfully.`

## pseudocode

```c

```

## disassembly

```asm
0x2b020  ldc.i4   0x32657468
0x2b025  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b02a  ldc.i4.s 0x64
0x2b02c  ldstr    aBeginCommittin// "Begin committing sandbox"
0x2b031  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2b036  ldarg.0
0x2b037  call     instance bool Microsoft.SharePoint.Taxonomy.Internal.Sandbox::get_HasAnyItems()
0x2b03c  brfalse.s loc_2B05F
0x2b03e  ldarg.0
0x2b03f  call     instance string Microsoft.SharePoint.Taxonomy.Internal.Sandbox::GenerateFullSandboxItemsXml()
0x2b044  stloc.0
0x2b045  ldc.i4.0
0x2b046  stloc.1
0x2b047  ldarg.0
0x2b048  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager Microsoft.SharePoint.Taxonomy.Internal.Sandbox::dataAccessManager
0x2b04d  ldloc.0
0x2b04e  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.DataAccessManager::Write(string data)
0x2b053  ldc.i4.1
0x2b054  stloc.1
0x2b055  leave.s  loc_2B075
0x2b057  ldarg.0
0x2b058  ldloc.1
0x2b059  call     instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::ClearSandbox(bool doRefreshCache)
0x2b05e  endfinally
0x2b05f  ldc.i4   0xC4708
0x2b064  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b069  ldc.i4.s 0x64
0x2b06b  ldstr    aSkipBecauseThe// "Skip because there is no item in the sa"...
0x2b070  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2b075  ldc.i4   0x32657469
0x2b07a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b07f  ldc.i4.s 0x64
0x2b081  ldstr    aCommittedSandb// "Committed sandbox successfully."
0x2b086  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2b08b  ret
```
