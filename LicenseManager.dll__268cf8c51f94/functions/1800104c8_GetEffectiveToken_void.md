# GetEffectiveToken(void)

- ea: `0x1800104c8`
- end: `0x180010748`
- name: `?GetEffectiveToken@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ`
- size: `640`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800107b0`
- `0x180011aa0`
- `0x180026b60`
- `0x1800336cc`
- `0x180034bec`
- `0x180045750`

## callees

- `0x18000b7a4`
- `0x1800104c8`
- `0x1800119e0`
- `0x1800593bc`
- `0x18008a400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001057d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001060f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001057d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001060f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001059a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001059a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001062d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001062d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010510`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800105b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010510`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800105b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010525`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800105d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010525`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800105d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001063d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001063d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180010683`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800106aa`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180010683`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800106aa`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800105f9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800105f9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010553`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010553`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001065b`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001065b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetEffectiveToken(__int64 a1)
{
  char v2; // bl
  bool v3; // di
  HANDLE CurrentThread; // rax
  int LastError; // eax
  HANDLE v6; // rax
  HRESULT v8; // eax
  signed int v9; // eax
  HANDLE CurrentProcess; // rax
  const char *v11; // r9
  const char *v12; // r9
  HRESULT v13; // eax
  HRESULT v14; // eax
  int ReturnLength; // [rsp+20h] [rbp-40h]
  void **v16; // [rsp+30h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-28h] BYREF
  void **v18; // [rsp+40h] [rbp-20h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+48h] [rbp-18h] BYREF
  char v20; // [rsp+50h] [rbp-10h]
  __int64 v21; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int TokenInformation; // [rsp+98h] [rbp+38h] BYREF
  DWORD v24; // [rsp+A0h] [rbp+40h] BYREF

  TokenInformation = 1;
  v2 = 0;
  v20 = 0;
  v21 = 0;
  v3 = 0;
  v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    TokenInformation = 0;
    v24 = 4;
    if ( GetTokenInformation(TokenHandle, TokenType, &TokenInformation, 4u, &v24) )
      v3 = TokenInformation == 2;
  }
  v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( TokenHandle
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v16) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  if ( !v3 )
  {
    v8 = CoImpersonateClient();
    if ( v8 )
    {
      if ( v8 != -2147417833 && v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A9,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
          (const char *)(unsigned int)v8,
          ReturnLength);
    }
    else
    {
      v2 = 1;
    }
    v20 = v2;
  }
  *(_QWORD *)a1 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  TokenInformation = 1;
  v6 = GetCurrentThread();
  if ( OpenThreadToken(v6, 0x2000Eu, 1, (PHANDLE)(a1 + 8)) )
  {
    if ( v2 )
    {
      v14 = CoRevertToSelf();
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
          (const char *)(unsigned int)v14,
          ReturnLength);
    }
  }
  else
  {
    v9 = GetLastError();
    if ( v9 != 1008 )
    {
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
        (const char *)(unsigned int)v9,
        ReturnLength);
    }
    v18 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    ExistingTokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x2000Eu, &ExistingTokenHandle) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
        v11);
    if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, (PHANDLE)(a1 + 8)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
        v12);
    v18 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v18);
    if ( v2 )
    {
      v13 = CoRevertToSelf();
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
          (const char *)(unsigned int)v13,
          ReturnLength);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800104c8  mov     [rsp-28h+arg_18], rbx
0x1800104cd  mov     [rsp-28h+arg_0], rcx
0x1800104d2  push    rbp
0x1800104d3  push    rsi
0x1800104d4  push    rdi
0x1800104d5  push    r12
0x1800104d7  push    r15
0x1800104d9  mov     rbp, rsp
0x1800104dc  sub     rsp, 60h
0x1800104e0  mov     rsi, rcx
0x1800104e3  mov     r15d, 1
0x1800104e9  mov     [rbp+TokenInformation], r15d
0x1800104ed  xor     bl, bl
0x1800104ef  mov     [rbp+var_10], bl
0x1800104f2  mov     [rbp+var_8], 0
0x1800104fa  xor     dil, dil
0x1800104fd  lea     r12, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180010504  mov     [rbp+var_30], r12
0x180010508  mov     [rbp+TokenHandle], 0
0x180010510  call    cs:__imp_GetCurrentThread
0x180010516  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001051a  mov     r8d, r15d; OpenAsSelf
0x18001051d  mov     edx, 20008h; DesiredAccess
0x180010522  mov     rcx, rax; ThreadHandle
0x180010525  call    cs:__imp_OpenThreadToken
0x18001052b  test    eax, eax
0x18001052d  jz      short loc_180010565
0x18001052f  mov     [rbp+TokenInformation], 0
0x180010536  lea     r9d, [r15+3]; TokenInformationLength
0x18001053a  mov     [rbp+arg_10], r9d
0x18001053e  lea     rax, [rbp+arg_10]
0x180010542  mov     qword ptr [rsp+60h+ReturnLength], rax; int
0x180010547  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001054b  lea     edx, [r15+7]; TokenInformationClass
0x18001054f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180010553  call    cs:__imp_GetTokenInformation
0x180010559  test    eax, eax
0x18001055b  jz      short loc_180010565
0x18001055d  cmp     [rbp+TokenInformation], 2
0x180010561  setz    dil
0x180010565  mov     [rbp+var_30], r12
0x180010569  cmp     [rbp+TokenHandle], 0
0x18001056e  jz      short loc_1800105A1
0x180010570  lea     rcx, [rbp+var_30]
0x180010574  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180010579  test    al, al
0x18001057b  jnz     short loc_1800105A1
0x18001057d  call    cs:__imp_GetLastError
0x180010583  test    eax, eax
0x180010585  jle     short loc_18001058F
0x180010587  movzx   eax, ax
0x18001058a  or      eax, 80070000h
0x18001058f  xor     r9d, r9d; lpArguments
0x180010592  xor     r8d, r8d; nNumberOfArguments
0x180010595  mov     edx, r15d; dwExceptionFlags
0x180010598  mov     ecx, eax; dwExceptionCode
0x18001059a  call    cs:__imp_RaiseException
0x1800105a0  int     3; Trap to Debugger
0x1800105a1  test    dil, dil
0x1800105a4  jz      short loc_1800105F9
0x1800105a6  mov     [rsi], r12
0x1800105a9  lea     rdi, [rsi+8]
0x1800105ad  mov     qword ptr [rdi], 0
0x1800105b4  mov     [rbp+TokenInformation], r15d
0x1800105b8  call    cs:__imp_GetCurrentThread
0x1800105be  mov     r9, rdi; TokenHandle
0x1800105c1  mov     r8d, r15d; OpenAsSelf
0x1800105c4  mov     r15d, 2000Eh
0x1800105ca  mov     edx, r15d; DesiredAccess
0x1800105cd  mov     rcx, rax; ThreadHandle
0x1800105d0  call    cs:__imp_OpenThreadToken
0x1800105d6  test    eax, eax
0x1800105d8  jz      short loc_18001060F
0x1800105da  test    bl, bl
0x1800105dc  jnz     loc_1800106AA
0x1800105e2  mov     rax, rsi
0x1800105e5  mov     rbx, [rsp+60h+arg_18]
0x1800105ed  add     rsp, 60h
0x1800105f1  pop     r15
0x1800105f3  pop     r12
0x1800105f5  pop     rdi
0x1800105f6  pop     rsi
0x1800105f7  pop     rbp
0x1800105f8  retn
0x1800105f9  call    cs:__imp_CoImpersonateClient
0x1800105ff  test    eax, eax
0x180010601  jnz     loc_180010717
0x180010607  mov     bl, r15b
0x18001060a  mov     [rbp+var_10], bl
0x18001060d  jmp     short loc_1800105A6
0x18001060f  call    cs:__imp_GetLastError
0x180010615  nop
0x180010616  cmp     eax, 3F0h
0x18001061b  jnz     loc_1800106F2
0x180010621  mov     [rbp+var_20], r12
0x180010625  mov     [rbp+ExistingTokenHandle], 0
0x18001062d  call    cs:__imp_GetCurrentProcess
0x180010633  lea     r8, [rbp+ExistingTokenHandle]; TokenHandle
0x180010637  mov     edx, r15d; DesiredAccess
0x18001063a  mov     rcx, rax; ProcessHandle
0x18001063d  call    cs:__imp_OpenProcessToken
0x180010643  mov     rcx, [rbp+28h]; this
0x180010647  test    eax, eax
0x180010649  jz      loc_180010724
0x18001064f  mov     r8, rdi; DuplicateTokenHandle
0x180010652  mov     edx, 2; ImpersonationLevel
0x180010657  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x18001065b  call    cs:__imp_DuplicateToken
0x180010661  mov     rcx, [rbp+28h]; this
0x180010665  test    eax, eax
0x180010667  jz      loc_180010736
0x18001066d  mov     [rbp+var_20], r12
0x180010671  lea     rcx, [rbp+var_20]
0x180010675  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18001067a  nop
0x18001067b  test    bl, bl
0x18001067d  jz      loc_1800105E2
0x180010683  call    cs:__imp_CoRevertToSelf
0x180010689  mov     rcx, [rbp+28h]; this
0x18001068d  test    eax, eax
0x18001068f  jns     loc_1800105E2
0x180010695  mov     r9d, eax; char *
0x180010698  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001069f  mov     edx, 1B0h; void *
0x1800106a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800106aa  call    cs:__imp_CoRevertToSelf
0x1800106b0  mov     rcx, [rbp+28h]; this
0x1800106b4  test    eax, eax
0x1800106b6  jns     loc_1800105E2
0x1800106bc  mov     r9d, eax; char *
0x1800106bf  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800106c6  mov     edx, 1B0h; void *
0x1800106cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800106d1  mov     rcx, [rbp+28h]; this
0x1800106d5  test    eax, eax
0x1800106d7  jns     loc_18001060A
0x1800106dd  mov     r9d, eax; char *
0x1800106e0  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800106e7  mov     edx, 1A9h; void *
0x1800106ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800106f2  test    eax, eax
0x1800106f4  jle     short loc_1800106FE
0x1800106f6  movzx   eax, ax
0x1800106f9  or      eax, 80070000h
0x1800106fe  mov     rcx, [rbp+28h]; this
0x180010702  mov     r9d, eax; char *
0x180010705  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001070c  mov     edx, 97h; void *
0x180010711  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010717  cmp     eax, 80010117h
0x18001071c  jz      loc_18001060A
0x180010722  jmp     short loc_1800106D1
0x180010724  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001072b  mov     edx, 9Dh; void *
0x180010730  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180010736  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x18001073d  mov     edx, 9Eh; void *
0x180010742  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
