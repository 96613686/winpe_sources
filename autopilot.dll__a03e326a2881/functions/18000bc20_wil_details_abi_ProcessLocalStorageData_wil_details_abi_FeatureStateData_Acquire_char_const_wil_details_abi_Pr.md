# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000bc20`
- end: `0x18000c016`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1014`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x18000c7e0`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x18000aaec`
- `0x18000b2a4`
- `0x18000bc20`
- `0x18000c094`
- `0x18000ca34`
- `0x18000d5a8`
- `0x18000e6bc`
- `0x1800105f4`
- `0x180011224`
- `0x1800116ac`
- `0x180012104`
- `0x180012114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000bee3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000bee3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bcb8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000bcb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bd4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000be61`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bf20`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bd4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000be61`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bf20`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000bc97`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000bc97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bc59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bc59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bf36`

## string_xrefs

- `0x18000bf6f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bf88`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bfb3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bfcc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bfeb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c004`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
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
  unsigned __int64 v19; // rax
  wil::details::in1diag3 *v20; // rcx
  bool v21; // r8
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v32[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v32[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v32, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v29);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v30);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v32[0]);
  if ( 4 * v32[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_24;
  }
  *a2 = 0;
  v19 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = (_DWORD *)v19;
  if ( !v19 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v32 = 0;
  if ( (v19 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v32,
          Name,
          v21,
          v19 >> 2);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v32);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v31);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v26);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v32[0];
  *((_QWORD *)v22 + 3) = v32[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v32[0] = 0;
  v32[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v32);
  v6 = 0;
LABEL_24:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v28);
  return 0;
}

```

## disassembly

```asm
0x18000bc20  mov     [rsp-8+arg_10], rbx
0x18000bc25  push    rbp
0x18000bc26  push    rsi
0x18000bc27  push    rdi
0x18000bc28  push    r14
0x18000bc2a  push    r15
0x18000bc2c  lea     rbp, [rsp-160h]
0x18000bc34  sub     rsp, 260h
0x18000bc3b  mov     rax, cs:__security_cookie
0x18000bc42  xor     rax, rsp
0x18000bc45  mov     [rbp+180h+var_30], rax
0x18000bc4c  mov     r15, rdx
0x18000bc4f  mov     qword ptr [rdx], 0
0x18000bc56  mov     rbx, rcx
0x18000bc59  call    cs:__imp_GetCurrentProcessId
0x18000bc5f  mov     r14d, 130h
0x18000bc65  mov     [rsp+280h+var_258], rbx
0x18000bc6a  mov     r9d, eax
0x18000bc6d  mov     [rsp+280h+var_260], r14d; int
0x18000bc72  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000bc79  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bc7e  lea     edx, [r14-2Ch]; unsigned __int64
0x18000bc82  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bc87  mov     r9d, 1F0001h; dwDesiredAccess
0x18000bc8d  lea     rdx, [rsp+280h+Name]; lpName
0x18000bc92  xor     r8d, r8d; dwFlags
0x18000bc95  xor     ecx, ecx; lpMutexAttributes
0x18000bc97  call    cs:__imp_CreateMutexExW
0x18000bc9d  mov     rbx, rax
0x18000bca0  test    rax, rax
0x18000bca3  jnz     short loc_18000BCAF
0x18000bca5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bcaa  jmp     loc_18000BF42
0x18000bcaf  xor     r8d, r8d; bAlertable
0x18000bcb2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000bcb5  mov     rcx, rbx; hHandle
0x18000bcb8  call    cs:__imp_WaitForSingleObjectEx
0x18000bcbe  cmp     eax, 102h
0x18000bcc3  jz      short loc_18000BCD5
0x18000bcc5  test    eax, 0FFFFFF7Fh
0x18000bcca  jnz     loc_18000BF9A
0x18000bcd0  mov     rdi, rbx
0x18000bcd3  jmp     short loc_18000BCD7
0x18000bcd5  xor     edi, edi
0x18000bcd7  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000bcdc  mov     [rsp+280h+var_250], 0
0x18000bce5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bcea  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000bcef  mov     esi, eax
0x18000bcf1  test    eax, eax
0x18000bcf3  jns     short loc_18000BD74
0x18000bcf5  mov     rcx, [rbp+188h]; this
0x18000bcfc  lea     r8, aWil; "wil"
0x18000bd03  mov     r9d, eax; char *
0x18000bd06  mov     edx, 66h ; 'f'; void *
0x18000bd0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd10  mov     rcx, [rbp+188h]; this
0x18000bd17  lea     r8, aWil; "wil"
0x18000bd1e  mov     r9d, esi; char *
0x18000bd21  mov     edx, 6Fh ; 'o'; void *
0x18000bd26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd2b  mov     rcx, [rbp+188h]; this
0x18000bd32  lea     r8, aWil; "wil"
0x18000bd39  mov     r9d, esi; char *
0x18000bd3c  mov     edx, 12Eh; void *
0x18000bd41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd46  test    rdi, rdi
0x18000bd49  jz      short loc_18000BD5C
0x18000bd4b  mov     rcx, rdi; hMutex
0x18000bd4e  call    cs:__imp_ReleaseMutex
0x18000bd54  test    eax, eax
0x18000bd56  jz      loc_18000BFAC
0x18000bd5c  mov     rcx, rbx; hObject
0x18000bd5f  call    cs:__imp_CloseHandle
0x18000bd65  test    eax, eax
0x18000bd67  jz      loc_18000BFC5
0x18000bd6d  mov     eax, esi
0x18000bd6f  jmp     loc_18000BF42
0x18000bd74  mov     rax, [rsp+280h+var_250]
0x18000bd79  lea     rcx, ds:0[rax*4]
0x18000bd81  test    rcx, rcx
0x18000bd84  jz      short loc_18000BD94
0x18000bd86  mov     [r15], rcx
0x18000bd89  mov     eax, [rcx]
0x18000bd8b  inc     eax
0x18000bd8d  mov     [rcx], eax
0x18000bd8f  jmp     loc_18000BF18
0x18000bd94  mov     rdx, r14; dwBytes
0x18000bd97  mov     qword ptr [r15], 0
0x18000bd9e  mov     ecx, 8; dwFlags
0x18000bda3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bda8  mov     r14, rax
0x18000bdab  test    rax, rax
0x18000bdae  jnz     short loc_18000BDD2
0x18000bdb0  mov     rcx, [rbp+188h]; this
0x18000bdb7  lea     r8, aWil; "wil"
0x18000bdbe  mov     esi, 8007000Eh
0x18000bdc3  mov     edx, 14Bh; void *
0x18000bdc8  mov     r9d, esi; char *
0x18000bdcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bdd0  jmp     short loc_18000BE3E
0x18000bdd2  xorps   xmm0, xmm0
0x18000bdd5  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000bddb  test    r14b, 3
0x18000bddf  jnz     loc_18000BFDE
0x18000bde5  mov     r9, r14
0x18000bde8  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000bded  shr     r9, 2; unsigned __int64
0x18000bdf1  lea     rcx, [rsp+280h+var_250]; this
0x18000bdf6  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000bdfb  mov     esi, eax
0x18000bdfd  test    eax, eax
0x18000bdff  jns     loc_18000BE85
0x18000be05  mov     rcx, [rbp+188h]; this
0x18000be0c  lea     r8, aWil; "wil"
0x18000be13  mov     r9d, eax; char *
0x18000be16  mov     edx, 14Eh; void *
0x18000be1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be20  lea     rcx, [rsp+280h+var_250]; this
0x18000be25  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000be2a  call    cs:__imp_GetProcessHeap
0x18000be30  mov     r8, r14; lpMem
0x18000be33  xor     edx, edx; dwFlags
0x18000be35  mov     rcx, rax; hHeap
0x18000be38  call    cs:__imp_HeapFree
0x18000be3e  mov     rcx, [rbp+188h]; this
0x18000be45  lea     r8, aWil; "wil"
0x18000be4c  mov     r9d, esi; char *
0x18000be4f  mov     edx, 137h; void *
0x18000be54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be59  test    rdi, rdi
0x18000be5c  jz      short loc_18000BE6F
0x18000be5e  mov     rcx, rdi; hMutex
0x18000be61  call    cs:__imp_ReleaseMutex
0x18000be67  test    eax, eax
0x18000be69  jz      loc_18000BFE4
0x18000be6f  mov     rcx, rbx; hObject
0x18000be72  call    cs:__imp_CloseHandle
0x18000be78  test    eax, eax
0x18000be7a  jz      loc_18000BF81
0x18000be80  jmp     loc_18000BD6D
0x18000be85  mov     rax, [rsp+280h+var_250]
0x18000be8a  lea     rcx, [r14+28h]; void *
0x18000be8e  mov     [r14+10h], rax
0x18000be92  xor     edx, edx; Val
0x18000be94  mov     rax, [rsp+280h+var_250+8]
0x18000be99  mov     r8d, 108h; Size
0x18000be9f  mov     [r14+18h], rax
0x18000bea3  mov     dword ptr [r14], 1
0x18000beaa  mov     [r14+8], rbx
0x18000beae  mov     [rsp+280h+var_250], 0
0x18000beb7  mov     [rsp+280h+var_250+8], 0
0x18000bec0  call    memset_0
0x18000bec5  xor     eax, eax
0x18000bec7  lea     rcx, [r14+28h]; this
0x18000becb  mov     [r14+20h], rax
0x18000becf  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000bed4  lea     rbx, [r14+0E8h]
0x18000bedb  xor     r8d, r8d; Flags
0x18000bede  mov     rcx, rbx; lpCriticalSection
0x18000bee1  xor     edx, edx; dwSpinCount
0x18000bee3  call    cs:__imp_InitializeCriticalSectionEx
0x18000bee9  mov     qword ptr [rbx+28h], 0
0x18000bef1  lea     rcx, [rsp+280h+var_250]; this
0x18000bef6  mov     qword ptr [rbx+30h], 0
0x18000befe  mov     qword ptr [rbx+38h], 0
0x18000bf06  mov     qword ptr [rbx+40h], 0
0x18000bf0e  mov     [r15], r14
0x18000bf11  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000bf16  xor     ebx, ebx
0x18000bf18  test    rdi, rdi
0x18000bf1b  jz      short loc_18000BF2E
0x18000bf1d  mov     rcx, rdi; hMutex
0x18000bf20  call    cs:__imp_ReleaseMutex
0x18000bf26  test    eax, eax
0x18000bf28  jz      loc_18000BFFD
0x18000bf2e  test    rbx, rbx
0x18000bf31  jz      short loc_18000BF40
0x18000bf33  mov     rcx, rbx; hObject
0x18000bf36  call    cs:__imp_CloseHandle
0x18000bf3c  test    eax, eax
0x18000bf3e  jz      short loc_18000BF68
0x18000bf40  xor     eax, eax
0x18000bf42  mov     rcx, [rbp+180h+var_30]
0x18000bf49  xor     rcx, rsp; StackCookie
0x18000bf4c  call    __security_check_cookie
0x18000bf51  mov     rbx, [rsp+280h+arg_10]
0x18000bf59  add     rsp, 260h
0x18000bf60  pop     r15
0x18000bf62  pop     r14
0x18000bf64  pop     rdi
0x18000bf65  pop     rsi
0x18000bf66  pop     rbp
0x18000bf67  retn
0x18000bf68  mov     rcx, [rbp+188h]; this
0x18000bf6f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bf76  mov     edx, 0A0Bh; void *
0x18000bf7b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bf81  mov     rcx, [rbp+188h]; this
0x18000bf88  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bf8f  mov     edx, 0A0Bh; void *
0x18000bf94  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bf9a  mov     rcx, [rbp+188h]; this
0x18000bfa1  mov     edx, 0E01h; void *
0x18000bfa6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000bfac  mov     rcx, [rbp+188h]; this
0x18000bfb3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bfba  mov     edx, 0A15h; void *
0x18000bfbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bfc5  mov     rcx, [rbp+188h]; this
0x18000bfcc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bfd3  mov     edx, 0A0Bh; void *
0x18000bfd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bfde  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000bfe4  mov     rcx, [rbp+188h]; this
0x18000bfeb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bff2  mov     edx, 0A15h; void *
0x18000bff7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bffd  mov     rcx, [rbp+188h]; this
0x18000c004  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c00b  mov     edx, 0A15h; void *
0x18000c010  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
