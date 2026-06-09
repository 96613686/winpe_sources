# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180006814`
- end: `0x1800069ab`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180002e6c`
- `0x18000c730`

## callees

- `0x1800029c0`
- `0x180002b54`
- `0x1800030e4`
- `0x180003bc0`
- `0x180003eb8`
- `0x180005878`
- `0x180006814`
- `0x1800072e0`
- `0x180007c5c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000685c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000685c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000689d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800068e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000689d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800068e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006892`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068ad`

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
  unsigned int v8; // r8d
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  _BYTE v13[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v14[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v15[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v13);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v13,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v14,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v15,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v13);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v13);
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
0x180006814  mov     [rsp+arg_0], rbx
0x180006819  mov     [rsp+arg_8], rsi
0x18000681e  push    rdi
0x18000681f  sub     rsp, 0E0h
0x180006826  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000682d  mov     rbx, rcx
0x180006830  jnz     loc_1800068F0
0x180006836  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000683d  test    rax, rax
0x180006840  jz      short loc_18000684F
0x180006842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006847  test    al, al
0x180006849  jnz     loc_1800068F0
0x18000684f  mov     rdi, [rbx+8]
0x180006853  xor     r8d, r8d; bAlertable
0x180006856  mov     rcx, rdi; hHandle
0x180006859  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000685c  call    cs:__imp_WaitForSingleObjectEx
0x180006862  cmp     eax, 102h
0x180006867  jz      short loc_180006876
0x180006869  test    eax, 0FFFFFF7Fh
0x18000686e  jnz     loc_18000698A
0x180006874  jmp     short loc_180006878
0x180006876  xor     edi, edi
0x180006878  mov     eax, [rbx]
0x18000687a  dec     eax
0x18000687c  mov     [rbx], eax
0x18000687e  mov     eax, [rbx]
0x180006880  test    eax, eax
0x180006882  jnz     short loc_1800068D4
0x180006884  lea     rcx, [rbx+10h]; this
0x180006888  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000688d  test    rdi, rdi
0x180006890  jz      short loc_1800068B3
0x180006892  call    cs:__imp_GetLastError
0x180006898  mov     rcx, rdi; hMutex
0x18000689b  mov     esi, eax
0x18000689d  call    cs:__imp_ReleaseMutex
0x1800068a3  test    eax, eax
0x1800068a5  jz      loc_180006977
0x1800068ab  mov     ecx, esi; dwErrCode
0x1800068ad  call    cs:__imp_SetLastError
0x1800068b3  mov     rcx, rbx
0x1800068b6  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x1800068bb  call    cs:__imp_GetProcessHeap
0x1800068c1  mov     r8, rbx; lpMem
0x1800068c4  xor     edx, edx; dwFlags
0x1800068c6  mov     rcx, rax; hHeap
0x1800068c9  call    cs:__imp_HeapFree
0x1800068cf  jmp     loc_180006962
0x1800068d4  test    rdi, rdi
0x1800068d7  jz      loc_180006962
0x1800068dd  mov     rcx, rdi; hMutex
0x1800068e0  call    cs:__imp_ReleaseMutex
0x1800068e6  test    eax, eax
0x1800068e8  jz      loc_180006998
0x1800068ee  jmp     short loc_180006962
0x1800068f0  mov     eax, [rbx]
0x1800068f2  dec     eax
0x1800068f4  mov     [rbx], eax
0x1800068f6  mov     eax, [rbx]
0x1800068f8  test    eax, eax
0x1800068fa  jnz     short loc_180006962
0x1800068fc  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006901  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006906  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000690a  cmp     byte ptr [rdx+38h], 0
0x18000690e  jz      short loc_18000691A
0x180006910  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006915  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000691a  cmp     byte ptr [rbx+0A0h], 0
0x180006921  jz      short loc_180006931
0x180006923  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180006927  lea     rcx, [rsp+0E8h+var_88]; this
0x18000692c  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006931  cmp     byte ptr [rbx+0E0h], 0
0x180006938  jz      short loc_18000694E
0x18000693a  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x180006941  lea     rcx, [rsp+0E8h+var_48]; this
0x180006949  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000694e  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006953  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180006958  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000695d  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180006962  lea     r11, [rsp+0E8h+var_8]
0x18000696a  mov     rbx, [r11+10h]
0x18000696e  mov     rsi, [r11+18h]
0x180006972  mov     rsp, r11
0x180006975  pop     rdi
0x180006976  retn
0x180006977  mov     rcx, [rsp+0E8h]; this
0x18000697f  mov     edx, 0A15h; void *
0x180006984  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000698a  mov     rcx, [rsp+0E8h]; this
0x180006992  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006998  mov     rcx, [rsp+0E8h]; this
0x1800069a0  mov     edx, 0A15h; void *
0x1800069a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
