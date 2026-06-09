# BaseSrvFreeDOSRecord

- ea: `0x18000a898`
- end: `0x18000a8f1`
- name: `BaseSrvFreeDOSRecord`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008394`
- `0x180008938`
- `0x18000a7d0`
- `0x18000b620`
- `0x18000c434`

## callees

- `0x18000a898`
- `0x18000a9b4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a8c2`
- `ntdll!RtlFreeHeap` at `0x18000a8c2`
- `ntdll!RtlFreeHeap` at `0x18000a8e5`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeDOSRecord(__int64 a1)
{
  void *v2; // r8

  BaseSrvFreeVDMInfo(*(PVOID *)(a1 + 32));
  v2 = *(void **)(a1 + 56);
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)a1);
}

```

## disassembly

```asm
0x18000a898  push    rbx
0x18000a89a  sub     rsp, 20h
0x18000a89e  mov     rbx, rcx
0x18000a8a1  mov     rcx, [rcx+20h]; P
0x18000a8a5  call    BaseSrvFreeVDMInfo
0x18000a8aa  mov     r8, [rbx+38h]; P
0x18000a8ae  test    r8, r8
0x18000a8b1  jz      short loc_18000A8CE
0x18000a8b3  mov     rcx, gs:60h
0x18000a8bc  xor     edx, edx; Flags
0x18000a8be  mov     rcx, [rcx+30h]; HeapHandle
0x18000a8c2  call    cs:__imp_RtlFreeHeap
0x18000a8c9  nop     dword ptr [rax+rax+00h]
0x18000a8ce  mov     rcx, gs:60h
0x18000a8d7  mov     r8, rbx
0x18000a8da  xor     edx, edx
0x18000a8dc  mov     rcx, [rcx+30h]
0x18000a8e0  add     rsp, 20h
0x18000a8e4  pop     rbx
0x18000a8e5  jmp     cs:__imp_RtlFreeHeap
```
