# EaLibAllocate

- ea: `0x180003630`
- end: `0x18000364c`
- name: `EaLibAllocate`
- size: `28`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `19`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001e00`
- `0x180003250`
- `0x180003660`
- `0x1800044c0`
- `0x180006e20`
- `0x1800086d0`
- `0x180008990`
- `0x180008fc0`
- `0x180009250`
- `0x180009370`
- `0x180009940`
- `0x180009a88`
- `0x180009d38`
- `0x180009ff0`
- `0x18000a2cc`
- `0x18000a414`
- `0x18000a5f8`
- `0x18000ab7c`
- `0x18000ad20`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180003645`

## pseudocode

```c
PVOID __fastcall EaLibAllocate(SIZE_T a1)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x180003630  mov     rax, gs:60h
0x180003639  mov     r8, rcx
0x18000363c  mov     edx, 8
0x180003641  mov     rcx, [rax+30h]
0x180003645  jmp     cs:__imp_RtlAllocateHeap
```
