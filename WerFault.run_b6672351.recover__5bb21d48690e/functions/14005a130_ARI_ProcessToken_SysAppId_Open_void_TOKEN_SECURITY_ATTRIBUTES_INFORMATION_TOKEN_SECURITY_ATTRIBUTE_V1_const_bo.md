# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x14005a130`
- end: `0x14005a2f6`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `454`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140059cd4`

## callees

- `0x1400030f8`
- `0x140059668`
- `0x14005a130`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14005a1d5`
- `ntdll!RtlAllocateHeap` at `0x14005a1d5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14005a193`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14005a22e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14005a193`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14005a22e`
- `ntdll!RtlCompareUnicodeString` at `0x14005a299`
- `ntdll!RtlCompareUnicodeString` at `0x14005a299`
- `ntdll!NtQueryInformationToken` at `0x14005a170`
- `ntdll!NtQueryInformationToken` at `0x14005a21c`
- `ntdll!NtQueryInformationToken` at `0x14005a170`
- `ntdll!NtQueryInformationToken` at `0x14005a21c`
- `ntdll!RtlInitUnicodeString` at `0x14005a268`
- `ntdll!RtlInitUnicodeString` at `0x14005a268`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        const UNICODE_STRING **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  PVOID Heap; // rax
  _DWORD *v10; // rdi
  int v11; // eax
  ULONG v12; // ebx
  _DWORD *v13; // rsi
  __int64 v14; // rbx
  const UNICODE_STRING *v15; // rbp
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  __int128 v17; // [rsp+40h] [rbp-38h]
  ULONG Size; // [rsp+98h] [rbp+20h] BYREF
  int Size_4; // [rsp+9Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    if ( is_mul_ok(Size, 0x10u)
      && (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, (Size * (unsigned __int128)0x10uLL) >> 64, 16LL * Size),
          (v10 = Heap) != 0) )
    {
      memset_0(Heap, 0, Size);
      v11 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v10, Size, &Size);
      if ( v11 >= 0 )
      {
        v13 = v10 + 1;
        if ( v10[1]
          && (DestinationString = 0, RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID"), v14 = 0, v17 = 0, *v13) )
        {
          while ( 1 )
          {
            v15 = (const UNICODE_STRING *)(*((_QWORD *)v10 + 1) + 40 * v14);
            if ( !RtlCompareUnicodeString(&DestinationString, v15, 1u) )
              break;
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= *v13 )
              goto LABEL_13;
          }
          *a3 = v15;
          *a2 = v10;
          ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(0);
          return 0;
        }
        else
        {
LABEL_13:
          ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
          return 1168;
        }
      }
      else
      {
        v12 = RtlNtStatusToDosErrorNoTeb(v11);
        ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
        return v12;
      }
    }
    else
    {
      ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(0);
      return 8;
    }
  }
  else if ( v7 )
  {
    return RtlNtStatusToDosErrorNoTeb(v7);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x14005a130  mov     rax, rsp
0x14005a133  mov     [rax+8], rbx
0x14005a137  mov     [rax+10h], rbp
0x14005a13b  mov     [rax+20h], r9
0x14005a13f  push    rsi
0x14005a140  push    rdi
0x14005a141  push    r12
0x14005a143  push    r14
0x14005a145  push    r15
0x14005a147  sub     rsp, 50h
0x14005a14b  xor     r9d, r9d; TokenInformationLength
0x14005a14e  mov     dword ptr [rax+20h], 0
0x14005a155  mov     r15, r8
0x14005a158  lea     rax, [rax+20h]
0x14005a15c  mov     r12, rdx
0x14005a15f  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x14005a164  xor     r8d, r8d; TokenInformation
0x14005a167  mov     rbx, rcx
0x14005a16a  lea     esi, [r9+27h]
0x14005a16e  mov     edx, esi; TokenInformationClass
0x14005a170  call    cs:__imp_NtQueryInformationToken
0x14005a177  nop     dword ptr [rax+rax+00h]
0x14005a17c  cmp     eax, 0C0000023h
0x14005a181  jz      short loc_14005A1A4
0x14005a183  test    eax, eax
0x14005a185  jnz     short loc_14005A191
0x14005a187  mov     eax, 54Fh
0x14005a18c  jmp     loc_14005A2DC
0x14005a191  mov     ecx, eax; Status
0x14005a193  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14005a19a  nop     dword ptr [rax+rax+00h]
0x14005a19f  jmp     loc_14005A2DC
0x14005a1a4  mov     ecx, dword ptr [rsp+78h+Size]
0x14005a1ab  mov     eax, 10h
0x14005a1b0  mul     rcx
0x14005a1b3  mov     qword ptr [rsp+78h+DestinationString.Length], 0
0x14005a1bc  test    rdx, rdx
0x14005a1bf  jnz     loc_14005A2D0
0x14005a1c5  mov     rcx, gs:60h
0x14005a1ce  mov     r8, rax; Size
0x14005a1d1  mov     rcx, [rcx+30h]; HeapHandle
0x14005a1d5  call    cs:__imp_RtlAllocateHeap
0x14005a1dc  nop     dword ptr [rax+rax+00h]
0x14005a1e1  mov     rdi, rax
0x14005a1e4  test    rax, rax
0x14005a1e7  jz      loc_14005A2D0
0x14005a1ed  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x14005a1f5  xor     edx, edx; Val
0x14005a1f7  mov     rcx, rax; void *
0x14005a1fa  call    memset_0
0x14005a1ff  mov     r9d, dword ptr [rsp+78h+Size]; TokenInformationLength
0x14005a207  lea     rax, [rsp+78h+Size]
0x14005a20f  mov     r8, rdi; TokenInformation
0x14005a212  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x14005a217  mov     edx, esi; TokenInformationClass
0x14005a219  mov     rcx, rbx; TokenHandle
0x14005a21c  call    cs:__imp_NtQueryInformationToken
0x14005a223  nop     dword ptr [rax+rax+00h]
0x14005a228  test    eax, eax
0x14005a22a  jns     short loc_14005A24B
0x14005a22c  mov     ecx, eax; Status
0x14005a22e  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14005a235  nop     dword ptr [rax+rax+00h]
0x14005a23a  mov     rcx, rdi; P
0x14005a23d  mov     ebx, eax
0x14005a23f  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x14005a244  mov     eax, ebx
0x14005a246  jmp     loc_14005A2DC
0x14005a24b  lea     rsi, [rdi+4]
0x14005a24f  cmp     dword ptr [rsi], 0
0x14005a252  jbe     short loc_14005A2AF
0x14005a254  xorps   xmm0, xmm0
0x14005a257  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x14005a25e  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14005a263  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x14005a268  call    cs:__imp_RtlInitUnicodeString
0x14005a26f  nop     dword ptr [rax+rax+00h]
0x14005a274  xor     ebx, ebx
0x14005a276  xorps   xmm0, xmm0
0x14005a279  movups  [rsp+78h+var_38], xmm0
0x14005a27e  cmp     [rsi], ebx
0x14005a280  jbe     short loc_14005A2AF
0x14005a282  mov     rax, [rdi+8]
0x14005a286  lea     rcx, [rbx+rbx*4]
0x14005a28a  mov     r8b, 1; CaseInsensitive
0x14005a28d  lea     rbp, [rax+rcx*8]
0x14005a291  mov     rdx, rbp; String2
0x14005a294  lea     rcx, [rsp+78h+DestinationString]; String1
0x14005a299  call    cs:__imp_RtlCompareUnicodeString
0x14005a2a0  nop     dword ptr [rax+rax+00h]
0x14005a2a5  test    eax, eax
0x14005a2a7  jz      short loc_14005A2BE
0x14005a2a9  inc     ebx
0x14005a2ab  cmp     ebx, [rsi]
0x14005a2ad  jb      short loc_14005A282
0x14005a2af  mov     rcx, rdi; P
0x14005a2b2  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x14005a2b7  mov     eax, 490h
0x14005a2bc  jmp     short loc_14005A2DC
0x14005a2be  mov     [r15], rbp
0x14005a2c1  xor     ecx, ecx; P
0x14005a2c3  mov     [r12], rdi
0x14005a2c7  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x14005a2cc  xor     eax, eax
0x14005a2ce  jmp     short loc_14005A2DC
0x14005a2d0  xor     ecx, ecx; P
0x14005a2d2  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x14005a2d7  mov     eax, 8
0x14005a2dc  lea     r11, [rsp+78h+var_28]
0x14005a2e1  mov     rbx, [r11+30h]
0x14005a2e5  mov     rbp, [r11+38h]
0x14005a2e9  mov     rsp, r11
0x14005a2ec  pop     r15
0x14005a2ee  pop     r14
0x14005a2f0  pop     r12
0x14005a2f2  pop     rdi
0x14005a2f3  pop     rsi
0x14005a2f4  retn
```
