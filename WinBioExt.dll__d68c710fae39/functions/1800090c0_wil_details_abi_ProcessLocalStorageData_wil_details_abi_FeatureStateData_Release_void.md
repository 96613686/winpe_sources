# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x1800090c0`
- end: `0x180009265`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `421`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180007480`
- `0x18000a690`

## callees

- `0x180003740`
- `0x1800037e4`
- `0x180005b5c`
- `0x1800071c8`
- `0x180007290`
- `0x1800076ac`
- `0x180008428`
- `0x1800090c0`
- `0x180009550`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009149`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000918c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009149`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000918c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009108`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009108`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009167`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009167`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009175`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009175`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000913e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000913e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009159`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009159`

## string_xrefs

- `0x180009240`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v9; // r8d
  const char *v10; // r9
  _BYTE v11[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v12[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v13[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v11);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v11,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v12,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v13,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v11);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v11);
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
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v9, v10);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v6, v7);
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
0x1800090c0  mov     [rsp+arg_0], rbx
0x1800090c5  mov     [rsp+arg_8], rsi
0x1800090ca  push    rdi
0x1800090cb  sub     rsp, 0E0h
0x1800090d2  mov     rbx, rcx
0x1800090d5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800090dc  jnz     loc_18000919C
0x1800090e2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800090e9  test    rax, rax
0x1800090ec  jz      short loc_1800090FB
0x1800090ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f3  test    al, al
0x1800090f5  jnz     loc_18000919C
0x1800090fb  mov     rdi, [rbx+8]
0x1800090ff  xor     r8d, r8d; bAlertable
0x180009102  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009105  mov     rcx, rdi; hHandle
0x180009108  call    cs:__imp_WaitForSingleObjectEx
0x18000910e  cmp     eax, 102h
0x180009113  jz      short loc_180009122
0x180009115  test    eax, 0FFFFFF7Fh
0x18000911a  jnz     loc_180009238
0x180009120  jmp     short loc_180009124
0x180009122  xor     edi, edi
0x180009124  mov     eax, [rbx]
0x180009126  dec     eax
0x180009128  mov     [rbx], eax
0x18000912a  mov     eax, [rbx]
0x18000912c  test    eax, eax
0x18000912e  jnz     short loc_180009180
0x180009130  lea     rcx, [rbx+10h]; this
0x180009134  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x180009139  test    rdi, rdi
0x18000913c  jz      short loc_18000915F
0x18000913e  call    cs:__imp_GetLastError
0x180009144  mov     esi, eax
0x180009146  mov     rcx, rdi; hMutex
0x180009149  call    cs:__imp_ReleaseMutex
0x18000914f  test    eax, eax
0x180009151  jz      loc_180009225
0x180009157  mov     ecx, esi; dwErrCode
0x180009159  call    cs:__imp_SetLastError
0x18000915f  mov     rcx, rbx
0x180009162  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x180009167  call    cs:__imp_GetProcessHeap
0x18000916d  mov     rcx, rax; hHeap
0x180009170  mov     r8, rbx; lpMem
0x180009173  xor     edx, edx; dwFlags
0x180009175  call    cs:__imp_HeapFree
0x18000917b  jmp     loc_180009210
0x180009180  test    rdi, rdi
0x180009183  jz      loc_180009210
0x180009189  mov     rcx, rdi; hMutex
0x18000918c  call    cs:__imp_ReleaseMutex
0x180009192  test    eax, eax
0x180009194  jz      loc_180009252
0x18000919a  jmp     short loc_180009210
0x18000919c  mov     eax, [rbx]
0x18000919e  dec     eax
0x1800091a0  mov     [rbx], eax
0x1800091a2  mov     eax, [rbx]
0x1800091a4  test    eax, eax
0x1800091a6  jnz     short loc_180009210
0x1800091a8  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800091ad  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800091b2  nop
0x1800091b3  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x1800091b7  cmp     byte ptr [rdx+38h], 0
0x1800091bb  jz      short loc_1800091C7
0x1800091bd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800091c2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800091c7  cmp     byte ptr [rbx+0A0h], 0
0x1800091ce  jz      short loc_1800091DE
0x1800091d0  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x1800091d4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800091d9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800091de  cmp     byte ptr [rbx+0E0h], 0
0x1800091e5  jz      short loc_1800091FB
0x1800091e7  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x1800091ee  lea     rcx, [rsp+0E8h+var_48]; this
0x1800091f6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800091fb  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009200  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180009205  nop
0x180009206  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000920b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180009210  lea     r11, [rsp+0E8h+var_8]
0x180009218  mov     rbx, [r11+10h]
0x18000921c  mov     rsi, [r11+18h]
0x180009220  mov     rsp, r11
0x180009223  pop     rdi
0x180009224  retn
0x180009225  mov     rcx, [rsp+0E8h]; this
0x18000922d  mov     edx, 0A15h; void *
0x180009232  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009238  mov     rcx, [rsp+0E8h]; this
0x180009240  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009247  mov     edx, 0E01h; void *
0x18000924c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009252  mov     rcx, [rsp+0E8h]; this
0x18000925a  mov     edx, 0A15h; void *
0x18000925f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
