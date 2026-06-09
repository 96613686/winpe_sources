# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000e74c`
- end: `0x18000e92b`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `479`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180007a88`
- `0x1800d08c0`

## callees

- `0x18000724c`
- `0x1800079b0`
- `0x180007d38`
- `0x180007e8c`
- `0x180008d50`
- `0x180009060`
- `0x18000d71c`
- `0x18000e74c`
- `0x18000fb30`
- `0x1800108d4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000e78e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000e78e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e7cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e833`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e7cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000e833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e80e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e80e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e81c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e81c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e800`

## string_xrefs

- `0x18000e8cb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e8e5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e8ff`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e919`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      wil::details::in1diag3::FailFast_Unexpected(
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
0x18000e74c  push    rbx
0x18000e74e  push    rbp
0x18000e74f  push    rsi
0x18000e750  push    rdi
0x18000e751  sub     rsp, 0E8h
0x18000e758  mov     rbx, rcx
0x18000e75b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000e762  jnz     loc_18000E843
0x18000e768  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e76f  test    rax, rax
0x18000e772  jz      short loc_18000E781
0x18000e774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e779  test    al, al
0x18000e77b  jnz     loc_18000E843
0x18000e781  mov     rdi, [rbx+8]
0x18000e785  xor     r8d, r8d; bAlertable
0x18000e788  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000e78b  mov     rcx, rdi; hHandle
0x18000e78e  call    cs:__imp_WaitForSingleObjectEx
0x18000e794  cmp     eax, 102h
0x18000e799  jz      short loc_18000E7A8
0x18000e79b  test    eax, 0FFFFFF7Fh
0x18000e7a0  jnz     loc_18000E8DD
0x18000e7a6  jmp     short loc_18000E7AA
0x18000e7a8  xor     edi, edi
0x18000e7aa  mov     eax, [rbx]
0x18000e7ac  dec     eax
0x18000e7ae  mov     [rbx], eax
0x18000e7b0  mov     eax, [rbx]
0x18000e7b2  test    eax, eax
0x18000e7b4  jnz     short loc_18000E827
0x18000e7b6  lea     rcx, [rbx+10h]; this
0x18000e7ba  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000e7bf  test    rdi, rdi
0x18000e7c2  jz      short loc_18000E7E5
0x18000e7c4  call    cs:__imp_GetLastError
0x18000e7ca  mov     ebp, eax
0x18000e7cc  mov     rcx, rdi; hMutex
0x18000e7cf  call    cs:__imp_ReleaseMutex
0x18000e7d5  test    eax, eax
0x18000e7d7  jz      loc_18000E911
0x18000e7dd  mov     ecx, ebp; dwErrCode
0x18000e7df  call    cs:__imp_SetLastError
0x18000e7e5  lea     rcx, [rbx+20h]; this
0x18000e7e9  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x18000e7ee  lea     rcx, [rbx+10h]; this
0x18000e7f2  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000e7f7  mov     rcx, [rbx+8]; hObject
0x18000e7fb  test    rcx, rcx
0x18000e7fe  jz      short loc_18000E80E
0x18000e800  call    cs:__imp_CloseHandle
0x18000e806  test    eax, eax
0x18000e808  jz      loc_18000E8C3
0x18000e80e  call    cs:__imp_GetProcessHeap
0x18000e814  mov     rcx, rax; hHeap
0x18000e817  mov     r8, rbx; lpMem
0x18000e81a  xor     edx, edx; dwFlags
0x18000e81c  call    cs:__imp_HeapFree
0x18000e822  jmp     loc_18000E8B7
0x18000e827  test    rdi, rdi
0x18000e82a  jz      loc_18000E8B7
0x18000e830  mov     rcx, rdi; hMutex
0x18000e833  call    cs:__imp_ReleaseMutex
0x18000e839  test    eax, eax
0x18000e83b  jz      loc_18000E8F7
0x18000e841  jmp     short loc_18000E8B7
0x18000e843  mov     eax, [rbx]
0x18000e845  dec     eax
0x18000e847  mov     [rbx], eax
0x18000e849  mov     eax, [rbx]
0x18000e84b  test    eax, eax
0x18000e84d  jnz     short loc_18000E8B7
0x18000e84f  lea     rcx, [rsp+108h+var_E8]; this
0x18000e854  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000e859  nop
0x18000e85a  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000e85e  cmp     byte ptr [rdx+38h], 0
0x18000e862  jz      short loc_18000E86E
0x18000e864  lea     rcx, [rsp+108h+var_E8]; this
0x18000e869  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000e86e  cmp     byte ptr [rbx+0A0h], 0
0x18000e875  jz      short loc_18000E885
0x18000e877  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000e87b  lea     rcx, [rsp+108h+var_A8]; this
0x18000e880  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000e885  cmp     byte ptr [rbx+0E0h], 0
0x18000e88c  jz      short loc_18000E8A2
0x18000e88e  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000e895  lea     rcx, [rsp+108h+var_68]; this
0x18000e89d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000e8a2  lea     rcx, [rsp+108h+var_E8]; this
0x18000e8a7  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000e8ac  nop
0x18000e8ad  lea     rcx, [rsp+108h+var_E8]; this
0x18000e8b2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000e8b7  add     rsp, 0E8h
0x18000e8be  pop     rdi
0x18000e8bf  pop     rsi
0x18000e8c0  pop     rbp
0x18000e8c1  pop     rbx
0x18000e8c2  retn
0x18000e8c3  mov     rcx, [rsp+108h]; this
0x18000e8cb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e8d2  mov     edx, 0A0Bh; void *
0x18000e8d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e8dd  mov     rcx, [rsp+108h]; this
0x18000e8e5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e8ec  mov     edx, 0E01h; void *
0x18000e8f1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000e8f7  mov     rcx, [rsp+108h]; this
0x18000e8ff  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e906  mov     edx, 0A15h; void *
0x18000e90b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e911  mov     rcx, [rsp+108h]; this
0x18000e919  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e920  mov     edx, 0A15h; void *
0x18000e925  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
