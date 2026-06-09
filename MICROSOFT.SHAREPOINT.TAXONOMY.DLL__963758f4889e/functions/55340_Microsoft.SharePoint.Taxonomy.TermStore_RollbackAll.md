# Microsoft.SharePoint.Taxonomy.TermStore::RollbackAll

- ea: `0x55340`
- end: `0x5537e`
- name: `Microsoft.SharePoint.Taxonomy.TermStore::RollbackAll`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2b280`
- `0x56c30`
- `0x57230`

## string_xrefs

- `0x5534c`: `Begin: TermStore.RollbackAll()`
- `0x55373`: `Begin: TermStore.RollbackAll()`

## pseudocode

```c

```

## disassembly

```asm
0x55340  ldc.i4   0x37787461
0x55345  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5534a  ldc.i4.s 0x64
0x5534c  ldstr    aBeginTermstore_11// "Begin: TermStore.RollbackAll()"
0x55351  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x55356  ldarg.0
0x55357  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::RequireOnline()
0x5535c  ldarg.0
0x5535d  call     instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x55362  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Sandbox::RollbackSandbox()
0x55367  ldc.i4   0x37787462
0x5536c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x55371  ldc.i4.s 0x64
0x55373  ldstr    aBeginTermstore_11// "Begin: TermStore.RollbackAll()"
0x55378  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x5537d  ret
```
