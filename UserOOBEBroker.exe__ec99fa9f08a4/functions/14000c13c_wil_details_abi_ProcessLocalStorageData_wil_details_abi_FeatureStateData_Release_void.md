# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x14000c13c`
- end: `0x14000c2d5`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `409`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140008014`
- `0x14000e9f0`

## callees

- `0x140003f70`
- `0x140004014`
- `0x140006244`
- `0x140007af8`
- `0x140007c60`
- `0x140008240`
- `0x14000afbc`
- `0x14000c13c`
- `0x14000cd10`
- `0x14000f010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000c1f1`
- `KERNEL32!HeapFree` at `0x14000c1f1`
- `KERNEL32!SetLastError` at `0x14000c1d5`
- `KERNEL32!SetLastError` at `0x14000c1d5`
- `KERNEL32!ReleaseMutex` at `0x14000c1c5`
- `KERNEL32!ReleaseMutex` at `0x14000c208`
- `KERNEL32!ReleaseMutex` at `0x14000c1c5`
- `KERNEL32!ReleaseMutex` at `0x14000c208`
- `KERNEL32!GetLastError` at `0x14000c1ba`
- `KERNEL32!GetLastError` at `0x14000c1ba`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000c184`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000c184`
- `KERNEL32!GetProcessHeap` at `0x14000c1e3`
- `KERNEL32!GetProcessHeap` at `0x14000c1e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x14000c13c  mov     [rsp+arg_0], rbx
0x14000c141  mov     [rsp+arg_8], rsi
0x14000c146  push    rdi
0x14000c147  sub     rsp, 0E0h
0x14000c14e  mov     rbx, rcx
0x14000c151  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000c158  jnz     loc_14000C218
0x14000c15e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000c165  test    rax, rax
0x14000c168  jz      short loc_14000C177
0x14000c16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c16f  test    al, al
0x14000c171  jnz     loc_14000C218
0x14000c177  mov     rdi, [rbx+8]
0x14000c17b  xor     r8d, r8d; bAlertable
0x14000c17e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000c181  mov     rcx, rdi; hHandle
0x14000c184  call    cs:__imp_WaitForSingleObjectEx
0x14000c18a  cmp     eax, 102h
0x14000c18f  jz      short loc_14000C19E
0x14000c191  test    eax, 0FFFFFF7Fh
0x14000c196  jnz     loc_14000C2B4
0x14000c19c  jmp     short loc_14000C1A0
0x14000c19e  xor     edi, edi
0x14000c1a0  mov     eax, [rbx]
0x14000c1a2  dec     eax
0x14000c1a4  mov     [rbx], eax
0x14000c1a6  mov     eax, [rbx]
0x14000c1a8  test    eax, eax
0x14000c1aa  jnz     short loc_14000C1FC
0x14000c1ac  lea     rcx, [rbx+10h]; this
0x14000c1b0  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x14000c1b5  test    rdi, rdi
0x14000c1b8  jz      short loc_14000C1DB
0x14000c1ba  call    cs:__imp_GetLastError
0x14000c1c0  mov     esi, eax
0x14000c1c2  mov     rcx, rdi; hMutex
0x14000c1c5  call    cs:__imp_ReleaseMutex
0x14000c1cb  test    eax, eax
0x14000c1cd  jz      loc_14000C2A1
0x14000c1d3  mov     ecx, esi; dwErrCode
0x14000c1d5  call    cs:__imp_SetLastError
0x14000c1db  mov     rcx, rbx
0x14000c1de  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x14000c1e3  call    cs:__imp_GetProcessHeap
0x14000c1e9  mov     rcx, rax; hHeap
0x14000c1ec  mov     r8, rbx; lpMem
0x14000c1ef  xor     edx, edx; dwFlags
0x14000c1f1  call    cs:__imp_HeapFree
0x14000c1f7  jmp     loc_14000C28C
0x14000c1fc  test    rdi, rdi
0x14000c1ff  jz      loc_14000C28C
0x14000c205  mov     rcx, rdi; hMutex
0x14000c208  call    cs:__imp_ReleaseMutex
0x14000c20e  test    eax, eax
0x14000c210  jz      loc_14000C2C2
0x14000c216  jmp     short loc_14000C28C
0x14000c218  mov     eax, [rbx]
0x14000c21a  dec     eax
0x14000c21c  mov     [rbx], eax
0x14000c21e  mov     eax, [rbx]
0x14000c220  test    eax, eax
0x14000c222  jnz     short loc_14000C28C
0x14000c224  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c229  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000c22e  nop
0x14000c22f  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x14000c233  cmp     byte ptr [rdx+38h], 0
0x14000c237  jz      short loc_14000C243
0x14000c239  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c23e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000c243  cmp     byte ptr [rbx+0A0h], 0
0x14000c24a  jz      short loc_14000C25A
0x14000c24c  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x14000c250  lea     rcx, [rsp+0E8h+var_88]; this
0x14000c255  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000c25a  cmp     byte ptr [rbx+0E0h], 0
0x14000c261  jz      short loc_14000C277
0x14000c263  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x14000c26a  lea     rcx, [rsp+0E8h+var_48]; this
0x14000c272  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000c277  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c27c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000c281  nop
0x14000c282  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000c287  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000c28c  lea     r11, [rsp+0E8h+var_8]
0x14000c294  mov     rbx, [r11+10h]
0x14000c298  mov     rsi, [r11+18h]
0x14000c29c  mov     rsp, r11
0x14000c29f  pop     rdi
0x14000c2a0  retn
0x14000c2a1  mov     rcx, [rsp+0E8h]; this
0x14000c2a9  mov     edx, 0A15h; void *
0x14000c2ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c2b4  mov     rcx, [rsp+0E8h]; this
0x14000c2bc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000c2c2  mov     rcx, [rsp+0E8h]; this
0x14000c2ca  mov     edx, 0A15h; void *
0x14000c2cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
