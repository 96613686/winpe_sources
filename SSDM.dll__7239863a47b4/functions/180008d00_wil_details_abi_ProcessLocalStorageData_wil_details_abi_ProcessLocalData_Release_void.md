# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180008d00`
- end: `0x180008e8b`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `395`
- prototype: `int __fastcall(_QWORD *lpMem)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000fe00`

## callees

- `0x1800056e4`
- `0x1800071e4`
- `0x180007dd8`
- `0x180008d00`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008dd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008dc1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008deb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008dc1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008deb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008ddf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008e17`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008ddf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008e17`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008d3f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008d3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008db1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008db1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008df9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008df9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008e07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008e07`

## string_xrefs

- `0x180008e49`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v8; // r8
  const char *v9; // r9
  void *v10; // rsi
  DWORD v11; // ebp
  __int64 v12; // r8
  const char *v13; // r9
  DWORD v14; // esi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE ProcessHeap; // rax
  __int64 v18; // r8
  const char *v19; // r9
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
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
      }
    }
    else
    {
      v6 = (void *)lpMem[2];
      if ( v6 )
      {
        LastError = GetLastError();
        if ( !CloseHandle(v6) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
        SetLastError(LastError);
      }
      lpMem[2] = 0;
      v10 = (void *)lpMem[3];
      if ( v10 )
      {
        v11 = GetLastError();
        if ( !CloseHandle(v10) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
        SetLastError(v11);
      }
      lpMem[3] = 0;
      if ( v2 )
      {
        v14 = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
        SetLastError(v14);
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
0x180008d00  push    rbx
0x180008d02  push    rbp
0x180008d03  push    rsi
0x180008d04  push    rdi
0x180008d05  sub     rsp, 28h
0x180008d09  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008d10  mov     rbx, rcx
0x180008d13  jnz     loc_180008E23
0x180008d19  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008d20  test    rax, rax
0x180008d23  jz      short loc_180008D32
0x180008d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d2a  test    al, al
0x180008d2c  jnz     loc_180008E23
0x180008d32  mov     rdi, [rbx+8]
0x180008d36  xor     r8d, r8d; bAlertable
0x180008d39  mov     rcx, rdi; hHandle
0x180008d3c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008d3f  call    cs:__imp_WaitForSingleObjectEx
0x180008d45  cmp     eax, 102h
0x180008d4a  jz      short loc_180008D59
0x180008d4c  test    eax, 0FFFFFF7Fh
0x180008d51  jnz     loc_180008E44
0x180008d57  jmp     short loc_180008D5B
0x180008d59  xor     edi, edi
0x180008d5b  mov     eax, [rbx]
0x180008d5d  dec     eax
0x180008d5f  mov     [rbx], eax
0x180008d61  mov     eax, [rbx]
0x180008d63  test    eax, eax
0x180008d65  jnz     loc_180008E0F
0x180008d6b  mov     rsi, [rbx+10h]
0x180008d6f  test    rsi, rsi
0x180008d72  jz      short loc_180008D95
0x180008d74  call    cs:__imp_GetLastError
0x180008d7a  mov     rcx, rsi; hObject
0x180008d7d  mov     ebp, eax
0x180008d7f  call    cs:__imp_CloseHandle
0x180008d85  test    eax, eax
0x180008d87  jz      loc_180008E6B
0x180008d8d  mov     ecx, ebp; dwErrCode
0x180008d8f  call    cs:__imp_SetLastError
0x180008d95  mov     qword ptr [rbx+10h], 0
0x180008d9d  mov     rsi, [rbx+18h]
0x180008da1  test    rsi, rsi
0x180008da4  jz      short loc_180008DC7
0x180008da6  call    cs:__imp_GetLastError
0x180008dac  mov     rcx, rsi; hObject
0x180008daf  mov     ebp, eax
0x180008db1  call    cs:__imp_CloseHandle
0x180008db7  test    eax, eax
0x180008db9  jz      loc_180008E7B
0x180008dbf  mov     ecx, ebp; dwErrCode
0x180008dc1  call    cs:__imp_SetLastError
0x180008dc7  mov     qword ptr [rbx+18h], 0
0x180008dcf  test    rdi, rdi
0x180008dd2  jz      short loc_180008DF1
0x180008dd4  call    cs:__imp_GetLastError
0x180008dda  mov     rcx, rdi; hMutex
0x180008ddd  mov     esi, eax
0x180008ddf  call    cs:__imp_ReleaseMutex
0x180008de5  test    eax, eax
0x180008de7  jz      short loc_180008E34
0x180008de9  mov     ecx, esi; dwErrCode
0x180008deb  call    cs:__imp_SetLastError
0x180008df1  mov     rcx, rbx
0x180008df4  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x180008df9  call    cs:__imp_GetProcessHeap
0x180008dff  mov     r8, rbx; lpMem
0x180008e02  xor     edx, edx; dwFlags
0x180008e04  mov     rcx, rax; hHeap
0x180008e07  call    cs:__imp_HeapFree
0x180008e0d  jmp     short loc_180008E2B
0x180008e0f  test    rdi, rdi
0x180008e12  jz      short loc_180008E2B
0x180008e14  mov     rcx, rdi; hMutex
0x180008e17  call    cs:__imp_ReleaseMutex
0x180008e1d  test    eax, eax
0x180008e1f  jz      short loc_180008E5B
0x180008e21  jmp     short loc_180008E2B
0x180008e23  mov     eax, [rbx]
0x180008e25  dec     eax
0x180008e27  mov     [rbx], eax
0x180008e29  mov     eax, [rbx]
0x180008e2b  add     rsp, 28h
0x180008e2f  pop     rdi
0x180008e30  pop     rsi
0x180008e31  pop     rbp
0x180008e32  pop     rbx
0x180008e33  retn
0x180008e34  mov     rcx, [rsp+48h]; this
0x180008e39  mov     edx, 0A15h; void *
0x180008e3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008e44  mov     rcx, [rsp+48h]; this
0x180008e49  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008e50  mov     edx, 0E01h; void *
0x180008e55  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180008e5b  mov     rcx, [rsp+48h]; this
0x180008e60  mov     edx, 0A15h; void *
0x180008e65  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008e6b  mov     rcx, [rsp+48h]; this
0x180008e70  mov     edx, 0A0Bh; void *
0x180008e75  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008e7b  mov     rcx, [rsp+48h]; this
0x180008e80  mov     edx, 0A0Bh; void *
0x180008e85  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
