# Microsoft.VisualStudio.Setup.Cache.Instance::set_Errors

- ea: `0x1aa70`
- end: `0x1aae5`
- name: `Microsoft.VisualStudio.Setup.Cache.Instance::set_Errors`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19020`
- `0x1afb0`

## callees

- `0x193b0`
- `0x193e0`
- `0x1a990`
- `0x1a9a0`
- `0x1aa70`
- `0x1b000`

## pseudocode

```c

```

## disassembly

```asm
0x1aa70  ldarg.0
0x1aa71  ldfld    class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::errors
0x1aa76  brfalse.s loc_1AA8F
0x1aa78  ldarg.0
0x1aa79  ldfld    class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::errors
0x1aa7e  ldarg.0
0x1aa7f  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::OnErrorsChanged(object source, class [System]System.ComponentModel.PropertyChangedEventArgs args)
0x1aa85  newobj   instance void [System]System.ComponentModel.PropertyChangedEventHandler::.ctor(object, native int)
0x1aa8a  callvirt instance void Microsoft.VisualStudio.Setup.Cache.ErrorState::remove_PropertyChanged(class [System]System.ComponentModel.PropertyChangedEventHandler value)
0x1aa8f  ldarg.0
0x1aa90  ldarg.1
0x1aa91  stfld    class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::errors
0x1aa96  ldarg.0
0x1aa97  ldarg.0
0x1aa98  ldflda   bool Microsoft.VisualStudio.Setup.Cache.Instance::errorsChanged
0x1aa9d  ldstr    aErrors// "Errors"
0x1aaa2  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::OnPropertyChanged(bool& field, [opt] string propertyName)
0x1aaa7  ldarg.0
0x1aaa8  ldfld    class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::errors
0x1aaad  brfalse.s loc_1AAD6
0x1aaaf  ldarg.0
0x1aab0  ldarg.0
0x1aab1  call     instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1aab6  ldc.i4.s 0xF7
0x1aab8  and
0x1aab9  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_State(valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState value)
0x1aabe  ldarg.0
0x1aabf  ldfld    class Microsoft.VisualStudio.Setup.Cache.ErrorState Microsoft.VisualStudio.Setup.Cache.Instance::errors
0x1aac4  ldarg.0
0x1aac5  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.Instance::OnErrorsChanged(object source, class [System]System.ComponentModel.PropertyChangedEventArgs args)
0x1aacb  newobj   instance void [System]System.ComponentModel.PropertyChangedEventHandler::.ctor(object, native int)
0x1aad0  callvirt instance void Microsoft.VisualStudio.Setup.Cache.ErrorState::add_PropertyChanged(class [System]System.ComponentModel.PropertyChangedEventHandler value)
0x1aad5  ret
0x1aad6  ldarg.0
0x1aad7  ldarg.0
0x1aad8  call     instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1aadd  ldc.i4.8
0x1aade  or
0x1aadf  call     instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_State(valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState value)
0x1aae4  ret
```
