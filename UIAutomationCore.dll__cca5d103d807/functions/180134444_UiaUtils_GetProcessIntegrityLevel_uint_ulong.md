# UiaUtils::GetProcessIntegrityLevel(uint,ulong *)

- ea: `0x180134444`
- end: `0x180134599`
- name: `?GetProcessIntegrityLevel@UiaUtils@@SAJIPEAK@Z`
- size: `341`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003871c`

## callees

- `0x18002f580`
- `0x1800946c0`
- `0x1800948b8`
- `0x180134444`
- `0x1801e8344`
- `0x1801e88a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801344cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013456c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801344cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013456c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18013451b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18013451b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180134529`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180134529`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801344c3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18013450e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801344c3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18013450e`

## string_xrefs

- `0x180134547`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`

## pseudocode

```c
__int64 __fastcall UiaUtils::GetProcessIntegrityLevel(unsigned int a1, unsigned int *a2)
{
  HANDLE v3; // rbx
  signed int LastError; // eax
  unsigned int v5; // ebx
  signed int v7; // eax
  PSID *v8; // rdi
  PUCHAR SidSubAuthorityCount; // rax
  PSID *v10; // rcx
  signed int v11; // eax
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF
  HANDLE v15; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  v15 = OpenProcessTokenHelper(a1, (int)a2, a1);
  v3 = v15;
  if ( !v15 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_4;
  }
  TokenInformationLength = 0;
  if ( GetTokenInformation(v15, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
  {
LABEL_10:
    v5 = 0;
    goto LABEL_4;
  }
  v7 = GetLastError();
  if ( v7 == 122 )
  {
    v8 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
    if ( v8 )
    {
      if ( GetTokenInformation(v3, TokenIntegrityLevel, v8, TokenInformationLength, &TokenInformationLength) )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(*v8);
        *a2 = *GetSidSubAuthority(*v8, (unsigned int)*SidSubAuthorityCount - 1);
        operator delete(v8);
        goto LABEL_10;
      }
      v11 = GetLastError();
      v5 = v11;
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      v10 = v8;
    }
    else
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x668,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
        (const char *)0x8007000ELL,
        ReturnLength);
      v10 = 0;
    }
    operator delete(v10);
    goto LABEL_4;
  }
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  v5 = v7;
LABEL_4:
  AutoCleanupInfo<void *>::SafeRelease(&v15);
  return v5;
}

```

## disassembly

```asm
0x180134444  mov     [rsp+arg_0], rbx
0x180134449  mov     [rsp+arg_18], rsi
0x18013444e  push    rdi
0x18013444f  sub     rsp, 30h
0x180134453  mov     r8d, ecx; unsigned int
0x180134456  mov     dword ptr [rdx], 0
0x18013445c  mov     rsi, rdx
0x18013445f  call    ?OpenProcessTokenHelper@@YAPEAXKHK@Z; OpenProcessTokenHelper(ulong,int,ulong)
0x180134464  mov     [rsp+38h+arg_10], rax
0x180134469  mov     rbx, rax
0x18013446c  test    rax, rax
0x18013446f  jnz     short loc_1801344A4
0x180134471  call    cs:__imp_GetLastError
0x180134477  mov     ebx, eax
0x180134479  test    eax, eax
0x18013447b  jg      short loc_180134499
0x18013447d  lea     rcx, [rsp+38h+arg_10]
0x180134482  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x180134487  mov     rsi, [rsp+38h+arg_18]
0x18013448c  mov     eax, ebx
0x18013448e  mov     rbx, [rsp+38h+arg_0]
0x180134493  add     rsp, 30h
0x180134497  pop     rdi
0x180134498  retn
0x180134499  movzx   ebx, ax
0x18013449c  or      ebx, 80070000h
0x1801344a2  jmp     short loc_18013447D
0x1801344a4  xor     r9d, r9d; TokenInformationLength
0x1801344a7  mov     [rsp+38h+TokenInformationLength], 0
0x1801344af  lea     rax, [rsp+38h+TokenInformationLength]
0x1801344b4  xor     r8d, r8d; TokenInformation
0x1801344b7  mov     rcx, rbx; TokenHandle
0x1801344ba  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1801344bf  lea     edx, [r9+19h]; TokenInformationClass
0x1801344c3  call    cs:__imp_GetTokenInformation
0x1801344c9  test    eax, eax
0x1801344cb  jnz     short loc_18013453B
0x1801344cd  call    cs:__imp_GetLastError
0x1801344d3  cmp     eax, 7Ah ; 'z'
0x1801344d6  jnz     loc_180134586
0x1801344dc  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1801344e0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801344e7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801344ec  mov     rdi, rax
0x1801344ef  test    rax, rax
0x1801344f2  jz      short loc_180134542
0x1801344f4  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1801344f9  lea     rax, [rsp+38h+TokenInformationLength]
0x1801344fe  mov     r8, rdi; TokenInformation
0x180134501  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180134506  mov     edx, 19h; TokenInformationClass
0x18013450b  mov     rcx, rbx; TokenHandle
0x18013450e  call    cs:__imp_GetTokenInformation
0x180134514  test    eax, eax
0x180134516  jz      short loc_18013456C
0x180134518  mov     rcx, [rdi]; pSid
0x18013451b  call    cs:__imp_GetSidSubAuthorityCount
0x180134521  mov     rcx, [rdi]; pSid
0x180134524  movzx   edx, byte ptr [rax]
0x180134527  dec     edx; nSubAuthority
0x180134529  call    cs:__imp_GetSidSubAuthority
0x18013452f  mov     ecx, [rax]
0x180134531  mov     [rsi], ecx
0x180134533  mov     rcx, rdi; Block
0x180134536  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18013453b  xor     ebx, ebx
0x18013453d  jmp     loc_18013447D
0x180134542  mov     rcx, [rsp+38h]; this
0x180134547  lea     r8, aOnecoreWindows_110; "onecore\\windows\\accessibletech\\uiaut"...
0x18013454e  mov     ebx, 8007000Eh
0x180134553  mov     edx, 668h; void *
0x180134558  mov     r9d, ebx; char *
0x18013455b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180134560  xor     ecx, ecx; Block
0x180134562  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180134567  jmp     loc_18013447D
0x18013456c  call    cs:__imp_GetLastError
0x180134572  mov     ebx, eax
0x180134574  test    eax, eax
0x180134576  jle     short loc_180134581
0x180134578  movzx   ebx, ax
0x18013457b  or      ebx, 80070000h
0x180134581  mov     rcx, rdi
0x180134584  jmp     short loc_180134562
0x180134586  test    eax, eax
0x180134588  jle     short loc_180134592
0x18013458a  movzx   eax, ax
0x18013458d  or      eax, 80070000h
0x180134592  mov     ebx, eax
0x180134594  jmp     loc_18013447D
```
