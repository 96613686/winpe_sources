# System.Windows.Xps.Packaging.XmlPartEditor::OpenDocumentForWrite

- ea: `0x23b70`
- end: `0x23ba7`
- name: `System.Windows.Xps.Packaging.XmlPartEditor::OpenDocumentForWrite`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x23af0`
- `0x23bb0`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x239b0`
- `0x23b70`

## string_xrefs

- `0x23b78`: `ReachPackaging_OpenDocOrElementAlreadyCalled`

## pseudocode

```c

```

## disassembly

```asm
0x23b70  ldarg.0
0x23b71  ldfld    class [System.Xml]System.Xml.XmlTextWriter System.Windows.Xps.Packaging.XmlPartEditor::_xmlWriter
0x23b76  brfalse.s loc_23B88
0x23b78  ldstr    aReachpackaging_15// "ReachPackaging_OpenDocOrElementAlreadyC"...
0x23b7d  call     string System.Windows.Xps.SR::Get(string id)
0x23b82  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x23b87  throw
0x23b88  ldarg.0
0x23b89  call     instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.PartEditor::get_MetroPart()
0x23b8e  ldc.i4.2
0x23b8f  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream(valuetype [mscorlib]System.IO.FileMode)
0x23b94  stloc.0
0x23b95  ldarg.0
0x23b96  ldloc.0
0x23b97  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x23b9c  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x23ba1  stfld    class [System.Xml]System.Xml.XmlTextWriter System.Windows.Xps.Packaging.XmlPartEditor::_xmlWriter
0x23ba6  ret
```
