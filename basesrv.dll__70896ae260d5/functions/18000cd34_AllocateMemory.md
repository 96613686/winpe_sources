# AllocateMemory

- ea: `0x18000cd34`
- end: `0x18000cd50`
- name: `AllocateMemory`
- size: `28`
- prototype: `PVOID __fastcall(SIZE_T)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000cd80`
- `0x18000d074`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000cd49`

## pseudocode

```c
PVOID __fastcall AllocateMemory(SIZE_T a1)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x18000cd34  mov     rax, gs:60h
0x18000cd3d  mov     r8, rcx
0x18000cd40  mov     edx, 8
0x18000cd45  mov     rcx, [rax+30h]
0x18000cd49  jmp     cs:__imp_RtlAllocateHeap
```
