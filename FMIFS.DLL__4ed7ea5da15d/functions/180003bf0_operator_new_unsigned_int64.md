# operator new(unsigned __int64)

- ea: `0x180003bf0`
- end: `0x180003c09`
- name: `??2@YAPEAX_K@Z`
- size: `25`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004900`
- `0x180008b00`
- `0x180008e18`
- `0x180008fc4`
- `0x18000940c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180003c02`

## pseudocode

```c
PVOID __fastcall operator new(SIZE_T a1)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180003bf0  mov     rax, gs:60h
0x180003bf9  mov     r8, rcx
0x180003bfc  xor     edx, edx
0x180003bfe  mov     rcx, [rax+30h]
0x180003c02  jmp     cs:__imp_RtlAllocateHeap
```
