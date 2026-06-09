# AllocateMemory

- ea: `0x18000d118`
- end: `0x18000d134`
- name: `AllocateMemory`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000d164`
- `0x18000d460`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000d12d`

## pseudocode

```c
PVOID __fastcall AllocateMemory(SIZE_T a1)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x18000d118  mov     rax, gs:60h
0x18000d121  mov     r8, rcx
0x18000d124  mov     edx, 8
0x18000d129  mov     rcx, [rax+30h]
0x18000d12d  jmp     cs:__imp_RtlAllocateHeap
```
