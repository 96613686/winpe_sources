# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180009300`
- end: `0x180009499`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `409`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180005b54`
- `0x18000bef0`

## callees

- `0x1800057d0`
- `0x180005964`
- `0x180005ef0`
- `0x180006a60`
- `0x180006c94`
- `0x1800084f0`
- `0x180009300`
- `0x18000a228`
- `0x18000ab0c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000937e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000937e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009399`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009399`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009348`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009348`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009389`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800093cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009389`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800093cc`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  DWORD LastError; // esi
  __int64 v8; // r8
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // r8
  const struct wil::details_abi::RawUsageIndex *v14; // r9
  struct wil::details_abi::RawUsageIndex *v15; // rdx
  _BYTE v16[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v17[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v18[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v16);
      v15 = (struct wil::details_abi::RawUsageIndex *)(lpMem + 40);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap((wil::details_abi::RawUsageIndex *)v16, v15);
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v17,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v18,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v16, (__int64)v15, v13, v14);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v16);
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v11, v12);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v8, v9);
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
0x180009300  mov     [rsp+arg_0], rbx
0x180009305  mov     [rsp+arg_8], rsi
0x18000930a  push    rdi
0x18000930b  sub     rsp, 0E0h
0x180009312  mov     rbx, rcx
0x180009315  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000931c  jnz     loc_1800093DC
0x180009322  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009329  test    rax, rax
0x18000932c  jz      short loc_18000933B
0x18000932e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009333  test    al, al
0x180009335  jnz     loc_1800093DC
0x18000933b  mov     rdi, [rbx+8]
0x18000933f  xor     r8d, r8d; bAlertable
0x180009342  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009345  mov     rcx, rdi; hHandle
0x180009348  call    cs:__imp_WaitForSingleObjectEx
0x18000934e  cmp     eax, 102h
0x180009353  jz      short loc_180009362
0x180009355  test    eax, 0FFFFFF7Fh
0x18000935a  jnz     loc_180009478
0x180009360  jmp     short loc_180009364
0x180009362  xor     edi, edi
0x180009364  mov     eax, [rbx]
0x180009366  dec     eax
0x180009368  mov     [rbx], eax
0x18000936a  mov     eax, [rbx]
0x18000936c  test    eax, eax
0x18000936e  jnz     short loc_1800093C0
0x180009370  lea     rcx, [rbx+10h]; this
0x180009374  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180009379  test    rdi, rdi
0x18000937c  jz      short loc_18000939F
0x18000937e  call    cs:__imp_GetLastError
0x180009384  mov     esi, eax
0x180009386  mov     rcx, rdi; hMutex
0x180009389  call    cs:__imp_ReleaseMutex
0x18000938f  test    eax, eax
0x180009391  jz      loc_180009465
0x180009397  mov     ecx, esi; dwErrCode
0x180009399  call    cs:__imp_SetLastError
0x18000939f  mov     rcx, rbx
0x1800093a2  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x1800093a7  call    cs:__imp_GetProcessHeap
0x1800093ad  mov     rcx, rax; hHeap
0x1800093b0  mov     r8, rbx; lpMem
0x1800093b3  xor     edx, edx; dwFlags
0x1800093b5  call    cs:__imp_HeapFree
0x1800093bb  jmp     loc_180009450
0x1800093c0  test    rdi, rdi
0x1800093c3  jz      loc_180009450
0x1800093c9  mov     rcx, rdi; hMutex
0x1800093cc  call    cs:__imp_ReleaseMutex
0x1800093d2  test    eax, eax
0x1800093d4  jz      loc_180009486
0x1800093da  jmp     short loc_180009450
0x1800093dc  mov     eax, [rbx]
0x1800093de  dec     eax
0x1800093e0  mov     [rbx], eax
0x1800093e2  mov     eax, [rbx]
0x1800093e4  test    eax, eax
0x1800093e6  jnz     short loc_180009450
0x1800093e8  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800093ed  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800093f2  nop
0x1800093f3  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x1800093f7  cmp     byte ptr [rdx+38h], 0
0x1800093fb  jz      short loc_180009407
0x1800093fd  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009402  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009407  cmp     byte ptr [rbx+0A0h], 0
0x18000940e  jz      short loc_18000941E
0x180009410  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180009414  lea     rcx, [rsp+0E8h+var_88]; this
0x180009419  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000941e  cmp     byte ptr [rbx+0E0h], 0
0x180009425  jz      short loc_18000943B
0x180009427  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000942e  lea     rcx, [rsp+0E8h+var_48]; this
0x180009436  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000943b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009440  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180009445  nop
0x180009446  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000944b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180009450  lea     r11, [rsp+0E8h+var_8]
0x180009458  mov     rbx, [r11+10h]
0x18000945c  mov     rsi, [r11+18h]
0x180009460  mov     rsp, r11
0x180009463  pop     rdi
0x180009464  retn
0x180009465  mov     rcx, [rsp+0E8h]; this
0x18000946d  mov     edx, 0A15h; void *
0x180009472  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009478  mov     rcx, [rsp+0E8h]; this
0x180009480  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009486  mov     rcx, [rsp+0E8h]; this
0x18000948e  mov     edx, 0A15h; void *
0x180009493  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
