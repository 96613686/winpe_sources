# IsPresenceMonitoringAllowed

- ea: `0x1800a7488`
- end: `0x1800a761b`
- name: `IsPresenceMonitoringAllowed`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180099b3c`

## callees

- `0x18000782c`
- `0x180007964`
- `0x1800323d0`
- `0x1800535f4`
- `0x18005fdf0`
- `0x1800a5914`
- `0x1800a7488`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800a7587`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800a7587`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800a74c6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800a74c6`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800a74a9`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800a74a9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800a7517`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800a7517`

## string_xrefs

- `0x1800a74d5`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a7530`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a75a0`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a75d9`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall IsPresenceMonitoringAllowed(_BYTE *a1)
{
  ULONG active; // eax
  unsigned int LastError; // ebx
  BOOL v5; // ebx
  const char *v6; // r9
  BOOL v7; // ebx
  void *v8; // rdx
  bool *v9; // r9
  int v10; // eax
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-30h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-30h]
  void *p_hExistingToken; // [rsp+30h] [rbp-20h] BYREF
  void *phToken; // [rsp+38h] [rbp-18h] BYREF
  char v15; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int v17; // [rsp+70h] [rbp+20h] BYREF
  int v18; // [rsp+78h] [rbp+28h] BYREF
  DcaUtil *v19; // [rsp+80h] [rbp+30h] BYREF
  HANDLE hExistingToken; // [rsp+88h] [rbp+38h] BYREF

  *a1 = 0;
  v18 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v18, 0);
  if ( v18 == 3 && (unsigned __int8)IsWTSQueryUserTokenPresent() )
  {
    active = WTSGetActiveConsoleSessionId();
    if ( active == -1 )
    {
      LastError = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6D3,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
        (const char *)0x80004005LL,
        TokenType);
      return LastError;
    }
    hExistingToken = 0;
    p_hExistingToken = &hExistingToken;
    phToken = 0;
    v15 = 1;
    v5 = WTSQueryUserToken(active, &phToken);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hExistingToken);
    if ( v5 )
    {
      p_hExistingToken = &v19;
      v19 = 0;
      phToken = 0;
      v15 = 1;
      v7 = DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityIdentification, TokenImpersonation, &phToken);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hExistingToken);
      if ( v7 )
      {
        LOBYTE(v17) = 1;
        v10 = DcaUtil::CheckTokenMembershipSubAuthority0(v19, v8, (bool *)&v17, v9);
        LastError = v10;
        if ( v10 >= 0 )
        {
          if ( !(_BYTE)v17 )
            *a1 = 1;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
          LastError = 0;
          goto LABEL_16;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6E7,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
          (const char *)(unsigned int)v10,
          TokenTypea);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x6E3,
                      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
                      (const char *)v9);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6D8,
                    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
                    v6);
    }
LABEL_16:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a7488  push    rbp
0x1800a748a  push    rbx
0x1800a748b  push    rdi
0x1800a748c  mov     rbp, rsp
0x1800a748f  sub     rsp, 50h
0x1800a7493  mov     rdi, rcx
0x1800a7496  mov     byte ptr [rcx], 0
0x1800a7499  xor     ecx, ecx
0x1800a749b  mov     [rbp+arg_8], 0
0x1800a74a2  xor     r8d, r8d
0x1800a74a5  lea     rdx, [rbp+arg_8]
0x1800a74a9  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800a74af  cmp     [rbp+arg_8], 3
0x1800a74b3  jnz     loc_1800A7611
0x1800a74b9  call    IsWTSQueryUserTokenPresent
0x1800a74be  test    al, al
0x1800a74c0  jz      loc_1800A7611
0x1800a74c6  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800a74cc  cmp     eax, 0FFFFFFFFh
0x1800a74cf  jnz     short loc_1800A74F5
0x1800a74d1  mov     rcx, [rbp+18h]; this
0x1800a74d5  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a74dc  mov     ebx, 80004005h
0x1800a74e1  mov     edx, 6D3h; void *
0x1800a74e6  mov     r9d, ebx; char *
0x1800a74e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a74ee  mov     eax, ebx
0x1800a74f0  jmp     loc_1800A7613
0x1800a74f5  lea     rcx, [rbp+hExistingToken]
0x1800a74f9  mov     [rbp+hExistingToken], 0
0x1800a7501  mov     [rbp+var_20], rcx
0x1800a7505  lea     rdx, [rbp+phToken]; phToken
0x1800a7509  mov     ecx, eax; SessionId
0x1800a750b  mov     [rbp+phToken], 0
0x1800a7513  mov     [rbp+var_10], 1
0x1800a7517  call    cs:__imp_WTSQueryUserToken
0x1800a751d  lea     rcx, [rbp+var_20]
0x1800a7521  mov     ebx, eax
0x1800a7523  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800a7528  test    ebx, ebx
0x1800a752a  jnz     short loc_1800A7548
0x1800a752c  mov     rcx, [rbp+18h]; this
0x1800a7530  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a7537  mov     edx, 6D8h; void *
0x1800a753c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a7541  mov     ebx, eax
0x1800a7543  jmp     loc_1800A7603
0x1800a7548  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x1800a754c  lea     rax, [rbp+arg_10]
0x1800a7550  mov     [rbp+var_20], rax
0x1800a7554  mov     r9d, 1; ImpersonationLevel
0x1800a755a  lea     rax, [rbp+phToken]
0x1800a755e  mov     [rbp+arg_10], 0
0x1800a7566  mov     [rsp+50h+phNewToken], rax; phNewToken
0x1800a756b  xor     r8d, r8d; lpTokenAttributes
0x1800a756e  mov     edx, 2000000h; dwDesiredAccess
0x1800a7573  mov     [rsp+50h+TokenType], 2; int
0x1800a757b  mov     [rbp+phToken], 0
0x1800a7583  mov     [rbp+var_10], 1
0x1800a7587  call    cs:__imp_DuplicateTokenEx
0x1800a758d  lea     rcx, [rbp+var_20]
0x1800a7591  mov     ebx, eax
0x1800a7593  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800a7598  test    ebx, ebx
0x1800a759a  jnz     short loc_1800A75BE
0x1800a759c  mov     rcx, [rbp+18h]; this
0x1800a75a0  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a75a7  mov     edx, 6E3h; void *
0x1800a75ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a75b1  mov     ebx, eax
0x1800a75b3  lea     rcx, [rbp+arg_10]
0x1800a75b7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a75bc  jmp     short loc_1800A7603
0x1800a75be  mov     rcx, [rbp+arg_10]; this
0x1800a75c2  lea     r8, [rbp+arg_0]; unsigned int
0x1800a75c6  mov     byte ptr [rbp+arg_0], 1
0x1800a75ca  call    ?CheckTokenMembershipSubAuthority0@DcaUtil@@YAJPEAXKPEA_N@Z; DcaUtil::CheckTokenMembershipSubAuthority0(void *,ulong,bool *)
0x1800a75cf  mov     ebx, eax
0x1800a75d1  test    eax, eax
0x1800a75d3  jns     short loc_1800A75EF
0x1800a75d5  mov     rcx, [rbp+18h]; this
0x1800a75d9  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a75e0  mov     r9d, eax; char *
0x1800a75e3  mov     edx, 6E7h; void *
0x1800a75e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a75ed  jmp     short loc_1800A75B3
0x1800a75ef  cmp     byte ptr [rbp+arg_0], 0
0x1800a75f3  lea     rcx, [rbp+arg_10]
0x1800a75f7  jnz     short loc_1800A75FC
0x1800a75f9  mov     byte ptr [rdi], 1
0x1800a75fc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a7601  xor     ebx, ebx
0x1800a7603  lea     rcx, [rbp+hExistingToken]
0x1800a7607  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a760c  jmp     loc_1800A74EE
0x1800a7611  xor     eax, eax
0x1800a7613  add     rsp, 50h
0x1800a7617  pop     rdi
0x1800a7618  pop     rbx
0x1800a7619  pop     rbp
0x1800a761a  retn
```
