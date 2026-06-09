# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180009fc8`
- end: `0x18000a0ef`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `295`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180067130`

## callees

- `0x180005f30`
- `0x1800072e0`
- `0x1800075e4`
- `0x180009fc8`
- `0x18000bd98`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a04e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a086`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a04e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a086`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a00d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a00d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a068`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a068`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a076`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a043`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a05a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a05a`

## string_xrefs

- `0x18000a0af`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000a0c6`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000a0dd`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(__int64 *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // esi
  const char *v7; // r9
  HANDLE ProcessHeap; // rax
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return --*(_DWORD *)lpMem;
  }
  else
  {
    v2 = (void *)lpMem[1];
    v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
    if ( v3 == 258 )
    {
      v2 = 0;
    }
    else if ( (v3 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v4);
    }
    result = --*(_DWORD *)lpMem;
    if ( *(_DWORD *)lpMem )
    {
      if ( v2 )
      {
        result = ReleaseMutex(v2);
        if ( !result )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
            v9);
      }
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
            v7);
        SetLastError(LastError);
      }
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(lpMem);
      ProcessHeap = GetProcessHeap();
      return HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009fc8  mov     [rsp+arg_0], rbx
0x180009fcd  mov     [rsp+arg_8], rsi
0x180009fd2  push    rdi
0x180009fd3  sub     rsp, 20h
0x180009fd7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009fde  mov     rbx, rcx
0x180009fe1  jnz     loc_18000A092
0x180009fe7  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009fee  test    rax, rax
0x180009ff1  jz      short loc_18000A000
0x180009ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff8  test    al, al
0x180009ffa  jnz     loc_18000A092
0x18000a000  mov     rdi, [rbx+8]
0x18000a004  xor     r8d, r8d; bAlertable
0x18000a007  mov     rcx, rdi; hHandle
0x18000a00a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a00d  call    cs:__imp_WaitForSingleObjectEx
0x18000a013  cmp     eax, 102h
0x18000a018  jz      short loc_18000A027
0x18000a01a  test    eax, 0FFFFFF7Fh
0x18000a01f  jnz     loc_18000A0C1
0x18000a025  jmp     short loc_18000A029
0x18000a027  xor     edi, edi
0x18000a029  mov     eax, [rbx]
0x18000a02b  dec     eax
0x18000a02d  mov     [rbx], eax
0x18000a02f  mov     eax, [rbx]
0x18000a031  test    eax, eax
0x18000a033  jnz     short loc_18000A07E
0x18000a035  lea     rcx, [rbx+10h]; this
0x18000a039  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000a03e  test    rdi, rdi
0x18000a041  jz      short loc_18000A060
0x18000a043  call    cs:__imp_GetLastError
0x18000a049  mov     rcx, rdi; hMutex
0x18000a04c  mov     esi, eax
0x18000a04e  call    cs:__imp_ReleaseMutex
0x18000a054  test    eax, eax
0x18000a056  jz      short loc_18000A0AA
0x18000a058  mov     ecx, esi; dwErrCode
0x18000a05a  call    cs:__imp_SetLastError
0x18000a060  mov     rcx, rbx
0x18000a063  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x18000a068  call    cs:__imp_GetProcessHeap
0x18000a06e  mov     r8, rbx; lpMem
0x18000a071  xor     edx, edx; dwFlags
0x18000a073  mov     rcx, rax; hHeap
0x18000a076  call    cs:__imp_HeapFree
0x18000a07c  jmp     short loc_18000A09A
0x18000a07e  test    rdi, rdi
0x18000a081  jz      short loc_18000A09A
0x18000a083  mov     rcx, rdi; hMutex
0x18000a086  call    cs:__imp_ReleaseMutex
0x18000a08c  test    eax, eax
0x18000a08e  jz      short loc_18000A0D8
0x18000a090  jmp     short loc_18000A09A
0x18000a092  mov     eax, [rbx]
0x18000a094  dec     eax
0x18000a096  mov     [rbx], eax
0x18000a098  mov     eax, [rbx]
0x18000a09a  mov     rbx, [rsp+28h+arg_0]
0x18000a09f  mov     rsi, [rsp+28h+arg_8]
0x18000a0a4  add     rsp, 20h
0x18000a0a8  pop     rdi
0x18000a0a9  retn
0x18000a0aa  mov     rcx, [rsp+28h]; this
0x18000a0af  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a0b6  mov     edx, 0A15h; void *
0x18000a0bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a0c1  mov     rcx, [rsp+28h]; this
0x18000a0c6  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a0cd  mov     edx, 0E01h; void *
0x18000a0d2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a0d8  mov     rcx, [rsp+28h]; this
0x18000a0dd  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a0e4  mov     edx, 0A15h; void *
0x18000a0e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
