# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x140009f38`
- end: `0x14000a0c3`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `395`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400592c0`

## callees

- `0x140007b54`
- `0x140008b34`
- `0x140009f38`
- `0x14000c55c`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009f77`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009f77`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000a017`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000a04f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000a017`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000a04f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a03f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a03f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a031`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a031`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009fc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009ff9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a023`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009fc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009ff9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009fde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a00c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009fde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a00c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009fb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009fe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009fb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009fe9`

## string_xrefs

- `0x14000a081`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140009f38  push    rbx
0x140009f3a  push    rbp
0x140009f3b  push    rsi
0x140009f3c  push    rdi
0x140009f3d  sub     rsp, 28h
0x140009f41  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140009f48  mov     rbx, rcx
0x140009f4b  jnz     loc_14000A05B
0x140009f51  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140009f58  test    rax, rax
0x140009f5b  jz      short loc_140009F6A
0x140009f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f62  test    al, al
0x140009f64  jnz     loc_14000A05B
0x140009f6a  mov     rdi, [rbx+8]
0x140009f6e  xor     r8d, r8d; bAlertable
0x140009f71  mov     rcx, rdi; hHandle
0x140009f74  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140009f77  call    cs:__imp_WaitForSingleObjectEx
0x140009f7d  cmp     eax, 102h
0x140009f82  jz      short loc_140009F91
0x140009f84  test    eax, 0FFFFFF7Fh
0x140009f89  jnz     loc_14000A07C
0x140009f8f  jmp     short loc_140009F93
0x140009f91  xor     edi, edi
0x140009f93  mov     eax, [rbx]
0x140009f95  dec     eax
0x140009f97  mov     [rbx], eax
0x140009f99  mov     eax, [rbx]
0x140009f9b  test    eax, eax
0x140009f9d  jnz     loc_14000A047
0x140009fa3  mov     rsi, [rbx+10h]
0x140009fa7  test    rsi, rsi
0x140009faa  jz      short loc_140009FCD
0x140009fac  call    cs:__imp_GetLastError
0x140009fb2  mov     rcx, rsi; hObject
0x140009fb5  mov     ebp, eax
0x140009fb7  call    cs:__imp_CloseHandle
0x140009fbd  test    eax, eax
0x140009fbf  jz      loc_14000A0A3
0x140009fc5  mov     ecx, ebp; dwErrCode
0x140009fc7  call    cs:__imp_SetLastError
0x140009fcd  mov     qword ptr [rbx+10h], 0
0x140009fd5  mov     rsi, [rbx+18h]
0x140009fd9  test    rsi, rsi
0x140009fdc  jz      short loc_140009FFF
0x140009fde  call    cs:__imp_GetLastError
0x140009fe4  mov     rcx, rsi; hObject
0x140009fe7  mov     ebp, eax
0x140009fe9  call    cs:__imp_CloseHandle
0x140009fef  test    eax, eax
0x140009ff1  jz      loc_14000A0B3
0x140009ff7  mov     ecx, ebp; dwErrCode
0x140009ff9  call    cs:__imp_SetLastError
0x140009fff  mov     qword ptr [rbx+18h], 0
0x14000a007  test    rdi, rdi
0x14000a00a  jz      short loc_14000A029
0x14000a00c  call    cs:__imp_GetLastError
0x14000a012  mov     rcx, rdi; hMutex
0x14000a015  mov     esi, eax
0x14000a017  call    cs:__imp_ReleaseMutex
0x14000a01d  test    eax, eax
0x14000a01f  jz      short loc_14000A06C
0x14000a021  mov     ecx, esi; dwErrCode
0x14000a023  call    cs:__imp_SetLastError
0x14000a029  mov     rcx, rbx
0x14000a02c  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x14000a031  call    cs:__imp_GetProcessHeap
0x14000a037  mov     r8, rbx; lpMem
0x14000a03a  xor     edx, edx; dwFlags
0x14000a03c  mov     rcx, rax; hHeap
0x14000a03f  call    cs:__imp_HeapFree
0x14000a045  jmp     short loc_14000A063
0x14000a047  test    rdi, rdi
0x14000a04a  jz      short loc_14000A063
0x14000a04c  mov     rcx, rdi; hMutex
0x14000a04f  call    cs:__imp_ReleaseMutex
0x14000a055  test    eax, eax
0x14000a057  jz      short loc_14000A093
0x14000a059  jmp     short loc_14000A063
0x14000a05b  mov     eax, [rbx]
0x14000a05d  dec     eax
0x14000a05f  mov     [rbx], eax
0x14000a061  mov     eax, [rbx]
0x14000a063  add     rsp, 28h
0x14000a067  pop     rdi
0x14000a068  pop     rsi
0x14000a069  pop     rbp
0x14000a06a  pop     rbx
0x14000a06b  retn
0x14000a06c  mov     rcx, [rsp+48h]; this
0x14000a071  mov     edx, 0A15h; void *
0x14000a076  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a07c  mov     rcx, [rsp+48h]; this
0x14000a081  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000a088  mov     edx, 0E01h; void *
0x14000a08d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000a093  mov     rcx, [rsp+48h]; this
0x14000a098  mov     edx, 0A15h; void *
0x14000a09d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a0a3  mov     rcx, [rsp+48h]; this
0x14000a0a8  mov     edx, 0A0Bh; void *
0x14000a0ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a0b3  mov     rcx, [rsp+48h]; this
0x14000a0b8  mov     edx, 0A0Bh; void *
0x14000a0bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
