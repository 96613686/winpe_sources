# EnterpriseModernAppManager::GetCallerProcessToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18000b1ec`
- end: `0x18000b53f`
- name: `?GetCallerProcessToken@EnterpriseModernAppManager@@QEAAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `851`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b7b0`
- `0x18000bd80`
- `0x18000d240`
- `0x18000ddd0`
- `0x18000df50`

## callees

- `0x180009d14`
- `0x18000b1ec`
- `0x18000d3bc`
- `0x18000d3dc`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b42a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b4d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b4ee`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b42a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b4d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b4ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b301`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b3ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b3ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b451`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b338`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b470`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b2a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b338`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b293`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b32a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b51d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b293`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b32a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b51d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000b4a2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000b4a2`
- `combase!__imp_CoGetCallContextOfObject` at `0x18000b21f`
- `combase!__imp_CoGetCallContextOfObject` at `0x18000b21f`

## string_xrefs

- `0x18000b36b`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\dll\enterprisemodernappmanager.cpp`
- `0x18000b3c1`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\dll\enterprisemodernappmanager.cpp`
- `0x18000b410`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\dll\enterprisemodernappmanager.cpp`
- `0x18000b4b6`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\dll\enterprisemodernappmanager.cpp`

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
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(v22, TokenHandle);
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
0x18000b1ec  mov     [rsp-18h+arg_0], rbx
0x18000b1f1  mov     [rsp-18h+arg_8], rsi
0x18000b1f6  push    rbp
0x18000b1f7  push    rdi
0x18000b1f8  push    r14
0x18000b1fa  mov     rbp, rsp
0x18000b1fd  sub     rsp, 40h
0x18000b201  mov     r14, rdx
0x18000b204  mov     [rbp+hObject], 0
0x18000b20c  mov     [rbp+var_10], 0
0x18000b214  lea     r8, [rbp+var_10]
0x18000b218  lea     rdx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541
0x18000b21f  call    cs:__imp_CoGetCallContextOfObject
0x18000b226  nop     dword ptr [rax+rax+00h]
0x18000b22b  mov     ebx, eax
0x18000b22d  test    eax, eax
0x18000b22f  jns     short loc_18000B265
0x18000b231  mov     rcx, [rbp+18h]; this
0x18000b235  mov     r9d, eax; char *
0x18000b238  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x18000b23f  mov     edx, 1C1h; void *
0x18000b244  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b249  nop
0x18000b24a  mov     rcx, [rbp+var_10]
0x18000b24e  test    rcx, rcx
0x18000b251  jz      short loc_18000B260
0x18000b253  mov     rax, [rcx]
0x18000b256  mov     rax, [rax+10h]
0x18000b25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b25f  nop
0x18000b260  jmp     loc_18000B360
0x18000b265  mov     rcx, [rbp+var_10]
0x18000b269  test    rcx, rcx
0x18000b26c  jz      loc_18000B301
0x18000b272  mov     rax, [rcx]
0x18000b275  mov     rsi, [rax+18h]
0x18000b279  mov     rdi, [rbp+hObject]
0x18000b27d  test    rdi, rdi
0x18000b280  jz      short loc_18000B2B1
0x18000b282  call    cs:__imp_GetLastError
0x18000b289  nop     dword ptr [rax+rax+00h]
0x18000b28e  mov     ebx, eax
0x18000b290  mov     rcx, rdi; hObject
0x18000b293  call    cs:__imp_CloseHandle
0x18000b29a  nop     dword ptr [rax+rax+00h]
0x18000b29f  mov     ecx, ebx; dwErrCode
0x18000b2a1  call    cs:__imp_SetLastError
0x18000b2a8  nop     dword ptr [rax+rax+00h]
0x18000b2ad  mov     rcx, [rbp+var_10]
0x18000b2b1  mov     [rbp+hObject], 0
0x18000b2b9  lea     r8, [rbp+hObject]
0x18000b2bd  mov     edx, 1000h
0x18000b2c2  mov     rax, rsi
0x18000b2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ca  mov     ebx, eax
0x18000b2cc  test    eax, eax
0x18000b2ce  jns     short loc_18000B348
0x18000b2d0  mov     rcx, [rbp+18h]; this
0x18000b2d4  mov     r9d, eax; char *
0x18000b2d7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x18000b2de  mov     edx, 1C4h; void *
0x18000b2e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2e8  nop
0x18000b2e9  mov     rcx, [rbp+var_10]
0x18000b2ed  test    rcx, rcx
0x18000b2f0  jz      short loc_18000B2FF
0x18000b2f2  mov     rax, [rcx]
0x18000b2f5  mov     rax, [rax+10h]
0x18000b2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2fe  nop
0x18000b2ff  jmp     short loc_18000B360
0x18000b301  call    cs:__imp_GetCurrentProcess
0x18000b308  nop     dword ptr [rax+rax+00h]
0x18000b30d  mov     rsi, rax
0x18000b310  mov     rdi, [rbp+hObject]
0x18000b314  test    rdi, rdi
0x18000b317  jz      short loc_18000B344
0x18000b319  call    cs:__imp_GetLastError
0x18000b320  nop     dword ptr [rax+rax+00h]
0x18000b325  mov     ebx, eax
0x18000b327  mov     rcx, rdi; hObject
0x18000b32a  call    cs:__imp_CloseHandle
0x18000b331  nop     dword ptr [rax+rax+00h]
0x18000b336  mov     ecx, ebx; dwErrCode
0x18000b338  call    cs:__imp_SetLastError
0x18000b33f  nop     dword ptr [rax+rax+00h]
0x18000b344  mov     [rbp+hObject], rsi
0x18000b348  mov     rcx, [rbp+var_10]
0x18000b34c  test    rcx, rcx
0x18000b34f  jz      short loc_18000B35E
0x18000b351  mov     rax, [rcx]
0x18000b354  mov     rax, [rax+10h]
0x18000b358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b35d  nop
0x18000b35e  xor     ebx, ebx
0x18000b360  test    ebx, ebx
0x18000b362  jns     short loc_18000B398
0x18000b364  mov     rcx, [rbp+18h]; this
0x18000b368  mov     r9d, ebx; char *
0x18000b36b  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18000b372  mov     edx, 69h ; 'i'; void *
0x18000b377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b37c  mov     rcx, [rbp+hObject]; hObject
0x18000b380  test    rcx, rcx
0x18000b383  jz      short loc_18000B391
0x18000b385  call    cs:__imp_CloseHandle
0x18000b38c  nop     dword ptr [rax+rax+00h]
0x18000b391  mov     eax, ebx
0x18000b393  jmp     loc_18000B52B
0x18000b398  mov     [rbp+TokenHandle], 0
0x18000b3a0  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000b3a4  mov     edx, 0Ah; DesiredAccess
0x18000b3a9  mov     rcx, [rbp+hObject]; ProcessHandle
0x18000b3ad  call    cs:__imp_OpenProcessToken
0x18000b3b4  nop     dword ptr [rax+rax+00h]
0x18000b3b9  test    eax, eax
0x18000b3bb  jnz     short loc_18000B3EE
0x18000b3bd  mov     rcx, [rbp+18h]; this
0x18000b3c1  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18000b3c8  lea     edx, [rax+6Ch]; void *
0x18000b3cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b3d0  mov     ebx, eax
0x18000b3d2  mov     rcx, [rbp+TokenHandle]; hObject
0x18000b3d6  lea     rdx, [rcx-1]
0x18000b3da  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000b3de  ja      short loc_18000B37C
0x18000b3e0  call    cs:__imp_CloseHandle
0x18000b3e7  nop     dword ptr [rax+rax+00h]
0x18000b3ec  jmp     short loc_18000B37C
0x18000b3ee  mov     [rbp+var_10], 0
0x18000b3f6  mov     rdx, [rbp+TokenHandle]
0x18000b3fa  lea     rcx, [rbp+var_10]
0x18000b3fe  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18000b403  mov     ebx, eax
0x18000b405  test    eax, eax
0x18000b407  jns     short loc_18000B444
0x18000b409  mov     rcx, [rbp+18h]; this
0x18000b40d  mov     r9d, eax; char *
0x18000b410  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18000b417  mov     edx, 6Fh ; 'o'; void *
0x18000b41c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b421  mov     rcx, [rbp+var_10]
0x18000b425  test    rcx, rcx
0x18000b428  jz      short loc_18000B436
0x18000b42a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b431  nop     dword ptr [rax+rax+00h]
0x18000b436  mov     rcx, [rbp+TokenHandle]
0x18000b43a  lea     rax, [rcx-1]
0x18000b43e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b442  jmp     short loc_18000B3DE
0x18000b444  mov     rdi, [r14]
0x18000b447  lea     rax, [rdi-1]
0x18000b44b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b44f  ja      short loc_18000B47C
0x18000b451  call    cs:__imp_GetLastError
0x18000b458  nop     dword ptr [rax+rax+00h]
0x18000b45d  mov     ebx, eax
0x18000b45f  mov     rcx, rdi; hObject
0x18000b462  call    cs:__imp_CloseHandle
0x18000b469  nop     dword ptr [rax+rax+00h]
0x18000b46e  mov     ecx, ebx; dwErrCode
0x18000b470  call    cs:__imp_SetLastError
0x18000b477  nop     dword ptr [rax+rax+00h]
0x18000b47c  mov     qword ptr [r14], 0
0x18000b483  mov     [rsp+40h+phNewToken], r14; phNewToken
0x18000b488  mov     [rsp+40h+TokenType], 2; TokenType
0x18000b490  mov     r9d, 1; ImpersonationLevel
0x18000b496  xor     r8d, r8d; lpTokenAttributes
0x18000b499  mov     edx, 20008h; dwDesiredAccess
0x18000b49e  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18000b4a2  call    cs:__imp_DuplicateTokenEx
0x18000b4a9  nop     dword ptr [rax+rax+00h]
0x18000b4ae  test    eax, eax
0x18000b4b0  jnz     short loc_18000B4E5
0x18000b4b2  mov     rcx, [rbp+18h]; this
0x18000b4b6  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18000b4bd  lea     edx, [rax+70h]; void *
0x18000b4c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b4c5  mov     ebx, eax
0x18000b4c7  mov     rcx, [rbp+var_10]
0x18000b4cb  test    rcx, rcx
0x18000b4ce  jz      loc_18000B3D2
0x18000b4d4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b4db  nop     dword ptr [rax+rax+00h]
0x18000b4e0  jmp     loc_18000B3D2
0x18000b4e5  mov     rcx, [rbp+var_10]
0x18000b4e9  test    rcx, rcx
0x18000b4ec  jz      short loc_18000B4FA
0x18000b4ee  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b4f5  nop     dword ptr [rax+rax+00h]
0x18000b4fa  mov     rcx, [rbp+TokenHandle]; hObject
0x18000b4fe  lea     rax, [rcx-1]
0x18000b502  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b506  ja      short loc_18000B514
0x18000b508  call    cs:__imp_CloseHandle
0x18000b50f  nop     dword ptr [rax+rax+00h]
0x18000b514  mov     rcx, [rbp+hObject]; hObject
0x18000b518  test    rcx, rcx
0x18000b51b  jz      short loc_18000B529
0x18000b51d  call    cs:__imp_CloseHandle
0x18000b524  nop     dword ptr [rax+rax+00h]
0x18000b529  xor     eax, eax
0x18000b52b  mov     rbx, [rsp+40h+arg_0]
0x18000b530  mov     rsi, [rsp+40h+arg_8]
0x18000b535  add     rsp, 40h
0x18000b539  pop     r14
0x18000b53b  pop     rdi
0x18000b53c  pop     rbp
0x18000b53d  retn
```
