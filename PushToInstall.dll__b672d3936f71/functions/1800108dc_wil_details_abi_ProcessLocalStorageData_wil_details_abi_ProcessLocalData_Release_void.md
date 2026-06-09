# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x1800108dc`
- end: `0x1800109f7`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `283`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004ead0`

## callees

- `0x18000ec44`
- `0x18000f5a0`
- `0x18000f650`
- `0x1800108dc`
- `0x180011afc`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010921`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010921`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010962`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001099a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010962`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001099a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001098a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001098a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001097c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001097c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010957`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001096e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001096e`

## string_xrefs

- `0x1800109c3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800109e5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(__int64 *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
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
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
0x1800108dc  mov     [rsp+arg_0], rbx
0x1800108e1  mov     [rsp+arg_8], rsi
0x1800108e6  push    rdi
0x1800108e7  sub     rsp, 20h
0x1800108eb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800108f2  mov     rbx, rcx
0x1800108f5  jnz     loc_1800109A6
0x1800108fb  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180010902  test    rax, rax
0x180010905  jz      short loc_180010914
0x180010907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001090c  test    al, al
0x18001090e  jnz     loc_1800109A6
0x180010914  mov     rdi, [rbx+8]
0x180010918  xor     r8d, r8d; bAlertable
0x18001091b  mov     rcx, rdi; hHandle
0x18001091e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010921  call    cs:__imp_WaitForSingleObjectEx
0x180010927  cmp     eax, 102h
0x18001092c  jz      short loc_18001093B
0x18001092e  test    eax, 0FFFFFF7Fh
0x180010933  jnz     loc_1800109D5
0x180010939  jmp     short loc_18001093D
0x18001093b  xor     edi, edi
0x18001093d  mov     eax, [rbx]
0x18001093f  dec     eax
0x180010941  mov     [rbx], eax
0x180010943  mov     eax, [rbx]
0x180010945  test    eax, eax
0x180010947  jnz     short loc_180010992
0x180010949  lea     rcx, [rbx+10h]; this
0x18001094d  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180010952  test    rdi, rdi
0x180010955  jz      short loc_180010974
0x180010957  call    cs:__imp_GetLastError
0x18001095d  mov     rcx, rdi; hMutex
0x180010960  mov     esi, eax
0x180010962  call    cs:__imp_ReleaseMutex
0x180010968  test    eax, eax
0x18001096a  jz      short loc_1800109BE
0x18001096c  mov     ecx, esi; dwErrCode
0x18001096e  call    cs:__imp_SetLastError
0x180010974  mov     rcx, rbx
0x180010977  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x18001097c  call    cs:__imp_GetProcessHeap
0x180010982  mov     r8, rbx; lpMem
0x180010985  xor     edx, edx; dwFlags
0x180010987  mov     rcx, rax; hHeap
0x18001098a  call    cs:__imp_HeapFree
0x180010990  jmp     short loc_1800109AE
0x180010992  test    rdi, rdi
0x180010995  jz      short loc_1800109AE
0x180010997  mov     rcx, rdi; hMutex
0x18001099a  call    cs:__imp_ReleaseMutex
0x1800109a0  test    eax, eax
0x1800109a2  jz      short loc_1800109E0
0x1800109a4  jmp     short loc_1800109AE
0x1800109a6  mov     eax, [rbx]
0x1800109a8  dec     eax
0x1800109aa  mov     [rbx], eax
0x1800109ac  mov     eax, [rbx]
0x1800109ae  mov     rbx, [rsp+28h+arg_0]
0x1800109b3  mov     rsi, [rsp+28h+arg_8]
0x1800109b8  add     rsp, 20h
0x1800109bc  pop     rdi
0x1800109bd  retn
0x1800109be  mov     rcx, [rsp+28h]; this
0x1800109c3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800109ca  mov     edx, 0A15h; void *
0x1800109cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800109d5  mov     rcx, [rsp+28h]; this
0x1800109da  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800109e0  mov     rcx, [rsp+28h]; this
0x1800109e5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800109ec  mov     edx, 0A15h; void *
0x1800109f1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
