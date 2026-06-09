# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000844c`
- end: `0x180008566`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `282`
- prototype: `void __fastcall(_QWORD *lpMem)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180003394`
- `0x18000cca0`

## callees

- `0x180003048`
- `0x1800045b0`
- `0x180004c98`
- `0x18000713c`
- `0x18000844c`
- `0x18000ab1c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800084d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000850a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800084d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000850a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008491`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008491`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800084de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800084de`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  DWORD LastError; // esi
  __int64 v8; // r8
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  __int64 v11; // r8
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
      wil::details_abi::FeatureStateData::ProcessShutdown((wil::details_abi::FeatureStateData *)(lpMem + 4));
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
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v11, v12);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v8, v9);
        SetLastError(LastError);
      }
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(lpMem);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x18000844c  mov     [rsp+arg_0], rbx
0x180008451  mov     [rsp+arg_8], rsi
0x180008456  push    rdi
0x180008457  sub     rsp, 20h
0x18000845b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008462  mov     rbx, rcx
0x180008465  jnz     loc_180008516
0x18000846b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008472  test    rax, rax
0x180008475  jz      short loc_180008484
0x180008477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000847c  test    al, al
0x18000847e  jnz     loc_180008516
0x180008484  mov     rdi, [rbx+8]
0x180008488  xor     r8d, r8d; bAlertable
0x18000848b  mov     rcx, rdi; hHandle
0x18000848e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008491  call    cs:__imp_WaitForSingleObjectEx
0x180008497  cmp     eax, 102h
0x18000849c  jz      short loc_1800084AB
0x18000849e  test    eax, 0FFFFFF7Fh
0x1800084a3  jnz     loc_18000854B
0x1800084a9  jmp     short loc_1800084AD
0x1800084ab  xor     edi, edi
0x1800084ad  mov     eax, [rbx]
0x1800084af  dec     eax
0x1800084b1  mov     [rbx], eax
0x1800084b3  mov     eax, [rbx]
0x1800084b5  test    eax, eax
0x1800084b7  jnz     short loc_180008502
0x1800084b9  lea     rcx, [rbx+10h]; this
0x1800084bd  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x1800084c2  test    rdi, rdi
0x1800084c5  jz      short loc_1800084E4
0x1800084c7  call    cs:__imp_GetLastError
0x1800084cd  mov     rcx, rdi; hMutex
0x1800084d0  mov     esi, eax
0x1800084d2  call    cs:__imp_ReleaseMutex
0x1800084d8  test    eax, eax
0x1800084da  jz      short loc_18000853B
0x1800084dc  mov     ecx, esi; dwErrCode
0x1800084de  call    cs:__imp_SetLastError
0x1800084e4  mov     rcx, rbx
0x1800084e7  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x1800084ec  call    cs:__imp_GetProcessHeap
0x1800084f2  mov     r8, rbx; lpMem
0x1800084f5  xor     edx, edx; dwFlags
0x1800084f7  mov     rcx, rax; hHeap
0x1800084fa  call    cs:__imp_HeapFree
0x180008500  jmp     short loc_18000852B
0x180008502  test    rdi, rdi
0x180008505  jz      short loc_18000852B
0x180008507  mov     rcx, rdi; hMutex
0x18000850a  call    cs:__imp_ReleaseMutex
0x180008510  test    eax, eax
0x180008512  jz      short loc_180008556
0x180008514  jmp     short loc_18000852B
0x180008516  mov     eax, [rbx]
0x180008518  dec     eax
0x18000851a  mov     [rbx], eax
0x18000851c  mov     eax, [rbx]
0x18000851e  test    eax, eax
0x180008520  jnz     short loc_18000852B
0x180008522  lea     rcx, [rbx+20h]; this
0x180008526  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x18000852b  mov     rbx, [rsp+28h+arg_0]
0x180008530  mov     rsi, [rsp+28h+arg_8]
0x180008535  add     rsp, 20h
0x180008539  pop     rdi
0x18000853a  retn
0x18000853b  mov     rcx, [rsp+28h]; this
0x180008540  mov     edx, 0A15h; void *
0x180008545  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000854b  mov     rcx, [rsp+28h]; this
0x180008550  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008556  mov     rcx, [rsp+28h]; this
0x18000855b  mov     edx, 0A15h; void *
0x180008560  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
