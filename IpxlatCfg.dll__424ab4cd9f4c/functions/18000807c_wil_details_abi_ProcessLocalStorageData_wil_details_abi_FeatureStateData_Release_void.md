# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000807c`
- end: `0x180008221`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `421`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800043e0`
- `0x180018930`

## callees

- `0x180003ec4`
- `0x180004090`
- `0x18000477c`
- `0x180005340`
- `0x180005638`
- `0x180007064`
- `0x18000807c`
- `0x180009214`
- `0x180009bcc`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008115`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008131`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008131`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008123`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008123`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800080c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800080c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008105`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008148`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008105`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008148`

## string_xrefs

- `0x1800081fc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  const char *v4; // r9
  DWORD LastError; // esi
  __int64 v6; // r8
  const char *v7; // r9
  HANDLE ProcessHeap; // rax
  __int64 v9; // r8
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
      wil::details::in1diag3::FailFast_Unexpected(
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
0x18000807c  mov     [rsp+arg_0], rbx
0x180008081  mov     [rsp+arg_8], rsi
0x180008086  push    rdi
0x180008087  sub     rsp, 0E0h
0x18000808e  mov     rbx, rcx
0x180008091  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008098  jnz     loc_180008158
0x18000809e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800080a5  test    rax, rax
0x1800080a8  jz      short loc_1800080B7
0x1800080aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080af  test    al, al
0x1800080b1  jnz     loc_180008158
0x1800080b7  mov     rdi, [rbx+8]
0x1800080bb  xor     r8d, r8d; bAlertable
0x1800080be  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800080c1  mov     rcx, rdi; hHandle
0x1800080c4  call    cs:__imp_WaitForSingleObjectEx
0x1800080ca  cmp     eax, 102h
0x1800080cf  jz      short loc_1800080DE
0x1800080d1  test    eax, 0FFFFFF7Fh
0x1800080d6  jnz     loc_1800081F4
0x1800080dc  jmp     short loc_1800080E0
0x1800080de  xor     edi, edi
0x1800080e0  mov     eax, [rbx]
0x1800080e2  dec     eax
0x1800080e4  mov     [rbx], eax
0x1800080e6  mov     eax, [rbx]
0x1800080e8  test    eax, eax
0x1800080ea  jnz     short loc_18000813C
0x1800080ec  lea     rcx, [rbx+10h]; this
0x1800080f0  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x1800080f5  test    rdi, rdi
0x1800080f8  jz      short loc_18000811B
0x1800080fa  call    cs:__imp_GetLastError
0x180008100  mov     esi, eax
0x180008102  mov     rcx, rdi; hMutex
0x180008105  call    cs:__imp_ReleaseMutex
0x18000810b  test    eax, eax
0x18000810d  jz      loc_1800081E1
0x180008113  mov     ecx, esi; dwErrCode
0x180008115  call    cs:__imp_SetLastError
0x18000811b  mov     rcx, rbx
0x18000811e  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x180008123  call    cs:__imp_GetProcessHeap
0x180008129  mov     rcx, rax; hHeap
0x18000812c  mov     r8, rbx; lpMem
0x18000812f  xor     edx, edx; dwFlags
0x180008131  call    cs:__imp_HeapFree
0x180008137  jmp     loc_1800081CC
0x18000813c  test    rdi, rdi
0x18000813f  jz      loc_1800081CC
0x180008145  mov     rcx, rdi; hMutex
0x180008148  call    cs:__imp_ReleaseMutex
0x18000814e  test    eax, eax
0x180008150  jz      loc_18000820E
0x180008156  jmp     short loc_1800081CC
0x180008158  mov     eax, [rbx]
0x18000815a  dec     eax
0x18000815c  mov     [rbx], eax
0x18000815e  mov     eax, [rbx]
0x180008160  test    eax, eax
0x180008162  jnz     short loc_1800081CC
0x180008164  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008169  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000816e  nop
0x18000816f  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x180008173  cmp     byte ptr [rdx+38h], 0
0x180008177  jz      short loc_180008183
0x180008179  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000817e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008183  cmp     byte ptr [rbx+0A0h], 0
0x18000818a  jz      short loc_18000819A
0x18000818c  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x180008190  lea     rcx, [rsp+0E8h+var_88]; this
0x180008195  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000819a  cmp     byte ptr [rbx+0E0h], 0
0x1800081a1  jz      short loc_1800081B7
0x1800081a3  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x1800081aa  lea     rcx, [rsp+0E8h+var_48]; this
0x1800081b2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800081b7  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800081bc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800081c1  nop
0x1800081c2  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800081c7  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800081cc  lea     r11, [rsp+0E8h+var_8]
0x1800081d4  mov     rbx, [r11+10h]
0x1800081d8  mov     rsi, [r11+18h]
0x1800081dc  mov     rsp, r11
0x1800081df  pop     rdi
0x1800081e0  retn
0x1800081e1  mov     rcx, [rsp+0E8h]; this
0x1800081e9  mov     edx, 0A15h; void *
0x1800081ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800081f4  mov     rcx, [rsp+0E8h]; this
0x1800081fc  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008203  mov     edx, 0E01h; void *
0x180008208  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000820e  mov     rcx, [rsp+0E8h]; this
0x180008216  mov     edx, 0A15h; void *
0x18000821b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
