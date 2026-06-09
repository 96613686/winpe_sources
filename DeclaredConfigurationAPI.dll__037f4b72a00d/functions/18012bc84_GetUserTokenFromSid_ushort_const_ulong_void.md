# GetUserTokenFromSid(ushort const *,ulong,void * *)

- ea: `0x18012bc84`
- end: `0x18012bdf7`
- name: `?GetUserTokenFromSid@@YAJPEBGKPEAPEAX@Z`
- size: `371`
- prototype: `int(const unsigned __int16 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18012be00`

## callees

- `0x18000b9e0`
- `0x18000c8f4`
- `0x1800117dc`
- `0x18012bc84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012bd45`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012bd45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bd7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bdb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bdd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bd7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bdb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bdd3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18012bd33`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18012bd33`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012bd12`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012bd12`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18012bce5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18012bce5`

## pseudocode

```c
__int64 __fastcall GetUserTokenFromSid(const unsigned __int16 *a1, ULONG a2, void **a3)
{
  signed int LastError; // eax
  signed int v8; // ebx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  DWORD v13; // [rsp+30h] [rbp-D0h] BYREF
  void *phToken; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  PSID TokenInformation[128]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+378h]

  phToken = 0;
  v13 = 0;
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  *a3 = 0;
  if ( WTSQueryUserToken(a2, &phToken) )
  {
    if ( GetTokenInformation(phToken, TokenUser, TokenInformation, 0x400u, &v13) )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
      {
        if ( !(unsigned int)_o__wcsicmp(StringSid, a1) )
          *a3 = phToken;
        return 0;
      }
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
        return 0;
      v9 = 852;
    }
    else
    {
      v10 = GetLastError();
      v8 = v10;
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      if ( v8 >= 0 )
        return 0;
      v9 = 855;
    }
  }
  else
  {
    v11 = GetLastError();
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    if ( v8 >= 0 )
      return 0;
    v9 = 858;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\utils.cpp",
    (const char *)(unsigned int)v8,
    ReturnLength);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18012bc84  mov     [rsp-8+arg_18], rbx
0x18012bc89  push    rbp
0x18012bc8a  push    rsi
0x18012bc8b  push    rdi
0x18012bc8c  lea     rbp, [rsp-360h]
0x18012bc94  sub     rsp, 460h
0x18012bc9b  mov     rax, cs:__security_cookie
0x18012bca2  xor     rax, rsp
0x18012bca5  mov     [rbp+370h+var_20], rax
0x18012bcac  mov     rdi, r8
0x18012bcaf  mov     [rsp+470h+phToken], 0
0x18012bcb8  mov     ebx, edx
0x18012bcba  mov     [rsp+470h+var_440], 0
0x18012bcc2  mov     rsi, rcx
0x18012bcc5  xor     edx, edx; Val
0x18012bcc7  mov     r8d, 400h; Size
0x18012bccd  lea     rcx, [rsp+470h+TokenInformation]; void *
0x18012bcd2  call    memset_0
0x18012bcd7  lea     rdx, [rsp+470h+phToken]; phToken
0x18012bcdc  mov     qword ptr [rdi], 0
0x18012bce3  mov     ecx, ebx; SessionId
0x18012bce5  call    cs:__imp_WTSQueryUserToken
0x18012bceb  test    eax, eax
0x18012bced  jz      loc_18012BDD3
0x18012bcf3  mov     rcx, [rsp+470h+phToken]; TokenHandle
0x18012bcf8  lea     rax, [rsp+470h+var_440]
0x18012bcfd  mov     r9d, 400h; TokenInformationLength
0x18012bd03  mov     qword ptr [rsp+470h+ReturnLength], rax; int
0x18012bd08  lea     r8, [rsp+470h+TokenInformation]; TokenInformation
0x18012bd0d  mov     edx, 1; TokenInformationClass
0x18012bd12  call    cs:__imp_GetTokenInformation
0x18012bd18  test    eax, eax
0x18012bd1a  jz      loc_18012BDB3
0x18012bd20  mov     rcx, [rsp+470h+TokenInformation]; Sid
0x18012bd25  lea     rdx, [rsp+470h+StringSid]; StringSid
0x18012bd2a  mov     [rsp+470h+StringSid], 0
0x18012bd33  call    cs:__imp_ConvertSidToStringSidW
0x18012bd39  test    eax, eax
0x18012bd3b  jz      short loc_18012BD7B
0x18012bd3d  mov     rcx, [rsp+470h+StringSid]
0x18012bd42  mov     rdx, rsi
0x18012bd45  call    cs:__imp__o__wcsicmp
0x18012bd4b  test    eax, eax
0x18012bd4d  jnz     short loc_18012BD57
0x18012bd4f  mov     rax, [rsp+470h+phToken]
0x18012bd54  mov     [rdi], rax
0x18012bd57  xor     eax, eax
0x18012bd59  mov     rcx, [rbp+370h+var_20]
0x18012bd60  xor     rcx, rsp; StackCookie
0x18012bd63  call    __security_check_cookie
0x18012bd68  mov     rbx, [rsp+470h+arg_18]
0x18012bd70  add     rsp, 460h
0x18012bd77  pop     rdi
0x18012bd78  pop     rsi
0x18012bd79  pop     rbp
0x18012bd7a  retn
0x18012bd7b  call    cs:__imp_GetLastError
0x18012bd81  mov     ebx, eax
0x18012bd83  test    eax, eax
0x18012bd85  jle     short loc_18012BD90
0x18012bd87  movzx   ebx, ax
0x18012bd8a  or      ebx, 80070000h
0x18012bd90  test    ebx, ebx
0x18012bd92  jns     short loc_18012BD57
0x18012bd94  mov     edx, 354h; void *
0x18012bd99  mov     rcx, [rbp+378h]; this
0x18012bda0  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x18012bda7  mov     r9d, ebx; char *
0x18012bdaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012bdaf  mov     eax, ebx
0x18012bdb1  jmp     short loc_18012BD59
0x18012bdb3  call    cs:__imp_GetLastError
0x18012bdb9  mov     ebx, eax
0x18012bdbb  test    eax, eax
0x18012bdbd  jle     short loc_18012BDC8
0x18012bdbf  movzx   ebx, ax
0x18012bdc2  or      ebx, 80070000h
0x18012bdc8  test    ebx, ebx
0x18012bdca  jns     short loc_18012BD57
0x18012bdcc  mov     edx, 357h
0x18012bdd1  jmp     short loc_18012BD99
0x18012bdd3  call    cs:__imp_GetLastError
0x18012bdd9  mov     ebx, eax
0x18012bddb  test    eax, eax
0x18012bddd  jle     short loc_18012BDE8
0x18012bddf  movzx   ebx, ax
0x18012bde2  or      ebx, 80070000h
0x18012bde8  test    ebx, ebx
0x18012bdea  jns     loc_18012BD57
0x18012bdf0  mov     edx, 35Ah
0x18012bdf5  jmp     short loc_18012BD99
```
