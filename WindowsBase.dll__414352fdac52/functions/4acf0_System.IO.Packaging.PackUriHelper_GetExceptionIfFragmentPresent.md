# System.IO.Packaging.PackUriHelper::GetExceptionIfFragmentPresent

- ea: `0x4acf0`
- end: `0x4ad0f`
- name: `System.IO.Packaging.PackUriHelper::GetExceptionIfFragmentPresent`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4abe0`
- `0x4ace0`

## callees

- `0x2c100`
- `0x4acf0`

## string_xrefs

- `0x4acfd`: `PartUriCannotHaveAFragment`

## pseudocode

```c

```

## disassembly

```asm
0x4acf0  ldarg.0
0x4acf1  ldstr    asc_5D80C// "#"
0x4acf6  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4acfb  brfalse.s loc_4AD0D
0x4acfd  ldstr    aParturicannoth// "PartUriCannotHaveAFragment"
0x4ad02  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4ad07  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ad0c  ret
0x4ad0d  ldnull
0x4ad0e  ret
```
