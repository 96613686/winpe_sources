# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x140010e70`
- end: `0x140011007`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140005fe4`
- `0x1400137c0`

## callees

- `0x1400036a0`
- `0x1400037f4`
- `0x1400054fc`
- `0x140005ba8`
- `0x140005ca0`
- `0x14000627c`
- `0x14001004c`
- `0x140010e70`
- `0x14001175c`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140010eb8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140010eb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010ef9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010f3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010ef9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010f3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010f17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010f17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010f25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010f25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010f09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010eee`

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
0x140010e70  mov     [rsp+arg_0], rbx
0x140010e75  mov     [rsp+arg_8], rsi
0x140010e7a  push    rdi
0x140010e7b  sub     rsp, 0E0h
0x140010e82  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140010e89  mov     rbx, rcx
0x140010e8c  jnz     loc_140010F4C
0x140010e92  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140010e99  test    rax, rax
0x140010e9c  jz      short loc_140010EAB
0x140010e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ea3  test    al, al
0x140010ea5  jnz     loc_140010F4C
0x140010eab  mov     rdi, [rbx+8]
0x140010eaf  xor     r8d, r8d; bAlertable
0x140010eb2  mov     rcx, rdi; hHandle
0x140010eb5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140010eb8  call    cs:__imp_WaitForSingleObjectEx
0x140010ebe  cmp     eax, 102h
0x140010ec3  jz      short loc_140010ED2
0x140010ec5  test    eax, 0FFFFFF7Fh
0x140010eca  jnz     loc_140010FE6
0x140010ed0  jmp     short loc_140010ED4
0x140010ed2  xor     edi, edi
0x140010ed4  mov     eax, [rbx]
0x140010ed6  dec     eax
0x140010ed8  mov     [rbx], eax
0x140010eda  mov     eax, [rbx]
0x140010edc  test    eax, eax
0x140010ede  jnz     short loc_140010F30
0x140010ee0  lea     rcx, [rbx+10h]; this
0x140010ee4  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x140010ee9  test    rdi, rdi
0x140010eec  jz      short loc_140010F0F
0x140010eee  call    cs:__imp_GetLastError
0x140010ef4  mov     rcx, rdi; hMutex
0x140010ef7  mov     esi, eax
0x140010ef9  call    cs:__imp_ReleaseMutex
0x140010eff  test    eax, eax
0x140010f01  jz      loc_140010FD3
0x140010f07  mov     ecx, esi; dwErrCode
0x140010f09  call    cs:__imp_SetLastError
0x140010f0f  mov     rcx, rbx
0x140010f12  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x140010f17  call    cs:__imp_GetProcessHeap
0x140010f1d  mov     r8, rbx; lpMem
0x140010f20  xor     edx, edx; dwFlags
0x140010f22  mov     rcx, rax; hHeap
0x140010f25  call    cs:__imp_HeapFree
0x140010f2b  jmp     loc_140010FBE
0x140010f30  test    rdi, rdi
0x140010f33  jz      loc_140010FBE
0x140010f39  mov     rcx, rdi; hMutex
0x140010f3c  call    cs:__imp_ReleaseMutex
0x140010f42  test    eax, eax
0x140010f44  jz      loc_140010FF4
0x140010f4a  jmp     short loc_140010FBE
0x140010f4c  mov     eax, [rbx]
0x140010f4e  dec     eax
0x140010f50  mov     [rbx], eax
0x140010f52  mov     eax, [rbx]
0x140010f54  test    eax, eax
0x140010f56  jnz     short loc_140010FBE
0x140010f58  lea     rcx, [rsp+0E8h+var_C8]; this
0x140010f5d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140010f62  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x140010f66  cmp     byte ptr [rdx+38h], 0
0x140010f6a  jz      short loc_140010F76
0x140010f6c  lea     rcx, [rsp+0E8h+var_C8]; this
0x140010f71  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140010f76  cmp     byte ptr [rbx+0A0h], 0
0x140010f7d  jz      short loc_140010F8D
0x140010f7f  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x140010f83  lea     rcx, [rsp+0E8h+var_88]; this
0x140010f88  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140010f8d  cmp     byte ptr [rbx+0E0h], 0
0x140010f94  jz      short loc_140010FAA
0x140010f96  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x140010f9d  lea     rcx, [rsp+0E8h+var_48]; this
0x140010fa5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140010faa  lea     rcx, [rsp+0E8h+var_C8]; this
0x140010faf  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140010fb4  lea     rcx, [rsp+0E8h+var_C8]; this
0x140010fb9  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140010fbe  lea     r11, [rsp+0E8h+var_8]
0x140010fc6  mov     rbx, [r11+10h]
0x140010fca  mov     rsi, [r11+18h]
0x140010fce  mov     rsp, r11
0x140010fd1  pop     rdi
0x140010fd2  retn
0x140010fd3  mov     rcx, [rsp+0E8h]; this
0x140010fdb  mov     edx, 0A15h; void *
0x140010fe0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140010fe6  mov     rcx, [rsp+0E8h]; this
0x140010fee  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140010ff4  mov     rcx, [rsp+0E8h]; this
0x140010ffc  mov     edx, 0A15h; void *
0x140011001  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
