# AiAlloc

- ea: `0x180003fd4`
- end: `0x180003ffa`
- name: `AiAlloc`
- size: `38`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000423c`
- `0x180004584`
- `0x180004980`
- `0x180004f4c`
- `0x1800051fc`
- `0x18000533c`
- `0x180005740`
- `0x180005b70`
- `0x180005cfc`
- `0x180005e84`
- `0x180006d90`
- `0x180006f08`
- `0x180007274`
- `0x18000765c`
- `0x180007748`
- `0x18000818c`
- `0x1800086b0`
- `0x18000879c`
- `0x180008be4`

## callees

- `0x180003fd4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180003ff3`

## pseudocode

```c
PVOID __fastcall AiAlloc(SIZE_T a1)
{
  if ( a1 <= 0xFFFFFFFF )
    return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
  else
    return 0;
}

```

## disassembly

```asm
0x180003fd4  mov     eax, 0FFFFFFFFh
0x180003fd9  mov     r8, rcx
0x180003fdc  cmp     rcx, rax
0x180003fdf  jbe     short loc_180003FE4
0x180003fe1  xor     eax, eax
0x180003fe3  retn
0x180003fe4  mov     rcx, gs:60h
0x180003fed  xor     edx, edx
0x180003fef  mov     rcx, [rcx+30h]
0x180003ff3  jmp     cs:__imp_RtlAllocateHeap
```
