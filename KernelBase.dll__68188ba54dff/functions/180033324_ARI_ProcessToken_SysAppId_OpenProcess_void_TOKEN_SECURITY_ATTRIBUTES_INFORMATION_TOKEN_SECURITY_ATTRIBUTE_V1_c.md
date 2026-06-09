# ARI::ProcessToken::SysAppId::OpenProcess(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180033324`
- end: `0x180033571`
- name: `?OpenProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `589`
- prototype: `__int64 __fastcall(ARI::ProcessToken::SysAppId *__hidden this, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800281f0`
- `0x180031bb0`

## callees

- `0x1800134a0`
- `0x180033324`
- `0x180033d08`
- `0x180048f30`
- `0x18012d119`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180033480`
- `ntdll!RtlInitUnicodeString` at `0x18003349d`
- `ntdll!RtlInitUnicodeString` at `0x180033480`
- `ntdll!RtlInitUnicodeString` at `0x18003349d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003354a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018d79a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003354a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018d79a`
- `ntdll!NtQueryInformationToken` at `0x1800333ae`
- `ntdll!NtQueryInformationToken` at `0x18003344c`
- `ntdll!NtQueryInformationToken` at `0x1800333ae`
- `ntdll!NtQueryInformationToken` at `0x18003344c`
- `ntdll!RtlCompareUnicodeString` at `0x1800334c5`
- `ntdll!RtlCompareUnicodeString` at `0x1800334de`
- `ntdll!RtlCompareUnicodeString` at `0x1800334c5`
- `ntdll!RtlCompareUnicodeString` at `0x1800334de`
- `ntdll!NtOpenProcessToken` at `0x180033365`
- `ntdll!NtOpenProcessToken` at `0x180033365`
- `ntdll!RtlAllocateHeap` at `0x18003341a`
- `ntdll!RtlAllocateHeap` at `0x18003341a`

## pseudocode

```c
__int64 __fastcall ARI::ProcessToken::SysAppId::OpenProcess(
        ARI::ProcessToken::SysAppId *this,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v6; // eax
  ULONG LastErrorValue; // ebx
  __int64 v8; // rbx
  NTSTATUS v9; // eax
  PVOID Heap; // rax
  PVOID v12; // rdi
  int v13; // eax
  char v14; // r12
  bool v15; // r15
  __int64 i; // rbx
  __int64 v17; // rax
  const UNICODE_STRING *v18; // r14
  HANDLE TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-28h] BYREF
  UNICODE_STRING String1; // [rsp+48h] [rbp-18h] BYREF
  ULONG TokenInformationLength; // [rsp+A0h] [rbp+40h] BYREF
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **v23; // [rsp+B0h] [rbp+50h]

  v23 = a3;
  TokenHandle = 0;
  if ( this == (ARI::ProcessToken::SysAppId *)-1LL )
  {
    v8 = -4;
    TokenHandle = (HANDLE)-4LL;
  }
  else
  {
    v6 = NtOpenProcessToken(this, 8u, &TokenHandle);
    if ( v6 < 0 )
    {
      BaseSetLastNTError((unsigned int)v6);
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
      if ( LastErrorValue )
        return LastErrorValue;
    }
    v8 = (__int64)TokenHandle;
  }
  if ( a4 )
    *(_BYTE *)a4 = 0;
  TokenInformationLength = 0;
  v9 = NtQueryInformationToken((HANDLE)v8, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v9 == -1073741789 )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    if ( is_mul_ok(TokenInformationLength, 0x10u)
      && (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * TokenInformationLength), (v12 = Heap) != 0) )
    {
      memset_0(Heap, 0, TokenInformationLength);
      v13 = NtQueryInformationToken(
              (HANDLE)v8,
              TokenSecurityAttributes,
              v12,
              TokenInformationLength,
              &TokenInformationLength);
      if ( v13 < 0 )
      {
        LastErrorValue = RtlNtStatusToDosErrorNoTeb(v13);
        AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v12);
      }
      else
      {
        if ( *((_DWORD *)v12 + 1) )
        {
          v14 = 1;
          v15 = a4 != 0;
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          String1 = 0;
          if ( a4 )
            RtlInitUnicodeString(&String1, L"WIN://PKG");
          for ( i = 0; (unsigned int)i < *((_DWORD *)v12 + 1); i = (unsigned int)(i + 1) )
          {
            v17 = *((_QWORD *)v12 + 1);
            v18 = (const UNICODE_STRING *)(v17 + 40 * i);
            if ( v14 && !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v17 + 40 * i), 1u) )
            {
              *v23 = (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)v18;
              if ( !v15 )
                goto LABEL_29;
              v14 = 0;
            }
            else if ( v15 && !RtlCompareUnicodeString(&String1, v18, 1u) )
            {
              *(_BYTE *)a4 = 1;
              if ( !v14 )
              {
LABEL_29:
                *a2 = v12;
                AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
                LastErrorValue = 0;
                goto LABEL_10;
              }
              v15 = 0;
            }
          }
        }
        AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v12);
        LastErrorValue = 1168;
      }
    }
    else
    {
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
      LastErrorValue = 8;
    }
  }
  else if ( v9 )
  {
    LastErrorValue = RtlNtStatusToDosErrorNoTeb(v9);
  }
  else
  {
    LastErrorValue = 1359;
  }
LABEL_10:
  if ( TokenHandle != (HANDLE)-4LL )
    CloseHandle(TokenHandle);
  return LastErrorValue;
}

```

## disassembly

```asm
0x180033324  mov     [rsp-38h+arg_8], rbx
0x180033329  mov     [rsp-38h+arg_10], r8
0x18003332e  push    rbp
0x18003332f  push    rsi
0x180033330  push    rdi
0x180033331  push    r12
0x180033333  push    r13
0x180033335  push    r14
0x180033337  push    r15
0x180033339  mov     rbp, rsp
0x18003333c  sub     rsp, 60h
0x180033340  mov     [rbp+TokenHandle], 0
0x180033348  mov     rsi, r9
0x18003334b  mov     r13, rdx
0x18003334e  mov     r14d, 8
0x180033354  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180033358  jz      loc_180033533
0x18003335e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180033362  mov     edx, r14d; DesiredAccess
0x180033365  call    cs:__imp_NtOpenProcessToken
0x18003336b  test    eax, eax
0x18003336d  jns     short loc_180033382
0x18003336f  mov     ecx, eax
0x180033371  call    BaseSetLastNTError
0x180033376  mov     ebx, gs:68h
0x18003337e  test    ebx, ebx
0x180033380  jnz     short loc_1800333EE
0x180033382  mov     rbx, [rbp+TokenHandle]
0x180033386  test    rsi, rsi
0x180033389  jz      short loc_18003338E
0x18003338b  mov     byte ptr [rsi], 0
0x18003338e  xor     r9d, r9d; TokenInformationLength
0x180033391  mov     [rbp+TokenInformationLength], 0
0x180033398  lea     rax, [rbp+TokenInformationLength]
0x18003339c  xor     r8d, r8d; TokenInformation
0x18003339f  mov     rcx, rbx; TokenHandle
0x1800333a2  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800333a7  lea     r15d, [r9+27h]
0x1800333ab  mov     edx, r15d; TokenInformationClass
0x1800333ae  call    cs:__imp_NtQueryInformationToken
0x1800333b4  cmp     eax, 0C0000023h
0x1800333b9  jnz     loc_18003355F
0x1800333bf  mov     ecx, [rbp+TokenInformationLength]
0x1800333c2  lea     eax, [r15-17h]
0x1800333c6  mul     rcx
0x1800333c9  mov     qword ptr [rbp+DestinationString.Length], 0
0x1800333d1  test    rdx, rdx
0x1800333d4  jz      short loc_180033408
0x1800333d6  xor     ecx, ecx; P
0x1800333d8  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800333dd  mov     ebx, r14d
0x1800333e0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800333e4  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x1800333e8  jnz     loc_1800334FE
0x1800333ee  mov     eax, ebx
0x1800333f0  mov     rbx, [rsp+60h+arg_8]
0x1800333f8  add     rsp, 60h
0x1800333fc  pop     r15
0x1800333fe  pop     r14
0x180033400  pop     r13
0x180033402  pop     r12
0x180033404  pop     rdi
0x180033405  pop     rsi
0x180033406  pop     rbp
0x180033407  retn
0x180033408  mov     rcx, gs:60h
0x180033411  mov     r8, rax; Size
0x180033414  xor     edx, edx; Flags
0x180033416  mov     rcx, [rcx+30h]; HeapHandle
0x18003341a  call    cs:__imp_RtlAllocateHeap
0x180033420  mov     rdi, rax
0x180033423  test    rax, rax
0x180033426  jz      short loc_1800333D6
0x180033428  mov     r8d, [rbp+TokenInformationLength]; Size
0x18003342c  xor     edx, edx; Val
0x18003342e  mov     rcx, rax; void *
0x180033431  call    memset_0
0x180033436  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003343a  lea     rax, [rbp+TokenInformationLength]
0x18003343e  mov     r8, rdi; TokenInformation
0x180033441  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180033446  mov     edx, r15d; TokenInformationClass
0x180033449  mov     rcx, rbx; TokenHandle
0x18003344c  call    cs:__imp_NtQueryInformationToken
0x180033452  test    eax, eax
0x180033454  js      loc_180033548
0x18003345a  cmp     dword ptr [rdi+4], 0
0x18003345e  jbe     loc_1800334EC
0x180033464  xorps   xmm0, xmm0
0x180033467  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x18003346e  test    rsi, rsi
0x180033471  lea     rcx, [rbp+DestinationString]; DestinationString
0x180033475  mov     r12b, 1
0x180033478  setnz   r15b
0x18003347c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180033480  call    cs:__imp_RtlInitUnicodeString
0x180033486  xorps   xmm0, xmm0
0x180033489  movups  xmmword ptr [rbp+String1.Length], xmm0
0x18003348d  test    rsi, rsi
0x180033490  jz      short loc_1800334A3
0x180033492  lea     rdx, aWinPkg; "WIN://PKG"
0x180033499  lea     rcx, [rbp+String1]; DestinationString
0x18003349d  call    cs:__imp_RtlInitUnicodeString
0x1800334a3  xor     ebx, ebx
0x1800334a5  cmp     ebx, [rdi+4]
0x1800334a8  jnb     short loc_1800334EC
0x1800334aa  mov     rax, [rdi+8]
0x1800334ae  lea     rcx, [rbx+rbx*4]
0x1800334b2  lea     r14, [rax+rcx*8]
0x1800334b6  test    r12b, r12b
0x1800334b9  jz      short loc_1800334CF
0x1800334bb  mov     r8b, 1; CaseInsensitive
0x1800334be  lea     rcx, [rbp+DestinationString]; String1
0x1800334c2  mov     rdx, r14; String2
0x1800334c5  call    cs:__imp_RtlCompareUnicodeString
0x1800334cb  test    eax, eax
0x1800334cd  jz      short loc_180033508
0x1800334cf  test    r15b, r15b
0x1800334d2  jz      short loc_1800334E8
0x1800334d4  mov     r8b, 1; CaseInsensitive
0x1800334d7  lea     rcx, [rbp+String1]; String1
0x1800334db  mov     rdx, r14; String2
0x1800334de  call    cs:__imp_RtlCompareUnicodeString
0x1800334e4  test    eax, eax
0x1800334e6  jz      short loc_180033519
0x1800334e8  inc     ebx
0x1800334ea  jmp     short loc_1800334A5
0x1800334ec  mov     rcx, rdi; P
0x1800334ef  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800334f4  mov     ebx, 490h
0x1800334f9  jmp     loc_1800333E0
0x1800334fe  call    CloseHandle
0x180033503  jmp     loc_1800333EE
0x180033508  mov     rax, [rbp+arg_10]
0x18003350c  mov     [rax], r14
0x18003350f  test    r15b, r15b
0x180033512  jz      short loc_180033521
0x180033514  xor     r12b, r12b
0x180033517  jmp     short loc_1800334E8
0x180033519  mov     byte ptr [rsi], 1
0x18003351c  test    r12b, r12b
0x18003351f  jnz     short loc_180033543
0x180033521  xor     ecx, ecx; P
0x180033523  mov     [r13+0], rdi
0x180033527  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18003352c  xor     ebx, ebx
0x18003352e  jmp     loc_1800333E0
0x180033533  mov     rbx, 0FFFFFFFFFFFFFFFCh
0x18003353a  mov     [rbp+TokenHandle], rbx
0x18003353e  jmp     loc_180033386
0x180033543  xor     r15b, r15b
0x180033546  jmp     short loc_1800334E8
0x180033548  mov     ecx, eax; Status
0x18003354a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180033550  mov     rcx, rdi; P
0x180033553  mov     ebx, eax
0x180033555  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18003355a  jmp     loc_1800333E0
0x18003355f  test    eax, eax
0x180033561  jnz     loc_18018D798
0x180033567  mov     ebx, 54Fh
0x18003356c  jmp     loc_1800333E0
0x18018d798  mov     ecx, eax; Status
0x18018d79a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18018d7a0  mov     ebx, eax
0x18018d7a2  jmp     loc_1800333E0
```
