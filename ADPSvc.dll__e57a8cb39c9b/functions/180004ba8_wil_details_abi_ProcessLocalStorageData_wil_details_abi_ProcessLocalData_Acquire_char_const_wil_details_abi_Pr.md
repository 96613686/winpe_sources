# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004ba8`
- end: `0x180004f80`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180005b50`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x18000494c`
- `0x180004ba8`
- `0x180004f88`
- `0x180005290`
- `0x1800058e8`
- `0x1800063c8`
- `0x180006844`
- `0x180007234`
- `0x18000730c`
- `0x18000770c`
- `0x18000771c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004cd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004dec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004cd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004dec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e83`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004c41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004c41`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004c20`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004c20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004db5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004db5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004dc3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004dc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004be1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004be1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ce8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ce8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e99`

## string_xrefs

- `0x180004ed2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004eeb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004f04`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004f1d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004f3c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004f55`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004f6e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180004ba8  mov     [rsp-8+arg_10], rbx
0x180004bad  push    rbp
0x180004bae  push    rsi
0x180004baf  push    rdi
0x180004bb0  push    r14
0x180004bb2  push    r15
0x180004bb4  lea     rbp, [rsp-160h]
0x180004bbc  sub     rsp, 260h
0x180004bc3  mov     rax, cs:__security_cookie
0x180004bca  xor     rax, rsp
0x180004bcd  mov     [rbp+180h+var_30], rax
0x180004bd4  mov     r15, rdx
0x180004bd7  mov     qword ptr [rdx], 0
0x180004bde  mov     rbx, rcx
0x180004be1  call    cs:__imp_GetCurrentProcessId
0x180004be7  mov     r14d, 78h ; 'x'
0x180004bed  mov     [rsp+280h+var_258], rbx
0x180004bf2  mov     r9d, eax
0x180004bf5  mov     [rsp+280h+var_260], r14d; int
0x180004bfa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004c01  mov     edx, 104h; unsigned __int64
0x180004c06  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180004c0b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004c10  mov     r9d, 1F0001h; dwDesiredAccess
0x180004c16  lea     rdx, [rsp+280h+Name]; lpName
0x180004c1b  xor     r8d, r8d; dwFlags
0x180004c1e  xor     ecx, ecx; lpMutexAttributes
0x180004c20  call    cs:__imp_CreateMutexExW
0x180004c26  mov     rbx, rax
0x180004c29  test    rax, rax
0x180004c2c  jnz     short loc_180004C38
0x180004c2e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004c33  jmp     loc_180004EA5
0x180004c38  xor     r8d, r8d; bAlertable
0x180004c3b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004c3e  mov     rcx, rbx; hHandle
0x180004c41  call    cs:__imp_WaitForSingleObjectEx
0x180004c47  cmp     eax, 102h
0x180004c4c  jz      short loc_180004C5E
0x180004c4e  test    eax, 0FFFFFF7Fh
0x180004c53  jnz     loc_180004EE4
0x180004c59  mov     rdi, rbx
0x180004c5c  jmp     short loc_180004C60
0x180004c5e  xor     edi, edi
0x180004c60  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180004c65  mov     [rsp+280h+var_250], 0
0x180004c6e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180004c73  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180004c78  mov     esi, eax
0x180004c7a  test    eax, eax
0x180004c7c  jns     short loc_180004CFD
0x180004c7e  mov     rcx, [rbp+188h]; this
0x180004c85  lea     r8, aWil; "wil"
0x180004c8c  mov     r9d, eax; char *
0x180004c8f  mov     edx, 66h ; 'f'; void *
0x180004c94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c99  mov     rcx, [rbp+188h]; this
0x180004ca0  lea     r8, aWil; "wil"
0x180004ca7  mov     r9d, esi; char *
0x180004caa  mov     edx, 6Fh ; 'o'; void *
0x180004caf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004cb4  mov     rcx, [rbp+188h]; this
0x180004cbb  lea     r8, aWil; "wil"
0x180004cc2  mov     r9d, esi; char *
0x180004cc5  mov     edx, 12Eh; void *
0x180004cca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ccf  test    rdi, rdi
0x180004cd2  jz      short loc_180004CE5
0x180004cd4  mov     rcx, rdi; hMutex
0x180004cd7  call    cs:__imp_ReleaseMutex
0x180004cdd  test    eax, eax
0x180004cdf  jz      loc_180004EFD
0x180004ce5  mov     rcx, rbx; hObject
0x180004ce8  call    cs:__imp_CloseHandle
0x180004cee  test    eax, eax
0x180004cf0  jz      loc_180004F16
0x180004cf6  mov     eax, esi
0x180004cf8  jmp     loc_180004EA5
0x180004cfd  mov     rax, [rsp+280h+var_250]
0x180004d02  lea     rcx, ds:0[rax*4]
0x180004d0a  test    rcx, rcx
0x180004d0d  jz      short loc_180004D1D
0x180004d0f  mov     [r15], rcx
0x180004d12  mov     eax, [rcx]
0x180004d14  inc     eax
0x180004d16  mov     [rcx], eax
0x180004d18  jmp     loc_180004E7B
0x180004d1d  mov     rdx, r14; dwBytes
0x180004d20  mov     qword ptr [r15], 0
0x180004d27  mov     ecx, 8; dwFlags
0x180004d2c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004d31  mov     rsi, rax
0x180004d34  test    rax, rax
0x180004d37  jnz     short loc_180004D5C
0x180004d39  mov     rcx, [rbp+188h]; this
0x180004d40  lea     r8, aWil; "wil"
0x180004d47  mov     r14d, 8007000Eh
0x180004d4d  mov     edx, 14Bh; void *
0x180004d52  mov     r9d, r14d; char *
0x180004d55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d5a  jmp     short loc_180004DC9
0x180004d5c  xorps   xmm0, xmm0
0x180004d5f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180004d65  test    sil, 3
0x180004d69  jnz     loc_180004F2F
0x180004d6f  mov     r9, rsi
0x180004d72  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180004d77  shr     r9, 2; unsigned __int64
0x180004d7b  lea     rcx, [rsp+280h+var_250]; this
0x180004d80  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180004d85  mov     r14d, eax
0x180004d88  test    eax, eax
0x180004d8a  jns     loc_180004E13
0x180004d90  mov     rcx, [rbp+188h]; this
0x180004d97  lea     r8, aWil; "wil"
0x180004d9e  mov     r9d, eax; char *
0x180004da1  mov     edx, 14Eh; void *
0x180004da6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dab  lea     rcx, [rsp+280h+var_250]; this
0x180004db0  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180004db5  call    cs:__imp_GetProcessHeap
0x180004dbb  mov     r8, rsi; lpMem
0x180004dbe  xor     edx, edx; dwFlags
0x180004dc0  mov     rcx, rax; hHeap
0x180004dc3  call    cs:__imp_HeapFree
0x180004dc9  mov     rcx, [rbp+188h]; this
0x180004dd0  lea     r8, aWil; "wil"
0x180004dd7  mov     r9d, r14d; char *
0x180004dda  mov     edx, 137h; void *
0x180004ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004de4  test    rdi, rdi
0x180004de7  jz      short loc_180004DFA
0x180004de9  mov     rcx, rdi; hMutex
0x180004dec  call    cs:__imp_ReleaseMutex
0x180004df2  test    eax, eax
0x180004df4  jz      loc_180004F35
0x180004dfa  mov     rcx, rbx; hObject
0x180004dfd  call    cs:__imp_CloseHandle
0x180004e03  test    eax, eax
0x180004e05  jz      loc_180004F4E
0x180004e0b  mov     eax, r14d
0x180004e0e  jmp     loc_180004EA5
0x180004e13  mov     rax, [rsp+280h+var_250]
0x180004e18  lea     rcx, [rsi+22h]; void *
0x180004e1c  xor     edx, edx; Val
0x180004e1e  mov     [rsi+10h], rax
0x180004e22  mov     rax, [rsp+280h+var_250+8]
0x180004e27  mov     dword ptr [rsi], 1
0x180004e2d  mov     [rsi+8], rbx
0x180004e31  lea     r8d, [rdx+56h]; Size
0x180004e35  mov     [rsp+280h+var_250], 0
0x180004e3e  mov     [rsi+18h], rax
0x180004e42  mov     [rsp+280h+var_250+8], 0
0x180004e4b  call    memset_0
0x180004e50  xor     edx, edx; Val
0x180004e52  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004e58  lea     rcx, [rsi+28h]; void *
0x180004e5c  mov     dword ptr [rsi+24h], 1
0x180004e63  lea     r8d, [rdx+50h]; Size
0x180004e67  call    memset_0
0x180004e6c  lea     rcx, [rsp+280h+var_250]; this
0x180004e71  mov     [r15], rsi
0x180004e74  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180004e79  xor     ebx, ebx
0x180004e7b  test    rdi, rdi
0x180004e7e  jz      short loc_180004E91
0x180004e80  mov     rcx, rdi; hMutex
0x180004e83  call    cs:__imp_ReleaseMutex
0x180004e89  test    eax, eax
0x180004e8b  jz      loc_180004F67
0x180004e91  test    rbx, rbx
0x180004e94  jz      short loc_180004EA3
0x180004e96  mov     rcx, rbx; hObject
0x180004e99  call    cs:__imp_CloseHandle
0x180004e9f  test    eax, eax
0x180004ea1  jz      short loc_180004ECB
0x180004ea3  xor     eax, eax
0x180004ea5  mov     rcx, [rbp+180h+var_30]
0x180004eac  xor     rcx, rsp; StackCookie
0x180004eaf  call    __security_check_cookie
0x180004eb4  mov     rbx, [rsp+280h+arg_10]
0x180004ebc  add     rsp, 260h
0x180004ec3  pop     r15
0x180004ec5  pop     r14
0x180004ec7  pop     rdi
0x180004ec8  pop     rsi
0x180004ec9  pop     rbp
0x180004eca  retn
0x180004ecb  mov     rcx, [rbp+188h]; this
0x180004ed2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004ed9  mov     edx, 0A0Bh; void *
0x180004ede  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ee4  mov     rcx, [rbp+188h]; this
0x180004eeb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004ef2  mov     edx, 0E01h; void *
0x180004ef7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180004efd  mov     rcx, [rbp+188h]; this
0x180004f04  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004f0b  mov     edx, 0A15h; void *
0x180004f10  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f16  mov     rcx, [rbp+188h]; this
0x180004f1d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004f24  mov     edx, 0A0Bh; void *
0x180004f29  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f2f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004f35  mov     rcx, [rbp+188h]; this
0x180004f3c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004f43  mov     edx, 0A15h; void *
0x180004f48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f4e  mov     rcx, [rbp+188h]; this
0x180004f55  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004f5c  mov     edx, 0A0Bh; void *
0x180004f61  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f67  mov     rcx, [rbp+188h]; this
0x180004f6e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004f75  mov     edx, 0A15h; void *
0x180004f7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
