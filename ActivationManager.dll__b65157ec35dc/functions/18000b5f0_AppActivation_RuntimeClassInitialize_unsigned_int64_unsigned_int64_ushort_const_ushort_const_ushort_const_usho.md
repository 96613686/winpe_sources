# AppActivation::RuntimeClassInitialize(unsigned __int64,unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,unsigned __int64,ACTIVATEOPTIONSINTERNAL,PACKAGEACTIVATIONSETTINGS,ActivateType,ActivateByExtensionArgs *,IUnknown *,_ActivateComponentInfo const *,EarlyReturnData *)

- ea: `0x18000b5f0`
- end: `0x18000bca7`
- name: `?RuntimeClassInitialize@AppActivation@@QEAAJ_K0PEBG111AEBU_GUID@@0W4ACTIVATEOPTIONSINTERNAL@@W4PACKAGEACTIVATIONSETTINGS@@W4ActivateType@@PEAUActivateByExtensionArgs@@PEAUIUnknown@@PEBU_ActivateComponentInfo@@PEAVEarlyReturnData@@@Z`
- size: `1719`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011ad0`
- `0x180013e68`
- `0x18004fc3c`

## callees

- `0x18000b5c0`
- `0x18000b5f0`
- `0x18000cbc0`
- `0x18000cbe4`
- `0x18000cd40`
- `0x180011328`
- `0x180015b7c`
- `0x180027ce8`
- `0x18002a380`
- `0x180031540`
- `0x180036014`
- `0x18003b578`
- `0x180044408`
- `0x180044514`
- `0x18004498c`
- `0x18005ae90`
- `0x18005b3c4`
- `0x180083a70`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bb37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000bb37`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b82a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b82a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000bb49`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000bb49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb74`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000ba8b`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000ba8b`
- `ntdll!NtQueryInformationProcess` at `0x18000b736`
- `ntdll!NtQueryInformationProcess` at `0x18000b736`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b95d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bb97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b95d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bb97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18000bbe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18000bbe5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b9b7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000b9b7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000bc64`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000bc7b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000bc64`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000bc7b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b85c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b85c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b900`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b900`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb19`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b84c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b84c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b8b0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b8b0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000b772`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000b772`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall AppActivation::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        const WCHAR *sourceString,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        __int64 a9,
        int a10,
        char a11,
        int a12,
        struct ActivateByExtensionArgs *a13,
        __int64 a14,
        struct _ActivateComponentInfo *a15,
        void *a16)
{
  __int64 v18; // r8
  __int64 v19; // rcx
  char v20; // al
  unsigned __int64 v21; // rdi
  NTSTATUS v22; // eax
  void *v23; // r12
  int v24; // eax
  int v25; // r15d
  unsigned int v27; // ebx
  HANDLE CurrentThread; // rax
  DWORD LengthSid; // r15d
  HLOCAL v30; // rax
  void *v31; // rbx
  void *v32; // rcx
  const char *v33; // r9
  void *v34; // rcx
  void *v35; // rcx
  unsigned int ActivateTimeoutLimitMs; // r15d
  HRESULT String; // eax
  unsigned int v38; // ecx
  const char *v39; // r9
  int v40; // ebx
  int v41; // eax
  int v42; // ebx
  __int64 v43; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  const char *v46; // r9
  HSTRING v47; // rbx
  HSTRING_HEADER *v48; // rax
  HRESULT v49; // eax
  HRESULT v50; // ebx
  int v51; // eax
  int ReturnLength; // [rsp+20h] [rbp-79h]
  void *TokenHandle; // [rsp+30h] [rbp-69h] BYREF
  void *Block; // [rsp+38h] [rbp-61h] BYREF
  int ProcessInformation; // [rsp+40h] [rbp-59h] BYREF
  const WCHAR *v56; // [rsp+48h] [rbp-51h] BYREF
  struct ActivateByExtensionArgs *v57; // [rsp+50h] [rbp-49h]
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-41h] BYREF
  HSTRING string2; // [rsp+70h] [rbp-29h]
  HSTRING_HEADER v60; // [rsp+78h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+3Fh]

  v56 = sourceString;
  v57 = a13;
  v18 = 0;
  if ( a15 )
  {
    v43 = *((_QWORD *)a15 + 4) - *a8;
    if ( !v43 )
      v43 = *((_QWORD *)a15 + 5) - a8[1];
    if ( v43 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x105,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        a4);
    *(_QWORD *)(a1 + 240) = *((_QWORD *)a15 + 1);
  }
  *(_QWORD *)(a1 + 64) = a2;
  *(_QWORD *)(a1 + 16) = a4;
  *(_QWORD *)(a1 + 24) = sourceString;
  *(_QWORD *)(a1 + 40) = a7;
  *(_QWORD *)(a1 + 32) = a6;
  *(_QWORD *)(a1 + 80) = a3;
  *(_DWORD *)(a1 + 100) = a10;
  if ( *(_QWORD *)(a1 + 176) != a14 )
  {
    if ( a14 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a14 + 8LL))(a14, a2, 0);
    v19 = *(_QWORD *)(a1 + 176);
    *(_QWORD *)(a1 + 176) = a14;
    if ( v19 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v19 + 16LL))(v19, a2, v18);
  }
  *(_QWORD *)(a1 + 72) = a9;
  *(_DWORD *)(a1 + 96) = a12;
  if ( (a10 & 0x200000) == 0 )
  {
    if ( dword_1800D1940 == -2147483638 )
    {
      LODWORD(TokenHandle) = 0;
      RtlGetDeviceFamilyInfoEnum(0, &TokenHandle, 0);
      if ( (_DWORD)TokenHandle != 5 && (_DWORD)TokenHandle != 11 )
      {
        dword_1800D1940 = 0;
        goto LABEL_10;
      }
      dword_1800D1940 = 1;
    }
    else if ( !dword_1800D1940 )
    {
LABEL_10:
      v20 = 1;
      goto LABEL_11;
    }
  }
  v20 = 0;
LABEL_11:
  *(_BYTE *)(a1 + 104) = v20;
  if ( *(void **)(a1 + 184) != a16 )
  {
    Block = a16;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&Block);
    Block = *(void **)(a1 + 184);
    *(_QWORD *)(a1 + 184) = a16;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&Block);
  }
  *(_OWORD *)(a1 + 48) = *(_OWORD *)a8;
  ProcessInformation = 0;
  v21 = -1;
  v22 = NtQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessSessionInformation, &ProcessInformation, 4u, 0);
  if ( v22 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x118,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
             (const char *)(unsigned int)v22,
             ReturnLength);
  *(_DWORD *)(a1 + 88) = ProcessInformation;
  v23 = *(void **)(a1 + 112);
  if ( v23 )
  {
    LastError = GetLastError();
    LocalFree(v23);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 112) = 0;
  TokenHandle = 0;
  if ( a3 )
  {
    v24 = UMgrQueryUserToken(a3, &TokenHandle);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40E,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)v24,
        ReturnLength);
LABEL_19:
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      goto LABEL_21;
    }
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        v25 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x412,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
                v46);
        goto LABEL_35;
      }
    }
  }
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, (__int64)TokenHandle);
  LengthSid = GetLengthSid(*(PSID *)Block);
  v30 = LocalAlloc(0x40u, LengthSid);
  v31 = v30;
  if ( !v30 )
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x418,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)0x8007000ELL,
      ReturnLength);
    v32 = Block;
    Block = 0;
    if ( v32 )
      operator delete(v32);
    goto LABEL_19;
  }
  if ( CopySid(LengthSid, v30, *(PSID *)Block) )
  {
    *(_QWORD *)(a1 + 112) = v31;
    v34 = Block;
    Block = 0;
    if ( v34 )
      operator delete(v34);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    goto LABEL_36;
  }
  v25 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x419,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
          v33);
  LocalFree(v31);
  v35 = Block;
  Block = 0;
  if ( v35 )
    operator delete(v35);
LABEL_35:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  if ( v25 < 0 )
  {
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v25,
      ReturnLength);
    return v25;
  }
LABEL_36:
  ActivateTimeoutLimitMs = -1;
  if ( (*(_DWORD *)(a1 + 100) & 0x2000000) == 0 )
  {
    if ( sourceString )
    {
      do
        ++v21;
      while ( sourceString[v21] );
      if ( v21 > 0xFFFFFFFF )
      {
        v27 = -2147024362;
        goto LABEL_23;
      }
      WindowsDeleteString(*(HSTRING *)(a1 + 120));
      *(_QWORD *)(a1 + 120) = 0;
      String = WindowsCreateString(sourceString, v21, (HSTRING *)(a1 + 120));
    }
    else
    {
      String = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)(a1 + 120), &Src, 0);
    }
    v27 = String;
    if ( String >= 0 )
      goto LABEL_42;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)v27,
      ReturnLength);
    return v27;
  }
  WindowsDeleteString(*(HSTRING *)(a1 + 120));
  *(_QWORD *)(a1 + 120) = 0;
  string2 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"+Prelaunch", 0xBu, 0xAu);
  v47 = string2;
  v48 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v60, &v56);
  v49 = WindowsConcatString((HSTRING)v48[1].Reserved.Reserved1, v47, (HSTRING *)(a1 + 120));
  v50 = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v49,
      ReturnLength);
    return v50;
  }
LABEL_42:
  if ( (a11 & 2) == 0 )
  {
    if ( (*(_DWORD *)(a1 + 100) & 0xA000000) != 0 )
    {
      ActivateTimeoutLimitMs = 120000;
    }
    else
    {
      ActivateTimeoutLimitMs = dword_1800D2388;
      if ( !dword_1800D2388 )
      {
        ActivateTimeoutLimitMs = GetActivateTimeoutLimitMs(v38);
        dword_1800D2388 = ActivateTimeoutLimitMs;
      }
    }
  }
  *(_DWORD *)(a1 + 92) = ActivateTimeoutLimitMs;
  LODWORD(TokenHandle) = 0;
  if ( !__std_init_once_begin_initialize(&AppActivation::s_initStoreOnce, 0, (PBOOL)&TokenHandle, 0) )
  {
    v40 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v39);
    goto LABEL_47;
  }
  if ( (_DWORD)TokenHandle )
  {
    v51 = lambda_a4e4d3ab868dca7d5316e1c70bab3b03_::operator()();
    v40 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37F,
        (unsigned int)"wil",
        (const char *)(unsigned int)v51,
        ReturnLength);
      InitOnceComplete(&AppActivation::s_initStoreOnce, 4u, 0);
      goto LABEL_47;
    }
    InitOnceComplete(&AppActivation::s_initStoreOnce, 0, 0);
  }
  v40 = 0;
LABEL_47:
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v40,
      ReturnLength);
    return v40;
  }
  else
  {
    v41 = AppActivation::PrepareExtensionForActivate((AppActivation *)a1, v57, a15);
    v42 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)v41,
        ReturnLength);
      return v42;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18000b5f0  mov     [rsp-8+arg_8], rbx
0x18000b5f5  push    rbp
0x18000b5f6  push    rsi
0x18000b5f7  push    rdi
0x18000b5f8  push    r12
0x18000b5fa  push    r13
0x18000b5fc  push    r14
0x18000b5fe  push    r15
0x18000b600  lea     rbp, [rsp-7]
0x18000b605  sub     rsp, 0A0h
0x18000b60c  mov     rax, cs:__security_cookie
0x18000b613  xor     rax, rsp
0x18000b616  mov     [rbp+37h+var_38], rax
0x18000b61a  mov     r15, r8
0x18000b61d  mov     rsi, rcx
0x18000b620  mov     r14, [rbp+37h+sourceString]
0x18000b624  mov     [rbp+37h+var_88], r14
0x18000b628  mov     rax, [rbp+37h+arg_60]
0x18000b62f  mov     [rbp+37h+var_80], rax
0x18000b633  mov     r13, [rbp+37h+arg_70]
0x18000b63a  xor     r8d, r8d
0x18000b63d  mov     r12, [rbp+37h+arg_38]
0x18000b641  test    r13, r13
0x18000b644  jnz     loc_18000BA3B
0x18000b64a  mov     [rsi+40h], rdx
0x18000b64e  mov     [rsi+10h], r9
0x18000b652  mov     [rsi+18h], r14
0x18000b656  mov     rax, [rbp+37h+arg_30]
0x18000b65a  mov     [rsi+28h], rax
0x18000b65e  mov     rax, [rbp+37h+arg_28]
0x18000b662  mov     [rsi+20h], rax
0x18000b666  mov     [rsi+50h], r15
0x18000b66a  mov     edi, [rbp+37h+arg_48]
0x18000b670  mov     [rsi+64h], edi
0x18000b673  mov     rbx, [rbp+37h+arg_68]
0x18000b67a  cmp     [rsi+0B0h], rbx
0x18000b681  jz      short loc_18000B6BB
0x18000b683  test    rbx, rbx
0x18000b686  jz      short loc_18000B698
0x18000b688  mov     rax, [rbx]
0x18000b68b  mov     rcx, rbx
0x18000b68e  mov     rax, [rax+8]
0x18000b692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b697  nop
0x18000b698  mov     rcx, [rsi+0B0h]
0x18000b69f  mov     [rsi+0B0h], rbx
0x18000b6a6  test    rcx, rcx
0x18000b6a9  jz      short loc_18000B6B8
0x18000b6ab  mov     rax, [rcx]
0x18000b6ae  mov     rax, [rax+10h]
0x18000b6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6b7  nop
0x18000b6b8  xor     r8d, r8d
0x18000b6bb  mov     rax, [rbp+37h+arg_40]
0x18000b6c2  mov     [rsi+48h], rax
0x18000b6c6  mov     eax, [rbp+37h+arg_58]
0x18000b6cc  mov     [rsi+60h], eax
0x18000b6cf  bt      edi, 15h
0x18000b6d3  jb      loc_18000BABA
0x18000b6d9  mov     eax, cs:dword_1800D1940
0x18000b6df  cmp     eax, 8000000Ah
0x18000b6e4  jz      loc_18000BA7E
0x18000b6ea  test    eax, eax
0x18000b6ec  jnz     loc_18000BABA
0x18000b6f2  mov     al, 1
0x18000b6f4  mov     [rsi+68h], al
0x18000b6f7  mov     rbx, [rbp+37h+arg_78]
0x18000b6fe  cmp     [rsi+0B8h], rbx
0x18000b705  jnz     loc_18000BAC1
0x18000b70b  movups  xmm0, xmmword ptr [r12]
0x18000b710  movups  xmmword ptr [rsi+30h], xmm0
0x18000b714  mov     [rbp+37h+ProcessInformation], r8d
0x18000b718  mov     qword ptr [rsp+0D0h+ReturnLength], r8; int
0x18000b71d  mov     r9d, 4; ProcessInformationLength
0x18000b723  lea     r8, [rbp+37h+ProcessInformation]; ProcessInformation
0x18000b727  mov     edx, 18h; ProcessInformationClass
0x18000b72c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000b733  mov     rcx, rdi; ProcessHandle
0x18000b736  call    cs:__imp_NtQueryInformationProcess
0x18000b73c  test    eax, eax
0x18000b73e  js      loc_18000BAF1
0x18000b744  mov     eax, [rbp+37h+ProcessInformation]
0x18000b747  mov     [rsi+58h], eax
0x18000b74a  mov     r12, [rsi+70h]
0x18000b74e  test    r12, r12
0x18000b751  jnz     loc_18000BB0E
0x18000b757  xor     r12d, r12d
0x18000b75a  mov     [rsi+70h], r12
0x18000b75e  mov     [rbp+37h+TokenHandle], r12
0x18000b762  test    r15, r15
0x18000b765  jz      loc_18000B811
0x18000b76b  lea     rdx, [rbp+37h+TokenHandle]
0x18000b76f  mov     rcx, r15
0x18000b772  call    cs:__imp_UMgrQueryUserToken
0x18000b778  mov     r15d, eax
0x18000b77b  test    eax, eax
0x18000b77d  jns     loc_18000B838
0x18000b783  mov     rcx, [rbp+3Fh]; this
0x18000b787  mov     r9d, eax; char *
0x18000b78a  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000b791  mov     edx, 40Eh; void *
0x18000b796  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b79b  nop
0x18000b79c  mov     rcx, [rbp+37h+TokenHandle]; hObject
0x18000b7a0  lea     rax, [rcx-1]
0x18000b7a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b7a8  jbe     loc_18000BB74
0x18000b7ae  mov     rcx, [rbp+3Fh]; this
0x18000b7b2  mov     r9d, r15d; char *
0x18000b7b5  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000b7bc  mov     edx, 11Bh; void *
0x18000b7c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7c6  mov     eax, r15d
0x18000b7c9  jmp     short loc_18000B7EA
0x18000b7cb  mov     ebx, 80070216h
0x18000b7d0  mov     rcx, [rbp+3Fh]; this
0x18000b7d4  mov     r9d, ebx; char *
0x18000b7d7  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000b7de  mov     edx, 123h; void *
0x18000b7e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7e8  mov     eax, ebx
0x18000b7ea  mov     rcx, [rbp+37h+var_38]
0x18000b7ee  xor     rcx, rsp; StackCookie
0x18000b7f1  call    __security_check_cookie
0x18000b7f6  mov     rbx, [rsp+0D0h+arg_8]
0x18000b7fe  add     rsp, 0A0h
0x18000b805  pop     r15
0x18000b807  pop     r14
0x18000b809  pop     r13
0x18000b80b  pop     r12
0x18000b80d  pop     rdi
0x18000b80e  pop     rsi
0x18000b80f  pop     rbp
0x18000b810  retn
0x18000b811  call    cs:__imp_GetCurrentThread
0x18000b817  nop
0x18000b818  lea     r9, [rbp+37h+TokenHandle]; TokenHandle
0x18000b81c  mov     edx, 8; DesiredAccess
0x18000b821  mov     r8d, 1; OpenAsSelf
0x18000b827  mov     rcx, rax; ThreadHandle
0x18000b82a  call    cs:__imp_OpenThreadToken
0x18000b830  test    eax, eax
0x18000b832  jz      loc_18000BB2C
0x18000b838  mov     rdx, [rbp+37h+TokenHandle]
0x18000b83c  lea     rcx, [rbp+37h+Block]
0x18000b840  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18000b845  mov     rcx, [rbp+37h+Block]
0x18000b849  mov     rcx, [rcx]; pSid
0x18000b84c  call    cs:__imp_GetLengthSid
0x18000b852  mov     r15d, eax
0x18000b855  mov     edx, eax; uBytes
0x18000b857  mov     ecx, 40h ; '@'; uFlags
0x18000b85c  call    cs:__imp_LocalAlloc
0x18000b862  mov     rbx, rax
0x18000b865  test    rax, rax
0x18000b868  jnz     short loc_18000B8A3
0x18000b86a  mov     rcx, [rbp+3Fh]; this
0x18000b86e  mov     r15d, 8007000Eh
0x18000b874  mov     r9d, r15d; char *
0x18000b877  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000b87e  mov     edx, 418h; void *
0x18000b883  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b888  mov     rcx, [rbp+37h+Block]; Block
0x18000b88c  mov     [rbp+37h+Block], r12
0x18000b890  test    rcx, rcx
0x18000b893  jz      loc_18000B79C
0x18000b899  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b89e  jmp     loc_18000B79C
0x18000b8a3  mov     r8, [rbp+37h+Block]
0x18000b8a7  mov     r8, [r8]; pSourceSid
0x18000b8aa  mov     rdx, rbx; pDestinationSid
0x18000b8ad  mov     ecx, r15d; nDestinationSidLength
0x18000b8b0  call    cs:__imp_CopySid
0x18000b8b6  test    eax, eax
0x18000b8b8  jz      short loc_18000B8E5
0x18000b8ba  mov     [rsi+70h], rbx
0x18000b8be  mov     rcx, [rbp+37h+Block]; Block
0x18000b8c2  mov     [rbp+37h+Block], r12
0x18000b8c6  test    rcx, rcx
0x18000b8c9  jnz     loc_18000BB89
0x18000b8cf  mov     rcx, [rbp+37h+TokenHandle]; hObject
0x18000b8d3  lea     rax, [rcx-1]
0x18000b8d7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b8db  ja      short loc_18000B929
0x18000b8dd  call    cs:__imp_CloseHandle
0x18000b8e3  jmp     short loc_18000B929
0x18000b8e5  mov     rcx, [rbp+3Fh]; this
0x18000b8e9  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000b8f0  mov     edx, 419h; void *
0x18000b8f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b8fa  mov     r15d, eax
0x18000b8fd  mov     rcx, rbx; hMem
0x18000b900  call    cs:__imp_LocalFree
0x18000b906  mov     rcx, [rbp+37h+Block]; Block
0x18000b90a  mov     [rbp+37h+Block], r12
0x18000b90e  test    rcx, rcx
0x18000b911  jnz     loc_18000BB7F
0x18000b917  lea     rcx, [rbp+37h+TokenHandle]
0x18000b91b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000b920  test    r15d, r15d
0x18000b923  js      loc_18000B7AE
0x18000b929  mov     r15d, 0FFFFFFFFh
0x18000b92f  test    dword ptr [rsi+64h], 2000000h
0x18000b936  jnz     loc_18000BB93
0x18000b93c  test    r14, r14
0x18000b93f  jz      loc_18000BC14
0x18000b945  inc     rdi
0x18000b948  cmp     word ptr [r14+rdi*2], 0
0x18000b94e  jnz     short loc_18000B945
0x18000b950  cmp     rdi, r15
0x18000b953  ja      loc_18000B7CB
0x18000b959  mov     rcx, [rsi+78h]; string
0x18000b95d  call    cs:__imp_WindowsDeleteString
0x18000b963  mov     qword ptr [rsi+78h], 0
0x18000b96b  mov     edx, edi; length
0x18000b96d  lea     r8, [rsi+78h]; string
0x18000b971  mov     rcx, r14; sourceString
0x18000b974  call    cs:__imp_WindowsCreateString
0x18000b97a  mov     ebx, eax
0x18000b97c  test    eax, eax
0x18000b97e  js      loc_18000B7D0
0x18000b984  test    [rbp+37h+arg_50], 2
0x18000b98b  jnz     short loc_18000B99C
0x18000b98d  test    dword ptr [rsi+64h], 0A000000h
0x18000b994  jz      short loc_18000BA00
0x18000b996  mov     r15d, 1D4C0h
0x18000b99c  mov     [rsi+5Ch], r15d
0x18000b9a0  mov     dword ptr [rbp+37h+TokenHandle], 0
0x18000b9a7  xor     r9d, r9d; lpContext
0x18000b9aa  lea     r8, [rbp+37h+TokenHandle]; fPending
0x18000b9ae  xor     edx, edx; dwFlags
0x18000b9b0  lea     rcx, ?s_initStoreOnce@AppActivation@@0T_RTL_RUN_ONCE@@A; lpInitOnce
0x18000b9b7  call    cs:__imp___std_init_once_begin_initialize
0x18000b9bd  test    eax, eax
0x18000b9bf  jnz     loc_18000BC2C
0x18000b9c5  mov     rcx, [rbp+3Fh]; this
0x18000b9c9  lea     r8, aWil; "wil"
0x18000b9d0  mov     edx, 37Ah; void *
0x18000b9d5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b9da  mov     ebx, eax
0x18000b9dc  test    ebx, ebx
0x18000b9de  js      short loc_18000BA1C
0x18000b9e0  mov     r8, r13; struct _ActivateComponentInfo *
0x18000b9e3  mov     rdx, [rbp+37h+var_80]; struct ActivateByExtensionArgs *
0x18000b9e7  mov     rcx, rsi; this
0x18000b9ea  call    ?PrepareExtensionForActivate@AppActivation@@AEAAJPEAUActivateByExtensionArgs@@PEBU_ActivateComponentInfo@@@Z; AppActivation::PrepareExtensionForActivate(ActivateByExtensionArgs *,_ActivateComponentInfo const *)
0x18000b9ef  mov     ebx, eax
0x18000b9f1  test    eax, eax
0x18000b9f3  js      loc_18000BC88
0x18000b9f9  xor     eax, eax
0x18000b9fb  jmp     loc_18000B7EA
0x18000ba00  mov     r15d, cs:dword_1800D2388
0x18000ba07  test    r15d, r15d
0x18000ba0a  jnz     short loc_18000B99C
0x18000ba0c  call    ?GetActivateTimeoutLimitMs@@YAKK@Z; GetActivateTimeoutLimitMs(ulong)
0x18000ba11  mov     r15d, eax
0x18000ba14  mov     cs:dword_1800D2388, eax
0x18000ba1a  jmp     short loc_18000B99C
0x18000ba1c  mov     rcx, [rbp+3Fh]; this
0x18000ba20  mov     r9d, ebx; char *
0x18000ba23  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000ba2a  mov     edx, 137h; void *
0x18000ba2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba34  mov     eax, ebx
0x18000ba36  jmp     loc_18000B7EA
0x18000ba3b  mov     rax, [r13+20h]
0x18000ba3f  sub     rax, [r12]
0x18000ba43  jnz     short loc_18000BA4E
0x18000ba45  mov     rax, [r13+28h]
0x18000ba49  sub     rax, [r12+8]
0x18000ba4e  test    rax, rax
0x18000ba51  setnz   al
0x18000ba54  mov     rcx, [rbp+3Fh]; this
0x18000ba58  test    al, al
0x18000ba5a  jz      short loc_18000BA6E
0x18000ba5c  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000ba63  mov     edx, 105h; void *
0x18000ba68  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000ba6e  mov     rax, [r13+8]
0x18000ba72  mov     [rsi+0F0h], rax
0x18000ba79  jmp     loc_18000B64A
0x18000ba7e  mov     dword ptr [rbp+37h+TokenHandle], r8d
0x18000ba82  xor     r8d, r8d
0x18000ba85  lea     rdx, [rbp+37h+TokenHandle]
0x18000ba89  xor     ecx, ecx
0x18000ba8b  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000ba91  mov     eax, dword ptr [rbp+37h+TokenHandle]
0x18000ba94  cmp     eax, 5
0x18000ba97  jz      short loc_18000BAAD
0x18000ba99  cmp     eax, 0Bh
0x18000ba9c  jz      short loc_18000BAAD
0x18000ba9e  xor     r8d, r8d
0x18000baa1  mov     cs:dword_1800D1940, r8d
0x18000baa8  jmp     loc_18000B6F2
0x18000baad  mov     cs:dword_1800D1940, 1
0x18000bab7  xor     r8d, r8d
0x18000baba  xor     al, al
0x18000babc  jmp     loc_18000B6F4
0x18000bac1  mov     [rbp+37h+Block], rbx
0x18000bac5  lea     rcx, [rbp+37h+Block]
  ... truncated ...
```
