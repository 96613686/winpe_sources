# _lambda_942f6dc8610eaee085bddeebfbc46684_::operator()

- ea: `0x18008072c`
- end: `0x18008080c`
- name: `_lambda_942f6dc8610eaee085bddeebfbc46684_::operator()`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024e84`

## callees

- `0x180024f38`
- `0x18008070c`
- `0x18008072c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800807e9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800807e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008073d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008073d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18008074a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18008074a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18008076f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18008076f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800807a7`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800807a7`

## string_xrefs

- `0x180080759`: `onecore\windows\accessibletech\common\basicutils.cpp`
- `0x1800807b6`: `onecore\windows\accessibletech\common\basicutils.cpp`

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
  if ( pSessionId != WTSGetActiveConsoleSessionId() )
  {
    pBytesReturned = 0;
    ppBuffer = 0;
    if ( !WTSQuerySessionInformationW(0, 0xFFFFFFFF, WTSInitialProgram, &ppBuffer, &pBytesReturned) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x104,
                    (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
                    v5);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
      return LastError;
    }
    if ( pBytesReturned )
    {
      if ( !(unsigned int)_o__wcsicmp(**a1, ppBuffer) )
        BasicUtils::s_isInRailSession = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
  }
  return 0;
}

```

## disassembly

```asm
0x18008072c  push    rbx
0x18008072e  sub     rsp, 30h
0x180080732  mov     rbx, rcx
0x180080735  mov     [rsp+38h+pSessionId], 0
0x18008073d  call    cs:__imp_GetCurrentProcessId
0x180080743  mov     ecx, eax; dwProcessId
0x180080745  lea     rdx, [rsp+38h+pSessionId]; pSessionId
0x18008074a  call    cs:__imp_ProcessIdToSessionId
0x180080750  test    eax, eax
0x180080752  jnz     short loc_18008076F
0x180080754  mov     rcx, [rsp+38h]; this
0x180080759  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x180080760  mov     edx, 0F8h; void *
0x180080765  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008076a  jmp     loc_180080806
0x18008076f  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180080775  cmp     [rsp+38h+pSessionId], eax
0x180080779  jz      loc_180080804
0x18008077f  lea     rax, [rsp+38h+arg_10]
0x180080784  mov     [rsp+38h+arg_10], 0
0x18008078c  lea     r9, [rsp+38h+ppBuffer]; ppBuffer
0x180080791  mov     [rsp+38h+pBytesReturned], rax; pBytesReturned
0x180080796  xor     r8d, r8d; WTSInfoClass
0x180080799  mov     [rsp+38h+ppBuffer], 0
0x1800807a2  or      edx, 0FFFFFFFFh; SessionId
0x1800807a5  xor     ecx, ecx; hServer
0x1800807a7  call    cs:__imp_WTSQuerySessionInformationW
0x1800807ad  test    eax, eax
0x1800807af  jnz     short loc_1800807D7
0x1800807b1  mov     rcx, [rsp+38h]; this
0x1800807b6  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x1800807bd  mov     edx, 104h; void *
0x1800807c2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800807c7  lea     rcx, [rsp+38h+ppBuffer]
0x1800807cc  mov     ebx, eax
0x1800807ce  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800807d3  mov     eax, ebx
0x1800807d5  jmp     short loc_180080806
0x1800807d7  cmp     [rsp+38h+arg_10], 0
0x1800807dc  jbe     short loc_1800807FA
0x1800807de  mov     rcx, [rbx]
0x1800807e1  mov     rdx, [rsp+38h+ppBuffer]
0x1800807e6  mov     rcx, [rcx]
0x1800807e9  call    cs:__imp__o__wcsicmp
0x1800807ef  test    eax, eax
0x1800807f1  jnz     short loc_1800807FA
0x1800807f3  mov     cs:?s_isInRailSession@BasicUtils@@0_NA, 1; bool BasicUtils::s_isInRailSession
0x1800807fa  lea     rcx, [rsp+38h+ppBuffer]
0x1800807ff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180080804  xor     eax, eax
0x180080806  add     rsp, 30h
0x18008080a  pop     rbx
0x18008080b  retn
```
