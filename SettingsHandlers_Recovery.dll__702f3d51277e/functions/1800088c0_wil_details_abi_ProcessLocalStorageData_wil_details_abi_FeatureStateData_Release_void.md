# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x1800088c0`
- end: `0x180008a93`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `467`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180004808`
- `0x18002ab10`

## callees

- `0x180004318`
- `0x180004730`
- `0x180004ab8`
- `0x180004c0c`
- `0x1800059e0`
- `0x180005cf0`
- `0x180007804`
- `0x1800088c0`
- `0x180009a90`
- `0x18000a49c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008902`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008902`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008943`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800089a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008943`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800089a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008982`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008982`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008990`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008990`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008953`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008938`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008938`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008974`

## string_xrefs

- `0x180008a3f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008a67`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008a81`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
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
  _BYTE v13[64]; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v14[64]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v15[104]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v13);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v13,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v14,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v15,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v13);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v13);
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
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
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
      wil::details_abi::FeatureStateData::~FeatureStateData((wil::details_abi::FeatureStateData *)(lpMem + 32));
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      v9 = (void *)*((_QWORD *)lpMem + 1);
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
0x1800088c0  push    rbx
0x1800088c2  push    rbp
0x1800088c3  push    rsi
0x1800088c4  push    rdi
0x1800088c5  sub     rsp, 0E8h
0x1800088cc  mov     rbx, rcx
0x1800088cf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800088d6  jnz     loc_1800089B7
0x1800088dc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800088e3  test    rax, rax
0x1800088e6  jz      short loc_1800088F5
0x1800088e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ed  test    al, al
0x1800088ef  jnz     loc_1800089B7
0x1800088f5  mov     rdi, [rbx+8]
0x1800088f9  xor     r8d, r8d; bAlertable
0x1800088fc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800088ff  mov     rcx, rdi; hHandle
0x180008902  call    cs:__imp_WaitForSingleObjectEx
0x180008908  cmp     eax, 102h
0x18000890d  jz      short loc_18000891C
0x18000890f  test    eax, 0FFFFFF7Fh
0x180008914  jnz     loc_180008A51
0x18000891a  jmp     short loc_18000891E
0x18000891c  xor     edi, edi
0x18000891e  mov     eax, [rbx]
0x180008920  dec     eax
0x180008922  mov     [rbx], eax
0x180008924  mov     eax, [rbx]
0x180008926  test    eax, eax
0x180008928  jnz     short loc_18000899B
0x18000892a  lea     rcx, [rbx+10h]; this
0x18000892e  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180008933  test    rdi, rdi
0x180008936  jz      short loc_180008959
0x180008938  call    cs:__imp_GetLastError
0x18000893e  mov     ebp, eax
0x180008940  mov     rcx, rdi; hMutex
0x180008943  call    cs:__imp_ReleaseMutex
0x180008949  test    eax, eax
0x18000894b  jz      loc_180008A79
0x180008951  mov     ecx, ebp; dwErrCode
0x180008953  call    cs:__imp_SetLastError
0x180008959  lea     rcx, [rbx+20h]; this
0x18000895d  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x180008962  lea     rcx, [rbx+10h]; this
0x180008966  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000896b  mov     rcx, [rbx+8]; hObject
0x18000896f  test    rcx, rcx
0x180008972  jz      short loc_180008982
0x180008974  call    cs:__imp_CloseHandle
0x18000897a  test    eax, eax
0x18000897c  jz      loc_180008A37
0x180008982  call    cs:__imp_GetProcessHeap
0x180008988  mov     rcx, rax; hHeap
0x18000898b  mov     r8, rbx; lpMem
0x18000898e  xor     edx, edx; dwFlags
0x180008990  call    cs:__imp_HeapFree
0x180008996  jmp     loc_180008A2B
0x18000899b  test    rdi, rdi
0x18000899e  jz      loc_180008A2B
0x1800089a4  mov     rcx, rdi; hMutex
0x1800089a7  call    cs:__imp_ReleaseMutex
0x1800089ad  test    eax, eax
0x1800089af  jz      loc_180008A5F
0x1800089b5  jmp     short loc_180008A2B
0x1800089b7  mov     eax, [rbx]
0x1800089b9  dec     eax
0x1800089bb  mov     [rbx], eax
0x1800089bd  mov     eax, [rbx]
0x1800089bf  test    eax, eax
0x1800089c1  jnz     short loc_180008A2B
0x1800089c3  lea     rcx, [rsp+108h+var_E8]; this
0x1800089c8  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800089cd  nop
0x1800089ce  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x1800089d2  cmp     byte ptr [rdx+38h], 0
0x1800089d6  jz      short loc_1800089E2
0x1800089d8  lea     rcx, [rsp+108h+var_E8]; this
0x1800089dd  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800089e2  cmp     byte ptr [rbx+0A0h], 0
0x1800089e9  jz      short loc_1800089F9
0x1800089eb  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x1800089ef  lea     rcx, [rsp+108h+var_A8]; this
0x1800089f4  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800089f9  cmp     byte ptr [rbx+0E0h], 0
0x180008a00  jz      short loc_180008A16
0x180008a02  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x180008a09  lea     rcx, [rsp+108h+var_68]; this
0x180008a11  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008a16  lea     rcx, [rsp+108h+var_E8]; this
0x180008a1b  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180008a20  nop
0x180008a21  lea     rcx, [rsp+108h+var_E8]; this
0x180008a26  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008a2b  add     rsp, 0E8h
0x180008a32  pop     rdi
0x180008a33  pop     rsi
0x180008a34  pop     rbp
0x180008a35  pop     rbx
0x180008a36  retn
0x180008a37  mov     rcx, [rsp+108h]; this
0x180008a3f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008a46  mov     edx, 0A0Bh; void *
0x180008a4b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a51  mov     rcx, [rsp+108h]; this
0x180008a59  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008a5f  mov     rcx, [rsp+108h]; this
0x180008a67  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008a6e  mov     edx, 0A15h; void *
0x180008a73  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008a79  mov     rcx, [rsp+108h]; this
0x180008a81  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008a88  mov     edx, 0A15h; void *
0x180008a8d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
