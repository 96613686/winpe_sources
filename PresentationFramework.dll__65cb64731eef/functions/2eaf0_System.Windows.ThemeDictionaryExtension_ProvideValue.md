# System.Windows.ThemeDictionaryExtension::ProvideValue

- ea: `0x2eaf0`
- end: `0x2ebbc`
- name: `System.Windows.ThemeDictionaryExtension::ProvideValue`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x2ead0`
- `0x2eaf0`
- `0x2ebc0`
- `0x2ecb0`
- `0x2ece0`
- `0x38c40`
- `0x38c70`
- `0x1d5a60`
- `0x252400`

## string_xrefs

- `0x2eb26`: `MarkupExtensionNoContext`
- `0x2eafd`: `ThemeDictionaryExtension_Name`
- `0x2eb83`: `ThemeDictionaryExtension_Source`

## pseudocode

```c

```

## disassembly

```asm
0x2eaf0  ldarg.0
0x2eaf1  call     instance string System.Windows.ThemeDictionaryExtension::get_AssemblyName()
0x2eaf6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2eafb  brfalse.s loc_2EB0D
0x2eafd  ldstr    aThemedictionar// "ThemeDictionaryExtension_Name"
0x2eb02  call     string System.Windows.SR::Get(string id)
0x2eb07  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2eb0c  throw
0x2eb0d  ldarg.1
0x2eb0e  ldtoken  [System.Xaml]System.Windows.Markup.IProvideValueTarget
0x2eb13  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2eb18  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x2eb1d  isinst   [System.Xaml]System.Windows.Markup.IProvideValueTarget
0x2eb22  stloc.0
0x2eb23  ldloc.0
0x2eb24  brtrue.s loc_2EB52
0x2eb26  ldstr    aMarkupextensio_0// "MarkupExtensionNoContext"
0x2eb2b  ldc.i4.2
0x2eb2c  newarr   [mscorlib]System.Object
0x2eb31  dup
0x2eb32  ldc.i4.0
0x2eb33  ldarg.0
0x2eb34  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2eb39  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2eb3e  stelem.ref
0x2eb3f  dup
0x2eb40  ldc.i4.1
0x2eb41  ldstr    aIprovidevaluet// "IProvideValueTarget"
0x2eb46  stelem.ref
0x2eb47  call     string System.Windows.SR::Get(string id, object[] args)
0x2eb4c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2eb51  throw
0x2eb52  ldloc.0
0x2eb53  callvirt instance object [System.Xaml]System.Windows.Markup.IProvideValueTarget::get_TargetObject()
0x2eb58  stloc.1
0x2eb59  ldloc.0
0x2eb5a  callvirt instance object [System.Xaml]System.Windows.Markup.IProvideValueTarget::get_TargetProperty()
0x2eb5f  stloc.2
0x2eb60  ldloc.1
0x2eb61  isinst   System.Windows.ResourceDictionary
0x2eb66  stloc.3
0x2eb67  ldloc.2
0x2eb68  isinst   [mscorlib]System.Reflection.PropertyInfo
0x2eb6d  stloc.s  4
0x2eb6f  ldloc.3
0x2eb70  brfalse.s loc_2EB83
0x2eb72  ldloc.2
0x2eb73  brfalse.s loc_2EB93
0x2eb75  ldloc.s  4
0x2eb77  call     class [mscorlib]System.Reflection.PropertyInfo System.Windows.ThemeDictionaryExtension::get_SourceProperty()
0x2eb7c  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Inequality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x2eb81  brfalse.s loc_2EB93
0x2eb83  ldstr    aThemedictionar_0// "ThemeDictionaryExtension_Source"
0x2eb88  call     string System.Windows.SR::Get(string id)
0x2eb8d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2eb92  throw
0x2eb93  ldloc.3
0x2eb94  ldarg.0
0x2eb95  ldfld    string System.Windows.ThemeDictionaryExtension::_assemblyName
0x2eb9a  call     void System.Windows.ThemeDictionaryExtension::Register(class System.Windows.ResourceDictionary dictionary, string assemblyName)
0x2eb9f  ldloc.3
0x2eba0  ldc.i4.1
0x2eba1  stfld    bool System.Windows.ResourceDictionary::IsSourcedFromThemeDictionary
0x2eba6  ldarg.0
0x2eba7  ldfld    string System.Windows.ThemeDictionaryExtension::_assemblyName
0x2ebac  call     string ResourceDictionaries::get_ThemedResourceName()
0x2ebb1  call     string MS.Win32.UxThemeWrapper::get_ThemeName()
0x2ebb6  call     class [System]System.Uri System.Windows.ThemeDictionaryExtension::GenerateUri(string assemblyName, string resourceName, string themeName)
0x2ebbb  ret
```
