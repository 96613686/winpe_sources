# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18000bd50`
- end: `0x18000bef5`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `421`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180009588`
- `0x18002e150`

## callees

- `0x180004630`
- `0x1800046d4`
- `0x180006f10`
- `0x180009088`
- `0x18000916c`
- `0x1800097d4`
- `0x18000b0b0`
- `0x18000bd50`
- `0x18000c6cc`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bd98`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bd98`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bdd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000be1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bdd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000be1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bdf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bdf7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bde9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bde9`

## string_xrefs

- `0x18000bed0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000bd50  mov     [rsp+arg_0], rbx
0x18000bd55  mov     [rsp+arg_8], rsi
0x18000bd5a  push    rdi
0x18000bd5b  sub     rsp, 0E0h
0x18000bd62  mov     rbx, rcx
0x18000bd65  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000bd6c  jnz     loc_18000BE2C
0x18000bd72  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000bd79  test    rax, rax
0x18000bd7c  jz      short loc_18000BD8B
0x18000bd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd83  test    al, al
0x18000bd85  jnz     loc_18000BE2C
0x18000bd8b  mov     rdi, [rbx+8]
0x18000bd8f  xor     r8d, r8d; bAlertable
0x18000bd92  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000bd95  mov     rcx, rdi; hHandle
0x18000bd98  call    cs:__imp_WaitForSingleObjectEx
0x18000bd9e  cmp     eax, 102h
0x18000bda3  jz      short loc_18000BDB2
0x18000bda5  test    eax, 0FFFFFF7Fh
0x18000bdaa  jnz     loc_18000BEC8
0x18000bdb0  jmp     short loc_18000BDB4
0x18000bdb2  xor     edi, edi
0x18000bdb4  mov     eax, [rbx]
0x18000bdb6  dec     eax
0x18000bdb8  mov     [rbx], eax
0x18000bdba  mov     eax, [rbx]
0x18000bdbc  test    eax, eax
0x18000bdbe  jnz     short loc_18000BE10
0x18000bdc0  lea     rcx, [rbx+10h]; this
0x18000bdc4  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000bdc9  test    rdi, rdi
0x18000bdcc  jz      short loc_18000BDEF
0x18000bdce  call    cs:__imp_GetLastError
0x18000bdd4  mov     esi, eax
0x18000bdd6  mov     rcx, rdi; hMutex
0x18000bdd9  call    cs:__imp_ReleaseMutex
0x18000bddf  test    eax, eax
0x18000bde1  jz      loc_18000BEB5
0x18000bde7  mov     ecx, esi; dwErrCode
0x18000bde9  call    cs:__imp_SetLastError
0x18000bdef  mov     rcx, rbx
0x18000bdf2  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x18000bdf7  call    cs:__imp_GetProcessHeap
0x18000bdfd  mov     rcx, rax; hHeap
0x18000be00  mov     r8, rbx; lpMem
0x18000be03  xor     edx, edx; dwFlags
0x18000be05  call    cs:__imp_HeapFree
0x18000be0b  jmp     loc_18000BEA0
0x18000be10  test    rdi, rdi
0x18000be13  jz      loc_18000BEA0
0x18000be19  mov     rcx, rdi; hMutex
0x18000be1c  call    cs:__imp_ReleaseMutex
0x18000be22  test    eax, eax
0x18000be24  jz      loc_18000BEE2
0x18000be2a  jmp     short loc_18000BEA0
0x18000be2c  mov     eax, [rbx]
0x18000be2e  dec     eax
0x18000be30  mov     [rbx], eax
0x18000be32  mov     eax, [rbx]
0x18000be34  test    eax, eax
0x18000be36  jnz     short loc_18000BEA0
0x18000be38  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000be3d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000be42  nop
0x18000be43  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000be47  cmp     byte ptr [rdx+38h], 0
0x18000be4b  jz      short loc_18000BE57
0x18000be4d  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000be52  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000be57  cmp     byte ptr [rbx+0A0h], 0
0x18000be5e  jz      short loc_18000BE6E
0x18000be60  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x18000be64  lea     rcx, [rsp+0E8h+var_88]; this
0x18000be69  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000be6e  cmp     byte ptr [rbx+0E0h], 0
0x18000be75  jz      short loc_18000BE8B
0x18000be77  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x18000be7e  lea     rcx, [rsp+0E8h+var_48]; this
0x18000be86  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000be8b  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000be90  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000be95  nop
0x18000be96  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000be9b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000bea0  lea     r11, [rsp+0E8h+var_8]
0x18000bea8  mov     rbx, [r11+10h]
0x18000beac  mov     rsi, [r11+18h]
0x18000beb0  mov     rsp, r11
0x18000beb3  pop     rdi
0x18000beb4  retn
0x18000beb5  mov     rcx, [rsp+0E8h]; this
0x18000bebd  mov     edx, 0A15h; void *
0x18000bec2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bec8  mov     rcx, [rsp+0E8h]; this
0x18000bed0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bed7  mov     edx, 0E01h; void *
0x18000bedc  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000bee2  mov     rcx, [rsp+0E8h]; this
0x18000beea  mov     edx, 0A15h; void *
0x18000beef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
