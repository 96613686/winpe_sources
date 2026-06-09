# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x18000a388`
- end: `0x18000a4af`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `295`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180107780`

## callees

- `0x180006208`
- `0x1800076a0`
- `0x1800079a4`
- `0x18000a388`
- `0x18000c268`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a3cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a3cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a40e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a446`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a40e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a446`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a436`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a436`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a428`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a403`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a41a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a41a`

## string_xrefs

- `0x18000a46f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a486`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a49d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
0x18000a388  mov     [rsp+arg_0], rbx
0x18000a38d  mov     [rsp+arg_8], rsi
0x18000a392  push    rdi
0x18000a393  sub     rsp, 20h
0x18000a397  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a39e  mov     rbx, rcx
0x18000a3a1  jnz     loc_18000A452
0x18000a3a7  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a3ae  test    rax, rax
0x18000a3b1  jz      short loc_18000A3C0
0x18000a3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3b8  test    al, al
0x18000a3ba  jnz     loc_18000A452
0x18000a3c0  mov     rdi, [rbx+8]
0x18000a3c4  xor     r8d, r8d; bAlertable
0x18000a3c7  mov     rcx, rdi; hHandle
0x18000a3ca  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a3cd  call    cs:__imp_WaitForSingleObjectEx
0x18000a3d3  cmp     eax, 102h
0x18000a3d8  jz      short loc_18000A3E7
0x18000a3da  test    eax, 0FFFFFF7Fh
0x18000a3df  jnz     loc_18000A481
0x18000a3e5  jmp     short loc_18000A3E9
0x18000a3e7  xor     edi, edi
0x18000a3e9  mov     eax, [rbx]
0x18000a3eb  dec     eax
0x18000a3ed  mov     [rbx], eax
0x18000a3ef  mov     eax, [rbx]
0x18000a3f1  test    eax, eax
0x18000a3f3  jnz     short loc_18000A43E
0x18000a3f5  lea     rcx, [rbx+10h]; this
0x18000a3f9  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000a3fe  test    rdi, rdi
0x18000a401  jz      short loc_18000A420
0x18000a403  call    cs:__imp_GetLastError
0x18000a409  mov     rcx, rdi; hMutex
0x18000a40c  mov     esi, eax
0x18000a40e  call    cs:__imp_ReleaseMutex
0x18000a414  test    eax, eax
0x18000a416  jz      short loc_18000A46A
0x18000a418  mov     ecx, esi; dwErrCode
0x18000a41a  call    cs:__imp_SetLastError
0x18000a420  mov     rcx, rbx
0x18000a423  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x18000a428  call    cs:__imp_GetProcessHeap
0x18000a42e  mov     r8, rbx; lpMem
0x18000a431  xor     edx, edx; dwFlags
0x18000a433  mov     rcx, rax; hHeap
0x18000a436  call    cs:__imp_HeapFree
0x18000a43c  jmp     short loc_18000A45A
0x18000a43e  test    rdi, rdi
0x18000a441  jz      short loc_18000A45A
0x18000a443  mov     rcx, rdi; hMutex
0x18000a446  call    cs:__imp_ReleaseMutex
0x18000a44c  test    eax, eax
0x18000a44e  jz      short loc_18000A498
0x18000a450  jmp     short loc_18000A45A
0x18000a452  mov     eax, [rbx]
0x18000a454  dec     eax
0x18000a456  mov     [rbx], eax
0x18000a458  mov     eax, [rbx]
0x18000a45a  mov     rbx, [rsp+28h+arg_0]
0x18000a45f  mov     rsi, [rsp+28h+arg_8]
0x18000a464  add     rsp, 20h
0x18000a468  pop     rdi
0x18000a469  retn
0x18000a46a  mov     rcx, [rsp+28h]; this
0x18000a46f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a476  mov     edx, 0A15h; void *
0x18000a47b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a481  mov     rcx, [rsp+28h]; this
0x18000a486  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a48d  mov     edx, 0E01h; void *
0x18000a492  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a498  mov     rcx, [rsp+28h]; this
0x18000a49d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a4a4  mov     edx, 0A15h; void *
0x18000a4a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
