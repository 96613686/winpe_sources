# System.Windows.Xps.Packaging.XpsManager::SetXpsDocumentStartingPart

- ea: `0x258f0`
- end: `0x25944`
- name: `System.Windows.Xps.Packaging.XpsManager::SetXpsDocumentStartingPart`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x24800`

## callees

- `0x1ef70`
- `0x20200`
- `0x258f0`

## string_xrefs

- `0x258f9`: `ReachPackaging_CannotModifyReadOnlyContainer`

## pseudocode

```c

```

## disassembly

```asm
0x258f0  ldarg.0
0x258f1  callvirt instance valuetype [mscorlib]System.IO.FileAccess [WindowsBase]System.IO.Packaging.Package::get_FileOpenAccess()
0x258f6  ldc.i4.1
0x258f7  bne.un.s loc_25909
0x258f9  ldstr    aReachpackaging_27// "ReachPackaging_CannotModifyReadOnlyCont"...
0x258fe  call     string System.Windows.Xps.SR::Get(string id)
0x25903  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x25908  throw
0x25909  ldarg.1
0x2590a  brtrue.s loc_25917
0x2590c  ldstr    aStartingpart// "startingPart"
0x25911  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x25916  throw
0x25917  ldarg.1
0x25918  callvirt instance class [WindowsBase]System.IO.Packaging.Package [WindowsBase]System.IO.Packaging.PackagePart::get_Package()
0x2591d  ldarg.0
0x2591e  beq.s    loc_25930
0x25920  ldstr    aReachpackaging_28// "ReachPackaging_PartFromDifferentContain"...
0x25925  call     string System.Windows.Xps.SR::Get(string id)
0x2592a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2592f  throw
0x25930  ldarg.0
0x25931  ldarg.1
0x25932  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x25937  ldc.i4.0
0x25938  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ReachPackageStartingPartRelationshipType()
0x2593d  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.Package::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string)
0x25942  pop
0x25943  ret
```
