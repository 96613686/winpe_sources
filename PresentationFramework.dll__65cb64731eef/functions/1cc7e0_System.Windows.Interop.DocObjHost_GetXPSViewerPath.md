# System.Windows.Interop.DocObjHost::GetXPSViewerPath

- ea: `0x1cc7e0`
- end: `0x1cc826`
- name: `System.Windows.Interop.DocObjHost::GetXPSViewerPath`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1cc480`

## callees

- `0x38c40`
- `0x1cc7e0`

## string_xrefs

- `0x1cc7e0`: `HKEY_LOCAL_MACHINE\SOFTWARE\Classes\CLSID\{7DDA204B-2097-47C9-8323-C40BB840AE44}\LocalServer32`
- `0x1cc80c`: `HKEY_LOCAL_MACHINE\SOFTWARE\Classes\CLSID\{7DDA204B-2097-47C9-8323-C40BB840AE44}\LocalServer32`
- `0x1cc7fa`: `DocumentApplicationRegistryKeyNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x1cc7e0  ldstr    aHkeyLocalMachi_0// "HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\"...
0x1cc7e5  ldnull
0x1cc7e6  ldnull
0x1cc7e7  call     object [mscorlib]Microsoft.Win32.Registry::GetValue(string, string, object)
0x1cc7ec  isinst   [mscorlib]System.String
0x1cc7f1  stloc.0
0x1cc7f2  ldloc.0
0x1cc7f3  brtrue.s loc_1CC81D
0x1cc7f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1cc7fa  ldstr    aDocumentapplic// "DocumentApplicationRegistryKeyNotFound"
0x1cc7ff  call     string System.Windows.SR::Get(string id)
0x1cc804  ldc.i4.1
0x1cc805  newarr   [mscorlib]System.Object
0x1cc80a  dup
0x1cc80b  ldc.i4.0
0x1cc80c  ldstr    aHkeyLocalMachi_0// "HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\"...
0x1cc811  stelem.ref
0x1cc812  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1cc817  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1cc81c  throw
0x1cc81d  ldloc.0
0x1cc81e  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1cc823  stloc.0
0x1cc824  ldloc.0
0x1cc825  ret
```
