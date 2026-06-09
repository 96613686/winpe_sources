# operator new(unsigned __int64)

- ea: `0x140002d50`
- end: `0x140002d5c`
- name: `??2@YAPEAX_K@Z`
- size: `12`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140001208`
- `0x140004410`

## import_xrefs

- `WsmSvc!?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z` at `0x140002d55`

## pseudocode

```c
__int64 __fastcall operator new(__int64 a1)
{
  return WSManMemory::Alloc(a1, 0, 0);
}

```

## disassembly

```asm
0x140002d50  xor     r8d, r8d
0x140002d53  xor     edx, edx
0x140002d55  jmp     cs:__imp_?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
```
