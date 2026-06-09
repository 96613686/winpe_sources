# System.Windows.Xps.Packaging.XmlPartEditor::OpenDocumentForRead

- ea: `0x23b30`
- end: `0x23b62`
- name: `System.Windows.Xps.Packaging.XmlPartEditor::OpenDocumentForRead`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x23b10`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x239b0`
- `0x23b30`

## string_xrefs

- `0x23b38`: `ReachPackaging_OpenDocOrElementAlreadyCalled`

## pseudocode

```c

```

## disassembly

```asm
0x23b30  ldarg.0
0x23b31  ldfld    class [System.Xml]System.Xml.XmlTextReader System.Windows.Xps.Packaging.XmlPartEditor::_xmlReader
0x23b36  brfalse.s loc_23B48
0x23b38  ldstr    aReachpackaging_15// "ReachPackaging_OpenDocOrElementAlreadyC"...
0x23b3d  call     string System.Windows.Xps.SR::Get(string id)
0x23b42  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x23b47  throw
0x23b48  ldarg.0
0x23b49  call     instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.PartEditor::get_MetroPart()
0x23b4e  ldc.i4.3
0x23b4f  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream(valuetype [mscorlib]System.IO.FileMode)
0x23b54  stloc.0
0x23b55  ldarg.0
0x23b56  ldloc.0
0x23b57  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.Stream)
0x23b5c  stfld    class [System.Xml]System.Xml.XmlTextReader System.Windows.Xps.Packaging.XmlPartEditor::_xmlReader
0x23b61  ret
```
