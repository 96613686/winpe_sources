# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x1800075fc`
- end: `0x18000776e`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `370`
- prototype: `int __fastcall(_QWORD *lpMem)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180036ef0`

## callees

- `0x180003ce4`
- `0x180005b04`
- `0x180005c5c`
- `0x180006504`
- `0x1800075fc`
- `0x180009518`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000768c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007703`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000768c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007703`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000763b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000763b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000767b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000767b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076c9`

## string_xrefs

- `0x18000773c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // ebp
  __int64 v7; // r8
  const char *v8; // r9
  void *v9; // rcx
  __int64 v10; // r8
  const char *v11; // r9
  HANDLE ProcessHeap; // rax
  __int64 v13; // r8
  const char *v14; // r9
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
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v13, v14);
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
      wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(lpMem + 5);
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      v9 = (void *)lpMem[1];
      if ( v9 )
      {
        if ( !CloseHandle(v9) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
      }
      ProcessHeap = GetProcessHeap();
      return HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800075fc  push    rbx
0x1800075fe  push    rbp
0x1800075ff  push    rsi
0x180007600  push    rdi
0x180007601  sub     rsp, 28h
0x180007605  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000760c  mov     rbx, rcx
0x18000760f  jnz     loc_180007715
0x180007615  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000761c  test    rax, rax
0x18000761f  jz      short loc_18000762E
0x180007621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007626  test    al, al
0x180007628  jnz     loc_180007715
0x18000762e  mov     rdi, [rbx+8]
0x180007632  xor     r8d, r8d; bAlertable
0x180007635  mov     rcx, rdi; hHandle
0x180007638  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000763b  call    cs:__imp_WaitForSingleObjectEx
0x180007642  nop     dword ptr [rax+rax+00h]
0x180007647  cmp     eax, 102h
0x18000764c  jz      short loc_18000765B
0x18000764e  test    eax, 0FFFFFF7Fh
0x180007653  jnz     loc_180007737
0x180007659  jmp     short loc_18000765D
0x18000765b  xor     edi, edi
0x18000765d  mov     eax, [rbx]
0x18000765f  dec     eax
0x180007661  mov     [rbx], eax
0x180007663  mov     eax, [rbx]
0x180007665  test    eax, eax
0x180007667  jnz     loc_1800076FB
0x18000766d  lea     rcx, [rbx+10h]; this
0x180007671  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180007676  test    rdi, rdi
0x180007679  jz      short loc_1800076AE
0x18000767b  call    cs:__imp_GetLastError
0x180007682  nop     dword ptr [rax+rax+00h]
0x180007687  mov     rcx, rdi; hMutex
0x18000768a  mov     ebp, eax
0x18000768c  call    cs:__imp_ReleaseMutex
0x180007693  nop     dword ptr [rax+rax+00h]
0x180007698  test    eax, eax
0x18000769a  jz      loc_18000775E
0x1800076a0  mov     ecx, ebp; dwErrCode
0x1800076a2  call    cs:__imp_SetLastError
0x1800076a9  nop     dword ptr [rax+rax+00h]
0x1800076ae  lea     rcx, [rbx+28h]
0x1800076b2  call    ??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)
0x1800076b7  lea     rcx, [rbx+10h]; this
0x1800076bb  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800076c0  mov     rcx, [rbx+8]; hObject
0x1800076c4  test    rcx, rcx
0x1800076c7  jz      short loc_1800076D9
0x1800076c9  call    cs:__imp_CloseHandle
0x1800076d0  nop     dword ptr [rax+rax+00h]
0x1800076d5  test    eax, eax
0x1800076d7  jz      short loc_180007727
0x1800076d9  call    cs:__imp_GetProcessHeap
0x1800076e0  nop     dword ptr [rax+rax+00h]
0x1800076e5  mov     r8, rbx; lpMem
0x1800076e8  xor     edx, edx; dwFlags
0x1800076ea  mov     rcx, rax; hHeap
0x1800076ed  call    cs:__imp_HeapFree
0x1800076f4  nop     dword ptr [rax+rax+00h]
0x1800076f9  jmp     short loc_18000771D
0x1800076fb  test    rdi, rdi
0x1800076fe  jz      short loc_18000771D
0x180007700  mov     rcx, rdi; hMutex
0x180007703  call    cs:__imp_ReleaseMutex
0x18000770a  nop     dword ptr [rax+rax+00h]
0x18000770f  test    eax, eax
0x180007711  jz      short loc_18000774E
0x180007713  jmp     short loc_18000771D
0x180007715  mov     eax, [rbx]
0x180007717  dec     eax
0x180007719  mov     [rbx], eax
0x18000771b  mov     eax, [rbx]
0x18000771d  add     rsp, 28h
0x180007721  pop     rdi
0x180007722  pop     rsi
0x180007723  pop     rbp
0x180007724  pop     rbx
0x180007725  retn
0x180007727  mov     rcx, [rsp+48h]; this
0x18000772c  mov     edx, 0A0Bh; void *
0x180007731  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007737  mov     rcx, [rsp+48h]; this
0x18000773c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007743  mov     edx, 0E01h; void *
0x180007748  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000774e  mov     rcx, [rsp+48h]; this
0x180007753  mov     edx, 0A15h; void *
0x180007758  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000775e  mov     rcx, [rsp+48h]; this
0x180007763  mov     edx, 0A15h; void *
0x180007768  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
