# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180006e30`
- end: `0x180006fc9`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `409`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180003648`
- `0x18000e7f0`

## callees

- `0x180003274`
- `0x180003440`
- `0x1800039e4`
- `0x180004590`
- `0x1800047c4`
- `0x180006020`
- `0x180006e30`
- `0x180007d58`
- `0x18000863c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006e78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006e78`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006eb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006efc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006eb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006efc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ed7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ed7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ee5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ee5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ec9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ec9`

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
0x180006e30  mov     [rsp+arg_0], rbx
0x180006e35  mov     [rsp+arg_8], rsi
0x180006e3a  push    rdi
0x180006e3b  sub     rsp, 0E0h
0x180006e42  mov     rbx, rcx
0x180006e45  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006e4c  jnz     loc_180006F0C
0x180006e52  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006e59  test    rax, rax
0x180006e5c  jz      short loc_180006E6B
0x180006e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e63  test    al, al
0x180006e65  jnz     loc_180006F0C
0x180006e6b  mov     rdi, [rbx+8]
0x180006e6f  xor     r8d, r8d; bAlertable
0x180006e72  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006e75  mov     rcx, rdi; hHandle
0x180006e78  call    cs:__imp_WaitForSingleObjectEx
0x180006e7e  cmp     eax, 102h
0x180006e83  jz      short loc_180006E92
0x180006e85  test    eax, 0FFFFFF7Fh
0x180006e8a  jnz     loc_180006FA8
0x180006e90  jmp     short loc_180006E94
0x180006e92  xor     edi, edi
0x180006e94  mov     eax, [rbx]
0x180006e96  dec     eax
0x180006e98  mov     [rbx], eax
0x180006e9a  mov     eax, [rbx]
0x180006e9c  test    eax, eax
0x180006e9e  jnz     short loc_180006EF0
0x180006ea0  lea     rcx, [rbx+10h]; this
0x180006ea4  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180006ea9  test    rdi, rdi
0x180006eac  jz      short loc_180006ECF
0x180006eae  call    cs:__imp_GetLastError
0x180006eb4  mov     esi, eax
0x180006eb6  mov     rcx, rdi; hMutex
0x180006eb9  call    cs:__imp_ReleaseMutex
0x180006ebf  test    eax, eax
0x180006ec1  jz      loc_180006F95
0x180006ec7  mov     ecx, esi; dwErrCode
0x180006ec9  call    cs:__imp_SetLastError
0x180006ecf  mov     rcx, rbx
0x180006ed2  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x180006ed7  call    cs:__imp_GetProcessHeap
0x180006edd  mov     rcx, rax; hHeap
0x180006ee0  mov     r8, rbx; lpMem
0x180006ee3  xor     edx, edx; dwFlags
0x180006ee5  call    cs:__imp_HeapFree
0x180006eeb  jmp     loc_180006F80
0x180006ef0  test    rdi, rdi
0x180006ef3  jz      loc_180006F80
0x180006ef9  mov     rcx, rdi; hMutex
0x180006efc  call    cs:__imp_ReleaseMutex
0x180006f02  test    eax, eax
0x180006f04  jz      loc_180006FB6
0x180006f0a  jmp     short loc_180006F80
0x180006f0c  mov     eax, [rbx]
0x180006f0e  dec     eax
0x180006f10  mov     [rbx], eax
0x180006f12  mov     eax, [rbx]
0x180006f14  test    eax, eax
0x180006f16  jnz     short loc_180006F80
0x180006f18  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006f1d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006f22  nop
0x180006f23  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x180006f27  cmp     byte ptr [rdx+38h], 0
0x180006f2b  jz      short loc_180006F37
0x180006f2d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006f32  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006f37  cmp     byte ptr [rbx+0A0h], 0
0x180006f3e  jz      short loc_180006F4E
0x180006f40  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180006f44  lea     rcx, [rsp+0E8h+var_88]; this
0x180006f49  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006f4e  cmp     byte ptr [rbx+0E0h], 0
0x180006f55  jz      short loc_180006F6B
0x180006f57  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x180006f5e  lea     rcx, [rsp+0E8h+var_48]; this
0x180006f66  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006f6b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006f70  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180006f75  nop
0x180006f76  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006f7b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180006f80  lea     r11, [rsp+0E8h+var_8]
0x180006f88  mov     rbx, [r11+10h]
0x180006f8c  mov     rsi, [r11+18h]
0x180006f90  mov     rsp, r11
0x180006f93  pop     rdi
0x180006f94  retn
0x180006f95  mov     rcx, [rsp+0E8h]; this
0x180006f9d  mov     edx, 0A15h; void *
0x180006fa2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fa8  mov     rcx, [rsp+0E8h]; this
0x180006fb0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006fb6  mov     rcx, [rsp+0E8h]; this
0x180006fbe  mov     edx, 0A15h; void *
0x180006fc3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
