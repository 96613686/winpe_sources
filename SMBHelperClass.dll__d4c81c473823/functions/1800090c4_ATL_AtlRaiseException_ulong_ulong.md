# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x1800090c4`
- end: `0x1800090d5`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004770`
- `0x180006f6c`
- `0x1800090ec`
- `0x18000b408`
- `0x18000b4c8`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800090ce`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800090c4  xor     r9d, r9d
0x1800090c7  xor     r8d, r8d
0x1800090ca  lea     edx, [r9+1]
0x1800090ce  jmp     cs:__imp_RaiseException
```
