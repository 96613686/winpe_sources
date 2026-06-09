# System.IO.Packaging.PackagePart::ThrowIfPackagePartDeleted

- ea: `0x49f10`
- end: `0x49f29`
- name: `System.IO.Packaging.PackagePart::ThrowIfPackagePartDeleted`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x49ee0`

## callees

- `0x2c100`
- `0x49f10`

## string_xrefs

- `0x49f18`: `PackagePartDeleted`

## pseudocode

```c

```

## disassembly

```asm
0x49f10  ldarg.0
0x49f11  ldfld    bool System.IO.Packaging.PackagePart::_deleted
0x49f16  brfalse.s loc_49F28
0x49f18  ldstr    aPackagepartdel// "PackagePartDeleted"
0x49f1d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x49f22  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x49f27  throw
0x49f28  ret
```
