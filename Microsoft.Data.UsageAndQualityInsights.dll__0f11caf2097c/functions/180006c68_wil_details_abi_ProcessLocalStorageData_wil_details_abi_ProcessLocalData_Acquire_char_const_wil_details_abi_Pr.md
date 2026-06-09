# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006c68`
- end: `0x180007040`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800085d4`

## callees

- `0x1800033d0`
- `0x180003fb8`
- `0x180006878`
- `0x180006c68`
- `0x18000744c`
- `0x1800079a4`
- `0x1800082c8`
- `0x180009058`
- `0x18000a894`
- `0x18000b394`
- `0x18000b81c`
- `0x18000c258`
- `0x18000c268`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006d01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006d01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006d97`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006eac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006f43`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006d97`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006eac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006f43`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006ce0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006ce0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ca1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ca1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f59`

## string_xrefs

- `0x180006f92`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006fab`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006fc4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006fdd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006ffc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007015`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000702e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rcx
  unsigned __int64 v18; // rax
  wil::details::in1diag3 *v19; // rcx
  bool v20; // r8
  _QWORD *v21; // rsi
  unsigned int v22; // r14d
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  unsigned __int64 v27; // rax
  const char *v28; // r9
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v33[2]; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v33[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v33, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v30);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v31);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    return v14;
  }
  v17 = (_DWORD *)(4 * v33[0]);
  if ( 4 * v33[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v21 = (_QWORD *)v18;
  if ( v18 )
  {
    *(_OWORD *)v33 = 0;
    if ( (v18 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
    v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v33,
            Name,
            v20,
            v18 >> 2);
    v22 = v23;
    if ( v23 >= 0 )
    {
      v21[2] = v33[0];
      v27 = v33[1];
      *(_DWORD *)v21 = 1;
      v21[1] = v6;
      v33[0] = 0;
      v21[3] = v27;
      v33[1] = 0;
      memset_0((char *)v21 + 34, 0, 0x56u);
      *((_WORD *)v21 + 16) = 88;
      *((_DWORD *)v21 + 9) = 1;
      memset_0(v21 + 5, 0, 0x50u);
      *a2 = v21;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
      v6 = 0;
LABEL_24:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  else
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v22, v32);
  if ( v11 && !ReleaseMutex(v11) )
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
  return v22;
}

```

## disassembly

```asm
0x180006c68  mov     [rsp-8+arg_10], rbx
0x180006c6d  push    rbp
0x180006c6e  push    rsi
0x180006c6f  push    rdi
0x180006c70  push    r14
0x180006c72  push    r15
0x180006c74  lea     rbp, [rsp-160h]
0x180006c7c  sub     rsp, 260h
0x180006c83  mov     rax, cs:__security_cookie
0x180006c8a  xor     rax, rsp
0x180006c8d  mov     [rbp+180h+var_30], rax
0x180006c94  mov     r15, rdx
0x180006c97  mov     qword ptr [rdx], 0
0x180006c9e  mov     rbx, rcx
0x180006ca1  call    cs:__imp_GetCurrentProcessId
0x180006ca7  mov     r14d, 78h ; 'x'
0x180006cad  mov     [rsp+280h+var_258], rbx
0x180006cb2  mov     r9d, eax
0x180006cb5  mov     [rsp+280h+var_260], r14d; int
0x180006cba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006cc1  mov     edx, 104h; unsigned __int64
0x180006cc6  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180006ccb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180006cd0  mov     r9d, 1F0001h; dwDesiredAccess
0x180006cd6  lea     rdx, [rsp+280h+Name]; lpName
0x180006cdb  xor     r8d, r8d; dwFlags
0x180006cde  xor     ecx, ecx; lpMutexAttributes
0x180006ce0  call    cs:__imp_CreateMutexExW
0x180006ce6  mov     rbx, rax
0x180006ce9  test    rax, rax
0x180006cec  jnz     short loc_180006CF8
0x180006cee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006cf3  jmp     loc_180006F65
0x180006cf8  xor     r8d, r8d; bAlertable
0x180006cfb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006cfe  mov     rcx, rbx; hHandle
0x180006d01  call    cs:__imp_WaitForSingleObjectEx
0x180006d07  cmp     eax, 102h
0x180006d0c  jz      short loc_180006D1E
0x180006d0e  test    eax, 0FFFFFF7Fh
0x180006d13  jnz     loc_180006FA4
0x180006d19  mov     rdi, rbx
0x180006d1c  jmp     short loc_180006D20
0x180006d1e  xor     edi, edi
0x180006d20  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180006d25  mov     [rsp+280h+var_250], 0
0x180006d2e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180006d33  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180006d38  mov     esi, eax
0x180006d3a  test    eax, eax
0x180006d3c  jns     short loc_180006DBD
0x180006d3e  mov     rcx, [rbp+188h]; this
0x180006d45  lea     r8, aWil; "wil"
0x180006d4c  mov     r9d, eax; char *
0x180006d4f  mov     edx, 66h ; 'f'; void *
0x180006d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d59  mov     rcx, [rbp+188h]; this
0x180006d60  lea     r8, aWil; "wil"
0x180006d67  mov     r9d, esi; char *
0x180006d6a  mov     edx, 6Fh ; 'o'; void *
0x180006d6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d74  mov     rcx, [rbp+188h]; this
0x180006d7b  lea     r8, aWil; "wil"
0x180006d82  mov     r9d, esi; char *
0x180006d85  mov     edx, 12Eh; void *
0x180006d8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d8f  test    rdi, rdi
0x180006d92  jz      short loc_180006DA5
0x180006d94  mov     rcx, rdi; hMutex
0x180006d97  call    cs:__imp_ReleaseMutex
0x180006d9d  test    eax, eax
0x180006d9f  jz      loc_180006FBD
0x180006da5  mov     rcx, rbx; hObject
0x180006da8  call    cs:__imp_CloseHandle
0x180006dae  test    eax, eax
0x180006db0  jz      loc_180006FD6
0x180006db6  mov     eax, esi
0x180006db8  jmp     loc_180006F65
0x180006dbd  mov     rax, [rsp+280h+var_250]
0x180006dc2  lea     rcx, ds:0[rax*4]
0x180006dca  test    rcx, rcx
0x180006dcd  jz      short loc_180006DDD
0x180006dcf  mov     [r15], rcx
0x180006dd2  mov     eax, [rcx]
0x180006dd4  inc     eax
0x180006dd6  mov     [rcx], eax
0x180006dd8  jmp     loc_180006F3B
0x180006ddd  mov     rdx, r14; dwBytes
0x180006de0  mov     qword ptr [r15], 0
0x180006de7  mov     ecx, 8; dwFlags
0x180006dec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006df1  mov     rsi, rax
0x180006df4  test    rax, rax
0x180006df7  jnz     short loc_180006E1C
0x180006df9  mov     rcx, [rbp+188h]; this
0x180006e00  lea     r8, aWil; "wil"
0x180006e07  mov     r14d, 8007000Eh
0x180006e0d  mov     edx, 14Bh; void *
0x180006e12  mov     r9d, r14d; char *
0x180006e15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e1a  jmp     short loc_180006E89
0x180006e1c  xorps   xmm0, xmm0
0x180006e1f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180006e25  test    sil, 3
0x180006e29  jnz     loc_180006FEF
0x180006e2f  mov     r9, rsi
0x180006e32  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180006e37  shr     r9, 2; unsigned __int64
0x180006e3b  lea     rcx, [rsp+280h+var_250]; this
0x180006e40  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180006e45  mov     r14d, eax
0x180006e48  test    eax, eax
0x180006e4a  jns     loc_180006ED3
0x180006e50  mov     rcx, [rbp+188h]; this
0x180006e57  lea     r8, aWil; "wil"
0x180006e5e  mov     r9d, eax; char *
0x180006e61  mov     edx, 14Eh; void *
0x180006e66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e6b  lea     rcx, [rsp+280h+var_250]; this
0x180006e70  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180006e75  call    cs:__imp_GetProcessHeap
0x180006e7b  mov     r8, rsi; lpMem
0x180006e7e  xor     edx, edx; dwFlags
0x180006e80  mov     rcx, rax; hHeap
0x180006e83  call    cs:__imp_HeapFree
0x180006e89  mov     rcx, [rbp+188h]; this
0x180006e90  lea     r8, aWil; "wil"
0x180006e97  mov     r9d, r14d; char *
0x180006e9a  mov     edx, 137h; void *
0x180006e9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ea4  test    rdi, rdi
0x180006ea7  jz      short loc_180006EBA
0x180006ea9  mov     rcx, rdi; hMutex
0x180006eac  call    cs:__imp_ReleaseMutex
0x180006eb2  test    eax, eax
0x180006eb4  jz      loc_180006FF5
0x180006eba  mov     rcx, rbx; hObject
0x180006ebd  call    cs:__imp_CloseHandle
0x180006ec3  test    eax, eax
0x180006ec5  jz      loc_18000700E
0x180006ecb  mov     eax, r14d
0x180006ece  jmp     loc_180006F65
0x180006ed3  mov     rax, [rsp+280h+var_250]
0x180006ed8  lea     rcx, [rsi+22h]; void *
0x180006edc  xor     edx, edx; Val
0x180006ede  mov     [rsi+10h], rax
0x180006ee2  mov     rax, [rsp+280h+var_250+8]
0x180006ee7  mov     dword ptr [rsi], 1
0x180006eed  mov     [rsi+8], rbx
0x180006ef1  lea     r8d, [rdx+56h]; Size
0x180006ef5  mov     [rsp+280h+var_250], 0
0x180006efe  mov     [rsi+18h], rax
0x180006f02  mov     [rsp+280h+var_250+8], 0
0x180006f0b  call    memset_0
0x180006f10  xor     edx, edx; Val
0x180006f12  mov     word ptr [rsi+20h], 58h ; 'X'
0x180006f18  lea     rcx, [rsi+28h]; void *
0x180006f1c  mov     dword ptr [rsi+24h], 1
0x180006f23  lea     r8d, [rdx+50h]; Size
0x180006f27  call    memset_0
0x180006f2c  lea     rcx, [rsp+280h+var_250]; this
0x180006f31  mov     [r15], rsi
0x180006f34  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180006f39  xor     ebx, ebx
0x180006f3b  test    rdi, rdi
0x180006f3e  jz      short loc_180006F51
0x180006f40  mov     rcx, rdi; hMutex
0x180006f43  call    cs:__imp_ReleaseMutex
0x180006f49  test    eax, eax
0x180006f4b  jz      loc_180007027
0x180006f51  test    rbx, rbx
0x180006f54  jz      short loc_180006F63
0x180006f56  mov     rcx, rbx; hObject
0x180006f59  call    cs:__imp_CloseHandle
0x180006f5f  test    eax, eax
0x180006f61  jz      short loc_180006F8B
0x180006f63  xor     eax, eax
0x180006f65  mov     rcx, [rbp+180h+var_30]
0x180006f6c  xor     rcx, rsp; StackCookie
0x180006f6f  call    __security_check_cookie
0x180006f74  mov     rbx, [rsp+280h+arg_10]
0x180006f7c  add     rsp, 260h
0x180006f83  pop     r15
0x180006f85  pop     r14
0x180006f87  pop     rdi
0x180006f88  pop     rsi
0x180006f89  pop     rbp
0x180006f8a  retn
0x180006f8b  mov     rcx, [rbp+188h]; this
0x180006f92  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006f99  mov     edx, 0A0Bh; void *
0x180006f9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fa4  mov     rcx, [rbp+188h]; this
0x180006fab  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006fb2  mov     edx, 0E01h; void *
0x180006fb7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006fbd  mov     rcx, [rbp+188h]; this
0x180006fc4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006fcb  mov     edx, 0A15h; void *
0x180006fd0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fd6  mov     rcx, [rbp+188h]; this
0x180006fdd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006fe4  mov     edx, 0A0Bh; void *
0x180006fe9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fef  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006ff5  mov     rcx, [rbp+188h]; this
0x180006ffc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007003  mov     edx, 0A15h; void *
0x180007008  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000700e  mov     rcx, [rbp+188h]; this
0x180007015  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000701c  mov     edx, 0A0Bh; void *
0x180007021  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007027  mov     rcx, [rbp+188h]; this
0x18000702e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007035  mov     edx, 0A15h; void *
0x18000703a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
