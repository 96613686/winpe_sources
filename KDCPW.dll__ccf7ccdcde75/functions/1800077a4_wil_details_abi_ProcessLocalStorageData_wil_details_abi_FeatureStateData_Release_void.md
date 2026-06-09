# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x1800077a4`
- end: `0x18000793b`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800035ec`
- `0x18000cca0`

## callees

- `0x180003140`
- `0x1800032d4`
- `0x180003864`
- `0x1800044c0`
- `0x1800047b8`
- `0x180006744`
- `0x1800077a4`
- `0x180008530`
- `0x180008ebc`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800077ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800077ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000782d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007870`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000782d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007870`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007859`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007859`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000784b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000784b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007822`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000783d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000783d`

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
0x1800077a4  mov     [rsp+arg_0], rbx
0x1800077a9  mov     [rsp+arg_8], rsi
0x1800077ae  push    rdi
0x1800077af  sub     rsp, 0E0h
0x1800077b6  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800077bd  mov     rbx, rcx
0x1800077c0  jnz     loc_180007880
0x1800077c6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800077cd  test    rax, rax
0x1800077d0  jz      short loc_1800077DF
0x1800077d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077d7  test    al, al
0x1800077d9  jnz     loc_180007880
0x1800077df  mov     rdi, [rbx+8]
0x1800077e3  xor     r8d, r8d; bAlertable
0x1800077e6  mov     rcx, rdi; hHandle
0x1800077e9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800077ec  call    cs:__imp_WaitForSingleObjectEx
0x1800077f2  cmp     eax, 102h
0x1800077f7  jz      short loc_180007806
0x1800077f9  test    eax, 0FFFFFF7Fh
0x1800077fe  jnz     loc_18000791A
0x180007804  jmp     short loc_180007808
0x180007806  xor     edi, edi
0x180007808  mov     eax, [rbx]
0x18000780a  dec     eax
0x18000780c  mov     [rbx], eax
0x18000780e  mov     eax, [rbx]
0x180007810  test    eax, eax
0x180007812  jnz     short loc_180007864
0x180007814  lea     rcx, [rbx+10h]; this
0x180007818  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18000781d  test    rdi, rdi
0x180007820  jz      short loc_180007843
0x180007822  call    cs:__imp_GetLastError
0x180007828  mov     rcx, rdi; hMutex
0x18000782b  mov     esi, eax
0x18000782d  call    cs:__imp_ReleaseMutex
0x180007833  test    eax, eax
0x180007835  jz      loc_180007907
0x18000783b  mov     ecx, esi; dwErrCode
0x18000783d  call    cs:__imp_SetLastError
0x180007843  mov     rcx, rbx
0x180007846  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x18000784b  call    cs:__imp_GetProcessHeap
0x180007851  mov     r8, rbx; lpMem
0x180007854  xor     edx, edx; dwFlags
0x180007856  mov     rcx, rax; hHeap
0x180007859  call    cs:__imp_HeapFree
0x18000785f  jmp     loc_1800078F2
0x180007864  test    rdi, rdi
0x180007867  jz      loc_1800078F2
0x18000786d  mov     rcx, rdi; hMutex
0x180007870  call    cs:__imp_ReleaseMutex
0x180007876  test    eax, eax
0x180007878  jz      loc_180007928
0x18000787e  jmp     short loc_1800078F2
0x180007880  mov     eax, [rbx]
0x180007882  dec     eax
0x180007884  mov     [rbx], eax
0x180007886  mov     eax, [rbx]
0x180007888  test    eax, eax
0x18000788a  jnz     short loc_1800078F2
0x18000788c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007891  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007896  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x18000789a  cmp     byte ptr [rdx+38h], 0
0x18000789e  jz      short loc_1800078AA
0x1800078a0  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800078a5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800078aa  cmp     byte ptr [rbx+0A0h], 0
0x1800078b1  jz      short loc_1800078C1
0x1800078b3  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x1800078b7  lea     rcx, [rsp+0E8h+var_88]; this
0x1800078bc  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800078c1  cmp     byte ptr [rbx+0E0h], 0
0x1800078c8  jz      short loc_1800078DE
0x1800078ca  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x1800078d1  lea     rcx, [rsp+0E8h+var_48]; this
0x1800078d9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800078de  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800078e3  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800078e8  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800078ed  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800078f2  lea     r11, [rsp+0E8h+var_8]
0x1800078fa  mov     rbx, [r11+10h]
0x1800078fe  mov     rsi, [r11+18h]
0x180007902  mov     rsp, r11
0x180007905  pop     rdi
0x180007906  retn
0x180007907  mov     rcx, [rsp+0E8h]; this
0x18000790f  mov     edx, 0A15h; void *
0x180007914  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000791a  mov     rcx, [rsp+0E8h]; this
0x180007922  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007928  mov     rcx, [rsp+0E8h]; this
0x180007930  mov     edx, 0A15h; void *
0x180007935  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
