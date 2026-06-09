# CalculateBranchesAlgorithm::TerminateCurrentBranch

- ea: `0x354c0`
- end: `0x3561b`
- name: `CalculateBranchesAlgorithm::TerminateCurrentBranch`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x352e0`

## callees

- `0x97d0`
- `0x1de50`
- `0x1de70`
- `0x354c0`
- `0x35e20`
- `0x35e40`
- `0x35e60`
- `0x35e70`
- `0x35ee0`
- `0x35ef0`

## string_xrefs

- `0x3550d`: `Attempt to terminate with partial branch`
- `0x3554b`: `m_currentBranch.LastItem does not match m_selectedPath.LastItem`

## pseudocode

```c

```

## disassembly

```asm
0x354c0  ldc.i4.0
0x354c1  stloc.0
0x354c2  ldarg.0
0x354c3  ldfld    class FilteredPath CalculateBranchesAlgorithm::m_currentBranch
0x354c8  callvirt instance int32 FilteredPath::get_Length()
0x354cd  ldc.i4.0
0x354ce  ble.s    loc_354FF
0x354d0  ldarg.0
0x354d1  ldfld    class FilteredPath CalculateBranchesAlgorithm::m_currentBranch
0x354d6  ldc.i4.0
0x354d7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class FilteredPathItem>::get_Item(!!T0)
0x354dc  callvirt instance class Microsoft.ReportingServices.Modeling.PathItem FilteredPathItem::get_PathItem()
0x354e1  brfalse.s loc_354F1
0x354e3  ldarg.0
0x354e4  ldfld    class FilteredPath CalculateBranchesAlgorithm::m_currentBranch
0x354e9  callvirt instance int32 FilteredPath::get_Length()
0x354ee  stloc.0
0x354ef  br.s     loc_354FF
0x354f1  ldarg.0
0x354f2  ldfld    class FilteredPath CalculateBranchesAlgorithm::m_currentBranch
0x354f7  callvirt instance int32 FilteredPath::get_Length()
0x354fc  ldc.i4.1
0x354fd  sub
0x354fe  stloc.0
0x354ff  ldloc.0
0x35500  ldarg.0
0x35501  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionPath CalculateBranchesAlgorithm::m_selectedPath
0x35506  callvirt instance int32 Microsoft.ReportingServices.Modeling.ExpressionPath::get_Length()
0x3550b  bge.s    loc_35518
0x3550d  ldstr    aAttemptToTermi// "Attempt to terminate with partial branc"...
0x35512  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x35517  throw
0x35518  ldarg.0
0x35519  ldfld    class FilteredPath CalculateBranchesAlgorithm::m_currentBranch
0x3551e  callvirt instance int32 FilteredPath::get_Length()
0x35523  ldc.i4.0
0x35524  bgt.s    loc_35529
0x35526  ldnull
0x35527  br.s     loc_35539
0x35529  ldarg.0
0x3552a  ldfld    class FilteredPath CalculateBranchesAlgorithm::m_currentBranch
0x3552f  callvirt instance class FilteredPathItem FilteredPath::get_LastItem()
0x35534  callvirt instance class Microsoft.ReportingServices.Modeling.PathItem FilteredPathItem::get_PathItem()
0x35539  ldarg.0
0x3553a  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionPath CalculateBranchesAlgorithm::m_selectedPath
0x3553f  callvirt instance class Microsoft.ReportingServices.Modeling.PathItem Microsoft.ReportingServices.Modeling.ExpressionPath::get_LastItem()
0x35544  call     bool [mscorlib]System.Object::Equals(object, object)
0x35549  brtrue.s loc_35556
0x3554b  ldstr    aMCurrentbranch// "m_currentBranch.LastItem does not match"...
0x35550  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x35555  throw
0x35556  ldc.i4.0
0x35557  stloc.1
0x35558  ldarg.0
0x35559  ldfld    class FilteredPath CalculateBranchesAlgorithm::m_currentBranch
0x3555e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class FilteredPathItem>::GetEnumerator()
0x35563  stloc.2
0x35564  br.s     loc_3557E
0x35566  ldloca.s 2
0x35568  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class FilteredPathItem>::get_Current()
0x3556d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.Expression> FilteredPathItem::get_Filters()
0x35572  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Count()
0x35577  ldc.i4.0
0x35578  ble.s    loc_3557E
0x3557a  ldc.i4.1
0x3557b  stloc.1
0x3557c  leave.s  loc_35597
0x3557e  ldloca.s 2
0x35580  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class FilteredPathItem>::MoveNext()
0x35585  brtrue.s loc_35566
0x35587  leave.s  loc_35597
0x35589  ldloca.s 2
0x3558b  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class FilteredPathItem>
0x35591  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35596  endfinally
0x35597  ldloc.1
0x35598  brtrue.s loc_355C3
0x3559a  ldarg.0
0x3559b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class FilteredPath> CalculateBranchesAlgorithm::m_branches
0x355a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class FilteredPath>::Clear()
0x355a5  ldarg.0
0x355a6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class FilteredPath> CalculateBranchesAlgorithm::m_branches
0x355ab  ldarg.0
0x355ac  ldfld    class FilteredPath CalculateBranchesAlgorithm::m_currentBranch
0x355b1  callvirt instance class FilteredPath FilteredPath::Clone()
0x355b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class FilteredPath>::Add(var<u1>)
0x355bb  ldarg.0
0x355bc  ldc.i4.1
0x355bd  stfld    bool CalculateBranchesAlgorithm::m_terminateAlgorithm
0x355c2  ret
0x355c3  ldarg.0
0x355c4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class FilteredPath> CalculateBranchesAlgorithm::m_branches
0x355c9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class FilteredPath>::GetEnumerator()
0x355ce  stloc.3
0x355cf  br.s     loc_355EB
0x355d1  ldloca.s 3
0x355d3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class FilteredPath>::get_Current()
0x355d8  stloc.s  4
0x355da  ldarg.0
0x355db  ldfld    class FilteredPath CalculateBranchesAlgorithm::m_currentBranch
0x355e0  ldloc.s  4
0x355e2  callvirt instance bool FilteredPath::IsSameAs(class FilteredPath other)
0x355e7  brfalse.s loc_355EB
0x355e9  leave.s  loc_3561A
0x355eb  ldloca.s 3
0x355ed  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class FilteredPath>::MoveNext()
0x355f2  brtrue.s loc_355D1
0x355f4  leave.s  loc_35604
0x355f6  ldloca.s 3
0x355f8  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class FilteredPath>
0x355fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35603  endfinally
0x35604  ldarg.0
0x35605  ldfld    class [mscorlib]System.Collections.Generic.List`1<class FilteredPath> CalculateBranchesAlgorithm::m_branches
0x3560a  ldarg.0
0x3560b  ldfld    class FilteredPath CalculateBranchesAlgorithm::m_currentBranch
0x35610  callvirt instance class FilteredPath FilteredPath::Clone()
0x35615  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class FilteredPath>::Add(var<u1>)
0x3561a  ret
```
