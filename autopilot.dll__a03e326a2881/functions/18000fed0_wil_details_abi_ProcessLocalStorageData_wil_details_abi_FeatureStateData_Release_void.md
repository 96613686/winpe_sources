# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000fed0`
- end: `0x1800100a8`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `472`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000afe4`
- `0x18002d2d0`

## callees

- `0x18000aaec`
- `0x18000af0c`
- `0x18000b2a4`
- `0x18000b3f8`
- `0x18000c520`
- `0x18000ca34`
- `0x18000eda0`
- `0x18000fed0`
- `0x180011590`
- `0x180012114`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ff12`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ff12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ff53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ffb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ff53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ffb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ffa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ffa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ff63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ff84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ff84`

## string_xrefs

- `0x18001004f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001007c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010096`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  unsigned int v4; // r8d
  const char *v5; // r9
  DWORD LastError; // ebp
  const char *v7; // r9
  void *v8; // rcx
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  const char *v11; // r9
  _BYTE v12[64]; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v13[64]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v14[104]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v12);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v12,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v13,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v14,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v12);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v12);
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v4, v5);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v11);
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
            v7);
        SetLastError(LastError);
      }
      wil::details_abi::FeatureStateData::~FeatureStateData((wil::details_abi::FeatureStateData *)(lpMem + 32));
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      v8 = (void *)*((_QWORD *)lpMem + 1);
      if ( v8 )
      {
        if ( !CloseHandle(v8) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0xA0B,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v9);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x18000fed0  push    rbx
0x18000fed2  push    rbp
0x18000fed3  push    rsi
0x18000fed4  push    rdi
0x18000fed5  sub     rsp, 0E8h
0x18000fedc  mov     rbx, rcx
0x18000fedf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000fee6  jnz     loc_18000FFC7
0x18000feec  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fef3  test    rax, rax
0x18000fef6  jz      short loc_18000FF05
0x18000fef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fefd  test    al, al
0x18000feff  jnz     loc_18000FFC7
0x18000ff05  mov     rdi, [rbx+8]
0x18000ff09  xor     r8d, r8d; bAlertable
0x18000ff0c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ff0f  mov     rcx, rdi; hHandle
0x18000ff12  call    cs:__imp_WaitForSingleObjectEx
0x18000ff18  cmp     eax, 102h
0x18000ff1d  jz      short loc_18000FF2C
0x18000ff1f  test    eax, 0FFFFFF7Fh
0x18000ff24  jnz     loc_180010061
0x18000ff2a  jmp     short loc_18000FF2E
0x18000ff2c  xor     edi, edi
0x18000ff2e  mov     eax, [rbx]
0x18000ff30  dec     eax
0x18000ff32  mov     [rbx], eax
0x18000ff34  mov     eax, [rbx]
0x18000ff36  test    eax, eax
0x18000ff38  jnz     short loc_18000FFAB
0x18000ff3a  lea     rcx, [rbx+10h]; this
0x18000ff3e  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000ff43  test    rdi, rdi
0x18000ff46  jz      short loc_18000FF69
0x18000ff48  call    cs:__imp_GetLastError
0x18000ff4e  mov     ebp, eax
0x18000ff50  mov     rcx, rdi; hMutex
0x18000ff53  call    cs:__imp_ReleaseMutex
0x18000ff59  test    eax, eax
0x18000ff5b  jz      loc_18001008E
0x18000ff61  mov     ecx, ebp; dwErrCode
0x18000ff63  call    cs:__imp_SetLastError
0x18000ff69  lea     rcx, [rbx+20h]; this
0x18000ff6d  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x18000ff72  lea     rcx, [rbx+10h]; this
0x18000ff76  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ff7b  mov     rcx, [rbx+8]; hObject
0x18000ff7f  test    rcx, rcx
0x18000ff82  jz      short loc_18000FF92
0x18000ff84  call    cs:__imp_CloseHandle
0x18000ff8a  test    eax, eax
0x18000ff8c  jz      loc_180010047
0x18000ff92  call    cs:__imp_GetProcessHeap
0x18000ff98  mov     rcx, rax; hHeap
0x18000ff9b  mov     r8, rbx; lpMem
0x18000ff9e  xor     edx, edx; dwFlags
0x18000ffa0  call    cs:__imp_HeapFree
0x18000ffa6  jmp     loc_18001003B
0x18000ffab  test    rdi, rdi
0x18000ffae  jz      loc_18001003B
0x18000ffb4  mov     rcx, rdi; hMutex
0x18000ffb7  call    cs:__imp_ReleaseMutex
0x18000ffbd  test    eax, eax
0x18000ffbf  jz      loc_180010074
0x18000ffc5  jmp     short loc_18001003B
0x18000ffc7  mov     eax, [rbx]
0x18000ffc9  dec     eax
0x18000ffcb  mov     [rbx], eax
0x18000ffcd  mov     eax, [rbx]
0x18000ffcf  test    eax, eax
0x18000ffd1  jnz     short loc_18001003B
0x18000ffd3  lea     rcx, [rsp+108h+var_E8]; this
0x18000ffd8  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000ffdd  nop
0x18000ffde  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000ffe2  cmp     byte ptr [rdx+38h], 0
0x18000ffe6  jz      short loc_18000FFF2
0x18000ffe8  lea     rcx, [rsp+108h+var_E8]; this
0x18000ffed  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000fff2  cmp     byte ptr [rbx+0A0h], 0
0x18000fff9  jz      short loc_180010009
0x18000fffb  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000ffff  lea     rcx, [rsp+108h+var_A8]; this
0x180010004  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010009  cmp     byte ptr [rbx+0E0h], 0
0x180010010  jz      short loc_180010026
0x180010012  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x180010019  lea     rcx, [rsp+108h+var_68]; this
0x180010021  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010026  lea     rcx, [rsp+108h+var_E8]; this
0x18001002b  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180010030  nop
0x180010031  lea     rcx, [rsp+108h+var_E8]; this
0x180010036  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001003b  add     rsp, 0E8h
0x180010042  pop     rdi
0x180010043  pop     rsi
0x180010044  pop     rbp
0x180010045  pop     rbx
0x180010046  retn
0x180010047  mov     rcx, [rsp+108h]; this
0x18001004f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010056  mov     edx, 0A0Bh; void *
0x18001005b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010061  mov     rcx, [rsp+108h]; this
0x180010069  mov     edx, 0E01h; void *
0x18001006e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180010074  mov     rcx, [rsp+108h]; this
0x18001007c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010083  mov     edx, 0A15h; void *
0x180010088  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001008e  mov     rcx, [rsp+108h]; this
0x180010096  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001009d  mov     edx, 0A15h; void *
0x1800100a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
