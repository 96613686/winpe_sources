# Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::ReadData

- ea: `0x296f0`
- end: `0x29920`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::ReadData`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x29690`

## callees

- `0x14e30`
- `0x1cd50`
- `0x1ce20`
- `0x27ff0`
- `0x28d30`
- `0x296f0`
- `0x29a00`
- `0x2b090`
- `0x45f50`
- `0x46eb0`
- `0x47000`

## string_xrefs

- `0x296f1`: `ReadData`
- `0x29914`: `ReadData`

## pseudocode

```c

```

## disassembly

```asm
0x296f0  ldarg.0
0x296f1  ldstr    aReaddata// "ReadData"
0x296f6  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x296fb  ldarg.0
0x296fc  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::homePageNode
0x29701  brfalse.s loc_2970E
0x29703  ldarg.0
0x29704  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::homePageNode
0x29709  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InsertChildren()
0x2970e  ldarg.0
0x2970f  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatusSyncRoot
0x29714  stloc.0
0x29715  ldc.i4.0
0x29716  stloc.1
0x29717  ldloc.0
0x29718  ldloca.s 1
0x2971a  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2971f  ldarg.0
0x29720  ldfld    valuetype RefreshStatus Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatus
0x29725  ldc.i4.3
0x29726  bne.un.s loc_2972D
0x29728  leave    loc_2991F
0x2972d  ldarg.0
0x2972e  ldc.i4.3
0x2972f  stfld    valuetype RefreshStatus Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatus
0x29734  ldarg.0
0x29735  ldc.i4.0
0x29736  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::partialData
0x2973b  leave.s  loc_29747
0x2973d  ldloc.1
0x2973e  brfalse.s loc_29746
0x29740  ldloc.0
0x29741  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x29746  endfinally
0x29747  ldarg.0
0x29748  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::homePageNode
0x2974d  brfalse  loc_297E9
0x29752  ldarg.0
0x29753  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::homePageNode
0x29758  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData> Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_RecentViewsDataArrayList()
0x2975d  stloc.2
0x2975e  ldc.i4.0
0x2975f  stloc.1
0x29760  ldloc.2
0x29761  ldloca.s 1
0x29763  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x29768  ldarg.0
0x29769  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::homePageNode
0x2976e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData> Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_RecentViewsDataArrayList()
0x29773  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData>::GetEnumerator()
0x29778  stloc.3
0x29779  br.s     loc_2978D
0x2977b  ldloca.s 3
0x2977d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData>::get_Current()
0x29782  ldarg.0
0x29783  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::get_Context()
0x29788  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData::RefreshLogData(class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext context)
0x2978d  ldloca.s 3
0x2978f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData>::MoveNext()
0x29794  brtrue.s loc_2977B
0x29796  leave.s  loc_297A6
0x29798  ldloca.s 3
0x2979a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData>
0x297a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x297a5  endfinally
0x297a6  leave.s  loc_297B2
0x297a8  ldloc.1
0x297a9  brfalse.s loc_297B1
0x297ab  ldloc.2
0x297ac  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x297b1  endfinally
0x297b2  ldarg.0
0x297b3  call     instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_InvokeRequired()
0x297b8  brfalse.s loc_297D8
0x297ba  ldarg.0
0x297bb  ldarg.0
0x297bc  ldfld    class UpdateUIDelegate Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::updateUI
0x297c1  ldc.i4.1
0x297c2  newarr   [mscorlib]System.Object
0x297c7  dup
0x297c8  ldc.i4.0
0x297c9  ldc.i4.1
0x297ca  box      [mscorlib]System.Int32
0x297cf  stelem.ref
0x297d0  call     instance class [mscorlib]System.IAsyncResult [System.Windows.Forms]System.Windows.Forms.Control::BeginInvoke(class [mscorlib]System.Delegate, object[])
0x297d5  pop
0x297d6  br.s     loc_297DE
0x297d8  ldarg.0
0x297d9  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::UpdateRecentViewsUI()
0x297de  ldarg.0
0x297df  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x297e4  stfld    valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshTime
0x297e9  ldarg.1
0x297ea  brfalse.s loc_297FB
0x297ec  ldarg.1
0x297ed  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x297f2  brtrue.s loc_297FB
0x297f4  ldarg.0
0x297f5  ldarg.1
0x297f6  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::ReadDataForEventSummaryHideDetailControl(class [System]System.ComponentModel.BackgroundWorker worker)
0x297fb  ldarg.1
0x297fc  brfalse.s loc_29831
0x297fe  ldarg.1
0x297ff  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x29804  brtrue.s loc_29831
0x29806  ldarg.0
0x29807  ldc.i4.1
0x29808  stfld    valuetype RefreshStatus Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatus
0x2980d  ldarg.0
0x2980e  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatusSyncRoot
0x29813  stloc.0
0x29814  ldc.i4.0
0x29815  stloc.1
0x29816  ldloc.0
0x29817  ldloca.s 1
0x29819  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2981e  ldarg.0
0x2981f  ldc.i4.1
0x29820  stfld    valuetype RefreshStatus Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatus
0x29825  leave.s  loc_29831
0x29827  ldloc.1
0x29828  brfalse.s loc_29830
0x2982a  ldloc.0
0x2982b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x29830  endfinally
0x29831  ldarg.1
0x29832  brfalse.s loc_29843
0x29834  ldarg.1
0x29835  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x2983a  brfalse.s loc_29843
0x2983c  ldarg.0
0x2983d  ldc.i4.4
0x2983e  stfld    valuetype RefreshStatus Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatus
0x29843  ldarg.0
0x29844  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::homePageNode
0x29849  brfalse.s loc_298C3
0x2984b  ldarg.1
0x2984c  brfalse.s loc_298C3
0x2984e  ldarg.1
0x2984f  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x29854  brtrue.s loc_298C3
0x29856  ldarg.0
0x29857  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::homePageNode
0x2985c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IItemsDictionary Microsoft.Windows.ManagementUI.CombinedControls.ManagementNode::get_SubNode()
0x29861  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x29866  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x2986b  stloc.s  4
0x2986d  br.s     loc_298A3
0x2986f  ldloc.s  4
0x29871  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x29876  castclass Microsoft.Windows.ManagementUI.CombinedControls.EventsNode
0x2987b  stloc.s  5
0x2987d  ldarg.1
0x2987e  brfalse.s loc_298A3
0x29880  ldarg.1
0x29881  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x29886  brtrue.s loc_298A3
0x29888  ldloc.s  5
0x2988a  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x2988f  ldc.i4.4
0x29890  beq.s    loc_2989C
0x29892  ldloc.s  5
0x29894  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x29899  ldc.i4.3
0x2989a  bne.un.s loc_298A3
0x2989c  ldloc.s  5
0x2989e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::InsertChildren()
0x298a3  ldloc.s  4
0x298a5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x298aa  brtrue.s loc_2986F
0x298ac  leave.s  loc_298C3
0x298ae  ldloc.s  4
0x298b0  isinst   [mscorlib]System.IDisposable
0x298b5  stloc.s  6
0x298b7  ldloc.s  6
0x298b9  brfalse.s loc_298C2
0x298bb  ldloc.s  6
0x298bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x298c2  endfinally
0x298c3  leave.s  loc_2991F
0x298c5  pop
0x298c6  ldarg.0
0x298c7  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatusSyncRoot
0x298cc  stloc.0
0x298cd  ldc.i4.0
0x298ce  stloc.1
0x298cf  ldloc.0
0x298d0  ldloca.s 1
0x298d2  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x298d7  ldarg.0
0x298d8  ldc.i4.2
0x298d9  stfld    valuetype RefreshStatus Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatus
0x298de  leave.s  loc_298EA
0x298e0  ldloc.1
0x298e1  brfalse.s loc_298E9
0x298e3  ldloc.0
0x298e4  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x298e9  endfinally
0x298ea  leave.s  loc_2991F
0x298ec  pop
0x298ed  ldarg.0
0x298ee  ldfld    object Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatusSyncRoot
0x298f3  stloc.0
0x298f4  ldc.i4.0
0x298f5  stloc.1
0x298f6  ldloc.0
0x298f7  ldloca.s 1
0x298f9  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x298fe  ldarg.0
0x298ff  ldc.i4.4
0x29900  stfld    valuetype RefreshStatus Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::refreshStatus
0x29905  leave.s  loc_29911
0x29907  ldloc.1
0x29908  brfalse.s loc_29910
0x2990a  ldloc.0
0x2990b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x29910  endfinally
0x29911  leave.s  loc_2991F
0x29913  ldarg.0
0x29914  ldstr    aReaddata// "ReadData"
0x29919  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x2991e  endfinally
0x2991f  ret
```
