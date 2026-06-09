# System.Windows.Xps.Packaging.XpsResourcePolicy::RegisterService

- ea: `0x265b0`
- end: `0x26618`
- name: `System.Windows.Xps.Packaging.XpsResourcePolicy::RegisterService`
- size: `104`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x26a00`
- `0x28f60`
- `0x2f600`

## callees

- `0x1ee90`
- `0x1efa0`
- `0x265b0`

## string_xrefs

- `0x265b9`: `serviceType`
- `0x265c7`: `service`
- `0x265fd`: `ReachPackaging_ServiceTypeAlreadyAdded`

## pseudocode

```c

```

## disassembly

```asm
0x265b0  ldarg.2
0x265b1  ldnull
0x265b2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x265b7  brfalse.s loc_265C4
0x265b9  ldstr    aServicetype// "serviceType"
0x265be  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x265c3  throw
0x265c4  ldarg.1
0x265c5  brtrue.s loc_265D2
0x265c7  ldstr    aService// "service"
0x265cc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x265d1  throw
0x265d2  ldarg.0
0x265d3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> System.Windows.Xps.Packaging.XpsResourcePolicy::_objDict
0x265d8  ldarg.2
0x265d9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::ContainsKey(var<u1>)
0x265de  brtrue.s loc_265EE
0x265e0  ldarg.0
0x265e1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> System.Windows.Xps.Packaging.XpsResourcePolicy::_objDict
0x265e6  ldarg.2
0x265e7  ldarg.1
0x265e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x265ed  ret
0x265ee  ldarg.0
0x265ef  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> System.Windows.Xps.Packaging.XpsResourcePolicy::_objDict
0x265f4  ldarg.2
0x265f5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::get_Item(void)
0x265fa  ldarg.1
0x265fb  beq.s    loc_26617
0x265fd  ldstr    aReachpackaging_36// "ReachPackaging_ServiceTypeAlreadyAdded"
0x26602  ldc.i4.1
0x26603  newarr   [mscorlib]System.Object
0x26608  dup
0x26609  ldc.i4.0
0x2660a  ldarg.2
0x2660b  stelem.ref
0x2660c  call     string System.Windows.Xps.SR::Get(string id, object[] args)
0x26611  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x26616  throw
0x26617  ret
```
