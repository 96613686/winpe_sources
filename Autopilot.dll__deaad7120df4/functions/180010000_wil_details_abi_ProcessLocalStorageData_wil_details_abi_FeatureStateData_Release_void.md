# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180010000`
- end: `0x18001020d`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `525`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000b048`
- `0x18002e190`

## callees

- `0x18000ab6c`
- `0x18000af60`
- `0x18000b2f8`
- `0x18000b480`
- `0x18000c554`
- `0x18000cac8`
- `0x18000eec4`
- `0x180010000`
- `0x180011658`
- `0x180012220`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010042`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010042`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010093`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010115`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010093`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010115`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800100e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800100e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800100f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800100f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010082`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100d0`

## string_xrefs

- `0x1800101b4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800101e1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800101fb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  __int64 v4; // r8
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
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
0x180010000  push    rbx
0x180010002  push    rbp
0x180010003  push    rsi
0x180010004  push    rdi
0x180010005  sub     rsp, 0E8h
0x18001000c  mov     rbx, rcx
0x18001000f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180010016  jnz     loc_18001012B
0x18001001c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180010023  test    rax, rax
0x180010026  jz      short loc_180010035
0x180010028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001002d  test    al, al
0x18001002f  jnz     loc_18001012B
0x180010035  mov     rdi, [rbx+8]
0x180010039  xor     r8d, r8d; bAlertable
0x18001003c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001003f  mov     rcx, rdi; hHandle
0x180010042  call    cs:__imp_WaitForSingleObjectEx
0x180010049  nop     dword ptr [rax+rax+00h]
0x18001004e  cmp     eax, 102h
0x180010053  jz      short loc_180010062
0x180010055  test    eax, 0FFFFFF7Fh
0x18001005a  jnz     loc_1800101C6
0x180010060  jmp     short loc_180010064
0x180010062  xor     edi, edi
0x180010064  mov     eax, [rbx]
0x180010066  dec     eax
0x180010068  mov     [rbx], eax
0x18001006a  mov     eax, [rbx]
0x18001006c  test    eax, eax
0x18001006e  jnz     loc_180010109
0x180010074  lea     rcx, [rbx+10h]; this
0x180010078  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18001007d  test    rdi, rdi
0x180010080  jz      short loc_1800100B5
0x180010082  call    cs:__imp_GetLastError
0x180010089  nop     dword ptr [rax+rax+00h]
0x18001008e  mov     ebp, eax
0x180010090  mov     rcx, rdi; hMutex
0x180010093  call    cs:__imp_ReleaseMutex
0x18001009a  nop     dword ptr [rax+rax+00h]
0x18001009f  test    eax, eax
0x1800100a1  jz      loc_1800101F3
0x1800100a7  mov     ecx, ebp; dwErrCode
0x1800100a9  call    cs:__imp_SetLastError
0x1800100b0  nop     dword ptr [rax+rax+00h]
0x1800100b5  lea     rcx, [rbx+20h]; this
0x1800100b9  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x1800100be  lea     rcx, [rbx+10h]; this
0x1800100c2  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800100c7  mov     rcx, [rbx+8]; hObject
0x1800100cb  test    rcx, rcx
0x1800100ce  jz      short loc_1800100E4
0x1800100d0  call    cs:__imp_CloseHandle
0x1800100d7  nop     dword ptr [rax+rax+00h]
0x1800100dc  test    eax, eax
0x1800100de  jz      loc_1800101AC
0x1800100e4  call    cs:__imp_GetProcessHeap
0x1800100eb  nop     dword ptr [rax+rax+00h]
0x1800100f0  mov     rcx, rax; hHeap
0x1800100f3  mov     r8, rbx; lpMem
0x1800100f6  xor     edx, edx; dwFlags
0x1800100f8  call    cs:__imp_HeapFree
0x1800100ff  nop     dword ptr [rax+rax+00h]
0x180010104  jmp     loc_18001019F
0x180010109  test    rdi, rdi
0x18001010c  jz      loc_18001019F
0x180010112  mov     rcx, rdi; hMutex
0x180010115  call    cs:__imp_ReleaseMutex
0x18001011c  nop     dword ptr [rax+rax+00h]
0x180010121  test    eax, eax
0x180010123  jz      loc_1800101D9
0x180010129  jmp     short loc_18001019F
0x18001012b  mov     eax, [rbx]
0x18001012d  dec     eax
0x18001012f  mov     [rbx], eax
0x180010131  mov     eax, [rbx]
0x180010133  test    eax, eax
0x180010135  jnz     short loc_18001019F
0x180010137  lea     rcx, [rsp+108h+var_E8]; this
0x18001013c  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180010141  nop
0x180010142  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x180010146  cmp     byte ptr [rdx+38h], 0
0x18001014a  jz      short loc_180010156
0x18001014c  lea     rcx, [rsp+108h+var_E8]; this
0x180010151  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010156  cmp     byte ptr [rbx+0A0h], 0
0x18001015d  jz      short loc_18001016D
0x18001015f  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180010163  lea     rcx, [rsp+108h+var_A8]; this
0x180010168  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001016d  cmp     byte ptr [rbx+0E0h], 0
0x180010174  jz      short loc_18001018A
0x180010176  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18001017d  lea     rcx, [rsp+108h+var_68]; this
0x180010185  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001018a  lea     rcx, [rsp+108h+var_E8]; this
0x18001018f  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180010194  nop
0x180010195  lea     rcx, [rsp+108h+var_E8]; this
0x18001019a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001019f  add     rsp, 0E8h
0x1800101a6  pop     rdi
0x1800101a7  pop     rsi
0x1800101a8  pop     rbp
0x1800101a9  pop     rbx
0x1800101aa  retn
0x1800101ac  mov     rcx, [rsp+108h]; this
0x1800101b4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800101bb  mov     edx, 0A0Bh; void *
0x1800101c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800101c6  mov     rcx, [rsp+108h]; this
0x1800101ce  mov     edx, 0E01h; void *
0x1800101d3  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800101d9  mov     rcx, [rsp+108h]; this
0x1800101e1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800101e8  mov     edx, 0A15h; void *
0x1800101ed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800101f3  mov     rcx, [rsp+108h]; this
0x1800101fb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010202  mov     edx, 0A15h; void *
0x180010207  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
