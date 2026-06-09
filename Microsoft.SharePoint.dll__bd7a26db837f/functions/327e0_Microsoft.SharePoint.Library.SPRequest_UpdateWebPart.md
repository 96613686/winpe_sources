# Microsoft.SharePoint.Library.SPRequest::UpdateWebPart

- ea: `0x327e0`
- end: `0x331f2`
- name: `Microsoft.SharePoint.Library.SPRequest::UpdateWebPart`
- size: `2578`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9eff20`

## callees

- `0x30b0`
- `0x327e0`
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

- `0x327ec`: `SPRequest.UpdateWebPart`
- `0x32870`: `UpdateWebPart`
- `0x32a4a`: `UpdateWebPart`
- `0x32c25`: `UpdateWebPart`
- `0x32e17`: `UpdateWebPart`
- `0x32ffe`: `UpdateWebPart`
- `0x3289f`: `fSaveCompressed`
- `0x32a79`: `fSaveCompressed`
- `0x32c54`: `fSaveCompressed`
- `0x32e46`: `fSaveCompressed`
- `0x3302d`: `fSaveCompressed`
- `0x32939`: `pWebPartUpdater`
- `0x32b13`: `pWebPartUpdater`
- `0x32cee`: `pWebPartUpdater`
- `0x32ee0`: `pWebPartUpdater`
- `0x330c7`: `pWebPartUpdater`

## pseudocode

```c

```

## disassembly

```asm
0x327e0  ldc.i4   0x66366C37
0x327e5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x327ea  ldc.i4.s 0x64
0x327ec  ldstr    aSprequestUpdat_8// "SPRequest.UpdateWebPart"
0x327f1  ldc.i4.1
0x327f2  ldc.i4.2
0x327f3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x327f8  stloc.s  5
0x327fa  ldloc.s  5
0x327fc  ldc.i4.0
0x327fd  ldc.i4   0x96
0x32802  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x32807  stelem.ref
0x32808  ldloc.s  5
0x3280a  ldc.i4.1
0x3280b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x32810  stelem.ref
0x32811  ldloc.s  5
0x32813  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x32818  stloc.s  6
0x3281a  ldarg.0
0x3281b  dup
0x3281c  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x32821  ldc.i4.1
0x32822  add
0x32823  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x32828  ldarg.0
0x32829  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x3282e  ldarg.0
0x3282f  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x32834  ldarg.1
0x32835  ldarg.2
0x32836  ldarg.3
0x32837  ldarg.s  4
0x32839  ldarg.s  5
0x3283b  ldarg.s  6
0x3283d  ldarg.s  7
0x3283f  ldarg.s  8
0x32841  ldarg.s  9
0x32843  ldarg.s  0xA
0x32845  ldarg.s  0xB
0x32847  ldarg.s  0xC
0x32849  ldarg.s  0xD
0x3284b  ldarg.s  0xE
0x3284d  ldarg.s  0xF
0x3284f  ldarg.s  0x10
0x32851  ldarg.s  0x11
0x32853  ldarg.s  0x12
0x32855  ldarg.s  0x13
0x32857  ldarg.s  0x14
0x32859  ldarg.s  0x15
0x3285b  ldarg.s  0x16
0x3285d  ldarg.s  0x17
0x3285f  ldarg.s  0x18
0x32861  ldarg.s  0x19
0x32863  ldarg.s  0x1A
0x32865  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::UpdateWebPart(string, bool, bool, string, string, string, string, string, string, string, bool, unsigned int8, string, int32, string, string, unsigned int8[]&, unsigned int8[]&, string, string[]&, bool, native int, string, int32, int32, int32)
0x3286a  leave    loc_331D2
0x3286f  stloc.0
0x32870  ldstr    aUpdatewebpart// "UpdateWebPart"
0x32875  ldarg.0
0x32876  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x3287b  ldarg.0
0x3287c  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x32881  ldc.i4.s 0x17
0x32883  newarr   [mscorlib]System.String
0x32888  stloc.s  7
0x3288a  ldloc.s  7
0x3288c  ldc.i4.0
0x3288d  ldstr    aBstrweburl// "bstrWebUrl"
0x32892  stelem.ref
0x32893  ldloc.s  7
0x32895  ldc.i4.1
0x32896  ldstr    aFallusers// "fAllUsers"
0x3289b  stelem.ref
0x3289c  ldloc.s  7
0x3289e  ldc.i4.2
0x3289f  ldstr    aFsavecompresse// "fSaveCompressed"
0x328a4  stelem.ref
0x328a5  ldloc.s  7
0x328a7  ldc.i4.3
0x328a8  ldstr    aBstrid// "bstrID"
0x328ad  stelem.ref
0x328ae  ldloc.s  7
0x328b0  ldc.i4.4
0x328b1  ldstr    aBstrfullpageur// "bstrFullPageUrl"
0x328b6  stelem.ref
0x328b7  ldloc.s  7
0x328b9  ldc.i4.5
0x328ba  ldstr    aBstrwebparttyp// "bstrWebPartTypeID"
0x328bf  stelem.ref
0x328c0  ldloc.s  7
0x328c2  ldc.i4.6
0x328c3  ldstr    aBstrassembly// "bstrAssembly"
0x328c8  stelem.ref
0x328c9  ldloc.s  7
0x328cb  ldc.i4.7
0x328cc  ldstr    aBstrclass// "bstrClass"
0x328d1  stelem.ref
0x328d2  ldloc.s  7
0x328d4  ldc.i4.8
0x328d5  ldstr    aBstrsolutionid// "bstrSolutionId"
0x328da  stelem.ref
0x328db  ldloc.s  7
0x328dd  ldc.i4.s 9
0x328df  ldstr    aBstrsolutionwe// "bstrSolutionWebId"
0x328e4  stelem.ref
0x328e5  ldloc.s  7
0x328e7  ldc.i4.s 0xA
0x328e9  ldstr    aFisincluded// "fIsIncluded"
0x328ee  stelem.ref
0x328ef  ldloc.s  7
0x328f1  ldc.i4.s 0xB
0x328f3  ldstr    aBframestate// "bFrameState"
0x328f8  stelem.ref
0x328f9  ldloc.s  7
0x328fb  ldc.i4.s 0xC
0x328fd  ldstr    aBstrzoneid// "bstrZoneID"
0x32902  stelem.ref
0x32903  ldloc.s  7
0x32905  ldc.i4.s 0xD
0x32907  ldstr    aLpartorder// "lPartOrder"
0x3290c  stelem.ref
0x3290d  ldloc.s  7
0x3290f  ldc.i4.s 0xE
0x32911  ldstr    aBstrcontenttyp_1// "bstrContentTypeId"
0x32916  stelem.ref
0x32917  ldloc.s  7
0x32919  ldc.i4.s 0xF
0x3291b  ldstr    aBstrsource// "bstrSource"
0x32920  stelem.ref
0x32921  ldloc.s  7
0x32923  ldc.i4.s 0x10
0x32925  ldstr    aBstrwebpartid// "bstrWebPartID"
0x3292a  stelem.ref
0x3292b  ldloc.s  7
0x3292d  ldc.i4.s 0x11
0x3292f  ldstr    aFhttpget// "fHttpGet"
0x32934  stelem.ref
0x32935  ldloc.s  7
0x32937  ldc.i4.s 0x12
0x32939  ldstr    aPwebpartupdate// "pWebPartUpdater"
0x3293e  stelem.ref
0x3293f  ldloc.s  7
0x32941  ldc.i4.s 0x13
0x32943  ldstr    aBstrlistid// "bstrListId"
0x32948  stelem.ref
0x32949  ldloc.s  7
0x3294b  ldc.i4.s 0x14
0x3294d  ldstr    aLflags// "lFlags"
0x32952  stelem.ref
0x32953  ldloc.s  7
0x32955  ldc.i4.s 0x15
0x32957  ldstr    aLtype// "lType"
0x3295c  stelem.ref
0x3295d  ldloc.s  7
0x3295f  ldc.i4.s 0x16
0x32961  ldstr    aLbaseviewid// "lBaseViewID"
0x32966  stelem.ref
0x32967  ldloc.s  7
0x32969  ldc.i4.s 0x17
0x3296b  newarr   [mscorlib]System.Object
0x32970  stloc.s  8
0x32972  ldloc.s  8
0x32974  ldc.i4.0
0x32975  ldarg.1
0x32976  stelem.ref
0x32977  ldloc.s  8
0x32979  ldc.i4.1
0x3297a  ldarg.2
0x3297b  box      [mscorlib]System.Boolean
0x32980  stelem.ref
0x32981  ldloc.s  8
0x32983  ldc.i4.2
0x32984  ldarg.3
0x32985  box      [mscorlib]System.Boolean
0x3298a  stelem.ref
0x3298b  ldloc.s  8
0x3298d  ldc.i4.3
0x3298e  ldarg.s  4
0x32990  stelem.ref
0x32991  ldloc.s  8
0x32993  ldc.i4.4
0x32994  ldarg.s  5
0x32996  stelem.ref
0x32997  ldloc.s  8
0x32999  ldc.i4.5
0x3299a  ldarg.s  6
0x3299c  stelem.ref
0x3299d  ldloc.s  8
0x3299f  ldc.i4.6
0x329a0  ldarg.s  7
0x329a2  stelem.ref
0x329a3  ldloc.s  8
0x329a5  ldc.i4.7
0x329a6  ldarg.s  8
0x329a8  stelem.ref
0x329a9  ldloc.s  8
0x329ab  ldc.i4.8
0x329ac  ldarg.s  9
0x329ae  stelem.ref
0x329af  ldloc.s  8
0x329b1  ldc.i4.s 9
0x329b3  ldarg.s  0xA
0x329b5  stelem.ref
0x329b6  ldloc.s  8
0x329b8  ldc.i4.s 0xA
0x329ba  ldarg.s  0xB
0x329bc  box      [mscorlib]System.Boolean
0x329c1  stelem.ref
0x329c2  ldloc.s  8
0x329c4  ldc.i4.s 0xB
0x329c6  ldarg.s  0xC
0x329c8  box      [mscorlib]System.Byte
0x329cd  stelem.ref
0x329ce  ldloc.s  8
0x329d0  ldc.i4.s 0xC
0x329d2  ldarg.s  0xD
0x329d4  stelem.ref
0x329d5  ldloc.s  8
0x329d7  ldc.i4.s 0xD
0x329d9  ldarg.s  0xE
0x329db  box      [mscorlib]System.Int32
0x329e0  stelem.ref
0x329e1  ldloc.s  8
0x329e3  ldc.i4.s 0xE
0x329e5  ldarg.s  0xF
0x329e7  stelem.ref
0x329e8  ldloc.s  8
0x329ea  ldc.i4.s 0xF
0x329ec  ldarg.s  0x10
0x329ee  stelem.ref
0x329ef  ldloc.s  8
0x329f1  ldc.i4.s 0x10
0x329f3  ldarg.s  0x13
0x329f5  stelem.ref
0x329f6  ldloc.s  8
0x329f8  ldc.i4.s 0x11
0x329fa  ldarg.s  0x15
0x329fc  box      [mscorlib]System.Boolean
0x32a01  stelem.ref
0x32a02  ldloc.s  8
0x32a04  ldc.i4.s 0x12
0x32a06  ldarg.s  0x16
0x32a08  box      [mscorlib]System.IntPtr
0x32a0d  stelem.ref
0x32a0e  ldloc.s  8
0x32a10  ldc.i4.s 0x13
0x32a12  ldarg.s  0x17
0x32a14  stelem.ref
0x32a15  ldloc.s  8
0x32a17  ldc.i4.s 0x14
0x32a19  ldarg.s  0x18
0x32a1b  box      [mscorlib]System.Int32
0x32a20  stelem.ref
0x32a21  ldloc.s  8
0x32a23  ldc.i4.s 0x15
0x32a25  ldarg.s  0x19
0x32a27  box      [mscorlib]System.Int32
0x32a2c  stelem.ref
0x32a2d  ldloc.s  8
0x32a2f  ldc.i4.s 0x16
0x32a31  ldarg.s  0x1A
0x32a33  box      [mscorlib]System.Int32
0x32a38  stelem.ref
0x32a39  ldloc.s  8
0x32a3b  ldloc.0
0x32a3c  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x32a41  ldloc.0
0x32a42  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x32a47  rethrow
0x32a49  stloc.1
0x32a4a  ldstr    aUpdatewebpart// "UpdateWebPart"
0x32a4f  ldarg.0
0x32a50  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x32a55  ldarg.0
0x32a56  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x32a5b  ldc.i4.s 0x17
0x32a5d  newarr   [mscorlib]System.String
0x32a62  stloc.s  9
0x32a64  ldloc.s  9
0x32a66  ldc.i4.0
0x32a67  ldstr    aBstrweburl// "bstrWebUrl"
0x32a6c  stelem.ref
0x32a6d  ldloc.s  9
0x32a6f  ldc.i4.1
0x32a70  ldstr    aFallusers// "fAllUsers"
0x32a75  stelem.ref
0x32a76  ldloc.s  9
0x32a78  ldc.i4.2
0x32a79  ldstr    aFsavecompresse// "fSaveCompressed"
0x32a7e  stelem.ref
0x32a7f  ldloc.s  9
0x32a81  ldc.i4.3
0x32a82  ldstr    aBstrid// "bstrID"
0x32a87  stelem.ref
0x32a88  ldloc.s  9
0x32a8a  ldc.i4.4
0x32a8b  ldstr    aBstrfullpageur// "bstrFullPageUrl"
0x32a90  stelem.ref
  ... truncated ...
```
