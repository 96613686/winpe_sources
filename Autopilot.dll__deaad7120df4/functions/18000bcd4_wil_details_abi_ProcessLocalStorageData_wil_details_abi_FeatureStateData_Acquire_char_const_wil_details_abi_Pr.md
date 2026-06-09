# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000bcd4`
- end: `0x18000c103`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1071`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000c870`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x18000ab6c`
- `0x18000b2f8`
- `0x18000bcd4`
- `0x18000c184`
- `0x18000cac8`
- `0x18000d5c0`
- `0x18000e7b0`
- `0x180010764`
- `0x180011220`
- `0x18001178c`
- `0x180012220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000bfc3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000bfc3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bd78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bd78`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000be18`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bf35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c006`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000be18`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bf35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c006`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000bd51`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000bd51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bef2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bef2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bd0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bd0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c022`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c022`

## string_xrefs

- `0x18000c062`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c07b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c0a6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c0bf`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c0d8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c0f1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  _DWORD *v19; // rax
  _DWORD *v20; // r14
  int v21; // eax
  HANDLE ProcessHeap; // rax
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v30[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  v30[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v30, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v27);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v28);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v30[0]);
  if ( 4 * v30[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_23;
  }
  *a2 = 0;
  v19 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v20 = v19;
  if ( !v19 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v30 = 0;
  v21 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v30, Name, v19);
  v15 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v21, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v20);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v29);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return v15;
  }
  *((_QWORD *)v20 + 2) = v30[0];
  *((_QWORD *)v20 + 3) = v30[1];
  *v20 = 1;
  *((_QWORD *)v20 + 1) = v6;
  v30[0] = 0;
  v30[1] = 0;
  memset_0(v20 + 10, 0, 0x108u);
  *((_QWORD *)v20 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v20 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v20 + 58), 0, 0);
  *((_QWORD *)v20 + 34) = 0;
  *((_QWORD *)v20 + 35) = 0;
  *((_QWORD *)v20 + 36) = 0;
  *((_QWORD *)v20 + 37) = 0;
  *a2 = v20;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v30);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  return 0;
}

```

## disassembly

```asm
0x18000bcd4  mov     [rsp-8+arg_10], rbx
0x18000bcd9  push    rbp
0x18000bcda  push    rsi
0x18000bcdb  push    rdi
0x18000bcdc  push    r14
0x18000bcde  push    r15
0x18000bce0  lea     rbp, [rsp-160h]
0x18000bce8  sub     rsp, 260h
0x18000bcef  mov     rax, cs:__security_cookie
0x18000bcf6  xor     rax, rsp
0x18000bcf9  mov     [rbp+180h+var_30], rax
0x18000bd00  mov     r15, rdx
0x18000bd03  mov     qword ptr [rdx], 0
0x18000bd0a  mov     rbx, rcx
0x18000bd0d  call    cs:__imp_GetCurrentProcessId
0x18000bd14  nop     dword ptr [rax+rax+00h]
0x18000bd19  mov     r14d, 130h
0x18000bd1f  mov     [rsp+280h+var_258], rbx
0x18000bd24  mov     r9d, eax
0x18000bd27  mov     [rsp+280h+var_260], r14d; int
0x18000bd2c  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000bd33  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bd38  lea     edx, [r14-2Ch]; unsigned __int64
0x18000bd3c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bd41  mov     r9d, 1F0001h; dwDesiredAccess
0x18000bd47  lea     rdx, [rsp+280h+Name]; lpName
0x18000bd4c  xor     r8d, r8d; dwFlags
0x18000bd4f  xor     ecx, ecx; lpMutexAttributes
0x18000bd51  call    cs:__imp_CreateMutexExW
0x18000bd58  nop     dword ptr [rax+rax+00h]
0x18000bd5d  mov     rbx, rax
0x18000bd60  test    rax, rax
0x18000bd63  jnz     short loc_18000BD6F
0x18000bd65  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bd6a  jmp     loc_18000C034
0x18000bd6f  xor     r8d, r8d; bAlertable
0x18000bd72  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000bd75  mov     rcx, rbx; hHandle
0x18000bd78  call    cs:__imp_WaitForSingleObjectEx
0x18000bd7f  nop     dword ptr [rax+rax+00h]
0x18000bd84  cmp     eax, 102h
0x18000bd89  jz      short loc_18000BD9B
0x18000bd8b  test    eax, 0FFFFFF7Fh
0x18000bd90  jnz     loc_18000C08D
0x18000bd96  mov     rdi, rbx
0x18000bd99  jmp     short loc_18000BD9D
0x18000bd9b  xor     edi, edi
0x18000bd9d  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000bda2  mov     [rsp+280h+var_250], 0
0x18000bdab  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bdb0  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000bdb5  mov     esi, eax
0x18000bdb7  test    eax, eax
0x18000bdb9  jns     loc_18000BE4A
0x18000bdbf  mov     rcx, [rbp+188h]; this
0x18000bdc6  lea     r8, aWil; "wil"
0x18000bdcd  mov     r9d, eax; char *
0x18000bdd0  mov     edx, 66h ; 'f'; void *
0x18000bdd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bdda  mov     rcx, [rbp+188h]; this
0x18000bde1  lea     r8, aWil; "wil"
0x18000bde8  mov     r9d, esi; char *
0x18000bdeb  mov     edx, 6Fh ; 'o'; void *
0x18000bdf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bdf5  mov     rcx, [rbp+188h]; this
0x18000bdfc  lea     r8, aWil; "wil"
0x18000be03  mov     r9d, esi; char *
0x18000be06  mov     edx, 12Eh; void *
0x18000be0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be10  test    rdi, rdi
0x18000be13  jz      short loc_18000BE2C
0x18000be15  mov     rcx, rdi; hMutex
0x18000be18  call    cs:__imp_ReleaseMutex
0x18000be1f  nop     dword ptr [rax+rax+00h]
0x18000be24  test    eax, eax
0x18000be26  jz      loc_18000C09F
0x18000be2c  mov     rcx, rbx; hObject
0x18000be2f  call    cs:__imp_CloseHandle
0x18000be36  nop     dword ptr [rax+rax+00h]
0x18000be3b  test    eax, eax
0x18000be3d  jz      loc_18000C0B8
0x18000be43  mov     eax, esi
0x18000be45  jmp     loc_18000C034
0x18000be4a  mov     rax, [rsp+280h+var_250]
0x18000be4f  lea     rcx, ds:0[rax*4]
0x18000be57  test    rcx, rcx
0x18000be5a  jz      short loc_18000BE6A
0x18000be5c  mov     [r15], rcx
0x18000be5f  mov     eax, [rcx]
0x18000be61  inc     eax
0x18000be63  mov     [rcx], eax
0x18000be65  jmp     loc_18000BFFE
0x18000be6a  mov     rdx, r14; dwBytes
0x18000be6d  mov     qword ptr [r15], 0
0x18000be74  mov     ecx, 8; dwFlags
0x18000be79  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000be7e  mov     r14, rax
0x18000be81  test    rax, rax
0x18000be84  jnz     short loc_18000BEA8
0x18000be86  mov     rcx, [rbp+188h]; this
0x18000be8d  lea     r8, aWil; "wil"
0x18000be94  mov     esi, 8007000Eh
0x18000be99  mov     edx, 14Bh; void *
0x18000be9e  mov     r9d, esi; char *
0x18000bea1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bea6  jmp     short loc_18000BF12
0x18000bea8  xorps   xmm0, xmm0
0x18000beab  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000beb0  mov     r8, r14; void *
0x18000beb3  lea     rcx, [rsp+280h+var_250]; this
0x18000beb8  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000bebe  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000bec3  mov     esi, eax
0x18000bec5  test    eax, eax
0x18000bec7  jns     loc_18000BF65
0x18000becd  mov     rcx, [rbp+188h]; this
0x18000bed4  lea     r8, aWil; "wil"
0x18000bedb  mov     r9d, eax; char *
0x18000bede  mov     edx, 14Eh; void *
0x18000bee3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bee8  lea     rcx, [rsp+280h+var_250]; this
0x18000beed  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000bef2  call    cs:__imp_GetProcessHeap
0x18000bef9  nop     dword ptr [rax+rax+00h]
0x18000befe  mov     r8, r14; lpMem
0x18000bf01  xor     edx, edx; dwFlags
0x18000bf03  mov     rcx, rax; hHeap
0x18000bf06  call    cs:__imp_HeapFree
0x18000bf0d  nop     dword ptr [rax+rax+00h]
0x18000bf12  mov     rcx, [rbp+188h]; this
0x18000bf19  lea     r8, aWil; "wil"
0x18000bf20  mov     r9d, esi; char *
0x18000bf23  mov     edx, 137h; void *
0x18000bf28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf2d  test    rdi, rdi
0x18000bf30  jz      short loc_18000BF49
0x18000bf32  mov     rcx, rdi; hMutex
0x18000bf35  call    cs:__imp_ReleaseMutex
0x18000bf3c  nop     dword ptr [rax+rax+00h]
0x18000bf41  test    eax, eax
0x18000bf43  jz      loc_18000C0D1
0x18000bf49  mov     rcx, rbx; hObject
0x18000bf4c  call    cs:__imp_CloseHandle
0x18000bf53  nop     dword ptr [rax+rax+00h]
0x18000bf58  test    eax, eax
0x18000bf5a  jz      loc_18000C074
0x18000bf60  jmp     loc_18000BE43
0x18000bf65  mov     rax, [rsp+280h+var_250]
0x18000bf6a  lea     rcx, [r14+28h]; void *
0x18000bf6e  mov     [r14+10h], rax
0x18000bf72  xor     edx, edx; Val
0x18000bf74  mov     rax, [rsp+280h+var_250+8]
0x18000bf79  mov     r8d, 108h; Size
0x18000bf7f  mov     [r14+18h], rax
0x18000bf83  mov     dword ptr [r14], 1
0x18000bf8a  mov     [r14+8], rbx
0x18000bf8e  mov     [rsp+280h+var_250], 0
0x18000bf97  mov     [rsp+280h+var_250+8], 0
0x18000bfa0  call    memset_0
0x18000bfa5  xor     eax, eax
0x18000bfa7  lea     rcx, [r14+28h]; this
0x18000bfab  mov     [r14+20h], rax
0x18000bfaf  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000bfb4  lea     rbx, [r14+0E8h]
0x18000bfbb  xor     r8d, r8d; Flags
0x18000bfbe  mov     rcx, rbx; lpCriticalSection
0x18000bfc1  xor     edx, edx; dwSpinCount
0x18000bfc3  call    cs:__imp_InitializeCriticalSectionEx
0x18000bfca  nop     dword ptr [rax+rax+00h]
0x18000bfcf  mov     qword ptr [rbx+28h], 0
0x18000bfd7  lea     rcx, [rsp+280h+var_250]; this
0x18000bfdc  mov     qword ptr [rbx+30h], 0
0x18000bfe4  mov     qword ptr [rbx+38h], 0
0x18000bfec  mov     qword ptr [rbx+40h], 0
0x18000bff4  mov     [r15], r14
0x18000bff7  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000bffc  xor     ebx, ebx
0x18000bffe  test    rdi, rdi
0x18000c001  jz      short loc_18000C01A
0x18000c003  mov     rcx, rdi; hMutex
0x18000c006  call    cs:__imp_ReleaseMutex
0x18000c00d  nop     dword ptr [rax+rax+00h]
0x18000c012  test    eax, eax
0x18000c014  jz      loc_18000C0EA
0x18000c01a  test    rbx, rbx
0x18000c01d  jz      short loc_18000C032
0x18000c01f  mov     rcx, rbx; hObject
0x18000c022  call    cs:__imp_CloseHandle
0x18000c029  nop     dword ptr [rax+rax+00h]
0x18000c02e  test    eax, eax
0x18000c030  jz      short loc_18000C05B
0x18000c032  xor     eax, eax
0x18000c034  mov     rcx, [rbp+180h+var_30]
0x18000c03b  xor     rcx, rsp; StackCookie
0x18000c03e  call    __security_check_cookie
0x18000c043  mov     rbx, [rsp+280h+arg_10]
0x18000c04b  add     rsp, 260h
0x18000c052  pop     r15
0x18000c054  pop     r14
0x18000c056  pop     rdi
0x18000c057  pop     rsi
0x18000c058  pop     rbp
0x18000c059  retn
0x18000c05b  mov     rcx, [rbp+188h]; this
0x18000c062  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c069  mov     edx, 0A0Bh; void *
0x18000c06e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c074  mov     rcx, [rbp+188h]; this
0x18000c07b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c082  mov     edx, 0A0Bh; void *
0x18000c087  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c08d  mov     rcx, [rbp+188h]; this
0x18000c094  mov     edx, 0E01h; void *
0x18000c099  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000c09f  mov     rcx, [rbp+188h]; this
0x18000c0a6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c0ad  mov     edx, 0A15h; void *
0x18000c0b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c0b8  mov     rcx, [rbp+188h]; this
0x18000c0bf  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c0c6  mov     edx, 0A0Bh; void *
0x18000c0cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c0d1  mov     rcx, [rbp+188h]; this
0x18000c0d8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c0df  mov     edx, 0A15h; void *
0x18000c0e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c0ea  mov     rcx, [rbp+188h]; this
0x18000c0f1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c0f8  mov     edx, 0A15h; void *
0x18000c0fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
