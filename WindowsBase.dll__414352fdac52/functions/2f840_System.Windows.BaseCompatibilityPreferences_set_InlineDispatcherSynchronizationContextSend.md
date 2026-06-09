# System.Windows.BaseCompatibilityPreferences::set_InlineDispatcherSynchronizationContextSend

- ea: `0x2f840`
- end: `0x2f890`
- name: `System.Windows.BaseCompatibilityPreferences::set_InlineDispatcherSynchronizationContextSend`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2c130`
- `0x2f840`

## string_xrefs

- `0x2f857`: `CompatibilityPreferencesSealed`
- `0x2f86c`: `BaseCompatibilityPreferences`

## pseudocode

```c

```

## disassembly

```asm
0x2f840  ldsfld   object System.Windows.BaseCompatibilityPreferences::_lockObject
0x2f845  stloc.0
0x2f846  ldc.i4.0
0x2f847  stloc.1
0x2f848  ldloc.0
0x2f849  ldloca.s 1
0x2f84b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2f850  ldsfld   bool System.Windows.BaseCompatibilityPreferences::_isSealed
0x2f855  brfalse.s loc_2F87D
0x2f857  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x2f85c  ldc.i4.2
0x2f85d  newarr   [mscorlib]System.Object
0x2f862  dup
0x2f863  ldc.i4.0
0x2f864  ldstr    aInlinedispatch// "InlineDispatcherSynchronizationContextS"...
0x2f869  stelem.ref
0x2f86a  dup
0x2f86b  ldc.i4.1
0x2f86c  ldstr    aBasecompatibil// "BaseCompatibilityPreferences"
0x2f871  stelem.ref
0x2f872  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x2f877  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2f87c  throw
0x2f87d  ldarg.0
0x2f87e  stsfld   bool System.Windows.BaseCompatibilityPreferences::_inlineDispatcherSynchronizationContextSend
0x2f883  leave.s  loc_2F88F
0x2f885  ldloc.1
0x2f886  brfalse.s loc_2F88E
0x2f888  ldloc.0
0x2f889  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2f88e  endfinally
0x2f88f  ret
```
