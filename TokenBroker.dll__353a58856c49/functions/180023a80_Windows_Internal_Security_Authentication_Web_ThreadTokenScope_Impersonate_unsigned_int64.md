# Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)

- ea: `0x180023a80`
- end: `0x180023c43`
- name: `?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z`
- size: `451`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, __int64)`
- caller_count: `66`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ef40`
- `0x1800232e8`
- `0x180024c88`
- `0x18002eb80`
- `0x18002f450`
- `0x18002fc10`
- `0x180030380`
- `0x180033800`
- `0x180054240`
- `0x180055574`
- `0x180057580`
- `0x1800586a8`
- `0x18005a26c`
- `0x18005aa84`
- `0x180069a40`
- `0x18006abe0`
- `0x18006b0c0`
- `0x1800803f0`
- `0x180081890`
- `0x180082e10`
- `0x180083f90`
- `0x1800845d0`
- `0x180084d40`
- `0x180085c40`
- `0x180086a40`
- `0x180087800`
- `0x180088620`
- `0x180089730`
- `0x1800899a0`
- `0x18008b9a0`
- `0x18008c150`
- `0x18008c7d0`
- `0x18008d0b0`
- `0x18008dc10`
- `0x1800a6a30`
- `0x1800a7600`
- `0x1800aef20`
- `0x1800bbcb0`
- `0x1800bd814`
- `0x1800bd970`
- `0x1800bdfe4`
- `0x1800be580`
- `0x1800bebe0`
- `0x1800ca920`
- `0x1800ccf00`
- `0x1800cd8f0`
- `0x1800d1cc0`
- `0x1800d4e70`
- `0x1800de6dc`
- `0x1800e2bf0`

## callees

- `0x18000bd40`
- `0x180023a80`
- `0x180024000`
- `0x1800349d0`
- `0x1800565a0`
- `0x18007c0f0`
- `0x18007c220`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180023b5d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180023b5d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023b16`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023b16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023ab6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023ab6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023bf0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023bf0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023acd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023af0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023c38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023c38`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180023b48`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180023b48`

## string_xrefs

- `0x180023b6c`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x180023bb9`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x180023bda`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x180023c0b`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
        PHANDLE TokenHandle,
        __int64 a2)
{
  char *v4; // rcx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  const char *v10; // r9
  __int64 v12; // rdx
  const char *v13; // r9
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE hToken; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v8 = -2147418113;
    v12 = 525;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
      (const char *)v8,
      v14);
    return v8;
  }
  v4 = (char *)*TokenHandle;
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v4);
  *TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError != -2147023888 )
    {
      v7 = GetLastError();
      v8 = v7;
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      if ( (v8 & 0x80000000) != 0 )
      {
        v12 = 526;
        goto LABEL_23;
      }
    }
  }
  hToken = 0;
  if ( !RevertToSelf() )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x211,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
      v9);
  if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(hToken);
  hToken = 0;
  v8 = UMgrQueryUserToken(a2, &hToken);
  if ( (v8 & 0x80000000) != 0 )
  {
    if ( !SetThreadToken(0, *TokenHandle) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x214,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
        v13);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      TokenHandle,
      0);
  }
  else
  {
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x218,
             (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
             v10);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&hToken);
      return v8;
    }
    *((_BYTE *)TokenHandle + 8) = 1;
  }
  if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hToken);
  return v8;
}

```

## disassembly

```asm
0x180023a80  mov     [rsp+arg_0], rbx
0x180023a85  mov     [rsp+arg_10], rsi
0x180023a8a  push    rdi; int
0x180023a8b  sub     rsp, 20h
0x180023a8f  mov     rsi, rdx
0x180023a92  mov     rdi, rcx
0x180023a95  test    rdx, rdx
0x180023a98  jz      loc_180023BCB
0x180023a9e  mov     rcx, [rcx]; hObject
0x180023aa1  lea     rax, [rcx-1]
0x180023aa5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023aa9  jbe     loc_180023C1D
0x180023aaf  mov     qword ptr [rdi], 0
0x180023ab6  call    cs:__imp_GetCurrentThread
0x180023abc  mov     r9, rdi; TokenHandle
0x180023abf  mov     edx, 0F01FFh; DesiredAccess
0x180023ac4  mov     rcx, rax; ThreadHandle
0x180023ac7  mov     r8d, 1; OpenAsSelf
0x180023acd  call    cs:__imp_OpenThreadToken
0x180023ad3  test    eax, eax
0x180023ad5  jnz     short loc_180023B0D
0x180023ad7  call    cs:__imp_GetLastError
0x180023add  test    eax, eax
0x180023adf  jle     short loc_180023AE9
0x180023ae1  movzx   eax, ax
0x180023ae4  or      eax, 80070000h
0x180023ae9  cmp     eax, 800703F0h
0x180023aee  jz      short loc_180023B0D
0x180023af0  call    cs:__imp_GetLastError
0x180023af6  mov     ebx, eax
0x180023af8  test    eax, eax
0x180023afa  jle     short loc_180023B05
0x180023afc  movzx   ebx, ax
0x180023aff  or      ebx, 80070000h
0x180023b05  test    ebx, ebx
0x180023b07  js      loc_180023C27
0x180023b0d  mov     [rsp+28h+hToken], 0
0x180023b16  call    cs:__imp_RevertToSelf
0x180023b1c  test    eax, eax
0x180023b1e  jz      loc_180023BB4
0x180023b24  mov     rcx, [rsp+28h+hToken]; hObject
0x180023b29  lea     rax, [rcx-1]
0x180023b2d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023b31  jbe     loc_180023C2E
0x180023b37  lea     rdx, [rsp+28h+hToken]
0x180023b3c  mov     [rsp+28h+hToken], 0
0x180023b45  mov     rcx, rsi
0x180023b48  call    cs:__imp_UMgrQueryUserToken
0x180023b4e  mov     ebx, eax
0x180023b50  test    eax, eax
0x180023b52  js      loc_180023BEB
0x180023b58  mov     rcx, [rsp+28h+hToken]; hToken
0x180023b5d  call    cs:__imp_ImpersonateLoggedOnUser
0x180023b63  test    eax, eax
0x180023b65  jnz     short loc_180023B8B
0x180023b67  mov     rcx, [rsp+28h]; this
0x180023b6c  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x180023b73  mov     edx, 218h; void *
0x180023b78  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023b7d  lea     rcx, [rsp+28h+hToken]; this
0x180023b82  mov     ebx, eax
0x180023b84  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x180023b89  jmp     short loc_180023BA2
0x180023b8b  mov     byte ptr [rdi+8], 1
0x180023b8f  mov     rcx, [rsp+28h+hToken]; hObject
0x180023b94  lea     rax, [rcx-1]
0x180023b98  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023b9c  jbe     loc_180023C38
0x180023ba2  mov     rsi, [rsp+28h+arg_10]
0x180023ba7  mov     eax, ebx
0x180023ba9  mov     rbx, [rsp+28h+arg_0]
0x180023bae  add     rsp, 20h
0x180023bb2  pop     rdi
0x180023bb3  retn
0x180023bb4  mov     rcx, [rsp+28h]; this
0x180023bb9  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x180023bc0  mov     edx, 211h; void *
0x180023bc5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023bcb  mov     ebx, 8000FFFFh
0x180023bd0  mov     edx, 20Dh; void *
0x180023bd5  mov     rcx, [rsp+28h]; this
0x180023bda  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x180023be1  mov     r9d, ebx; char *
0x180023be4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023be9  jmp     short loc_180023BA2
0x180023beb  mov     rdx, [rdi]; Token
0x180023bee  xor     ecx, ecx; Thread
0x180023bf0  call    cs:__imp_SetThreadToken
0x180023bf6  test    eax, eax
0x180023bf8  jz      short loc_180023C06
0x180023bfa  xor     edx, edx
0x180023bfc  mov     rcx, rdi
0x180023bff  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180023c04  jmp     short loc_180023B8F
0x180023c06  mov     rcx, [rsp+28h]; this
0x180023c0b  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x180023c12  mov     edx, 214h; void *
0x180023c17  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023c1d  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180023c22  jmp     loc_180023AAF
0x180023c27  mov     edx, 20Eh
0x180023c2c  jmp     short loc_180023BD5
0x180023c2e  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180023c33  jmp     loc_180023B37
0x180023c38  call    cs:__imp_CloseHandle
0x180023c3e  jmp     loc_180023BA2
```
