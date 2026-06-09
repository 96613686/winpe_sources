# System.Windows.FrameworkCompatibilityPreferences::set_HandleTwoWayBindingToPropertyWithNonPublicSetter

- ea: `0x8af0`
- end: `0x8b60`
- name: `System.Windows.FrameworkCompatibilityPreferences::set_HandleTwoWayBindingToPropertyWithNonPublicSetter`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8b70`

## callees

- `0x8af0`
- `0x38c70`

## string_xrefs

- `0x8b07`: `CompatibilityPreferencesSealed`
- `0x8b1c`: `FrameworkCompatibilityPreferences`

## pseudocode

```c

```

## disassembly

```asm
0x8af0  ldsfld   object System.Windows.FrameworkCompatibilityPreferences::_lockObject
0x8af5  stloc.0
0x8af6  ldc.i4.0
0x8af7  stloc.1
0x8af8  ldloc.0
0x8af9  ldloca.s 1
0x8afb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x8b00  ldsfld   bool System.Windows.FrameworkCompatibilityPreferences::_isSealed
0x8b05  brfalse.s loc_8B2D
0x8b07  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x8b0c  ldc.i4.2
0x8b0d  newarr   [mscorlib]System.Object
0x8b12  dup
0x8b13  ldc.i4.0
0x8b14  ldstr    aHandletwowaybi// "HandleTwoWayBindingToPropertyWithNonPub"...
0x8b19  stelem.ref
0x8b1a  dup
0x8b1b  ldc.i4.1
0x8b1c  ldstr    aFrameworkcompa// "FrameworkCompatibilityPreferences"
0x8b21  stelem.ref
0x8b22  call     string System.Windows.SR::Get(string id, object[] args)
0x8b27  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8b2c  throw
0x8b2d  ldarga.s 0
0x8b2f  ldsfld   valuetype HandleBindingOptions System.Windows.FrameworkCompatibilityPreferences::_handleTwoWayBindingToPropertyWithNonPublicSetter
0x8b34  box      HandleBindingOptions
0x8b39  constrained. HandleBindingOptions
0x8b3f  callvirt instance int32 [mscorlib]System.Enum::CompareTo(object)
0x8b44  ldc.i4.0
0x8b45  ble.s    loc_8B4D
0x8b47  newobj   instance void [mscorlib]System.ArgumentException::.ctor()
0x8b4c  throw
0x8b4d  ldarg.0
0x8b4e  stsfld   valuetype HandleBindingOptions System.Windows.FrameworkCompatibilityPreferences::_handleTwoWayBindingToPropertyWithNonPublicSetter
0x8b53  leave.s  loc_8B5F
0x8b55  ldloc.1
0x8b56  brfalse.s loc_8B5E
0x8b58  ldloc.0
0x8b59  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x8b5e  endfinally
0x8b5f  ret
```
