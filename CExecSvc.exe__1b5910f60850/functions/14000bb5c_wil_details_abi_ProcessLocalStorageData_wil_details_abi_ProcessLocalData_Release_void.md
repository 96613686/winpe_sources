# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x14000bb5c`
- end: `0x14000bc75`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `281`
- prototype: `int __fastcall(_QWORD *lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140023300`

## callees

- `0x140007ed4`
- `0x140009330`
- `0x140009490`
- `0x14000bb5c`
- `0x14000e3a4`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000bbe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000bc1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000bbe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000bc1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000bba1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000bba1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bc0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bc0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bbfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bbfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bbd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bbd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bbee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bbee`

## string_xrefs

- `0x14000bc53`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // esi
  __int64 v7; // r8
  const char *v8; // r9
  HANDLE ProcessHeap; // rax
  __int64 v10; // r8
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

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
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v10, v11);
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
0x14000bb5c  mov     [rsp+arg_8], rbx
0x14000bb61  mov     [rsp+arg_10], rsi
0x14000bb66  push    rdi
0x14000bb67  sub     rsp, 20h
0x14000bb6b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000bb72  mov     rbx, rcx
0x14000bb75  jnz     loc_14000BC26
0x14000bb7b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000bb82  test    rax, rax
0x14000bb85  jz      short loc_14000BB94
0x14000bb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb8c  test    al, al
0x14000bb8e  jnz     loc_14000BC26
0x14000bb94  mov     rdi, [rbx+8]
0x14000bb98  xor     r8d, r8d; bAlertable
0x14000bb9b  mov     rcx, rdi; hHandle
0x14000bb9e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000bba1  call    cs:__imp_WaitForSingleObjectEx
0x14000bba7  cmp     eax, 102h
0x14000bbac  jz      short loc_14000BBBB
0x14000bbae  test    eax, 0FFFFFF7Fh
0x14000bbb3  jnz     loc_14000BC4E
0x14000bbb9  jmp     short loc_14000BBBD
0x14000bbbb  xor     edi, edi
0x14000bbbd  mov     eax, [rbx]
0x14000bbbf  dec     eax
0x14000bbc1  mov     [rbx], eax
0x14000bbc3  mov     eax, [rbx]
0x14000bbc5  test    eax, eax
0x14000bbc7  jnz     short loc_14000BC12
0x14000bbc9  lea     rcx, [rbx+10h]; this
0x14000bbcd  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x14000bbd2  test    rdi, rdi
0x14000bbd5  jz      short loc_14000BBF4
0x14000bbd7  call    cs:__imp_GetLastError
0x14000bbdd  mov     rcx, rdi; hMutex
0x14000bbe0  mov     esi, eax
0x14000bbe2  call    cs:__imp_ReleaseMutex
0x14000bbe8  test    eax, eax
0x14000bbea  jz      short loc_14000BC3E
0x14000bbec  mov     ecx, esi; dwErrCode
0x14000bbee  call    cs:__imp_SetLastError
0x14000bbf4  mov     rcx, rbx
0x14000bbf7  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x14000bbfc  call    cs:__imp_GetProcessHeap
0x14000bc02  mov     r8, rbx; lpMem
0x14000bc05  xor     edx, edx; dwFlags
0x14000bc07  mov     rcx, rax; hHeap
0x14000bc0a  call    cs:__imp_HeapFree
0x14000bc10  jmp     short loc_14000BC2E
0x14000bc12  test    rdi, rdi
0x14000bc15  jz      short loc_14000BC2E
0x14000bc17  mov     rcx, rdi; hMutex
0x14000bc1a  call    cs:__imp_ReleaseMutex
0x14000bc20  test    eax, eax
0x14000bc22  jz      short loc_14000BC65
0x14000bc24  jmp     short loc_14000BC2E
0x14000bc26  mov     eax, [rbx]
0x14000bc28  dec     eax
0x14000bc2a  mov     [rbx], eax
0x14000bc2c  mov     eax, [rbx]
0x14000bc2e  mov     rbx, [rsp+28h+arg_8]
0x14000bc33  mov     rsi, [rsp+28h+arg_10]
0x14000bc38  add     rsp, 20h
0x14000bc3c  pop     rdi
0x14000bc3d  retn
0x14000bc3e  mov     rcx, [rsp+28h]; this
0x14000bc43  mov     edx, 0A15h; void *
0x14000bc48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bc4e  mov     rcx, [rsp+28h]; this
0x14000bc53  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000bc5a  mov     edx, 0E01h; void *
0x14000bc5f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000bc65  mov     rcx, [rsp+28h]; this
0x14000bc6a  mov     edx, 0A15h; void *
0x14000bc6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
