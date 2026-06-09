# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x14000c11c`
- end: `0x14000c235`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `281`
- prototype: `int __fastcall(_QWORD *lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140017a60`

## callees

- `0x14000a700`
- `0x14000b0f0`
- `0x14000b194`
- `0x14000c11c`
- `0x14000d2ec`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000c1a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000c1da`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000c1a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000c1da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000c161`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000c161`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c1ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c1ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c1bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c1bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c1ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c1ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c197`

## string_xrefs

- `0x14000c213`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // esi
  __int64 v7; // r8
  const char *v8; // r9
  HANDLE ProcessHeap; // rax
  __int64 v10; // r8
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
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        3585,
        (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
    result = --*(_DWORD *)lpMem;
    if ( *(_DWORD *)lpMem )
    {
      if ( v2 )
      {
        result = ReleaseMutex(v2);
        if ( !result )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v10, v11);
      }
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v7, v8);
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
0x14000c11c  mov     [rsp+arg_0], rbx
0x14000c121  mov     [rsp+arg_8], rsi
0x14000c126  push    rdi
0x14000c127  sub     rsp, 20h
0x14000c12b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000c132  mov     rbx, rcx
0x14000c135  jnz     loc_14000C1E6
0x14000c13b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000c142  test    rax, rax
0x14000c145  jz      short loc_14000C154
0x14000c147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c14c  test    al, al
0x14000c14e  jnz     loc_14000C1E6
0x14000c154  mov     rdi, [rbx+8]
0x14000c158  xor     r8d, r8d; bAlertable
0x14000c15b  mov     rcx, rdi; hHandle
0x14000c15e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000c161  call    cs:__imp_WaitForSingleObjectEx
0x14000c167  cmp     eax, 102h
0x14000c16c  jz      short loc_14000C17B
0x14000c16e  test    eax, 0FFFFFF7Fh
0x14000c173  jnz     loc_14000C20E
0x14000c179  jmp     short loc_14000C17D
0x14000c17b  xor     edi, edi
0x14000c17d  mov     eax, [rbx]
0x14000c17f  dec     eax
0x14000c181  mov     [rbx], eax
0x14000c183  mov     eax, [rbx]
0x14000c185  test    eax, eax
0x14000c187  jnz     short loc_14000C1D2
0x14000c189  lea     rcx, [rbx+10h]; this
0x14000c18d  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x14000c192  test    rdi, rdi
0x14000c195  jz      short loc_14000C1B4
0x14000c197  call    cs:__imp_GetLastError
0x14000c19d  mov     rcx, rdi; hMutex
0x14000c1a0  mov     esi, eax
0x14000c1a2  call    cs:__imp_ReleaseMutex
0x14000c1a8  test    eax, eax
0x14000c1aa  jz      short loc_14000C1FE
0x14000c1ac  mov     ecx, esi; dwErrCode
0x14000c1ae  call    cs:__imp_SetLastError
0x14000c1b4  mov     rcx, rbx
0x14000c1b7  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x14000c1bc  call    cs:__imp_GetProcessHeap
0x14000c1c2  mov     r8, rbx; lpMem
0x14000c1c5  xor     edx, edx; dwFlags
0x14000c1c7  mov     rcx, rax; hHeap
0x14000c1ca  call    cs:__imp_HeapFree
0x14000c1d0  jmp     short loc_14000C1EE
0x14000c1d2  test    rdi, rdi
0x14000c1d5  jz      short loc_14000C1EE
0x14000c1d7  mov     rcx, rdi; hMutex
0x14000c1da  call    cs:__imp_ReleaseMutex
0x14000c1e0  test    eax, eax
0x14000c1e2  jz      short loc_14000C225
0x14000c1e4  jmp     short loc_14000C1EE
0x14000c1e6  mov     eax, [rbx]
0x14000c1e8  dec     eax
0x14000c1ea  mov     [rbx], eax
0x14000c1ec  mov     eax, [rbx]
0x14000c1ee  mov     rbx, [rsp+28h+arg_0]
0x14000c1f3  mov     rsi, [rsp+28h+arg_8]
0x14000c1f8  add     rsp, 20h
0x14000c1fc  pop     rdi
0x14000c1fd  retn
0x14000c1fe  mov     rcx, [rsp+28h]; this
0x14000c203  mov     edx, 0A15h; void *
0x14000c208  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c20e  mov     rcx, [rsp+28h]; this
0x14000c213  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000c21a  mov     edx, 0E01h; void *
0x14000c21f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000c225  mov     rcx, [rsp+28h]; this
0x14000c22a  mov     edx, 0A15h; void *
0x14000c22f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
