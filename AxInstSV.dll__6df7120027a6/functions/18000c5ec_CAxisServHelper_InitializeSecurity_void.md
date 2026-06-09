# CAxisServHelper::InitializeSecurity(void)

- ea: `0x18000c5ec`
- end: `0x18000c7c8`
- name: `?InitializeSecurity@CAxisServHelper@@QEAAJXZ`
- size: `476`
- prototype: `__int64 __fastcall(CAxisServHelper *this, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bf6c`

## callees

- `0x180001720`
- `0x180008930`
- `0x180009c88`
- `0x18000c4a8`
- `0x18000c5ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18000c785`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18000c785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c648`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000c735`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000c735`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000c796`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000c796`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000c673`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000c6a8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000c6dd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000c673`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000c6a8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000c6dd`

## pseudocode

```c
__int64 __fastcall CAxisServHelper::InitializeSecurity(CAxisServHelper *this, int a2, int a3)
{
  signed int LastError; // eax
  int v4; // ebx
  unsigned int v5; // r8d
  unsigned int v6; // r8d
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  DWORD cbSid; // [rsp+60h] [rbp-49h] BYREF
  PSID v11; // [rsp+68h] [rbp-41h] BYREF
  PSECURITY_DESCRIPTOR pSecDesc[2]; // [rsp+70h] [rbp-39h] BYREF
  __int128 v13; // [rsp+80h] [rbp-29h]
  __int64 v14; // [rsp+90h] [rbp-19h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp-11h] BYREF
  _BYTE pSid[80]; // [rsp+A0h] [rbp-9h] BYREF

  *(_OWORD *)pSecDesc = 0;
  v13 = 0;
  v14 = 0;
  cbSid = 68;
  v11 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  if ( (int)ATL::CSecurityDescriptor::InitializeFromThreadToken((ATL::CSecurityDescriptor *)pSecDesc, a2, a3) < 0
    || !CreateWellKnownSid(WinAuthenticatedUserSid, 0, pSid, &cbSid) )
  {
    goto LABEL_2;
  }
  v4 = ATL::CSecurityDescriptor::Allow((ATL::CSecurityDescriptor *)pSecDesc, pSid, v5);
  if ( v4 < 0 )
    goto LABEL_13;
  cbSid = 68;
  if ( !CreateWellKnownSid(WinWorldSid, 0, pSid, &cbSid) )
    goto LABEL_2;
  v4 = ATL::CSecurityDescriptor::Allow((ATL::CSecurityDescriptor *)pSecDesc, pSid, v6);
  if ( v4 < 0 )
    goto LABEL_13;
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinGuestsSid, 0, pSid, &cbSid) )
    goto LABEL_2;
  v4 = ATL::CSecurityDescriptor::Allow((ATL::CSecurityDescriptor *)pSecDesc, pSid, v7);
  if ( v4 < 0 )
    goto LABEL_13;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 3u, 0x1000u, 0, 0, 0, 0, 0, 0, &v11) )
  {
    v4 = ATL::CSecurityDescriptor::Allow((ATL::CSecurityDescriptor *)pSecDesc, v11, v8);
    if ( v4 >= 0 )
      v4 = CoInitializeSecurity(pSecDesc[0], -1, 0, 0, 2u, 3u, 0, 0x2000u, 0);
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_13:
  if ( v11 )
    FreeSid(v11);
  ATL::CSecurityDescriptor::~CSecurityDescriptor((ATL::CSecurityDescriptor *)pSecDesc);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c5ec  mov     [rsp-8+arg_0], rbx
0x18000c5f1  mov     [rsp-8+arg_8], rdi
0x18000c5f6  push    rbp
0x18000c5f7  lea     rbp, [rsp-57h]
0x18000c5fc  sub     rsp, 100h
0x18000c603  mov     rax, cs:__security_cookie
0x18000c60a  xor     rax, rsp
0x18000c60d  mov     [rbp+57h+var_10], rax
0x18000c611  xorps   xmm0, xmm0
0x18000c614  movdqu  xmmword ptr [rbp+57h+pSecDesc], xmm0
0x18000c619  xorps   xmm1, xmm1
0x18000c61c  movdqu  [rbp+57h+var_80], xmm1
0x18000c621  xor     edi, edi
0x18000c623  mov     [rbp+57h+var_70], rdi
0x18000c627  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000c62e  mov     [rbp+57h+var_98], rdi
0x18000c632  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18000c635  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 0F00h
0x18000c63b  lea     rcx, [rbp+57h+pSecDesc]; this
0x18000c63f  call    ?InitializeFromThreadToken@CSecurityDescriptor@ATL@@QEAAJHH@Z; ATL::CSecurityDescriptor::InitializeFromThreadToken(int,int)
0x18000c644  test    eax, eax
0x18000c646  jns     short loc_18000C666
0x18000c648  call    cs:__imp_GetLastError
0x18000c64e  mov     ebx, eax
0x18000c650  test    eax, eax
0x18000c652  jle     loc_18000C78D
0x18000c658  movzx   ebx, ax
0x18000c65b  or      ebx, 80070000h
0x18000c661  jmp     loc_18000C78D
0x18000c666  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000c66a  lea     r8, [rbp+57h+pSid]; pSid
0x18000c66e  xor     edx, edx; DomainSid
0x18000c670  lea     ecx, [rdx+11h]; WellKnownSidType
0x18000c673  call    cs:__imp_CreateWellKnownSid
0x18000c679  test    eax, eax
0x18000c67b  jz      short loc_18000C648
0x18000c67d  lea     rdx, [rbp+57h+pSid]; void *
0x18000c681  lea     rcx, [rbp+57h+pSecDesc]; this
0x18000c685  call    ?Allow@CSecurityDescriptor@ATL@@QEAAJPEAXK@Z; ATL::CSecurityDescriptor::Allow(void *,ulong)
0x18000c68a  mov     ebx, eax
0x18000c68c  test    eax, eax
0x18000c68e  js      loc_18000C78D
0x18000c694  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000c69b  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000c69f  lea     r8, [rbp+57h+pSid]; pSid
0x18000c6a3  xor     edx, edx; DomainSid
0x18000c6a5  lea     ecx, [rdx+1]; WellKnownSidType
0x18000c6a8  call    cs:__imp_CreateWellKnownSid
0x18000c6ae  test    eax, eax
0x18000c6b0  jz      short loc_18000C648
0x18000c6b2  lea     rdx, [rbp+57h+pSid]; void *
0x18000c6b6  lea     rcx, [rbp+57h+pSecDesc]; this
0x18000c6ba  call    ?Allow@CSecurityDescriptor@ATL@@QEAAJPEAXK@Z; ATL::CSecurityDescriptor::Allow(void *,ulong)
0x18000c6bf  mov     ebx, eax
0x18000c6c1  test    eax, eax
0x18000c6c3  js      loc_18000C78D
0x18000c6c9  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000c6d0  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000c6d4  lea     r8, [rbp+57h+pSid]; pSid
0x18000c6d8  xor     edx, edx; DomainSid
0x18000c6da  lea     ecx, [rdx+1Ch]; WellKnownSidType
0x18000c6dd  call    cs:__imp_CreateWellKnownSid
0x18000c6e3  test    eax, eax
0x18000c6e5  jz      loc_18000C648
0x18000c6eb  lea     rdx, [rbp+57h+pSid]; void *
0x18000c6ef  lea     rcx, [rbp+57h+pSecDesc]; this
0x18000c6f3  call    ?Allow@CSecurityDescriptor@ATL@@QEAAJPEAXK@Z; ATL::CSecurityDescriptor::Allow(void *,ulong)
0x18000c6f8  mov     ebx, eax
0x18000c6fa  test    eax, eax
0x18000c6fc  js      loc_18000C78D
0x18000c702  lea     rax, [rbp+57h+var_98]
0x18000c706  mov     [rsp+100h+var_B0], rax; pSid
0x18000c70b  mov     [rsp+100h+nSubAuthority7], edi; nSubAuthority7
0x18000c70f  mov     [rsp+100h+nSubAuthority6], edi; nSubAuthority6
0x18000c713  mov     [rsp+100h+nSubAuthority5], edi; nSubAuthority5
0x18000c717  mov     [rsp+100h+nSubAuthority4], edi; nSubAuthority4
0x18000c71b  mov     [rsp+100h+nSubAuthority3], edi; nSubAuthority3
0x18000c71f  mov     [rsp+100h+nSubAuthority2], edi; nSubAuthority2
0x18000c723  mov     r9d, 1000h; nSubAuthority1
0x18000c729  mov     r8d, 3; nSubAuthority0
0x18000c72f  mov     dl, 2; nSubAuthorityCount
0x18000c731  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000c735  call    cs:__imp_AllocateAndInitializeSid
0x18000c73b  test    eax, eax
0x18000c73d  jz      loc_18000C648
0x18000c743  mov     rdx, [rbp+57h+var_98]; void *
0x18000c747  lea     rcx, [rbp+57h+pSecDesc]; this
0x18000c74b  call    ?Allow@CSecurityDescriptor@ATL@@QEAAJPEAXK@Z; ATL::CSecurityDescriptor::Allow(void *,ulong)
0x18000c750  mov     ebx, eax
0x18000c752  test    eax, eax
0x18000c754  js      short loc_18000C78D
0x18000c756  mov     qword ptr [rsp+100h+nSubAuthority6], rdi; pReserved3
0x18000c75b  mov     [rsp+100h+nSubAuthority5], 2000h; dwCapabilities
0x18000c763  mov     qword ptr [rsp+100h+nSubAuthority4], rdi; pAuthList
0x18000c768  mov     [rsp+100h+nSubAuthority3], 3; dwImpLevel
0x18000c770  mov     [rsp+100h+nSubAuthority2], 2; dwAuthnLevel
0x18000c778  xor     r9d, r9d; pReserved1
0x18000c77b  xor     r8d, r8d; asAuthSvc
0x18000c77e  or      edx, 0FFFFFFFFh; cAuthSvc
0x18000c781  mov     rcx, [rbp+57h+pSecDesc]; pSecDesc
0x18000c785  call    cs:__imp_CoInitializeSecurity
0x18000c78b  mov     ebx, eax
0x18000c78d  mov     rcx, [rbp+57h+var_98]; pSid
0x18000c791  test    rcx, rcx
0x18000c794  jz      short loc_18000C79C
0x18000c796  call    cs:__imp_FreeSid
0x18000c79c  lea     rcx, [rbp+57h+pSecDesc]; this
0x18000c7a0  call    ??1CSecurityDescriptor@ATL@@QEAA@XZ; ATL::CSecurityDescriptor::~CSecurityDescriptor(void)
0x18000c7a5  mov     eax, ebx
0x18000c7a7  mov     rcx, [rbp+57h+var_10]
0x18000c7ab  xor     rcx, rsp; StackCookie
0x18000c7ae  call    __security_check_cookie
0x18000c7b3  lea     r11, [rsp+100h+var_s0]
0x18000c7bb  mov     rbx, [r11+10h]
0x18000c7bf  mov     rdi, [r11+18h]
0x18000c7c3  mov     rsp, r11
0x18000c7c6  pop     rbp
0x18000c7c7  retn
```
