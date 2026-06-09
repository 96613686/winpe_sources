# ARI::ProcessToken::AutoSysAppId::OpenIfPackaged(void *)

- ea: `0x180033ae0`
- end: `0x180033d01`
- name: `?OpenIfPackaged@AutoSysAppId@ProcessToken@ARI@@QEAAJPEAX@Z`
- size: `545`
- prototype: `__int64 __fastcall(ARI::ProcessToken::AutoSysAppId *__hidden this, HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033d70`
- `0x18004c3e8`

## callees

- `0x180033ae0`
- `0x180033d08`
- `0x180033d34`
- `0x18012d119`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180033be8`
- `ntdll!RtlInitUnicodeString` at `0x180033c00`
- `ntdll!RtlInitUnicodeString` at `0x180033be8`
- `ntdll!RtlInitUnicodeString` at `0x180033c00`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180033cd5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018d7ca`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180033cd5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018d7ca`
- `ntdll!NtQueryInformationToken` at `0x180033b29`
- `ntdll!NtQueryInformationToken` at `0x180033bbb`
- `ntdll!NtQueryInformationToken` at `0x180033b29`
- `ntdll!NtQueryInformationToken` at `0x180033bbb`
- `ntdll!RtlCompareUnicodeString` at `0x180033c2e`
- `ntdll!RtlCompareUnicodeString` at `0x180033c47`
- `ntdll!RtlCompareUnicodeString` at `0x180033c2e`
- `ntdll!RtlCompareUnicodeString` at `0x180033c47`
- `ntdll!RtlAllocateHeap` at `0x180033b89`
- `ntdll!RtlAllocateHeap` at `0x180033b89`

## pseudocode

```c
__int64 __fastcall ARI::ProcessToken::AutoSysAppId::OpenIfPackaged(
        ARI::ProcessToken::AutoSysAppId *this,
        HANDLE TokenHandle)
{
  void *v4; // rcx
  NTSTATUS v5; // eax
  ULONG v6; // edi
  PVOID Heap; // rax
  PVOID v9; // rbx
  int v10; // eax
  char v11; // r13
  __int64 v12; // rdi
  char v13; // r12
  char v14; // r14
  __int64 v15; // rax
  const UNICODE_STRING *v16; // r15
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-10h] BYREF
  ULONG TokenInformationLength; // [rsp+90h] [rbp+40h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+50h]

  v4 = *(void **)this;
  if ( v4 )
  {
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v4);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
  }
  TokenInformationLength = 0;
  v5 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v5 == -1073741789 )
  {
    v20 = 0;
    if ( !is_mul_ok(TokenInformationLength, 0x10u)
      || (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * TokenInformationLength), (v9 = Heap) == 0) )
    {
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
      return 8;
    }
    memset_0(Heap, 0, TokenInformationLength);
    v10 = NtQueryInformationToken(
            TokenHandle,
            TokenSecurityAttributes,
            v9,
            TokenInformationLength,
            &TokenInformationLength);
    if ( v10 >= 0 )
    {
      if ( *((_DWORD *)v9 + 1) )
      {
        v11 = 1;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
        String1 = 0;
        RtlInitUnicodeString(&String1, L"WIN://PKG");
        v12 = 0;
        v13 = 1;
        v14 = 0;
        while ( (unsigned int)v12 < *((_DWORD *)v9 + 1) )
        {
          v15 = *((_QWORD *)v9 + 1);
          v16 = (const UNICODE_STRING *)(v15 + 40 * v12);
          if ( v11 && !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v15 + 40 * v12), 1u) )
          {
            *((_QWORD *)this + 1) = v16;
            if ( !v13 )
            {
              *(_QWORD *)this = v9;
              AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
              v6 = 0;
              goto LABEL_24;
            }
            v11 = 0;
          }
          else if ( v13 && !RtlCompareUnicodeString(&String1, v16, 1u) )
          {
            if ( !v11 )
            {
              *(_QWORD *)this = v9;
              AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
              return 0;
            }
            v14 = 1;
            v13 = 0;
          }
          v12 = (unsigned int)(v12 + 1);
        }
      }
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v9);
      return 1168;
    }
    v6 = RtlNtStatusToDosErrorNoTeb(v10);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v9);
  }
  else if ( v5 )
  {
    v6 = RtlNtStatusToDosErrorNoTeb(v5);
  }
  else
  {
    v6 = 1359;
  }
  v14 = 0;
  if ( v6 )
    return v6;
LABEL_24:
  if ( v14 )
    return v6;
  ARI::ProcessToken::AutoSysAppId::Close(this);
  return 15700;
}

```

## disassembly

```asm
0x180033ae0  mov     [rsp-38h+arg_8], rbx
0x180033ae5  push    rbp
0x180033ae6  push    rsi
0x180033ae7  push    rdi
0x180033ae8  push    r12
0x180033aea  push    r13
0x180033aec  push    r14
0x180033aee  push    r15
0x180033af0  mov     rbp, rsp
0x180033af3  sub     rsp, 50h
0x180033af7  mov     rsi, rcx
0x180033afa  mov     rdi, rdx
0x180033afd  mov     rcx, [rcx]; P
0x180033b00  test    rcx, rcx
0x180033b03  jnz     loc_180033C8B
0x180033b09  xor     r9d, r9d; TokenInformationLength
0x180033b0c  mov     [rbp+TokenInformationLength], 0
0x180033b13  lea     rax, [rbp+TokenInformationLength]
0x180033b17  xor     r8d, r8d; TokenInformation
0x180033b1a  mov     rcx, rdi; TokenHandle
0x180033b1d  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180033b22  lea     r14d, [r9+27h]
0x180033b26  mov     edx, r14d; TokenInformationClass
0x180033b29  call    cs:__imp_NtQueryInformationToken
0x180033b2f  cmp     eax, 0C0000023h
0x180033b34  jnz     loc_180033CF2
0x180033b3a  mov     ecx, [rbp+TokenInformationLength]
0x180033b3d  lea     eax, [r14-17h]
0x180033b41  mul     rcx
0x180033b44  mov     [rbp+arg_10], 0
0x180033b4c  test    rdx, rdx
0x180033b4f  jz      short loc_180033B77
0x180033b51  xor     ecx, ecx; P
0x180033b53  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033b58  mov     edi, 8
0x180033b5d  mov     eax, edi
0x180033b5f  mov     rbx, [rsp+50h+arg_8]
0x180033b67  add     rsp, 50h
0x180033b6b  pop     r15
0x180033b6d  pop     r14
0x180033b6f  pop     r13
0x180033b71  pop     r12
0x180033b73  pop     rdi
0x180033b74  pop     rsi
0x180033b75  pop     rbp
0x180033b76  retn
0x180033b77  mov     rcx, gs:60h
0x180033b80  mov     r8, rax; Size
0x180033b83  xor     edx, edx; Flags
0x180033b85  mov     rcx, [rcx+30h]; HeapHandle
0x180033b89  call    cs:__imp_RtlAllocateHeap
0x180033b8f  mov     rbx, rax
0x180033b92  test    rax, rax
0x180033b95  jz      short loc_180033B51
0x180033b97  mov     r8d, [rbp+TokenInformationLength]; Size
0x180033b9b  xor     edx, edx; Val
0x180033b9d  mov     rcx, rax; void *
0x180033ba0  call    memset_0
0x180033ba5  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180033ba9  lea     rax, [rbp+TokenInformationLength]
0x180033bad  mov     r8, rbx; TokenInformation
0x180033bb0  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180033bb5  mov     edx, r14d; TokenInformationClass
0x180033bb8  mov     rcx, rdi; TokenHandle
0x180033bbb  call    cs:__imp_NtQueryInformationToken
0x180033bc1  test    eax, eax
0x180033bc3  js      loc_180033CD3
0x180033bc9  cmp     dword ptr [rbx+4], 0
0x180033bcd  jbe     loc_180033C55
0x180033bd3  xorps   xmm0, xmm0
0x180033bd6  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x180033bdd  lea     rcx, [rbp+DestinationString]; DestinationString
0x180033be1  mov     r13b, 1
0x180033be4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180033be8  call    cs:__imp_RtlInitUnicodeString
0x180033bee  xorps   xmm0, xmm0
0x180033bf1  lea     rdx, aWinPkg; "WIN://PKG"
0x180033bf8  lea     rcx, [rbp+String1]; DestinationString
0x180033bfc  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180033c00  call    cs:__imp_RtlInitUnicodeString
0x180033c06  xor     edi, edi
0x180033c08  mov     r12b, r13b
0x180033c0b  xor     r14b, r14b
0x180033c0e  cmp     edi, [rbx+4]
0x180033c11  jnb     short loc_180033C55
0x180033c13  mov     rax, [rbx+8]
0x180033c17  lea     rcx, [rdi+rdi*4]
0x180033c1b  lea     r15, [rax+rcx*8]
0x180033c1f  test    r13b, r13b
0x180033c22  jz      short loc_180033C38
0x180033c24  mov     r8b, 1; CaseInsensitive
0x180033c27  lea     rcx, [rbp+DestinationString]; String1
0x180033c2b  mov     rdx, r15; String2
0x180033c2e  call    cs:__imp_RtlCompareUnicodeString
0x180033c34  test    eax, eax
0x180033c36  jz      short loc_180033C67
0x180033c38  test    r12b, r12b
0x180033c3b  jz      short loc_180033C51
0x180033c3d  mov     r8b, 1; CaseInsensitive
0x180033c40  lea     rcx, [rbp+String1]; String1
0x180033c44  mov     rdx, r15; String2
0x180033c47  call    cs:__imp_RtlCompareUnicodeString
0x180033c4d  test    eax, eax
0x180033c4f  jz      short loc_180033C75
0x180033c51  inc     edi
0x180033c53  jmp     short loc_180033C0E
0x180033c55  mov     rcx, rbx; P
0x180033c58  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033c5d  mov     edi, 490h
0x180033c62  jmp     loc_180033B5D
0x180033c67  mov     [rsi+8], r15
0x180033c6b  test    r12b, r12b
0x180033c6e  jz      short loc_180033CAC
0x180033c70  xor     r13b, r13b
0x180033c73  jmp     short loc_180033C51
0x180033c75  test    r13b, r13b
0x180033c78  jnz     short loc_180033CA4
0x180033c7a  xor     ecx, ecx; P
0x180033c7c  mov     [rsi], rbx
0x180033c7f  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033c84  xor     edi, edi
0x180033c86  jmp     loc_180033B5D
0x180033c8b  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033c90  mov     qword ptr [rsi], 0
0x180033c97  mov     qword ptr [rsi+8], 0
0x180033c9f  jmp     loc_180033B09
0x180033ca4  mov     r14b, 1
0x180033ca7  xor     r12b, r12b
0x180033caa  jmp     short loc_180033C51
0x180033cac  xor     ecx, ecx; P
0x180033cae  mov     [rsi], rbx
0x180033cb1  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033cb6  xor     edi, edi
0x180033cb8  test    r14b, r14b
0x180033cbb  jnz     loc_180033B5D
0x180033cc1  mov     rcx, rsi; this
0x180033cc4  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x180033cc9  mov     eax, 3D54h
0x180033cce  jmp     loc_180033B5F
0x180033cd3  mov     ecx, eax; Status
0x180033cd5  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180033cdb  mov     rcx, rbx; P
0x180033cde  mov     edi, eax
0x180033ce0  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033ce5  xor     r14b, r14b
0x180033ce8  test    edi, edi
0x180033cea  jnz     loc_180033B5D
0x180033cf0  jmp     short loc_180033CB8
0x180033cf2  test    eax, eax
0x180033cf4  jnz     loc_18018D7C8
0x180033cfa  mov     edi, 54Fh
0x180033cff  jmp     short loc_180033CE5
0x18018d7c8  mov     ecx, eax; Status
0x18018d7ca  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18018d7d0  mov     edi, eax
0x18018d7d2  jmp     loc_180033CE5
```
