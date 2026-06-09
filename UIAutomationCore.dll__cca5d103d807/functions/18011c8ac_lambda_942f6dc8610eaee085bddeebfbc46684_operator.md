# _lambda_942f6dc8610eaee085bddeebfbc46684_::operator()

- ea: `0x18011c8ac`
- end: `0x18011c98a`
- name: `_lambda_942f6dc8610eaee085bddeebfbc46684_::operator()`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18011c7f8`

## callees

- `0x18011c8ac`
- `0x1801b62e0`
- `0x1802bf4a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011c96a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011c96a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18011c8ca`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18011c8ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18011c8bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18011c8bd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18011c8d4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18011c8d4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18011c928`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18011c928`

## string_xrefs

- `0x18011c8ed`: `onecore\windows\accessibletech\common\basicutils.cpp`
- `0x18011c937`: `onecore\windows\accessibletech\common\basicutils.cpp`

## pseudocode

```c
__int64 __fastcall lambda_942f6dc8610eaee085bddeebfbc46684_::operator()(_QWORD **a1)
{
  DWORD CurrentProcessId; // eax
  const char *v3; // r9
  const char *v5; // r9
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD pSessionId; // [rsp+48h] [rbp+10h] BYREF
  DWORD pBytesReturned; // [rsp+50h] [rbp+18h] BYREF
  LPWSTR ppBuffer; // [rsp+58h] [rbp+20h] BYREF

  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xF8,
             (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
             v3);
  if ( pSessionId == WTSGetActiveConsoleSessionId() )
    return 0;
  pBytesReturned = 0;
  ppBuffer = 0;
  if ( WTSQuerySessionInformationW(0, 0xFFFFFFFF, WTSInitialProgram, &ppBuffer, &pBytesReturned) )
  {
    if ( pBytesReturned )
    {
      if ( !(unsigned int)_o__wcsicmp(**a1, ppBuffer) )
        BasicUtils::s_isInRailSession = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
    return 0;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x104,
                (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
                v5);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
  return LastError;
}

```

## disassembly

```asm
0x18011c8ac  push    rbx
0x18011c8ae  sub     rsp, 30h
0x18011c8b2  mov     rbx, rcx
0x18011c8b5  mov     [rsp+38h+pSessionId], 0
0x18011c8bd  call    cs:__imp_GetCurrentProcessId
0x18011c8c3  mov     ecx, eax; dwProcessId
0x18011c8c5  lea     rdx, [rsp+38h+pSessionId]; pSessionId
0x18011c8ca  call    cs:__imp_ProcessIdToSessionId
0x18011c8d0  test    eax, eax
0x18011c8d2  jz      short loc_18011C8E8
0x18011c8d4  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18011c8da  cmp     [rsp+38h+pSessionId], eax
0x18011c8de  jnz     short loc_18011C900
0x18011c8e0  xor     eax, eax
0x18011c8e2  add     rsp, 30h
0x18011c8e6  pop     rbx
0x18011c8e7  retn
0x18011c8e8  mov     rcx, [rsp+38h]; this
0x18011c8ed  lea     r8, aOnecoreWindows_41; "onecore\\windows\\accessibletech\\commo"...
0x18011c8f4  mov     edx, 0F8h; void *
0x18011c8f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011c8fe  jmp     short loc_18011C8E2
0x18011c900  lea     rax, [rsp+38h+arg_10]
0x18011c905  mov     [rsp+38h+arg_10], 0
0x18011c90d  lea     r9, [rsp+38h+ppBuffer]; ppBuffer
0x18011c912  mov     [rsp+38h+pBytesReturned], rax; pBytesReturned
0x18011c917  xor     r8d, r8d; WTSInfoClass
0x18011c91a  mov     [rsp+38h+ppBuffer], 0
0x18011c923  or      edx, 0FFFFFFFFh; SessionId
0x18011c926  xor     ecx, ecx; hServer
0x18011c928  call    cs:__imp_WTSQuerySessionInformationW
0x18011c92e  test    eax, eax
0x18011c930  jnz     short loc_18011C958
0x18011c932  mov     rcx, [rsp+38h]; this
0x18011c937  lea     r8, aOnecoreWindows_41; "onecore\\windows\\accessibletech\\commo"...
0x18011c93e  mov     edx, 104h; void *
0x18011c943  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011c948  lea     rcx, [rsp+38h+ppBuffer]
0x18011c94d  mov     ebx, eax
0x18011c94f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18011c954  mov     eax, ebx
0x18011c956  jmp     short loc_18011C8E2
0x18011c958  cmp     [rsp+38h+arg_10], 0
0x18011c95d  jbe     short loc_18011C97B
0x18011c95f  mov     rcx, [rbx]
0x18011c962  mov     rdx, [rsp+38h+ppBuffer]
0x18011c967  mov     rcx, [rcx]
0x18011c96a  call    cs:__imp__o__wcsicmp
0x18011c970  test    eax, eax
0x18011c972  jnz     short loc_18011C97B
0x18011c974  mov     cs:?s_isInRailSession@BasicUtils@@0_NA, 1; bool BasicUtils::s_isInRailSession
0x18011c97b  lea     rcx, [rsp+38h+ppBuffer]
0x18011c980  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18011c985  jmp     loc_18011C8E0
```
