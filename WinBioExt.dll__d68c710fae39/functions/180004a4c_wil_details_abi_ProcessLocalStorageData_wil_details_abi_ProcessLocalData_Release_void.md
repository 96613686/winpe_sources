# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x180004a4c`
- end: `0x180004b65`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `281`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000a570`

## callees

- `0x180002e98`
- `0x180003740`
- `0x1800037e4`
- `0x180004a4c`
- `0x180005b5c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004ad2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004b0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004ad2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004b0a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004a91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004a91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004aec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004aec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004afa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004afa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ac7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ade`

## string_xrefs

- `0x180004b43`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180004a4c  mov     [rsp+arg_0], rbx
0x180004a51  mov     [rsp+arg_8], rsi
0x180004a56  push    rdi
0x180004a57  sub     rsp, 20h
0x180004a5b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180004a62  mov     rbx, rcx
0x180004a65  jnz     loc_180004B16
0x180004a6b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180004a72  test    rax, rax
0x180004a75  jz      short loc_180004A84
0x180004a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a7c  test    al, al
0x180004a7e  jnz     loc_180004B16
0x180004a84  mov     rdi, [rbx+8]
0x180004a88  xor     r8d, r8d; bAlertable
0x180004a8b  mov     rcx, rdi; hHandle
0x180004a8e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004a91  call    cs:__imp_WaitForSingleObjectEx
0x180004a97  cmp     eax, 102h
0x180004a9c  jz      short loc_180004AAB
0x180004a9e  test    eax, 0FFFFFF7Fh
0x180004aa3  jnz     loc_180004B3E
0x180004aa9  jmp     short loc_180004AAD
0x180004aab  xor     edi, edi
0x180004aad  mov     eax, [rbx]
0x180004aaf  dec     eax
0x180004ab1  mov     [rbx], eax
0x180004ab3  mov     eax, [rbx]
0x180004ab5  test    eax, eax
0x180004ab7  jnz     short loc_180004B02
0x180004ab9  lea     rcx, [rbx+10h]; this
0x180004abd  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180004ac2  test    rdi, rdi
0x180004ac5  jz      short loc_180004AE4
0x180004ac7  call    cs:__imp_GetLastError
0x180004acd  mov     rcx, rdi; hMutex
0x180004ad0  mov     esi, eax
0x180004ad2  call    cs:__imp_ReleaseMutex
0x180004ad8  test    eax, eax
0x180004ada  jz      short loc_180004B2E
0x180004adc  mov     ecx, esi; dwErrCode
0x180004ade  call    cs:__imp_SetLastError
0x180004ae4  mov     rcx, rbx
0x180004ae7  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x180004aec  call    cs:__imp_GetProcessHeap
0x180004af2  mov     r8, rbx; lpMem
0x180004af5  xor     edx, edx; dwFlags
0x180004af7  mov     rcx, rax; hHeap
0x180004afa  call    cs:__imp_HeapFree
0x180004b00  jmp     short loc_180004B1E
0x180004b02  test    rdi, rdi
0x180004b05  jz      short loc_180004B1E
0x180004b07  mov     rcx, rdi; hMutex
0x180004b0a  call    cs:__imp_ReleaseMutex
0x180004b10  test    eax, eax
0x180004b12  jz      short loc_180004B55
0x180004b14  jmp     short loc_180004B1E
0x180004b16  mov     eax, [rbx]
0x180004b18  dec     eax
0x180004b1a  mov     [rbx], eax
0x180004b1c  mov     eax, [rbx]
0x180004b1e  mov     rbx, [rsp+28h+arg_0]
0x180004b23  mov     rsi, [rsp+28h+arg_8]
0x180004b28  add     rsp, 20h
0x180004b2c  pop     rdi
0x180004b2d  retn
0x180004b2e  mov     rcx, [rsp+28h]; this
0x180004b33  mov     edx, 0A15h; void *
0x180004b38  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004b3e  mov     rcx, [rsp+28h]; this
0x180004b43  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004b4a  mov     edx, 0E01h; void *
0x180004b4f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180004b55  mov     rcx, [rsp+28h]; this
0x180004b5a  mov     edx, 0A15h; void *
0x180004b5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
