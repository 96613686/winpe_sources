# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x180006658`
- end: `0x180006849`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `497`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180002f20`
- `0x180009aa0`

## callees

- `0x180002d04`
- `0x180002e38`
- `0x1800030e8`
- `0x1800031ec`
- `0x180003c1c`
- `0x180003e60`
- `0x180005830`
- `0x180006658`
- `0x180007000`
- `0x18000787c`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000673c`
- `KERNEL32!GetProcessHeap` at `0x18000673c`
- `KERNEL32!HeapFree` at `0x180006750`
- `KERNEL32!HeapFree` at `0x180006750`
- `KERNEL32!CloseHandle` at `0x180006728`
- `KERNEL32!CloseHandle` at `0x180006728`
- `KERNEL32!GetLastError` at `0x1800066da`
- `KERNEL32!GetLastError` at `0x1800066da`
- `KERNEL32!SetLastError` at `0x180006701`
- `KERNEL32!SetLastError` at `0x180006701`
- `KERNEL32!ReleaseMutex` at `0x1800066eb`
- `KERNEL32!ReleaseMutex` at `0x18000676d`
- `KERNEL32!ReleaseMutex` at `0x1800066eb`
- `KERNEL32!ReleaseMutex` at `0x18000676d`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000669a`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000669a`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  DWORD LastError; // ebp
  unsigned int v8; // r8d
  const char *v9; // r9
  void *v10; // rcx
  unsigned int v11; // r8d
  const char *v12; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  _BYTE v16[64]; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v17[64]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v18[104]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v16);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v16,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v17,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v18,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v16);
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
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v14, v15);
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
      wil::details_abi::FeatureStateData::~FeatureStateData((wil::details_abi::FeatureStateData *)(lpMem + 32));
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      v10 = (void *)*((_QWORD *)lpMem + 1);
      if ( v10 )
      {
        if ( !CloseHandle(v10) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v12);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x180006658  push    rbx
0x18000665a  push    rbp
0x18000665b  push    rsi
0x18000665c  push    rdi
0x18000665d  sub     rsp, 0E8h
0x180006664  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000666b  mov     rbx, rcx
0x18000666e  jnz     loc_180006783
0x180006674  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000667b  test    rax, rax
0x18000667e  jz      short loc_18000668D
0x180006680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006685  test    al, al
0x180006687  jnz     loc_180006783
0x18000668d  mov     rdi, [rbx+8]
0x180006691  xor     r8d, r8d; bAlertable
0x180006694  mov     rcx, rdi; hHandle
0x180006697  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000669a  call    cs:__imp_WaitForSingleObjectEx
0x1800066a1  nop     dword ptr [rax+rax+00h]
0x1800066a6  cmp     eax, 102h
0x1800066ab  jz      short loc_1800066BA
0x1800066ad  test    eax, 0FFFFFF7Fh
0x1800066b2  jnz     loc_180006815
0x1800066b8  jmp     short loc_1800066BC
0x1800066ba  xor     edi, edi
0x1800066bc  mov     eax, [rbx]
0x1800066be  dec     eax
0x1800066c0  mov     [rbx], eax
0x1800066c2  mov     eax, [rbx]
0x1800066c4  test    eax, eax
0x1800066c6  jnz     loc_180006761
0x1800066cc  lea     rcx, [rbx+10h]; this
0x1800066d0  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x1800066d5  test    rdi, rdi
0x1800066d8  jz      short loc_18000670D
0x1800066da  call    cs:__imp_GetLastError
0x1800066e1  nop     dword ptr [rax+rax+00h]
0x1800066e6  mov     rcx, rdi; hMutex
0x1800066e9  mov     ebp, eax
0x1800066eb  call    cs:__imp_ReleaseMutex
0x1800066f2  nop     dword ptr [rax+rax+00h]
0x1800066f7  test    eax, eax
0x1800066f9  jz      loc_180006836
0x1800066ff  mov     ecx, ebp; dwErrCode
0x180006701  call    cs:__imp_SetLastError
0x180006708  nop     dword ptr [rax+rax+00h]
0x18000670d  lea     rcx, [rbx+20h]; this
0x180006711  call    ??1FeatureStateData@details_abi@wil@@QEAA@XZ; wil::details_abi::FeatureStateData::~FeatureStateData(void)
0x180006716  lea     rcx, [rbx+10h]; this
0x18000671a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000671f  mov     rcx, [rbx+8]; hObject
0x180006723  test    rcx, rcx
0x180006726  jz      short loc_18000673C
0x180006728  call    cs:__imp_CloseHandle
0x18000672f  nop     dword ptr [rax+rax+00h]
0x180006734  test    eax, eax
0x180006736  jz      loc_180006802
0x18000673c  call    cs:__imp_GetProcessHeap
0x180006743  nop     dword ptr [rax+rax+00h]
0x180006748  mov     r8, rbx; lpMem
0x18000674b  xor     edx, edx; dwFlags
0x18000674d  mov     rcx, rax; hHeap
0x180006750  call    cs:__imp_HeapFree
0x180006757  nop     dword ptr [rax+rax+00h]
0x18000675c  jmp     loc_1800067F5
0x180006761  test    rdi, rdi
0x180006764  jz      loc_1800067F5
0x18000676a  mov     rcx, rdi; hMutex
0x18000676d  call    cs:__imp_ReleaseMutex
0x180006774  nop     dword ptr [rax+rax+00h]
0x180006779  test    eax, eax
0x18000677b  jz      loc_180006823
0x180006781  jmp     short loc_1800067F5
0x180006783  mov     eax, [rbx]
0x180006785  dec     eax
0x180006787  mov     [rbx], eax
0x180006789  mov     eax, [rbx]
0x18000678b  test    eax, eax
0x18000678d  jnz     short loc_1800067F5
0x18000678f  lea     rcx, [rsp+108h+var_E8]; this
0x180006794  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006799  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000679d  cmp     byte ptr [rdx+38h], 0
0x1800067a1  jz      short loc_1800067AD
0x1800067a3  lea     rcx, [rsp+108h+var_E8]; this
0x1800067a8  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800067ad  cmp     byte ptr [rbx+0A0h], 0
0x1800067b4  jz      short loc_1800067C4
0x1800067b6  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x1800067ba  lea     rcx, [rsp+108h+var_A8]; this
0x1800067bf  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800067c4  cmp     byte ptr [rbx+0E0h], 0
0x1800067cb  jz      short loc_1800067E1
0x1800067cd  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x1800067d4  lea     rcx, [rsp+108h+var_68]; this
0x1800067dc  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800067e1  lea     rcx, [rsp+108h+var_E8]; this
0x1800067e6  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800067eb  lea     rcx, [rsp+108h+var_E8]; this
0x1800067f0  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800067f5  add     rsp, 0E8h
0x1800067fc  pop     rdi
0x1800067fd  pop     rsi
0x1800067fe  pop     rbp
0x1800067ff  pop     rbx
0x180006800  retn
0x180006802  mov     rcx, [rsp+108h]; this
0x18000680a  mov     edx, 0A0Bh; void *
0x18000680f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006815  mov     rcx, [rsp+108h]; this
0x18000681d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006823  mov     rcx, [rsp+108h]; this
0x18000682b  mov     edx, 0A15h; void *
0x180006830  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006836  mov     rcx, [rsp+108h]; this
0x18000683e  mov     edx, 0A15h; void *
0x180006843  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
