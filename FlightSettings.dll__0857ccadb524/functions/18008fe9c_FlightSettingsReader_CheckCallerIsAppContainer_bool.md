# FlightSettingsReader::CheckCallerIsAppContainer(bool *)

- ea: `0x18008fe9c`
- end: `0x18008ffd8`
- name: `?CheckCallerIsAppContainer@FlightSettingsReader@@AEAAJPEA_N@Z`
- size: `316`
- prototype: `__int64 __fastcall(FlightSettingsReader *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180090a00`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x18001b2c0`
- `0x18008fe9c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ff12`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008ff12`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18008ff7c`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18008ff7c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18008ff96`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18008ff96`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18008fee1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18008fee1`

## string_xrefs

- `0x18008ff34`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`
- `0x18008ff55`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`

## pseudocode

```c
__int64 __fastcall FlightSettingsReader::CheckCallerIsAppContainer(FlightSettingsReader *this, bool *a2)
{
  int v2; // edi
  HRESULT v4; // eax
  int Error; // ebx
  __int64 v6; // rdx
  int ReturnLength; // [rsp+20h] [rbp-98h]
  int ReturnLengtha; // [rsp+20h] [rbp-98h]
  int v10; // [rsp+30h] [rbp-88h] BYREF
  DWORD v11[3]; // [rsp+34h] [rbp-84h] BYREF
  _QWORD TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v10 = 0;
  v2 = 0;
  v11[0] = 0;
  if ( !NtCurrentTeb()->IsImpersonating )
  {
    v4 = CoImpersonateClient();
    Error = v4;
    if ( v4 < 0 )
    {
      if ( v4 != -2147417833 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C5,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
          (const char *)(unsigned int)v4,
          ReturnLength);
        return (unsigned int)Error;
      }
    }
    else
    {
      v2 = 1;
    }
  }
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, TokenInformation, 0x54u, v11) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      v6 = 466;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
        (const char *)(unsigned int)Error,
        ReturnLengtha);
      goto LABEL_13;
    }
  }
  if ( (unsigned int)CheckTokenMembershipEx(-6, TokenInformation[0], 0, &v10) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      v6 = 470;
      goto LABEL_7;
    }
  }
  *a2 = v10 == 0;
LABEL_13:
  if ( v2 )
    CoRevertToSelf();
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18008fe9c  mov     [rsp+arg_0], rbx
0x18008fea1  mov     [rsp+arg_10], rsi
0x18008fea6  push    rdi
0x18008fea7  sub     rsp, 0B0h
0x18008feae  mov     rax, cs:__security_cookie
0x18008feb5  xor     rax, rsp
0x18008feb8  mov     [rsp+0B8h+var_18], rax
0x18008fec0  mov     [rsp+0B8h+var_88], 0
0x18008fec8  xor     edi, edi
0x18008feca  mov     [rsp+0B8h+var_84], 0
0x18008fed2  mov     rsi, rdx
0x18008fed5  mov     eax, gs:179Ch
0x18008fedd  test    eax, eax
0x18008fedf  jnz     short loc_18008FEF2
0x18008fee1  call    cs:__imp_CoImpersonateClient
0x18008fee7  mov     ebx, eax
0x18008fee9  test    eax, eax
0x18008feeb  js      short loc_18008FF45
0x18008feed  mov     edi, 1
0x18008fef2  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18008fef8  lea     rax, [rsp+0B8h+var_84]
0x18008fefd  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18008ff02  mov     qword ptr [rsp+0B8h+ReturnLength], rax; int
0x18008ff07  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18008ff0e  lea     edx, [r9-53h]; TokenInformationClass
0x18008ff12  call    cs:__imp_GetTokenInformation
0x18008ff18  test    eax, eax
0x18008ff1a  jnz     short loc_18008FF6B
0x18008ff1c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008ff21  mov     ebx, eax
0x18008ff23  test    eax, eax
0x18008ff25  jns     short loc_18008FF6B
0x18008ff27  mov     edx, 1D2h; void *
0x18008ff2c  mov     rcx, [rsp+0B8h]; this
0x18008ff34  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x18008ff3b  mov     r9d, ebx; char *
0x18008ff3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ff43  jmp     short loc_18008FF92
0x18008ff45  cmp     ebx, 80010117h
0x18008ff4b  jz      short loc_18008FEF2
0x18008ff4d  mov     rcx, [rsp+0B8h]; this
0x18008ff55  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x18008ff5c  mov     r9d, ebx; char *
0x18008ff5f  mov     edx, 1C5h; void *
0x18008ff64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ff69  jmp     short loc_18008FF9C
0x18008ff6b  mov     rdx, [rsp+0B8h+TokenInformation]
0x18008ff70  lea     r9, [rsp+0B8h+var_88]
0x18008ff75  xor     r8d, r8d
0x18008ff78  lea     rcx, [r8-6]
0x18008ff7c  call    cs:__imp_CheckTokenMembershipEx
0x18008ff82  test    eax, eax
0x18008ff84  jz      short loc_18008FFC3
0x18008ff86  xor     ebx, ebx
0x18008ff88  cmp     [rsp+0B8h+var_88], 0
0x18008ff8d  setz    al
0x18008ff90  mov     [rsi], al
0x18008ff92  test    edi, edi
0x18008ff94  jz      short loc_18008FF9C
0x18008ff96  call    cs:__imp_CoRevertToSelf
0x18008ff9c  mov     eax, ebx
0x18008ff9e  mov     rcx, [rsp+0B8h+var_18]
0x18008ffa6  xor     rcx, rsp; StackCookie
0x18008ffa9  call    __security_check_cookie
0x18008ffae  lea     r11, [rsp+0B8h+var_8]
0x18008ffb6  mov     rbx, [r11+10h]
0x18008ffba  mov     rsi, [r11+20h]
0x18008ffbe  mov     rsp, r11
0x18008ffc1  pop     rdi
0x18008ffc2  retn
0x18008ffc3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008ffc8  mov     ebx, eax
0x18008ffca  test    eax, eax
0x18008ffcc  jns     short loc_18008FF88
0x18008ffce  mov     edx, 1D6h
0x18008ffd3  jmp     loc_18008FF2C
```
