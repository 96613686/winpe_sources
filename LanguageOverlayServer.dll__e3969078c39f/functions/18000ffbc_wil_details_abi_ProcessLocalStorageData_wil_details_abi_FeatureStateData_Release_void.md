# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000ffbc`
- end: `0x18001010f`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `339`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000c388`
- `0x180069810`

## callees

- `0x180006ec8`
- `0x180007790`
- `0x180007840`
- `0x18000a008`
- `0x18000c31c`
- `0x18000e804`
- `0x18000ffbc`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fffb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fffb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001003c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010095`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001003c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010095`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010085`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010077`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010031`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001004c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001004c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001006d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001006d`

## string_xrefs

- `0x1800100c4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800100e6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800100fd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(_QWORD *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
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
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v12);
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
      wil::details_abi::FeatureStateData::~FeatureStateData((struct _RTL_CRITICAL_SECTION *)(lpMem + 4));
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      v9 = (void *)lpMem[1];
      if ( v9 )
      {
        if ( !CloseHandle(v9) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v10);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x18000ffbc  push    rbx
0x18000ffbe  push    rbp
0x18000ffbf  push    rsi
0x18000ffc0  push    rdi
0x18000ffc1  sub     rsp, 28h
0x18000ffc5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ffcc  mov     rbx, rcx
0x18000ffcf  jnz     loc_1800100A1
0x18000ffd5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ffdc  test    rax, rax
0x18000ffdf  jz      short loc_18000FFEE
0x18000ffe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffe6  test    al, al
0x18000ffe8  jnz     loc_1800100A1
0x18000ffee  mov     rdi, [rbx+8]
0x18000fff2  xor     r8d, r8d; bAlertable
0x18000fff5  mov     rcx, rdi; hHandle
0x18000fff8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000fffb  call    cs:__imp_WaitForSingleObjectEx
0x180010001  cmp     eax, 102h
0x180010006  jz      short loc_180010015
0x180010008  test    eax, 0FFFFFF7Fh
0x18001000d  jnz     loc_1800100D6
0x180010013  jmp     short loc_180010017
0x180010015  xor     edi, edi
0x180010017  mov     eax, [rbx]
0x180010019  dec     eax
0x18001001b  mov     [rbx], eax
0x18001001d  mov     eax, [rbx]
0x18001001f  test    eax, eax
0x180010021  jnz     short loc_18001008D
0x180010023  lea     rcx, [rbx+10h]; this
0x180010027  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18001002c  test    rdi, rdi
0x18001002f  jz      short loc_180010052
0x180010031  call    cs:__imp_GetLastError
0x180010037  mov     rcx, rdi; hMutex
0x18001003a  mov     ebp, eax
0x18001003c  call    cs:__imp_ReleaseMutex
0x180010042  test    eax, eax
0x180010044  jz      loc_1800100F8
0x18001004a  mov     ecx, ebp; dwErrCode
0x18001004c  call    cs:__imp_SetLastError
0x180010052  lea     rcx, [rbx+20h]; this
0x180010056  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x18001005b  lea     rcx, [rbx+10h]; this
0x18001005f  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180010064  mov     rcx, [rbx+8]; hObject
0x180010068  test    rcx, rcx
0x18001006b  jz      short loc_180010077
0x18001006d  call    cs:__imp_CloseHandle
0x180010073  test    eax, eax
0x180010075  jz      short loc_1800100BF
0x180010077  call    cs:__imp_GetProcessHeap
0x18001007d  mov     r8, rbx; lpMem
0x180010080  xor     edx, edx; dwFlags
0x180010082  mov     rcx, rax; hHeap
0x180010085  call    cs:__imp_HeapFree
0x18001008b  jmp     short loc_1800100B6
0x18001008d  test    rdi, rdi
0x180010090  jz      short loc_1800100B6
0x180010092  mov     rcx, rdi; hMutex
0x180010095  call    cs:__imp_ReleaseMutex
0x18001009b  test    eax, eax
0x18001009d  jz      short loc_1800100E1
0x18001009f  jmp     short loc_1800100B6
0x1800100a1  mov     eax, [rbx]
0x1800100a3  dec     eax
0x1800100a5  mov     [rbx], eax
0x1800100a7  mov     eax, [rbx]
0x1800100a9  test    eax, eax
0x1800100ab  jnz     short loc_1800100B6
0x1800100ad  lea     rcx, [rbx+20h]; this
0x1800100b1  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x1800100b6  add     rsp, 28h
0x1800100ba  pop     rdi
0x1800100bb  pop     rsi
0x1800100bc  pop     rbp
0x1800100bd  pop     rbx
0x1800100be  retn
0x1800100bf  mov     rcx, [rsp+48h]; this
0x1800100c4  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800100cb  mov     edx, 0A0Bh; void *
0x1800100d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800100d6  mov     rcx, [rsp+48h]; this
0x1800100db  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800100e1  mov     rcx, [rsp+48h]; this
0x1800100e6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800100ed  mov     edx, 0A15h; void *
0x1800100f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800100f8  mov     rcx, [rsp+48h]; this
0x1800100fd  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010104  mov     edx, 0A15h; void *
0x180010109  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
