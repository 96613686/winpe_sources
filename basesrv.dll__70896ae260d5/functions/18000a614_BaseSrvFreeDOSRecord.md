# BaseSrvFreeDOSRecord

- ea: `0x18000a614`
- end: `0x18000a66d`
- name: `BaseSrvFreeDOSRecord`
- size: `89`
- prototype: `BOOLEAN __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000806c`
- `0x180008644`
- `0x18000a54c`
- `0x18000b380`
- `0x18000c088`

## callees

- `0x18000a614`
- `0x18000a72c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a63e`
- `ntdll!RtlFreeHeap` at `0x18000a63e`
- `ntdll!RtlFreeHeap` at `0x18000a661`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeDOSRecord(__int64 a1)
{
  void *v2; // r8

  BaseSrvFreeVDMInfo(*(_QWORD **)(a1 + 32));
  v2 = *(void **)(a1 + 56);
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)a1);
}

```

## disassembly

```asm
0x18000a614  push    rbx
0x18000a616  sub     rsp, 20h
0x18000a61a  mov     rbx, rcx
0x18000a61d  mov     rcx, [rcx+20h]; P
0x18000a621  call    BaseSrvFreeVDMInfo
0x18000a626  mov     r8, [rbx+38h]; P
0x18000a62a  test    r8, r8
0x18000a62d  jz      short loc_18000A64A
0x18000a62f  mov     rcx, gs:60h
0x18000a638  xor     edx, edx; Flags
0x18000a63a  mov     rcx, [rcx+30h]; HeapHandle
0x18000a63e  call    cs:__imp_RtlFreeHeap
0x18000a645  nop     dword ptr [rax+rax+00h]
0x18000a64a  mov     rcx, gs:60h
0x18000a653  mov     r8, rbx
0x18000a656  xor     edx, edx
0x18000a658  mov     rcx, [rcx+30h]
0x18000a65c  add     rsp, 20h
0x18000a660  pop     rbx
0x18000a661  jmp     cs:__imp_RtlFreeHeap
```
