# GetImpersonationTokenFromProcess(void *,ulong,void * *)

- ea: `0x180013740`
- end: `0x1800137df`
- name: `?GetImpersonationTokenFromProcess@@YAJPEAXKPEAPEAX@Z`
- size: `159`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013b70`

## callees

- `0x180007f8c`
- `0x18000d4e0`
- `0x180013740`
- `0x180014400`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180013779`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180013779`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800137a4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800137a4`

## pseudocode

```c
__int64 __fastcall GetImpersonationTokenFromProcess(HANDLE ProcessHandle, __int64 a2, void **a3)
{
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  if ( OpenProcessToken(ProcessHandle, 0xEu, &TokenHandle) )
  {
    if ( DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, a3) )
    {
      LastError = 0;
      goto LABEL_7;
    }
    v6 = 81;
  }
  else
  {
    v6 = 72;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v6,
                (unsigned int)"onecore\\base\\windows.storage\\src\\camcheckhelpers.h",
                v5);
LABEL_7:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180013740  mov     [rsp+arg_0], rbx
0x180013745  push    rdi
0x180013746  sub     rsp, 30h
0x18001374a  mov     rbx, rcx
0x18001374d  mov     qword ptr [r8], 0
0x180013754  lea     rcx, [rsp+38h+TokenHandle]
0x180013759  mov     [rsp+38h+TokenHandle], 0
0x180013762  xor     edx, edx
0x180013764  mov     rdi, r8
0x180013767  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001376c  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180013771  mov     edx, 0Eh; DesiredAccess
0x180013776  mov     rcx, rbx; ProcessHandle
0x180013779  call    cs:__imp_OpenProcessToken
0x18001377f  test    eax, eax
0x180013781  jnz     short loc_180013788
0x180013783  lea     edx, [rax+48h]
0x180013786  jmp     short loc_1800137B1
0x180013788  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x18001378d  mov     r9d, 2; ImpersonationLevel
0x180013793  mov     [rsp+38h+phNewToken], rdi; phNewToken
0x180013798  xor     r8d, r8d; lpTokenAttributes
0x18001379b  mov     [rsp+38h+TokenType], r9d; TokenType
0x1800137a0  lea     edx, [r9+0Ah]; dwDesiredAccess
0x1800137a4  call    cs:__imp_DuplicateTokenEx
0x1800137aa  test    eax, eax
0x1800137ac  jnz     short loc_1800137C6
0x1800137ae  lea     edx, [rax+51h]; void *
0x1800137b1  mov     rcx, [rsp+38h]; this
0x1800137b6  lea     r8, aOnecoreBaseWin_0; "onecore\\base\\windows.storage\\src\\ca"...
0x1800137bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800137c2  mov     ebx, eax
0x1800137c4  jmp     short loc_1800137C8
0x1800137c6  xor     ebx, ebx
0x1800137c8  lea     rcx, [rsp+38h+TokenHandle]
0x1800137cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800137d2  mov     eax, ebx
0x1800137d4  mov     rbx, [rsp+38h+arg_0]
0x1800137d9  add     rsp, 30h
0x1800137dd  pop     rdi
0x1800137de  retn
```
