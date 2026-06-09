# BaseSrvFreeWOWRecord

- ea: `0x18000ab1c`
- end: `0x18000ab7b`
- name: `BaseSrvFreeWOWRecord`
- size: `95`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008528`
- `0x18000905c`
- `0x18000a8f8`
- `0x18000c16c`
- `0x18000c820`

## callees

- `0x18000a9b4`
- `0x18000ab1c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000ab41`
- `ntdll!RtlFreeHeap` at `0x18000ab68`
- `ntdll!RtlFreeHeap` at `0x18000ab41`
- `ntdll!RtlFreeHeap` at `0x18000ab68`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeWOWRecord(_QWORD *P)
{
  void *v1; // r8
  BOOLEAN result; // al

  if ( P )
  {
    v1 = (void *)P[6];
    if ( v1 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
    BaseSrvFreeVDMInfo((_QWORD *)P[3]);
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x18000ab1c  test    rcx, rcx
0x18000ab1f  jz      short locret_18000AB79
0x18000ab21  push    rbx
0x18000ab22  sub     rsp, 20h
0x18000ab26  mov     r8, [rcx+30h]; P
0x18000ab2a  mov     rbx, rcx
0x18000ab2d  test    r8, r8
0x18000ab30  jz      short loc_18000AB4D
0x18000ab32  mov     rcx, gs:60h
0x18000ab3b  xor     edx, edx; Flags
0x18000ab3d  mov     rcx, [rcx+30h]; HeapHandle
0x18000ab41  call    cs:__imp_RtlFreeHeap
0x18000ab48  nop     dword ptr [rax+rax+00h]
0x18000ab4d  mov     rcx, [rbx+18h]; P
0x18000ab51  call    BaseSrvFreeVDMInfo
0x18000ab56  mov     rcx, gs:60h
0x18000ab5f  mov     r8, rbx; P
0x18000ab62  xor     edx, edx; Flags
0x18000ab64  mov     rcx, [rcx+30h]; HeapHandle
0x18000ab68  call    cs:__imp_RtlFreeHeap
0x18000ab6f  nop     dword ptr [rax+rax+00h]
0x18000ab74  add     rsp, 20h
0x18000ab78  pop     rbx
0x18000ab79  retn
```
