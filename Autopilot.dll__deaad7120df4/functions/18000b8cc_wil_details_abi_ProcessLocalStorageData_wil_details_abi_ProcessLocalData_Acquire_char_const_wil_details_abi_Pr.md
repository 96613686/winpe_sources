# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000b8cc`
- end: `0x18000bcce`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1026`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000d940`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x18000b2f8`
- `0x18000b8cc`
- `0x18000c184`
- `0x18000cac8`
- `0x18000d5c0`
- `0x18000e7b0`
- `0x180010764`
- `0x180011220`
- `0x18001178c`
- `0x180012220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b971`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b971`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ba11`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bb2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bbd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ba11`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bb2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bbd1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b94a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b94a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000baeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000baeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000baff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000baff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b905`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b905`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbed`

## string_xrefs

- `0x18000bc2d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bc46`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bc71`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bc8a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bca3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bcbc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  unsigned __int64 v25; // rax
  const char *v26; // r9
  const char *v27; // r9
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v31[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v31[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v31, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v28);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v29);
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
  v18 = (_DWORD *)(4 * v31[0]);
  if ( 4 * v31[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_23;
  }
  *a2 = 0;
  v19 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v20 = v19;
  if ( !v19 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v31 = 0;
  v21 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v31, Name, v19);
  v15 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v21, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v20);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v30);
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
  *((_QWORD *)v20 + 2) = v31[0];
  v25 = v31[1];
  *v20 = 1;
  *((_QWORD *)v20 + 1) = v6;
  v31[0] = 0;
  *((_QWORD *)v20 + 3) = v25;
  v31[1] = 0;
  memset_0((char *)v20 + 34, 0, 0x56u);
  *((_WORD *)v20 + 16) = 88;
  v20[9] = 1;
  memset_0(v20 + 10, 0, 0x50u);
  *a2 = v20;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return 0;
}

```

## disassembly

```asm
0x18000b8cc  mov     [rsp-8+arg_10], rbx
0x18000b8d1  push    rbp
0x18000b8d2  push    rsi
0x18000b8d3  push    rdi
0x18000b8d4  push    r14
0x18000b8d6  push    r15
0x18000b8d8  lea     rbp, [rsp-160h]
0x18000b8e0  sub     rsp, 260h
0x18000b8e7  mov     rax, cs:__security_cookie
0x18000b8ee  xor     rax, rsp
0x18000b8f1  mov     [rbp+180h+var_30], rax
0x18000b8f8  mov     r15, rdx
0x18000b8fb  mov     qword ptr [rdx], 0
0x18000b902  mov     rbx, rcx
0x18000b905  call    cs:__imp_GetCurrentProcessId
0x18000b90c  nop     dword ptr [rax+rax+00h]
0x18000b911  mov     r14d, 78h ; 'x'
0x18000b917  mov     [rsp+280h+var_258], rbx
0x18000b91c  mov     r9d, eax
0x18000b91f  mov     [rsp+280h+var_260], r14d; int
0x18000b924  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b92b  mov     edx, 104h; unsigned __int64
0x18000b930  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b935  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b93a  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b940  lea     rdx, [rsp+280h+Name]; lpName
0x18000b945  xor     r8d, r8d; dwFlags
0x18000b948  xor     ecx, ecx; lpMutexAttributes
0x18000b94a  call    cs:__imp_CreateMutexExW
0x18000b951  nop     dword ptr [rax+rax+00h]
0x18000b956  mov     rbx, rax
0x18000b959  test    rax, rax
0x18000b95c  jnz     short loc_18000B968
0x18000b95e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b963  jmp     loc_18000BBFF
0x18000b968  xor     r8d, r8d; bAlertable
0x18000b96b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b96e  mov     rcx, rbx; hHandle
0x18000b971  call    cs:__imp_WaitForSingleObjectEx
0x18000b978  nop     dword ptr [rax+rax+00h]
0x18000b97d  cmp     eax, 102h
0x18000b982  jz      short loc_18000B994
0x18000b984  test    eax, 0FFFFFF7Fh
0x18000b989  jnz     loc_18000BC58
0x18000b98f  mov     rdi, rbx
0x18000b992  jmp     short loc_18000B996
0x18000b994  xor     edi, edi
0x18000b996  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000b99b  mov     [rsp+280h+var_250], 0
0x18000b9a4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b9a9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000b9ae  mov     esi, eax
0x18000b9b0  test    eax, eax
0x18000b9b2  jns     loc_18000BA43
0x18000b9b8  mov     rcx, [rbp+188h]; this
0x18000b9bf  lea     r8, aWil; "wil"
0x18000b9c6  mov     r9d, eax; char *
0x18000b9c9  mov     edx, 66h ; 'f'; void *
0x18000b9ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9d3  mov     rcx, [rbp+188h]; this
0x18000b9da  lea     r8, aWil; "wil"
0x18000b9e1  mov     r9d, esi; char *
0x18000b9e4  mov     edx, 6Fh ; 'o'; void *
0x18000b9e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9ee  mov     rcx, [rbp+188h]; this
0x18000b9f5  lea     r8, aWil; "wil"
0x18000b9fc  mov     r9d, esi; char *
0x18000b9ff  mov     edx, 12Eh; void *
0x18000ba04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba09  test    rdi, rdi
0x18000ba0c  jz      short loc_18000BA25
0x18000ba0e  mov     rcx, rdi; hMutex
0x18000ba11  call    cs:__imp_ReleaseMutex
0x18000ba18  nop     dword ptr [rax+rax+00h]
0x18000ba1d  test    eax, eax
0x18000ba1f  jz      loc_18000BC6A
0x18000ba25  mov     rcx, rbx; hObject
0x18000ba28  call    cs:__imp_CloseHandle
0x18000ba2f  nop     dword ptr [rax+rax+00h]
0x18000ba34  test    eax, eax
0x18000ba36  jz      loc_18000BC83
0x18000ba3c  mov     eax, esi
0x18000ba3e  jmp     loc_18000BBFF
0x18000ba43  mov     rax, [rsp+280h+var_250]
0x18000ba48  lea     rcx, ds:0[rax*4]
0x18000ba50  test    rcx, rcx
0x18000ba53  jz      short loc_18000BA63
0x18000ba55  mov     [r15], rcx
0x18000ba58  mov     eax, [rcx]
0x18000ba5a  inc     eax
0x18000ba5c  mov     [rcx], eax
0x18000ba5e  jmp     loc_18000BBC9
0x18000ba63  mov     rdx, r14; dwBytes
0x18000ba66  mov     qword ptr [r15], 0
0x18000ba6d  mov     ecx, 8; dwFlags
0x18000ba72  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ba77  mov     r14, rax
0x18000ba7a  test    rax, rax
0x18000ba7d  jnz     short loc_18000BAA1
0x18000ba7f  mov     rcx, [rbp+188h]; this
0x18000ba86  lea     r8, aWil; "wil"
0x18000ba8d  mov     esi, 8007000Eh
0x18000ba92  mov     edx, 14Bh; void *
0x18000ba97  mov     r9d, esi; char *
0x18000ba9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba9f  jmp     short loc_18000BB0B
0x18000baa1  xorps   xmm0, xmm0
0x18000baa4  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000baa9  mov     r8, r14; void *
0x18000baac  lea     rcx, [rsp+280h+var_250]; this
0x18000bab1  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000bab7  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000babc  mov     esi, eax
0x18000babe  test    eax, eax
0x18000bac0  jns     loc_18000BB5E
0x18000bac6  mov     rcx, [rbp+188h]; this
0x18000bacd  lea     r8, aWil; "wil"
0x18000bad4  mov     r9d, eax; char *
0x18000bad7  mov     edx, 14Eh; void *
0x18000badc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bae1  lea     rcx, [rsp+280h+var_250]; this
0x18000bae6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000baeb  call    cs:__imp_GetProcessHeap
0x18000baf2  nop     dword ptr [rax+rax+00h]
0x18000baf7  mov     r8, r14; lpMem
0x18000bafa  xor     edx, edx; dwFlags
0x18000bafc  mov     rcx, rax; hHeap
0x18000baff  call    cs:__imp_HeapFree
0x18000bb06  nop     dword ptr [rax+rax+00h]
0x18000bb0b  mov     rcx, [rbp+188h]; this
0x18000bb12  lea     r8, aWil; "wil"
0x18000bb19  mov     r9d, esi; char *
0x18000bb1c  mov     edx, 137h; void *
0x18000bb21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb26  test    rdi, rdi
0x18000bb29  jz      short loc_18000BB42
0x18000bb2b  mov     rcx, rdi; hMutex
0x18000bb2e  call    cs:__imp_ReleaseMutex
0x18000bb35  nop     dword ptr [rax+rax+00h]
0x18000bb3a  test    eax, eax
0x18000bb3c  jz      loc_18000BC9C
0x18000bb42  mov     rcx, rbx; hObject
0x18000bb45  call    cs:__imp_CloseHandle
0x18000bb4c  nop     dword ptr [rax+rax+00h]
0x18000bb51  test    eax, eax
0x18000bb53  jz      loc_18000BC3F
0x18000bb59  jmp     loc_18000BA3C
0x18000bb5e  mov     rax, [rsp+280h+var_250]
0x18000bb63  lea     rcx, [r14+22h]; void *
0x18000bb67  xor     edx, edx; Val
0x18000bb69  mov     [r14+10h], rax
0x18000bb6d  mov     rax, [rsp+280h+var_250+8]
0x18000bb72  mov     dword ptr [r14], 1
0x18000bb79  mov     [r14+8], rbx
0x18000bb7d  lea     r8d, [rdx+56h]; Size
0x18000bb81  mov     [rsp+280h+var_250], 0
0x18000bb8a  mov     [r14+18h], rax
0x18000bb8e  mov     [rsp+280h+var_250+8], 0
0x18000bb97  call    memset_0
0x18000bb9c  xor     edx, edx; Val
0x18000bb9e  mov     word ptr [r14+20h], 58h ; 'X'
0x18000bba5  lea     rcx, [r14+28h]; void *
0x18000bba9  mov     dword ptr [r14+24h], 1
0x18000bbb1  lea     r8d, [rdx+50h]; Size
0x18000bbb5  call    memset_0
0x18000bbba  lea     rcx, [rsp+280h+var_250]; this
0x18000bbbf  mov     [r15], r14
0x18000bbc2  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000bbc7  xor     ebx, ebx
0x18000bbc9  test    rdi, rdi
0x18000bbcc  jz      short loc_18000BBE5
0x18000bbce  mov     rcx, rdi; hMutex
0x18000bbd1  call    cs:__imp_ReleaseMutex
0x18000bbd8  nop     dword ptr [rax+rax+00h]
0x18000bbdd  test    eax, eax
0x18000bbdf  jz      loc_18000BCB5
0x18000bbe5  test    rbx, rbx
0x18000bbe8  jz      short loc_18000BBFD
0x18000bbea  mov     rcx, rbx; hObject
0x18000bbed  call    cs:__imp_CloseHandle
0x18000bbf4  nop     dword ptr [rax+rax+00h]
0x18000bbf9  test    eax, eax
0x18000bbfb  jz      short loc_18000BC26
0x18000bbfd  xor     eax, eax
0x18000bbff  mov     rcx, [rbp+180h+var_30]
0x18000bc06  xor     rcx, rsp; StackCookie
0x18000bc09  call    __security_check_cookie
0x18000bc0e  mov     rbx, [rsp+280h+arg_10]
0x18000bc16  add     rsp, 260h
0x18000bc1d  pop     r15
0x18000bc1f  pop     r14
0x18000bc21  pop     rdi
0x18000bc22  pop     rsi
0x18000bc23  pop     rbp
0x18000bc24  retn
0x18000bc26  mov     rcx, [rbp+188h]; this
0x18000bc2d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bc34  mov     edx, 0A0Bh; void *
0x18000bc39  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bc3f  mov     rcx, [rbp+188h]; this
0x18000bc46  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bc4d  mov     edx, 0A0Bh; void *
0x18000bc52  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bc58  mov     rcx, [rbp+188h]; this
0x18000bc5f  mov     edx, 0E01h; void *
0x18000bc64  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000bc6a  mov     rcx, [rbp+188h]; this
0x18000bc71  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bc78  mov     edx, 0A15h; void *
0x18000bc7d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bc83  mov     rcx, [rbp+188h]; this
0x18000bc8a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bc91  mov     edx, 0A0Bh; void *
0x18000bc96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bc9c  mov     rcx, [rbp+188h]; this
0x18000bca3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bcaa  mov     edx, 0A15h; void *
0x18000bcaf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bcb5  mov     rcx, [rbp+188h]; this
0x18000bcbc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bcc3  mov     edx, 0A15h; void *
0x18000bcc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
