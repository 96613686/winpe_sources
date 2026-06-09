# Microsoft.SharePoint.Client.CompMgrRoot::EnsureComponents

- ea: `0x17330`
- end: `0x1748c`
- name: `Microsoft.SharePoint.Client.CompMgrRoot::EnsureComponents`
- size: `348`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x17490`
- `0x174d0`
- `0x17510`
- `0x17550`
- `0x17580`

## callees

- `0xe000`
- `0xe620`
- `0x17120`
- `0x17140`
- `0x17330`
- `0x177f0`

## string_xrefs

- `0x1735a`: `Component Mananger Root: Initializing the component manager root.`
- `0x173a1`: `Component Mananger Root: Find the real component manager.`
- `0x173b5`: `Component Mananger Root: Load the real component manager.`
- `0x173c7`: `Component Mananger Root: Init the real component manager.`
- `0x173d9`: `Component Mananger Root: Load the experiment manager.`
- `0x1741b`: `Component Mananger Root: Loaded the experiment manager.`
- `0x17446`: `Component Mananger Root: Something went wrong loading the component manager.`

## pseudocode

```c

```

## disassembly

```asm
0x17330  ldc.i4.0
0x17331  stloc.0
0x17332  ldsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr Microsoft.SharePoint.Client.CompMgrRoot::compMgr
0x17337  brtrue   loc_17434
0x1733c  ldc.i4.0
0x1733d  stloc.s  4
0x1733f  ldsfld   object Microsoft.SharePoint.Client.CompMgrRoot::lockObject
0x17344  dup
0x17345  stloc.s  7
0x17347  ldloca.s 4
0x17349  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1734e  ldsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr Microsoft.SharePoint.Client.CompMgrRoot::compMgr
0x17353  brtrue   loc_17426
0x17358  ldnull
0x17359  stloc.1
0x1735a  ldstr    aComponentManan// "Component Mananger Root: Initializing t"...
0x1735f  ldc.i4.3
0x17360  call     void Microsoft.SharePoint.Client.CompMgrRoot::ULSTrace(string msg, valuetype [System]System.Diagnostics.TraceLevel level)
0x17365  newobj   instance void Microsoft.SharePoint.Client.CompMgr::.ctor()
0x1736a  stloc.2
0x1736b  ldloc.2
0x1736c  ldnull
0x1736d  ldftn    void Microsoft.SharePoint.Client.CompMgrRoot::MyULSTracer(string message, int16 traceLevel)
0x17373  newobj   instance void [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.LoggerDelegate::.ctor(object, native int)
0x17378  callvirt instance void [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit::SetLogger(class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.LoggerDelegate)
0x1737d  ldloc.2
0x1737e  ldnull
0x1737f  ldftn    string Microsoft.SharePoint.Client.CompMgrRoot::MyInstallPath()
0x17385  newobj   instance void [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.InstallPathDelegate::.ctor(object, native int)
0x1738a  callvirt instance void [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit::SetInstallPath(class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.InstallPathDelegate)
0x1738f  ldloc.2
0x17390  ldsfld   string Microsoft.SharePoint.Client.CompMgrRoot::appName
0x17395  callvirt instance void [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit::SetAppName(string)
0x1739a  ldloc.2
0x1739b  callvirt instance string [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit::FindProductionCompSetPath()
0x173a0  stloc.3
0x173a1  ldstr    aComponentManan_0// "Component Mananger Root: Find the real "...
0x173a6  ldc.i4.3
0x173a7  call     void Microsoft.SharePoint.Client.CompMgrRoot::ULSTrace(string msg, valuetype [System]System.Diagnostics.TraceLevel level)
0x173ac  ldloc.2
0x173ad  ldloc.3
0x173ae  callvirt instance bool [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit::GetAllData(string)
0x173b3  brfalse.s loc_17426
0x173b5  ldstr    aComponentManan_1// "Component Mananger Root: Load the real "...
0x173ba  ldc.i4.3
0x173bb  call     void Microsoft.SharePoint.Client.CompMgrRoot::ULSTrace(string msg, valuetype [System]System.Diagnostics.TraceLevel level)
0x173c0  ldloc.2
0x173c1  callvirt instance class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgrInit::Reload()
0x173c6  stloc.1
0x173c7  ldstr    aComponentManan_2// "Component Mananger Root: Init the real "...
0x173cc  ldc.i4.3
0x173cd  call     void Microsoft.SharePoint.Client.CompMgrRoot::ULSTrace(string msg, valuetype [System]System.Diagnostics.TraceLevel level)
0x173d2  ldloc.1
0x173d3  ldnull
0x173d4  call     void Microsoft.SharePoint.Client.CompMgrRoot::MyCompMgrInit(object obj, object data)
0x173d9  ldstr    aComponentManan_3// "Component Mananger Root: Load the exper"...
0x173de  ldc.i4.3
0x173df  call     void Microsoft.SharePoint.Client.CompMgrRoot::ULSTrace(string msg, valuetype [System]System.Diagnostics.TraceLevel level)
0x173e4  ldloc.1
0x173e5  ldsfld   string Microsoft.SharePoint.Client.CompMgrRoot::typeNameExpMgr
0x173ea  ldnull
0x173eb  ldftn    void Microsoft.SharePoint.Client.CompMgrRoot::MyExpMgrInit(object obj, object data)
0x173f1  newobj   instance void [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.TypeInitDelegate::.ctor(object, native int)
0x173f6  callvirt instance void [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr::SetTypeInit(string, class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.TypeInitDelegate)
0x173fb  ldloc.1
0x173fc  ldsfld   string Microsoft.SharePoint.Client.CompMgrRoot::defaultSetName
0x17401  ldsfld   string Microsoft.SharePoint.Client.CompMgrRoot::typeNameExpMgr
0x17406  callvirt instance object [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr::RetrieveInstance(string, string)
0x1740b  isinst   [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.IExpMgr
0x17410  stsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.IExpMgr Microsoft.SharePoint.Client.CompMgrRoot::expMgr
0x17415  ldloc.1
0x17416  stsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr Microsoft.SharePoint.Client.CompMgrRoot::compMgr
0x1741b  ldstr    aComponentManan_4// "Component Mananger Root: Loaded the exp"...
0x17420  ldc.i4.3
0x17421  call     void Microsoft.SharePoint.Client.CompMgrRoot::ULSTrace(string msg, valuetype [System]System.Diagnostics.TraceLevel level)
0x17426  leave.s  loc_17434
0x17428  ldloc.s  4
0x1742a  brfalse.s loc_17433
0x1742c  ldloc.s  7
0x1742e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x17433  endfinally
0x17434  ldsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr Microsoft.SharePoint.Client.CompMgrRoot::compMgr
0x17439  brfalse.s loc_17446
0x1743b  ldsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.IExpMgr Microsoft.SharePoint.Client.CompMgrRoot::expMgr
0x17440  brfalse.s loc_17446
0x17442  ldc.i4.1
0x17443  stloc.0
0x17444  br.s     loc_1745D
0x17446  ldstr    aComponentManan_5// "Component Mananger Root: Something went"...
0x1744b  ldc.i4.1
0x1744c  call     void Microsoft.SharePoint.Client.CompMgrRoot::ULSTrace(string msg, valuetype [System]System.Diagnostics.TraceLevel level)
0x17451  ldnull
0x17452  stsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr Microsoft.SharePoint.Client.CompMgrRoot::compMgr
0x17457  ldnull
0x17458  stsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.IExpMgr Microsoft.SharePoint.Client.CompMgrRoot::expMgr
0x1745d  leave.s  loc_1748A
0x1745f  stloc.s  5
0x17461  call     class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientServiceHost::CreateServiceHost()
0x17466  stloc.s  6
0x17468  ldloc.s  6
0x1746a  ldc.i4   0x11D70D0
0x1746f  ldc.i4.1
0x17470  ldloc.s  5
0x17472  callvirt instance string [mscorlib]System.Exception::get_Message()
0x17477  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x1747c  ldnull
0x1747d  stsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.ICompMgr Microsoft.SharePoint.Client.CompMgrRoot::compMgr
0x17482  ldnull
0x17483  stsfld   class [Microsoft.SPExtensions.IspCompMgr]Microsoft.SPExtensions.ISPCompMgr.IExpMgr Microsoft.SharePoint.Client.CompMgrRoot::expMgr
0x17488  leave.s  loc_1748A
0x1748a  ldloc.0
0x1748b  ret
```
