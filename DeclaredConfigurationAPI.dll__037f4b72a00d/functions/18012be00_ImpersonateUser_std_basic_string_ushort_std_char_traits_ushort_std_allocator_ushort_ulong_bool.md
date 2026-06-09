# ImpersonateUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,bool &)

- ea: `0x18012be00`
- end: `0x18012bf8b`
- name: `?ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z`
- size: `395`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18012a874`

## callees

- `0x1800117dc`
- `0x180018ac0`
- `0x18012bc84`
- `0x18012be00`
- `0x18012bf94`
- `0x18012c77c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012beff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012beff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012bf58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012bf67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012bf67`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18012bf28`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18012bf28`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012bef2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18012bef2`

## string_xrefs

- `0x18012bf13`: `ImpersonateUser - Failed to get an linked token :0x%1!x!`
- `0x18012bf4c`: `ImpersonateUser - Failed to impersonate - Error 0x%1!x!`
- `0x18012be2e`: `ImpersonateUser - a valid SID must be specified`
- `0x18012be55`: `ImpersonateUser - IsRunningInSystemContext() failed - Error 0x%1!x!`
- `0x18012be6e`: `ImpersonateUser - Cannot impersoante, not running as SYSTEM.`
- `0x18012bebc`: `ImpersonateUser - GetUserTokenFromSid() failed - Error 0x%1!x!`

## pseudocode

```c
__int64 __fastcall ImpersonateUser(unsigned __int16 *a1, unsigned int a2, _BYTE *a3)
{
  bool v3; // zf
  __int64 v7; // rdx
  unsigned int v8; // ebx
  int v9; // eax
  const unsigned __int16 *v10; // rcx
  int UserTokenFromSid; // eax
  HANDLE v12; // rsi
  BOOL v13; // r14d
  signed int LastError; // eax
  signed int v15; // eax
  int ReturnLength; // [rsp+20h] [rbp-30h]
  bool v18; // [rsp+30h] [rbp-20h] BYREF
  DWORD v19; // [rsp+34h] [rbp-1Ch] BYREF
  HANDLE TokenInformation; // [rsp+38h] [rbp-18h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v3 = *((_QWORD *)a1 + 2) == 0;
  v18 = 0;
  TokenHandle = 0;
  if ( v3 )
  {
    LogTelemetryError(L"ImpersonateUser - a valid SID must be specified");
    v7 = 588;
    v8 = -2147024809;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\utils.cpp",
      (const char *)v8,
      ReturnLength);
    goto LABEL_26;
  }
  v9 = IsRunningInSystemContext(&v18);
  v8 = v9;
  if ( v9 < 0 )
  {
    LogTelemetryError(L"ImpersonateUser - IsRunningInSystemContext() failed - Error 0x%1!x!", (unsigned int)v9);
    goto LABEL_26;
  }
  if ( !v18 )
  {
    LogTelemetryError(L"ImpersonateUser - Cannot impersoante, not running as SYSTEM.");
    v7 = 599;
    v8 = -2147467259;
    goto LABEL_8;
  }
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v10 = a1;
  else
    v10 = *(const unsigned __int16 **)a1;
  UserTokenFromSid = GetUserTokenFromSid(v10, a2, &TokenHandle);
  v8 = UserTokenFromSid;
  if ( UserTokenFromSid >= 0 )
  {
    v12 = TokenHandle;
    v19 = 0;
    TokenInformation = 0;
    v13 = GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &v19);
    if ( v13 )
    {
      v12 = TokenInformation;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LogTelemetryError(L"ImpersonateUser - Failed to get an linked token :0x%1!x!", (unsigned int)LastError);
    }
    if ( ImpersonateLoggedOnUser(v12) )
    {
      *a3 = 1;
    }
    else
    {
      v15 = GetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      LogTelemetryError(L"ImpersonateUser - Failed to impersonate - Error 0x%1!x!", (unsigned int)v15);
      GetLastError();
    }
    if ( v13 )
      CloseHandle(TokenInformation);
  }
  else
  {
    LogTelemetryError(L"ImpersonateUser - GetUserTokenFromSid() failed - Error 0x%1!x!", (unsigned int)UserTokenFromSid);
  }
LABEL_26:
  std::wstring::_Tidy_deallocate(a1);
  return v8;
}

```

## disassembly

```asm
0x18012be00  mov     [rsp-28h+arg_18], rbx
0x18012be05  push    rbp
0x18012be06  push    rsi
0x18012be07  push    rdi
0x18012be08  push    r14
0x18012be0a  push    r15
0x18012be0c  mov     rbp, rsp
0x18012be0f  sub     rsp, 50h
0x18012be13  cmp     qword ptr [rcx+10h], 0
0x18012be18  mov     r15, r8
0x18012be1b  mov     esi, edx
0x18012be1d  mov     [rbp+var_20], 0
0x18012be21  mov     rdi, rcx
0x18012be24  mov     [rbp+TokenHandle], 0
0x18012be2c  jnz     short loc_18012BE46
0x18012be2e  lea     rcx, aImpersonateuse_1; "ImpersonateUser - a valid SID must be s"...
0x18012be35  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012be3a  mov     edx, 24Ch
0x18012be3f  mov     ebx, 80070057h
0x18012be44  jmp     short loc_18012BE84
0x18012be46  lea     rcx, [rbp+var_20]; bool *
0x18012be4a  call    ?IsRunningInSystemContext@@YAJAEA_N@Z; IsRunningInSystemContext(bool &)
0x18012be4f  mov     ebx, eax
0x18012be51  test    eax, eax
0x18012be53  jns     short loc_18012BE68
0x18012be55  lea     rcx, aImpersonateuse_0; "ImpersonateUser - IsRunningInSystemCont"...
0x18012be5c  mov     edx, eax
0x18012be5e  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012be63  jmp     loc_18012BF6D
0x18012be68  cmp     [rbp+var_20], 0
0x18012be6c  jnz     short loc_18012BE9C
0x18012be6e  lea     rcx, aImpersonateuse; "ImpersonateUser - Cannot impersoante, n"...
0x18012be75  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012be7a  mov     edx, 257h; void *
0x18012be7f  mov     ebx, 80004005h
0x18012be84  mov     rcx, [rbp+28h]; this
0x18012be88  lea     r8, aOnecoreuapAdmi_35; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x18012be8f  mov     r9d, ebx; char *
0x18012be92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012be97  jmp     loc_18012BF6D
0x18012be9c  cmp     qword ptr [rdi+18h], 7
0x18012bea1  jbe     short loc_18012BEA8
0x18012bea3  mov     rcx, [rdi]
0x18012bea6  jmp     short loc_18012BEAB
0x18012bea8  mov     rcx, rdi; unsigned __int16 *
0x18012beab  lea     r8, [rbp+TokenHandle]; void **
0x18012beaf  mov     edx, esi; unsigned int
0x18012beb1  call    ?GetUserTokenFromSid@@YAJPEBGKPEAPEAX@Z; GetUserTokenFromSid(ushort const *,ulong,void * *)
0x18012beb6  mov     ebx, eax
0x18012beb8  test    eax, eax
0x18012beba  jns     short loc_18012BEC5
0x18012bebc  lea     rcx, aImpersonateuse_3; "ImpersonateUser - GetUserTokenFromSid()"...
0x18012bec3  jmp     short loc_18012BE5C
0x18012bec5  mov     rsi, [rbp+TokenHandle]
0x18012bec9  lea     rax, [rbp+var_1C]
0x18012becd  mov     r9d, 8; TokenInformationLength
0x18012bed3  mov     [rbp+var_1C], 0
0x18012beda  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18012bede  mov     [rbp+TokenInformation], 0
0x18012bee6  mov     rcx, rsi; TokenHandle
0x18012bee9  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x18012beee  lea     edx, [r9+0Bh]; TokenInformationClass
0x18012bef2  call    cs:__imp_GetTokenInformation
0x18012bef8  mov     r14d, eax
0x18012befb  test    eax, eax
0x18012befd  jnz     short loc_18012BF21
0x18012beff  call    cs:__imp_GetLastError
0x18012bf05  test    eax, eax
0x18012bf07  jle     short loc_18012BF11
0x18012bf09  movzx   eax, ax
0x18012bf0c  or      eax, 80070000h
0x18012bf11  mov     edx, eax
0x18012bf13  lea     rcx, aImpersonateuse_2; "ImpersonateUser - Failed to get an link"...
0x18012bf1a  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012bf1f  jmp     short loc_18012BF25
0x18012bf21  mov     rsi, [rbp+TokenInformation]
0x18012bf25  mov     rcx, rsi; hToken
0x18012bf28  call    cs:__imp_ImpersonateLoggedOnUser
0x18012bf2e  test    eax, eax
0x18012bf30  jz      short loc_18012BF38
0x18012bf32  mov     byte ptr [r15], 1
0x18012bf36  jmp     short loc_18012BF5E
0x18012bf38  call    cs:__imp_GetLastError
0x18012bf3e  test    eax, eax
0x18012bf40  jle     short loc_18012BF4A
0x18012bf42  movzx   eax, ax
0x18012bf45  or      eax, 80070000h
0x18012bf4a  mov     edx, eax
0x18012bf4c  lea     rcx, aImpersonateuse_4; "ImpersonateUser - Failed to impersonate"...
0x18012bf53  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x18012bf58  call    cs:__imp_GetLastError
0x18012bf5e  test    r14d, r14d
0x18012bf61  jz      short loc_18012BF6D
0x18012bf63  mov     rcx, [rbp+TokenInformation]; hObject
0x18012bf67  call    cs:__imp_CloseHandle
0x18012bf6d  mov     rcx, rdi
0x18012bf70  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012bf75  mov     eax, ebx
0x18012bf77  mov     rbx, [rsp+50h+arg_18]
0x18012bf7f  add     rsp, 50h
0x18012bf83  pop     r15
0x18012bf85  pop     r14
0x18012bf87  pop     rdi
0x18012bf88  pop     rsi
0x18012bf89  pop     rbp
0x18012bf8a  retn
```
