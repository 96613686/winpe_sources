# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180008b30`
- end: `0x180008cc7`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800055bc`
- `0x18000a600`

## callees

- `0x18000525c`
- `0x1800053f0`
- `0x180005834`
- `0x180006310`
- `0x180006544`
- `0x180007d7c`
- `0x180008b30`
- `0x180009400`
- `0x180009cac`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008bb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008bfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008bb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008bfc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008b78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008b78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008be5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008be5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008bd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008bd7`

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
0x180008b30  mov     [rsp+arg_0], rbx
0x180008b35  mov     [rsp+arg_8], rsi
0x180008b3a  push    rdi
0x180008b3b  sub     rsp, 0E0h
0x180008b42  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008b49  mov     rbx, rcx
0x180008b4c  jnz     loc_180008C0C
0x180008b52  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008b59  test    rax, rax
0x180008b5c  jz      short loc_180008B6B
0x180008b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b63  test    al, al
0x180008b65  jnz     loc_180008C0C
0x180008b6b  mov     rdi, [rbx+8]
0x180008b6f  xor     r8d, r8d; bAlertable
0x180008b72  mov     rcx, rdi; hHandle
0x180008b75  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008b78  call    cs:__imp_WaitForSingleObjectEx
0x180008b7e  cmp     eax, 102h
0x180008b83  jz      short loc_180008B92
0x180008b85  test    eax, 0FFFFFF7Fh
0x180008b8a  jnz     loc_180008CA6
0x180008b90  jmp     short loc_180008B94
0x180008b92  xor     edi, edi
0x180008b94  mov     eax, [rbx]
0x180008b96  dec     eax
0x180008b98  mov     [rbx], eax
0x180008b9a  mov     eax, [rbx]
0x180008b9c  test    eax, eax
0x180008b9e  jnz     short loc_180008BF0
0x180008ba0  lea     rcx, [rbx+10h]; this
0x180008ba4  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180008ba9  test    rdi, rdi
0x180008bac  jz      short loc_180008BCF
0x180008bae  call    cs:__imp_GetLastError
0x180008bb4  mov     rcx, rdi; hMutex
0x180008bb7  mov     esi, eax
0x180008bb9  call    cs:__imp_ReleaseMutex
0x180008bbf  test    eax, eax
0x180008bc1  jz      loc_180008C93
0x180008bc7  mov     ecx, esi; dwErrCode
0x180008bc9  call    cs:__imp_SetLastError
0x180008bcf  mov     rcx, rbx
0x180008bd2  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x180008bd7  call    cs:__imp_GetProcessHeap
0x180008bdd  mov     r8, rbx; lpMem
0x180008be0  xor     edx, edx; dwFlags
0x180008be2  mov     rcx, rax; hHeap
0x180008be5  call    cs:__imp_HeapFree
0x180008beb  jmp     loc_180008C7E
0x180008bf0  test    rdi, rdi
0x180008bf3  jz      loc_180008C7E
0x180008bf9  mov     rcx, rdi; hMutex
0x180008bfc  call    cs:__imp_ReleaseMutex
0x180008c02  test    eax, eax
0x180008c04  jz      loc_180008CB4
0x180008c0a  jmp     short loc_180008C7E
0x180008c0c  mov     eax, [rbx]
0x180008c0e  dec     eax
0x180008c10  mov     [rbx], eax
0x180008c12  mov     eax, [rbx]
0x180008c14  test    eax, eax
0x180008c16  jnz     short loc_180008C7E
0x180008c18  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008c1d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008c22  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x180008c26  cmp     byte ptr [rdx+38h], 0
0x180008c2a  jz      short loc_180008C36
0x180008c2c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008c31  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008c36  cmp     byte ptr [rbx+0A0h], 0
0x180008c3d  jz      short loc_180008C4D
0x180008c3f  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180008c43  lea     rcx, [rsp+0E8h+var_88]; this
0x180008c48  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008c4d  cmp     byte ptr [rbx+0E0h], 0
0x180008c54  jz      short loc_180008C6A
0x180008c56  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x180008c5d  lea     rcx, [rsp+0E8h+var_48]; this
0x180008c65  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008c6a  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008c6f  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180008c74  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008c79  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008c7e  lea     r11, [rsp+0E8h+var_8]
0x180008c86  mov     rbx, [r11+10h]
0x180008c8a  mov     rsi, [r11+18h]
0x180008c8e  mov     rsp, r11
0x180008c91  pop     rdi
0x180008c92  retn
0x180008c93  mov     rcx, [rsp+0E8h]; this
0x180008c9b  mov     edx, 0A15h; void *
0x180008ca0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008ca6  mov     rcx, [rsp+0E8h]; this
0x180008cae  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008cb4  mov     rcx, [rsp+0E8h]; this
0x180008cbc  mov     edx, 0A15h; void *
0x180008cc1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
