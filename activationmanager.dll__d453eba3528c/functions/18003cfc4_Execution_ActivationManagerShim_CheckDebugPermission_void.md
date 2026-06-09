# Execution::ActivationManagerShim::_CheckDebugPermission(void)

- ea: `0x18003cfc4`
- end: `0x18003d0bc`
- name: `?_CheckDebugPermission@ActivationManagerShim@Execution@@IEAAJXZ`
- size: `248`
- prototype: `int(Execution::ActivationManagerShim *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006eb00`
- `0x18006f4c0`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x18003cfc4`
- `0x180044408`
- `0x180044514`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d018`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d018`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d001`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0ae`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d03a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d042`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d03a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d042`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003cfce`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003cfce`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18003d05e`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18003d05e`

## pseudocode

```c
__int64 __fastcall Execution::ActivationManagerShim::_CheckDebugPermission(Execution::ActivationManagerShim *this)
{
  HRESULT v1; // eax
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  int v5; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  Execution::ActivationManagerShim *v9; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  v9 = this;
  v1 = CoImpersonateClient();
  LastError = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C7,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v1,
      v7);
    return LastError;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x6D0,
                  (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
                  v4);
    CoRevertToSelf();
LABEL_7:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return LastError;
  }
  CoRevertToSelf();
  LOBYTE(v9) = 0;
  v5 = CapabilityCheck(TokenHandle, L"ID_CAP_DEBUG", &v9);
  if ( v5 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x6D4,
                  (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
                  (const char *)(unsigned int)v5,
                  v7);
    goto LABEL_7;
  }
  LastError = (_BYTE)v9 == 0 ? 0x80070005 : 0;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18003cfc4  mov     [rsp+arg_0], rcx
0x18003cfc9  push    rbx; int
0x18003cfca  sub     rsp, 20h
0x18003cfce  call    cs:__imp_CoImpersonateClient
0x18003cfd4  mov     ebx, eax
0x18003cfd6  test    eax, eax
0x18003cfd8  jns     short loc_18003CFF8
0x18003cfda  mov     rcx, [rsp+28h]; this
0x18003cfdf  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003cfe6  mov     r9d, eax; char *
0x18003cfe9  mov     edx, 6C7h; void *
0x18003cfee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cff3  jmp     loc_18003D0B4
0x18003cff8  mov     [rsp+28h+TokenHandle], 0
0x18003d001  call    cs:__imp_GetCurrentThread
0x18003d007  mov     edx, 8; DesiredAccess
0x18003d00c  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18003d011  mov     rcx, rax; ThreadHandle
0x18003d014  lea     r8d, [rdx-7]; OpenAsSelf
0x18003d018  call    cs:__imp_OpenThreadToken
0x18003d01e  test    eax, eax
0x18003d020  jnz     short loc_18003D042
0x18003d022  mov     rcx, [rsp+28h]; this
0x18003d027  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003d02e  mov     edx, 6D0h; void *
0x18003d033  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d038  mov     ebx, eax
0x18003d03a  call    cs:__imp_CoRevertToSelf
0x18003d040  jmp     short loc_18003D083
0x18003d042  call    cs:__imp_CoRevertToSelf
0x18003d048  mov     rcx, [rsp+28h+TokenHandle]
0x18003d04d  lea     r8, [rsp+28h+arg_0]
0x18003d052  lea     rdx, aIdCapDebug; "ID_CAP_DEBUG"
0x18003d059  mov     byte ptr [rsp+28h+arg_0], 0
0x18003d05e  call    cs:__imp_CapabilityCheck
0x18003d064  test    eax, eax
0x18003d066  jns     short loc_18003D08F
0x18003d068  mov     rcx, [rsp+28h]; this
0x18003d06d  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003d074  mov     r9d, eax; char *
0x18003d077  mov     edx, 6D4h; void *
0x18003d07c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18003d081  mov     ebx, eax
0x18003d083  lea     rcx, [rsp+28h+TokenHandle]
0x18003d088  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003d08d  jmp     short loc_18003D0B4
0x18003d08f  mov     al, byte ptr [rsp+28h+arg_0]
0x18003d093  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18003d098  neg     al
0x18003d09a  sbb     ebx, ebx
0x18003d09c  not     ebx
0x18003d09e  and     ebx, 80070005h
0x18003d0a4  lea     rdx, [rcx-1]
0x18003d0a8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003d0ac  ja      short loc_18003D0B4
0x18003d0ae  call    cs:__imp_CloseHandle
0x18003d0b4  mov     eax, ebx
0x18003d0b6  add     rsp, 20h
0x18003d0ba  pop     rbx
0x18003d0bb  retn
```
