# ImpersonateUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,bool &)

- ea: `0x14004e740`
- end: `0x14004e8cb`
- name: `?ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z`
- size: `395`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, _BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004c794`

## callees

- `0x1400095b4`
- `0x14001ed14`
- `0x14004e5c4`
- `0x14004e740`
- `0x14004e8d4`
- `0x14004f4d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e898`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e8a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004e8a7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14004e868`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14004e868`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004e832`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004e832`

## string_xrefs

- `0x14004e7ae`: `ImpersonateUser - Cannot impersoante, not running as SYSTEM.`
- `0x14004e7fc`: `ImpersonateUser - GetUserTokenFromSid() failed - Error 0x%1!x!`
- `0x14004e76e`: `ImpersonateUser - a valid SID must be specified`
- `0x14004e795`: `ImpersonateUser - IsRunningInSystemContext() failed - Error 0x%1!x!`
- `0x14004e853`: `ImpersonateUser - Failed to get an linked token :0x%1!x!`
- `0x14004e88c`: `ImpersonateUser - Failed to impersonate - Error 0x%1!x!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  std::wstring::~wstring(a1);
  return v8;
}

```

## disassembly

```asm
0x14004e740  mov     [rsp-28h+arg_18], rbx
0x14004e745  push    rbp
0x14004e746  push    rsi
0x14004e747  push    rdi
0x14004e748  push    r14
0x14004e74a  push    r15
0x14004e74c  mov     rbp, rsp
0x14004e74f  sub     rsp, 50h
0x14004e753  cmp     qword ptr [rcx+10h], 0
0x14004e758  mov     r15, r8
0x14004e75b  mov     esi, edx
0x14004e75d  mov     [rbp+var_20], 0
0x14004e761  mov     rdi, rcx
0x14004e764  mov     [rbp+TokenHandle], 0
0x14004e76c  jnz     short loc_14004E786
0x14004e76e  lea     rcx, aImpersonateuse_1; "ImpersonateUser - a valid SID must be s"...
0x14004e775  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e77a  mov     edx, 24Ch
0x14004e77f  mov     ebx, 80070057h
0x14004e784  jmp     short loc_14004E7C4
0x14004e786  lea     rcx, [rbp+var_20]; bool *
0x14004e78a  call    ?IsRunningInSystemContext@@YAJAEA_N@Z; IsRunningInSystemContext(bool &)
0x14004e78f  mov     ebx, eax
0x14004e791  test    eax, eax
0x14004e793  jns     short loc_14004E7A8
0x14004e795  lea     rcx, aImpersonateuse_0; "ImpersonateUser - IsRunningInSystemCont"...
0x14004e79c  mov     edx, eax
0x14004e79e  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e7a3  jmp     loc_14004E8AD
0x14004e7a8  cmp     [rbp+var_20], 0
0x14004e7ac  jnz     short loc_14004E7DC
0x14004e7ae  lea     rcx, aImpersonateuse; "ImpersonateUser - Cannot impersoante, n"...
0x14004e7b5  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e7ba  mov     edx, 257h; void *
0x14004e7bf  mov     ebx, 80004005h
0x14004e7c4  mov     rcx, [rbp+28h]; this
0x14004e7c8  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004e7cf  mov     r9d, ebx; char *
0x14004e7d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004e7d7  jmp     loc_14004E8AD
0x14004e7dc  cmp     qword ptr [rdi+18h], 7
0x14004e7e1  jbe     short loc_14004E7E8
0x14004e7e3  mov     rcx, [rdi]
0x14004e7e6  jmp     short loc_14004E7EB
0x14004e7e8  mov     rcx, rdi; unsigned __int16 *
0x14004e7eb  lea     r8, [rbp+TokenHandle]; void **
0x14004e7ef  mov     edx, esi; unsigned int
0x14004e7f1  call    ?GetUserTokenFromSid@@YAJPEBGKPEAPEAX@Z; GetUserTokenFromSid(ushort const *,ulong,void * *)
0x14004e7f6  mov     ebx, eax
0x14004e7f8  test    eax, eax
0x14004e7fa  jns     short loc_14004E805
0x14004e7fc  lea     rcx, aImpersonateuse_3; "ImpersonateUser - GetUserTokenFromSid()"...
0x14004e803  jmp     short loc_14004E79C
0x14004e805  mov     rsi, [rbp+TokenHandle]
0x14004e809  lea     rax, [rbp+var_1C]
0x14004e80d  mov     r9d, 8; TokenInformationLength
0x14004e813  mov     [rbp+var_1C], 0
0x14004e81a  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14004e81e  mov     [rbp+TokenInformation], 0
0x14004e826  mov     rcx, rsi; TokenHandle
0x14004e829  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x14004e82e  lea     edx, [r9+0Bh]; TokenInformationClass
0x14004e832  call    cs:__imp_GetTokenInformation
0x14004e838  mov     r14d, eax
0x14004e83b  test    eax, eax
0x14004e83d  jnz     short loc_14004E861
0x14004e83f  call    cs:__imp_GetLastError
0x14004e845  test    eax, eax
0x14004e847  jle     short loc_14004E851
0x14004e849  movzx   eax, ax
0x14004e84c  or      eax, 80070000h
0x14004e851  mov     edx, eax
0x14004e853  lea     rcx, aImpersonateuse_2; "ImpersonateUser - Failed to get an link"...
0x14004e85a  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e85f  jmp     short loc_14004E865
0x14004e861  mov     rsi, [rbp+TokenInformation]
0x14004e865  mov     rcx, rsi; hToken
0x14004e868  call    cs:__imp_ImpersonateLoggedOnUser
0x14004e86e  test    eax, eax
0x14004e870  jz      short loc_14004E878
0x14004e872  mov     byte ptr [r15], 1
0x14004e876  jmp     short loc_14004E89E
0x14004e878  call    cs:__imp_GetLastError
0x14004e87e  test    eax, eax
0x14004e880  jle     short loc_14004E88A
0x14004e882  movzx   eax, ax
0x14004e885  or      eax, 80070000h
0x14004e88a  mov     edx, eax
0x14004e88c  lea     rcx, aImpersonateuse_4; "ImpersonateUser - Failed to impersonate"...
0x14004e893  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e898  call    cs:__imp_GetLastError
0x14004e89e  test    r14d, r14d
0x14004e8a1  jz      short loc_14004E8AD
0x14004e8a3  mov     rcx, [rbp+TokenInformation]; hObject
0x14004e8a7  call    cs:__imp_CloseHandle
0x14004e8ad  mov     rcx, rdi
0x14004e8b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004e8b5  mov     eax, ebx
0x14004e8b7  mov     rbx, [rsp+50h+arg_18]
0x14004e8bf  add     rsp, 50h
0x14004e8c3  pop     r15
0x14004e8c5  pop     r14
0x14004e8c7  pop     rdi
0x14004e8c8  pop     rsi
0x14004e8c9  pop     rbp
0x14004e8ca  retn
```
