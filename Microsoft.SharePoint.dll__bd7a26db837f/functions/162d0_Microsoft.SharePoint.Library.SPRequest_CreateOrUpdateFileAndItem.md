# Microsoft.SharePoint.Library.SPRequest::CreateOrUpdateFileAndItem

- ea: `0x162d0`
- end: `0x16a92`
- name: `Microsoft.SharePoint.Library.SPRequest::CreateOrUpdateFileAndItem`
- size: `1986`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5f6a50`

## callees

- `0x30b0`
- `0x162d0`
- `0x4727e0`
- `0x472800`
- `0x4729d0`
- `0x472c90`
- `0x472d60`
- `0x7b4dd0`
- `0x7c78d0`
- `0x7c89b0`
- `0x957470`

## string_xrefs

- `0x162dc`: `SPRequest.CreateOrUpdateFileAndItem`
- `0x16354`: `CreateOrUpdateFileAndItem`
- `0x164ba`: `CreateOrUpdateFileAndItem`
- `0x16621`: `CreateOrUpdateFileAndItem`
- `0x1679f`: `CreateOrUpdateFileAndItem`
- `0x16912`: `CreateOrUpdateFileAndItem`
- `0x1639e`: `bstrCreatedBy`
- `0x16504`: `bstrCreatedBy`
- `0x1666b`: `bstrCreatedBy`
- `0x167e9`: `bstrCreatedBy`
- `0x1695c`: `bstrCreatedBy`
- `0x163b0`: `iCreatedByID`
- `0x16516`: `iCreatedByID`
- `0x1667d`: `iCreatedByID`
- `0x167fb`: `iCreatedByID`
- `0x1696e`: `iCreatedByID`
- `0x163cd`: `varTimeCreated`
- `0x16533`: `varTimeCreated`
- `0x1669a`: `varTimeCreated`
- `0x16818`: `varTimeCreated`
- `0x1698b`: `varTimeCreated`
- `0x163eb`: `checkInComment`
- `0x16551`: `checkInComment`
- `0x166b8`: `checkInComment`
- `0x16836`: `checkInComment`
- `0x169a9`: `checkInComment`

## pseudocode

```c

```

## disassembly

```asm
0x162d0  ldc.i4   0x66366C37
0x162d5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x162da  ldc.i4.s 0x64
0x162dc  ldstr    aSprequestCreat_2// "SPRequest.CreateOrUpdateFileAndItem"
0x162e1  ldc.i4.1
0x162e2  ldc.i4.2
0x162e3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x162e8  stloc.s  5
0x162ea  ldloc.s  5
0x162ec  ldc.i4.0
0x162ed  ldc.i4   0x96
0x162f2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x162f7  stelem.ref
0x162f8  ldloc.s  5
0x162fa  ldc.i4.1
0x162fb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x16300  stelem.ref
0x16301  ldloc.s  5
0x16303  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x16308  stloc.s  6
0x1630a  ldarg.0
0x1630b  dup
0x1630c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x16311  ldc.i4.1
0x16312  add
0x16313  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x16318  ldarg.0
0x16319  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x1631e  ldarg.0
0x1631f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x16324  ldarg.1
0x16325  ldarg.2
0x16326  ldarg.3
0x16327  ldarg.s  4
0x16329  ldarg.s  5
0x1632b  ldarg.s  6
0x1632d  ldarg.s  7
0x1632f  ldarg.s  8
0x16331  ldarg.s  9
0x16333  ldarg.s  0xA
0x16335  ldarg.s  0xB
0x16337  ldarg.s  0xC
0x16339  ldarg.s  0xD
0x1633b  ldarg.s  0xE
0x1633d  ldarg.s  0xF
0x1633f  ldarg.s  0x10
0x16341  ldarg.s  0x11
0x16343  ldarg.s  0x12
0x16345  ldarg.s  0x13
0x16347  ldarg.s  0x14
0x16349  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::CreateOrUpdateFileAndItem(string, string, valuetype [mscorlib]System.Guid&, object, int32, int32, string, string, int32, int32, int32, object, object, object, string, int32, string, int32, unsigned int32&, string&)
0x1634e  leave    loc_16A72
0x16353  stloc.0
0x16354  ldstr    aCreateorupdate// "CreateOrUpdateFileAndItem"
0x16359  ldarg.0
0x1635a  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x1635f  ldarg.0
0x16360  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x16365  ldc.i4.s 0x11
0x16367  newarr   [mscorlib]System.String
0x1636c  stloc.s  7
0x1636e  ldloc.s  7
0x16370  ldc.i4.0
0x16371  ldstr    aBstrurl// "bstrUrl"
0x16376  stelem.ref
0x16377  ldloc.s  7
0x16379  ldc.i4.1
0x1637a  ldstr    aBstrwebrelativ// "bstrWebRelativeUrl"
0x1637f  stelem.ref
0x16380  ldloc.s  7
0x16382  ldc.i4.2
0x16383  ldstr    aPunkdoc// "punkDoc"
0x16388  stelem.ref
0x16389  ldloc.s  7
0x1638b  ldc.i4.3
0x1638c  ldstr    aDoclength// "docLength"
0x16391  stelem.ref
0x16392  ldloc.s  7
0x16394  ldc.i4.4
0x16395  ldstr    aExists// "exists"
0x1639a  stelem.ref
0x1639b  ldloc.s  7
0x1639d  ldc.i4.5
0x1639e  ldstr    aBstrcreatedby// "bstrCreatedBy"
0x163a3  stelem.ref
0x163a4  ldloc.s  7
0x163a6  ldc.i4.6
0x163a7  ldstr    aBstrmodifiedby// "bstrModifiedBy"
0x163ac  stelem.ref
0x163ad  ldloc.s  7
0x163af  ldc.i4.7
0x163b0  ldstr    aIcreatedbyid// "iCreatedByID"
0x163b5  stelem.ref
0x163b6  ldloc.s  7
0x163b8  ldc.i4.8
0x163b9  ldstr    aImodifiedbyid// "iModifiedByID"
0x163be  stelem.ref
0x163bf  ldloc.s  7
0x163c1  ldc.i4.s 9
0x163c3  ldstr    aIversion// "iVersion"
0x163c8  stelem.ref
0x163c9  ldloc.s  7
0x163cb  ldc.i4.s 0xA
0x163cd  ldstr    aVartimecreated// "varTimeCreated"
0x163d2  stelem.ref
0x163d3  ldloc.s  7
0x163d5  ldc.i4.s 0xB
0x163d7  ldstr    aVartimelastmod// "varTimeLastModified"
0x163dc  stelem.ref
0x163dd  ldloc.s  7
0x163df  ldc.i4.s 0xC
0x163e1  ldstr    aVarproperties// "varProperties"
0x163e6  stelem.ref
0x163e7  ldloc.s  7
0x163e9  ldc.i4.s 0xD
0x163eb  ldstr    aCheckincomment// "checkInComment"
0x163f0  stelem.ref
0x163f1  ldloc.s  7
0x163f3  ldc.i4.s 0xE
0x163f5  ldstr    aDoclibrowid// "docLibRowID"
0x163fa  stelem.ref
0x163fb  ldloc.s  7
0x163fd  ldc.i4.s 0xF
0x163ff  ldstr    aBstrlistname// "bstrListName"
0x16404  stelem.ref
0x16405  ldloc.s  7
0x16407  ldc.i4.s 0x10
0x16409  ldstr    aBnoexecute// "bNoExecute"
0x1640e  stelem.ref
0x1640f  ldloc.s  7
0x16411  ldc.i4.s 0x11
0x16413  newarr   [mscorlib]System.Object
0x16418  stloc.s  8
0x1641a  ldloc.s  8
0x1641c  ldc.i4.0
0x1641d  ldarg.1
0x1641e  stelem.ref
0x1641f  ldloc.s  8
0x16421  ldc.i4.1
0x16422  ldarg.2
0x16423  stelem.ref
0x16424  ldloc.s  8
0x16426  ldc.i4.2
0x16427  ldarg.s  4
0x16429  stelem.ref
0x1642a  ldloc.s  8
0x1642c  ldc.i4.3
0x1642d  ldarg.s  5
0x1642f  box      [mscorlib]System.Int32
0x16434  stelem.ref
0x16435  ldloc.s  8
0x16437  ldc.i4.4
0x16438  ldarg.s  6
0x1643a  box      [mscorlib]System.Int32
0x1643f  stelem.ref
0x16440  ldloc.s  8
0x16442  ldc.i4.5
0x16443  ldarg.s  7
0x16445  stelem.ref
0x16446  ldloc.s  8
0x16448  ldc.i4.6
0x16449  ldarg.s  8
0x1644b  stelem.ref
0x1644c  ldloc.s  8
0x1644e  ldc.i4.7
0x1644f  ldarg.s  9
0x16451  box      [mscorlib]System.Int32
0x16456  stelem.ref
0x16457  ldloc.s  8
0x16459  ldc.i4.8
0x1645a  ldarg.s  0xA
0x1645c  box      [mscorlib]System.Int32
0x16461  stelem.ref
0x16462  ldloc.s  8
0x16464  ldc.i4.s 9
0x16466  ldarg.s  0xB
0x16468  box      [mscorlib]System.Int32
0x1646d  stelem.ref
0x1646e  ldloc.s  8
0x16470  ldc.i4.s 0xA
0x16472  ldarg.s  0xC
0x16474  stelem.ref
0x16475  ldloc.s  8
0x16477  ldc.i4.s 0xB
0x16479  ldarg.s  0xD
0x1647b  stelem.ref
0x1647c  ldloc.s  8
0x1647e  ldc.i4.s 0xC
0x16480  ldarg.s  0xE
0x16482  stelem.ref
0x16483  ldloc.s  8
0x16485  ldc.i4.s 0xD
0x16487  ldarg.s  0xF
0x16489  stelem.ref
0x1648a  ldloc.s  8
0x1648c  ldc.i4.s 0xE
0x1648e  ldarg.s  0x10
0x16490  box      [mscorlib]System.Int32
0x16495  stelem.ref
0x16496  ldloc.s  8
0x16498  ldc.i4.s 0xF
0x1649a  ldarg.s  0x11
0x1649c  stelem.ref
0x1649d  ldloc.s  8
0x1649f  ldc.i4.s 0x10
0x164a1  ldarg.s  0x12
0x164a3  box      [mscorlib]System.Int32
0x164a8  stelem.ref
0x164a9  ldloc.s  8
0x164ab  ldloc.0
0x164ac  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x164b1  ldloc.0
0x164b2  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x164b7  rethrow
0x164b9  stloc.1
0x164ba  ldstr    aCreateorupdate// "CreateOrUpdateFileAndItem"
0x164bf  ldarg.0
0x164c0  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x164c5  ldarg.0
0x164c6  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x164cb  ldc.i4.s 0x11
0x164cd  newarr   [mscorlib]System.String
0x164d2  stloc.s  9
0x164d4  ldloc.s  9
0x164d6  ldc.i4.0
0x164d7  ldstr    aBstrurl// "bstrUrl"
0x164dc  stelem.ref
0x164dd  ldloc.s  9
0x164df  ldc.i4.1
0x164e0  ldstr    aBstrwebrelativ// "bstrWebRelativeUrl"
0x164e5  stelem.ref
0x164e6  ldloc.s  9
0x164e8  ldc.i4.2
0x164e9  ldstr    aPunkdoc// "punkDoc"
0x164ee  stelem.ref
0x164ef  ldloc.s  9
0x164f1  ldc.i4.3
0x164f2  ldstr    aDoclength// "docLength"
0x164f7  stelem.ref
0x164f8  ldloc.s  9
0x164fa  ldc.i4.4
0x164fb  ldstr    aExists// "exists"
0x16500  stelem.ref
0x16501  ldloc.s  9
0x16503  ldc.i4.5
0x16504  ldstr    aBstrcreatedby// "bstrCreatedBy"
0x16509  stelem.ref
0x1650a  ldloc.s  9
0x1650c  ldc.i4.6
0x1650d  ldstr    aBstrmodifiedby// "bstrModifiedBy"
0x16512  stelem.ref
0x16513  ldloc.s  9
0x16515  ldc.i4.7
0x16516  ldstr    aIcreatedbyid// "iCreatedByID"
0x1651b  stelem.ref
0x1651c  ldloc.s  9
0x1651e  ldc.i4.8
0x1651f  ldstr    aImodifiedbyid// "iModifiedByID"
0x16524  stelem.ref
0x16525  ldloc.s  9
0x16527  ldc.i4.s 9
0x16529  ldstr    aIversion// "iVersion"
0x1652e  stelem.ref
0x1652f  ldloc.s  9
0x16531  ldc.i4.s 0xA
0x16533  ldstr    aVartimecreated// "varTimeCreated"
0x16538  stelem.ref
0x16539  ldloc.s  9
0x1653b  ldc.i4.s 0xB
0x1653d  ldstr    aVartimelastmod// "varTimeLastModified"
0x16542  stelem.ref
0x16543  ldloc.s  9
0x16545  ldc.i4.s 0xC
0x16547  ldstr    aVarproperties// "varProperties"
0x1654c  stelem.ref
0x1654d  ldloc.s  9
0x1654f  ldc.i4.s 0xD
0x16551  ldstr    aCheckincomment// "checkInComment"
0x16556  stelem.ref
0x16557  ldloc.s  9
0x16559  ldc.i4.s 0xE
0x1655b  ldstr    aDoclibrowid// "docLibRowID"
0x16560  stelem.ref
0x16561  ldloc.s  9
0x16563  ldc.i4.s 0xF
0x16565  ldstr    aBstrlistname// "bstrListName"
0x1656a  stelem.ref
0x1656b  ldloc.s  9
0x1656d  ldc.i4.s 0x10
0x1656f  ldstr    aBnoexecute// "bNoExecute"
0x16574  stelem.ref
0x16575  ldloc.s  9
0x16577  ldc.i4.s 0x11
0x16579  newarr   [mscorlib]System.Object
0x1657e  stloc.s  0xA
0x16580  ldloc.s  0xA
0x16582  ldc.i4.0
0x16583  ldarg.1
0x16584  stelem.ref
0x16585  ldloc.s  0xA
  ... truncated ...
```
