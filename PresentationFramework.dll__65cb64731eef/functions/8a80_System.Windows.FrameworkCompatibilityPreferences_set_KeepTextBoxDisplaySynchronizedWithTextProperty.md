# System.Windows.FrameworkCompatibilityPreferences::set_KeepTextBoxDisplaySynchronizedWithTextProperty

- ea: `0x8a80`
- end: `0x8ad0`
- name: `System.Windows.FrameworkCompatibilityPreferences::set_KeepTextBoxDisplaySynchronizedWithTextProperty`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8a80`
- `0x38c70`

## string_xrefs

- `0x8a97`: `CompatibilityPreferencesSealed`
- `0x8aac`: `FrameworkCompatibilityPreferences`

## pseudocode

```c

```

## disassembly

```asm
0x8a80  ldsfld   object System.Windows.FrameworkCompatibilityPreferences::_lockObject
0x8a85  stloc.0
0x8a86  ldc.i4.0
0x8a87  stloc.1
0x8a88  ldloc.0
0x8a89  ldloca.s 1
0x8a8b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x8a90  ldsfld   bool System.Windows.FrameworkCompatibilityPreferences::_isSealed
0x8a95  brfalse.s loc_8ABD
0x8a97  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x8a9c  ldc.i4.2
0x8a9d  newarr   [mscorlib]System.Object
0x8aa2  dup
0x8aa3  ldc.i4.0
0x8aa4  ldstr    aAextboxdisplay// "AextBoxDisplaysText"
0x8aa9  stelem.ref
0x8aaa  dup
0x8aab  ldc.i4.1
0x8aac  ldstr    aFrameworkcompa// "FrameworkCompatibilityPreferences"
0x8ab1  stelem.ref
0x8ab2  call     string System.Windows.SR::Get(string id, object[] args)
0x8ab7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8abc  throw
0x8abd  ldarg.0
0x8abe  stsfld   bool System.Windows.FrameworkCompatibilityPreferences::_keepTextBoxDisplaySynchronizedWithTextProperty
0x8ac3  leave.s  loc_8ACF
0x8ac5  ldloc.1
0x8ac6  brfalse.s loc_8ACE
0x8ac8  ldloc.0
0x8ac9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x8ace  endfinally
0x8acf  ret
```
