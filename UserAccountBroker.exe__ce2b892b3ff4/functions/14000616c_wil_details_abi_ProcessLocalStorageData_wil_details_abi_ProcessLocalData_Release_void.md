# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x14000616c`
- end: `0x1400062eb`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `383`
- prototype: `int __fastcall(_QWORD *lpMem)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140006e00`

## callees

- `0x140004880`
- `0x140004fe0`
- `0x14000616c`
- `0x140006acc`
- `0x140007010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400061e0`
- `KERNEL32!GetLastError` at `0x140006212`
- `KERNEL32!GetLastError` at `0x140006240`
- `KERNEL32!GetLastError` at `0x1400061e0`
- `KERNEL32!GetLastError` at `0x140006212`
- `KERNEL32!GetLastError` at `0x140006240`
- `KERNEL32!CloseHandle` at `0x1400061eb`
- `KERNEL32!CloseHandle` at `0x14000621d`
- `KERNEL32!CloseHandle` at `0x1400061eb`
- `KERNEL32!CloseHandle` at `0x14000621d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400061fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000622d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006257`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400061fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000622d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006257`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400061ab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400061ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000624b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006283`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000624b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006283`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006273`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006273`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006265`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006265`

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
0x14000616c  push    rbx
0x14000616e  push    rbp
0x14000616f  push    rsi
0x140006170  push    rdi
0x140006171  sub     rsp, 28h
0x140006175  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000617c  mov     rbx, rcx
0x14000617f  jnz     loc_14000628F
0x140006185  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000618c  test    rax, rax
0x14000618f  jz      short loc_14000619E
0x140006191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006196  test    al, al
0x140006198  jnz     loc_14000628F
0x14000619e  mov     rdi, [rbx+8]
0x1400061a2  xor     r8d, r8d; bAlertable
0x1400061a5  mov     rcx, rdi; hHandle
0x1400061a8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400061ab  call    cs:__imp_WaitForSingleObjectEx
0x1400061b1  cmp     eax, 102h
0x1400061b6  jz      short loc_1400061C5
0x1400061b8  test    eax, 0FFFFFF7Fh
0x1400061bd  jnz     loc_1400062B0
0x1400061c3  jmp     short loc_1400061C7
0x1400061c5  xor     edi, edi
0x1400061c7  mov     eax, [rbx]
0x1400061c9  dec     eax
0x1400061cb  mov     [rbx], eax
0x1400061cd  mov     eax, [rbx]
0x1400061cf  test    eax, eax
0x1400061d1  jnz     loc_14000627B
0x1400061d7  mov     rsi, [rbx+10h]
0x1400061db  test    rsi, rsi
0x1400061de  jz      short loc_140006201
0x1400061e0  call    cs:__imp_GetLastError
0x1400061e6  mov     rcx, rsi; hObject
0x1400061e9  mov     ebp, eax
0x1400061eb  call    cs:__imp_CloseHandle
0x1400061f1  test    eax, eax
0x1400061f3  jz      loc_1400062CB
0x1400061f9  mov     ecx, ebp; dwErrCode
0x1400061fb  call    cs:__imp_SetLastError
0x140006201  mov     qword ptr [rbx+10h], 0
0x140006209  mov     rsi, [rbx+18h]
0x14000620d  test    rsi, rsi
0x140006210  jz      short loc_140006233
0x140006212  call    cs:__imp_GetLastError
0x140006218  mov     rcx, rsi; hObject
0x14000621b  mov     ebp, eax
0x14000621d  call    cs:__imp_CloseHandle
0x140006223  test    eax, eax
0x140006225  jz      loc_1400062DB
0x14000622b  mov     ecx, ebp; dwErrCode
0x14000622d  call    cs:__imp_SetLastError
0x140006233  mov     qword ptr [rbx+18h], 0
0x14000623b  test    rdi, rdi
0x14000623e  jz      short loc_14000625D
0x140006240  call    cs:__imp_GetLastError
0x140006246  mov     rcx, rdi; hMutex
0x140006249  mov     esi, eax
0x14000624b  call    cs:__imp_ReleaseMutex
0x140006251  test    eax, eax
0x140006253  jz      short loc_1400062A0
0x140006255  mov     ecx, esi; dwErrCode
0x140006257  call    cs:__imp_SetLastError
0x14000625d  mov     rcx, rbx
0x140006260  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x140006265  call    cs:__imp_GetProcessHeap
0x14000626b  mov     r8, rbx; lpMem
0x14000626e  xor     edx, edx; dwFlags
0x140006270  mov     rcx, rax; hHeap
0x140006273  call    cs:__imp_HeapFree
0x140006279  jmp     short loc_140006297
0x14000627b  test    rdi, rdi
0x14000627e  jz      short loc_140006297
0x140006280  mov     rcx, rdi; hMutex
0x140006283  call    cs:__imp_ReleaseMutex
0x140006289  test    eax, eax
0x14000628b  jz      short loc_1400062BB
0x14000628d  jmp     short loc_140006297
0x14000628f  mov     eax, [rbx]
0x140006291  dec     eax
0x140006293  mov     [rbx], eax
0x140006295  mov     eax, [rbx]
0x140006297  add     rsp, 28h
0x14000629b  pop     rdi
0x14000629c  pop     rsi
0x14000629d  pop     rbp
0x14000629e  pop     rbx
0x14000629f  retn
0x1400062a0  mov     rcx, [rsp+48h]; this
0x1400062a5  mov     edx, 0A15h; void *
0x1400062aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400062b0  mov     rcx, [rsp+48h]; this
0x1400062b5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400062bb  mov     rcx, [rsp+48h]; this
0x1400062c0  mov     edx, 0A15h; void *
0x1400062c5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400062cb  mov     rcx, [rsp+48h]; this
0x1400062d0  mov     edx, 0A0Bh; void *
0x1400062d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400062db  mov     rcx, [rsp+48h]; this
0x1400062e0  mov     edx, 0A0Bh; void *
0x1400062e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
