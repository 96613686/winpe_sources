# UserService::GetCurrentProcessSessionId(void)

- ea: `0x180029a58`
- end: `0x180029ae9`
- name: `?GetCurrentProcessSessionId@UserService@@AEAAKXZ`
- size: `145`
- prototype: `unsigned int __fastcall(UserService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x180059280`

## callees

- `0x180004a58`
- `0x180004a98`
- `0x180005028`
- `0x180029a58`
- `0x18002c570`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a8e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180029a84`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180029a84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029a6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029a6d`

## string_xrefs

- `0x180029aa6`: `NTUserService failed to retrieve sessionId, processId = %u, hr:0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserService::GetCurrentProcessSessionId(UserService *this)
{
  DWORD CurrentProcessId; // ebx
  signed int LastError; // eax
  DWORD pSessionId; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v5[32]; // [rsp+28h] [rbp-30h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  pSessionId = -1;
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    cdp::detail::StringFormat(
      v5,
      "NTUserService failed to retrieve sessionId, processId = %u, hr:0x%08x",
      CurrentProcessId,
      LastError);
    shared::LogMessage(1, v5);
    std::string::_Tidy_deallocate(v5);
  }
  return pSessionId;
}

```

## disassembly

```asm
0x180029a58  push    rbx
0x180029a5a  sub     rsp, 50h
0x180029a5e  mov     rax, cs:__security_cookie
0x180029a65  xor     rax, rsp
0x180029a68  mov     [rsp+58h+var_10], rax
0x180029a6d  call    cs:__imp_GetCurrentProcessId
0x180029a73  mov     ebx, eax
0x180029a75  mov     [rsp+58h+pSessionId], 0FFFFFFFFh
0x180029a7d  lea     rdx, [rsp+58h+pSessionId]; pSessionId
0x180029a82  mov     ecx, eax; dwProcessId
0x180029a84  call    cs:__imp_ProcessIdToSessionId
0x180029a8a  test    eax, eax
0x180029a8c  jnz     short loc_180029AD2
0x180029a8e  call    cs:__imp_GetLastError
0x180029a94  test    eax, eax
0x180029a96  jle     short loc_180029AA0
0x180029a98  movzx   eax, ax
0x180029a9b  or      eax, 80070000h
0x180029aa0  mov     r9d, eax
0x180029aa3  mov     r8d, ebx
0x180029aa6  lea     rdx, aNtuserserviceF; "NTUserService failed to retrieve sessio"...
0x180029aad  lea     rcx, [rsp+58h+var_30]
0x180029ab2  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180029ab7  nop
0x180029ab8  lea     rdx, [rsp+58h+var_30]
0x180029abd  mov     ecx, 1
0x180029ac2  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x180029ac7  nop
0x180029ac8  lea     rcx, [rsp+58h+var_30]
0x180029acd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180029ad2  mov     eax, [rsp+58h+pSessionId]
0x180029ad6  mov     rcx, [rsp+58h+var_10]
0x180029adb  xor     rcx, rsp; StackCookie
0x180029ade  call    __security_check_cookie
0x180029ae3  add     rsp, 50h
0x180029ae7  pop     rbx
0x180029ae8  retn
```
