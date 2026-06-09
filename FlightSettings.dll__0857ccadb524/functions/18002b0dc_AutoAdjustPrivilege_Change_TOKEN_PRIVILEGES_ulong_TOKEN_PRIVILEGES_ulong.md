# AutoAdjustPrivilege::Change(_TOKEN_PRIVILEGES *,ulong,_TOKEN_PRIVILEGES *,ulong *)

- ea: `0x18002b0dc`
- end: `0x18002b1a9`
- name: `?Change@AutoAdjustPrivilege@@CAJPEAU_TOKEN_PRIVILEGES@@K0PEAK@Z`
- size: `205`
- prototype: `__int64 __fastcall(PTOKEN_PRIVILEGES NewState, DWORD BufferLength, struct _TOKEN_PRIVILEGES *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002b1b0`
- `0x18002b5a0`

## callees

- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010e9c`
- `0x180017870`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b140`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002b140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b12d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002b12d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002b16e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002b16e`

## string_xrefs

- `0x18002b0fa`: `onecore\base\flighting\flightSettings\broker\libs\inc\AutoAdjustPrivilege.h`
- `0x18002b180`: `onecore\base\flighting\flightSettings\broker\libs\inc\AutoAdjustPrivilege.h`

## pseudocode

```c
__int64 __fastcall AutoAdjustPrivilege::Change(
        PTOKEN_PRIVILEGES NewState,
        DWORD BufferLength,
        struct _TOKEN_PRIVILEGES *a3,
        unsigned int *a4)
{
  unsigned int LastError; // ebx
  HANDLE CurrentProcess; // rax
  const char *v8; // r9
  __int64 v9; // rdx
  int PreviousState; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = a4;
  if ( NewState->PrivilegeCount )
  {
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      if ( AdjustTokenPrivileges(TokenHandle, 0, NewState, BufferLength, 0, 0) )
      {
        LastError = 0;
        goto LABEL_9;
      }
      v9 = 72;
    }
    else
    {
      v9 = 70;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\AutoAdjustPrivilege.h",
                  v8);
LABEL_9:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return LastError;
  }
  LastError = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x33,
    (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\AutoAdjustPrivilege.h",
    (const char *)0x8000FFFFLL,
    PreviousState);
  return LastError;
}

```

## disassembly

```asm
0x18002b0dc  mov     [rsp+arg_0], rbx
0x18002b0e1  mov     [rsp+TokenHandle], r9
0x18002b0e6  push    rdi
0x18002b0e7  sub     rsp, 30h
0x18002b0eb  cmp     dword ptr [rcx], 0
0x18002b0ee  mov     edi, edx
0x18002b0f0  mov     rbx, rcx
0x18002b0f3  jnz     short loc_18002B118
0x18002b0f5  mov     rcx, [rsp+38h]; this
0x18002b0fa  lea     r8, aOnecoreBaseFli_95; "onecore\\base\\flighting\\flightSetting"...
0x18002b101  mov     ebx, 8000FFFFh
0x18002b106  mov     edx, 33h ; '3'; void *
0x18002b10b  mov     r9d, ebx; char *
0x18002b10e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b113  jmp     loc_18002B19C
0x18002b118  xor     edx, edx
0x18002b11a  mov     [rsp+38h+TokenHandle], 0
0x18002b123  lea     rcx, [rsp+38h+TokenHandle]
0x18002b128  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002b12d  call    cs:__imp_GetCurrentProcess
0x18002b133  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18002b138  mov     edx, 28h ; '('; DesiredAccess
0x18002b13d  mov     rcx, rax; ProcessHandle
0x18002b140  call    cs:__imp_OpenProcessToken
0x18002b146  test    eax, eax
0x18002b148  jnz     short loc_18002B14F
0x18002b14a  lea     edx, [rax+46h]
0x18002b14d  jmp     short loc_18002B17B
0x18002b14f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18002b154  mov     r9d, edi; BufferLength
0x18002b157  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x18002b160  mov     r8, rbx; NewState
0x18002b163  xor     edx, edx; DisableAllPrivileges
0x18002b165  mov     [rsp+38h+PreviousState], 0; PreviousState
0x18002b16e  call    cs:__imp_AdjustTokenPrivileges
0x18002b174  test    eax, eax
0x18002b176  jnz     short loc_18002B190
0x18002b178  lea     edx, [rax+48h]; void *
0x18002b17b  mov     rcx, [rsp+38h]; this
0x18002b180  lea     r8, aOnecoreBaseFli_95; "onecore\\base\\flighting\\flightSetting"...
0x18002b187  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b18c  mov     ebx, eax
0x18002b18e  jmp     short loc_18002B192
0x18002b190  xor     ebx, ebx
0x18002b192  lea     rcx, [rsp+38h+TokenHandle]
0x18002b197  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002b19c  mov     eax, ebx
0x18002b19e  mov     rbx, [rsp+38h+arg_0]
0x18002b1a3  add     rsp, 30h
0x18002b1a7  pop     rdi
0x18002b1a8  retn
```
