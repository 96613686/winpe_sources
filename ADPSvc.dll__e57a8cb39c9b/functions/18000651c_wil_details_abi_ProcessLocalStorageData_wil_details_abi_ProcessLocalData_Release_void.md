# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x18000651c`
- end: `0x180006643`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `295`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800c9540`

## callees

- `0x180004830`
- `0x1800051e0`
- `0x180005290`
- `0x18000651c`
- `0x18000771c`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800065a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800065da`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800065a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800065da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006561`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006561`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800065bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800065ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006597`

## string_xrefs

- `0x180006603`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000661a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006631`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000651c  mov     [rsp+arg_0], rbx
0x180006521  mov     [rsp+arg_8], rsi
0x180006526  push    rdi
0x180006527  sub     rsp, 20h
0x18000652b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006532  mov     rbx, rcx
0x180006535  jnz     loc_1800065E6
0x18000653b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006542  test    rax, rax
0x180006545  jz      short loc_180006554
0x180006547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654c  test    al, al
0x18000654e  jnz     loc_1800065E6
0x180006554  mov     rdi, [rbx+8]
0x180006558  xor     r8d, r8d; bAlertable
0x18000655b  mov     rcx, rdi; hHandle
0x18000655e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006561  call    cs:__imp_WaitForSingleObjectEx
0x180006567  cmp     eax, 102h
0x18000656c  jz      short loc_18000657B
0x18000656e  test    eax, 0FFFFFF7Fh
0x180006573  jnz     loc_180006615
0x180006579  jmp     short loc_18000657D
0x18000657b  xor     edi, edi
0x18000657d  mov     eax, [rbx]
0x18000657f  dec     eax
0x180006581  mov     [rbx], eax
0x180006583  mov     eax, [rbx]
0x180006585  test    eax, eax
0x180006587  jnz     short loc_1800065D2
0x180006589  lea     rcx, [rbx+10h]; this
0x18000658d  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180006592  test    rdi, rdi
0x180006595  jz      short loc_1800065B4
0x180006597  call    cs:__imp_GetLastError
0x18000659d  mov     rcx, rdi; hMutex
0x1800065a0  mov     esi, eax
0x1800065a2  call    cs:__imp_ReleaseMutex
0x1800065a8  test    eax, eax
0x1800065aa  jz      short loc_1800065FE
0x1800065ac  mov     ecx, esi; dwErrCode
0x1800065ae  call    cs:__imp_SetLastError
0x1800065b4  mov     rcx, rbx
0x1800065b7  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x1800065bc  call    cs:__imp_GetProcessHeap
0x1800065c2  mov     r8, rbx; lpMem
0x1800065c5  xor     edx, edx; dwFlags
0x1800065c7  mov     rcx, rax; hHeap
0x1800065ca  call    cs:__imp_HeapFree
0x1800065d0  jmp     short loc_1800065EE
0x1800065d2  test    rdi, rdi
0x1800065d5  jz      short loc_1800065EE
0x1800065d7  mov     rcx, rdi; hMutex
0x1800065da  call    cs:__imp_ReleaseMutex
0x1800065e0  test    eax, eax
0x1800065e2  jz      short loc_18000662C
0x1800065e4  jmp     short loc_1800065EE
0x1800065e6  mov     eax, [rbx]
0x1800065e8  dec     eax
0x1800065ea  mov     [rbx], eax
0x1800065ec  mov     eax, [rbx]
0x1800065ee  mov     rbx, [rsp+28h+arg_0]
0x1800065f3  mov     rsi, [rsp+28h+arg_8]
0x1800065f8  add     rsp, 20h
0x1800065fc  pop     rdi
0x1800065fd  retn
0x1800065fe  mov     rcx, [rsp+28h]; this
0x180006603  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000660a  mov     edx, 0A15h; void *
0x18000660f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006615  mov     rcx, [rsp+28h]; this
0x18000661a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006621  mov     edx, 0E01h; void *
0x180006626  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000662c  mov     rcx, [rsp+28h]; this
0x180006631  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006638  mov     edx, 0A15h; void *
0x18000663d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
