# AiSvcOnCreateProcess$dtor$1

- ea: `0x18000c9f4`
- end: `0x18000ca02`
- name: `AiSvcOnCreateProcess$dtor$1`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, loader_planting`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c9fb`

## pseudocode

```c
void __fastcall AiSvcOnCreateProcess_dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 152));
}

```

## disassembly

```asm
0x18000c9f4  mov     rcx, [rdx+98h]
0x18000c9fb  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
