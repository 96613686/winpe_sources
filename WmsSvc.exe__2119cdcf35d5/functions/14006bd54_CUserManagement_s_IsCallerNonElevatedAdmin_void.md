# CUserManagement::s_IsCallerNonElevatedAdmin(void *)

- ea: `0x14006bd54`
- end: `0x14006bf6f`
- name: `?s_IsCallerNonElevatedAdmin@CUserManagement@@SAHPEAX@Z`
- size: `539`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006c998`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006bd54`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x14006be4f`
- `ADVAPI32!CreateWellKnownSid` at `0x14006be4f`
- `ADVAPI32!CheckTokenMembership` at `0x14006be82`
- `ADVAPI32!CheckTokenMembership` at `0x14006be82`
- `ADVAPI32!GetTokenInformation` at `0x14006bdcd`
- `ADVAPI32!GetTokenInformation` at `0x14006be1b`
- `ADVAPI32!GetTokenInformation` at `0x14006bdcd`
- `ADVAPI32!GetTokenInformation` at `0x14006be1b`
- `KERNEL32!GetLastError` at `0x14006bdd7`
- `KERNEL32!GetLastError` at `0x14006be25`
- `KERNEL32!GetLastError` at `0x14006be59`
- `KERNEL32!GetLastError` at `0x14006be90`
- `KERNEL32!GetLastError` at `0x14006bdd7`
- `KERNEL32!GetLastError` at `0x14006be25`
- `KERNEL32!GetLastError` at `0x14006be59`
- `KERNEL32!GetLastError` at `0x14006be90`
- `KERNEL32!IsDebuggerPresent` at `0x14006beeb`
- `KERNEL32!IsDebuggerPresent` at `0x14006beeb`

## string_xrefs

- `0x14006bec0`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`

## pseudocode

```c
__int64 __fastcall CUserManagement::s_IsCallerNonElevatedAdmin(HANDLE TokenHandle)
{
  signed int v2; // eax
  signed int v3; // ebx
  unsigned int v4; // r13d
  signed int v5; // eax
  signed int v6; // eax
  signed int LastError; // eax
  int TokenInformation; // [rsp+40h] [rbp-49h] BYREF
  DWORD ReturnLength; // [rsp+44h] [rbp-45h] BYREF
  WINBOOL IsMember; // [rsp+48h] [rbp-41h] BYREF
  DWORD cbSid; // [rsp+4Ch] [rbp-3Dh] BYREF
  HANDLE TokenHandlea[2]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-29h] BYREF

  IsMember = 0;
  ReturnLength = 0;
  TokenHandlea[0] = 0;
  TokenInformation = 2;
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( TokenInformation != 3 )
      return (unsigned int)IsMember;
    if ( GetTokenInformation(TokenHandle, TokenLinkedToken, TokenHandlea, 8u, &ReturnLength) )
    {
      if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
      {
        if ( CheckTokenMembership(TokenHandlea[0], pSid, &IsMember) )
          return (unsigned int)IsMember;
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        v4 = 1648;
      }
      else
      {
        v6 = GetLastError();
        v3 = v6;
        if ( v6 > 0 )
          v3 = (unsigned __int16)v6 | 0x80070000;
        v4 = 1645;
      }
    }
    else
    {
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      v4 = 1642;
    }
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = 1635;
  }
  if ( v3 >= 0 )
    v3 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
    v4,
    L"CUserManagement::s_IsCallerNonElevatedAdmin",
    L"CBRAEx",
    L"fSuccess",
    v3);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      v4,
      L"CUserManagement::s_IsCallerNonElevatedAdmin",
      L"CBRAEx",
      L"fSuccess",
      v3);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      v4,
      L"CUserManagement::s_IsCallerNonElevatedAdmin",
      L"CBRAEx",
      L"fSuccess",
      v3);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x14006bd54  mov     [rsp-8+arg_8], rbx
0x14006bd59  mov     [rsp-8+arg_10], rsi
0x14006bd5e  push    rbp
0x14006bd5f  push    rdi
0x14006bd60  push    r13
0x14006bd62  push    r14
0x14006bd64  push    r15
0x14006bd66  lea     rbp, [rsp-37h]
0x14006bd6b  sub     rsp, 0C0h
0x14006bd72  mov     rax, cs:__security_cookie
0x14006bd79  xor     rax, rsp
0x14006bd7c  mov     [rbp+57h+var_30], rax
0x14006bd80  mov     rbx, rcx
0x14006bd83  mov     [rbp+57h+IsMember], 0
0x14006bd8a  mov     edi, 44h ; 'D'
0x14006bd8f  mov     [rbp+57h+var_9C], 0
0x14006bd96  mov     r8d, edi; Size
0x14006bd99  mov     [rbp+57h+TokenHandle], 0
0x14006bda1  xor     edx, edx; Val
0x14006bda3  mov     [rbp+57h+TokenInformation], 2
0x14006bdaa  lea     rcx, [rbp+57h+pSid]; void *
0x14006bdae  call    memset_0
0x14006bdb3  lea     rax, [rbp+57h+var_9C]
0x14006bdb7  mov     [rbp+57h+cbSid], edi
0x14006bdba  lea     r9d, [rdi-40h]; TokenInformationLength
0x14006bdbe  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x14006bdc3  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14006bdc7  mov     rcx, rbx; TokenHandle
0x14006bdca  lea     edx, [rdi-32h]; TokenInformationClass
0x14006bdcd  call    cs:__imp_GetTokenInformation
0x14006bdd3  test    eax, eax
0x14006bdd5  jnz     short loc_14006BDF7
0x14006bdd7  call    cs:__imp_GetLastError
0x14006bddd  mov     ebx, eax
0x14006bddf  test    eax, eax
0x14006bde1  jle     short loc_14006BDEC
0x14006bde3  movzx   ebx, ax
0x14006bde6  or      ebx, 80070000h
0x14006bdec  mov     r13d, 663h
0x14006bdf2  jmp     loc_14006BEAB
0x14006bdf7  cmp     [rbp+57h+TokenInformation], 3
0x14006bdfb  jnz     loc_14006BF44
0x14006be01  mov     r9d, 8; TokenInformationLength
0x14006be07  lea     rax, [rbp+57h+var_9C]
0x14006be0b  lea     r8, [rbp+57h+TokenHandle]; TokenInformation
0x14006be0f  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x14006be14  mov     rcx, rbx; TokenHandle
0x14006be17  lea     edx, [r9+0Bh]; TokenInformationClass
0x14006be1b  call    cs:__imp_GetTokenInformation
0x14006be21  test    eax, eax
0x14006be23  jnz     short loc_14006BE42
0x14006be25  call    cs:__imp_GetLastError
0x14006be2b  mov     ebx, eax
0x14006be2d  test    eax, eax
0x14006be2f  jle     short loc_14006BE3A
0x14006be31  movzx   ebx, ax
0x14006be34  or      ebx, 80070000h
0x14006be3a  mov     r13d, 66Ah
0x14006be40  jmp     short loc_14006BEAB
0x14006be42  xor     edx, edx; DomainSid
0x14006be44  lea     r9, [rbp+57h+cbSid]; cbSid
0x14006be48  lea     r8, [rbp+57h+pSid]; pSid
0x14006be4c  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x14006be4f  call    cs:__imp_CreateWellKnownSid
0x14006be55  test    eax, eax
0x14006be57  jnz     short loc_14006BE76
0x14006be59  call    cs:__imp_GetLastError
0x14006be5f  mov     ebx, eax
0x14006be61  test    eax, eax
0x14006be63  jle     short loc_14006BE6E
0x14006be65  movzx   ebx, ax
0x14006be68  or      ebx, 80070000h
0x14006be6e  mov     r13d, 66Dh
0x14006be74  jmp     short loc_14006BEAB
0x14006be76  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14006be7a  lea     r8, [rbp+57h+IsMember]; IsMember
0x14006be7e  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x14006be82  call    cs:__imp_CheckTokenMembership
0x14006be88  test    eax, eax
0x14006be8a  jnz     loc_14006BF44
0x14006be90  call    cs:__imp_GetLastError
0x14006be96  mov     ebx, eax
0x14006be98  test    eax, eax
0x14006be9a  jle     short loc_14006BEA5
0x14006be9c  movzx   ebx, ax
0x14006be9f  or      ebx, 80070000h
0x14006bea5  mov     r13d, 670h
0x14006beab  mov     eax, 80004005h
0x14006beb0  lea     r15, aCbraex; "CBRAEx"
0x14006beb7  test    ebx, ebx
0x14006beb9  lea     rsi, aCusermanagemen_9; "CUserManagement::s_IsCallerNonElevatedA"...
0x14006bec0  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006bec7  mov     r9, r15; unsigned __int16 *
0x14006beca  cmovns  ebx, eax
0x14006becd  lea     r14, aFsuccess; "fSuccess"
0x14006bed4  mov     [rsp+0E0h+var_B8], ebx; int
0x14006bed8  mov     r8, rsi; unsigned __int16 *
0x14006bedb  mov     edx, r13d; unsigned int
0x14006bede  mov     [rsp+0E0h+ReturnLength], r14; unsigned __int16 *
0x14006bee3  mov     rcx, rdi; unsigned __int16 *
0x14006bee6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006beeb  call    cs:__imp_IsDebuggerPresent
0x14006bef1  test    eax, eax
0x14006bef3  jz      short loc_14006BF21
0x14006bef5  mov     [rsp+0E0h+var_A8], ebx
0x14006bef9  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006bf00  mov     [rsp+0E0h+var_B0], r14
0x14006bf05  mov     r9d, r13d
0x14006bf08  mov     qword ptr [rsp+0E0h+var_B8], r15
0x14006bf0d  mov     r8, rdi
0x14006bf10  mov     ecx, 2; unsigned __int8
0x14006bf15  mov     [rsp+0E0h+ReturnLength], rsi
0x14006bf1a  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006bf1f  jmp     short loc_14006BF44
0x14006bf21  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x14006bf25  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006bf2c  mov     qword ptr [rsp+0E0h+var_B8], r14
0x14006bf31  mov     r9, rsi
0x14006bf34  mov     r8d, r13d
0x14006bf37  mov     [rsp+0E0h+ReturnLength], r15
0x14006bf3c  mov     rdx, rdi
0x14006bf3f  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006bf44  mov     eax, [rbp+57h+IsMember]
0x14006bf47  mov     rcx, [rbp+57h+var_30]
0x14006bf4b  xor     rcx, rsp; StackCookie
0x14006bf4e  call    __security_check_cookie
0x14006bf53  lea     r11, [rsp+0E0h+var_20]
0x14006bf5b  mov     rbx, [r11+38h]
0x14006bf5f  mov     rsi, [r11+40h]
0x14006bf63  mov     rsp, r11
0x14006bf66  pop     r15
0x14006bf68  pop     r14
0x14006bf6a  pop     r13
0x14006bf6c  pop     rdi
0x14006bf6d  pop     rbp
0x14006bf6e  retn
```
