# System.IO.Packaging.StreamInfo::CreateTimeReadOnlyCheck

- ea: `0x47f10`
- end: `0x47f48`
- name: `System.IO.Packaging.StreamInfo::CreateTimeReadOnlyCheck`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x47a20`
- `0x47cf0`

## callees

- `0x2c100`
- `0x46ae0`
- `0x47440`
- `0x47f10`

## string_xrefs

- `0x47f23`: `CanNotCreateInReadOnly`
- `0x47f37`: `CanNotCreateAsReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x47f10  ldc.i4.1
0x47f11  ldarg.0
0x47f12  ldfld    class System.IO.Packaging.StorageInfo System.IO.Packaging.StreamInfo::parentStorage
0x47f17  callvirt instance class System.IO.Packaging.StorageRoot System.IO.Packaging.StorageInfo::get_Root()
0x47f1c  callvirt instance valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.StorageRoot::get_OpenAccess()
0x47f21  bne.un.s loc_47F33
0x47f23  ldstr    aCannotcreatein// "CanNotCreateInReadOnly"
0x47f28  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47f2d  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x47f32  throw
0x47f33  ldarg.1
0x47f34  ldc.i4.1
0x47f35  bne.un.s loc_47F47
0x47f37  ldstr    aCannotcreateas// "CanNotCreateAsReadOnly"
0x47f3c  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x47f41  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x47f46  throw
0x47f47  ret
```
