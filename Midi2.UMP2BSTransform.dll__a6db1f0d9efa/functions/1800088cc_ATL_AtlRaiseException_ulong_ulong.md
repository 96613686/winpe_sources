# ATL::_AtlRaiseException(ulong,ulong)

- ea: `0x1800088cc`
- end: `0x1800088dd`
- name: `?_AtlRaiseException@ATL@@YAXKK@Z`
- size: `17`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004820`
- `0x18000628c`
- `0x180008c2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800088d6`

## pseudocode

```c
void __fastcall ATL::_AtlRaiseException(DWORD a1)
{
  RaiseException(a1, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800088cc  xor     r9d, r9d
0x1800088cf  xor     r8d, r8d
0x1800088d2  lea     edx, [r9+1]
0x1800088d6  jmp     cs:__imp_RaiseException
```
