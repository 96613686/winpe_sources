# System.IO.Packaging.PackUriHelper::GetExceptionIfAbsoluteUri

- ea: `0x4acc0`
- end: `0x4acda`
- name: `System.IO.Packaging.PackUriHelper::GetExceptionIfAbsoluteUri`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4abe0`
- `0x4acb0`

## callees

- `0x2c100`
- `0x4acc0`

## string_xrefs

- `0x4acc8`: `URIShouldNotBeAbsolute`

## pseudocode

```c

```

## disassembly

```asm
0x4acc0  ldarg.0
0x4acc1  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x4acc6  brfalse.s loc_4ACD8
0x4acc8  ldstr    aUrishouldnotbe// "URIShouldNotBeAbsolute"
0x4accd  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4acd2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4acd7  ret
0x4acd8  ldnull
0x4acd9  ret
```
