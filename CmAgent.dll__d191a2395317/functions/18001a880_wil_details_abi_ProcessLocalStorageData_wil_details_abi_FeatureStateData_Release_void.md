# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18001a880`
- end: `0x18001aa7f`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `511`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18001548c`
- `0x180037060`

## callees

- `0x180003ce4`
- `0x180005c5c`
- `0x180006504`
- `0x180009518`
- `0x180014c64`
- `0x1800153a4`
- `0x1800157d0`
- `0x180019a94`
- `0x18001a880`
- `0x18001f94c`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001a913`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001a995`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001a913`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001a995`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001a8c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001a8c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a964`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a964`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a978`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a902`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a929`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a929`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a950`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a950`

## string_xrefs

- `0x18001aa47`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // ebp
  __int64 v6; // r8
  const char *v7; // r9
  void *v8; // rcx
  __int64 v9; // r8
  const char *v10; // r9
  HANDLE ProcessHeap; // rax
  __int64 v12; // r8
  const char *v13; // r9
  _BYTE v14[64]; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v15[64]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v16[104]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v14);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v14,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v15,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v16,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v14);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v14);
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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v12, v13);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v6, v7);
        SetLastError(LastError);
      }
      wil::details_abi::FeatureStateData::~FeatureStateData((wil::details_abi::FeatureStateData *)(lpMem + 32));
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      v8 = (void *)*((_QWORD *)lpMem + 1);
      if ( v8 )
      {
        if ( !CloseHandle(v8) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x18001a880  push    rbx
0x18001a882  push    rbp
0x18001a883  push    rsi
0x18001a884  push    rdi
0x18001a885  sub     rsp, 0E8h
0x18001a88c  mov     rbx, rcx
0x18001a88f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001a896  jnz     loc_18001A9AB
0x18001a89c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001a8a3  test    rax, rax
0x18001a8a6  jz      short loc_18001A8B5
0x18001a8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8ad  test    al, al
0x18001a8af  jnz     loc_18001A9AB
0x18001a8b5  mov     rdi, [rbx+8]
0x18001a8b9  xor     r8d, r8d; bAlertable
0x18001a8bc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001a8bf  mov     rcx, rdi; hHandle
0x18001a8c2  call    cs:__imp_WaitForSingleObjectEx
0x18001a8c9  nop     dword ptr [rax+rax+00h]
0x18001a8ce  cmp     eax, 102h
0x18001a8d3  jz      short loc_18001A8E2
0x18001a8d5  test    eax, 0FFFFFF7Fh
0x18001a8da  jnz     loc_18001AA3F
0x18001a8e0  jmp     short loc_18001A8E4
0x18001a8e2  xor     edi, edi
0x18001a8e4  mov     eax, [rbx]
0x18001a8e6  dec     eax
0x18001a8e8  mov     [rbx], eax
0x18001a8ea  mov     eax, [rbx]
0x18001a8ec  test    eax, eax
0x18001a8ee  jnz     loc_18001A989
0x18001a8f4  lea     rcx, [rbx+10h]; this
0x18001a8f8  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18001a8fd  test    rdi, rdi
0x18001a900  jz      short loc_18001A935
0x18001a902  call    cs:__imp_GetLastError
0x18001a909  nop     dword ptr [rax+rax+00h]
0x18001a90e  mov     ebp, eax
0x18001a910  mov     rcx, rdi; hMutex
0x18001a913  call    cs:__imp_ReleaseMutex
0x18001a91a  nop     dword ptr [rax+rax+00h]
0x18001a91f  test    eax, eax
0x18001a921  jz      loc_18001AA6C
0x18001a927  mov     ecx, ebp; dwErrCode
0x18001a929  call    cs:__imp_SetLastError
0x18001a930  nop     dword ptr [rax+rax+00h]
0x18001a935  lea     rcx, [rbx+20h]; this
0x18001a939  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x18001a93e  lea     rcx, [rbx+10h]; this
0x18001a942  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18001a947  mov     rcx, [rbx+8]; hObject
0x18001a94b  test    rcx, rcx
0x18001a94e  jz      short loc_18001A964
0x18001a950  call    cs:__imp_CloseHandle
0x18001a957  nop     dword ptr [rax+rax+00h]
0x18001a95c  test    eax, eax
0x18001a95e  jz      loc_18001AA2C
0x18001a964  call    cs:__imp_GetProcessHeap
0x18001a96b  nop     dword ptr [rax+rax+00h]
0x18001a970  mov     rcx, rax; hHeap
0x18001a973  mov     r8, rbx; lpMem
0x18001a976  xor     edx, edx; dwFlags
0x18001a978  call    cs:__imp_HeapFree
0x18001a97f  nop     dword ptr [rax+rax+00h]
0x18001a984  jmp     loc_18001AA1F
0x18001a989  test    rdi, rdi
0x18001a98c  jz      loc_18001AA1F
0x18001a992  mov     rcx, rdi; hMutex
0x18001a995  call    cs:__imp_ReleaseMutex
0x18001a99c  nop     dword ptr [rax+rax+00h]
0x18001a9a1  test    eax, eax
0x18001a9a3  jz      loc_18001AA59
0x18001a9a9  jmp     short loc_18001AA1F
0x18001a9ab  mov     eax, [rbx]
0x18001a9ad  dec     eax
0x18001a9af  mov     [rbx], eax
0x18001a9b1  mov     eax, [rbx]
0x18001a9b3  test    eax, eax
0x18001a9b5  jnz     short loc_18001AA1F
0x18001a9b7  lea     rcx, [rsp+108h+var_E8]; this
0x18001a9bc  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001a9c1  nop
0x18001a9c2  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18001a9c6  cmp     byte ptr [rdx+38h], 0
0x18001a9ca  jz      short loc_18001A9D6
0x18001a9cc  lea     rcx, [rsp+108h+var_E8]; this
0x18001a9d1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001a9d6  cmp     byte ptr [rbx+0A0h], 0
0x18001a9dd  jz      short loc_18001A9ED
0x18001a9df  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18001a9e3  lea     rcx, [rsp+108h+var_A8]; this
0x18001a9e8  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001a9ed  cmp     byte ptr [rbx+0E0h], 0
0x18001a9f4  jz      short loc_18001AA0A
0x18001a9f6  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18001a9fd  lea     rcx, [rsp+108h+var_68]; this
0x18001aa05  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001aa0a  lea     rcx, [rsp+108h+var_E8]; this
0x18001aa0f  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18001aa14  nop
0x18001aa15  lea     rcx, [rsp+108h+var_E8]; this
0x18001aa1a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001aa1f  add     rsp, 0E8h
0x18001aa26  pop     rdi
0x18001aa27  pop     rsi
0x18001aa28  pop     rbp
0x18001aa29  pop     rbx
0x18001aa2a  retn
0x18001aa2c  mov     rcx, [rsp+108h]; this
0x18001aa34  mov     edx, 0A0Bh; void *
0x18001aa39  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001aa3f  mov     rcx, [rsp+108h]; this
0x18001aa47  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001aa4e  mov     edx, 0E01h; void *
0x18001aa53  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001aa59  mov     rcx, [rsp+108h]; this
0x18001aa61  mov     edx, 0A15h; void *
0x18001aa66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001aa6c  mov     rcx, [rsp+108h]; this
0x18001aa74  mov     edx, 0A15h; void *
0x18001aa79  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
