# operator delete[](void *)

- ea: `0x140006b48`
- end: `0x140006b6e`
- name: `??_V@YAXPEAX@Z`
- size: `38`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x140001e5c`
- `0x140002340`
- `0x1400025fc`
- `0x140002888`
- `0x140003e54`
- `0x140004950`
- `0x140006578`
- `0x140006750`
- `0x140007588`

## callees

- `0x140006b48`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140006b63`
- `ntdll!RtlFreeHeap` at `0x140006b63`

## pseudocode

```c
void __fastcall operator delete[](PVOID P)
{
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
}

```

## disassembly

```asm
0x140006b48  sub     rsp, 28h
0x140006b4c  mov     r8, rcx; P
0x140006b4f  test    rcx, rcx
0x140006b52  jz      short loc_140006B69
0x140006b54  mov     rcx, gs:60h
0x140006b5d  xor     edx, edx; Flags
0x140006b5f  mov     rcx, [rcx+30h]; HeapHandle
0x140006b63  call    cs:__imp_RtlFreeHeap
0x140006b69  add     rsp, 28h
0x140006b6d  retn
```
