# System.Windows.DependencyProperty::ValidateDefaultValueCommon

- ea: `0x32870`
- end: `0x32942`
- name: `System.Windows.DependencyProperty::ValidateDefaultValueCommon`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x32830`
- `0x32850`

## callees

- `0xd6a0`
- `0x2c100`
- `0x2c130`
- `0x32870`
- `0x33000`
- `0x38120`
- `0x38130`
- `0x38140`
- `0x394a0`
- `0x3d490`

## string_xrefs

- `0x32901`: `DefaultValueMustBeFreeThreaded`

## pseudocode

```c

```

## disassembly

```asm
0x32870  ldarg.0
0x32871  ldarg.1
0x32872  call     bool System.Windows.DependencyProperty::IsValidType(object value, class [mscorlib]System.Type propertyType)
0x32877  brtrue.s loc_32893
0x32879  ldstr    aDefaultvaluepr// "DefaultValuePropertyTypeMismatch"
0x3287e  ldc.i4.1
0x3287f  newarr   [mscorlib]System.Object
0x32884  dup
0x32885  ldc.i4.0
0x32886  ldarg.2
0x32887  stelem.ref
0x32888  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x3288d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x32892  throw
0x32893  ldarg.0
0x32894  isinst   System.Windows.Expression
0x32899  brfalse.s loc_328AB
0x3289b  ldstr    aDefaultvaluema// "DefaultValueMayNotBeExpression"
0x328a0  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x328a5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x328aa  throw
0x328ab  ldarg.s  4
0x328ad  brfalse.s loc_3291B
0x328af  ldarg.0
0x328b0  isinst   System.Windows.Threading.DispatcherObject
0x328b5  stloc.0
0x328b6  ldloc.0
0x328b7  brfalse.s loc_3291B
0x328b9  ldloc.0
0x328ba  callvirt instance class System.Windows.Threading.Dispatcher System.Windows.Threading.DispatcherObject::get_Dispatcher()
0x328bf  brfalse.s loc_3291B
0x328c1  ldloc.0
0x328c2  isinst   System.Windows.ISealable
0x328c7  stloc.1
0x328c8  ldloc.1
0x328c9  brfalse.s loc_32901
0x328cb  ldloc.1
0x328cc  callvirt instance bool System.Windows.ISealable::get_CanSeal()
0x328d1  brfalse.s loc_32901
0x328d3  ldloc.1
0x328d4  callvirt instance bool System.Windows.ISealable::get_IsSealed()
0x328d9  ldc.i4.0
0x328da  ceq
0x328dc  ldstr    aASealedIsealab// "A Sealed ISealable must not have dispat"...
0x328e1  call     void MS.Internal.Invariant::Assert(bool condition, string invariantMessage)
0x328e6  ldloc.1
0x328e7  callvirt instance void System.Windows.ISealable::Seal()
0x328ec  ldloc.0
0x328ed  callvirt instance class System.Windows.Threading.Dispatcher System.Windows.Threading.DispatcherObject::get_Dispatcher()
0x328f2  ldnull
0x328f3  ceq
0x328f5  ldstr    aIsealableSealF// "ISealable.Seal() failed after ISealable"...
0x328fa  call     void MS.Internal.Invariant::Assert(bool condition, string invariantMessage)
0x328ff  br.s     loc_3291B
0x32901  ldstr    aDefaultvaluemu// "DefaultValueMustBeFreeThreaded"
0x32906  ldc.i4.1
0x32907  newarr   [mscorlib]System.Object
0x3290c  dup
0x3290d  ldc.i4.0
0x3290e  ldarg.2
0x3290f  stelem.ref
0x32910  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x32915  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3291a  throw
0x3291b  ldarg.3
0x3291c  brfalse.s loc_32941
0x3291e  ldarg.3
0x3291f  ldarg.0
0x32920  callvirt instance bool System.Windows.ValidateValueCallback::Invoke(object value)
0x32925  brtrue.s loc_32941
0x32927  ldstr    aDefaultvaluein// "DefaultValueInvalid"
0x3292c  ldc.i4.1
0x3292d  newarr   [mscorlib]System.Object
0x32932  dup
0x32933  ldc.i4.0
0x32934  ldarg.2
0x32935  stelem.ref
0x32936  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x3293b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x32940  throw
0x32941  ret
```
