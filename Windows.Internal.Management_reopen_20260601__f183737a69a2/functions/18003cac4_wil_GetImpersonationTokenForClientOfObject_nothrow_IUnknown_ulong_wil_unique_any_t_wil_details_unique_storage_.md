# wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18003cac4`
- end: `0x18003ccac`
- name: `?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ca64`

## callees

- `0x18000a5a4`
- `0x18000a5c4`
- `0x180018698`
- `0x180033500`
- `0x18003ba90`
- `0x18003cac4`
- `0x18003e70c`

## import_xrefs

- `combase!__imp_CoImpersonateClientOfObject` at `0x18003cae1`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18003cae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb7f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003cb6b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003cb6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003cb50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003cb50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cbb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cbb3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003cbcc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003cbcc`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003cc7e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003cc92`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003cc7e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003cc92`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003cc18`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003cc18`

## pseudocode

```c
__int64 __fastcall wil::GetImpersonationTokenForClientOfObject_nothrow(__int64 a1, __int64 a2, HANDLE *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  bool v7; // bl
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  void *v13; // rcx
  unsigned int v14; // edi
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-18h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v18; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  v18 = 0;
  v4 = CoImpersonateClientOfObject(a1, &v18);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v4,
      TokenType);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)v5,
      TokenTypea);
    return v5;
  }
  v7 = v18 != 0;
  if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
  *a3 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, a3) )
    goto LABEL_21;
  LastError = GetLastError();
  if ( !v7 && LastError == 1008 )
  {
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      v12 = 386;
LABEL_15:
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
             v11);
      wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return v5;
    }
    if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*a3);
    v13 = TokenHandle;
    *a3 = 0;
    if ( !DuplicateTokenEx(v13, 8u, 0, SecurityImpersonation, TokenImpersonation, a3) )
    {
      v12 = 388;
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
  if ( !LastError )
  {
LABEL_21:
    if ( v7 )
      CoRevertToSelf();
    return 0;
  }
  v14 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
          (const char *)LastError,
          TokenType);
  if ( v7 )
    CoRevertToSelf();
  return v14;
}

```

## disassembly

```asm
0x18003cac4  mov     rax, rsp
0x18003cac7  mov     [rax+8], rbx
0x18003cacb  mov     [rax+10h], edx
0x18003cace  push    rdi
0x18003cacf  sub     rsp, 30h
0x18003cad3  lea     rdx, [rax+10h]
0x18003cad7  mov     dword ptr [rax+10h], 0
0x18003cade  mov     rdi, r8
0x18003cae1  call    cs:__imp_CoImpersonateClientOfObject
0x18003cae8  nop     dword ptr [rax+rax+00h]
0x18003caed  mov     ebx, eax
0x18003caef  test    eax, eax
0x18003caf1  jns     short loc_18003CB2C
0x18003caf3  mov     rcx, [rsp+38h]; this
0x18003caf8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003caff  mov     r9d, eax; char *
0x18003cb02  mov     edx, 157h; void *
0x18003cb07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb0c  mov     rcx, [rsp+38h]; this
0x18003cb11  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003cb18  mov     r9d, ebx; char *
0x18003cb1b  mov     edx, 177h; void *
0x18003cb20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb25  mov     eax, ebx
0x18003cb27  jmp     loc_18003CCA0
0x18003cb2c  xor     bl, bl
0x18003cb2e  cmp     [rsp+38h+arg_8], 0
0x18003cb33  jz      short loc_18003CB37
0x18003cb35  mov     bl, 1
0x18003cb37  mov     rcx, [rdi]; hObject
0x18003cb3a  lea     rax, [rcx-1]
0x18003cb3e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003cb42  ja      short loc_18003CB49
0x18003cb44  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18003cb49  mov     qword ptr [rdi], 0
0x18003cb50  call    cs:__imp_GetCurrentThread
0x18003cb57  nop     dword ptr [rax+rax+00h]
0x18003cb5c  mov     edx, 8; DesiredAccess
0x18003cb61  mov     r9, rdi; TokenHandle
0x18003cb64  mov     rcx, rax; ThreadHandle
0x18003cb67  lea     r8d, [rdx-7]; OpenAsSelf
0x18003cb6b  call    cs:__imp_OpenThreadToken
0x18003cb72  nop     dword ptr [rax+rax+00h]
0x18003cb77  test    eax, eax
0x18003cb79  jnz     loc_18003CC8E
0x18003cb7f  call    cs:__imp_GetLastError
0x18003cb86  nop     dword ptr [rax+rax+00h]
0x18003cb8b  test    bl, bl
0x18003cb8d  jnz     loc_18003CC5B
0x18003cb93  cmp     eax, 3F0h
0x18003cb98  jnz     loc_18003CC5B
0x18003cb9e  xor     edx, edx
0x18003cba0  mov     [rsp+38h+TokenHandle], 0
0x18003cba9  lea     rcx, [rsp+38h+TokenHandle]
0x18003cbae  call    ?reset@?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003cbb3  call    cs:__imp_GetCurrentProcess
0x18003cbba  nop     dword ptr [rax+rax+00h]
0x18003cbbf  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18003cbc4  mov     edx, 0Ah; DesiredAccess
0x18003cbc9  mov     rcx, rax; ProcessHandle
0x18003cbcc  call    cs:__imp_OpenProcessToken
0x18003cbd3  nop     dword ptr [rax+rax+00h]
0x18003cbd8  test    eax, eax
0x18003cbda  jnz     short loc_18003CBE3
0x18003cbdc  mov     edx, 182h
0x18003cbe1  jmp     short loc_18003CC2D
0x18003cbe3  mov     rcx, [rdi]; hObject
0x18003cbe6  lea     rax, [rcx-1]
0x18003cbea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003cbee  ja      short loc_18003CBF5
0x18003cbf0  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18003cbf5  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18003cbfa  mov     r9d, 2; ImpersonationLevel
0x18003cc00  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x18003cc05  xor     r8d, r8d; lpTokenAttributes
0x18003cc08  mov     qword ptr [rdi], 0
0x18003cc0f  mov     [rsp+38h+TokenType], r9d; TokenType
0x18003cc14  lea     edx, [r9+6]; dwDesiredAccess
0x18003cc18  call    cs:__imp_DuplicateTokenEx
0x18003cc1f  nop     dword ptr [rax+rax+00h]
0x18003cc24  test    eax, eax
0x18003cc26  jnz     short loc_18003CC4F
0x18003cc28  mov     edx, 184h; void *
0x18003cc2d  mov     rcx, [rsp+38h]; this
0x18003cc32  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003cc39  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003cc3e  lea     rcx, [rsp+38h+TokenHandle]
0x18003cc43  mov     ebx, eax
0x18003cc45  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003cc4a  jmp     loc_18003CB25
0x18003cc4f  lea     rcx, [rsp+38h+TokenHandle]
0x18003cc54  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003cc59  jmp     short loc_18003CC9E
0x18003cc5b  test    eax, eax
0x18003cc5d  jz      short loc_18003CC8E
0x18003cc5f  mov     rcx, [rsp+38h]; this
0x18003cc64  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18003cc6b  mov     r9d, eax; char *
0x18003cc6e  mov     edx, 188h; void *
0x18003cc73  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003cc78  mov     edi, eax
0x18003cc7a  test    bl, bl
0x18003cc7c  jz      short loc_18003CC8A
0x18003cc7e  call    cs:__imp_CoRevertToSelf
0x18003cc85  nop     dword ptr [rax+rax+00h]
0x18003cc8a  mov     eax, edi
0x18003cc8c  jmp     short loc_18003CCA0
0x18003cc8e  test    bl, bl
0x18003cc90  jz      short loc_18003CC9E
0x18003cc92  call    cs:__imp_CoRevertToSelf
0x18003cc99  nop     dword ptr [rax+rax+00h]
0x18003cc9e  xor     eax, eax
0x18003cca0  mov     rbx, [rsp+38h+arg_0]
0x18003cca5  add     rsp, 30h
0x18003cca9  pop     rdi
0x18003ccaa  retn
```
