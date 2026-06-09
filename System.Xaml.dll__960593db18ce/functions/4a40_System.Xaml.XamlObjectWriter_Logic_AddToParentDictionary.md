# System.Xaml.XamlObjectWriter::Logic_AddToParentDictionary

- ea: `0x4a40`
- end: `0x4b0a`
- name: `System.Xaml.XamlObjectWriter::Logic_AddToParentDictionary`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x4940`
- `0x5a20`

## callees

- `0x2870`
- `0x4110`
- `0x4a40`
- `0x8b40`
- `0x20300`
- `0x21540`
- `0x21590`
- `0x215d0`
- `0x21610`
- `0x21670`
- `0x216d0`
- `0x216f0`
- `0x21790`
- `0x21c30`
- `0x21c90`
- `0x21cb0`
- `0x21d10`
- `0x21d30`

## pseudocode

```c

```

## disassembly

```asm
0x4a40  ldarg.1
0x4a41  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentKeyIsUnconverted()
0x4a46  brfalse  loc_4AEA
0x4a4b  ldarg.1
0x4a4c  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentShouldNotConvertChildKeys()
0x4a51  brtrue   loc_4AEA
0x4a56  ldarg.1
0x4a57  callvirt instance bool MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentShouldConvertChildKeys()
0x4a5c  brtrue.s loc_4AB5
0x4a5e  ldarg.0
0x4a5f  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x4a64  ldarg.1
0x4a65  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentCollection()
0x4a6a  ldarg.1
0x4a6b  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x4a70  ldarg.3
0x4a71  ldarg.1
0x4a72  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x4a77  ldarg.2
0x4a78  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::AddToDictionary(object collection, class System.Xaml.XamlType dictionaryType, object value, class System.Xaml.XamlType valueXamlType, object key)
0x4a7d  ldarg.1
0x4a7e  ldc.i4.1
0x4a7f  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_ParentShouldNotConvertChildKeys(bool value)
0x4a84  leave    loc_4B09
0x4a89  stloc.0
0x4a8a  ldloc.0
0x4a8b  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x4a90  isinst   [mscorlib]System.ArgumentException
0x4a95  brtrue.s loc_4AA6
0x4a97  ldloc.0
0x4a98  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x4a9d  isinst   [mscorlib]System.InvalidCastException
0x4aa2  brtrue.s loc_4AA6
0x4aa4  rethrow
0x4aa6  call     bool [mscorlib]System.Diagnostics.Debugger::IsLogging()
0x4aab  pop
0x4aac  leave.s  loc_4AAE
0x4aae  ldarg.1
0x4aaf  ldc.i4.1
0x4ab0  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_ParentShouldConvertChildKeys(bool value)
0x4ab5  ldarg.1
0x4ab6  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_Key()
0x4abb  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentProperty(class System.Xaml.XamlMember value)
0x4ac0  ldarg.1
0x4ac1  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PushScope()
0x4ac6  ldarg.1
0x4ac7  ldarg.2
0x4ac8  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentInstance(object value)
0x4acd  ldarg.0
0x4ace  ldarg.1
0x4acf  call     instance bool System.Xaml.XamlObjectWriter::Logic_CreatePropertyValueFromValue(class MS.Internal.Xaml.Context.ObjectWriterContext ctx)
0x4ad4  pop
0x4ad5  ldarg.1
0x4ad6  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x4adb  starg.s  2
0x4add  ldarg.1
0x4ade  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::PopScope()
0x4ae3  ldarg.1
0x4ae4  ldnull
0x4ae5  callvirt instance void MS.Internal.Xaml.Context.ObjectWriterContext::set_CurrentProperty(class System.Xaml.XamlMember value)
0x4aea  ldarg.0
0x4aeb  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x4af0  ldarg.1
0x4af1  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentCollection()
0x4af6  ldarg.1
0x4af7  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_ParentType()
0x4afc  ldarg.3
0x4afd  ldarg.1
0x4afe  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x4b03  ldarg.2
0x4b04  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::AddToDictionary(object collection, class System.Xaml.XamlType dictionaryType, object value, class System.Xaml.XamlType valueXamlType, object key)
0x4b09  ret
```
