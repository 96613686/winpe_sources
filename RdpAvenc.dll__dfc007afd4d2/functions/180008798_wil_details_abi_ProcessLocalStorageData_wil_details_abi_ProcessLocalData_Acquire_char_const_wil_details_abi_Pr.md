# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008798`
- end: `0x180008b6c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800095f0`

## callees

- `0x180006580`
- `0x180007018`
- `0x180008798`
- `0x180008b74`
- `0x180008dc0`
- `0x180009388`
- `0x180009d44`
- `0x18000a1b4`
- `0x18000abb8`
- `0x18000ac9c`
- `0x18000b06c`
- `0x18000b07c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800088c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a05`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800088c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a05`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a75`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008831`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008831`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008810`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008810`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800087d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800087d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a8b`

## string_xrefs

- `0x180008ad6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v35 = *(_OWORD *)hObject;
      *(_DWORD *)v23 = 1;
      v23[1] = v6;
      *((_OWORD *)v23 + 1) = v35;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v23;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v24, v42);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v24;
}

```

## disassembly

```asm
0x180008798  mov     [rsp-8+arg_10], rbx
0x18000879d  push    rbp
0x18000879e  push    rsi
0x18000879f  push    rdi
0x1800087a0  push    r14
0x1800087a2  push    r15
0x1800087a4  lea     rbp, [rsp-160h]
0x1800087ac  sub     rsp, 260h
0x1800087b3  mov     rax, cs:__security_cookie
0x1800087ba  xor     rax, rsp
0x1800087bd  mov     [rbp+180h+var_30], rax
0x1800087c4  mov     r15, rdx
0x1800087c7  mov     qword ptr [rdx], 0
0x1800087ce  mov     rbx, rcx
0x1800087d1  call    cs:__imp_GetCurrentProcessId
0x1800087d7  mov     r14d, 78h ; 'x'
0x1800087dd  mov     [rsp+280h+var_258], rbx
0x1800087e2  mov     r9d, eax
0x1800087e5  mov     [rsp+280h+var_260], r14d; int
0x1800087ea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800087f1  mov     edx, 104h; unsigned __int64
0x1800087f6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800087fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008800  mov     r9d, 1F0001h; dwDesiredAccess
0x180008806  lea     rdx, [rsp+280h+Name]; lpName
0x18000880b  xor     r8d, r8d; dwFlags
0x18000880e  xor     ecx, ecx; lpMutexAttributes
0x180008810  call    cs:__imp_CreateMutexExW
0x180008816  mov     rbx, rax
0x180008819  test    rax, rax
0x18000881c  jnz     short loc_180008828
0x18000881e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008823  jmp     loc_180008A97
0x180008828  xor     r8d, r8d; bAlertable
0x18000882b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000882e  mov     rcx, rbx; hHandle
0x180008831  call    cs:__imp_WaitForSingleObjectEx
0x180008837  cmp     eax, 102h
0x18000883c  jz      short loc_18000884E
0x18000883e  test    eax, 0FFFFFF7Fh
0x180008843  jnz     loc_180008ACF
0x180008849  mov     rdi, rbx
0x18000884c  jmp     short loc_180008850
0x18000884e  xor     edi, edi
0x180008850  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008855  mov     [rsp+280h+hObject], 0
0x18000885e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008863  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008868  mov     esi, eax
0x18000886a  test    eax, eax
0x18000886c  jns     short loc_1800088ED
0x18000886e  mov     rcx, [rbp+188h]; this
0x180008875  lea     r8, aWil; "wil"
0x18000887c  mov     r9d, eax; char *
0x18000887f  mov     edx, 66h ; 'f'; void *
0x180008884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008889  mov     rcx, [rbp+188h]; this
0x180008890  lea     r8, aWil; "wil"
0x180008897  mov     r9d, esi; char *
0x18000889a  mov     edx, 6Fh ; 'o'; void *
0x18000889f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088a4  mov     rcx, [rbp+188h]; this
0x1800088ab  lea     r8, aWil; "wil"
0x1800088b2  mov     r9d, esi; char *
0x1800088b5  mov     edx, 12Eh; void *
0x1800088ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088bf  test    rdi, rdi
0x1800088c2  jz      short loc_1800088D5
0x1800088c4  mov     rcx, rdi; hMutex
0x1800088c7  call    cs:__imp_ReleaseMutex
0x1800088cd  test    eax, eax
0x1800088cf  jz      loc_180008AE8
0x1800088d5  mov     rcx, rbx; hObject
0x1800088d8  call    cs:__imp_CloseHandle
0x1800088de  test    eax, eax
0x1800088e0  jz      loc_180008AFA
0x1800088e6  mov     eax, esi
0x1800088e8  jmp     loc_180008A97
0x1800088ed  mov     rax, [rsp+280h+hObject]
0x1800088f2  lea     rcx, ds:0[rax*4]
0x1800088fa  test    rcx, rcx
0x1800088fd  jz      short loc_18000890D
0x1800088ff  mov     [r15], rcx
0x180008902  mov     eax, [rcx]
0x180008904  inc     eax
0x180008906  mov     [rcx], eax
0x180008908  jmp     loc_180008A6D
0x18000890d  mov     rdx, r14; dwBytes
0x180008910  mov     qword ptr [r15], 0
0x180008917  mov     ecx, 8; dwFlags
0x18000891c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008921  mov     rsi, rax
0x180008924  test    rax, rax
0x180008927  jnz     short loc_18000894F
0x180008929  mov     rcx, [rbp+188h]; this
0x180008930  lea     r8, aWil; "wil"
0x180008937  mov     r14d, 8007000Eh
0x18000893d  mov     edx, 14Bh; void *
0x180008942  mov     r9d, r14d; char *
0x180008945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000894a  jmp     loc_1800089E2
0x18000894f  xorps   xmm0, xmm0
0x180008952  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180008958  test    sil, 3
0x18000895c  jnz     loc_180008B0C
0x180008962  mov     r9, rsi
0x180008965  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000896a  shr     r9, 2; unsigned __int64
0x18000896e  lea     rcx, [rsp+280h+hObject]; this
0x180008973  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180008978  mov     r14d, eax
0x18000897b  test    eax, eax
0x18000897d  jns     loc_180008A29
0x180008983  mov     rcx, [rbp+188h]; this
0x18000898a  lea     r8, aWil; "wil"
0x180008991  mov     r9d, eax; char *
0x180008994  mov     edx, 14Eh; void *
0x180008999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000899e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800089a3  test    rcx, rcx
0x1800089a6  jz      short loc_1800089B6
0x1800089a8  call    cs:__imp_CloseHandle
0x1800089ae  test    eax, eax
0x1800089b0  jz      loc_180008B12
0x1800089b6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800089bb  test    rcx, rcx
0x1800089be  jz      short loc_1800089CE
0x1800089c0  call    cs:__imp_CloseHandle
0x1800089c6  test    eax, eax
0x1800089c8  jz      loc_180008B24
0x1800089ce  call    cs:__imp_GetProcessHeap
0x1800089d4  mov     r8, rsi; lpMem
0x1800089d7  xor     edx, edx; dwFlags
0x1800089d9  mov     rcx, rax; hHeap
0x1800089dc  call    cs:__imp_HeapFree
0x1800089e2  mov     rcx, [rbp+188h]; this
0x1800089e9  lea     r8, aWil; "wil"
0x1800089f0  mov     r9d, r14d; char *
0x1800089f3  mov     edx, 137h; void *
0x1800089f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089fd  test    rdi, rdi
0x180008a00  jz      short loc_180008A13
0x180008a02  mov     rcx, rdi; hMutex
0x180008a05  call    cs:__imp_ReleaseMutex
0x180008a0b  test    eax, eax
0x180008a0d  jz      loc_180008B36
0x180008a13  mov     rcx, rbx; hObject
0x180008a16  call    cs:__imp_CloseHandle
0x180008a1c  test    eax, eax
0x180008a1e  jz      loc_180008B48
0x180008a24  mov     eax, r14d
0x180008a27  jmp     short loc_180008A97
0x180008a29  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008a2e  xor     edx, edx; Val
0x180008a30  mov     dword ptr [rsi], 1
0x180008a36  lea     rcx, [rsi+22h]; void *
0x180008a3a  mov     [rsi+8], rbx
0x180008a3e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180008a43  lea     r8d, [rdx+56h]; Size
0x180008a47  call    memset_0
0x180008a4c  xor     edx, edx; Val
0x180008a4e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180008a54  lea     rcx, [rsi+28h]; void *
0x180008a58  mov     dword ptr [rsi+24h], 1
0x180008a5f  lea     r8d, [rdx+50h]; Size
0x180008a63  call    memset_0
0x180008a68  xor     ebx, ebx
0x180008a6a  mov     [r15], rsi
0x180008a6d  test    rdi, rdi
0x180008a70  jz      short loc_180008A83
0x180008a72  mov     rcx, rdi; hMutex
0x180008a75  call    cs:__imp_ReleaseMutex
0x180008a7b  test    eax, eax
0x180008a7d  jz      loc_180008B5A
0x180008a83  test    rbx, rbx
0x180008a86  jz      short loc_180008A95
0x180008a88  mov     rcx, rbx; hObject
0x180008a8b  call    cs:__imp_CloseHandle
0x180008a91  test    eax, eax
0x180008a93  jz      short loc_180008ABD
0x180008a95  xor     eax, eax
0x180008a97  mov     rcx, [rbp+180h+var_30]
0x180008a9e  xor     rcx, rsp; StackCookie
0x180008aa1  call    __security_check_cookie
0x180008aa6  mov     rbx, [rsp+280h+arg_10]
0x180008aae  add     rsp, 260h
0x180008ab5  pop     r15
0x180008ab7  pop     r14
0x180008ab9  pop     rdi
0x180008aba  pop     rsi
0x180008abb  pop     rbp
0x180008abc  retn
0x180008abd  mov     rcx, [rbp+188h]; this
0x180008ac4  mov     edx, 0A0Bh; void *
0x180008ac9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008acf  mov     rcx, [rbp+188h]; this
0x180008ad6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008add  mov     edx, 0E01h; void *
0x180008ae2  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008ae8  mov     rcx, [rbp+188h]; this
0x180008aef  mov     edx, 0A15h; void *
0x180008af4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008afa  mov     rcx, [rbp+188h]; this
0x180008b01  mov     edx, 0A0Bh; void *
0x180008b06  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b0c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008b12  mov     rcx, [rbp+188h]; this
0x180008b19  mov     edx, 0A0Bh; void *
0x180008b1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b24  mov     rcx, [rbp+188h]; this
0x180008b2b  mov     edx, 0A0Bh; void *
0x180008b30  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b36  mov     rcx, [rbp+188h]; this
0x180008b3d  mov     edx, 0A15h; void *
0x180008b42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b48  mov     rcx, [rbp+188h]; this
0x180008b4f  mov     edx, 0A0Bh; void *
0x180008b54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b5a  mov     rcx, [rbp+188h]; this
0x180008b61  mov     edx, 0A15h; void *
0x180008b66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
