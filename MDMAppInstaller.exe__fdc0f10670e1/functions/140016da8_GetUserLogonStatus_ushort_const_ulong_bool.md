# GetUserLogonStatus(ushort const *,ulong,bool &)

- ea: `0x140016da8`
- end: `0x140016ec4`
- name: `?GetUserLogonStatus@@YAJPEBGKAEA_N@Z`
- size: `284`
- prototype: `__int64 __fastcall(wchar_t *String2, ULONG SessionId, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000cd78`
- `0x14000e6cc`

## callees

- `0x14000740c`
- `0x140016da8`
- `0x14001a8aa`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x140016e4b`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140016e4b`
- `ADVAPI32!GetTokenInformation` at `0x140016e2e`
- `ADVAPI32!GetTokenInformation` at `0x140016e2e`
- `KERNEL32!CloseHandle` at `0x140016e88`
- `KERNEL32!CloseHandle` at `0x140016e88`
- `KERNEL32!GetLastError` at `0x140016e6e`
- `KERNEL32!GetLastError` at `0x140016e6e`
- `msvcrt!_wcsicmp` at `0x140016e5f`
- `msvcrt!_wcsicmp` at `0x140016e5f`
- `WTSAPI32!WTSQueryUserToken` at `0x140016e05`
- `WTSAPI32!WTSQueryUserToken` at `0x140016e05`

## pseudocode

```c
__int64 __fastcall GetUserLogonStatus(wchar_t *String2, ULONG SessionId, bool *a3)
{
  unsigned int v6; // ebx
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  void *phToken; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  PSID TokenInformation[128]; // [rsp+50h] [rbp-B0h] BYREF

  phToken = 0;
  ReturnLength = 0;
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  *a3 = 0;
  if ( WTSQueryUserToken(SessionId, &phToken)
    && GetTokenInformation(phToken, TokenUser, TokenInformation, 0x400u, &ReturnLength)
    && (StringSid = 0, ConvertSidToStringSidW(TokenInformation[0], &StringSid)) )
  {
    v6 = 0;
    if ( !_wcsicmp(StringSid, String2) )
      *a3 = 1;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  CloseHandle(phToken);
  if ( (v6 & 0x80000000) != 0 )
    LogError(L"GetUserLogonStatus failed with error 0x%1!x!", v6);
  return v6;
}

```

## disassembly

```asm
0x140016da8  mov     [rsp-8+arg_18], rbx
0x140016dad  push    rbp
0x140016dae  push    rsi
0x140016daf  push    rdi
0x140016db0  lea     rbp, [rsp-360h]
0x140016db8  sub     rsp, 460h
0x140016dbf  mov     rax, cs:__security_cookie
0x140016dc6  xor     rax, rsp
0x140016dc9  mov     [rbp+370h+var_20], rax
0x140016dd0  mov     rdi, r8
0x140016dd3  mov     [rsp+470h+phToken], 0
0x140016ddc  mov     ebx, edx
0x140016dde  mov     [rsp+470h+var_440], 0
0x140016de6  mov     rsi, rcx
0x140016de9  xor     edx, edx; Val
0x140016deb  mov     r8d, 400h; Size
0x140016df1  lea     rcx, [rsp+470h+TokenInformation]; void *
0x140016df6  call    memset_0
0x140016dfb  lea     rdx, [rsp+470h+phToken]; phToken
0x140016e00  mov     byte ptr [rdi], 0
0x140016e03  mov     ecx, ebx; SessionId
0x140016e05  call    cs:__imp_WTSQueryUserToken
0x140016e0b  test    eax, eax
0x140016e0d  jz      short loc_140016E6E
0x140016e0f  mov     rcx, [rsp+470h+phToken]; TokenHandle
0x140016e14  lea     rax, [rsp+470h+var_440]
0x140016e19  mov     r9d, 400h; TokenInformationLength
0x140016e1f  mov     [rsp+470h+ReturnLength], rax; ReturnLength
0x140016e24  lea     r8, [rsp+470h+TokenInformation]; TokenInformation
0x140016e29  mov     edx, 1; TokenInformationClass
0x140016e2e  call    cs:__imp_GetTokenInformation
0x140016e34  test    eax, eax
0x140016e36  jz      short loc_140016E6E
0x140016e38  mov     rcx, [rsp+470h+TokenInformation]; Sid
0x140016e3d  lea     rdx, [rsp+470h+StringSid]; StringSid
0x140016e42  mov     [rsp+470h+StringSid], 0
0x140016e4b  call    cs:__imp_ConvertSidToStringSidW
0x140016e51  test    eax, eax
0x140016e53  jz      short loc_140016E6E
0x140016e55  mov     rcx, [rsp+470h+StringSid]; String1
0x140016e5a  mov     rdx, rsi; String2
0x140016e5d  xor     ebx, ebx
0x140016e5f  call    cs:__imp__wcsicmp
0x140016e65  test    eax, eax
0x140016e67  jnz     short loc_140016E83
0x140016e69  mov     byte ptr [rdi], 1
0x140016e6c  jmp     short loc_140016E83
0x140016e6e  call    cs:__imp_GetLastError
0x140016e74  mov     ebx, eax
0x140016e76  test    eax, eax
0x140016e78  jle     short loc_140016E83
0x140016e7a  movzx   ebx, ax
0x140016e7d  or      ebx, 80070000h
0x140016e83  mov     rcx, [rsp+470h+phToken]; hObject
0x140016e88  call    cs:__imp_CloseHandle
0x140016e8e  test    ebx, ebx
0x140016e90  jns     short loc_140016EA0
0x140016e92  mov     edx, ebx
0x140016e94  lea     rcx, aGetuserlogonst; "GetUserLogonStatus failed with error 0x"...
0x140016e9b  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140016ea0  mov     eax, ebx
0x140016ea2  mov     rcx, [rbp+370h+var_20]
0x140016ea9  xor     rcx, rsp; StackCookie
0x140016eac  call    __security_check_cookie
0x140016eb1  mov     rbx, [rsp+470h+arg_18]
0x140016eb9  add     rsp, 460h
0x140016ec0  pop     rdi
0x140016ec1  pop     rsi
0x140016ec2  pop     rbp
0x140016ec3  retn
```
