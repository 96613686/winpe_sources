# MapSDToRpcSD

- ea: `0x18006177c`
- end: `0x180061813`
- name: `MapSDToRpcSD`
- size: `151`
- prototype: `ULONG __fastcall(PSECURITY_DESCRIPTOR AbsoluteSD, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180061728`

## callees

- `0x18006177c`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18006179e`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18006179e`
- `ntdll!RtlValidSecurityDescriptor` at `0x180061791`
- `ntdll!RtlValidSecurityDescriptor` at `0x180061791`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800617de`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800617de`
- `ntdll!RtlAllocateHeap` at `0x1800617c0`
- `ntdll!RtlAllocateHeap` at `0x1800617c0`
- `ntdll!RtlNtStatusToDosError` at `0x1800617e6`
- `ntdll!RtlNtStatusToDosError` at `0x1800617e6`

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
0x18006177c  mov     [rsp+arg_0], rbx
0x180061781  mov     [rsp+arg_8], rsi
0x180061786  push    rdi
0x180061787  sub     rsp, 20h
0x18006178b  mov     rbx, rdx
0x18006178e  mov     rsi, rcx
0x180061791  call    cs:__imp_RtlValidSecurityDescriptor
0x180061797  test    al, al
0x180061799  jz      short loc_1800617FE
0x18006179b  mov     rcx, rsi; SecurityDescriptor
0x18006179e  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800617a4  mov     edi, eax
0x1800617a6  mov     rax, [rbx]
0x1800617a9  test    rax, rax
0x1800617ac  jnz     short loc_1800617EE
0x1800617ae  mov     rcx, gs:60h
0x1800617b7  mov     r8d, edi; Size
0x1800617ba  xor     edx, edx; Flags
0x1800617bc  mov     rcx, [rcx+30h]; HeapHandle
0x1800617c0  call    cs:__imp_RtlAllocateHeap
0x1800617c6  mov     [rbx], rax
0x1800617c9  test    rax, rax
0x1800617cc  jz      short loc_1800617F7
0x1800617ce  lea     r8, [rbx+8]; BufferLength
0x1800617d2  mov     [r8], edi
0x1800617d5  mov     rdx, rax; SelfRelativeSD
0x1800617d8  mov     [rbx+0Ch], edi
0x1800617db  mov     rcx, rsi; AbsoluteSD
0x1800617de  call    cs:__imp_RtlMakeSelfRelativeSD
0x1800617e4  mov     ecx, eax; Status
0x1800617e6  call    cs:__imp_RtlNtStatusToDosError
0x1800617ec  jmp     short loc_180061803
0x1800617ee  lea     r8, [rbx+8]
0x1800617f2  cmp     [r8], edi
0x1800617f5  jnb     short loc_1800617D5
0x1800617f7  mov     eax, 0Eh
0x1800617fc  jmp     short loc_180061803
0x1800617fe  mov     eax, 57h ; 'W'
0x180061803  mov     rbx, [rsp+28h+arg_0]
0x180061808  mov     rsi, [rsp+28h+arg_8]
0x18006180d  add     rsp, 20h
0x180061811  pop     rdi
0x180061812  retn
```
