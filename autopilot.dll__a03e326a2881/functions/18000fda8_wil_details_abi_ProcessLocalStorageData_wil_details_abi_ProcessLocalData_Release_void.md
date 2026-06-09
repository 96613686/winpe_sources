# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(void)

- ea: `0x18000fda8`
- end: `0x18000fec8`
- name: `?Release@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `288`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002d330`

## callees

- `0x18000ac1c`
- `0x18000c520`
- `0x18000ca34`
- `0x18000fda8`
- `0x180012114`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fded`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fded`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fe2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fe66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fe2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fe66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe3a`

## string_xrefs

- `0x18000fe8f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000feb6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  unsigned int v4; // r8d
  const char *v5; // r9
  int result; // eax
  DWORD LastError; // esi
  const char *v8; // r9
  HANDLE ProcessHeap; // rax
  const char *v10; // r9
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
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v10);
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
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v8);
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
0x18000fda8  mov     [rsp+arg_0], rbx
0x18000fdad  mov     [rsp+arg_8], rsi
0x18000fdb2  push    rdi
0x18000fdb3  sub     rsp, 20h
0x18000fdb7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000fdbe  mov     rbx, rcx
0x18000fdc1  jnz     loc_18000FE72
0x18000fdc7  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fdce  test    rax, rax
0x18000fdd1  jz      short loc_18000FDE0
0x18000fdd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd8  test    al, al
0x18000fdda  jnz     loc_18000FE72
0x18000fde0  mov     rdi, [rbx+8]
0x18000fde4  xor     r8d, r8d; bAlertable
0x18000fde7  mov     rcx, rdi; hHandle
0x18000fdea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000fded  call    cs:__imp_WaitForSingleObjectEx
0x18000fdf3  cmp     eax, 102h
0x18000fdf8  jz      short loc_18000FE07
0x18000fdfa  test    eax, 0FFFFFF7Fh
0x18000fdff  jnz     loc_18000FEA1
0x18000fe05  jmp     short loc_18000FE09
0x18000fe07  xor     edi, edi
0x18000fe09  mov     eax, [rbx]
0x18000fe0b  dec     eax
0x18000fe0d  mov     [rbx], eax
0x18000fe0f  mov     eax, [rbx]
0x18000fe11  test    eax, eax
0x18000fe13  jnz     short loc_18000FE5E
0x18000fe15  lea     rcx, [rbx+10h]; this
0x18000fe19  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000fe1e  test    rdi, rdi
0x18000fe21  jz      short loc_18000FE40
0x18000fe23  call    cs:__imp_GetLastError
0x18000fe29  mov     rcx, rdi; hMutex
0x18000fe2c  mov     esi, eax
0x18000fe2e  call    cs:__imp_ReleaseMutex
0x18000fe34  test    eax, eax
0x18000fe36  jz      short loc_18000FE8A
0x18000fe38  mov     ecx, esi; dwErrCode
0x18000fe3a  call    cs:__imp_SetLastError
0x18000fe40  mov     rcx, rbx
0x18000fe43  call    ??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)
0x18000fe48  call    cs:__imp_GetProcessHeap
0x18000fe4e  mov     r8, rbx; lpMem
0x18000fe51  xor     edx, edx; dwFlags
0x18000fe53  mov     rcx, rax; hHeap
0x18000fe56  call    cs:__imp_HeapFree
0x18000fe5c  jmp     short loc_18000FE7A
0x18000fe5e  test    rdi, rdi
0x18000fe61  jz      short loc_18000FE7A
0x18000fe63  mov     rcx, rdi; hMutex
0x18000fe66  call    cs:__imp_ReleaseMutex
0x18000fe6c  test    eax, eax
0x18000fe6e  jz      short loc_18000FEB1
0x18000fe70  jmp     short loc_18000FE7A
0x18000fe72  mov     eax, [rbx]
0x18000fe74  dec     eax
0x18000fe76  mov     [rbx], eax
0x18000fe78  mov     eax, [rbx]
0x18000fe7a  mov     rbx, [rsp+28h+arg_0]
0x18000fe7f  mov     rsi, [rsp+28h+arg_8]
0x18000fe84  add     rsp, 20h
0x18000fe88  pop     rdi
0x18000fe89  retn
0x18000fe8a  mov     rcx, [rsp+28h]; this
0x18000fe8f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000fe96  mov     edx, 0A15h; void *
0x18000fe9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fea1  mov     rcx, [rsp+28h]; this
0x18000fea6  mov     edx, 0E01h; void *
0x18000feab  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000feb1  mov     rcx, [rsp+28h]; this
0x18000feb6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000febd  mov     edx, 0A15h; void *
0x18000fec2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
