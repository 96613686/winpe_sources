# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000a898`
- end: `0x18000aa77`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `479`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1800087e4`
- `0x1800c9630`

## callees

- `0x18000494c`
- `0x1800051e0`
- `0x180005290`
- `0x18000771c`
- `0x180008414`
- `0x18000870c`
- `0x180008a10`
- `0x180009a08`
- `0x18000a898`
- `0x18000afb0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a91b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a97f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a91b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a97f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a8da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a8da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a95a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a95a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a968`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a92b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a910`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a94c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a94c`

## string_xrefs

- `0x18000aa17`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000aa31`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000aa4b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000aa65`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000a898  push    rbx
0x18000a89a  push    rbp
0x18000a89b  push    rsi
0x18000a89c  push    rdi
0x18000a89d  sub     rsp, 0E8h
0x18000a8a4  mov     rbx, rcx
0x18000a8a7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a8ae  jnz     loc_18000A98F
0x18000a8b4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a8bb  test    rax, rax
0x18000a8be  jz      short loc_18000A8CD
0x18000a8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8c5  test    al, al
0x18000a8c7  jnz     loc_18000A98F
0x18000a8cd  mov     rdi, [rbx+8]
0x18000a8d1  xor     r8d, r8d; bAlertable
0x18000a8d4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a8d7  mov     rcx, rdi; hHandle
0x18000a8da  call    cs:__imp_WaitForSingleObjectEx
0x18000a8e0  cmp     eax, 102h
0x18000a8e5  jz      short loc_18000A8F4
0x18000a8e7  test    eax, 0FFFFFF7Fh
0x18000a8ec  jnz     loc_18000AA29
0x18000a8f2  jmp     short loc_18000A8F6
0x18000a8f4  xor     edi, edi
0x18000a8f6  mov     eax, [rbx]
0x18000a8f8  dec     eax
0x18000a8fa  mov     [rbx], eax
0x18000a8fc  mov     eax, [rbx]
0x18000a8fe  test    eax, eax
0x18000a900  jnz     short loc_18000A973
0x18000a902  lea     rcx, [rbx+10h]; this
0x18000a906  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000a90b  test    rdi, rdi
0x18000a90e  jz      short loc_18000A931
0x18000a910  call    cs:__imp_GetLastError
0x18000a916  mov     ebp, eax
0x18000a918  mov     rcx, rdi; hMutex
0x18000a91b  call    cs:__imp_ReleaseMutex
0x18000a921  test    eax, eax
0x18000a923  jz      loc_18000AA5D
0x18000a929  mov     ecx, ebp; dwErrCode
0x18000a92b  call    cs:__imp_SetLastError
0x18000a931  lea     rcx, [rbx+20h]; this
0x18000a935  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x18000a93a  lea     rcx, [rbx+10h]; this
0x18000a93e  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a943  mov     rcx, [rbx+8]; hObject
0x18000a947  test    rcx, rcx
0x18000a94a  jz      short loc_18000A95A
0x18000a94c  call    cs:__imp_CloseHandle
0x18000a952  test    eax, eax
0x18000a954  jz      loc_18000AA0F
0x18000a95a  call    cs:__imp_GetProcessHeap
0x18000a960  mov     rcx, rax; hHeap
0x18000a963  mov     r8, rbx; lpMem
0x18000a966  xor     edx, edx; dwFlags
0x18000a968  call    cs:__imp_HeapFree
0x18000a96e  jmp     loc_18000AA03
0x18000a973  test    rdi, rdi
0x18000a976  jz      loc_18000AA03
0x18000a97c  mov     rcx, rdi; hMutex
0x18000a97f  call    cs:__imp_ReleaseMutex
0x18000a985  test    eax, eax
0x18000a987  jz      loc_18000AA43
0x18000a98d  jmp     short loc_18000AA03
0x18000a98f  mov     eax, [rbx]
0x18000a991  dec     eax
0x18000a993  mov     [rbx], eax
0x18000a995  mov     eax, [rbx]
0x18000a997  test    eax, eax
0x18000a999  jnz     short loc_18000AA03
0x18000a99b  lea     rcx, [rsp+108h+var_E8]; this
0x18000a9a0  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a9a5  nop
0x18000a9a6  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000a9aa  cmp     byte ptr [rdx+38h], 0
0x18000a9ae  jz      short loc_18000A9BA
0x18000a9b0  lea     rcx, [rsp+108h+var_E8]; this
0x18000a9b5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a9ba  cmp     byte ptr [rbx+0A0h], 0
0x18000a9c1  jz      short loc_18000A9D1
0x18000a9c3  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000a9c7  lea     rcx, [rsp+108h+var_A8]; this
0x18000a9cc  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a9d1  cmp     byte ptr [rbx+0E0h], 0
0x18000a9d8  jz      short loc_18000A9EE
0x18000a9da  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000a9e1  lea     rcx, [rsp+108h+var_68]; this
0x18000a9e9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a9ee  lea     rcx, [rsp+108h+var_E8]; this
0x18000a9f3  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000a9f8  nop
0x18000a9f9  lea     rcx, [rsp+108h+var_E8]; this
0x18000a9fe  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000aa03  add     rsp, 0E8h
0x18000aa0a  pop     rdi
0x18000aa0b  pop     rsi
0x18000aa0c  pop     rbp
0x18000aa0d  pop     rbx
0x18000aa0e  retn
0x18000aa0f  mov     rcx, [rsp+108h]; this
0x18000aa17  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000aa1e  mov     edx, 0A0Bh; void *
0x18000aa23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aa29  mov     rcx, [rsp+108h]; this
0x18000aa31  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000aa38  mov     edx, 0E01h; void *
0x18000aa3d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000aa43  mov     rcx, [rsp+108h]; this
0x18000aa4b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000aa52  mov     edx, 0A15h; void *
0x18000aa57  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aa5d  mov     rcx, [rsp+108h]; this
0x18000aa65  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000aa6c  mov     edx, 0A15h; void *
0x18000aa71  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
