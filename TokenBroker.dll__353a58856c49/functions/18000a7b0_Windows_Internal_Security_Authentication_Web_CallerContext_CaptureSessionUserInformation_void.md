# Windows::Internal::Security::Authentication::Web::CallerContext::CaptureSessionUserInformation(void)

- ea: `0x18000a7b0`
- end: `0x18000ac81`
- name: `?CaptureSessionUserInformation@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJXZ`
- size: `1233`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::Web::CallerContext *__hidden this)`
- caller_count: `5`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020268`
- `0x1800228e0`
- `0x180064ebc`
- `0x180065dc0`
- `0x18009e750`

## callees

- `0x18000a7b0`
- `0x18000bd40`
- `0x18000e350`
- `0x180040790`
- `0x1800565a0`
- `0x18007c0f0`
- `0x18008e690`
- `0x180090434`
- `0x1800e55e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a88d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a88d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a833`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a833`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a7f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a7f4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a933`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000aa03`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000aac5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000abcb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a933`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000aa03`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000aac5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000abcb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a80c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a80c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a999`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a999`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000a975`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000a975`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a90f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a9df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ab4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a90f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a9df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ab4f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a8a7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a8a7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x18000ac0d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x18000ac0d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18000a85f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18000a85f`

## string_xrefs

- `0x18000aaa5`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000ab76`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000ab99`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000ac2c`: `onecore\ds\security\tokenbroker\callercontext\lib\wamcallercontext.cpp`
- `0x18000aa2e`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x18000aa44`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x18000aa5a`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x18000aa8d`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x18000aaec`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x18000abf0`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CallerContext::CaptureSessionUserInformation(
        Windows::Internal::Security::Authentication::Web::CallerContext *this)
{
  void **v1; // r14
  HRESULT LastErrorMsg; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const char *v6; // r9
  ULONG v7; // ebx
  HSTRING v8; // rbx
  unsigned __int64 v9; // rdx
  const char *v10; // r9
  void *v11; // rcx
  char *v13; // rbx
  char *v14; // rcx
  const char *v15; // r9
  signed int v16; // eax
  unsigned int v17; // ebx
  const char *v18; // r9
  signed int v19; // eax
  unsigned int v20; // ebx
  void *v21; // rcx
  signed int v22; // eax
  const char *v23; // r9
  const char *ReturnLength; // [rsp+20h] [rbp-89h]
  int ReturnLengthb; // [rsp+20h] [rbp-89h]
  int ReturnLengtha; // [rsp+20h] [rbp-89h]
  char *v27; // [rsp+28h] [rbp-81h]
  void *phToken; // [rsp+30h] [rbp-79h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-71h] BYREF
  char v30; // [rsp+40h] [rbp-69h]
  LPWSTR StringSid; // [rsp+48h] [rbp-61h] BYREF
  DWORD v32; // [rsp+50h] [rbp-59h] BYREF
  HSTRING string; // [rsp+58h] [rbp-51h] BYREF
  PSID TokenInformation[12]; // [rsp+60h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v1 = (void **)((char *)this + 288);
  LastErrorMsg = 0;
  if ( *((_QWORD *)this + 36) )
    return (unsigned int)LastErrorMsg;
  v30 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
    goto LABEL_6;
  v16 = GetLastError();
  v17 = v16;
  if ( v16 > 0 )
    v17 = (unsigned __int16)v16 | 0x80070000;
  if ( (v17 & 0x80000000) == 0 )
  {
LABEL_6:
    if ( !RevertToSelf() )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x1E6,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
        v6);
    v7 = *((_DWORD *)this + 6);
    v30 = 1;
    phToken = 0;
    if ( (unsigned __int8)IsWTSQueryUserTokenPresent() )
    {
      if ( !WTSQueryUserToken(v7, &phToken) )
      {
        LODWORD(ReturnLength) = v7;
        LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                         retaddr,
                         (void *)0x17,
                         (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
                         "%d",
                         ReturnLength);
        if ( LastErrorMsg < 0 )
        {
LABEL_65:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
            (const char *)(unsigned int)LastErrorMsg,
            ReturnLengtha);
          if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(phToken);
          if ( v30 && !SetThreadToken(0, TokenHandle) )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0x1DE,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
              v23);
          v11 = TokenHandle;
          if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
            return (unsigned int)LastErrorMsg;
          goto LABEL_41;
        }
      }
    }
    else
    {
      LastErrorMsg = UMgrQuerySessionUserToken(v7, &phToken);
      if ( LastErrorMsg < 0 )
      {
        LODWORD(v27) = v7;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1B,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
          (const char *)(unsigned int)LastErrorMsg,
          (int)"%d",
          v27);
        goto LABEL_65;
      }
    }
    v32 = 0;
    if ( GetTokenInformation(phToken, TokenUser, TokenInformation, 0x54u, &v32) )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
      {
        if ( StringSid )
        {
          v8 = 0;
          string = 0;
          v9 = -1;
          do
            ++v9;
          while ( StringSid[v9] );
          if ( v9 <= 0xFFFFFFFF )
          {
            LastErrorMsg = WindowsCreateString(StringSid, v9, &string);
            if ( LastErrorMsg >= 0 )
            {
              v8 = string;
              WindowsDeleteString(0);
            }
          }
          else
          {
            LastErrorMsg = -2147024362;
          }
          if ( LastErrorMsg >= 0 )
          {
            WindowsDeleteString(*((HSTRING *)this + 4));
            *((_QWORD *)this + 4) = v8;
            v13 = (char *)*v1;
            *v1 = 0;
            if ( v1 == &phToken )
            {
              v14 = (char *)phToken;
            }
            else
            {
              v14 = 0;
              *v1 = phToken;
              phToken = 0;
            }
            if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v14);
            phToken = v13;
            if ( StringSid )
            {
              LocalFree(StringSid);
              v13 = (char *)phToken;
            }
            if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v13);
            if ( v30 )
            {
              if ( !SetThreadToken(0, TokenHandle) )
                wil::details::in1diag3::_FailFast_GetLastError(
                  retaddr,
                  (void *)0x1DE,
                  (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
                  v15);
            }
            v11 = TokenHandle;
            if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
              return (unsigned int)LastErrorMsg;
            goto LABEL_41;
          }
          if ( v8 )
            WindowsDeleteString(v8);
        }
        else
        {
          LastErrorMsg = -2147467261;
        }
        if ( StringSid )
          LocalFree(StringSid);
        if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(phToken);
        if ( v30 && !SetThreadToken(0, TokenHandle) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x1DE,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
            v10);
        v11 = TokenHandle;
        if ( (char *)TokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
          return (unsigned int)LastErrorMsg;
LABEL_41:
        CloseHandle(v11);
        return (unsigned int)LastErrorMsg;
      }
      v22 = GetLastError();
      v20 = v22;
      if ( v22 > 0 )
        v20 = (unsigned __int16)v22 | 0x80070000;
      if ( StringSid )
        LocalFree(StringSid);
      v21 = phToken;
      if ( (char *)phToken - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      {
LABEL_57:
        Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&TokenHandle);
        return v20;
      }
    }
    else
    {
      v19 = GetLastError();
      v20 = v19;
      if ( v19 > 0 )
        v20 = (unsigned __int16)v19 | 0x80070000;
      v21 = phToken;
      if ( (char *)phToken - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        goto LABEL_57;
    }
    CloseHandle(v21);
    goto LABEL_57;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E5,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
    (const char *)v17,
    (int)ReturnLength);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x38,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\callercontext\\lib\\wamcallercontext.cpp",
    (const char *)v17,
    ReturnLengthb);
  if ( v30 && !SetThreadToken(0, TokenHandle) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
      v18);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return v17;
}

```

## disassembly

```asm
0x18000a7b0  push    rbp
0x18000a7b2  push    rbx
0x18000a7b3  push    rsi
0x18000a7b4  push    rdi
0x18000a7b5  push    r14
0x18000a7b7  push    r15
0x18000a7b9  lea     rbp, [rsp-2Fh]
0x18000a7be  sub     rsp, 0D8h
0x18000a7c5  mov     rax, cs:__security_cookie
0x18000a7cc  xor     rax, rsp
0x18000a7cf  mov     [rbp+57h+var_40], rax
0x18000a7d3  xor     r15d, r15d
0x18000a7d6  lea     r14, [rcx+120h]
0x18000a7dd  mov     edi, r15d
0x18000a7e0  mov     rsi, rcx
0x18000a7e3  cmp     [r14], rdi
0x18000a7e6  jnz     loc_18000A953
0x18000a7ec  mov     [rbp+57h+var_C0], dil
0x18000a7f0  mov     [rbp+57h+TokenHandle], r15
0x18000a7f4  call    cs:__imp_GetCurrentThread
0x18000a7fa  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000a7fe  mov     edx, 0F01FFh; DesiredAccess
0x18000a803  mov     rcx, rax; ThreadHandle
0x18000a806  mov     r8d, 1; OpenAsSelf
0x18000a80c  call    cs:__imp_OpenThreadToken
0x18000a812  test    eax, eax
0x18000a814  jnz     short loc_18000A833
0x18000a816  call    cs:__imp_GetLastError
0x18000a81c  test    eax, eax
0x18000a81e  jle     short loc_18000A828
0x18000a820  movzx   eax, ax
0x18000a823  or      eax, 80070000h
0x18000a828  cmp     eax, 800703F0h
0x18000a82d  jnz     loc_18000AA6C
0x18000a833  call    cs:__imp_RevertToSelf
0x18000a839  test    eax, eax
0x18000a83b  jz      loc_18000AA2A
0x18000a841  mov     ebx, [rsi+18h]
0x18000a844  mov     [rbp+57h+var_C0], 1
0x18000a848  mov     [rbp+57h+phToken], r15
0x18000a84c  call    IsWTSQueryUserTokenPresent
0x18000a851  lea     rdx, [rbp+57h+phToken]; phToken
0x18000a855  mov     ecx, ebx; SessionId
0x18000a857  test    al, al
0x18000a859  jz      loc_18000AC0D
0x18000a85f  call    cs:__imp_WTSQueryUserToken
0x18000a865  test    eax, eax
0x18000a867  jz      loc_18000AB6B
0x18000a86d  mov     rcx, [rbp+57h+phToken]; TokenHandle
0x18000a871  lea     rax, [rbp+57h+var_B0]
0x18000a875  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000a87b  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18000a880  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000a884  mov     [rbp+57h+var_B0], r15d
0x18000a888  mov     edx, 1; TokenInformationClass
0x18000a88d  call    cs:__imp_GetTokenInformation
0x18000a893  test    eax, eax
0x18000a895  jz      loc_18000AAFE
0x18000a89b  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x18000a89f  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18000a8a3  mov     [rbp+57h+StringSid], r15
0x18000a8a7  call    cs:__imp_ConvertSidToStringSidW
0x18000a8ad  test    eax, eax
0x18000a8af  jz      loc_18000AB31
0x18000a8b5  mov     rcx, [rbp+57h+StringSid]; sourceString
0x18000a8b9  test    rcx, rcx
0x18000a8bc  jz      short loc_18000A8F1
0x18000a8be  mov     rbx, r15
0x18000a8c1  mov     [rbp+57h+string], r15
0x18000a8c5  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000a8cc  nop     dword ptr [rax+00h]
0x18000a8d0  inc     rdx; length
0x18000a8d3  cmp     [rcx+rdx*2], bx
0x18000a8d7  jnz     short loc_18000A8D0
0x18000a8d9  mov     eax, 0FFFFFFFFh
0x18000a8de  cmp     rdx, rax
0x18000a8e1  jbe     loc_18000A971
0x18000a8e7  mov     edi, 80070216h
0x18000a8ec  jmp     loc_18000A98D
0x18000a8f1  mov     edi, 80004003h
0x18000a8f6  jmp     short loc_18000A906
0x18000a8f8  test    rbx, rbx
0x18000a8fb  jz      short loc_18000A906
0x18000a8fd  mov     rcx, rbx; string
0x18000a900  call    cs:__imp_WindowsDeleteString
0x18000a906  mov     rcx, [rbp+57h+StringSid]; hMem
0x18000a90a  test    rcx, rcx
0x18000a90d  jz      short loc_18000A915
0x18000a90f  call    cs:__imp_LocalFree
0x18000a915  mov     rcx, [rbp+57h+phToken]; hObject
0x18000a919  lea     rax, [rcx-1]
0x18000a91d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a921  jbe     loc_18000AC76
0x18000a927  cmp     [rbp+57h+var_C0], r15b
0x18000a92b  jz      short loc_18000A941
0x18000a92d  mov     rdx, [rbp+57h+TokenHandle]; Token
0x18000a931  xor     ecx, ecx; Thread
0x18000a933  call    cs:__imp_SetThreadToken
0x18000a939  test    eax, eax
0x18000a93b  jz      loc_18000AA40
0x18000a941  mov     rcx, [rbp+57h+TokenHandle]
0x18000a945  lea     rdx, [rcx-1]
0x18000a949  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000a94d  jbe     loc_18000AA1F
0x18000a953  mov     eax, edi
0x18000a955  mov     rcx, [rbp+57h+var_40]
0x18000a959  xor     rcx, rsp; StackCookie
0x18000a95c  call    __security_check_cookie
0x18000a961  add     rsp, 0D8h
0x18000a968  pop     r15
0x18000a96a  pop     r14
0x18000a96c  pop     rdi
0x18000a96d  pop     rsi
0x18000a96e  pop     rbx
0x18000a96f  pop     rbp
0x18000a970  retn
0x18000a971  lea     r8, [rbp+57h+string]; string
0x18000a975  call    cs:__imp_WindowsCreateString
0x18000a97b  mov     edi, eax
0x18000a97d  test    eax, eax
0x18000a97f  js      short loc_18000A98D
0x18000a981  mov     rbx, [rbp+57h+string]
0x18000a985  xor     ecx, ecx; string
0x18000a987  call    cs:__imp_WindowsDeleteString
0x18000a98d  test    edi, edi
0x18000a98f  js      loc_18000A8F8
0x18000a995  mov     rcx, [rsi+20h]; string
0x18000a999  call    cs:__imp_WindowsDeleteString
0x18000a99f  mov     [rsi+20h], rbx
0x18000a9a3  lea     rax, [rbp+57h+phToken]
0x18000a9a7  mov     rbx, [r14]
0x18000a9aa  mov     [r14], r15
0x18000a9ad  cmp     r14, rax
0x18000a9b0  jz      loc_18000AC55
0x18000a9b6  mov     rax, [rbp+57h+phToken]
0x18000a9ba  mov     rcx, r15; hObject
0x18000a9bd  mov     [r14], rax
0x18000a9c0  mov     [rbp+57h+phToken], rcx
0x18000a9c4  lea     rax, [rcx-1]
0x18000a9c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a9cc  jbe     loc_18000AC5E
0x18000a9d2  mov     rcx, [rbp+57h+StringSid]; hMem
0x18000a9d6  mov     [rbp+57h+phToken], rbx
0x18000a9da  test    rcx, rcx
0x18000a9dd  jz      short loc_18000A9E9
0x18000a9df  call    cs:__imp_LocalFree
0x18000a9e5  mov     rbx, [rbp+57h+phToken]
0x18000a9e9  lea     rax, [rbx-1]
0x18000a9ed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a9f1  jbe     loc_18000AC68
0x18000a9f7  cmp     [rbp+57h+var_C0], r15b
0x18000a9fb  jz      short loc_18000AA0D
0x18000a9fd  mov     rdx, [rbp+57h+TokenHandle]; Token
0x18000aa01  xor     ecx, ecx; Thread
0x18000aa03  call    cs:__imp_SetThreadToken
0x18000aa09  test    eax, eax
0x18000aa0b  jz      short loc_18000AA56
0x18000aa0d  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000aa11  lea     rax, [rcx-1]
0x18000aa15  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000aa19  ja      loc_18000A953
0x18000aa1f  call    cs:__imp_CloseHandle
0x18000aa25  jmp     loc_18000A953
0x18000aa2a  mov     rcx, [rbp+5Fh]; this
0x18000aa2e  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x18000aa35  mov     edx, 1E6h; void *
0x18000aa3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aa40  mov     rcx, [rbp+5Fh]; this
0x18000aa44  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x18000aa4b  mov     edx, 1DEh; void *
0x18000aa50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aa56  mov     rcx, [rbp+5Fh]; this
0x18000aa5a  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x18000aa61  mov     edx, 1DEh; void *
0x18000aa66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aa6c  call    cs:__imp_GetLastError
0x18000aa72  mov     ebx, eax
0x18000aa74  test    eax, eax
0x18000aa76  jle     short loc_18000AA81
0x18000aa78  movzx   ebx, ax
0x18000aa7b  or      ebx, 80070000h
0x18000aa81  test    ebx, ebx
0x18000aa83  jns     loc_18000A833
0x18000aa89  mov     rcx, [rbp+5Fh]; this
0x18000aa8d  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x18000aa94  mov     r9d, ebx; char *
0x18000aa97  mov     edx, 1E5h; void *
0x18000aa9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aaa1  mov     rcx, [rbp+5Fh]; this
0x18000aaa5  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\tokenbroker\\cal"...
0x18000aaac  mov     r9d, ebx; char *
0x18000aaaf  mov     edx, 38h ; '8'; void *
0x18000aab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aab9  cmp     [rbp+57h+var_C0], dil
0x18000aabd  jz      short loc_18000AACF
0x18000aabf  mov     rdx, [rbp+57h+TokenHandle]; Token
0x18000aac3  xor     ecx, ecx; Thread
0x18000aac5  call    cs:__imp_SetThreadToken
0x18000aacb  test    eax, eax
0x18000aacd  jz      short loc_18000AAE8
0x18000aacf  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18000aad3  lea     rdx, [rcx-1]
0x18000aad7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000aadb  jbe     loc_18000AC02
0x18000aae1  mov     eax, ebx
0x18000aae3  jmp     loc_18000A955
0x18000aae8  mov     rcx, [rbp+5Fh]; this
0x18000aaec  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x18000aaf3  mov     edx, 1DEh; void *
0x18000aaf8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aafe  call    cs:__imp_GetLastError
0x18000ab04  mov     ebx, eax
0x18000ab06  test    eax, eax
0x18000ab08  jle     short loc_18000AB13
0x18000ab0a  movzx   ebx, ax
0x18000ab0d  or      ebx, 80070000h
0x18000ab13  mov     rcx, [rbp+57h+phToken]
0x18000ab17  lea     rdx, [rcx-1]
0x18000ab1b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000ab1f  jbe     short loc_18000AB63
0x18000ab21  lea     rcx, [rbp+57h+TokenHandle]; this
0x18000ab25  call    ??1SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x18000ab2a  mov     eax, ebx
0x18000ab2c  jmp     loc_18000A955
0x18000ab31  call    cs:__imp_GetLastError
0x18000ab37  mov     ebx, eax
0x18000ab39  test    eax, eax
0x18000ab3b  jle     short loc_18000AB46
0x18000ab3d  movzx   ebx, ax
0x18000ab40  or      ebx, 80070000h
0x18000ab46  mov     rcx, [rbp+57h+StringSid]; hMem
0x18000ab4a  test    rcx, rcx
0x18000ab4d  jz      short loc_18000AB55
0x18000ab4f  call    cs:__imp_LocalFree
0x18000ab55  mov     rcx, [rbp+57h+phToken]; hObject
0x18000ab59  lea     rdx, [rcx-1]
0x18000ab5d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000ab61  ja      short loc_18000AB21
0x18000ab63  call    cs:__imp_CloseHandle
0x18000ab69  jmp     short loc_18000AB21
0x18000ab6b  mov     rcx, [rbp+5Fh]; this
0x18000ab6f  lea     r9, aD; "%d"
0x18000ab76  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\tokenbroker\\cal"...
0x18000ab7d  mov     dword ptr [rsp+100h+ReturnLength], ebx; int
0x18000ab81  mov     edx, 17h; void *
0x18000ab86  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18000ab8b  mov     edi, eax
0x18000ab8d  test    eax, eax
0x18000ab8f  jns     loc_18000A86D
0x18000ab95  mov     rcx, [rbp+5Fh]; this
0x18000ab99  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\tokenbroker\\cal"...
0x18000aba0  mov     r9d, edi; char *
0x18000aba3  mov     edx, 3Ch ; '<'; void *
0x18000aba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000abad  mov     rcx, [rbp+57h+phToken]; hObject
0x18000abb1  lea     rax, [rcx-1]
0x18000abb5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000abb9  jbe     loc_18000AC4A
0x18000abbf  cmp     [rbp+57h+var_C0], r15b
0x18000abc3  jz      short loc_18000ABD5
0x18000abc5  mov     rdx, [rbp+57h+TokenHandle]; Token
0x18000abc9  xor     ecx, ecx; Thread
0x18000abcb  call    cs:__imp_SetThreadToken
0x18000abd1  test    eax, eax
0x18000abd3  jz      short loc_18000ABEC
0x18000abd5  mov     rcx, [rbp+57h+TokenHandle]
0x18000abd9  lea     rdx, [rcx-1]
0x18000abdd  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000abe1  ja      loc_18000A953
0x18000abe7  jmp     loc_18000AA1F
0x18000abec  mov     rcx, [rbp+5Fh]; this
0x18000abf0  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x18000abf7  mov     edx, 1DEh; void *
0x18000abfc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ac02  call    cs:__imp_CloseHandle
0x18000ac08  jmp     loc_18000AAE1
0x18000ac0d  call    cs:__imp_UMgrQuerySessionUserToken
0x18000ac13  mov     edi, eax
0x18000ac15  test    eax, eax
0x18000ac17  jns     loc_18000A86D
0x18000ac1d  mov     rcx, [rbp+5Fh]; this
0x18000ac21  lea     rax, aD; "%d"
0x18000ac28  mov     dword ptr [rsp+100h+var_D8], ebx; char *
0x18000ac2c  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\tokenbroker\\cal"...
0x18000ac33  mov     r9d, edi; char *
0x18000ac36  mov     [rsp+100h+ReturnLength], rax; int
0x18000ac3b  mov     edx, 1Bh; void *
0x18000ac40  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000ac45  jmp     loc_18000AB95
0x18000ac4a  call    cs:__imp_CloseHandle
0x18000ac50  jmp     loc_18000ABBF
0x18000ac55  mov     rcx, [rbp+57h+phToken]
0x18000ac59  jmp     loc_18000A9C4
0x18000ac5e  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000ac63  jmp     loc_18000A9D2
0x18000ac68  mov     rcx, rbx; hObject
0x18000ac6b  call    cs:__imp_CloseHandle
0x18000ac71  jmp     loc_18000A9F7
0x18000ac76  call    cs:__imp_CloseHandle
0x18000ac7c  jmp     loc_18000A927
  ... truncated ...
```
