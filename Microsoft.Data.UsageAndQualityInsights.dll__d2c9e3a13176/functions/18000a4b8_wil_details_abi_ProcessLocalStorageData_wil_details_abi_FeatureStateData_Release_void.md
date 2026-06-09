# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000a4b8`
- end: `0x18000a697`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `479`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1800065c8`
- `0x180107720`

## callees

- `0x180005ffc`
- `0x1800064f0`
- `0x180006878`
- `0x1800069cc`
- `0x1800076a0`
- `0x1800079a4`
- `0x180009484`
- `0x18000a4b8`
- `0x18000b700`
- `0x18000c268`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a4fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a4fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a53b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a59f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a53b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a59f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a588`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a588`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a57a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a57a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a530`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a54b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a54b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a56c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a56c`

## string_xrefs

- `0x18000a637`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a651`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a66b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a685`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // ebp
  const char *v6; // r9
  void *v7; // rcx
  const char *v8; // r9
  HANDLE ProcessHeap; // rax
  const char *v10; // r9
  _BYTE v11[64]; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v12[64]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v13[104]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v11);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v11,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v12,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v13,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v11);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v11);
    }
  }
  else
  {
    v2 = (void *)*((_QWORD *)lpMem + 1);
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
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v10);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA15,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v6);
        SetLastError(LastError);
      }
      wil::details_abi::FeatureStateData::~FeatureStateData((wil::details_abi::FeatureStateData *)(lpMem + 32));
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      v7 = (void *)*((_QWORD *)lpMem + 1);
      if ( v7 )
      {
        if ( !CloseHandle(v7) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v8);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x18000a4b8  push    rbx
0x18000a4ba  push    rbp
0x18000a4bb  push    rsi
0x18000a4bc  push    rdi
0x18000a4bd  sub     rsp, 0E8h
0x18000a4c4  mov     rbx, rcx
0x18000a4c7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a4ce  jnz     loc_18000A5AF
0x18000a4d4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a4db  test    rax, rax
0x18000a4de  jz      short loc_18000A4ED
0x18000a4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e5  test    al, al
0x18000a4e7  jnz     loc_18000A5AF
0x18000a4ed  mov     rdi, [rbx+8]
0x18000a4f1  xor     r8d, r8d; bAlertable
0x18000a4f4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a4f7  mov     rcx, rdi; hHandle
0x18000a4fa  call    cs:__imp_WaitForSingleObjectEx
0x18000a500  cmp     eax, 102h
0x18000a505  jz      short loc_18000A514
0x18000a507  test    eax, 0FFFFFF7Fh
0x18000a50c  jnz     loc_18000A649
0x18000a512  jmp     short loc_18000A516
0x18000a514  xor     edi, edi
0x18000a516  mov     eax, [rbx]
0x18000a518  dec     eax
0x18000a51a  mov     [rbx], eax
0x18000a51c  mov     eax, [rbx]
0x18000a51e  test    eax, eax
0x18000a520  jnz     short loc_18000A593
0x18000a522  lea     rcx, [rbx+10h]; this
0x18000a526  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000a52b  test    rdi, rdi
0x18000a52e  jz      short loc_18000A551
0x18000a530  call    cs:__imp_GetLastError
0x18000a536  mov     ebp, eax
0x18000a538  mov     rcx, rdi; hMutex
0x18000a53b  call    cs:__imp_ReleaseMutex
0x18000a541  test    eax, eax
0x18000a543  jz      loc_18000A67D
0x18000a549  mov     ecx, ebp; dwErrCode
0x18000a54b  call    cs:__imp_SetLastError
0x18000a551  lea     rcx, [rbx+20h]; this
0x18000a555  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x18000a55a  lea     rcx, [rbx+10h]; this
0x18000a55e  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a563  mov     rcx, [rbx+8]; hObject
0x18000a567  test    rcx, rcx
0x18000a56a  jz      short loc_18000A57A
0x18000a56c  call    cs:__imp_CloseHandle
0x18000a572  test    eax, eax
0x18000a574  jz      loc_18000A62F
0x18000a57a  call    cs:__imp_GetProcessHeap
0x18000a580  mov     rcx, rax; hHeap
0x18000a583  mov     r8, rbx; lpMem
0x18000a586  xor     edx, edx; dwFlags
0x18000a588  call    cs:__imp_HeapFree
0x18000a58e  jmp     loc_18000A623
0x18000a593  test    rdi, rdi
0x18000a596  jz      loc_18000A623
0x18000a59c  mov     rcx, rdi; hMutex
0x18000a59f  call    cs:__imp_ReleaseMutex
0x18000a5a5  test    eax, eax
0x18000a5a7  jz      loc_18000A663
0x18000a5ad  jmp     short loc_18000A623
0x18000a5af  mov     eax, [rbx]
0x18000a5b1  dec     eax
0x18000a5b3  mov     [rbx], eax
0x18000a5b5  mov     eax, [rbx]
0x18000a5b7  test    eax, eax
0x18000a5b9  jnz     short loc_18000A623
0x18000a5bb  lea     rcx, [rsp+108h+var_E8]; this
0x18000a5c0  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a5c5  nop
0x18000a5c6  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000a5ca  cmp     byte ptr [rdx+38h], 0
0x18000a5ce  jz      short loc_18000A5DA
0x18000a5d0  lea     rcx, [rsp+108h+var_E8]; this
0x18000a5d5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a5da  cmp     byte ptr [rbx+0A0h], 0
0x18000a5e1  jz      short loc_18000A5F1
0x18000a5e3  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000a5e7  lea     rcx, [rsp+108h+var_A8]; this
0x18000a5ec  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a5f1  cmp     byte ptr [rbx+0E0h], 0
0x18000a5f8  jz      short loc_18000A60E
0x18000a5fa  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000a601  lea     rcx, [rsp+108h+var_68]; this
0x18000a609  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a60e  lea     rcx, [rsp+108h+var_E8]; this
0x18000a613  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000a618  nop
0x18000a619  lea     rcx, [rsp+108h+var_E8]; this
0x18000a61e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000a623  add     rsp, 0E8h
0x18000a62a  pop     rdi
0x18000a62b  pop     rsi
0x18000a62c  pop     rbp
0x18000a62d  pop     rbx
0x18000a62e  retn
0x18000a62f  mov     rcx, [rsp+108h]; this
0x18000a637  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a63e  mov     edx, 0A0Bh; void *
0x18000a643  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a649  mov     rcx, [rsp+108h]; this
0x18000a651  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a658  mov     edx, 0E01h; void *
0x18000a65d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a663  mov     rcx, [rsp+108h]; this
0x18000a66b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a672  mov     edx, 0A15h; void *
0x18000a677  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a67d  mov     rcx, [rsp+108h]; this
0x18000a685  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a68c  mov     edx, 0A15h; void *
0x18000a691  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
