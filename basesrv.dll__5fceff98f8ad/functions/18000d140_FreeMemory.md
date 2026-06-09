# FreeMemory

- ea: `0x18000d140`
- end: `0x18000d159`
- name: `FreeMemory`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000d164`
- `0x18000d460`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000d152`

## pseudocode

```c
BOOLEAN __fastcall FreeMemory(void *a1)
{
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18000d140  mov     rax, gs:60h
0x18000d149  mov     r8, rcx
0x18000d14c  xor     edx, edx
0x18000d14e  mov     rcx, [rax+30h]
0x18000d152  jmp     cs:__imp_RtlFreeHeap
```
