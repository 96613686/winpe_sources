# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::GetPreviousChangeToken

- ea: `0xe470`
- end: `0xe572`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::GetPreviousChangeToken`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe2b0`

## callees

- `0xe470`

## string_xrefs

- `0xe481`: `MetadataHubPreviousToken`
- `0xe496`: `MetadataHubPreviousToken`
- `0xe4c4`: `The previous change token {0} on the hub site '{1}' is invalid. No changes will be processed`
- `0xe4f2`: `The previous change token {0} on the hub site '{1}' is invalid. No changes will be processed`
- `0xe521`: `The previous change token {0} on the hub site '{1}' is invalid. No changes will be processed`
- `0xe550`: `The previous change token {0} on the hub site '{1}' is invalid. No changes will be processed`

## pseudocode

```c

```

## disassembly

```asm
0xe470  ldnull
0xe471  stloc.0
0xe472  ldnull
0xe473  stloc.1
0xe474  ldarg.0
0xe475  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0xe47a  stloc.2
0xe47b  ldarg.0
0xe47c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPropertyBag [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Properties()
0xe481  ldstr    aMetadatahubpre// "MetadataHubPreviousToken"
0xe486  callvirt instance bool [System]System.Collections.Specialized.StringDictionary::ContainsKey(string)
0xe48b  brfalse  loc_E570
0xe490  ldarg.0
0xe491  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPropertyBag [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Properties()
0xe496  ldstr    aMetadatahubpre// "MetadataHubPreviousToken"
0xe49b  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0xe4a0  stloc.0
0xe4a1  ldloc.0
0xe4a2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe4a7  brtrue.s loc_E4B0
0xe4a9  ldloc.0
0xe4aa  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken::.ctor(string)
0xe4af  stloc.1
0xe4b0  leave    loc_E570
0xe4b5  pop
0xe4b6  ldnull
0xe4b7  stloc.1
0xe4b8  ldc.i4   0x38797139
0xe4bd  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe4c2  ldc.i4.s 0xF
0xe4c4  ldstr    aThePreviousCha// "The previous change token {0} on the hu"...
0xe4c9  ldc.i4.2
0xe4ca  newarr   [mscorlib]System.Object
0xe4cf  stloc.3
0xe4d0  ldloc.3
0xe4d1  ldc.i4.0
0xe4d2  ldloc.0
0xe4d3  stelem.ref
0xe4d4  ldloc.3
0xe4d5  ldc.i4.1
0xe4d6  ldloc.2
0xe4d7  stelem.ref
0xe4d8  ldloc.3
0xe4d9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xe4de  leave    loc_E570
0xe4e3  pop
0xe4e4  ldnull
0xe4e5  stloc.1
0xe4e6  ldc.i4   0x38797161
0xe4eb  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe4f0  ldc.i4.s 0xF
0xe4f2  ldstr    aThePreviousCha// "The previous change token {0} on the hu"...
0xe4f7  ldc.i4.2
0xe4f8  newarr   [mscorlib]System.Object
0xe4fd  stloc.s  4
0xe4ff  ldloc.s  4
0xe501  ldc.i4.0
0xe502  ldloc.0
0xe503  stelem.ref
0xe504  ldloc.s  4
0xe506  ldc.i4.1
0xe507  ldloc.2
0xe508  stelem.ref
0xe509  ldloc.s  4
0xe50b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xe510  leave.s  loc_E570
0xe512  pop
0xe513  ldnull
0xe514  stloc.1
0xe515  ldc.i4   0x38797162
0xe51a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe51f  ldc.i4.s 0xF
0xe521  ldstr    aThePreviousCha// "The previous change token {0} on the hu"...
0xe526  ldc.i4.2
0xe527  newarr   [mscorlib]System.Object
0xe52c  stloc.s  5
0xe52e  ldloc.s  5
0xe530  ldc.i4.0
0xe531  ldloc.0
0xe532  stelem.ref
0xe533  ldloc.s  5
0xe535  ldc.i4.1
0xe536  ldloc.2
0xe537  stelem.ref
0xe538  ldloc.s  5
0xe53a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xe53f  leave.s  loc_E570
0xe541  pop
0xe542  ldnull
0xe543  stloc.1
0xe544  ldc.i4   0x38797163
0xe549  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe54e  ldc.i4.s 0xF
0xe550  ldstr    aThePreviousCha// "The previous change token {0} on the hu"...
0xe555  ldc.i4.2
0xe556  newarr   [mscorlib]System.Object
0xe55b  stloc.s  6
0xe55d  ldloc.s  6
0xe55f  ldc.i4.0
0xe560  ldloc.0
0xe561  stelem.ref
0xe562  ldloc.s  6
0xe564  ldc.i4.1
0xe565  ldloc.2
0xe566  stelem.ref
0xe567  ldloc.s  6
0xe569  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xe56e  leave.s  loc_E570
0xe570  ldloc.1
0xe571  ret
```
