# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x18000fe78`
- end: `0x18000fff8`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `384`
- prototype: `int __fastcall(_QWORD *lpMem)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002e1f0`

## callees

- `0x18000aca0`
- `0x18000b2f8`
- `0x18000c554`
- `0x18000cac8`
- `0x18000fe78`
- `0x180012220`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000feb7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000feb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ff08`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ff7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ff08`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ff7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ff69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ff69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fef7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ff45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ff45`

## string_xrefs

- `0x18000ffa8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000ffcf`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000ffe6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  __int64 v4; // r8
  const char *v5; // r9
  int result; // eax
  DWORD LastError; // ebp
  const char *v8; // r9
  void *v9; // rcx
  const char *v10; // r9
  HANDLE ProcessHeap; // rax
  const char *v12; // r9
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v4, v5);
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
            v12);
      }
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v8);
        SetLastError(LastError);
      }
      wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(lpMem + 5);
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      v9 = (void *)lpMem[1];
      if ( v9 )
      {
        if ( !CloseHandle(v9) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v10);
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
0x18000fe78  push    rbx
0x18000fe7a  push    rbp
0x18000fe7b  push    rsi
0x18000fe7c  push    rdi
0x18000fe7d  sub     rsp, 28h
0x18000fe81  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000fe88  mov     rbx, rcx
0x18000fe8b  jnz     loc_18000FF91
0x18000fe91  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fe98  test    rax, rax
0x18000fe9b  jz      short loc_18000FEAA
0x18000fe9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fea2  test    al, al
0x18000fea4  jnz     loc_18000FF91
0x18000feaa  mov     rdi, [rbx+8]
0x18000feae  xor     r8d, r8d; bAlertable
0x18000feb1  mov     rcx, rdi; hHandle
0x18000feb4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000feb7  call    cs:__imp_WaitForSingleObjectEx
0x18000febe  nop     dword ptr [rax+rax+00h]
0x18000fec3  cmp     eax, 102h
0x18000fec8  jz      short loc_18000FED7
0x18000feca  test    eax, 0FFFFFF7Fh
0x18000fecf  jnz     loc_18000FFBA
0x18000fed5  jmp     short loc_18000FED9
0x18000fed7  xor     edi, edi
0x18000fed9  mov     eax, [rbx]
0x18000fedb  dec     eax
0x18000fedd  mov     [rbx], eax
0x18000fedf  mov     eax, [rbx]
0x18000fee1  test    eax, eax
0x18000fee3  jnz     loc_18000FF77
0x18000fee9  lea     rcx, [rbx+10h]; this
0x18000feed  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000fef2  test    rdi, rdi
0x18000fef5  jz      short loc_18000FF2A
0x18000fef7  call    cs:__imp_GetLastError
0x18000fefe  nop     dword ptr [rax+rax+00h]
0x18000ff03  mov     rcx, rdi; hMutex
0x18000ff06  mov     ebp, eax
0x18000ff08  call    cs:__imp_ReleaseMutex
0x18000ff0f  nop     dword ptr [rax+rax+00h]
0x18000ff14  test    eax, eax
0x18000ff16  jz      loc_18000FFE1
0x18000ff1c  mov     ecx, ebp; dwErrCode
0x18000ff1e  call    cs:__imp_SetLastError
0x18000ff25  nop     dword ptr [rax+rax+00h]
0x18000ff2a  lea     rcx, [rbx+28h]
0x18000ff2e  call    ??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)
0x18000ff33  lea     rcx, [rbx+10h]; this
0x18000ff37  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ff3c  mov     rcx, [rbx+8]; hObject
0x18000ff40  test    rcx, rcx
0x18000ff43  jz      short loc_18000FF55
0x18000ff45  call    cs:__imp_CloseHandle
0x18000ff4c  nop     dword ptr [rax+rax+00h]
0x18000ff51  test    eax, eax
0x18000ff53  jz      short loc_18000FFA3
0x18000ff55  call    cs:__imp_GetProcessHeap
0x18000ff5c  nop     dword ptr [rax+rax+00h]
0x18000ff61  mov     r8, rbx; lpMem
0x18000ff64  xor     edx, edx; dwFlags
0x18000ff66  mov     rcx, rax; hHeap
0x18000ff69  call    cs:__imp_HeapFree
0x18000ff70  nop     dword ptr [rax+rax+00h]
0x18000ff75  jmp     short loc_18000FF99
0x18000ff77  test    rdi, rdi
0x18000ff7a  jz      short loc_18000FF99
0x18000ff7c  mov     rcx, rdi; hMutex
0x18000ff7f  call    cs:__imp_ReleaseMutex
0x18000ff86  nop     dword ptr [rax+rax+00h]
0x18000ff8b  test    eax, eax
0x18000ff8d  jz      short loc_18000FFCA
0x18000ff8f  jmp     short loc_18000FF99
0x18000ff91  mov     eax, [rbx]
0x18000ff93  dec     eax
0x18000ff95  mov     [rbx], eax
0x18000ff97  mov     eax, [rbx]
0x18000ff99  add     rsp, 28h
0x18000ff9d  pop     rdi
0x18000ff9e  pop     rsi
0x18000ff9f  pop     rbp
0x18000ffa0  pop     rbx
0x18000ffa1  retn
0x18000ffa3  mov     rcx, [rsp+48h]; this
0x18000ffa8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ffaf  mov     edx, 0A0Bh; void *
0x18000ffb4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ffba  mov     rcx, [rsp+48h]; this
0x18000ffbf  mov     edx, 0E01h; void *
0x18000ffc4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000ffca  mov     rcx, [rsp+48h]; this
0x18000ffcf  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ffd6  mov     edx, 0A15h; void *
0x18000ffdb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ffe1  mov     rcx, [rsp+48h]; this
0x18000ffe6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ffed  mov     edx, 0A15h; void *
0x18000fff2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
