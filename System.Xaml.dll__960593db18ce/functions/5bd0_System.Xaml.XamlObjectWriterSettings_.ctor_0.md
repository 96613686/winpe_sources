# System.Xaml.XamlObjectWriterSettings::.ctor_0

- ea: `0x5bd0`
- end: `0x5c8d`
- name: `System.Xaml.XamlObjectWriterSettings::.ctor_0`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `registry_config`

## callers

- `0x5e50`
- `0x23490`

## callees

- `0x5bd0`
- `0x5c90`
- `0x5ca0`
- `0x5cb0`
- `0x5cc0`
- `0x5cd0`
- `0x5ce0`
- `0x5cf0`
- `0x5d00`
- `0x5d10`
- `0x5d20`
- `0x5d30`
- `0x5d40`
- `0x5d50`
- `0x5d60`
- `0x5d70`
- `0x5d80`
- `0x5d90`
- `0x5da0`
- `0x5db0`
- `0x5dc0`
- `0x5dd0`
- `0x5de0`
- `0x5df0`
- `0x5e00`
- `0x5e10`
- `0x5e20`
- `0x5e30`
- `0x5e40`
- `0x10240`

## pseudocode

```c

```

## disassembly

```asm
0x5bd0  ldarg.0
0x5bd1  call     instance void System.Xaml.XamlWriterSettings::.ctor()
0x5bd6  ldarg.1
0x5bd7  brtrue.s loc_5BE4
0x5bd9  ldstr    aSettings// "settings"
0x5bde  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5be3  throw
0x5be4  ldarg.0
0x5be5  ldarg.1
0x5be6  callvirt instance class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriterSettings::get_AfterBeginInitHandler()
0x5beb  call     instance void System.Xaml.XamlObjectWriterSettings::set_AfterBeginInitHandler(class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> value)
0x5bf0  ldarg.0
0x5bf1  ldarg.1
0x5bf2  callvirt instance class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriterSettings::get_BeforePropertiesHandler()
0x5bf7  call     instance void System.Xaml.XamlObjectWriterSettings::set_BeforePropertiesHandler(class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> value)
0x5bfc  ldarg.0
0x5bfd  ldarg.1
0x5bfe  callvirt instance class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriterSettings::get_AfterPropertiesHandler()
0x5c03  call     instance void System.Xaml.XamlObjectWriterSettings::set_AfterPropertiesHandler(class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> value)
0x5c08  ldarg.0
0x5c09  ldarg.1
0x5c0a  callvirt instance class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> System.Xaml.XamlObjectWriterSettings::get_AfterEndInitHandler()
0x5c0f  call     instance void System.Xaml.XamlObjectWriterSettings::set_AfterEndInitHandler(class [mscorlib]System.EventHandler`1<class System.Xaml.XamlObjectEventArgs> value)
0x5c14  ldarg.0
0x5c15  ldarg.1
0x5c16  callvirt instance class [mscorlib]System.EventHandler`1<class System.Windows.Markup.XamlSetValueEventArgs> System.Xaml.XamlObjectWriterSettings::get_XamlSetValueHandler()
0x5c1b  call     instance void System.Xaml.XamlObjectWriterSettings::set_XamlSetValueHandler(class [mscorlib]System.EventHandler`1<class System.Windows.Markup.XamlSetValueEventArgs> value)
0x5c20  ldarg.0
0x5c21  ldarg.1
0x5c22  callvirt instance object System.Xaml.XamlObjectWriterSettings::get_RootObjectInstance()
0x5c27  call     instance void System.Xaml.XamlObjectWriterSettings::set_RootObjectInstance(object value)
0x5c2c  ldarg.0
0x5c2d  ldarg.1
0x5c2e  callvirt instance bool System.Xaml.XamlObjectWriterSettings::get_IgnoreCanConvert()
0x5c33  call     instance void System.Xaml.XamlObjectWriterSettings::set_IgnoreCanConvert(bool value)
0x5c38  ldarg.0
0x5c39  ldarg.1
0x5c3a  callvirt instance class System.Windows.Markup.INameScope System.Xaml.XamlObjectWriterSettings::get_ExternalNameScope()
0x5c3f  call     instance void System.Xaml.XamlObjectWriterSettings::set_ExternalNameScope(class System.Windows.Markup.INameScope value)
0x5c44  ldarg.0
0x5c45  ldarg.1
0x5c46  callvirt instance bool System.Xaml.XamlObjectWriterSettings::get_SkipDuplicatePropertyCheck()
0x5c4b  call     instance void System.Xaml.XamlObjectWriterSettings::set_SkipDuplicatePropertyCheck(bool value)
0x5c50  ldarg.0
0x5c51  ldarg.1
0x5c52  callvirt instance bool System.Xaml.XamlObjectWriterSettings::get_RegisterNamesOnExternalNamescope()
0x5c57  call     instance void System.Xaml.XamlObjectWriterSettings::set_RegisterNamesOnExternalNamescope(bool value)
0x5c5c  ldarg.0
0x5c5d  ldarg.1
0x5c5e  callvirt instance class System.Xaml.Permissions.XamlAccessLevel System.Xaml.XamlObjectWriterSettings::get_AccessLevel()
0x5c63  call     instance void System.Xaml.XamlObjectWriterSettings::set_AccessLevel(class System.Xaml.Permissions.XamlAccessLevel value)
0x5c68  ldarg.0
0x5c69  ldarg.1
0x5c6a  callvirt instance bool System.Xaml.XamlObjectWriterSettings::get_SkipProvideValueOnRoot()
0x5c6f  call     instance void System.Xaml.XamlObjectWriterSettings::set_SkipProvideValueOnRoot(bool value)
0x5c74  ldarg.0
0x5c75  ldarg.1
0x5c76  callvirt instance bool System.Xaml.XamlObjectWriterSettings::get_PreferUnconvertedDictionaryKeys()
0x5c7b  call     instance void System.Xaml.XamlObjectWriterSettings::set_PreferUnconvertedDictionaryKeys(bool value)
0x5c80  ldarg.0
0x5c81  ldarg.1
0x5c82  callvirt instance class [System]System.Uri System.Xaml.XamlObjectWriterSettings::get_SourceBamlUri()
0x5c87  call     instance void System.Xaml.XamlObjectWriterSettings::set_SourceBamlUri(class [System]System.Uri value)
0x5c8c  ret
```
