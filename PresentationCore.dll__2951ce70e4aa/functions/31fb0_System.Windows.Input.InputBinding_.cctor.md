# System.Windows.Input.InputBinding::.cctor

- ea: `0x31fb0`
- end: `0x32036`
- name: `System.Windows.Input.InputBinding::.cctor`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2e760`

## string_xrefs

- `0x31fb0`: `Command`
- `0x31fe5`: `CommandParameter`
- `0x32008`: `CommandTarget`

## pseudocode

```c

```

## disassembly

```asm
0x31fb0  ldstr    aCommand_0// "Command"
0x31fb5  ldtoken  [System]System.Windows.Input.ICommand
0x31fba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31fbf  ldtoken  System.Windows.Input.InputBinding
0x31fc4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31fc9  ldnull
0x31fca  ldnull
0x31fcb  ldftn    void System.Windows.Input.InputBinding::OnCommandPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x31fd1  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x31fd6  newobj   instance void System.Windows.UIPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x31fdb  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x31fe0  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.InputBinding::CommandProperty
0x31fe5  ldstr    aCommandparamet// "CommandParameter"
0x31fea  ldtoken  [mscorlib]System.Object
0x31fef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31ff4  ldtoken  System.Windows.Input.InputBinding
0x31ff9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31ffe  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x32003  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.InputBinding::CommandParameterProperty
0x32008  ldstr    aCommandtarget// "CommandTarget"
0x3200d  ldtoken  System.Windows.IInputElement
0x32012  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32017  ldtoken  System.Windows.Input.InputBinding
0x3201c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32021  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x32026  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.InputBinding::CommandTargetProperty
0x3202b  newobj   instance void [mscorlib]System.Object::.ctor()
0x32030  stsfld   object System.Windows.Input.InputBinding::_dataLock
0x32035  ret
```
