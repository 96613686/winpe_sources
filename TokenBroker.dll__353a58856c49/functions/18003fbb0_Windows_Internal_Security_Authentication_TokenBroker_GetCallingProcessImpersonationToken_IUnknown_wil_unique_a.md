# Windows::Internal::Security::Authentication::TokenBroker::GetCallingProcessImpersonationToken(IUnknown *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18003fbb0`
- end: `0x18003fe9b`
- name: `?GetCallingProcessImpersonationToken@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `747`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d2b0`

## callees

- `0x18000bd40`
- `0x180024000`
- `0x18003fbb0`
- `0x1800565a0`
- `0x18007c220`
- `0x1800af930`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003fcb6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003fcb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003fc13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003fc13`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003fc2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003fc2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003fc6b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003fc6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003fc58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003fc58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fc3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fc3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fcca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fd58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fdea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fe90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fcca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fd58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fdea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fe90`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18003fbe1`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18003fbe1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003fe18`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003fe2b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003fe18`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003fe2b`

## string_xrefs

- `0x18003fd9f`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18003fe3b`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetCallingProcessImpersonationToken(
        __int64 a1,
        void **a2)
{
  int v3; // eax
  unsigned int v4; // esi
  bool v5; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v9; // r9
  const char *v10; // r9
  char *v11; // rbx
  char *v12; // rcx
  unsigned int v14; // eax
  HANDLE v15; // rcx
  unsigned int v16; // eax
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-28h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-28h]
  void *TokenHandle[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HANDLE hExistingToken; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x867,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)0x80070057LL,
      TokenType);
    return 2147942487LL;
  }
  TokenHandle[0] = 0;
  LODWORD(hExistingToken) = 0;
  v3 = CoImpersonateClientOfObject(a1, &hExistingToken);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v3,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)v4,
      TokenTypea);
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)v4,
      TokenType);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)TokenHandle);
    return v4;
  }
  v5 = (_DWORD)hExistingToken != 0;
  if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle[0]);
  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, TokenHandle) )
  {
    if ( !v5 )
      goto LABEL_15;
    goto LABEL_33;
  }
  LastError = GetLastError();
  if ( v5 || LastError != 1008 )
  {
    if ( LastError )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x188,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
             (const char *)LastError,
             TokenType);
      if ( v5 )
        CoRevertToSelf();
      goto LABEL_24;
    }
    if ( !v5 )
      goto LABEL_15;
LABEL_33:
    CoRevertToSelf();
    goto LABEL_15;
  }
  hExistingToken = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x2000Eu, &hExistingToken) )
  {
    if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle[0]);
    TokenHandle[0] = 0;
    if ( DuplicateTokenEx(hExistingToken, 0x2000Cu, 0, SecurityImpersonation, TokenImpersonation, TokenHandle) )
    {
      if ( hExistingToken )
        CloseHandle(hExistingToken);
      goto LABEL_15;
    }
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x184,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
            v10);
    v15 = hExistingToken;
    v4 = v14;
    if ( hExistingToken )
      goto LABEL_23;
  }
  else
  {
    v16 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x182,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
            v9);
    v15 = hExistingToken;
    v4 = v16;
    if ( hExistingToken )
LABEL_23:
      CloseHandle(v15);
  }
LABEL_24:
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_27;
LABEL_15:
  v11 = (char *)*a2;
  *a2 = 0;
  if ( a2 == TokenHandle )
  {
    v12 = (char *)TokenHandle[0];
  }
  else
  {
    v12 = 0;
    *a2 = TokenHandle[0];
    TokenHandle[0] = 0;
  }
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v12);
  TokenHandle[0] = v11;
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v11);
  return 0;
}

```

## disassembly

```asm
0x18003fbb0  push    rdi
0x18003fbb2  sub     rsp, 40h
0x18003fbb6  mov     rdi, rdx
0x18003fbb9  test    rcx, rcx
0x18003fbbc  jz      loc_18003FE36
0x18003fbc2  mov     [rsp+48h+arg_8], rbx
0x18003fbc7  lea     rdx, [rsp+48h+hExistingToken]
0x18003fbcc  mov     [rsp+48h+arg_10], rbp
0x18003fbd1  xor     ebp, ebp
0x18003fbd3  mov     [rsp+48h+TokenHandle], rbp
0x18003fbd8  mov     dword ptr [rsp+48h+hExistingToken], ebp
0x18003fbdc  mov     [rsp+48h+arg_18], rsi
0x18003fbe1  call    cs:__imp_CoImpersonateClientOfObject
0x18003fbe7  mov     esi, eax
0x18003fbe9  test    eax, eax
0x18003fbeb  js      loc_18003FD68
0x18003fbf1  xor     bl, bl
0x18003fbf3  cmp     dword ptr [rsp+48h+hExistingToken], ebp
0x18003fbf7  jz      short loc_18003FBFB
0x18003fbf9  mov     bl, 1
0x18003fbfb  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18003fc00  lea     rax, [rcx-1]
0x18003fc04  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003fc08  jbe     loc_18003FE5C
0x18003fc0e  mov     [rsp+48h+TokenHandle], rbp
0x18003fc13  call    cs:__imp_GetCurrentThread
0x18003fc19  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18003fc1e  mov     edx, 2000Ch; DesiredAccess
0x18003fc23  mov     rcx, rax; ThreadHandle
0x18003fc26  mov     r8d, 1; OpenAsSelf
0x18003fc2c  call    cs:__imp_OpenThreadToken
0x18003fc32  test    eax, eax
0x18003fc34  jnz     loc_18003FCD2
0x18003fc3a  call    cs:__imp_GetLastError
0x18003fc40  test    bl, bl
0x18003fc42  jnz     loc_18003FE70
0x18003fc48  cmp     eax, 3F0h
0x18003fc4d  jnz     loc_18003FE70
0x18003fc53  mov     [rsp+48h+hExistingToken], rbp
0x18003fc58  call    cs:__imp_GetCurrentProcess
0x18003fc5e  lea     r8, [rsp+48h+hExistingToken]; TokenHandle
0x18003fc63  mov     edx, 2000Eh; DesiredAccess
0x18003fc68  mov     rcx, rax; ProcessHandle
0x18003fc6b  call    cs:__imp_OpenProcessToken
0x18003fc71  test    eax, eax
0x18003fc73  jz      loc_18003FDC4
0x18003fc79  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18003fc7e  lea     rax, [rcx-1]
0x18003fc82  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003fc86  jbe     loc_18003FE66
0x18003fc8c  mov     rcx, [rsp+48h+hExistingToken]; hExistingToken
0x18003fc91  lea     rax, [rsp+48h+TokenHandle]
0x18003fc96  mov     [rsp+48h+phNewToken], rax; phNewToken
0x18003fc9b  mov     r9d, 2; ImpersonationLevel
0x18003fca1  xor     r8d, r8d; lpTokenAttributes
0x18003fca4  mov     [rsp+48h+TokenType], 2; TokenType
0x18003fcac  mov     edx, 2000Ch; dwDesiredAccess
0x18003fcb1  mov     [rsp+48h+TokenHandle], rbp
0x18003fcb6  call    cs:__imp_DuplicateTokenEx
0x18003fcbc  test    eax, eax
0x18003fcbe  jz      short loc_18003FD36
0x18003fcc0  mov     rcx, [rsp+48h+hExistingToken]; hObject
0x18003fcc5  test    rcx, rcx
0x18003fcc8  jz      short loc_18003FCDA
0x18003fcca  call    cs:__imp_CloseHandle
0x18003fcd0  jmp     short loc_18003FCDA
0x18003fcd2  test    bl, bl
0x18003fcd4  jnz     loc_18003FE2B
0x18003fcda  mov     rbx, [rdi]
0x18003fcdd  lea     rax, [rsp+48h+TokenHandle]
0x18003fce2  mov     [rdi], rbp
0x18003fce5  cmp     rdi, rax
0x18003fce8  jz      loc_18003FE79
0x18003fcee  mov     rax, [rsp+48h+TokenHandle]
0x18003fcf3  mov     rcx, rbp; hObject
0x18003fcf6  mov     [rdi], rax
0x18003fcf9  mov     [rsp+48h+TokenHandle], rcx
0x18003fcfe  lea     rax, [rcx-1]
0x18003fd02  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003fd06  jbe     loc_18003FE83
0x18003fd0c  lea     rax, [rbx-1]
0x18003fd10  mov     [rsp+48h+TokenHandle], rbx
0x18003fd15  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003fd19  jbe     loc_18003FE8D
0x18003fd1f  xor     eax, eax
0x18003fd21  mov     rbp, [rsp+48h+arg_10]
0x18003fd26  mov     rbx, [rsp+48h+arg_8]
0x18003fd2b  mov     rsi, [rsp+48h+arg_18]
0x18003fd30  add     rsp, 40h
0x18003fd34  pop     rdi
0x18003fd35  retn
0x18003fd36  mov     rcx, [rsp+48h]; this
0x18003fd3b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003fd42  mov     edx, 184h; void *
0x18003fd47  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003fd4c  mov     rcx, [rsp+48h+hExistingToken]; hObject
0x18003fd51  mov     esi, eax
0x18003fd53  test    rcx, rcx
0x18003fd56  jz      short loc_18003FD5E
0x18003fd58  call    cs:__imp_CloseHandle
0x18003fd5e  test    esi, esi
0x18003fd60  jns     loc_18003FCDA
0x18003fd66  jmp     short loc_18003FD9A
0x18003fd68  mov     rcx, [rsp+48h]; this
0x18003fd6d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003fd74  mov     r9d, esi; char *
0x18003fd77  mov     edx, 157h; void *
0x18003fd7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fd81  mov     rcx, [rsp+48h]; this
0x18003fd86  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003fd8d  mov     r9d, esi; char *
0x18003fd90  mov     edx, 177h; void *
0x18003fd95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fd9a  mov     rcx, [rsp+48h]; this
0x18003fd9f  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18003fda6  mov     r9d, esi; char *
0x18003fda9  mov     edx, 86Eh; void *
0x18003fdae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fdb3  lea     rcx, [rsp+48h+TokenHandle]; this
0x18003fdb8  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18003fdbd  mov     eax, esi
0x18003fdbf  jmp     loc_18003FD21
0x18003fdc4  mov     rcx, [rsp+48h]; this
0x18003fdc9  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003fdd0  mov     edx, 182h; void *
0x18003fdd5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003fdda  mov     rcx, [rsp+48h+hExistingToken]; hObject
0x18003fddf  mov     esi, eax
0x18003fde1  test    rcx, rcx
0x18003fde4  jz      loc_18003FD5E
0x18003fdea  call    cs:__imp_CloseHandle
0x18003fdf0  jmp     loc_18003FD5E
0x18003fdf5  mov     rcx, [rsp+48h]; this
0x18003fdfa  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003fe01  mov     r9d, eax; char *
0x18003fe04  mov     edx, 188h; void *
0x18003fe09  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003fe0e  mov     esi, eax
0x18003fe10  test    bl, bl
0x18003fe12  jz      loc_18003FD5E
0x18003fe18  call    cs:__imp_CoRevertToSelf
0x18003fe1e  jmp     loc_18003FD5E
0x18003fe23  test    bl, bl
0x18003fe25  jz      loc_18003FCDA
0x18003fe2b  call    cs:__imp_CoRevertToSelf
0x18003fe31  jmp     loc_18003FCDA
0x18003fe36  mov     rcx, [rsp+48h]; this
0x18003fe3b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x18003fe42  mov     r9d, 80070057h; char *
0x18003fe48  mov     edx, 867h; void *
0x18003fe4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fe52  mov     eax, 80070057h
0x18003fe57  jmp     loc_18003FD30
0x18003fe5c  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18003fe61  jmp     loc_18003FC0E
0x18003fe66  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18003fe6b  jmp     loc_18003FC8C
0x18003fe70  test    eax, eax
0x18003fe72  jz      short loc_18003FE23
0x18003fe74  jmp     loc_18003FDF5
0x18003fe79  mov     rcx, [rsp+48h+TokenHandle]
0x18003fe7e  jmp     loc_18003FCFE
0x18003fe83  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18003fe88  jmp     loc_18003FD0C
0x18003fe8d  mov     rcx, rbx; hObject
0x18003fe90  call    cs:__imp_CloseHandle
0x18003fe96  jmp     loc_18003FD1F
```
