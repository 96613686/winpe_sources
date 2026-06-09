# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000b848`
- end: `0x18000bc19`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `977`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000d914`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x18000b2a4`
- `0x18000b848`
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

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b8e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b8e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b977`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ba8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bb23`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b977`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ba8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bb23`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b8c0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b8c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b881`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b881`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bb39`

## string_xrefs

- `0x18000bb72`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bb9d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bbb6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bbd5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bbee`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bc07`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
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
  unsigned __int64 v19; // rax
  wil::details::in1diag3 *v20; // rcx
  bool v21; // r8
  _QWORD *v22; // rsi
  unsigned int v23; // r14d
  int v24; // eax
  HANDLE ProcessHeap; // rax
  const char *v26; // r9
  const char *v27; // r9
  unsigned __int64 v28; // rax
  const char *v29; // r9
  const char *v30; // r9
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v34[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v34[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v34, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v31);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v32);
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
  v18 = (_DWORD *)(4 * v34[0]);
  if ( 4 * v34[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_24;
  }
  *a2 = 0;
  v19 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = (_QWORD *)v19;
  if ( v19 )
  {
    *(_OWORD *)v34 = 0;
    if ( (v19 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
    v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v34,
            Name,
            v21,
            v19 >> 2);
    v23 = v24;
    if ( v24 >= 0 )
    {
      v22[2] = v34[0];
      v28 = v34[1];
      *(_DWORD *)v22 = 1;
      v22[1] = v6;
      v34[0] = 0;
      v22[3] = v28;
      v34[1] = 0;
      memset_0((char *)v22 + 34, 0, 0x56u);
      *((_WORD *)v22 + 16) = 88;
      *((_DWORD *)v22 + 9) = 1;
      memset_0(v22 + 5, 0, 0x50u);
      *a2 = v22;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
      v6 = 0;
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v30);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v24, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
  }
  else
  {
    v23 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v23, v33);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return v23;
}

```

## disassembly

```asm
0x18000b848  mov     [rsp-8+arg_10], rbx
0x18000b84d  push    rbp
0x18000b84e  push    rsi
0x18000b84f  push    rdi
0x18000b850  push    r14
0x18000b852  push    r15
0x18000b854  lea     rbp, [rsp-160h]
0x18000b85c  sub     rsp, 260h
0x18000b863  mov     rax, cs:__security_cookie
0x18000b86a  xor     rax, rsp
0x18000b86d  mov     [rbp+180h+var_30], rax
0x18000b874  mov     r15, rdx
0x18000b877  mov     qword ptr [rdx], 0
0x18000b87e  mov     rbx, rcx
0x18000b881  call    cs:__imp_GetCurrentProcessId
0x18000b887  mov     r14d, 78h ; 'x'
0x18000b88d  mov     [rsp+280h+var_258], rbx
0x18000b892  mov     r9d, eax
0x18000b895  mov     [rsp+280h+var_260], r14d; int
0x18000b89a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b8a1  mov     edx, 104h; unsigned __int64
0x18000b8a6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b8ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b8b0  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b8b6  lea     rdx, [rsp+280h+Name]; lpName
0x18000b8bb  xor     r8d, r8d; dwFlags
0x18000b8be  xor     ecx, ecx; lpMutexAttributes
0x18000b8c0  call    cs:__imp_CreateMutexExW
0x18000b8c6  mov     rbx, rax
0x18000b8c9  test    rax, rax
0x18000b8cc  jnz     short loc_18000B8D8
0x18000b8ce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b8d3  jmp     loc_18000BB45
0x18000b8d8  xor     r8d, r8d; bAlertable
0x18000b8db  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b8de  mov     rcx, rbx; hHandle
0x18000b8e1  call    cs:__imp_WaitForSingleObjectEx
0x18000b8e7  cmp     eax, 102h
0x18000b8ec  jz      short loc_18000B8FE
0x18000b8ee  test    eax, 0FFFFFF7Fh
0x18000b8f3  jnz     loc_18000BB84
0x18000b8f9  mov     rdi, rbx
0x18000b8fc  jmp     short loc_18000B900
0x18000b8fe  xor     edi, edi
0x18000b900  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000b905  mov     [rsp+280h+var_250], 0
0x18000b90e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b913  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000b918  mov     esi, eax
0x18000b91a  test    eax, eax
0x18000b91c  jns     short loc_18000B99D
0x18000b91e  mov     rcx, [rbp+188h]; this
0x18000b925  lea     r8, aWil; "wil"
0x18000b92c  mov     r9d, eax; char *
0x18000b92f  mov     edx, 66h ; 'f'; void *
0x18000b934  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b939  mov     rcx, [rbp+188h]; this
0x18000b940  lea     r8, aWil; "wil"
0x18000b947  mov     r9d, esi; char *
0x18000b94a  mov     edx, 6Fh ; 'o'; void *
0x18000b94f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b954  mov     rcx, [rbp+188h]; this
0x18000b95b  lea     r8, aWil; "wil"
0x18000b962  mov     r9d, esi; char *
0x18000b965  mov     edx, 12Eh; void *
0x18000b96a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b96f  test    rdi, rdi
0x18000b972  jz      short loc_18000B985
0x18000b974  mov     rcx, rdi; hMutex
0x18000b977  call    cs:__imp_ReleaseMutex
0x18000b97d  test    eax, eax
0x18000b97f  jz      loc_18000BB96
0x18000b985  mov     rcx, rbx; hObject
0x18000b988  call    cs:__imp_CloseHandle
0x18000b98e  test    eax, eax
0x18000b990  jz      loc_18000BBAF
0x18000b996  mov     eax, esi
0x18000b998  jmp     loc_18000BB45
0x18000b99d  mov     rax, [rsp+280h+var_250]
0x18000b9a2  lea     rcx, ds:0[rax*4]
0x18000b9aa  test    rcx, rcx
0x18000b9ad  jz      short loc_18000B9BD
0x18000b9af  mov     [r15], rcx
0x18000b9b2  mov     eax, [rcx]
0x18000b9b4  inc     eax
0x18000b9b6  mov     [rcx], eax
0x18000b9b8  jmp     loc_18000BB1B
0x18000b9bd  mov     rdx, r14; dwBytes
0x18000b9c0  mov     qword ptr [r15], 0
0x18000b9c7  mov     ecx, 8; dwFlags
0x18000b9cc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b9d1  mov     rsi, rax
0x18000b9d4  test    rax, rax
0x18000b9d7  jnz     short loc_18000B9FC
0x18000b9d9  mov     rcx, [rbp+188h]; this
0x18000b9e0  lea     r8, aWil; "wil"
0x18000b9e7  mov     r14d, 8007000Eh
0x18000b9ed  mov     edx, 14Bh; void *
0x18000b9f2  mov     r9d, r14d; char *
0x18000b9f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9fa  jmp     short loc_18000BA69
0x18000b9fc  xorps   xmm0, xmm0
0x18000b9ff  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000ba05  test    sil, 3
0x18000ba09  jnz     loc_18000BBC8
0x18000ba0f  mov     r9, rsi
0x18000ba12  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000ba17  shr     r9, 2; unsigned __int64
0x18000ba1b  lea     rcx, [rsp+280h+var_250]; this
0x18000ba20  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000ba25  mov     r14d, eax
0x18000ba28  test    eax, eax
0x18000ba2a  jns     loc_18000BAB3
0x18000ba30  mov     rcx, [rbp+188h]; this
0x18000ba37  lea     r8, aWil; "wil"
0x18000ba3e  mov     r9d, eax; char *
0x18000ba41  mov     edx, 14Eh; void *
0x18000ba46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba4b  lea     rcx, [rsp+280h+var_250]; this
0x18000ba50  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ba55  call    cs:__imp_GetProcessHeap
0x18000ba5b  mov     r8, rsi; lpMem
0x18000ba5e  xor     edx, edx; dwFlags
0x18000ba60  mov     rcx, rax; hHeap
0x18000ba63  call    cs:__imp_HeapFree
0x18000ba69  mov     rcx, [rbp+188h]; this
0x18000ba70  lea     r8, aWil; "wil"
0x18000ba77  mov     r9d, r14d; char *
0x18000ba7a  mov     edx, 137h; void *
0x18000ba7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba84  test    rdi, rdi
0x18000ba87  jz      short loc_18000BA9A
0x18000ba89  mov     rcx, rdi; hMutex
0x18000ba8c  call    cs:__imp_ReleaseMutex
0x18000ba92  test    eax, eax
0x18000ba94  jz      loc_18000BBCE
0x18000ba9a  mov     rcx, rbx; hObject
0x18000ba9d  call    cs:__imp_CloseHandle
0x18000baa3  test    eax, eax
0x18000baa5  jz      loc_18000BBE7
0x18000baab  mov     eax, r14d
0x18000baae  jmp     loc_18000BB45
0x18000bab3  mov     rax, [rsp+280h+var_250]
0x18000bab8  lea     rcx, [rsi+22h]; void *
0x18000babc  xor     edx, edx; Val
0x18000babe  mov     [rsi+10h], rax
0x18000bac2  mov     rax, [rsp+280h+var_250+8]
0x18000bac7  mov     dword ptr [rsi], 1
0x18000bacd  mov     [rsi+8], rbx
0x18000bad1  lea     r8d, [rdx+56h]; Size
0x18000bad5  mov     [rsp+280h+var_250], 0
0x18000bade  mov     [rsi+18h], rax
0x18000bae2  mov     [rsp+280h+var_250+8], 0
0x18000baeb  call    memset_0
0x18000baf0  xor     edx, edx; Val
0x18000baf2  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000baf8  lea     rcx, [rsi+28h]; void *
0x18000bafc  mov     dword ptr [rsi+24h], 1
0x18000bb03  lea     r8d, [rdx+50h]; Size
0x18000bb07  call    memset_0
0x18000bb0c  lea     rcx, [rsp+280h+var_250]; this
0x18000bb11  mov     [r15], rsi
0x18000bb14  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000bb19  xor     ebx, ebx
0x18000bb1b  test    rdi, rdi
0x18000bb1e  jz      short loc_18000BB31
0x18000bb20  mov     rcx, rdi; hMutex
0x18000bb23  call    cs:__imp_ReleaseMutex
0x18000bb29  test    eax, eax
0x18000bb2b  jz      loc_18000BC00
0x18000bb31  test    rbx, rbx
0x18000bb34  jz      short loc_18000BB43
0x18000bb36  mov     rcx, rbx; hObject
0x18000bb39  call    cs:__imp_CloseHandle
0x18000bb3f  test    eax, eax
0x18000bb41  jz      short loc_18000BB6B
0x18000bb43  xor     eax, eax
0x18000bb45  mov     rcx, [rbp+180h+var_30]
0x18000bb4c  xor     rcx, rsp; StackCookie
0x18000bb4f  call    __security_check_cookie
0x18000bb54  mov     rbx, [rsp+280h+arg_10]
0x18000bb5c  add     rsp, 260h
0x18000bb63  pop     r15
0x18000bb65  pop     r14
0x18000bb67  pop     rdi
0x18000bb68  pop     rsi
0x18000bb69  pop     rbp
0x18000bb6a  retn
0x18000bb6b  mov     rcx, [rbp+188h]; this
0x18000bb72  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bb79  mov     edx, 0A0Bh; void *
0x18000bb7e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bb84  mov     rcx, [rbp+188h]; this
0x18000bb8b  mov     edx, 0E01h; void *
0x18000bb90  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000bb96  mov     rcx, [rbp+188h]; this
0x18000bb9d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bba4  mov     edx, 0A15h; void *
0x18000bba9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bbaf  mov     rcx, [rbp+188h]; this
0x18000bbb6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bbbd  mov     edx, 0A0Bh; void *
0x18000bbc2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bbc8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000bbce  mov     rcx, [rbp+188h]; this
0x18000bbd5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bbdc  mov     edx, 0A15h; void *
0x18000bbe1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bbe7  mov     rcx, [rbp+188h]; this
0x18000bbee  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bbf5  mov     edx, 0A0Bh; void *
0x18000bbfa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bc00  mov     rcx, [rbp+188h]; this
0x18000bc07  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bc0e  mov     edx, 0A15h; void *
0x18000bc13  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
