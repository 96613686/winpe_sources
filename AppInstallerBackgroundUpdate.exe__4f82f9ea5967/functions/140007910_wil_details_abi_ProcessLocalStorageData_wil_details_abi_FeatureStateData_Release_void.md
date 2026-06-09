# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x140007910`
- end: `0x140007aa9`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `409`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140005cc0`
- `0x140008ba0`

## callees

- `0x140003330`
- `0x1400033d4`
- `0x1400055ec`
- `0x140005a08`
- `0x140005ad0`
- `0x140005eec`
- `0x140006c84`
- `0x140007910`
- `0x140007d88`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140007958`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140007958`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007999`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400079dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007999`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400079dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400079b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400079b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400079c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400079c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000798e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000798e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400079a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400079a9`

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
0x140007910  mov     [rsp+arg_0], rbx
0x140007915  mov     [rsp+arg_8], rsi
0x14000791a  push    rdi
0x14000791b  sub     rsp, 0E0h
0x140007922  mov     rbx, rcx
0x140007925  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000792c  jnz     loc_1400079EC
0x140007932  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140007939  test    rax, rax
0x14000793c  jz      short loc_14000794B
0x14000793e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007943  test    al, al
0x140007945  jnz     loc_1400079EC
0x14000794b  mov     rdi, [rbx+8]
0x14000794f  xor     r8d, r8d; bAlertable
0x140007952  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140007955  mov     rcx, rdi; hHandle
0x140007958  call    cs:__imp_WaitForSingleObjectEx
0x14000795e  cmp     eax, 102h
0x140007963  jz      short loc_140007972
0x140007965  test    eax, 0FFFFFF7Fh
0x14000796a  jnz     loc_140007A88
0x140007970  jmp     short loc_140007974
0x140007972  xor     edi, edi
0x140007974  mov     eax, [rbx]
0x140007976  dec     eax
0x140007978  mov     [rbx], eax
0x14000797a  mov     eax, [rbx]
0x14000797c  test    eax, eax
0x14000797e  jnz     short loc_1400079D0
0x140007980  lea     rcx, [rbx+10h]; this
0x140007984  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x140007989  test    rdi, rdi
0x14000798c  jz      short loc_1400079AF
0x14000798e  call    cs:__imp_GetLastError
0x140007994  mov     esi, eax
0x140007996  mov     rcx, rdi; hMutex
0x140007999  call    cs:__imp_ReleaseMutex
0x14000799f  test    eax, eax
0x1400079a1  jz      loc_140007A75
0x1400079a7  mov     ecx, esi; dwErrCode
0x1400079a9  call    cs:__imp_SetLastError
0x1400079af  mov     rcx, rbx
0x1400079b2  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x1400079b7  call    cs:__imp_GetProcessHeap
0x1400079bd  mov     rcx, rax; hHeap
0x1400079c0  mov     r8, rbx; lpMem
0x1400079c3  xor     edx, edx; dwFlags
0x1400079c5  call    cs:__imp_HeapFree
0x1400079cb  jmp     loc_140007A60
0x1400079d0  test    rdi, rdi
0x1400079d3  jz      loc_140007A60
0x1400079d9  mov     rcx, rdi; hMutex
0x1400079dc  call    cs:__imp_ReleaseMutex
0x1400079e2  test    eax, eax
0x1400079e4  jz      loc_140007A96
0x1400079ea  jmp     short loc_140007A60
0x1400079ec  mov     eax, [rbx]
0x1400079ee  dec     eax
0x1400079f0  mov     [rbx], eax
0x1400079f2  mov     eax, [rbx]
0x1400079f4  test    eax, eax
0x1400079f6  jnz     short loc_140007A60
0x1400079f8  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400079fd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140007a02  nop
0x140007a03  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x140007a07  cmp     byte ptr [rdx+38h], 0
0x140007a0b  jz      short loc_140007A17
0x140007a0d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007a12  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140007a17  cmp     byte ptr [rbx+0A0h], 0
0x140007a1e  jz      short loc_140007A2E
0x140007a20  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x140007a24  lea     rcx, [rsp+0E8h+var_88]; this
0x140007a29  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140007a2e  cmp     byte ptr [rbx+0E0h], 0
0x140007a35  jz      short loc_140007A4B
0x140007a37  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x140007a3e  lea     rcx, [rsp+0E8h+var_48]; this
0x140007a46  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140007a4b  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007a50  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140007a55  nop
0x140007a56  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007a5b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140007a60  lea     r11, [rsp+0E8h+var_8]
0x140007a68  mov     rbx, [r11+10h]
0x140007a6c  mov     rsi, [r11+18h]
0x140007a70  mov     rsp, r11
0x140007a73  pop     rdi
0x140007a74  retn
0x140007a75  mov     rcx, [rsp+0E8h]; this
0x140007a7d  mov     edx, 0A15h; void *
0x140007a82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007a88  mov     rcx, [rsp+0E8h]; this
0x140007a90  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140007a96  mov     rcx, [rsp+0E8h]; this
0x140007a9e  mov     edx, 0A15h; void *
0x140007aa3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
