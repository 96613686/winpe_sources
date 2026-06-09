# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x180008f7c`
- end: `0x180008f8d`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180006764`
- `0x18000678c`
- `0x18000729c`
- `0x1800087c8`
- `0x18000f568`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180008f86`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x180008f7c  xor     r9d, r9d
0x180008f7f  xor     r8d, r8d
0x180008f82  lea     edx, [r9+1]
0x180008f86  jmp     cs:__imp_RaiseException
```
