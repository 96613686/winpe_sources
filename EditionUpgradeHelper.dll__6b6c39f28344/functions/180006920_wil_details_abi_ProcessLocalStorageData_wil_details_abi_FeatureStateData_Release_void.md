# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180006920`
- end: `0x180006ab7`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800032fc`
- `0x180026810`

## callees

- `0x180002f9c`
- `0x180003130`
- `0x180003574`
- `0x180004090`
- `0x1800042c4`
- `0x180005b1c`
- `0x180006920`
- `0x180007280`
- `0x180007b3c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006968`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006968`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800069a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800069ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800069a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800069ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000699e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000699e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069b9`

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
0x180006920  mov     [rsp+arg_0], rbx
0x180006925  mov     [rsp+arg_8], rsi
0x18000692a  push    rdi
0x18000692b  sub     rsp, 0E0h
0x180006932  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006939  mov     rbx, rcx
0x18000693c  jnz     loc_1800069FC
0x180006942  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006949  test    rax, rax
0x18000694c  jz      short loc_18000695B
0x18000694e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006953  test    al, al
0x180006955  jnz     loc_1800069FC
0x18000695b  mov     rdi, [rbx+8]
0x18000695f  xor     r8d, r8d; bAlertable
0x180006962  mov     rcx, rdi; hHandle
0x180006965  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006968  call    cs:__imp_WaitForSingleObjectEx
0x18000696e  cmp     eax, 102h
0x180006973  jz      short loc_180006982
0x180006975  test    eax, 0FFFFFF7Fh
0x18000697a  jnz     loc_180006A96
0x180006980  jmp     short loc_180006984
0x180006982  xor     edi, edi
0x180006984  mov     eax, [rbx]
0x180006986  dec     eax
0x180006988  mov     [rbx], eax
0x18000698a  mov     eax, [rbx]
0x18000698c  test    eax, eax
0x18000698e  jnz     short loc_1800069E0
0x180006990  lea     rcx, [rbx+10h]; this
0x180006994  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180006999  test    rdi, rdi
0x18000699c  jz      short loc_1800069BF
0x18000699e  call    cs:__imp_GetLastError
0x1800069a4  mov     rcx, rdi; hMutex
0x1800069a7  mov     esi, eax
0x1800069a9  call    cs:__imp_ReleaseMutex
0x1800069af  test    eax, eax
0x1800069b1  jz      loc_180006A83
0x1800069b7  mov     ecx, esi; dwErrCode
0x1800069b9  call    cs:__imp_SetLastError
0x1800069bf  mov     rcx, rbx
0x1800069c2  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x1800069c7  call    cs:__imp_GetProcessHeap
0x1800069cd  mov     r8, rbx; lpMem
0x1800069d0  xor     edx, edx; dwFlags
0x1800069d2  mov     rcx, rax; hHeap
0x1800069d5  call    cs:__imp_HeapFree
0x1800069db  jmp     loc_180006A6E
0x1800069e0  test    rdi, rdi
0x1800069e3  jz      loc_180006A6E
0x1800069e9  mov     rcx, rdi; hMutex
0x1800069ec  call    cs:__imp_ReleaseMutex
0x1800069f2  test    eax, eax
0x1800069f4  jz      loc_180006AA4
0x1800069fa  jmp     short loc_180006A6E
0x1800069fc  mov     eax, [rbx]
0x1800069fe  dec     eax
0x180006a00  mov     [rbx], eax
0x180006a02  mov     eax, [rbx]
0x180006a04  test    eax, eax
0x180006a06  jnz     short loc_180006A6E
0x180006a08  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006a0d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006a12  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x180006a16  cmp     byte ptr [rdx+38h], 0
0x180006a1a  jz      short loc_180006A26
0x180006a1c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006a21  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006a26  cmp     byte ptr [rbx+0A0h], 0
0x180006a2d  jz      short loc_180006A3D
0x180006a2f  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180006a33  lea     rcx, [rsp+0E8h+var_88]; this
0x180006a38  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006a3d  cmp     byte ptr [rbx+0E0h], 0
0x180006a44  jz      short loc_180006A5A
0x180006a46  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x180006a4d  lea     rcx, [rsp+0E8h+var_48]; this
0x180006a55  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006a5a  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006a5f  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180006a64  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006a69  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180006a6e  lea     r11, [rsp+0E8h+var_8]
0x180006a76  mov     rbx, [r11+10h]
0x180006a7a  mov     rsi, [r11+18h]
0x180006a7e  mov     rsp, r11
0x180006a81  pop     rdi
0x180006a82  retn
0x180006a83  mov     rcx, [rsp+0E8h]; this
0x180006a8b  mov     edx, 0A15h; void *
0x180006a90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006a96  mov     rcx, [rsp+0E8h]; this
0x180006a9e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006aa4  mov     rcx, [rsp+0E8h]; this
0x180006aac  mov     edx, 0A15h; void *
0x180006ab1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
