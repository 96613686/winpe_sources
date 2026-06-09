# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x18000e61c`
- end: `0x18000e743`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `295`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800d0980`

## callees

- `0x1800073fc`
- `0x180008d50`
- `0x180009060`
- `0x18000e61c`
- `0x1800108d4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000e661`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000e661`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e6a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e6da`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e6a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e6da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e6ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e6ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e6ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e697`

## string_xrefs

- `0x18000e703`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e71a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e731`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      wil::details::in1diag3::FailFast_Unexpected(
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
0x18000e61c  mov     [rsp+arg_0], rbx
0x18000e621  mov     [rsp+arg_8], rsi
0x18000e626  push    rdi
0x18000e627  sub     rsp, 20h
0x18000e62b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000e632  mov     rbx, rcx
0x18000e635  jnz     loc_18000E6E6
0x18000e63b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e642  test    rax, rax
0x18000e645  jz      short loc_18000E654
0x18000e647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e64c  test    al, al
0x18000e64e  jnz     loc_18000E6E6
0x18000e654  mov     rdi, [rbx+8]
0x18000e658  xor     r8d, r8d; bAlertable
0x18000e65b  mov     rcx, rdi; hHandle
0x18000e65e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000e661  call    cs:__imp_WaitForSingleObjectEx
0x18000e667  cmp     eax, 102h
0x18000e66c  jz      short loc_18000E67B
0x18000e66e  test    eax, 0FFFFFF7Fh
0x18000e673  jnz     loc_18000E715
0x18000e679  jmp     short loc_18000E67D
0x18000e67b  xor     edi, edi
0x18000e67d  mov     eax, [rbx]
0x18000e67f  dec     eax
0x18000e681  mov     [rbx], eax
0x18000e683  mov     eax, [rbx]
0x18000e685  test    eax, eax
0x18000e687  jnz     short loc_18000E6D2
0x18000e689  lea     rcx, [rbx+10h]; this
0x18000e68d  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000e692  test    rdi, rdi
0x18000e695  jz      short loc_18000E6B4
0x18000e697  call    cs:__imp_GetLastError
0x18000e69d  mov     rcx, rdi; hMutex
0x18000e6a0  mov     esi, eax
0x18000e6a2  call    cs:__imp_ReleaseMutex
0x18000e6a8  test    eax, eax
0x18000e6aa  jz      short loc_18000E6FE
0x18000e6ac  mov     ecx, esi; dwErrCode
0x18000e6ae  call    cs:__imp_SetLastError
0x18000e6b4  mov     rcx, rbx
0x18000e6b7  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x18000e6bc  call    cs:__imp_GetProcessHeap
0x18000e6c2  mov     r8, rbx; lpMem
0x18000e6c5  xor     edx, edx; dwFlags
0x18000e6c7  mov     rcx, rax; hHeap
0x18000e6ca  call    cs:__imp_HeapFree
0x18000e6d0  jmp     short loc_18000E6EE
0x18000e6d2  test    rdi, rdi
0x18000e6d5  jz      short loc_18000E6EE
0x18000e6d7  mov     rcx, rdi; hMutex
0x18000e6da  call    cs:__imp_ReleaseMutex
0x18000e6e0  test    eax, eax
0x18000e6e2  jz      short loc_18000E72C
0x18000e6e4  jmp     short loc_18000E6EE
0x18000e6e6  mov     eax, [rbx]
0x18000e6e8  dec     eax
0x18000e6ea  mov     [rbx], eax
0x18000e6ec  mov     eax, [rbx]
0x18000e6ee  mov     rbx, [rsp+28h+arg_0]
0x18000e6f3  mov     rsi, [rsp+28h+arg_8]
0x18000e6f8  add     rsp, 20h
0x18000e6fc  pop     rdi
0x18000e6fd  retn
0x18000e6fe  mov     rcx, [rsp+28h]; this
0x18000e703  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e70a  mov     edx, 0A15h; void *
0x18000e70f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e715  mov     rcx, [rsp+28h]; this
0x18000e71a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e721  mov     edx, 0E01h; void *
0x18000e726  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000e72c  mov     rcx, [rsp+28h]; this
0x18000e731  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e738  mov     edx, 0A15h; void *
0x18000e73d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
