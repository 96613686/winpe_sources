# GetUserTokenFromSid(ushort const *,ulong,void * *)

- ea: `0x14004e5c4`
- end: `0x14004e737`
- name: `?GetUserTokenFromSid@@YAJPEBGKPEAPEAX@Z`
- size: `371`
- prototype: `int(const unsigned __int16 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004e740`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x1400095b4`
- `0x14004e5c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004e685`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004e685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e6f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e6f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e713`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14004e673`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14004e673`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004e652`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004e652`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x14004e625`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x14004e625`

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
0x14004e5c4  mov     [rsp-8+arg_18], rbx
0x14004e5c9  push    rbp
0x14004e5ca  push    rsi
0x14004e5cb  push    rdi
0x14004e5cc  lea     rbp, [rsp-360h]
0x14004e5d4  sub     rsp, 460h
0x14004e5db  mov     rax, cs:__security_cookie
0x14004e5e2  xor     rax, rsp
0x14004e5e5  mov     [rbp+370h+var_20], rax
0x14004e5ec  mov     rdi, r8
0x14004e5ef  mov     [rsp+470h+phToken], 0
0x14004e5f8  mov     ebx, edx
0x14004e5fa  mov     [rsp+470h+var_440], 0
0x14004e602  mov     rsi, rcx
0x14004e605  xor     edx, edx; Val
0x14004e607  mov     r8d, 400h; Size
0x14004e60d  lea     rcx, [rsp+470h+TokenInformation]; void *
0x14004e612  call    memset_0
0x14004e617  lea     rdx, [rsp+470h+phToken]; phToken
0x14004e61c  mov     qword ptr [rdi], 0
0x14004e623  mov     ecx, ebx; SessionId
0x14004e625  call    cs:__imp_WTSQueryUserToken
0x14004e62b  test    eax, eax
0x14004e62d  jz      loc_14004E713
0x14004e633  mov     rcx, [rsp+470h+phToken]; TokenHandle
0x14004e638  lea     rax, [rsp+470h+var_440]
0x14004e63d  mov     r9d, 400h; TokenInformationLength
0x14004e643  mov     qword ptr [rsp+470h+ReturnLength], rax; int
0x14004e648  lea     r8, [rsp+470h+TokenInformation]; TokenInformation
0x14004e64d  mov     edx, 1; TokenInformationClass
0x14004e652  call    cs:__imp_GetTokenInformation
0x14004e658  test    eax, eax
0x14004e65a  jz      loc_14004E6F3
0x14004e660  mov     rcx, [rsp+470h+TokenInformation]; Sid
0x14004e665  lea     rdx, [rsp+470h+StringSid]; StringSid
0x14004e66a  mov     [rsp+470h+StringSid], 0
0x14004e673  call    cs:__imp_ConvertSidToStringSidW
0x14004e679  test    eax, eax
0x14004e67b  jz      short loc_14004E6BB
0x14004e67d  mov     rcx, [rsp+470h+StringSid]
0x14004e682  mov     rdx, rsi
0x14004e685  call    cs:__imp__o__wcsicmp
0x14004e68b  test    eax, eax
0x14004e68d  jnz     short loc_14004E697
0x14004e68f  mov     rax, [rsp+470h+phToken]
0x14004e694  mov     [rdi], rax
0x14004e697  xor     eax, eax
0x14004e699  mov     rcx, [rbp+370h+var_20]
0x14004e6a0  xor     rcx, rsp; StackCookie
0x14004e6a3  call    __security_check_cookie
0x14004e6a8  mov     rbx, [rsp+470h+arg_18]
0x14004e6b0  add     rsp, 460h
0x14004e6b7  pop     rdi
0x14004e6b8  pop     rsi
0x14004e6b9  pop     rbp
0x14004e6ba  retn
0x14004e6bb  call    cs:__imp_GetLastError
0x14004e6c1  mov     ebx, eax
0x14004e6c3  test    eax, eax
0x14004e6c5  jle     short loc_14004E6D0
0x14004e6c7  movzx   ebx, ax
0x14004e6ca  or      ebx, 80070000h
0x14004e6d0  test    ebx, ebx
0x14004e6d2  jns     short loc_14004E697
0x14004e6d4  mov     edx, 354h; void *
0x14004e6d9  mov     rcx, [rbp+378h]; this
0x14004e6e0  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004e6e7  mov     r9d, ebx; char *
0x14004e6ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004e6ef  mov     eax, ebx
0x14004e6f1  jmp     short loc_14004E699
0x14004e6f3  call    cs:__imp_GetLastError
0x14004e6f9  mov     ebx, eax
0x14004e6fb  test    eax, eax
0x14004e6fd  jle     short loc_14004E708
0x14004e6ff  movzx   ebx, ax
0x14004e702  or      ebx, 80070000h
0x14004e708  test    ebx, ebx
0x14004e70a  jns     short loc_14004E697
0x14004e70c  mov     edx, 357h
0x14004e711  jmp     short loc_14004E6D9
0x14004e713  call    cs:__imp_GetLastError
0x14004e719  mov     ebx, eax
0x14004e71b  test    eax, eax
0x14004e71d  jle     short loc_14004E728
0x14004e71f  movzx   ebx, ax
0x14004e722  or      ebx, 80070000h
0x14004e728  test    ebx, ebx
0x14004e72a  jns     loc_14004E697
0x14004e730  mov     edx, 35Ah
0x14004e735  jmp     short loc_14004E6D9
```
