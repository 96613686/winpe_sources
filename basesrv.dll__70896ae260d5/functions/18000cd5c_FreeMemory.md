# FreeMemory

- ea: `0x18000cd5c`
- end: `0x18000cd75`
- name: `FreeMemory`
- size: `25`
- prototype: `BOOLEAN __fastcall(void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000cd80`
- `0x18000d074`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000cd6e`

## pseudocode

```c
BOOLEAN __fastcall FreeMemory(void *a1)
{
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18000cd5c  mov     rax, gs:60h
0x18000cd65  mov     r8, rcx
0x18000cd68  xor     edx, edx
0x18000cd6a  mov     rcx, [rax+30h]
0x18000cd6e  jmp     cs:__imp_RtlFreeHeap
```
