# System.Windows.Xps.Packaging.XpsResource::RelativeUri

- ea: `0x26450`
- end: `0x26477`
- name: `System.Windows.Xps.Packaging.XpsResource::RelativeUri`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x25950`
- `0x25a70`
- `0x26450`

## string_xrefs

- `0x26459`: `inUri`

## pseudocode

```c

```

## disassembly

```asm
0x26450  ldarg.1
0x26451  ldnull
0x26452  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x26457  brfalse.s loc_26464
0x26459  ldstr    aInuri// "inUri"
0x2645e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x26463  throw
0x26464  ldarg.0
0x26465  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2646a  ldarg.1
0x2646b  call     string System.Windows.Xps.Packaging.XpsManager::MakeRelativePath(class [System]System.Uri baseUri, class [System]System.Uri fileUri)
0x26470  ldc.i4.2
0x26471  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x26476  ret
```
