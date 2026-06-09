# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x1800059b8`
- end: `0x180005b37`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `383`
- prototype: `int __fastcall(_QWORD *lpMem)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008080`

## callees

- `0x1800030c8`
- `0x1800040cc`
- `0x1800059b8`
- `0x1800078f4`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005aa3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005a97`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005acf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005a97`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005acf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800059f7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800059f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ab1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ab1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005abf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005abf`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  int v5; // r8d
  const char *v6; // r9
  int result; // eax
  void *v8; // rsi
  DWORD LastError; // ebp
  __int64 v10; // r8
  const char *v11; // r9
  void *v12; // rsi
  DWORD v13; // ebp
  __int64 v14; // r8
  const char *v15; // r9
  DWORD v16; // esi
  __int64 v17; // r8
  const char *v18; // r9
  HANDLE ProcessHeap; // rax
  __int64 v20; // r8
  const char *v21; // r9
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v4, v5, v6);
    }
    result = --*(_DWORD *)lpMem;
    if ( *(_DWORD *)lpMem )
    {
      if ( v2 )
      {
        result = ReleaseMutex(v2);
        if ( !result )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v20, v21);
      }
    }
    else
    {
      v8 = (void *)lpMem[2];
      if ( v8 )
      {
        LastError = GetLastError();
        if ( !CloseHandle(v8) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
        SetLastError(LastError);
      }
      lpMem[2] = 0;
      v12 = (void *)lpMem[3];
      if ( v12 )
      {
        v13 = GetLastError();
        if ( !CloseHandle(v12) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
        SetLastError(v13);
      }
      lpMem[3] = 0;
      if ( v2 )
      {
        v16 = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
        SetLastError(v16);
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
0x1800059b8  push    rbx
0x1800059ba  push    rbp
0x1800059bb  push    rsi
0x1800059bc  push    rdi
0x1800059bd  sub     rsp, 28h
0x1800059c1  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800059c8  mov     rbx, rcx
0x1800059cb  jnz     loc_180005ADB
0x1800059d1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800059d8  test    rax, rax
0x1800059db  jz      short loc_1800059EA
0x1800059dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e2  test    al, al
0x1800059e4  jnz     loc_180005ADB
0x1800059ea  mov     rdi, [rbx+8]
0x1800059ee  xor     r8d, r8d; bAlertable
0x1800059f1  mov     rcx, rdi; hHandle
0x1800059f4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800059f7  call    cs:__imp_WaitForSingleObjectEx
0x1800059fd  cmp     eax, 102h
0x180005a02  jz      short loc_180005A11
0x180005a04  test    eax, 0FFFFFF7Fh
0x180005a09  jnz     loc_180005AFC
0x180005a0f  jmp     short loc_180005A13
0x180005a11  xor     edi, edi
0x180005a13  mov     eax, [rbx]
0x180005a15  dec     eax
0x180005a17  mov     [rbx], eax
0x180005a19  mov     eax, [rbx]
0x180005a1b  test    eax, eax
0x180005a1d  jnz     loc_180005AC7
0x180005a23  mov     rsi, [rbx+10h]
0x180005a27  test    rsi, rsi
0x180005a2a  jz      short loc_180005A4D
0x180005a2c  call    cs:__imp_GetLastError
0x180005a32  mov     rcx, rsi; hObject
0x180005a35  mov     ebp, eax
0x180005a37  call    cs:__imp_CloseHandle
0x180005a3d  test    eax, eax
0x180005a3f  jz      loc_180005B17
0x180005a45  mov     ecx, ebp; dwErrCode
0x180005a47  call    cs:__imp_SetLastError
0x180005a4d  mov     qword ptr [rbx+10h], 0
0x180005a55  mov     rsi, [rbx+18h]
0x180005a59  test    rsi, rsi
0x180005a5c  jz      short loc_180005A7F
0x180005a5e  call    cs:__imp_GetLastError
0x180005a64  mov     rcx, rsi; hObject
0x180005a67  mov     ebp, eax
0x180005a69  call    cs:__imp_CloseHandle
0x180005a6f  test    eax, eax
0x180005a71  jz      loc_180005B27
0x180005a77  mov     ecx, ebp; dwErrCode
0x180005a79  call    cs:__imp_SetLastError
0x180005a7f  mov     qword ptr [rbx+18h], 0
0x180005a87  test    rdi, rdi
0x180005a8a  jz      short loc_180005AA9
0x180005a8c  call    cs:__imp_GetLastError
0x180005a92  mov     rcx, rdi; hMutex
0x180005a95  mov     esi, eax
0x180005a97  call    cs:__imp_ReleaseMutex
0x180005a9d  test    eax, eax
0x180005a9f  jz      short loc_180005AEC
0x180005aa1  mov     ecx, esi; dwErrCode
0x180005aa3  call    cs:__imp_SetLastError
0x180005aa9  mov     rcx, rbx
0x180005aac  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x180005ab1  call    cs:__imp_GetProcessHeap
0x180005ab7  mov     r8, rbx; lpMem
0x180005aba  xor     edx, edx; dwFlags
0x180005abc  mov     rcx, rax; hHeap
0x180005abf  call    cs:__imp_HeapFree
0x180005ac5  jmp     short loc_180005AE3
0x180005ac7  test    rdi, rdi
0x180005aca  jz      short loc_180005AE3
0x180005acc  mov     rcx, rdi; hMutex
0x180005acf  call    cs:__imp_ReleaseMutex
0x180005ad5  test    eax, eax
0x180005ad7  jz      short loc_180005B07
0x180005ad9  jmp     short loc_180005AE3
0x180005adb  mov     eax, [rbx]
0x180005add  dec     eax
0x180005adf  mov     [rbx], eax
0x180005ae1  mov     eax, [rbx]
0x180005ae3  add     rsp, 28h
0x180005ae7  pop     rdi
0x180005ae8  pop     rsi
0x180005ae9  pop     rbp
0x180005aea  pop     rbx
0x180005aeb  retn
0x180005aec  mov     rcx, [rsp+48h]; this
0x180005af1  mov     edx, 0A15h; void *
0x180005af6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005afc  mov     rcx, [rsp+48h]; this
0x180005b01  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005b07  mov     rcx, [rsp+48h]; this
0x180005b0c  mov     edx, 0A15h; void *
0x180005b11  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005b17  mov     rcx, [rsp+48h]; this
0x180005b1c  mov     edx, 0A0Bh; void *
0x180005b21  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005b27  mov     rcx, [rsp+48h]; this
0x180005b2c  mov     edx, 0A0Bh; void *
0x180005b31  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
