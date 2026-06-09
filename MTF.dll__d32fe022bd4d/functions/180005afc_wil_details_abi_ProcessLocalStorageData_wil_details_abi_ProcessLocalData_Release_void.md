# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180005afc`
- end: `0x180005c15`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `281`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002df90`

## callees

- `0x180003c28`
- `0x180004630`
- `0x1800046d4`
- `0x180005afc`
- `0x180006f10`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005b41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005b41`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005b82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005bba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005b82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005bba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005baa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005baa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b8e`

## string_xrefs

- `0x180005bf3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  int result; // eax
  DWORD LastError; // esi
  unsigned int v7; // r8d
  const char *v8; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v10; // r8d
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
0x180005afc  mov     [rsp+arg_0], rbx
0x180005b01  mov     [rsp+arg_8], rsi
0x180005b06  push    rdi
0x180005b07  sub     rsp, 20h
0x180005b0b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005b12  mov     rbx, rcx
0x180005b15  jnz     loc_180005BC6
0x180005b1b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005b22  test    rax, rax
0x180005b25  jz      short loc_180005B34
0x180005b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b2c  test    al, al
0x180005b2e  jnz     loc_180005BC6
0x180005b34  mov     rdi, [rbx+8]
0x180005b38  xor     r8d, r8d; bAlertable
0x180005b3b  mov     rcx, rdi; hHandle
0x180005b3e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005b41  call    cs:__imp_WaitForSingleObjectEx
0x180005b47  cmp     eax, 102h
0x180005b4c  jz      short loc_180005B5B
0x180005b4e  test    eax, 0FFFFFF7Fh
0x180005b53  jnz     loc_180005BEE
0x180005b59  jmp     short loc_180005B5D
0x180005b5b  xor     edi, edi
0x180005b5d  mov     eax, [rbx]
0x180005b5f  dec     eax
0x180005b61  mov     [rbx], eax
0x180005b63  mov     eax, [rbx]
0x180005b65  test    eax, eax
0x180005b67  jnz     short loc_180005BB2
0x180005b69  lea     rcx, [rbx+10h]; this
0x180005b6d  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180005b72  test    rdi, rdi
0x180005b75  jz      short loc_180005B94
0x180005b77  call    cs:__imp_GetLastError
0x180005b7d  mov     rcx, rdi; hMutex
0x180005b80  mov     esi, eax
0x180005b82  call    cs:__imp_ReleaseMutex
0x180005b88  test    eax, eax
0x180005b8a  jz      short loc_180005BDE
0x180005b8c  mov     ecx, esi; dwErrCode
0x180005b8e  call    cs:__imp_SetLastError
0x180005b94  mov     rcx, rbx
0x180005b97  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x180005b9c  call    cs:__imp_GetProcessHeap
0x180005ba2  mov     r8, rbx; lpMem
0x180005ba5  xor     edx, edx; dwFlags
0x180005ba7  mov     rcx, rax; hHeap
0x180005baa  call    cs:__imp_HeapFree
0x180005bb0  jmp     short loc_180005BCE
0x180005bb2  test    rdi, rdi
0x180005bb5  jz      short loc_180005BCE
0x180005bb7  mov     rcx, rdi; hMutex
0x180005bba  call    cs:__imp_ReleaseMutex
0x180005bc0  test    eax, eax
0x180005bc2  jz      short loc_180005C05
0x180005bc4  jmp     short loc_180005BCE
0x180005bc6  mov     eax, [rbx]
0x180005bc8  dec     eax
0x180005bca  mov     [rbx], eax
0x180005bcc  mov     eax, [rbx]
0x180005bce  mov     rbx, [rsp+28h+arg_0]
0x180005bd3  mov     rsi, [rsp+28h+arg_8]
0x180005bd8  add     rsp, 20h
0x180005bdc  pop     rdi
0x180005bdd  retn
0x180005bde  mov     rcx, [rsp+28h]; this
0x180005be3  mov     edx, 0A15h; void *
0x180005be8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005bee  mov     rcx, [rsp+28h]; this
0x180005bf3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005bfa  mov     edx, 0E01h; void *
0x180005bff  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005c05  mov     rcx, [rsp+28h]; this
0x180005c0a  mov     edx, 0A15h; void *
0x180005c0f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
