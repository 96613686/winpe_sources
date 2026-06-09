# CDplUser::CheckCaller(void)

- ea: `0x1800ac870`
- end: `0x1800acb04`
- name: `?CheckCaller@CDplUser@@AEAAJXZ`
- size: `660`
- prototype: `__int64 __fastcall(PSID *this)`
- caller_count: `10`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800895e8`
- `0x18008b678`
- `0x180090228`
- `0x180092240`
- `0x1800928fc`
- `0x1800a8660`
- `0x1800aa5a4`
- `0x1800ad2d0`
- `0x1800b4c78`
- `0x1800bc65c`

## callees

- `0x18003bf9c`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800ac870`
- `0x1800d43e8`
- `0x1800d4510`
- `0x1800d45bc`
- `0x1800d5af8`
- `0x1800d6064`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac8db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aca45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac8db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aca45`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ac8d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ac8d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ac8bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ac8bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac95c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acaaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac95c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800acaaa`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800aca6e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800aca6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ac983`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800aca3b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ac983`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800aca3b`

## pseudocode

```c
__int64 __fastcall CDplUser::CheckCaller(PSID *this)
{
  PSID *v1; // rdi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  int v6; // r8d
  void *v7; // rcx
  int v8; // ecx
  signed int v9; // eax
  int v10; // eax
  signed int v11; // eax
  char ReturnLength; // [rsp+20h] [rbp-40h]
  DWORD v14; // [rsp+40h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-18h] BYREF
  LPVOID TokenInformation[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+98h] [rbp+38h] BYREF
  void *NewTokenHandle; // [rsp+A0h] [rbp+40h] BYREF
  int v19; // [rsp+A8h] [rbp+48h]

  v1 = 0;
  TokenHandle = 0;
  v14 = 0;
  TokenInformation[0] = 0;
  TokenInformationLength = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 107);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    ReturnLength = 114;
LABEL_5:
    v6 = v5;
    goto LABEL_28;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::GetImpl'::`2'::impl)
    && (unsigned int)LUAIsShadowAdminEnabled()
    && (v19 = 0, LODWORD(NewTokenHandle) = 0, !(unsigned int)LUAIsElevatedToken(TokenHandle))
    && (_DWORD)NewTokenHandle
    && v19
    && (NewTokenHandle = 0, !(unsigned int)LUAGetStandardToken(TokenHandle, &NewTokenHandle)) )
  {
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    v7 = NewTokenHandle;
    TokenHandle = NewTokenHandle;
  }
  else
  {
    v7 = TokenHandle;
  }
  if ( !GetTokenInformation(v7, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    ReturnLength = -105;
    goto LABEL_5;
  }
  fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 159);
  v5 = DplibpMemAllocEx(TokenInformationLength, 0, 0, TokenInformation);
  v10 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          v5,
          40,
          159);
  v1 = (PSID *)TokenInformation[0];
  if ( v10 < 0 )
    goto LABEL_29;
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation[0], TokenInformationLength, &v14) )
  {
    v11 = GetLastError();
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    ReturnLength = -89;
    goto LABEL_5;
  }
  if ( EqualSid(this[14], *v1) )
    goto LABEL_29;
  v5 = -2147024891;
  ReturnLength = -84;
  v6 = -2147024891;
LABEL_28:
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 40, ReturnLength);
LABEL_29:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v1 )
    DplibMemFree(v1);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v5,
    40,
    185);
  return v5;
}

```

## disassembly

```asm
0x1800ac870  push    rbp
0x1800ac872  push    rbx
0x1800ac873  push    rsi
0x1800ac874  push    rdi
0x1800ac875  push    r15
0x1800ac877  mov     rbp, rsp
0x1800ac87a  sub     rsp, 60h
0x1800ac87e  xor     edi, edi
0x1800ac880  mov     [rbp+TokenHandle], 0
0x1800ac888  lea     r8, sourceString
0x1800ac88f  mov     [rbp+var_20], 0
0x1800ac896  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800ac89d  mov     [rbp+TokenInformation], rdi
0x1800ac8a1  mov     rsi, rcx
0x1800ac8a4  mov     [rbp+TokenInformationLength], edi
0x1800ac8a7  lea     r15d, [rdi+28h]
0x1800ac8ab  mov     dword ptr [rsp+60h+ReturnLength], 216Bh
0x1800ac8b3  mov     r9d, r15d
0x1800ac8b6  call    fnEfsLogTrace1Strings
0x1800ac8bb  call    cs:__imp_GetCurrentThread
0x1800ac8c1  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ac8c5  mov     edx, 20008h; DesiredAccess
0x1800ac8ca  mov     rcx, rax; ThreadHandle
0x1800ac8cd  lea     r8d, [rdi+1]; OpenAsSelf
0x1800ac8d1  call    cs:__imp_OpenThreadToken
0x1800ac8d7  test    eax, eax
0x1800ac8d9  jnz     short loc_1800AC900
0x1800ac8db  call    cs:__imp_GetLastError
0x1800ac8e1  mov     ebx, eax
0x1800ac8e3  test    eax, eax
0x1800ac8e5  jle     short loc_1800AC8F0
0x1800ac8e7  movzx   ebx, ax
0x1800ac8ea  or      ebx, 80070000h
0x1800ac8f0  mov     dword ptr [rsp+60h+ReturnLength], 2172h
0x1800ac8f8  mov     r8d, ebx
0x1800ac8fb  jmp     loc_1800ACA8B
0x1800ac900  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::GetImpl(void)'::`2'::impl
0x1800ac907  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::__private_IsEnabled(void)
0x1800ac90c  test    al, al
0x1800ac90e  jz      short loc_1800AC96C
0x1800ac910  call    LUAIsShadowAdminEnabled
0x1800ac915  test    eax, eax
0x1800ac917  jz      short loc_1800AC96C
0x1800ac919  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ac91d  lea     r8, [rbp+arg_18]
0x1800ac921  lea     rdx, [rbp+NewTokenHandle]
0x1800ac925  mov     [rbp+arg_18], edi
0x1800ac928  mov     dword ptr [rbp+NewTokenHandle], edi
0x1800ac92b  call    LUAIsElevatedToken
0x1800ac930  test    eax, eax
0x1800ac932  jnz     short loc_1800AC96C
0x1800ac934  cmp     dword ptr [rbp+NewTokenHandle], edi
0x1800ac937  jz      short loc_1800AC96C
0x1800ac939  cmp     [rbp+arg_18], edi
0x1800ac93c  jz      short loc_1800AC96C
0x1800ac93e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ac942  lea     rdx, [rbp+NewTokenHandle]; NewTokenHandle
0x1800ac946  mov     [rbp+NewTokenHandle], rdi
0x1800ac94a  call    LUAGetStandardToken
0x1800ac94f  test    eax, eax
0x1800ac951  jnz     short loc_1800AC96C
0x1800ac953  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ac957  test    rcx, rcx
0x1800ac95a  jz      short loc_1800AC962
0x1800ac95c  call    cs:__imp_CloseHandle
0x1800ac962  mov     rcx, [rbp+NewTokenHandle]
0x1800ac966  mov     [rbp+TokenHandle], rcx
0x1800ac96a  jmp     short loc_1800AC970
0x1800ac96c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ac970  xor     r9d, r9d; TokenInformationLength
0x1800ac973  lea     rax, [rbp+TokenInformationLength]
0x1800ac977  xor     r8d, r8d; TokenInformation
0x1800ac97a  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800ac97f  lea     edx, [r9+1]; TokenInformationClass
0x1800ac983  call    cs:__imp_GetTokenInformation
0x1800ac989  test    eax, eax
0x1800ac98b  jnz     short loc_1800AC9BA
0x1800ac98d  call    cs:__imp_GetLastError
0x1800ac993  cmp     eax, 7Ah ; 'z'
0x1800ac996  jz      short loc_1800AC9BA
0x1800ac998  call    cs:__imp_GetLastError
0x1800ac99e  mov     ebx, eax
0x1800ac9a0  test    eax, eax
0x1800ac9a2  jle     short loc_1800AC9AD
0x1800ac9a4  movzx   ebx, ax
0x1800ac9a7  or      ebx, 80070000h
0x1800ac9ad  mov     dword ptr [rsp+60h+ReturnLength], 2197h
0x1800ac9b5  jmp     loc_1800AC8F8
0x1800ac9ba  mov     edi, 219Fh
0x1800ac9bf  lea     r8, sourceString
0x1800ac9c6  mov     r9d, r15d
0x1800ac9c9  mov     dword ptr [rsp+60h+ReturnLength], edi
0x1800ac9cd  lea     rdx, EFS_TRACE_START_EVENT
0x1800ac9d4  call    fnEfsLogTrace1Strings
0x1800ac9d9  mov     ecx, [rbp+TokenInformationLength]
0x1800ac9dc  lea     r9, [rbp+TokenInformation]
0x1800ac9e0  xor     r8d, r8d
0x1800ac9e3  xor     edx, edx
0x1800ac9e5  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800ac9ea  mov     rcx, cs:g_hPublisher
0x1800ac9f1  lea     r9, sourceString
0x1800ac9f8  mov     [rsp+60h+var_30], edi
0x1800ac9fc  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800aca03  mov     [rsp+60h+var_38], r15d
0x1800aca08  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800aca0f  mov     dword ptr [rsp+60h+ReturnLength], eax
0x1800aca13  mov     ebx, eax
0x1800aca15  call    fnEfsLogTrace1String1Dword
0x1800aca1a  mov     rdi, [rbp+TokenInformation]
0x1800aca1e  test    eax, eax
0x1800aca20  js      short loc_1800ACAA1
0x1800aca22  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800aca26  lea     rax, [rbp+var_20]
0x1800aca2a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800aca2e  mov     r8, rdi; TokenInformation
0x1800aca31  mov     edx, 1; TokenInformationClass
0x1800aca36  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800aca3b  call    cs:__imp_GetTokenInformation
0x1800aca41  test    eax, eax
0x1800aca43  jnz     short loc_1800ACA67
0x1800aca45  call    cs:__imp_GetLastError
0x1800aca4b  mov     ebx, eax
0x1800aca4d  test    eax, eax
0x1800aca4f  jle     short loc_1800ACA5A
0x1800aca51  movzx   ebx, ax
0x1800aca54  or      ebx, 80070000h
0x1800aca5a  mov     dword ptr [rsp+60h+ReturnLength], 21A7h
0x1800aca62  jmp     loc_1800AC8F8
0x1800aca67  mov     rdx, [rdi]; pSid2
0x1800aca6a  mov     rcx, [rsi+70h]; pSid1
0x1800aca6e  call    cs:__imp_EqualSid
0x1800aca74  test    eax, eax
0x1800aca76  jnz     short loc_1800ACAA1
0x1800aca78  mov     ebx, 80070005h
0x1800aca7d  mov     dword ptr [rsp+60h+ReturnLength], 21ACh
0x1800aca85  mov     r8d, 80070005h
0x1800aca8b  mov     rcx, cs:g_hPublisher
0x1800aca92  lea     rdx, EFS_TRACE_ERROR
0x1800aca99  mov     r9d, r15d
0x1800aca9c  call    fnEfsLogTrace1
0x1800acaa1  mov     rcx, [rbp+TokenHandle]; hObject
0x1800acaa5  test    rcx, rcx
0x1800acaa8  jz      short loc_1800ACAB8
0x1800acaaa  call    cs:__imp_CloseHandle
0x1800acab0  mov     [rbp+TokenHandle], 0
0x1800acab8  test    rdi, rdi
0x1800acabb  jz      short loc_1800ACAC5
0x1800acabd  mov     rcx, rdi; void *
0x1800acac0  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800acac5  mov     rcx, cs:g_hPublisher
0x1800acacc  lea     r9, sourceString
0x1800acad3  mov     [rsp+60h+var_30], 21B9h
0x1800acadb  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800acae2  mov     [rsp+60h+var_38], r15d
0x1800acae7  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800acaee  mov     dword ptr [rsp+60h+ReturnLength], ebx
0x1800acaf2  call    fnEfsLogTrace1String1Dword
0x1800acaf7  mov     eax, ebx
0x1800acaf9  add     rsp, 60h
0x1800acafd  pop     r15
0x1800acaff  pop     rdi
0x1800acb00  pop     rsi
0x1800acb01  pop     rbx
0x1800acb02  pop     rbp
0x1800acb03  retn
```
