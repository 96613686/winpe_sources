# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x180007f28`
- end: `0x1800080c6`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `414`
- prototype: `__int64 __fastcall(__int64, DWORD, HANDLE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007ac8`
- `0x180007bc0`

## callees

- `0x180006224`
- `0x180007a64`
- `0x180007f28`
- `0x1800081c8`
- `0x18000820c`
- `0x180008230`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800080a0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800080ae`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800080a0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800080ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007fc5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007fc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007fb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007fb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007ff5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007ff5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000800c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000800c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fd3`
- `combase!__imp_CoImpersonateClientOfObject` at `0x180007f48`
- `combase!__imp_CoImpersonateClientOfObject` at `0x180007f48`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000804c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000804c`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, DWORD a2, HANDLE *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  bool v8; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  HANDLE CurrentProcess; // rax
  const char *v14; // r9
  __int64 v15; // rdx
  HANDLE v16; // rcx
  unsigned int v17; // edi
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-18h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  LODWORD(TokenHandle) = 0;
  v5 = CoImpersonateClientOfObject(a1, &TokenHandle);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
      (const char *)(unsigned int)v5,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
      (const char *)v6,
      TokenTypea);
    return v6;
  }
  v8 = (_DWORD)TokenHandle != 0;
  if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, a2, 1, a3) )
    goto LABEL_21;
  LastError = GetLastError();
  if ( !v8 && LastError == 1008 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, a2 | 2, &TokenHandle) )
    {
      v15 = 386;
LABEL_15:
      v6 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v15,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
             v14);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v6;
    }
    if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
    v16 = TokenHandle;
    *a3 = 0;
    if ( !DuplicateTokenEx(v16, a2, 0, SecurityImpersonation, TokenImpersonation, a3) )
    {
      v15 = 388;
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  if ( !LastError )
  {
LABEL_21:
    if ( v8 )
      CoRevertToSelf();
    return 0;
  }
  v17 = wil::details::in1diag3::Return_Win32(retaddr, v11, v12, (const char *)LastError, TokenType);
  if ( v8 )
    CoRevertToSelf();
  return v17;
}

```

## disassembly

```asm
0x180007f28  mov     rax, rsp
0x180007f2b  mov     [rax+8], rbx
0x180007f2f  mov     [rax+10h], rsi
0x180007f33  push    rdi
0x180007f34  sub     rsp, 30h
0x180007f38  mov     esi, edx
0x180007f3a  mov     dword ptr [rax+20h], 0
0x180007f41  lea     rdx, [rax+20h]
0x180007f45  mov     rdi, r8
0x180007f48  call    cs:__imp_CoImpersonateClientOfObject
0x180007f4e  mov     ebx, eax
0x180007f50  test    eax, eax
0x180007f52  jns     short loc_180007F8D
0x180007f54  mov     rcx, [rsp+38h]; this
0x180007f59  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x180007f60  mov     r9d, eax; char *
0x180007f63  mov     edx, 157h; void *
0x180007f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f6d  mov     rcx, [rsp+38h]; this
0x180007f72  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x180007f79  mov     r9d, ebx; char *
0x180007f7c  mov     edx, 177h; void *
0x180007f81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f86  mov     eax, ebx
0x180007f88  jmp     loc_1800080B6
0x180007f8d  xor     bl, bl
0x180007f8f  cmp     dword ptr [rsp+38h+TokenHandle], 0
0x180007f94  jz      short loc_180007F98
0x180007f96  mov     bl, 1
0x180007f98  mov     rcx, [rdi]; hObject
0x180007f9b  lea     rax, [rcx-1]
0x180007f9f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007fa3  ja      short loc_180007FAA
0x180007fa5  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180007faa  mov     qword ptr [rdi], 0
0x180007fb1  call    cs:__imp_GetCurrentThread
0x180007fb7  mov     r9, rdi; TokenHandle
0x180007fba  mov     r8d, 1; OpenAsSelf
0x180007fc0  mov     rcx, rax; ThreadHandle
0x180007fc3  mov     edx, esi; DesiredAccess
0x180007fc5  call    cs:__imp_OpenThreadToken
0x180007fcb  test    eax, eax
0x180007fcd  jnz     loc_1800080AA
0x180007fd3  call    cs:__imp_GetLastError
0x180007fd9  test    bl, bl
0x180007fdb  jnz     loc_180008089
0x180007fe1  cmp     eax, 3F0h
0x180007fe6  jnz     loc_180008089
0x180007fec  mov     [rsp+38h+TokenHandle], 0
0x180007ff5  call    cs:__imp_GetCurrentProcess
0x180007ffb  mov     edx, esi
0x180007ffd  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180008002  mov     ebx, 2
0x180008007  mov     rcx, rax; ProcessHandle
0x18000800a  or      edx, ebx; DesiredAccess
0x18000800c  call    cs:__imp_OpenProcessToken
0x180008012  test    eax, eax
0x180008014  jnz     short loc_18000801D
0x180008016  mov     edx, 182h
0x18000801b  jmp     short loc_18000805B
0x18000801d  mov     rcx, [rdi]; hObject
0x180008020  lea     rax, [rcx-1]
0x180008024  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008028  ja      short loc_18000802F
0x18000802a  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18000802f  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x180008034  mov     r9d, ebx; ImpersonationLevel
0x180008037  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x18000803c  xor     r8d, r8d; lpTokenAttributes
0x18000803f  mov     edx, esi; dwDesiredAccess
0x180008041  mov     [rsp+38h+TokenType], ebx; TokenType
0x180008045  mov     qword ptr [rdi], 0
0x18000804c  call    cs:__imp_DuplicateTokenEx
0x180008052  test    eax, eax
0x180008054  jnz     short loc_18000807D
0x180008056  mov     edx, 184h; void *
0x18000805b  mov     rcx, [rsp+38h]; this
0x180008060  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x180008067  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000806c  lea     rcx, [rsp+38h+TokenHandle]
0x180008071  mov     ebx, eax
0x180008073  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008078  jmp     loc_180007F86
0x18000807d  lea     rcx, [rsp+38h+TokenHandle]
0x180008082  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008087  jmp     short loc_1800080B4
0x180008089  test    eax, eax
0x18000808b  jz      short loc_1800080AA
0x18000808d  mov     rcx, [rsp+38h]; this
0x180008092  mov     r9d, eax; char *
0x180008095  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000809a  mov     edi, eax
0x18000809c  test    bl, bl
0x18000809e  jz      short loc_1800080A6
0x1800080a0  call    cs:__imp_CoRevertToSelf
0x1800080a6  mov     eax, edi
0x1800080a8  jmp     short loc_1800080B6
0x1800080aa  test    bl, bl
0x1800080ac  jz      short loc_1800080B4
0x1800080ae  call    cs:__imp_CoRevertToSelf
0x1800080b4  xor     eax, eax
0x1800080b6  mov     rbx, [rsp+38h+arg_0]
0x1800080bb  mov     rsi, [rsp+38h+arg_8]
0x1800080c0  add     rsp, 30h
0x1800080c4  pop     rdi
0x1800080c5  retn
```
