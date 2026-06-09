# EnterpriseModernAppManager::GetCallerProcessToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18000afdc`
- end: `0x18000b2b2`
- name: `?GetCallerProcessToken@EnterpriseModernAppManager@@QEAAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `726`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b4d0`
- `0x18000b9a0`
- `0x18000ce70`
- `0x18000d850`
- `0x18000d9d0`

## callees

- `0x180009a40`
- `0x18000afdc`
- `0x18000cfc8`
- `0x18000cfe8`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b1d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b260`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b274`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b1d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b260`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b274`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b0d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b0d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b163`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b07b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b208`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b07b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b073`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b0f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b190`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b288`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b297`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b073`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b0f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b190`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b288`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b297`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000b234`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000b234`
- `combase!__imp_CoGetCallContextOfObject` at `0x18000b00f`
- `combase!__imp_CoGetCallContextOfObject` at `0x18000b00f`

## string_xrefs

- `0x18000b127`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\dll\enterprisemodernappmanager.cpp`
- `0x18000b171`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\dll\enterprisemodernappmanager.cpp`
- `0x18000b1ba`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\dll\enterprisemodernappmanager.cpp`
- `0x18000b242`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\dll\enterprisemodernappmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseModernAppManager::GetCallerProcessToken(__int64 a1, void **a2)
{
  int v3; // eax
  int v4; // ebx
  void *v5; // rcx
  __int64 (__fastcall *v6)(void *, __int64, HANDLE *); // rsi
  HANDLE v7; // rdi
  DWORD LastError; // ebx
  int v9; // eax
  HANDLE CurrentProcess; // rsi
  HANDLE v11; // rdi
  DWORD v12; // ebx
  const char *v14; // r9
  void *v15; // rcx
  bool v16; // cc
  int token_information; // eax
  void *v18; // rdi
  DWORD v19; // ebx
  const char *v20; // r9
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-20h]
  void *v22[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HANDLE hObject; // [rsp+70h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+38h] BYREF

  hObject = 0;
  v22[0] = 0;
  v3 = CoGetCallContextOfObject(a1, &GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, v22);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
      (const char *)(unsigned int)v3,
      TokenType);
    if ( v22[0] )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v22[0] + 16LL))(v22[0]);
    goto LABEL_18;
  }
  v5 = v22[0];
  if ( v22[0] )
  {
    v6 = *(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)v22[0] + 24LL);
    v7 = hObject;
    if ( hObject )
    {
      LastError = GetLastError();
      CloseHandle(v7);
      SetLastError(LastError);
      v5 = v22[0];
    }
    hObject = 0;
    v9 = v6(v5, 4096, &hObject);
    v4 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
        (const char *)(unsigned int)v9,
        TokenType);
      if ( v22[0] )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v22[0] + 16LL))(v22[0]);
      goto LABEL_18;
    }
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    v11 = hObject;
    if ( hObject )
    {
      v12 = GetLastError();
      CloseHandle(v11);
      SetLastError(v12);
    }
    hObject = CurrentProcess;
  }
  if ( v22[0] )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v22[0] + 16LL))(v22[0]);
  v4 = 0;
LABEL_18:
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\dll\\enterprisemodernappmanager.cpp",
      (const char *)(unsigned int)v4,
      TokenType);
LABEL_20:
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)v4;
  }
  TokenHandle = 0;
  if ( !OpenProcessToken(hObject, 0xAu, &TokenHandle) )
  {
    v4 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x6C,
           (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\dll\\enterprisemodernappmanager.cpp",
           v14);
LABEL_25:
    v15 = TokenHandle;
    v16 = (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_26:
    if ( v16 )
      CloseHandle(v15);
    goto LABEL_20;
  }
  v22[0] = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(v22, (__int64)TokenHandle);
  v4 = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\dll\\enterprisemodernappmanager.cpp",
      (const char *)(unsigned int)token_information,
      TokenType);
    if ( v22[0] )
      operator delete(v22[0]);
    v15 = TokenHandle;
    v16 = (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_26;
  }
  v18 = *a2;
  if ( (char *)*a2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v19 = GetLastError();
    CloseHandle(v18);
    SetLastError(v19);
  }
  *a2 = 0;
  if ( !DuplicateTokenEx(TokenHandle, 0x20008u, 0, SecurityIdentification, TokenImpersonation, a2) )
  {
    v4 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x70,
           (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\dll\\enterprisemodernappmanager.cpp",
           v20);
    if ( v22[0] )
      operator delete(v22[0]);
    goto LABEL_25;
  }
  if ( v22[0] )
    operator delete(v22[0]);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  if ( hObject )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x18000afdc  mov     [rsp-18h+arg_0], rbx
0x18000afe1  mov     [rsp-18h+arg_8], rsi
0x18000afe6  push    rbp
0x18000afe7  push    rdi
0x18000afe8  push    r14
0x18000afea  mov     rbp, rsp
0x18000afed  sub     rsp, 40h
0x18000aff1  mov     r14, rdx
0x18000aff4  mov     [rbp+hObject], 0
0x18000affc  mov     [rbp+var_10], 0
0x18000b004  lea     r8, [rbp+var_10]
0x18000b008  lea     rdx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541
0x18000b00f  call    cs:__imp_CoGetCallContextOfObject
0x18000b015  mov     ebx, eax
0x18000b017  test    eax, eax
0x18000b019  jns     short loc_18000B04F
0x18000b01b  mov     rcx, [rbp+18h]; this
0x18000b01f  mov     r9d, eax; char *
0x18000b022  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x18000b029  mov     edx, 1C1h; void *
0x18000b02e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b033  nop
0x18000b034  mov     rcx, [rbp+var_10]
0x18000b038  test    rcx, rcx
0x18000b03b  jz      short loc_18000B04A
0x18000b03d  mov     rax, [rcx]
0x18000b040  mov     rax, [rax+10h]
0x18000b044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b049  nop
0x18000b04a  jmp     loc_18000B11C
0x18000b04f  mov     rcx, [rbp+var_10]
0x18000b053  test    rcx, rcx
0x18000b056  jz      short loc_18000B0D5
0x18000b058  mov     rax, [rcx]
0x18000b05b  mov     rsi, [rax+18h]
0x18000b05f  mov     rdi, [rbp+hObject]
0x18000b063  test    rdi, rdi
0x18000b066  jz      short loc_18000B085
0x18000b068  call    cs:__imp_GetLastError
0x18000b06e  mov     ebx, eax
0x18000b070  mov     rcx, rdi; hObject
0x18000b073  call    cs:__imp_CloseHandle
0x18000b079  mov     ecx, ebx; dwErrCode
0x18000b07b  call    cs:__imp_SetLastError
0x18000b081  mov     rcx, [rbp+var_10]
0x18000b085  mov     [rbp+hObject], 0
0x18000b08d  lea     r8, [rbp+hObject]
0x18000b091  mov     edx, 1000h
0x18000b096  mov     rax, rsi
0x18000b099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b09e  mov     ebx, eax
0x18000b0a0  test    eax, eax
0x18000b0a2  jns     short loc_18000B104
0x18000b0a4  mov     rcx, [rbp+18h]; this
0x18000b0a8  mov     r9d, eax; char *
0x18000b0ab  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x18000b0b2  mov     edx, 1C4h; void *
0x18000b0b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b0bc  nop
0x18000b0bd  mov     rcx, [rbp+var_10]
0x18000b0c1  test    rcx, rcx
0x18000b0c4  jz      short loc_18000B0D3
0x18000b0c6  mov     rax, [rcx]
0x18000b0c9  mov     rax, [rax+10h]
0x18000b0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0d2  nop
0x18000b0d3  jmp     short loc_18000B11C
0x18000b0d5  call    cs:__imp_GetCurrentProcess
0x18000b0db  mov     rsi, rax
0x18000b0de  mov     rdi, [rbp+hObject]
0x18000b0e2  test    rdi, rdi
0x18000b0e5  jz      short loc_18000B100
0x18000b0e7  call    cs:__imp_GetLastError
0x18000b0ed  mov     ebx, eax
0x18000b0ef  mov     rcx, rdi; hObject
0x18000b0f2  call    cs:__imp_CloseHandle
0x18000b0f8  mov     ecx, ebx; dwErrCode
0x18000b0fa  call    cs:__imp_SetLastError
0x18000b100  mov     [rbp+hObject], rsi
0x18000b104  mov     rcx, [rbp+var_10]
0x18000b108  test    rcx, rcx
0x18000b10b  jz      short loc_18000B11A
0x18000b10d  mov     rax, [rcx]
0x18000b110  mov     rax, [rax+10h]
0x18000b114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b119  nop
0x18000b11a  xor     ebx, ebx
0x18000b11c  test    ebx, ebx
0x18000b11e  jns     short loc_18000B14E
0x18000b120  mov     rcx, [rbp+18h]; this
0x18000b124  mov     r9d, ebx; char *
0x18000b127  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18000b12e  mov     edx, 69h ; 'i'; void *
0x18000b133  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b138  mov     rcx, [rbp+hObject]; hObject
0x18000b13c  test    rcx, rcx
0x18000b13f  jz      short loc_18000B147
0x18000b141  call    cs:__imp_CloseHandle
0x18000b147  mov     eax, ebx
0x18000b149  jmp     loc_18000B29F
0x18000b14e  mov     [rbp+TokenHandle], 0
0x18000b156  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000b15a  mov     edx, 0Ah; DesiredAccess
0x18000b15f  mov     rcx, [rbp+hObject]; ProcessHandle
0x18000b163  call    cs:__imp_OpenProcessToken
0x18000b169  test    eax, eax
0x18000b16b  jnz     short loc_18000B198
0x18000b16d  mov     rcx, [rbp+18h]; this
0x18000b171  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18000b178  lea     edx, [rax+6Ch]; void *
0x18000b17b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b180  mov     ebx, eax
0x18000b182  mov     rcx, [rbp+TokenHandle]; hObject
0x18000b186  lea     rdx, [rcx-1]
0x18000b18a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000b18e  ja      short loc_18000B138
0x18000b190  call    cs:__imp_CloseHandle
0x18000b196  jmp     short loc_18000B138
0x18000b198  mov     [rbp+var_10], 0
0x18000b1a0  mov     rdx, [rbp+TokenHandle]
0x18000b1a4  lea     rcx, [rbp+var_10]
0x18000b1a8  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18000b1ad  mov     ebx, eax
0x18000b1af  test    eax, eax
0x18000b1b1  jns     short loc_18000B1E8
0x18000b1b3  mov     rcx, [rbp+18h]; this
0x18000b1b7  mov     r9d, eax; char *
0x18000b1ba  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18000b1c1  mov     edx, 6Fh ; 'o'; void *
0x18000b1c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b1cb  mov     rcx, [rbp+var_10]
0x18000b1cf  test    rcx, rcx
0x18000b1d2  jz      short loc_18000B1DA
0x18000b1d4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b1da  mov     rcx, [rbp+TokenHandle]
0x18000b1de  lea     rax, [rcx-1]
0x18000b1e2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b1e6  jmp     short loc_18000B18E
0x18000b1e8  mov     rdi, [r14]
0x18000b1eb  lea     rax, [rdi-1]
0x18000b1ef  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b1f3  ja      short loc_18000B20E
0x18000b1f5  call    cs:__imp_GetLastError
0x18000b1fb  mov     ebx, eax
0x18000b1fd  mov     rcx, rdi; hObject
0x18000b200  call    cs:__imp_CloseHandle
0x18000b206  mov     ecx, ebx; dwErrCode
0x18000b208  call    cs:__imp_SetLastError
0x18000b20e  mov     qword ptr [r14], 0
0x18000b215  mov     [rsp+40h+phNewToken], r14; phNewToken
0x18000b21a  mov     [rsp+40h+TokenType], 2; TokenType
0x18000b222  mov     r9d, 1; ImpersonationLevel
0x18000b228  xor     r8d, r8d; lpTokenAttributes
0x18000b22b  mov     edx, 20008h; dwDesiredAccess
0x18000b230  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18000b234  call    cs:__imp_DuplicateTokenEx
0x18000b23a  test    eax, eax
0x18000b23c  jnz     short loc_18000B26B
0x18000b23e  mov     rcx, [rbp+18h]; this
0x18000b242  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18000b249  lea     edx, [rax+70h]; void *
0x18000b24c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b251  mov     ebx, eax
0x18000b253  mov     rcx, [rbp+var_10]
0x18000b257  test    rcx, rcx
0x18000b25a  jz      loc_18000B182
0x18000b260  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b266  jmp     loc_18000B182
0x18000b26b  mov     rcx, [rbp+var_10]
0x18000b26f  test    rcx, rcx
0x18000b272  jz      short loc_18000B27A
0x18000b274  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b27a  mov     rcx, [rbp+TokenHandle]; hObject
0x18000b27e  lea     rax, [rcx-1]
0x18000b282  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b286  ja      short loc_18000B28E
0x18000b288  call    cs:__imp_CloseHandle
0x18000b28e  mov     rcx, [rbp+hObject]; hObject
0x18000b292  test    rcx, rcx
0x18000b295  jz      short loc_18000B29D
0x18000b297  call    cs:__imp_CloseHandle
0x18000b29d  xor     eax, eax
0x18000b29f  mov     rbx, [rsp+40h+arg_0]
0x18000b2a4  mov     rsi, [rsp+40h+arg_8]
0x18000b2a9  add     rsp, 40h
0x18000b2ad  pop     r14
0x18000b2af  pop     rdi
0x18000b2b0  pop     rbp
0x18000b2b1  retn
```
