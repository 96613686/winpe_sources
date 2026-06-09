# Microsoft.SharePoint.Library.SPRequest::CreateListOnImport

- ea: `0x14f90`
- end: `0x158dc`
- name: `Microsoft.SharePoint.Library.SPRequest::CreateListOnImport`
- size: `2380`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x5ef1e0`

## callees

- `0x30b0`
- `0x14f90`
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

- `0x15050`: `lTemplateID`
- `0x15204`: `lTemplateID`
- `0x153b9`: `lTemplateID`
- `0x15585`: `lTemplateID`
- `0x15746`: `lTemplateID`
- `0x14f9c`: `SPRequest.CreateListOnImport`
- `0x15018`: `CreateListOnImport`
- `0x151cc`: `CreateListOnImport`
- `0x15381`: `CreateListOnImport`
- `0x1554d`: `CreateListOnImport`
- `0x1570e`: `CreateListOnImport`
- `0x150cd`: `guidDocTemplateId`
- `0x15281`: `guidDocTemplateId`
- `0x15436`: `guidDocTemplateId`
- `0x15602`: `guidDocTemplateId`
- `0x157c3`: `guidDocTemplateId`
- `0x150eb`: `bCompressedSchema`
- `0x1529f`: `bCompressedSchema`
- `0x15454`: `bCompressedSchema`
- `0x15620`: `bCompressedSchema`
- `0x157e1`: `bCompressedSchema`
- `0x150f5`: `dtTimeCreated`
- `0x152a9`: `dtTimeCreated`
- `0x1545e`: `dtTimeCreated`
- `0x1562a`: `dtTimeCreated`
- `0x157eb`: `dtTimeCreated`

## pseudocode

```c

```

## disassembly

```asm
0x14f90  ldc.i4   0x66366C37
0x14f95  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x14f9a  ldc.i4.s 0x64
0x14f9c  ldstr    aSprequestCreat_1// "SPRequest.CreateListOnImport"
0x14fa1  ldc.i4.1
0x14fa2  ldc.i4.2
0x14fa3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x14fa8  stloc.s  5
0x14faa  ldloc.s  5
0x14fac  ldc.i4.0
0x14fad  ldc.i4   0x96
0x14fb2  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x14fb7  stelem.ref
0x14fb8  ldloc.s  5
0x14fba  ldc.i4.1
0x14fbb  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x14fc0  stelem.ref
0x14fc1  ldloc.s  5
0x14fc3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x14fc8  stloc.s  6
0x14fca  ldarg.0
0x14fcb  dup
0x14fcc  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x14fd1  ldc.i4.1
0x14fd2  add
0x14fd3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x14fd8  ldarg.0
0x14fd9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x14fde  ldarg.0
0x14fdf  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x14fe4  ldarg.1
0x14fe5  ldarg.2
0x14fe6  ldarg.3
0x14fe7  ldarg.s  4
0x14fe9  ldarg.s  5
0x14feb  ldarg.s  6
0x14fed  ldarg.s  7
0x14fef  ldarg.s  8
0x14ff1  ldarg.s  9
0x14ff3  ldarg.s  0xA
0x14ff5  ldarg.s  0xB
0x14ff7  ldarg.s  0xC
0x14ff9  ldarg.s  0xD
0x14ffb  ldarg.s  0xE
0x14ffd  ldarg.s  0xF
0x14fff  ldarg.s  0x10
0x15001  ldarg.s  0x11
0x15003  ldarg.s  0x12
0x15005  ldarg.s  0x13
0x15007  ldarg.s  0x14
0x15009  ldarg.s  0x15
0x1500b  ldarg.s  0x16
0x1500d  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::CreateListOnImport(string, valuetype [mscorlib]System.Guid&, string, string, int32, string, valuetype [mscorlib]System.Guid, int64, int64, int32, int32, string, string, string, string, string, string, valuetype [mscorlib]System.Guid, string, string, bool, valuetype [mscorlib]System.DateTime)
0x15012  leave    loc_158BC
0x15017  stloc.0
0x15018  ldstr    aCreatelistonim// "CreateListOnImport"
0x1501d  ldarg.0
0x1501e  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x15023  ldarg.0
0x15024  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x15029  ldc.i4.s 0x15
0x1502b  newarr   [mscorlib]System.String
0x15030  stloc.s  7
0x15032  ldloc.s  7
0x15034  ldc.i4.0
0x15035  ldstr    aBstrurl// "bstrUrl"
0x1503a  stelem.ref
0x1503b  ldloc.s  7
0x1503d  ldc.i4.1
0x1503e  ldstr    aBstrtitle// "bstrTitle"
0x15043  stelem.ref
0x15044  ldloc.s  7
0x15046  ldc.i4.2
0x15047  ldstr    aBstrdescriptio// "bstrDescription"
0x1504c  stelem.ref
0x1504d  ldloc.s  7
0x1504f  ldc.i4.3
0x15050  ldstr    aLtemplateid// "lTemplateID"
0x15055  stelem.ref
0x15056  ldloc.s  7
0x15058  ldc.i4.4
0x15059  ldstr    aBstrfeatureid// "bstrFeatureId"
0x1505e  stelem.ref
0x1505f  ldloc.s  7
0x15061  ldc.i4.5
0x15062  ldstr    aGuidrootfolder// "guidRootFolderId"
0x15067  stelem.ref
0x15068  ldloc.s  7
0x1506a  ldc.i4.6
0x1506b  ldstr    aLlflags// "llFlags"
0x15070  stelem.ref
0x15071  ldloc.s  7
0x15073  ldc.i4.7
0x15074  ldstr    aLlflags2// "llFlags2"
0x15079  stelem.ref
0x1507a  ldloc.s  7
0x1507c  ldc.i4.8
0x1507d  ldstr    aIversion// "iVersion"
0x15082  stelem.ref
0x15083  ldloc.s  7
0x15085  ldc.i4.s 9
0x15087  ldstr    aIauthor// "iAuthor"
0x1508c  stelem.ref
0x1508d  ldloc.s  7
0x1508f  ldc.i4.s 0xA
0x15091  ldstr    aBstrfields// "bstrFields"
0x15096  stelem.ref
0x15097  ldloc.s  7
0x15099  ldc.i4.s 0xB
0x1509b  ldstr    aBstrcontenttyp_0// "bstrContentTypes"
0x150a0  stelem.ref
0x150a1  ldloc.s  7
0x150a3  ldc.i4.s 0xC
0x150a5  ldstr    aBstrimageurl// "bstrImageUrl"
0x150aa  stelem.ref
0x150ab  ldloc.s  7
0x150ad  ldc.i4.s 0xD
0x150af  ldstr    aBstreventsinka// "bstrEventSinkAssembly"
0x150b4  stelem.ref
0x150b5  ldloc.s  7
0x150b7  ldc.i4.s 0xE
0x150b9  ldstr    aBstreventsinkc// "bstrEventSinkClass"
0x150be  stelem.ref
0x150bf  ldloc.s  7
0x150c1  ldc.i4.s 0xF
0x150c3  ldstr    aBstreventsinkd// "bstrEventSinkData"
0x150c8  stelem.ref
0x150c9  ldloc.s  7
0x150cb  ldc.i4.s 0x10
0x150cd  ldstr    aGuiddoctemplat// "guidDocTemplateId"
0x150d2  stelem.ref
0x150d3  ldloc.s  7
0x150d5  ldc.i4.s 0x11
0x150d7  ldstr    aBstrviews// "bstrViews"
0x150dc  stelem.ref
0x150dd  ldloc.s  7
0x150df  ldc.i4.s 0x12
0x150e1  ldstr    aBstrforms// "bstrForms"
0x150e6  stelem.ref
0x150e7  ldloc.s  7
0x150e9  ldc.i4.s 0x13
0x150eb  ldstr    aBcompressedsch// "bCompressedSchema"
0x150f0  stelem.ref
0x150f1  ldloc.s  7
0x150f3  ldc.i4.s 0x14
0x150f5  ldstr    aDttimecreated// "dtTimeCreated"
0x150fa  stelem.ref
0x150fb  ldloc.s  7
0x150fd  ldc.i4.s 0x15
0x150ff  newarr   [mscorlib]System.Object
0x15104  stloc.s  8
0x15106  ldloc.s  8
0x15108  ldc.i4.0
0x15109  ldarg.1
0x1510a  stelem.ref
0x1510b  ldloc.s  8
0x1510d  ldc.i4.1
0x1510e  ldarg.3
0x1510f  stelem.ref
0x15110  ldloc.s  8
0x15112  ldc.i4.2
0x15113  ldarg.s  4
0x15115  stelem.ref
0x15116  ldloc.s  8
0x15118  ldc.i4.3
0x15119  ldarg.s  5
0x1511b  box      [mscorlib]System.Int32
0x15120  stelem.ref
0x15121  ldloc.s  8
0x15123  ldc.i4.4
0x15124  ldarg.s  6
0x15126  stelem.ref
0x15127  ldloc.s  8
0x15129  ldc.i4.5
0x1512a  ldarg.s  7
0x1512c  box      [mscorlib]System.Guid
0x15131  stelem.ref
0x15132  ldloc.s  8
0x15134  ldc.i4.6
0x15135  ldarg.s  8
0x15137  box      [mscorlib]System.Int64
0x1513c  stelem.ref
0x1513d  ldloc.s  8
0x1513f  ldc.i4.7
0x15140  ldarg.s  9
0x15142  box      [mscorlib]System.Int64
0x15147  stelem.ref
0x15148  ldloc.s  8
0x1514a  ldc.i4.8
0x1514b  ldarg.s  0xA
0x1514d  box      [mscorlib]System.Int32
0x15152  stelem.ref
0x15153  ldloc.s  8
0x15155  ldc.i4.s 9
0x15157  ldarg.s  0xB
0x15159  box      [mscorlib]System.Int32
0x1515e  stelem.ref
0x1515f  ldloc.s  8
0x15161  ldc.i4.s 0xA
0x15163  ldarg.s  0xC
0x15165  stelem.ref
0x15166  ldloc.s  8
0x15168  ldc.i4.s 0xB
0x1516a  ldarg.s  0xD
0x1516c  stelem.ref
0x1516d  ldloc.s  8
0x1516f  ldc.i4.s 0xC
0x15171  ldarg.s  0xE
0x15173  stelem.ref
0x15174  ldloc.s  8
0x15176  ldc.i4.s 0xD
0x15178  ldarg.s  0xF
0x1517a  stelem.ref
0x1517b  ldloc.s  8
0x1517d  ldc.i4.s 0xE
0x1517f  ldarg.s  0x10
0x15181  stelem.ref
0x15182  ldloc.s  8
0x15184  ldc.i4.s 0xF
0x15186  ldarg.s  0x11
0x15188  stelem.ref
0x15189  ldloc.s  8
0x1518b  ldc.i4.s 0x10
0x1518d  ldarg.s  0x12
0x1518f  box      [mscorlib]System.Guid
0x15194  stelem.ref
0x15195  ldloc.s  8
0x15197  ldc.i4.s 0x11
0x15199  ldarg.s  0x13
0x1519b  stelem.ref
0x1519c  ldloc.s  8
0x1519e  ldc.i4.s 0x12
0x151a0  ldarg.s  0x14
0x151a2  stelem.ref
0x151a3  ldloc.s  8
0x151a5  ldc.i4.s 0x13
0x151a7  ldarg.s  0x15
0x151a9  box      [mscorlib]System.Boolean
0x151ae  stelem.ref
0x151af  ldloc.s  8
0x151b1  ldc.i4.s 0x14
0x151b3  ldarg.s  0x16
0x151b5  box      [mscorlib]System.DateTime
0x151ba  stelem.ref
0x151bb  ldloc.s  8
0x151bd  ldloc.0
0x151be  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x151c3  ldloc.0
0x151c4  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x151c9  rethrow
0x151cb  stloc.1
0x151cc  ldstr    aCreatelistonim// "CreateListOnImport"
0x151d1  ldarg.0
0x151d2  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x151d7  ldarg.0
0x151d8  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x151dd  ldc.i4.s 0x15
0x151df  newarr   [mscorlib]System.String
0x151e4  stloc.s  9
0x151e6  ldloc.s  9
0x151e8  ldc.i4.0
0x151e9  ldstr    aBstrurl// "bstrUrl"
0x151ee  stelem.ref
0x151ef  ldloc.s  9
0x151f1  ldc.i4.1
0x151f2  ldstr    aBstrtitle// "bstrTitle"
0x151f7  stelem.ref
0x151f8  ldloc.s  9
0x151fa  ldc.i4.2
0x151fb  ldstr    aBstrdescriptio// "bstrDescription"
0x15200  stelem.ref
0x15201  ldloc.s  9
0x15203  ldc.i4.3
0x15204  ldstr    aLtemplateid// "lTemplateID"
0x15209  stelem.ref
0x1520a  ldloc.s  9
0x1520c  ldc.i4.4
0x1520d  ldstr    aBstrfeatureid// "bstrFeatureId"
0x15212  stelem.ref
0x15213  ldloc.s  9
0x15215  ldc.i4.5
0x15216  ldstr    aGuidrootfolder// "guidRootFolderId"
0x1521b  stelem.ref
0x1521c  ldloc.s  9
0x1521e  ldc.i4.6
0x1521f  ldstr    aLlflags// "llFlags"
0x15224  stelem.ref
0x15225  ldloc.s  9
0x15227  ldc.i4.7
0x15228  ldstr    aLlflags2// "llFlags2"
0x1522d  stelem.ref
0x1522e  ldloc.s  9
0x15230  ldc.i4.8
0x15231  ldstr    aIversion// "iVersion"
0x15236  stelem.ref
0x15237  ldloc.s  9
0x15239  ldc.i4.s 9
0x1523b  ldstr    aIauthor// "iAuthor"
0x15240  stelem.ref
0x15241  ldloc.s  9
  ... truncated ...
```
