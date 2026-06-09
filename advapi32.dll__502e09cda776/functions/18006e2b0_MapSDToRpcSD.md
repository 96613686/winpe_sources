# MapSDToRpcSD

- ea: `0x18006e2b0`
- end: `0x18006e366`
- name: `MapSDToRpcSD`
- size: `182`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR AbsoluteSD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006e258`

## callees

- `0x18006e2b0`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18006e2d8`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006e2d8`
- `ntdll!RtlValidSecurityDescriptor` at `0x18006e2c5`
- `ntdll!RtlValidSecurityDescriptor` at `0x18006e2c5`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18006e324`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18006e324`
- `ntdll!RtlAllocateHeap` at `0x18006e300`
- `ntdll!RtlAllocateHeap` at `0x18006e300`
- `ntdll!RtlNtStatusToDosError` at `0x18006e332`
- `ntdll!RtlNtStatusToDosError` at `0x18006e332`

## pseudocode

```c
ULONG __fastcall MapSDToRpcSD(PSECURITY_DESCRIPTOR AbsoluteSD, __int64 a2)
{
  ULONG v4; // edi
  PVOID Heap; // rax
  ULONG *v6; // r8
  NTSTATUS SelfRelativeSD; // eax

  if ( !RtlValidSecurityDescriptor(AbsoluteSD) )
    return 87;
  v4 = RtlLengthSecurityDescriptor(AbsoluteSD);
  Heap = *(PVOID *)a2;
  if ( *(_QWORD *)a2 )
  {
    v6 = (ULONG *)(a2 + 8);
    if ( *(_DWORD *)(a2 + 8) >= v4 )
      goto LABEL_5;
  }
  else
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    *(_QWORD *)a2 = Heap;
    if ( Heap )
    {
      v6 = (ULONG *)(a2 + 8);
      *(_DWORD *)(a2 + 8) = v4;
LABEL_5:
      *(_DWORD *)(a2 + 12) = v4;
      SelfRelativeSD = RtlMakeSelfRelativeSD(AbsoluteSD, Heap, v6);
      return RtlNtStatusToDosError(SelfRelativeSD);
    }
  }
  return 14;
}

```

## disassembly

```asm
0x18006e2b0  mov     [rsp+arg_0], rbx
0x18006e2b5  mov     [rsp+arg_8], rsi
0x18006e2ba  push    rdi
0x18006e2bb  sub     rsp, 20h
0x18006e2bf  mov     rbx, rdx
0x18006e2c2  mov     rsi, rcx
0x18006e2c5  call    cs:__imp_RtlValidSecurityDescriptor
0x18006e2cc  nop     dword ptr [rax+rax+00h]
0x18006e2d1  test    al, al
0x18006e2d3  jz      short loc_18006E350
0x18006e2d5  mov     rcx, rsi; SecurityDescriptor
0x18006e2d8  call    cs:__imp_RtlLengthSecurityDescriptor
0x18006e2df  nop     dword ptr [rax+rax+00h]
0x18006e2e4  mov     edi, eax
0x18006e2e6  mov     rax, [rbx]
0x18006e2e9  test    rax, rax
0x18006e2ec  jnz     short loc_18006E340
0x18006e2ee  mov     rcx, gs:60h
0x18006e2f7  mov     r8d, edi; Size
0x18006e2fa  xor     edx, edx; Flags
0x18006e2fc  mov     rcx, [rcx+30h]; HeapHandle
0x18006e300  call    cs:__imp_RtlAllocateHeap
0x18006e307  nop     dword ptr [rax+rax+00h]
0x18006e30c  mov     [rbx], rax
0x18006e30f  test    rax, rax
0x18006e312  jz      short loc_18006E349
0x18006e314  lea     r8, [rbx+8]; BufferLength
0x18006e318  mov     [r8], edi
0x18006e31b  mov     rdx, rax; SelfRelativeSD
0x18006e31e  mov     [rbx+0Ch], edi
0x18006e321  mov     rcx, rsi; AbsoluteSD
0x18006e324  call    cs:__imp_RtlMakeSelfRelativeSD
0x18006e32b  nop     dword ptr [rax+rax+00h]
0x18006e330  mov     ecx, eax; Status
0x18006e332  call    cs:__imp_RtlNtStatusToDosError
0x18006e339  nop     dword ptr [rax+rax+00h]
0x18006e33e  jmp     short loc_18006E355
0x18006e340  lea     r8, [rbx+8]
0x18006e344  cmp     [r8], edi
0x18006e347  jnb     short loc_18006E31B
0x18006e349  mov     eax, 0Eh
0x18006e34e  jmp     short loc_18006E355
0x18006e350  mov     eax, 57h ; 'W'
0x18006e355  mov     rbx, [rsp+28h+arg_0]
0x18006e35a  mov     rsi, [rsp+28h+arg_8]
0x18006e35f  add     rsp, 20h
0x18006e363  pop     rdi
0x18006e364  retn
```
