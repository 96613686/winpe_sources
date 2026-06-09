# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x18000701c`
- end: `0x18000702d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003898`
- `0x180004a4c`
- `0x1800064c0`
- `0x18000b2c4`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180007026`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x18000701c  xor     r9d, r9d
0x18000701f  xor     r8d, r8d
0x180007022  lea     edx, [r9+1]
0x180007026  jmp     cs:__imp_RaiseException
```
