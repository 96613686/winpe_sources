# System.Windows.Documents.WinRTSpellerInterop::LoadDictionaryImpl

- ea: `0x12c0c0`
- end: `0x12c250`
- name: `System.Windows.Documents.WinRTSpellerInterop::LoadDictionaryImpl`
- size: `400`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x12be80`
- `0x12bea0`

## callees

- `0x38c70`
- `0x12c0c0`
- `0x12c320`
- `0x12c3a0`
- `0x130fa0`
- `0x133f10`

## string_xrefs

- `0x12c0e0`: `CustomDictionaryFailedToLoadDictionaryUri`
- `0x12c103`: `CustomDictionaryFailedToLoadDictionaryUri`
- `0x12c231`: `CustomDictionaryFailedToLoadDictionaryUri`

## pseudocode

```c

```

## disassembly

```asm
0x12c0c0  ldarg.0
0x12c0c1  ldfld    bool System.Windows.Documents.WinRTSpellerInterop::_isDisposed
0x12c0c6  brfalse.s loc_12C0D0
0x12c0c8  ldnull
0x12c0c9  ldnull
0x12c0ca  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12c0cf  ret
0x12c0d0  nop
0x12c0d1  ldc.i4.1
0x12c0d2  ldarg.1
0x12c0d3  newobj   instance void [mscorlib]System.Security.Permissions.FileIOPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.FileIOPermissionAccess, string)
0x12c0d8  call     instance void [mscorlib]System.Security.CodeAccessPermission::Demand()
0x12c0dd  leave.s  loc_12C0FB
0x12c0df  stloc.2
0x12c0e0  ldstr    aCustomdictiona// "CustomDictionaryFailedToLoadDictionaryU"...
0x12c0e5  ldc.i4.1
0x12c0e6  newarr   [mscorlib]System.Object
0x12c0eb  dup
0x12c0ec  ldc.i4.0
0x12c0ed  ldarg.1
0x12c0ee  stelem.ref
0x12c0ef  call     string System.Windows.SR::Get(string id, object[] args)
0x12c0f4  ldloc.2
0x12c0f5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, class [mscorlib]System.Exception)
0x12c0fa  throw
0x12c0fb  ldarg.1
0x12c0fc  call     bool [mscorlib]System.IO.File::Exists(string)
0x12c101  brtrue.s loc_12C11D
0x12c103  ldstr    aCustomdictiona// "CustomDictionaryFailedToLoadDictionaryU"...
0x12c108  ldc.i4.1
0x12c109  newarr   [mscorlib]System.Object
0x12c10e  dup
0x12c10f  ldc.i4.0
0x12c110  ldarg.1
0x12c111  stelem.ref
0x12c112  call     string System.Windows.SR::Get(string id, object[] args)
0x12c117  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x12c11c  throw
0x12c11d  ldc.i4.0
0x12c11e  stloc.0
0x12c11f  ldnull
0x12c120  stloc.1
0x12c121  ldnull
0x12c122  stloc.3
0x12c123  ldarg.1
0x12c124  ldc.i4.3
0x12c125  ldc.i4.1
0x12c126  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x12c12b  stloc.s  5
0x12c12d  ldnull
0x12c12e  stloc.s  6
0x12c130  ldloc.s  5
0x12c132  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x12c137  stloc.s  7
0x12c139  ldloc.s  7
0x12c13b  callvirt instance string [mscorlib]System.IO.TextReader::ReadLine()
0x12c140  stloc.s  6
0x12c142  ldloc.s  6
0x12c144  call     class [mscorlib]System.Globalization.CultureInfo System.Windows.Documents.WinRTSpellerInterop::TryParseLexiconCulture(string line)
0x12c149  stloc.3
0x12c14a  leave.s  loc_12C158
0x12c14c  ldloc.s  7
0x12c14e  brfalse.s loc_12C157
0x12c150  ldloc.s  7
0x12c152  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12c157  endfinally
0x12c158  leave.s  loc_12C166
0x12c15a  ldloc.s  5
0x12c15c  brfalse.s loc_12C165
0x12c15e  ldloc.s  5
0x12c160  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12c165  endfinally
0x12c166  ldloc.3
0x12c167  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_IetfLanguageTag()
0x12c16c  stloc.s  4
0x12c16e  ldloca.s 1
0x12c170  ldc.i4.2
0x12c171  ldc.i4.0
0x12c172  ldstr    aDic// "dic"
0x12c177  ldstr    aWpf// "WPF"
0x12c17c  call     class [mscorlib]System.IO.FileStream [PresentationCore]System.IO.FileHelper::CreateAndOpenTemporaryFile(string&, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileOptions, string, string)
0x12c181  stloc.s  8
0x12c183  ldarg.1
0x12c184  ldloc.s  8
0x12c186  call     void System.Windows.Documents.WinRTSpellerInterop::CopyToUnicodeFile(string sourcePath, class [mscorlib]System.IO.FileStream targetStream)
0x12c18b  ldc.i4.1
0x12c18c  stloc.0
0x12c18d  leave.s  loc_12C19B
0x12c18f  ldloc.s  8
0x12c191  brfalse.s loc_12C19A
0x12c193  ldloc.s  8
0x12c195  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12c19a  endfinally
0x12c19b  ldarg.0
0x12c19c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> System.Windows.Documents.WinRTSpellerInterop::_customDictionaryFiles
0x12c1a1  ldloc.s  4
0x12c1a3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::ContainsKey(var<u1>)
0x12c1a8  brtrue.s loc_12C1BC
0x12c1aa  ldarg.0
0x12c1ab  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> System.Windows.Documents.WinRTSpellerInterop::_customDictionaryFiles
0x12c1b0  ldloc.s  4
0x12c1b2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x12c1b7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::set_Item(var<u1>, !!T0)
0x12c1bc  ldarg.0
0x12c1bd  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> System.Windows.Documents.WinRTSpellerInterop::_customDictionaryFiles
0x12c1c2  ldloc.s  4
0x12c1c4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item(void)
0x12c1c9  ldloc.1
0x12c1ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x12c1cf  ldarg.0
0x12c1d0  ldc.i4.1
0x12c1d1  newobj   instance void System.Windows.Documents.Tracing.SpellerCOMActionTraceLogger::.ctor(class System.Windows.Documents.WinRTSpellerInterop caller, valuetype Actions action)
0x12c1d6  stloc.s  9
0x12c1d8  ldloc.1
0x12c1d9  ldloc.s  4
0x12c1db  ldc.i4.1
0x12c1dc  call     void System.Windows.Documents.MsSpellCheckLib.SpellCheckerFactory::RegisterUserDictionary(string dictionaryPath, string languageTag, [opt] bool suppressCOMExceptions)
0x12c1e1  leave.s  loc_12C1EF
0x12c1e3  ldloc.s  9
0x12c1e5  brfalse.s loc_12C1EE
0x12c1e7  ldloc.s  9
0x12c1e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12c1ee  endfinally
0x12c1ef  ldloc.s  4
0x12c1f1  ldloc.1
0x12c1f2  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12c1f7  stloc.s  0xA
0x12c1f9  leave.s  loc_12C24D
0x12c1fb  isinst   [mscorlib]System.Exception
0x12c200  dup
0x12c201  brtrue.s loc_12C207
0x12c203  pop
0x12c204  ldc.i4.0
0x12c205  br.s     loc_12C225
0x12c207  stloc.s  0xB
0x12c209  ldloc.s  0xB
0x12c20b  isinst   [mscorlib]System.Security.SecurityException
0x12c210  brtrue.s loc_12C221
0x12c212  ldloc.s  0xB
0x12c214  isinst   [mscorlib]System.ArgumentException
0x12c219  brtrue.s loc_12C221
0x12c21b  ldloc.0
0x12c21c  ldc.i4.0
0x12c21d  ceq
0x12c21f  br.s     loc_12C222
0x12c221  ldc.i4.1
0x12c222  ldc.i4.0
0x12c223  cgt.un
0x12c225  endfilter
0x12c227  pop
0x12c228  ldloc.1
0x12c229  brfalse.s loc_12C231
0x12c22b  ldloc.1
0x12c22c  call     void [PresentationCore]System.IO.FileHelper::DeleteTemporaryFile(string)
0x12c231  ldstr    aCustomdictiona// "CustomDictionaryFailedToLoadDictionaryU"...
0x12c236  ldc.i4.1
0x12c237  newarr   [mscorlib]System.Object
0x12c23c  dup
0x12c23d  ldc.i4.0
0x12c23e  ldarg.1
0x12c23f  stelem.ref
0x12c240  call     string System.Windows.SR::Get(string id, object[] args)
0x12c245  ldloc.s  0xB
0x12c247  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, class [mscorlib]System.Exception)
0x12c24c  throw
0x12c24d  ldloc.s  0xA
0x12c24f  ret
```
