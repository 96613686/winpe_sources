# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180016140`
- end: `0x1800162e3`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `419`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18001067c`
- `0x18001d650`

## callees

- `0x180007930`
- `0x18001029c`
- `0x180010364`
- `0x180010870`
- `0x180012f3c`
- `0x1800152d0`
- `0x180016140`
- `0x180017520`
- `0x180017f00`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800161e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800161e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800161f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800161f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800161c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001620c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800161c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001620c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180016188`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180016188`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800161d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800161d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161be`

## string_xrefs

- `0x1800162be`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v9; // r8d
  const char *v10; // r9
  _BYTE v11[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v12[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v13[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v9, v10);
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
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(lpMem);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x180016140  mov     [rsp+arg_0], rbx
0x180016145  mov     [rsp+arg_8], rsi
0x18001614a  push    rdi
0x18001614b  sub     rsp, 0E0h
0x180016152  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180016159  mov     rbx, rcx
0x18001615c  jnz     loc_18001621C
0x180016162  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180016169  test    rax, rax
0x18001616c  jz      short loc_18001617B
0x18001616e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016173  test    al, al
0x180016175  jnz     loc_18001621C
0x18001617b  mov     rdi, [rbx+8]
0x18001617f  xor     r8d, r8d; bAlertable
0x180016182  mov     rcx, rdi; hHandle
0x180016185  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180016188  call    cs:__imp_WaitForSingleObjectEx
0x18001618e  cmp     eax, 102h
0x180016193  jz      short loc_1800161A2
0x180016195  test    eax, 0FFFFFF7Fh
0x18001619a  jnz     loc_1800162B6
0x1800161a0  jmp     short loc_1800161A4
0x1800161a2  xor     edi, edi
0x1800161a4  mov     eax, [rbx]
0x1800161a6  dec     eax
0x1800161a8  mov     [rbx], eax
0x1800161aa  mov     eax, [rbx]
0x1800161ac  test    eax, eax
0x1800161ae  jnz     short loc_180016200
0x1800161b0  lea     rcx, [rbx+10h]; this
0x1800161b4  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x1800161b9  test    rdi, rdi
0x1800161bc  jz      short loc_1800161DF
0x1800161be  call    cs:__imp_GetLastError
0x1800161c4  mov     rcx, rdi; hMutex
0x1800161c7  mov     esi, eax
0x1800161c9  call    cs:__imp_ReleaseMutex
0x1800161cf  test    eax, eax
0x1800161d1  jz      loc_1800162A3
0x1800161d7  mov     ecx, esi; dwErrCode
0x1800161d9  call    cs:__imp_SetLastError
0x1800161df  mov     rcx, rbx
0x1800161e2  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x1800161e7  call    cs:__imp_GetProcessHeap
0x1800161ed  mov     r8, rbx; lpMem
0x1800161f0  xor     edx, edx; dwFlags
0x1800161f2  mov     rcx, rax; hHeap
0x1800161f5  call    cs:__imp_HeapFree
0x1800161fb  jmp     loc_18001628E
0x180016200  test    rdi, rdi
0x180016203  jz      loc_18001628E
0x180016209  mov     rcx, rdi; hMutex
0x18001620c  call    cs:__imp_ReleaseMutex
0x180016212  test    eax, eax
0x180016214  jz      loc_1800162D0
0x18001621a  jmp     short loc_18001628E
0x18001621c  mov     eax, [rbx]
0x18001621e  dec     eax
0x180016220  mov     [rbx], eax
0x180016222  mov     eax, [rbx]
0x180016224  test    eax, eax
0x180016226  jnz     short loc_18001628E
0x180016228  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001622d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180016232  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x180016236  cmp     byte ptr [rdx+38h], 0
0x18001623a  jz      short loc_180016246
0x18001623c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180016241  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180016246  cmp     byte ptr [rbx+0A0h], 0
0x18001624d  jz      short loc_18001625D
0x18001624f  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180016253  lea     rcx, [rsp+0E8h+var_88]; this
0x180016258  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001625d  cmp     byte ptr [rbx+0E0h], 0
0x180016264  jz      short loc_18001627A
0x180016266  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18001626d  lea     rcx, [rsp+0E8h+var_48]; this
0x180016275  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001627a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001627f  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180016284  lea     rcx, [rsp+0E8h+var_C8]; this
0x180016289  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001628e  lea     r11, [rsp+0E8h+var_8]
0x180016296  mov     rbx, [r11+10h]
0x18001629a  mov     rsi, [r11+18h]
0x18001629e  mov     rsp, r11
0x1800162a1  pop     rdi
0x1800162a2  retn
0x1800162a3  mov     rcx, [rsp+0E8h]; this
0x1800162ab  mov     edx, 0A15h; void *
0x1800162b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800162b6  mov     rcx, [rsp+0E8h]; this
0x1800162be  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800162c5  mov     edx, 0E01h; void *
0x1800162ca  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800162d0  mov     rcx, [rsp+0E8h]; this
0x1800162d8  mov     edx, 0A15h; void *
0x1800162dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
