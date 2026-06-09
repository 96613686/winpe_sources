# System.Windows.FrameworkCompatibilityPreferences::set_UseSetWindowPosForTopmostWindows

- ea: `0x8bc0`
- end: `0x8c10`
- name: `System.Windows.FrameworkCompatibilityPreferences::set_UseSetWindowPosForTopmostWindows`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8c20`

## callees

- `0x8bc0`
- `0x38c70`

## string_xrefs

- `0x8bd7`: `CompatibilityPreferencesSealed`
- `0x8bec`: `FrameworkCompatibilityPreferences`

## pseudocode

```c

```

## disassembly

```asm
0x8bc0  ldsfld   object System.Windows.FrameworkCompatibilityPreferences::_lockObject
0x8bc5  stloc.0
0x8bc6  ldc.i4.0
0x8bc7  stloc.1
0x8bc8  ldloc.0
0x8bc9  ldloca.s 1
0x8bcb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x8bd0  ldsfld   bool System.Windows.FrameworkCompatibilityPreferences::_isSealed
0x8bd5  brfalse.s loc_8BFD
0x8bd7  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x8bdc  ldc.i4.2
0x8bdd  newarr   [mscorlib]System.Object
0x8be2  dup
0x8be3  ldc.i4.0
0x8be4  ldstr    aUsesetwindowpo// "UseSetWindowPosForTopmostWindows"
0x8be9  stelem.ref
0x8bea  dup
0x8beb  ldc.i4.1
0x8bec  ldstr    aFrameworkcompa// "FrameworkCompatibilityPreferences"
0x8bf1  stelem.ref
0x8bf2  call     string System.Windows.SR::Get(string id, object[] args)
0x8bf7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8bfc  throw
0x8bfd  ldarg.0
0x8bfe  stsfld   bool System.Windows.FrameworkCompatibilityPreferences::_useSetWindowPosForTopmostWindows
0x8c03  leave.s  loc_8C0F
0x8c05  ldloc.1
0x8c06  brfalse.s loc_8C0E
0x8c08  ldloc.0
0x8c09  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x8c0e  endfinally
0x8c0f  ret
```
