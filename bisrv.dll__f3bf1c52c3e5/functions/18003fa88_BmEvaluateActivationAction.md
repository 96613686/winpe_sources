# BmEvaluateActivationAction

- ea: `0x18003fa88`
- end: `0x18003fc57`
- name: `BmEvaluateActivationAction`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006caac`

## callees

- `0x18003fa88`
- `0x180095010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003fab7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003fab7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003fad1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003fbf9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003fad1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003fbf9`
- `ntdll!RtlAllocateHeap` at `0x18003fb99`
- `ntdll!RtlAllocateHeap` at `0x18003fc28`
- `ntdll!RtlAllocateHeap` at `0x18003fb99`
- `ntdll!RtlAllocateHeap` at `0x18003fc28`
- `ntdll!RtlValidSid` at `0x18003fbb9`
- `ntdll!RtlValidSid` at `0x18003fbb9`
- `ntdll!RtlCopySid` at `0x18003fc3f`
- `ntdll!RtlCopySid` at `0x18003fc3f`
- `ntdll!RtlLengthSid` at `0x18003fc0e`
- `ntdll!RtlLengthSid` at `0x18003fc0e`

## pseudocode

```c
__int64 __fastcall BmEvaluateActivationAction(
        unsigned int a1,
        void *a2,
        __int64 a3,
        int a4,
        _OWORD *a5,
        __int64 a6,
        __int64 a7,
        char a8,
        __int64 a9,
        int a10,
        char a11,
        _DWORD *a12,
        __int64 a13)
{
  unsigned __int16 v17; // ax
  NTSTATUS v18; // ebx
  char *Heap; // rdi
  struct _LIST_ENTRY *v21; // rcx
  ULONG v22; // esi
  PVOID v23; // rax

  *a12 = 1;
  RtlAcquireSRWLockExclusive(&BmpActivationBufferLock);
  if ( !BmpReady )
  {
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x28u);
    if ( Heap )
    {
      *(_OWORD *)Heap = *a5;
      if ( !RtlValidSid(a2) )
      {
        v18 = -1073741704;
LABEL_10:
        RtlReleaseSRWLockExclusive(&BmpActivationBufferLock);
        return (unsigned int)v18;
      }
      v22 = RtlLengthSid(a2);
      v23 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
      *((_QWORD *)Heap + 2) = v23;
      if ( v23 )
      {
        v18 = RtlCopySid(v22, v23, a2);
        if ( v18 >= 0 )
        {
          v21 = off_1800C3128;
          if ( off_1800C3128->Flink != &BmpActivationBuffer )
            __fastfail(3u);
          *((_QWORD *)Heap + 3) = &BmpActivationBuffer;
          *((_QWORD *)Heap + 4) = v21;
          v21->Flink = (struct _LIST_ENTRY *)(Heap + 24);
          off_1800C3128 = (struct _LIST_ENTRY *)(Heap + 24);
        }
        goto LABEL_10;
      }
    }
    v18 = -1073741801;
    goto LABEL_10;
  }
  RtlReleaseSRWLockExclusive(&BmpActivationBufferLock);
  v17 = (*(__int64 (__fastcall **)(struct Execution::IBackgroundManager *, _QWORD, void *, __int64, int, _OWORD *, __int64, __int64, char, __int64, int, int, _DWORD *, __int64))(*(_QWORD *)BmpManager + 24LL))(
          BmpManager,
          a1,
          a2,
          a3,
          a4,
          a5,
          a6,
          a7,
          a8,
          a9,
          a10,
          a11 != 0 ? 2 : 0,
          a12,
          a13);
  v18 = v17;
  if ( v17 )
    return v17 | 0xC0070000;
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18003fa88  push    rbx
0x18003fa8a  push    rbp
0x18003fa8b  push    rsi
0x18003fa8c  push    rdi
0x18003fa8d  push    r14
0x18003fa8f  sub     rsp, 80h
0x18003fa96  mov     rdi, [rsp+0A8h+arg_58]
0x18003fa9e  mov     r14d, ecx
0x18003faa1  lea     rcx, ?BmpActivationBufferLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK BmpActivationBufferLock
0x18003faa8  mov     esi, r9d
0x18003faab  mov     rbp, r8
0x18003faae  mov     rbx, rdx
0x18003fab1  mov     dword ptr [rdi], 1
0x18003fab7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003fabd  cmp     cs:?BmpReady@@3HA, 0; int BmpReady
0x18003fac4  jz      loc_18003FB86
0x18003faca  lea     rcx, ?BmpActivationBufferLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK BmpActivationBufferLock
0x18003fad1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003fad7  mov     r11, cs:?BmpManager@@3V?$ComPtr@UIBackgroundManager@Execution@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Execution::IBackgroundManager> BmpManager
0x18003fade  mov     r9, rbp
0x18003fae1  mov     rdx, [rsp+0A8h+arg_40]
0x18003fae9  mov     r8, rbx
0x18003faec  neg     [rsp+0A8h+arg_50]
0x18003faf3  mov     rax, [r11]
0x18003faf6  sbb     ecx, ecx
0x18003faf8  and     ecx, 2
0x18003fafb  mov     r10, [rax+18h]
0x18003faff  mov     rax, [rsp+0A8h+arg_60]
0x18003fb07  mov     [rsp+0A8h+var_40], rax
0x18003fb0c  mov     eax, [rsp+0A8h+arg_48]
0x18003fb13  mov     [rsp+0A8h+var_48], rdi
0x18003fb18  mov     [rsp+0A8h+var_50], ecx
0x18003fb1c  mov     rcx, r11
0x18003fb1f  mov     [rsp+0A8h+var_58], eax
0x18003fb23  mov     rax, r10
0x18003fb26  mov     [rsp+0A8h+var_60], rdx
0x18003fb2b  mov     dl, [rsp+0A8h+arg_38]
0x18003fb32  mov     [rsp+0A8h+var_68], dl
0x18003fb36  mov     rdx, [rsp+0A8h+arg_30]
0x18003fb3e  mov     [rsp+0A8h+var_70], rdx
0x18003fb43  mov     rdx, [rsp+0A8h+arg_28]
0x18003fb4b  mov     [rsp+0A8h+var_78], rdx
0x18003fb50  mov     rdx, [rsp+0A8h+arg_20]
0x18003fb58  mov     [rsp+0A8h+var_80], rdx
0x18003fb5d  mov     edx, r14d
0x18003fb60  mov     [rsp+0A8h+var_88], esi
0x18003fb64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb69  movzx   ebx, ax
0x18003fb6c  test    ebx, ebx
0x18003fb6e  jz      short loc_18003FB76
0x18003fb70  or      ebx, 0C0070000h
0x18003fb76  mov     eax, ebx
0x18003fb78  add     rsp, 80h
0x18003fb7f  pop     r14
0x18003fb81  pop     rdi
0x18003fb82  pop     rsi
0x18003fb83  pop     rbp
0x18003fb84  pop     rbx
0x18003fb85  retn
0x18003fb86  mov     rcx, gs:60h
0x18003fb8f  xor     edx, edx; Flags
0x18003fb91  mov     rcx, [rcx+30h]; HeapHandle
0x18003fb95  lea     r8d, [rdx+28h]; Size
0x18003fb99  call    cs:__imp_RtlAllocateHeap
0x18003fb9f  mov     rdi, rax
0x18003fba2  test    rax, rax
0x18003fba5  jz      short loc_18003FC04
0x18003fba7  mov     rax, [rsp+0A8h+arg_20]
0x18003fbaf  mov     rcx, rbx; Sid
0x18003fbb2  movups  xmm0, xmmword ptr [rax]
0x18003fbb5  movdqu  xmmword ptr [rdi], xmm0
0x18003fbb9  call    cs:__imp_RtlValidSid
0x18003fbbf  test    al, al
0x18003fbc1  jnz     short loc_18003FC0B
0x18003fbc3  mov     ebx, 0C0000078h
0x18003fbc8  jmp     short loc_18003FBF2
0x18003fbca  mov     rcx, cs:off_1800C3128
0x18003fbd1  lea     rdx, ?BmpActivationBuffer@@3U_LIST_ENTRY@@A; _LIST_ENTRY BmpActivationBuffer
0x18003fbd8  cmp     [rcx], rdx
0x18003fbdb  jnz     short loc_18003FC50
0x18003fbdd  lea     rax, [rdi+18h]
0x18003fbe1  mov     [rax], rdx
0x18003fbe4  mov     [rax+8], rcx
0x18003fbe8  mov     [rcx], rax
0x18003fbeb  mov     cs:off_1800C3128, rax
0x18003fbf2  lea     rcx, ?BmpActivationBufferLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK BmpActivationBufferLock
0x18003fbf9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003fbff  jmp     loc_18003FB76
0x18003fc04  mov     ebx, 0C0000017h
0x18003fc09  jmp     short loc_18003FBF2
0x18003fc0b  mov     rcx, rbx; Sid
0x18003fc0e  call    cs:__imp_RtlLengthSid
0x18003fc14  mov     rcx, gs:60h
0x18003fc1d  xor     edx, edx; Flags
0x18003fc1f  mov     r8d, eax; Size
0x18003fc22  mov     esi, eax
0x18003fc24  mov     rcx, [rcx+30h]; HeapHandle
0x18003fc28  call    cs:__imp_RtlAllocateHeap
0x18003fc2e  mov     [rdi+10h], rax
0x18003fc32  test    rax, rax
0x18003fc35  jz      short loc_18003FC04
0x18003fc37  mov     r8, rbx; SourceSid
0x18003fc3a  mov     rdx, rax; DestinationSid
0x18003fc3d  mov     ecx, esi; DestinationSidLength
0x18003fc3f  call    cs:__imp_RtlCopySid
0x18003fc45  mov     ebx, eax
0x18003fc47  test    eax, eax
0x18003fc49  js      short loc_18003FBF2
0x18003fc4b  jmp     loc_18003FBCA
0x18003fc50  mov     ecx, 3
0x18003fc55  int     29h; Win8: RtlFailFast(ecx)
```
