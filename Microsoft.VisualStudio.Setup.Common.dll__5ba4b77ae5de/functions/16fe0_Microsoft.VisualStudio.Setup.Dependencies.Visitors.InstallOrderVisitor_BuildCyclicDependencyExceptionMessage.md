# Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::BuildCyclicDependencyExceptionMessage

- ea: `0x16fe0`
- end: `0x170df`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::BuildCyclicDependencyExceptionMessage`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16f90`

## callees

- `0x16680`
- `0x16fe0`
- `0x1d600`
- `0x1d610`
- `0x1d630`
- `0x1d700`

## pseudocode

```c

```

## disassembly

```asm
0x16fe0  newobj   instance void <>c__DisplayClass28_0::.ctor()
0x16fe5  stloc.0
0x16fe6  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x16feb  stloc.1
0x16fec  call     string [mscorlib]System.Environment::get_NewLine()
0x16ff1  ldstr    asc_24AE8// "  "
0x16ff6  call     string [mscorlib]System.String::Concat(string, string)
0x16ffb  stloc.2
0x16ffc  ldloc.0
0x16ffd  ldarg.0
0x16ffe  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class VisitationRecord> Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::visitationLog
0x17003  ldarg.1
0x17004  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class VisitationRecord>::get_Item(void)
0x17009  callvirt instance int32 VisitationRecord::get_Index()
0x1700e  stfld    int32 <>c__DisplayClass28_0::cycleStartIndex
0x17013  ldarg.0
0x17014  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class VisitationRecord> Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::visitationLog
0x17019  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class VisitationRecord>::get_Values()
0x1701e  ldloc.0
0x1701f  ldfld    class [mscorlib]System.Func`2<class VisitationRecord, bool> <>c__DisplayClass28_0::<>9__0
0x17024  dup
0x17025  brtrue.s loc_1703F
0x17027  pop
0x17028  ldloc.0
0x17029  ldloc.0
0x1702a  ldftn    instance bool <>c__DisplayClass28_0::<BuildCyclicDependencyExceptionMessage>b__0(class VisitationRecord x)
0x17030  newobj   instance void class [mscorlib]System.Func`2<class VisitationRecord, bool>::.ctor(object, native int)
0x17035  dup
0x17036  stloc.s  4
0x17038  stfld    class [mscorlib]System.Func`2<class VisitationRecord, bool> <>c__DisplayClass28_0::<>9__0
0x1703d  ldloc.s  4
0x1703f  call     T0x2B000097
0x17044  ldsfld   class [mscorlib]System.Func`2<class VisitationRecord, int32> <>c::<>9__28_1
0x17049  dup
0x1704a  brtrue.s loc_17063
0x1704c  pop
0x1704d  ldsfld   class <>c <>c::<>9
0x17052  ldftn    instance int32 <>c::<BuildCyclicDependencyExceptionMessage>b__28_1(class VisitationRecord x)
0x17058  newobj   instance void class [mscorlib]System.Func`2<class VisitationRecord, int32>::.ctor(object, native int)
0x1705d  dup
0x1705e  stsfld   class [mscorlib]System.Func`2<class VisitationRecord, int32> <>c::<>9__28_1
0x17063  call     T0x2B000098
0x17068  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class VisitationRecord>::GetEnumerator()
0x1706d  stloc.3
0x1706e  br.s     loc_170AF
0x17070  ldloc.3
0x17071  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class VisitationRecord>::get_Current()
0x17076  stloc.s  5
0x17078  ldloc.s  5
0x1707a  callvirt instance valuetype VisitationState VisitationRecord::get_State()
0x1707f  ldc.i4.1
0x17080  bne.un.s loc_17084
0x17082  leave.s  loc_170C3
0x17084  ldloc.1
0x17085  ldloc.2
0x17086  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1708b  pop
0x1708c  ldloc.1
0x1708d  ldloc.s  5
0x1708f  callvirt instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode VisitationRecord::get_Node()
0x17094  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Id()
0x17099  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1709e  pop
0x1709f  call     string [mscorlib]System.Environment::get_NewLine()
0x170a4  ldstr    asc_24AEE// "  ---> "
0x170a9  call     string [mscorlib]System.String::Concat(string, string)
0x170ae  stloc.2
0x170af  ldloc.3
0x170b0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x170b5  brtrue.s loc_17070
0x170b7  leave.s  loc_170C3
0x170b9  ldloc.3
0x170ba  brfalse.s loc_170C2
0x170bc  ldloc.3
0x170bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x170c2  endfinally
0x170c3  ldloc.1
0x170c4  ldloc.2
0x170c5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x170ca  pop
0x170cb  ldloc.1
0x170cc  ldarg.1
0x170cd  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Id()
0x170d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x170d7  pop
0x170d8  ldloc.1
0x170d9  callvirt instance string [mscorlib]System.Object::ToString()
0x170de  ret
```
