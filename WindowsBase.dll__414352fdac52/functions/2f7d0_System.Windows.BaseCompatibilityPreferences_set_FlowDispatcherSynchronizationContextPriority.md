# System.Windows.BaseCompatibilityPreferences::set_FlowDispatcherSynchronizationContextPriority

- ea: `0x2f7d0`
- end: `0x2f820`
- name: `System.Windows.BaseCompatibilityPreferences::set_FlowDispatcherSynchronizationContextPriority`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2c130`
- `0x2f7d0`

## string_xrefs

- `0x2f7e7`: `CompatibilityPreferencesSealed`
- `0x2f7fc`: `BaseCompatibilityPreferences`

## pseudocode

```c

```

## disassembly

```asm
0x2f7d0  ldsfld   object System.Windows.BaseCompatibilityPreferences::_lockObject
0x2f7d5  stloc.0
0x2f7d6  ldc.i4.0
0x2f7d7  stloc.1
0x2f7d8  ldloc.0
0x2f7d9  ldloca.s 1
0x2f7db  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2f7e0  ldsfld   bool System.Windows.BaseCompatibilityPreferences::_isSealed
0x2f7e5  brfalse.s loc_2F80D
0x2f7e7  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x2f7ec  ldc.i4.2
0x2f7ed  newarr   [mscorlib]System.Object
0x2f7f2  dup
0x2f7f3  ldc.i4.0
0x2f7f4  ldstr    aFlowdispatcher// "FlowDispatcherSynchronizationContextPri"...
0x2f7f9  stelem.ref
0x2f7fa  dup
0x2f7fb  ldc.i4.1
0x2f7fc  ldstr    aBasecompatibil// "BaseCompatibilityPreferences"
0x2f801  stelem.ref
0x2f802  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x2f807  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2f80c  throw
0x2f80d  ldarg.0
0x2f80e  stsfld   bool System.Windows.BaseCompatibilityPreferences::_flowDispatcherSynchronizationContextPriority
0x2f813  leave.s  loc_2F81F
0x2f815  ldloc.1
0x2f816  brfalse.s loc_2F81E
0x2f818  ldloc.0
0x2f819  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2f81e  endfinally
0x2f81f  ret
```
