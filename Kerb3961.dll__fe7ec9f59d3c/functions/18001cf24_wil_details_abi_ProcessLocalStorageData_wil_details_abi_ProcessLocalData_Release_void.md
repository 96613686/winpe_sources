# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x18001cf24`
- end: `0x18001d03d`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `281`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001d6b0`

## callees

- `0x180007930`
- `0x180012f3c`
- `0x180017f00`
- `0x18001c664`
- `0x18001cf24`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cfc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cfc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cfd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cfd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cfaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cfe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cfaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001cfe2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001cf69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001cf69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cfb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cfb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf9f`

## string_xrefs

- `0x18001d01b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18001cf24  mov     [rsp+arg_0], rbx
0x18001cf29  mov     [rsp+arg_8], rsi
0x18001cf2e  push    rdi
0x18001cf2f  sub     rsp, 20h
0x18001cf33  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001cf3a  mov     rbx, rcx
0x18001cf3d  jnz     loc_18001CFEE
0x18001cf43  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001cf4a  test    rax, rax
0x18001cf4d  jz      short loc_18001CF5C
0x18001cf4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf54  test    al, al
0x18001cf56  jnz     loc_18001CFEE
0x18001cf5c  mov     rdi, [rbx+8]
0x18001cf60  xor     r8d, r8d; bAlertable
0x18001cf63  mov     rcx, rdi; hHandle
0x18001cf66  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001cf69  call    cs:__imp_WaitForSingleObjectEx
0x18001cf6f  cmp     eax, 102h
0x18001cf74  jz      short loc_18001CF83
0x18001cf76  test    eax, 0FFFFFF7Fh
0x18001cf7b  jnz     loc_18001D016
0x18001cf81  jmp     short loc_18001CF85
0x18001cf83  xor     edi, edi
0x18001cf85  mov     eax, [rbx]
0x18001cf87  dec     eax
0x18001cf89  mov     [rbx], eax
0x18001cf8b  mov     eax, [rbx]
0x18001cf8d  test    eax, eax
0x18001cf8f  jnz     short loc_18001CFDA
0x18001cf91  lea     rcx, [rbx+10h]; this
0x18001cf95  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18001cf9a  test    rdi, rdi
0x18001cf9d  jz      short loc_18001CFBC
0x18001cf9f  call    cs:__imp_GetLastError
0x18001cfa5  mov     rcx, rdi; hMutex
0x18001cfa8  mov     esi, eax
0x18001cfaa  call    cs:__imp_ReleaseMutex
0x18001cfb0  test    eax, eax
0x18001cfb2  jz      short loc_18001D006
0x18001cfb4  mov     ecx, esi; dwErrCode
0x18001cfb6  call    cs:__imp_SetLastError
0x18001cfbc  mov     rcx, rbx
0x18001cfbf  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x18001cfc4  call    cs:__imp_GetProcessHeap
0x18001cfca  mov     r8, rbx; lpMem
0x18001cfcd  xor     edx, edx; dwFlags
0x18001cfcf  mov     rcx, rax; hHeap
0x18001cfd2  call    cs:__imp_HeapFree
0x18001cfd8  jmp     short loc_18001CFF6
0x18001cfda  test    rdi, rdi
0x18001cfdd  jz      short loc_18001CFF6
0x18001cfdf  mov     rcx, rdi; hMutex
0x18001cfe2  call    cs:__imp_ReleaseMutex
0x18001cfe8  test    eax, eax
0x18001cfea  jz      short loc_18001D02D
0x18001cfec  jmp     short loc_18001CFF6
0x18001cfee  mov     eax, [rbx]
0x18001cff0  dec     eax
0x18001cff2  mov     [rbx], eax
0x18001cff4  mov     eax, [rbx]
0x18001cff6  mov     rbx, [rsp+28h+arg_0]
0x18001cffb  mov     rsi, [rsp+28h+arg_8]
0x18001d000  add     rsp, 20h
0x18001d004  pop     rdi
0x18001d005  retn
0x18001d006  mov     rcx, [rsp+28h]; this
0x18001d00b  mov     edx, 0A15h; void *
0x18001d010  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001d016  mov     rcx, [rsp+28h]; this
0x18001d01b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d022  mov     edx, 0E01h; void *
0x18001d027  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001d02d  mov     rcx, [rsp+28h]; this
0x18001d032  mov     edx, 0A15h; void *
0x18001d037  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
