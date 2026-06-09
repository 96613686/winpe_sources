# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x140015610`
- end: `0x1400157b5`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `421`
- prototype: `void __fastcall(char *lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1400132c4`
- `0x140017cc0`

## callees

- `0x14000b0f0`
- `0x14000b194`
- `0x14000d2ec`
- `0x140012d54`
- `0x140012e1c`
- `0x1400134f0`
- `0x140014984`
- `0x140015610`
- `0x140015d64`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140015699`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400156dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140015699`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400156dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140015658`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140015658`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400156c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400156c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400156b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400156b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400156a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400156a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001568e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001568e`

## string_xrefs

- `0x140015790`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v11; // r8
  const struct wil::details_abi::RawUsageIndex *v12; // r9
  struct wil::details_abi::RawUsageIndex *v13; // rdx
  _BYTE v14[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v15[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v16[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v14);
      v13 = (struct wil::details_abi::RawUsageIndex *)(lpMem + 40);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap((wil::details_abi::RawUsageIndex *)v14, v13);
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v15,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v16,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v14, (__int64)v13, v11, v12);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v14);
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
        3585,
        (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
0x140015610  mov     [rsp+arg_0], rbx
0x140015615  mov     [rsp+arg_8], rsi
0x14001561a  push    rdi
0x14001561b  sub     rsp, 0E0h
0x140015622  mov     rbx, rcx
0x140015625  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14001562c  jnz     loc_1400156EC
0x140015632  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140015639  test    rax, rax
0x14001563c  jz      short loc_14001564B
0x14001563e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015643  test    al, al
0x140015645  jnz     loc_1400156EC
0x14001564b  mov     rdi, [rbx+8]
0x14001564f  xor     r8d, r8d; bAlertable
0x140015652  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140015655  mov     rcx, rdi; hHandle
0x140015658  call    cs:__imp_WaitForSingleObjectEx
0x14001565e  cmp     eax, 102h
0x140015663  jz      short loc_140015672
0x140015665  test    eax, 0FFFFFF7Fh
0x14001566a  jnz     loc_140015788
0x140015670  jmp     short loc_140015674
0x140015672  xor     edi, edi
0x140015674  mov     eax, [rbx]
0x140015676  dec     eax
0x140015678  mov     [rbx], eax
0x14001567a  mov     eax, [rbx]
0x14001567c  test    eax, eax
0x14001567e  jnz     short loc_1400156D0
0x140015680  lea     rcx, [rbx+10h]; this
0x140015684  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x140015689  test    rdi, rdi
0x14001568c  jz      short loc_1400156AF
0x14001568e  call    cs:__imp_GetLastError
0x140015694  mov     esi, eax
0x140015696  mov     rcx, rdi; hMutex
0x140015699  call    cs:__imp_ReleaseMutex
0x14001569f  test    eax, eax
0x1400156a1  jz      loc_140015775
0x1400156a7  mov     ecx, esi; dwErrCode
0x1400156a9  call    cs:__imp_SetLastError
0x1400156af  mov     rcx, rbx
0x1400156b2  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x1400156b7  call    cs:__imp_GetProcessHeap
0x1400156bd  mov     rcx, rax; hHeap
0x1400156c0  mov     r8, rbx; lpMem
0x1400156c3  xor     edx, edx; dwFlags
0x1400156c5  call    cs:__imp_HeapFree
0x1400156cb  jmp     loc_140015760
0x1400156d0  test    rdi, rdi
0x1400156d3  jz      loc_140015760
0x1400156d9  mov     rcx, rdi; hMutex
0x1400156dc  call    cs:__imp_ReleaseMutex
0x1400156e2  test    eax, eax
0x1400156e4  jz      loc_1400157A2
0x1400156ea  jmp     short loc_140015760
0x1400156ec  mov     eax, [rbx]
0x1400156ee  dec     eax
0x1400156f0  mov     [rbx], eax
0x1400156f2  mov     eax, [rbx]
0x1400156f4  test    eax, eax
0x1400156f6  jnz     short loc_140015760
0x1400156f8  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400156fd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140015702  nop
0x140015703  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x140015707  cmp     byte ptr [rdx+38h], 0
0x14001570b  jz      short loc_140015717
0x14001570d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015712  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140015717  cmp     byte ptr [rbx+0A0h], 0
0x14001571e  jz      short loc_14001572E
0x140015720  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x140015724  lea     rcx, [rsp+0E8h+var_88]; this
0x140015729  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14001572e  cmp     byte ptr [rbx+0E0h], 0
0x140015735  jz      short loc_14001574B
0x140015737  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x14001573e  lea     rcx, [rsp+0E8h+var_48]; this
0x140015746  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14001574b  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015750  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140015755  nop
0x140015756  lea     rcx, [rsp+0E8h+var_C8]; this
0x14001575b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140015760  lea     r11, [rsp+0E8h+var_8]
0x140015768  mov     rbx, [r11+10h]
0x14001576c  mov     rsi, [r11+18h]
0x140015770  mov     rsp, r11
0x140015773  pop     rdi
0x140015774  retn
0x140015775  mov     rcx, [rsp+0E8h]; this
0x14001577d  mov     edx, 0A15h; void *
0x140015782  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140015788  mov     rcx, [rsp+0E8h]; this
0x140015790  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140015797  mov     edx, 0E01h; void *
0x14001579c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400157a2  mov     rcx, [rsp+0E8h]; this
0x1400157aa  mov     edx, 0A15h; void *
0x1400157af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
