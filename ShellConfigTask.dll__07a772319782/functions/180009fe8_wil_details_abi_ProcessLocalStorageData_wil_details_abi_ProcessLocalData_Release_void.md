# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180009fe8`
- end: `0x18000a10f`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `295`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800320e0`

## callees

- `0x180004e54`
- `0x1800067f4`
- `0x180006cb8`
- `0x180009fe8`
- `0x18000c5d4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a096`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a096`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a088`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a088`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a07a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a07a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a063`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a06e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a0a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a06e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a0a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a02d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a02d`

## string_xrefs

- `0x18000a0cf`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a0e6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a0fd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
0x180009fe8  mov     [rsp+arg_0], rbx
0x180009fed  mov     [rsp+arg_8], rsi
0x180009ff2  push    rdi
0x180009ff3  sub     rsp, 20h
0x180009ff7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009ffe  mov     rbx, rcx
0x18000a001  jnz     loc_18000A0B2
0x18000a007  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a00e  test    rax, rax
0x18000a011  jz      short loc_18000A020
0x18000a013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a018  test    al, al
0x18000a01a  jnz     loc_18000A0B2
0x18000a020  mov     rdi, [rbx+8]
0x18000a024  xor     r8d, r8d; bAlertable
0x18000a027  mov     rcx, rdi; hHandle
0x18000a02a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a02d  call    cs:__imp_WaitForSingleObjectEx
0x18000a033  cmp     eax, 102h
0x18000a038  jz      short loc_18000A047
0x18000a03a  test    eax, 0FFFFFF7Fh
0x18000a03f  jnz     loc_18000A0E1
0x18000a045  jmp     short loc_18000A049
0x18000a047  xor     edi, edi
0x18000a049  mov     eax, [rbx]
0x18000a04b  dec     eax
0x18000a04d  mov     [rbx], eax
0x18000a04f  mov     eax, [rbx]
0x18000a051  test    eax, eax
0x18000a053  jnz     short loc_18000A09E
0x18000a055  lea     rcx, [rbx+10h]; this
0x18000a059  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000a05e  test    rdi, rdi
0x18000a061  jz      short loc_18000A080
0x18000a063  call    cs:__imp_GetLastError
0x18000a069  mov     rcx, rdi; hMutex
0x18000a06c  mov     esi, eax
0x18000a06e  call    cs:__imp_ReleaseMutex
0x18000a074  test    eax, eax
0x18000a076  jz      short loc_18000A0CA
0x18000a078  mov     ecx, esi; dwErrCode
0x18000a07a  call    cs:__imp_SetLastError
0x18000a080  mov     rcx, rbx
0x18000a083  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x18000a088  call    cs:__imp_GetProcessHeap
0x18000a08e  mov     r8, rbx; lpMem
0x18000a091  xor     edx, edx; dwFlags
0x18000a093  mov     rcx, rax; hHeap
0x18000a096  call    cs:__imp_HeapFree
0x18000a09c  jmp     short loc_18000A0BA
0x18000a09e  test    rdi, rdi
0x18000a0a1  jz      short loc_18000A0BA
0x18000a0a3  mov     rcx, rdi; hMutex
0x18000a0a6  call    cs:__imp_ReleaseMutex
0x18000a0ac  test    eax, eax
0x18000a0ae  jz      short loc_18000A0F8
0x18000a0b0  jmp     short loc_18000A0BA
0x18000a0b2  mov     eax, [rbx]
0x18000a0b4  dec     eax
0x18000a0b6  mov     [rbx], eax
0x18000a0b8  mov     eax, [rbx]
0x18000a0ba  mov     rbx, [rsp+28h+arg_0]
0x18000a0bf  mov     rsi, [rsp+28h+arg_8]
0x18000a0c4  add     rsp, 20h
0x18000a0c8  pop     rdi
0x18000a0c9  retn
0x18000a0ca  mov     rcx, [rsp+28h]; this
0x18000a0cf  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a0d6  mov     edx, 0A15h; void *
0x18000a0db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a0e1  mov     rcx, [rsp+28h]; this
0x18000a0e6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a0ed  mov     edx, 0E01h; void *
0x18000a0f2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a0f8  mov     rcx, [rsp+28h]; this
0x18000a0fd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a104  mov     edx, 0A15h; void *
0x18000a109  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
