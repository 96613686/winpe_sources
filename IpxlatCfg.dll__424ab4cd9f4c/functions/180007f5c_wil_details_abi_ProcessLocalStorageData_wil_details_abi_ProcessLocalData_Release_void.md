# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180007f5c`
- end: `0x180008075`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `281`
- prototype: `int __fastcall(_QWORD *lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180018990`

## callees

- `0x180003fc4`
- `0x180005340`
- `0x180005638`
- `0x180007f5c`
- `0x180009bcc`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007fee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000800a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000800a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ffc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ffc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007fa1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007fa1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007fe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000801a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007fe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000801a`

## string_xrefs

- `0x180008053`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180007f5c  mov     [rsp+arg_0], rbx
0x180007f61  mov     [rsp+arg_8], rsi
0x180007f66  push    rdi
0x180007f67  sub     rsp, 20h
0x180007f6b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007f72  mov     rbx, rcx
0x180007f75  jnz     loc_180008026
0x180007f7b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007f82  test    rax, rax
0x180007f85  jz      short loc_180007F94
0x180007f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f8c  test    al, al
0x180007f8e  jnz     loc_180008026
0x180007f94  mov     rdi, [rbx+8]
0x180007f98  xor     r8d, r8d; bAlertable
0x180007f9b  mov     rcx, rdi; hHandle
0x180007f9e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007fa1  call    cs:__imp_WaitForSingleObjectEx
0x180007fa7  cmp     eax, 102h
0x180007fac  jz      short loc_180007FBB
0x180007fae  test    eax, 0FFFFFF7Fh
0x180007fb3  jnz     loc_18000804E
0x180007fb9  jmp     short loc_180007FBD
0x180007fbb  xor     edi, edi
0x180007fbd  mov     eax, [rbx]
0x180007fbf  dec     eax
0x180007fc1  mov     [rbx], eax
0x180007fc3  mov     eax, [rbx]
0x180007fc5  test    eax, eax
0x180007fc7  jnz     short loc_180008012
0x180007fc9  lea     rcx, [rbx+10h]; this
0x180007fcd  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180007fd2  test    rdi, rdi
0x180007fd5  jz      short loc_180007FF4
0x180007fd7  call    cs:__imp_GetLastError
0x180007fdd  mov     rcx, rdi; hMutex
0x180007fe0  mov     esi, eax
0x180007fe2  call    cs:__imp_ReleaseMutex
0x180007fe8  test    eax, eax
0x180007fea  jz      short loc_18000803E
0x180007fec  mov     ecx, esi; dwErrCode
0x180007fee  call    cs:__imp_SetLastError
0x180007ff4  mov     rcx, rbx
0x180007ff7  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x180007ffc  call    cs:__imp_GetProcessHeap
0x180008002  mov     r8, rbx; lpMem
0x180008005  xor     edx, edx; dwFlags
0x180008007  mov     rcx, rax; hHeap
0x18000800a  call    cs:__imp_HeapFree
0x180008010  jmp     short loc_18000802E
0x180008012  test    rdi, rdi
0x180008015  jz      short loc_18000802E
0x180008017  mov     rcx, rdi; hMutex
0x18000801a  call    cs:__imp_ReleaseMutex
0x180008020  test    eax, eax
0x180008022  jz      short loc_180008065
0x180008024  jmp     short loc_18000802E
0x180008026  mov     eax, [rbx]
0x180008028  dec     eax
0x18000802a  mov     [rbx], eax
0x18000802c  mov     eax, [rbx]
0x18000802e  mov     rbx, [rsp+28h+arg_0]
0x180008033  mov     rsi, [rsp+28h+arg_8]
0x180008038  add     rsp, 20h
0x18000803c  pop     rdi
0x18000803d  retn
0x18000803e  mov     rcx, [rsp+28h]; this
0x180008043  mov     edx, 0A15h; void *
0x180008048  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000804e  mov     rcx, [rsp+28h]; this
0x180008053  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000805a  mov     edx, 0E01h; void *
0x18000805f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008065  mov     rcx, [rsp+28h]; this
0x18000806a  mov     edx, 0A15h; void *
0x18000806f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
