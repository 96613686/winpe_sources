# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000a118`
- end: `0x18000a2f7`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `479`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000521c`
- `0x180032080`

## callees

- `0x180004c50`
- `0x180005144`
- `0x1800054cc`
- `0x180005620`
- `0x1800067f4`
- `0x180006cb8`
- `0x180008fb8`
- `0x18000a118`
- `0x18000ba9c`
- `0x18000c5d4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a190`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a19b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a19b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a15a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a15a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1cc`

## string_xrefs

- `0x18000a297`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a2b1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a2cb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a2e5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000a118  push    rbx
0x18000a11a  push    rbp
0x18000a11b  push    rsi
0x18000a11c  push    rdi
0x18000a11d  sub     rsp, 0E8h
0x18000a124  mov     rbx, rcx
0x18000a127  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a12e  jnz     loc_18000A20F
0x18000a134  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a13b  test    rax, rax
0x18000a13e  jz      short loc_18000A14D
0x18000a140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a145  test    al, al
0x18000a147  jnz     loc_18000A20F
0x18000a14d  mov     rdi, [rbx+8]
0x18000a151  xor     r8d, r8d; bAlertable
0x18000a154  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a157  mov     rcx, rdi; hHandle
0x18000a15a  call    cs:__imp_WaitForSingleObjectEx
0x18000a160  cmp     eax, 102h
0x18000a165  jz      short loc_18000A174
0x18000a167  test    eax, 0FFFFFF7Fh
0x18000a16c  jnz     loc_18000A2A9
0x18000a172  jmp     short loc_18000A176
0x18000a174  xor     edi, edi
0x18000a176  mov     eax, [rbx]
0x18000a178  dec     eax
0x18000a17a  mov     [rbx], eax
0x18000a17c  mov     eax, [rbx]
0x18000a17e  test    eax, eax
0x18000a180  jnz     short loc_18000A1F3
0x18000a182  lea     rcx, [rbx+10h]; this
0x18000a186  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000a18b  test    rdi, rdi
0x18000a18e  jz      short loc_18000A1B1
0x18000a190  call    cs:__imp_GetLastError
0x18000a196  mov     ebp, eax
0x18000a198  mov     rcx, rdi; hMutex
0x18000a19b  call    cs:__imp_ReleaseMutex
0x18000a1a1  test    eax, eax
0x18000a1a3  jz      loc_18000A2DD
0x18000a1a9  mov     ecx, ebp; dwErrCode
0x18000a1ab  call    cs:__imp_SetLastError
0x18000a1b1  lea     rcx, [rbx+20h]; this
0x18000a1b5  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x18000a1ba  lea     rcx, [rbx+10h]; this
0x18000a1be  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a1c3  mov     rcx, [rbx+8]; hObject
0x18000a1c7  test    rcx, rcx
0x18000a1ca  jz      short loc_18000A1DA
0x18000a1cc  call    cs:__imp_CloseHandle
0x18000a1d2  test    eax, eax
0x18000a1d4  jz      loc_18000A28F
0x18000a1da  call    cs:__imp_GetProcessHeap
0x18000a1e0  mov     rcx, rax; hHeap
0x18000a1e3  mov     r8, rbx; lpMem
0x18000a1e6  xor     edx, edx; dwFlags
0x18000a1e8  call    cs:__imp_HeapFree
0x18000a1ee  jmp     loc_18000A283
0x18000a1f3  test    rdi, rdi
0x18000a1f6  jz      loc_18000A283
0x18000a1fc  mov     rcx, rdi; hMutex
0x18000a1ff  call    cs:__imp_ReleaseMutex
0x18000a205  test    eax, eax
0x18000a207  jz      loc_18000A2C3
0x18000a20d  jmp     short loc_18000A283
0x18000a20f  mov     eax, [rbx]
0x18000a211  dec     eax
0x18000a213  mov     [rbx], eax
0x18000a215  mov     eax, [rbx]
0x18000a217  test    eax, eax
0x18000a219  jnz     short loc_18000A283
0x18000a21b  lea     rcx, [rsp+108h+var_E8]; this
0x18000a220  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a225  nop
0x18000a226  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000a22a  cmp     byte ptr [rdx+38h], 0
0x18000a22e  jz      short loc_18000A23A
0x18000a230  lea     rcx, [rsp+108h+var_E8]; this
0x18000a235  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a23a  cmp     byte ptr [rbx+0A0h], 0
0x18000a241  jz      short loc_18000A251
0x18000a243  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000a247  lea     rcx, [rsp+108h+var_A8]; this
0x18000a24c  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a251  cmp     byte ptr [rbx+0E0h], 0
0x18000a258  jz      short loc_18000A26E
0x18000a25a  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000a261  lea     rcx, [rsp+108h+var_68]; this
0x18000a269  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a26e  lea     rcx, [rsp+108h+var_E8]; this
0x18000a273  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000a278  nop
0x18000a279  lea     rcx, [rsp+108h+var_E8]; this
0x18000a27e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000a283  add     rsp, 0E8h
0x18000a28a  pop     rdi
0x18000a28b  pop     rsi
0x18000a28c  pop     rbp
0x18000a28d  pop     rbx
0x18000a28e  retn
0x18000a28f  mov     rcx, [rsp+108h]; this
0x18000a297  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a29e  mov     edx, 0A0Bh; void *
0x18000a2a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2a9  mov     rcx, [rsp+108h]; this
0x18000a2b1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a2b8  mov     edx, 0E01h; void *
0x18000a2bd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a2c3  mov     rcx, [rsp+108h]; this
0x18000a2cb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a2d2  mov     edx, 0A15h; void *
0x18000a2d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2dd  mov     rcx, [rsp+108h]; this
0x18000a2e5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a2ec  mov     edx, 0A15h; void *
0x18000a2f1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
