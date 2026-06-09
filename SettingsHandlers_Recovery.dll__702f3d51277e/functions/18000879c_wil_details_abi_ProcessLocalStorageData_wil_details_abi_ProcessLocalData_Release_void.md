# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x18000879c`
- end: `0x1800088b7`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `283`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002ab70`

## callees

- `0x180004450`
- `0x1800059e0`
- `0x180005cf0`
- `0x18000879c`
- `0x18000a49c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800087e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800087e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008822`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000885a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008822`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000885a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000883c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000883c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000884a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000884a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000882e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000882e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008817`

## string_xrefs

- `0x180008883`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800088a5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  int result; // eax
  DWORD LastError; // esi
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  const char *v11; // r9
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v4, v5, v6);
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
            v11);
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
            v9);
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
0x18000879c  mov     [rsp+arg_0], rbx
0x1800087a1  mov     [rsp+arg_8], rsi
0x1800087a6  push    rdi
0x1800087a7  sub     rsp, 20h
0x1800087ab  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800087b2  mov     rbx, rcx
0x1800087b5  jnz     loc_180008866
0x1800087bb  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800087c2  test    rax, rax
0x1800087c5  jz      short loc_1800087D4
0x1800087c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087cc  test    al, al
0x1800087ce  jnz     loc_180008866
0x1800087d4  mov     rdi, [rbx+8]
0x1800087d8  xor     r8d, r8d; bAlertable
0x1800087db  mov     rcx, rdi; hHandle
0x1800087de  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800087e1  call    cs:__imp_WaitForSingleObjectEx
0x1800087e7  cmp     eax, 102h
0x1800087ec  jz      short loc_1800087FB
0x1800087ee  test    eax, 0FFFFFF7Fh
0x1800087f3  jnz     loc_180008895
0x1800087f9  jmp     short loc_1800087FD
0x1800087fb  xor     edi, edi
0x1800087fd  mov     eax, [rbx]
0x1800087ff  dec     eax
0x180008801  mov     [rbx], eax
0x180008803  mov     eax, [rbx]
0x180008805  test    eax, eax
0x180008807  jnz     short loc_180008852
0x180008809  lea     rcx, [rbx+10h]; this
0x18000880d  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180008812  test    rdi, rdi
0x180008815  jz      short loc_180008834
0x180008817  call    cs:__imp_GetLastError
0x18000881d  mov     rcx, rdi; hMutex
0x180008820  mov     esi, eax
0x180008822  call    cs:__imp_ReleaseMutex
0x180008828  test    eax, eax
0x18000882a  jz      short loc_18000887E
0x18000882c  mov     ecx, esi; dwErrCode
0x18000882e  call    cs:__imp_SetLastError
0x180008834  mov     rcx, rbx
0x180008837  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x18000883c  call    cs:__imp_GetProcessHeap
0x180008842  mov     r8, rbx; lpMem
0x180008845  xor     edx, edx; dwFlags
0x180008847  mov     rcx, rax; hHeap
0x18000884a  call    cs:__imp_HeapFree
0x180008850  jmp     short loc_18000886E
0x180008852  test    rdi, rdi
0x180008855  jz      short loc_18000886E
0x180008857  mov     rcx, rdi; hMutex
0x18000885a  call    cs:__imp_ReleaseMutex
0x180008860  test    eax, eax
0x180008862  jz      short loc_1800088A0
0x180008864  jmp     short loc_18000886E
0x180008866  mov     eax, [rbx]
0x180008868  dec     eax
0x18000886a  mov     [rbx], eax
0x18000886c  mov     eax, [rbx]
0x18000886e  mov     rbx, [rsp+28h+arg_0]
0x180008873  mov     rsi, [rsp+28h+arg_8]
0x180008878  add     rsp, 20h
0x18000887c  pop     rdi
0x18000887d  retn
0x18000887e  mov     rcx, [rsp+28h]; this
0x180008883  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000888a  mov     edx, 0A15h; void *
0x18000888f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008895  mov     rcx, [rsp+28h]; this
0x18000889a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800088a0  mov     rcx, [rsp+28h]; this
0x1800088a5  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800088ac  mov     edx, 0A15h; void *
0x1800088b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
