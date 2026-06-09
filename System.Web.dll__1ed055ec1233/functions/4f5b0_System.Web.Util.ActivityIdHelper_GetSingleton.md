# System.Web.Util.ActivityIdHelper::GetSingleton

- ea: `0x4f5b0`
- end: `0x4f63f`
- name: `System.Web.Util.ActivityIdHelper::GetSingleton`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x4f680`

## callees

- `0x4f580`
- `0x4f5b0`

## string_xrefs

- `0x4f5c4`: `get_CurrentThreadActivityId`
- `0x4f5ea`: `SetCurrentThreadActivityId`
- `0x4f610`: `SetCurrentThreadActivityId`

## pseudocode

```c

```

## disassembly

```asm
0x4f5b0  ldtoken  GetCurrentDelegate
0x4f5b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f5ba  ldtoken  [mscorlib]System.Diagnostics.Tracing.EventSource
0x4f5bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f5c4  ldstr    aGetCurrentthre// "get_CurrentThreadActivityId"
0x4f5c9  ldc.i4.0
0x4f5ca  ldc.i4.0
0x4f5cb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::CreateDelegate(class [mscorlib]System.Type, class [mscorlib]System.Type, string, bool, bool)
0x4f5d0  castclass GetCurrentDelegate
0x4f5d5  stloc.0
0x4f5d6  ldtoken  SetAndDestroyDelegate
0x4f5db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f5e0  ldtoken  [mscorlib]System.Diagnostics.Tracing.EventSource
0x4f5e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f5ea  ldstr    aSetcurrentthre// "SetCurrentThreadActivityId"
0x4f5ef  ldc.i4.0
0x4f5f0  ldc.i4.0
0x4f5f1  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::CreateDelegate(class [mscorlib]System.Type, class [mscorlib]System.Type, string, bool, bool)
0x4f5f6  castclass SetAndDestroyDelegate
0x4f5fb  stloc.1
0x4f5fc  ldtoken  SetAndPreserveDelegate
0x4f601  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f606  ldtoken  [mscorlib]System.Diagnostics.Tracing.EventSource
0x4f60b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f610  ldstr    aSetcurrentthre// "SetCurrentThreadActivityId"
0x4f615  ldc.i4.0
0x4f616  ldc.i4.0
0x4f617  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::CreateDelegate(class [mscorlib]System.Type, class [mscorlib]System.Type, string, bool, bool)
0x4f61c  castclass SetAndPreserveDelegate
0x4f621  stloc.2
0x4f622  ldloc.0
0x4f623  brfalse.s loc_4F636
0x4f625  ldloc.1
0x4f626  brfalse.s loc_4F636
0x4f628  ldloc.2
0x4f629  brfalse.s loc_4F636
0x4f62b  ldloc.0
0x4f62c  ldloc.1
0x4f62d  ldloc.2
0x4f62e  newobj   instance void System.Web.Util.ActivityIdHelper::.ctor(class GetCurrentDelegate getCurrentDel, class SetAndDestroyDelegate setAndDestroyDel, class SetAndPreserveDelegate setAndPreserveDel)
0x4f633  stloc.3
0x4f634  leave.s  loc_4F63D
0x4f636  leave.s  loc_4F63B
0x4f638  pop
0x4f639  leave.s  loc_4F63B
0x4f63b  ldnull
0x4f63c  ret
0x4f63d  ldloc.3
0x4f63e  ret
```
