# wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::~ProcessLocalStorage<wil::details_abi::FeatureStateData>(void)

- ea: `0x180007368`
- end: `0x18000750a`
- name: `??1?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `418`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180005914`
- `0x180009a90`

## callees

- `0x180002e24`
- `0x180002e40`
- `0x1800031dc`
- `0x1800044ec`
- `0x18000531c`
- `0x1800053e4`
- `0x180005880`
- `0x180007368`
- `0x180007bf4`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800073ba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800073ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800073fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000743e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800073fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000743e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007427`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007427`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007419`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007419`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000740b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000740b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073f0`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::~ProcessLocalStorage<wil::details_abi::FeatureStateData>(
        __int64 a1)
{
  char *v1; // rbx
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  DWORD LastError; // esi
  unsigned int v8; // r8d
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  _BYTE v13[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v14[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v15[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v1 = *(char **)(a1 + 8);
  if ( v1 )
  {
    if ( wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
      if ( !--*(_DWORD *)v1 )
      {
        wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v13);
        if ( v1[96] )
          wil::details_abi::RawUsageIndex::Swap(
            (wil::details_abi::RawUsageIndex *)v13,
            (struct wil::details_abi::RawUsageIndex *)(v1 + 40));
        if ( v1[160] )
          wil::details_abi::RawUsageIndex::Swap(
            (wil::details_abi::RawUsageIndex *)v14,
            (struct wil::details_abi::RawUsageIndex *)(v1 + 104));
        if ( v1[224] )
          wil::details_abi::RawUsageIndex::Swap(
            (wil::details_abi::RawUsageIndex *)v15,
            (struct wil::details_abi::RawUsageIndex *)(v1 + 168));
        wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v13);
        wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v13);
      }
    }
    else
    {
      v2 = (void *)*((_QWORD *)v1 + 1);
      v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
      if ( v3 == 258 )
      {
        v2 = 0;
      }
      else if ( (v3 & 0xFFFFFF7F) != 0 )
      {
        wil::details::in1diag3::FailFast_Unexpected(retaddr, v4, v5, v6);
      }
      if ( --*(_DWORD *)v1 )
      {
        if ( v2 && !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v11, v12);
      }
      else
      {
        wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(v1 + 16));
        if ( v2 )
        {
          LastError = GetLastError();
          if ( !ReleaseMutex(v2) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v8, v9);
          SetLastError(LastError);
        }
        wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(v1);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v1);
      }
    }
  }
}

```

## disassembly

```asm
0x180007368  mov     [rsp+arg_0], rbx
0x18000736d  mov     [rsp+arg_8], rsi
0x180007372  push    rdi
0x180007373  sub     rsp, 0E0h
0x18000737a  mov     rbx, [rcx+8]
0x18000737e  test    rbx, rbx
0x180007381  jz      loc_1800074C1
0x180007387  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000738e  jnz     loc_18000744E
0x180007394  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000739b  test    rax, rax
0x18000739e  jz      short loc_1800073AD
0x1800073a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a5  test    al, al
0x1800073a7  jnz     loc_18000744E
0x1800073ad  mov     rdi, [rbx+8]
0x1800073b1  xor     r8d, r8d; bAlertable
0x1800073b4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800073b7  mov     rcx, rdi; hHandle
0x1800073ba  call    cs:__imp_WaitForSingleObjectEx
0x1800073c0  cmp     eax, 102h
0x1800073c5  jz      short loc_1800073D4
0x1800073c7  test    eax, 0FFFFFF7Fh
0x1800073cc  jnz     loc_1800074E9
0x1800073d2  jmp     short loc_1800073D6
0x1800073d4  xor     edi, edi
0x1800073d6  mov     eax, [rbx]
0x1800073d8  dec     eax
0x1800073da  mov     [rbx], eax
0x1800073dc  mov     eax, [rbx]
0x1800073de  test    eax, eax
0x1800073e0  jnz     short loc_180007432
0x1800073e2  lea     rcx, [rbx+10h]; this
0x1800073e6  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x1800073eb  test    rdi, rdi
0x1800073ee  jz      short loc_180007411
0x1800073f0  call    cs:__imp_GetLastError
0x1800073f6  mov     esi, eax
0x1800073f8  mov     rcx, rdi; hMutex
0x1800073fb  call    cs:__imp_ReleaseMutex
0x180007401  test    eax, eax
0x180007403  jz      loc_1800074D6
0x180007409  mov     ecx, esi; dwErrCode
0x18000740b  call    cs:__imp_SetLastError
0x180007411  mov     rcx, rbx
0x180007414  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x180007419  call    cs:__imp_GetProcessHeap
0x18000741f  mov     rcx, rax; hHeap
0x180007422  mov     r8, rbx; lpMem
0x180007425  xor     edx, edx; dwFlags
0x180007427  call    cs:__imp_HeapFree
0x18000742d  jmp     loc_1800074C1
0x180007432  test    rdi, rdi
0x180007435  jz      loc_1800074C1
0x18000743b  mov     rcx, rdi; hMutex
0x18000743e  call    cs:__imp_ReleaseMutex
0x180007444  test    eax, eax
0x180007446  jz      loc_1800074F7
0x18000744c  jmp     short loc_1800074C1
0x18000744e  mov     eax, [rbx]
0x180007450  dec     eax
0x180007452  mov     [rbx], eax
0x180007454  mov     eax, [rbx]
0x180007456  test    eax, eax
0x180007458  jnz     short loc_1800074C1
0x18000745a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000745f  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007464  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x180007468  cmp     byte ptr [rdx+38h], 0
0x18000746c  jz      short loc_180007478
0x18000746e  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007473  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180007478  cmp     byte ptr [rbx+0A0h], 0
0x18000747f  jz      short loc_18000748F
0x180007481  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180007485  lea     rcx, [rsp+0E8h+var_88]; this
0x18000748a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000748f  cmp     byte ptr [rbx+0E0h], 0
0x180007496  jz      short loc_1800074AC
0x180007498  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000749f  lea     rcx, [rsp+0E8h+var_48]; this
0x1800074a7  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800074ac  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800074b1  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800074b6  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800074bb  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800074c0  nop
0x1800074c1  lea     r11, [rsp+0E8h+var_8]
0x1800074c9  mov     rbx, [r11+10h]
0x1800074cd  mov     rsi, [r11+18h]
0x1800074d1  mov     rsp, r11
0x1800074d4  pop     rdi
0x1800074d5  retn
0x1800074d6  mov     rcx, [rsp+0E8h]; this
0x1800074de  mov     edx, 0A15h; void *
0x1800074e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800074e9  mov     rcx, [rsp+0E8h]; this
0x1800074f1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800074f7  mov     rcx, [rsp+0E8h]; this
0x1800074ff  mov     edx, 0A15h; void *
0x180007504  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
