# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000a370`
- end: `0x18000a509`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `409`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180007a20`
- `0x18000be70`

## callees

- `0x180004560`
- `0x180004604`
- `0x1800066ac`
- `0x180007768`
- `0x180007830`
- `0x180007c4c`
- `0x180009730`
- `0x18000a370`
- `0x18000aa98`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a409`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a409`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a3b8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a3b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a3f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a43c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a3f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a43c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a417`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a417`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a425`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a425`

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
0x18000a370  mov     [rsp+arg_0], rbx
0x18000a375  mov     [rsp+arg_8], rsi
0x18000a37a  push    rdi
0x18000a37b  sub     rsp, 0E0h
0x18000a382  mov     rbx, rcx
0x18000a385  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a38c  jnz     loc_18000A44C
0x18000a392  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a399  test    rax, rax
0x18000a39c  jz      short loc_18000A3AB
0x18000a39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a3  test    al, al
0x18000a3a5  jnz     loc_18000A44C
0x18000a3ab  mov     rdi, [rbx+8]
0x18000a3af  xor     r8d, r8d; bAlertable
0x18000a3b2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a3b5  mov     rcx, rdi; hHandle
0x18000a3b8  call    cs:__imp_WaitForSingleObjectEx
0x18000a3be  cmp     eax, 102h
0x18000a3c3  jz      short loc_18000A3D2
0x18000a3c5  test    eax, 0FFFFFF7Fh
0x18000a3ca  jnz     loc_18000A4E8
0x18000a3d0  jmp     short loc_18000A3D4
0x18000a3d2  xor     edi, edi
0x18000a3d4  mov     eax, [rbx]
0x18000a3d6  dec     eax
0x18000a3d8  mov     [rbx], eax
0x18000a3da  mov     eax, [rbx]
0x18000a3dc  test    eax, eax
0x18000a3de  jnz     short loc_18000A430
0x18000a3e0  lea     rcx, [rbx+10h]; this
0x18000a3e4  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000a3e9  test    rdi, rdi
0x18000a3ec  jz      short loc_18000A40F
0x18000a3ee  call    cs:__imp_GetLastError
0x18000a3f4  mov     esi, eax
0x18000a3f6  mov     rcx, rdi; hMutex
0x18000a3f9  call    cs:__imp_ReleaseMutex
0x18000a3ff  test    eax, eax
0x18000a401  jz      loc_18000A4D5
0x18000a407  mov     ecx, esi; dwErrCode
0x18000a409  call    cs:__imp_SetLastError
0x18000a40f  mov     rcx, rbx
0x18000a412  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x18000a417  call    cs:__imp_GetProcessHeap
0x18000a41d  mov     rcx, rax; hHeap
0x18000a420  mov     r8, rbx; lpMem
0x18000a423  xor     edx, edx; dwFlags
0x18000a425  call    cs:__imp_HeapFree
0x18000a42b  jmp     loc_18000A4C0
0x18000a430  test    rdi, rdi
0x18000a433  jz      loc_18000A4C0
0x18000a439  mov     rcx, rdi; hMutex
0x18000a43c  call    cs:__imp_ReleaseMutex
0x18000a442  test    eax, eax
0x18000a444  jz      loc_18000A4F6
0x18000a44a  jmp     short loc_18000A4C0
0x18000a44c  mov     eax, [rbx]
0x18000a44e  dec     eax
0x18000a450  mov     [rbx], eax
0x18000a452  mov     eax, [rbx]
0x18000a454  test    eax, eax
0x18000a456  jnz     short loc_18000A4C0
0x18000a458  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a45d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a462  nop
0x18000a463  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000a467  cmp     byte ptr [rdx+38h], 0
0x18000a46b  jz      short loc_18000A477
0x18000a46d  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a472  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a477  cmp     byte ptr [rbx+0A0h], 0
0x18000a47e  jz      short loc_18000A48E
0x18000a480  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000a484  lea     rcx, [rsp+0E8h+var_88]; this
0x18000a489  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a48e  cmp     byte ptr [rbx+0E0h], 0
0x18000a495  jz      short loc_18000A4AB
0x18000a497  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000a49e  lea     rcx, [rsp+0E8h+var_48]; this
0x18000a4a6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a4ab  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a4b0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000a4b5  nop
0x18000a4b6  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a4bb  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000a4c0  lea     r11, [rsp+0E8h+var_8]
0x18000a4c8  mov     rbx, [r11+10h]
0x18000a4cc  mov     rsi, [r11+18h]
0x18000a4d0  mov     rsp, r11
0x18000a4d3  pop     rdi
0x18000a4d4  retn
0x18000a4d5  mov     rcx, [rsp+0E8h]; this
0x18000a4dd  mov     edx, 0A15h; void *
0x18000a4e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a4e8  mov     rcx, [rsp+0E8h]; this
0x18000a4f0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a4f6  mov     rcx, [rsp+0E8h]; this
0x18000a4fe  mov     edx, 0A15h; void *
0x18000a503  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
