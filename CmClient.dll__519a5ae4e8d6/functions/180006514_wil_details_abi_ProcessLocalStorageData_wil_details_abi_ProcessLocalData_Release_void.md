# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180006514`
- end: `0x1800066bb`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `423`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000f020`

## callees

- `0x180003d24`
- `0x1800048a0`
- `0x180006514`
- `0x18000700c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006553`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006553`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800065f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000662b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800065f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000662b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000660d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000660d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000661b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000661b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065c5`

## string_xrefs

- `0x18000664d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006664`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000667b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006692`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800066a9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  void *v6; // rsi
  DWORD LastError; // ebp
  const char *v8; // r9
  void *v9; // rsi
  DWORD v10; // ebp
  const char *v11; // r9
  DWORD v12; // esi
  const char *v13; // r9
  HANDLE ProcessHeap; // rax
  const char *v15; // r9
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
            v15);
      }
    }
    else
    {
      v6 = (void *)lpMem[2];
      if ( v6 )
      {
        LastError = GetLastError();
        if ( !CloseHandle(v6) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v8);
        SetLastError(LastError);
      }
      lpMem[2] = 0;
      v9 = (void *)lpMem[3];
      if ( v9 )
      {
        v10 = GetLastError();
        if ( !CloseHandle(v9) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v11);
        SetLastError(v10);
      }
      lpMem[3] = 0;
      if ( v2 )
      {
        v12 = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v13);
        SetLastError(v12);
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
0x180006514  push    rbx
0x180006516  push    rbp
0x180006517  push    rsi
0x180006518  push    rdi
0x180006519  sub     rsp, 28h
0x18000651d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006524  mov     rbx, rcx
0x180006527  jnz     loc_180006637
0x18000652d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006534  test    rax, rax
0x180006537  jz      short loc_180006546
0x180006539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000653e  test    al, al
0x180006540  jnz     loc_180006637
0x180006546  mov     rdi, [rbx+8]
0x18000654a  xor     r8d, r8d; bAlertable
0x18000654d  mov     rcx, rdi; hHandle
0x180006550  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006553  call    cs:__imp_WaitForSingleObjectEx
0x180006559  cmp     eax, 102h
0x18000655e  jz      short loc_18000656D
0x180006560  test    eax, 0FFFFFF7Fh
0x180006565  jnz     loc_18000665F
0x18000656b  jmp     short loc_18000656F
0x18000656d  xor     edi, edi
0x18000656f  mov     eax, [rbx]
0x180006571  dec     eax
0x180006573  mov     [rbx], eax
0x180006575  mov     eax, [rbx]
0x180006577  test    eax, eax
0x180006579  jnz     loc_180006623
0x18000657f  mov     rsi, [rbx+10h]
0x180006583  test    rsi, rsi
0x180006586  jz      short loc_1800065A9
0x180006588  call    cs:__imp_GetLastError
0x18000658e  mov     rcx, rsi; hObject
0x180006591  mov     ebp, eax
0x180006593  call    cs:__imp_CloseHandle
0x180006599  test    eax, eax
0x18000659b  jz      loc_18000668D
0x1800065a1  mov     ecx, ebp; dwErrCode
0x1800065a3  call    cs:__imp_SetLastError
0x1800065a9  mov     qword ptr [rbx+10h], 0
0x1800065b1  mov     rsi, [rbx+18h]
0x1800065b5  test    rsi, rsi
0x1800065b8  jz      short loc_1800065DB
0x1800065ba  call    cs:__imp_GetLastError
0x1800065c0  mov     rcx, rsi; hObject
0x1800065c3  mov     ebp, eax
0x1800065c5  call    cs:__imp_CloseHandle
0x1800065cb  test    eax, eax
0x1800065cd  jz      loc_1800066A4
0x1800065d3  mov     ecx, ebp; dwErrCode
0x1800065d5  call    cs:__imp_SetLastError
0x1800065db  mov     qword ptr [rbx+18h], 0
0x1800065e3  test    rdi, rdi
0x1800065e6  jz      short loc_180006605
0x1800065e8  call    cs:__imp_GetLastError
0x1800065ee  mov     rcx, rdi; hMutex
0x1800065f1  mov     esi, eax
0x1800065f3  call    cs:__imp_ReleaseMutex
0x1800065f9  test    eax, eax
0x1800065fb  jz      short loc_180006648
0x1800065fd  mov     ecx, esi; dwErrCode
0x1800065ff  call    cs:__imp_SetLastError
0x180006605  mov     rcx, rbx
0x180006608  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x18000660d  call    cs:__imp_GetProcessHeap
0x180006613  mov     r8, rbx; lpMem
0x180006616  xor     edx, edx; dwFlags
0x180006618  mov     rcx, rax; hHeap
0x18000661b  call    cs:__imp_HeapFree
0x180006621  jmp     short loc_18000663F
0x180006623  test    rdi, rdi
0x180006626  jz      short loc_18000663F
0x180006628  mov     rcx, rdi; hMutex
0x18000662b  call    cs:__imp_ReleaseMutex
0x180006631  test    eax, eax
0x180006633  jz      short loc_180006676
0x180006635  jmp     short loc_18000663F
0x180006637  mov     eax, [rbx]
0x180006639  dec     eax
0x18000663b  mov     [rbx], eax
0x18000663d  mov     eax, [rbx]
0x18000663f  add     rsp, 28h
0x180006643  pop     rdi
0x180006644  pop     rsi
0x180006645  pop     rbp
0x180006646  pop     rbx
0x180006647  retn
0x180006648  mov     rcx, [rsp+48h]; this
0x18000664d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006654  mov     edx, 0A15h; void *
0x180006659  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000665f  mov     rcx, [rsp+48h]; this
0x180006664  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000666b  mov     edx, 0E01h; void *
0x180006670  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006676  mov     rcx, [rsp+48h]; this
0x18000667b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006682  mov     edx, 0A15h; void *
0x180006687  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000668d  mov     rcx, [rsp+48h]; this
0x180006692  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006699  mov     edx, 0A0Bh; void *
0x18000669e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800066a4  mov     rcx, [rsp+48h]; this
0x1800066a9  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800066b0  mov     edx, 0A0Bh; void *
0x1800066b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
