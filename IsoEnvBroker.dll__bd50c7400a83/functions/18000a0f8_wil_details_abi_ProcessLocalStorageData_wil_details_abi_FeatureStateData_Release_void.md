# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000a0f8`
- end: `0x18000a2d7`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `479`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180006290`
- `0x1800670d0`

## callees

- `0x180005df8`
- `0x1800061b8`
- `0x180006540`
- `0x180006694`
- `0x1800072e0`
- `0x1800075e4`
- `0x1800090c4`
- `0x18000a0f8`
- `0x18000b2d0`
- `0x18000bd98`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a17b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1df`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a17b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a13a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a13a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a170`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a18b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a18b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1ac`

## string_xrefs

- `0x18000a277`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000a291`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000a2ab`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000a2c5`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v4);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
0x18000a0f8  push    rbx
0x18000a0fa  push    rbp
0x18000a0fb  push    rsi
0x18000a0fc  push    rdi
0x18000a0fd  sub     rsp, 0E8h
0x18000a104  mov     rbx, rcx
0x18000a107  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a10e  jnz     loc_18000A1EF
0x18000a114  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a11b  test    rax, rax
0x18000a11e  jz      short loc_18000A12D
0x18000a120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a125  test    al, al
0x18000a127  jnz     loc_18000A1EF
0x18000a12d  mov     rdi, [rbx+8]
0x18000a131  xor     r8d, r8d; bAlertable
0x18000a134  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a137  mov     rcx, rdi; hHandle
0x18000a13a  call    cs:__imp_WaitForSingleObjectEx
0x18000a140  cmp     eax, 102h
0x18000a145  jz      short loc_18000A154
0x18000a147  test    eax, 0FFFFFF7Fh
0x18000a14c  jnz     loc_18000A289
0x18000a152  jmp     short loc_18000A156
0x18000a154  xor     edi, edi
0x18000a156  mov     eax, [rbx]
0x18000a158  dec     eax
0x18000a15a  mov     [rbx], eax
0x18000a15c  mov     eax, [rbx]
0x18000a15e  test    eax, eax
0x18000a160  jnz     short loc_18000A1D3
0x18000a162  lea     rcx, [rbx+10h]; this
0x18000a166  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000a16b  test    rdi, rdi
0x18000a16e  jz      short loc_18000A191
0x18000a170  call    cs:__imp_GetLastError
0x18000a176  mov     ebp, eax
0x18000a178  mov     rcx, rdi; hMutex
0x18000a17b  call    cs:__imp_ReleaseMutex
0x18000a181  test    eax, eax
0x18000a183  jz      loc_18000A2BD
0x18000a189  mov     ecx, ebp; dwErrCode
0x18000a18b  call    cs:__imp_SetLastError
0x18000a191  lea     rcx, [rbx+20h]; this
0x18000a195  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x18000a19a  lea     rcx, [rbx+10h]; this
0x18000a19e  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a1a3  mov     rcx, [rbx+8]; hObject
0x18000a1a7  test    rcx, rcx
0x18000a1aa  jz      short loc_18000A1BA
0x18000a1ac  call    cs:__imp_CloseHandle
0x18000a1b2  test    eax, eax
0x18000a1b4  jz      loc_18000A26F
0x18000a1ba  call    cs:__imp_GetProcessHeap
0x18000a1c0  mov     rcx, rax; hHeap
0x18000a1c3  mov     r8, rbx; lpMem
0x18000a1c6  xor     edx, edx; dwFlags
0x18000a1c8  call    cs:__imp_HeapFree
0x18000a1ce  jmp     loc_18000A263
0x18000a1d3  test    rdi, rdi
0x18000a1d6  jz      loc_18000A263
0x18000a1dc  mov     rcx, rdi; hMutex
0x18000a1df  call    cs:__imp_ReleaseMutex
0x18000a1e5  test    eax, eax
0x18000a1e7  jz      loc_18000A2A3
0x18000a1ed  jmp     short loc_18000A263
0x18000a1ef  mov     eax, [rbx]
0x18000a1f1  dec     eax
0x18000a1f3  mov     [rbx], eax
0x18000a1f5  mov     eax, [rbx]
0x18000a1f7  test    eax, eax
0x18000a1f9  jnz     short loc_18000A263
0x18000a1fb  lea     rcx, [rsp+108h+var_E8]; this
0x18000a200  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a205  nop
0x18000a206  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000a20a  cmp     byte ptr [rdx+38h], 0
0x18000a20e  jz      short loc_18000A21A
0x18000a210  lea     rcx, [rsp+108h+var_E8]; this
0x18000a215  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a21a  cmp     byte ptr [rbx+0A0h], 0
0x18000a221  jz      short loc_18000A231
0x18000a223  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000a227  lea     rcx, [rsp+108h+var_A8]; this
0x18000a22c  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a231  cmp     byte ptr [rbx+0E0h], 0
0x18000a238  jz      short loc_18000A24E
0x18000a23a  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000a241  lea     rcx, [rsp+108h+var_68]; this
0x18000a249  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a24e  lea     rcx, [rsp+108h+var_E8]; this
0x18000a253  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000a258  nop
0x18000a259  lea     rcx, [rsp+108h+var_E8]; this
0x18000a25e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000a263  add     rsp, 0E8h
0x18000a26a  pop     rdi
0x18000a26b  pop     rsi
0x18000a26c  pop     rbp
0x18000a26d  pop     rbx
0x18000a26e  retn
0x18000a26f  mov     rcx, [rsp+108h]; this
0x18000a277  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a27e  mov     edx, 0A0Bh; void *
0x18000a283  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a289  mov     rcx, [rsp+108h]; this
0x18000a291  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a298  mov     edx, 0E01h; void *
0x18000a29d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a2a3  mov     rcx, [rsp+108h]; this
0x18000a2ab  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a2b2  mov     edx, 0A15h; void *
0x18000a2b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2bd  mov     rcx, [rsp+108h]; this
0x18000a2c5  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a2cc  mov     edx, 0A15h; void *
0x18000a2d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
