# System.Windows.BaseCompatibilityPreferences::set_ReuseDispatcherSynchronizationContextInstance

- ea: `0x2f760`
- end: `0x2f7b0`
- name: `System.Windows.BaseCompatibilityPreferences::set_ReuseDispatcherSynchronizationContextInstance`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2c130`
- `0x2f760`

## string_xrefs

- `0x2f777`: `CompatibilityPreferencesSealed`
- `0x2f78c`: `BaseCompatibilityPreferences`

## pseudocode

```c

```

## disassembly

```asm
0x2f760  ldsfld   object System.Windows.BaseCompatibilityPreferences::_lockObject
0x2f765  stloc.0
0x2f766  ldc.i4.0
0x2f767  stloc.1
0x2f768  ldloc.0
0x2f769  ldloca.s 1
0x2f76b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2f770  ldsfld   bool System.Windows.BaseCompatibilityPreferences::_isSealed
0x2f775  brfalse.s loc_2F79D
0x2f777  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x2f77c  ldc.i4.2
0x2f77d  newarr   [mscorlib]System.Object
0x2f782  dup
0x2f783  ldc.i4.0
0x2f784  ldstr    aReusedispatche// "ReuseDispatcherSynchronizationContextIn"...
0x2f789  stelem.ref
0x2f78a  dup
0x2f78b  ldc.i4.1
0x2f78c  ldstr    aBasecompatibil// "BaseCompatibilityPreferences"
0x2f791  stelem.ref
0x2f792  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x2f797  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2f79c  throw
0x2f79d  ldarg.0
0x2f79e  stsfld   bool System.Windows.BaseCompatibilityPreferences::_reuseDispatcherSynchronizationContextInstance
0x2f7a3  leave.s  loc_2F7AF
0x2f7a5  ldloc.1
0x2f7a6  brfalse.s loc_2F7AE
0x2f7a8  ldloc.0
0x2f7a9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2f7ae  endfinally
0x2f7af  ret
```
