# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x140011f4c`
- end: `0x140012072`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `294`
- prototype: `void __fastcall(_QWORD *lpMem)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000fa20`
- `0x1400233f0`

## callees

- `0x140009330`
- `0x140009490`
- `0x14000e3a4`
- `0x14000f7a4`
- `0x140010f7c`
- `0x140011f4c`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140011fd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14001200a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140011fd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14001200a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140011f91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140011f91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011ffa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011ffa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011fec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011fc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011fc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011fde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011fde`

## string_xrefs

- `0x140012050`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // esi
  __int64 v6; // r8
  const char *v7; // r9
  HANDLE ProcessHeap; // rax
  __int64 v9; // r8
  const char *v10; // r9
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
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v9, v10);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v6, v7);
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
0x140011f4c  mov     [rsp+arg_8], rbx
0x140011f51  mov     [rsp+arg_10], rsi
0x140011f56  push    rdi
0x140011f57  sub     rsp, 20h
0x140011f5b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140011f62  mov     rbx, rcx
0x140011f65  jnz     loc_140012016
0x140011f6b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140011f72  test    rax, rax
0x140011f75  jz      short loc_140011F84
0x140011f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011f7c  test    al, al
0x140011f7e  jnz     loc_140012016
0x140011f84  mov     rdi, [rbx+8]
0x140011f88  xor     r8d, r8d; bAlertable
0x140011f8b  mov     rcx, rdi; hHandle
0x140011f8e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140011f91  call    cs:__imp_WaitForSingleObjectEx
0x140011f97  cmp     eax, 102h
0x140011f9c  jz      short loc_140011FAB
0x140011f9e  test    eax, 0FFFFFF7Fh
0x140011fa3  jnz     loc_14001204B
0x140011fa9  jmp     short loc_140011FAD
0x140011fab  xor     edi, edi
0x140011fad  mov     eax, [rbx]
0x140011faf  dec     eax
0x140011fb1  mov     [rbx], eax
0x140011fb3  mov     eax, [rbx]
0x140011fb5  test    eax, eax
0x140011fb7  jnz     short loc_140012002
0x140011fb9  lea     rcx, [rbx+10h]; this
0x140011fbd  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x140011fc2  test    rdi, rdi
0x140011fc5  jz      short loc_140011FE4
0x140011fc7  call    cs:__imp_GetLastError
0x140011fcd  mov     rcx, rdi; hMutex
0x140011fd0  mov     esi, eax
0x140011fd2  call    cs:__imp_ReleaseMutex
0x140011fd8  test    eax, eax
0x140011fda  jz      short loc_14001203B
0x140011fdc  mov     ecx, esi; dwErrCode
0x140011fde  call    cs:__imp_SetLastError
0x140011fe4  mov     rcx, rbx
0x140011fe7  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x140011fec  call    cs:__imp_GetProcessHeap
0x140011ff2  mov     r8, rbx; lpMem
0x140011ff5  xor     edx, edx; dwFlags
0x140011ff7  mov     rcx, rax; hHeap
0x140011ffa  call    cs:__imp_HeapFree
0x140012000  jmp     short loc_14001202B
0x140012002  test    rdi, rdi
0x140012005  jz      short loc_14001202B
0x140012007  mov     rcx, rdi; hMutex
0x14001200a  call    cs:__imp_ReleaseMutex
0x140012010  test    eax, eax
0x140012012  jz      short loc_140012062
0x140012014  jmp     short loc_14001202B
0x140012016  mov     eax, [rbx]
0x140012018  dec     eax
0x14001201a  mov     [rbx], eax
0x14001201c  mov     eax, [rbx]
0x14001201e  test    eax, eax
0x140012020  jnz     short loc_14001202B
0x140012022  lea     rcx, [rbx+20h]; this
0x140012026  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x14001202b  mov     rbx, [rsp+28h+arg_8]
0x140012030  mov     rsi, [rsp+28h+arg_10]
0x140012035  add     rsp, 20h
0x140012039  pop     rdi
0x14001203a  retn
0x14001203b  mov     rcx, [rsp+28h]; this
0x140012040  mov     edx, 0A15h; void *
0x140012045  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001204b  mov     rcx, [rsp+28h]; this
0x140012050  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140012057  mov     edx, 0E01h; void *
0x14001205c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140012062  mov     rcx, [rsp+28h]; this
0x140012067  mov     edx, 0A15h; void *
0x14001206c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
