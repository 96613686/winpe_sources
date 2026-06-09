# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x18000832c`
- end: `0x1800084cc`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `416`
- prototype: `int __fastcall(__int64 *lpMem)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180011a60`

## callees

- `0x180007098`
- `0x1800079e0`
- `0x18000832c`
- `0x180009260`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008400`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008417`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000836b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000836b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000840b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008443`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000840b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008443`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008433`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008433`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008425`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008425`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083dd`

## string_xrefs

- `0x180008465`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000848c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800084a3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800084ba`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(__int64 *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  __int64 v4; // r8
  const char *v5; // r9
  int result; // eax
  void *v7; // rsi
  DWORD LastError; // ebp
  const char *v9; // r9
  void *v10; // rsi
  DWORD v11; // ebp
  const char *v12; // r9
  DWORD v13; // esi
  const char *v14; // r9
  HANDLE ProcessHeap; // rax
  const char *v16; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, 3585, v4, v5);
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
            v16);
      }
    }
    else
    {
      v7 = (void *)lpMem[2];
      if ( v7 )
      {
        LastError = GetLastError();
        if ( !CloseHandle(v7) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v9);
        SetLastError(LastError);
      }
      lpMem[2] = 0;
      v10 = (void *)lpMem[3];
      if ( v10 )
      {
        v11 = GetLastError();
        if ( !CloseHandle(v10) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v12);
        SetLastError(v11);
      }
      lpMem[3] = 0;
      if ( v2 )
      {
        v13 = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v14);
        SetLastError(v13);
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
0x18000832c  push    rbx
0x18000832e  push    rbp
0x18000832f  push    rsi
0x180008330  push    rdi
0x180008331  sub     rsp, 28h
0x180008335  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000833c  mov     rbx, rcx
0x18000833f  jnz     loc_18000844F
0x180008345  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000834c  test    rax, rax
0x18000834f  jz      short loc_18000835E
0x180008351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008356  test    al, al
0x180008358  jnz     loc_18000844F
0x18000835e  mov     rdi, [rbx+8]
0x180008362  xor     r8d, r8d; bAlertable
0x180008365  mov     rcx, rdi; hHandle
0x180008368  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000836b  call    cs:__imp_WaitForSingleObjectEx
0x180008371  cmp     eax, 102h
0x180008376  jz      short loc_180008385
0x180008378  test    eax, 0FFFFFF7Fh
0x18000837d  jnz     loc_180008477
0x180008383  jmp     short loc_180008387
0x180008385  xor     edi, edi
0x180008387  mov     eax, [rbx]
0x180008389  dec     eax
0x18000838b  mov     [rbx], eax
0x18000838d  mov     eax, [rbx]
0x18000838f  test    eax, eax
0x180008391  jnz     loc_18000843B
0x180008397  mov     rsi, [rbx+10h]
0x18000839b  test    rsi, rsi
0x18000839e  jz      short loc_1800083C1
0x1800083a0  call    cs:__imp_GetLastError
0x1800083a6  mov     rcx, rsi; hObject
0x1800083a9  mov     ebp, eax
0x1800083ab  call    cs:__imp_CloseHandle
0x1800083b1  test    eax, eax
0x1800083b3  jz      loc_18000849E
0x1800083b9  mov     ecx, ebp; dwErrCode
0x1800083bb  call    cs:__imp_SetLastError
0x1800083c1  mov     qword ptr [rbx+10h], 0
0x1800083c9  mov     rsi, [rbx+18h]
0x1800083cd  test    rsi, rsi
0x1800083d0  jz      short loc_1800083F3
0x1800083d2  call    cs:__imp_GetLastError
0x1800083d8  mov     rcx, rsi; hObject
0x1800083db  mov     ebp, eax
0x1800083dd  call    cs:__imp_CloseHandle
0x1800083e3  test    eax, eax
0x1800083e5  jz      loc_1800084B5
0x1800083eb  mov     ecx, ebp; dwErrCode
0x1800083ed  call    cs:__imp_SetLastError
0x1800083f3  mov     qword ptr [rbx+18h], 0
0x1800083fb  test    rdi, rdi
0x1800083fe  jz      short loc_18000841D
0x180008400  call    cs:__imp_GetLastError
0x180008406  mov     rcx, rdi; hMutex
0x180008409  mov     esi, eax
0x18000840b  call    cs:__imp_ReleaseMutex
0x180008411  test    eax, eax
0x180008413  jz      short loc_180008460
0x180008415  mov     ecx, esi; dwErrCode
0x180008417  call    cs:__imp_SetLastError
0x18000841d  mov     rcx, rbx
0x180008420  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x180008425  call    cs:__imp_GetProcessHeap
0x18000842b  mov     r8, rbx; lpMem
0x18000842e  xor     edx, edx; dwFlags
0x180008430  mov     rcx, rax; hHeap
0x180008433  call    cs:__imp_HeapFree
0x180008439  jmp     short loc_180008457
0x18000843b  test    rdi, rdi
0x18000843e  jz      short loc_180008457
0x180008440  mov     rcx, rdi; hMutex
0x180008443  call    cs:__imp_ReleaseMutex
0x180008449  test    eax, eax
0x18000844b  jz      short loc_180008487
0x18000844d  jmp     short loc_180008457
0x18000844f  mov     eax, [rbx]
0x180008451  dec     eax
0x180008453  mov     [rbx], eax
0x180008455  mov     eax, [rbx]
0x180008457  add     rsp, 28h
0x18000845b  pop     rdi
0x18000845c  pop     rsi
0x18000845d  pop     rbp
0x18000845e  pop     rbx
0x18000845f  retn
0x180008460  mov     rcx, [rsp+48h]; this
0x180008465  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000846c  mov     edx, 0A15h; void *
0x180008471  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008477  mov     rcx, [rsp+48h]; this
0x18000847c  mov     edx, 0E01h; void *
0x180008481  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008487  mov     rcx, [rsp+48h]; this
0x18000848c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008493  mov     edx, 0A15h; void *
0x180008498  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000849e  mov     rcx, [rsp+48h]; this
0x1800084a3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800084aa  mov     edx, 0A0Bh; void *
0x1800084af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800084b5  mov     rcx, [rsp+48h]; this
0x1800084ba  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800084c1  mov     edx, 0A0Bh; void *
0x1800084c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
