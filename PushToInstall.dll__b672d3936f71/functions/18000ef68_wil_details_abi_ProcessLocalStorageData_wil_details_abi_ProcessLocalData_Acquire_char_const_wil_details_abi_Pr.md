# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000ef68`
- end: `0x18000f334`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `972`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000ff10`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x18000ed60`
- `0x18000ef68`
- `0x18000f33c`
- `0x18000f650`
- `0x18000fca8`
- `0x180010788`
- `0x180010b84`
- `0x1800115fc`
- `0x1800116dc`
- `0x180011aec`
- `0x180011afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000f001`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000f001`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f097`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f1ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f243`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f097`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f1ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f243`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000efe0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000efe0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f183`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f183`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f175`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f175`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000efa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000efa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f0a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f259`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f0a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f259`

## string_xrefs

- `0x18000f292`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f2b8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f2d1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f2f0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f309`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000f322`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v34[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v34, (bool *)v11);
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
0x18000ef68  mov     [rsp-8+arg_10], rbx
0x18000ef6d  push    rbp
0x18000ef6e  push    rsi
0x18000ef6f  push    rdi
0x18000ef70  push    r14
0x18000ef72  push    r15
0x18000ef74  lea     rbp, [rsp-160h]
0x18000ef7c  sub     rsp, 260h
0x18000ef83  mov     rax, cs:__security_cookie
0x18000ef8a  xor     rax, rsp
0x18000ef8d  mov     [rbp+180h+var_30], rax
0x18000ef94  mov     r15, rdx
0x18000ef97  mov     qword ptr [rdx], 0
0x18000ef9e  mov     rbx, rcx
0x18000efa1  call    cs:__imp_GetCurrentProcessId
0x18000efa7  mov     r14d, 78h ; 'x'
0x18000efad  mov     [rsp+280h+var_258], rbx
0x18000efb2  mov     r9d, eax
0x18000efb5  mov     [rsp+280h+var_260], r14d; int
0x18000efba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000efc1  mov     edx, 104h; unsigned __int64
0x18000efc6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000efcb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000efd0  mov     r9d, 1F0001h; dwDesiredAccess
0x18000efd6  lea     rdx, [rsp+280h+Name]; lpName
0x18000efdb  xor     r8d, r8d; dwFlags
0x18000efde  xor     ecx, ecx; lpMutexAttributes
0x18000efe0  call    cs:__imp_CreateMutexExW
0x18000efe6  mov     rbx, rax
0x18000efe9  test    rax, rax
0x18000efec  jnz     short loc_18000EFF8
0x18000efee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000eff3  jmp     loc_18000F265
0x18000eff8  xor     r8d, r8d; bAlertable
0x18000effb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000effe  mov     rcx, rbx; hHandle
0x18000f001  call    cs:__imp_WaitForSingleObjectEx
0x18000f007  cmp     eax, 102h
0x18000f00c  jz      short loc_18000F01E
0x18000f00e  test    eax, 0FFFFFF7Fh
0x18000f013  jnz     loc_18000F2A4
0x18000f019  mov     rdi, rbx
0x18000f01c  jmp     short loc_18000F020
0x18000f01e  xor     edi, edi
0x18000f020  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000f025  mov     [rsp+280h+var_250], 0
0x18000f02e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000f033  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000f038  mov     esi, eax
0x18000f03a  test    eax, eax
0x18000f03c  jns     short loc_18000F0BD
0x18000f03e  mov     rcx, [rbp+188h]; this
0x18000f045  lea     r8, aWil; "wil"
0x18000f04c  mov     r9d, eax; char *
0x18000f04f  mov     edx, 66h ; 'f'; void *
0x18000f054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f059  mov     rcx, [rbp+188h]; this
0x18000f060  lea     r8, aWil; "wil"
0x18000f067  mov     r9d, esi; char *
0x18000f06a  mov     edx, 6Fh ; 'o'; void *
0x18000f06f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f074  mov     rcx, [rbp+188h]; this
0x18000f07b  lea     r8, aWil; "wil"
0x18000f082  mov     r9d, esi; char *
0x18000f085  mov     edx, 12Eh; void *
0x18000f08a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f08f  test    rdi, rdi
0x18000f092  jz      short loc_18000F0A5
0x18000f094  mov     rcx, rdi; hMutex
0x18000f097  call    cs:__imp_ReleaseMutex
0x18000f09d  test    eax, eax
0x18000f09f  jz      loc_18000F2B1
0x18000f0a5  mov     rcx, rbx; hObject
0x18000f0a8  call    cs:__imp_CloseHandle
0x18000f0ae  test    eax, eax
0x18000f0b0  jz      loc_18000F2CA
0x18000f0b6  mov     eax, esi
0x18000f0b8  jmp     loc_18000F265
0x18000f0bd  mov     rax, [rsp+280h+var_250]
0x18000f0c2  lea     rcx, ds:0[rax*4]
0x18000f0ca  test    rcx, rcx
0x18000f0cd  jz      short loc_18000F0DD
0x18000f0cf  mov     [r15], rcx
0x18000f0d2  mov     eax, [rcx]
0x18000f0d4  inc     eax
0x18000f0d6  mov     [rcx], eax
0x18000f0d8  jmp     loc_18000F23B
0x18000f0dd  mov     rdx, r14; dwBytes
0x18000f0e0  mov     qword ptr [r15], 0
0x18000f0e7  mov     ecx, 8; dwFlags
0x18000f0ec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f0f1  mov     rsi, rax
0x18000f0f4  test    rax, rax
0x18000f0f7  jnz     short loc_18000F11C
0x18000f0f9  mov     rcx, [rbp+188h]; this
0x18000f100  lea     r8, aWil; "wil"
0x18000f107  mov     r14d, 8007000Eh
0x18000f10d  mov     edx, 14Bh; void *
0x18000f112  mov     r9d, r14d; char *
0x18000f115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f11a  jmp     short loc_18000F189
0x18000f11c  xorps   xmm0, xmm0
0x18000f11f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000f125  test    sil, 3
0x18000f129  jnz     loc_18000F2E3
0x18000f12f  mov     r9, rsi
0x18000f132  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000f137  shr     r9, 2; unsigned __int64
0x18000f13b  lea     rcx, [rsp+280h+var_250]; this
0x18000f140  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000f145  mov     r14d, eax
0x18000f148  test    eax, eax
0x18000f14a  jns     loc_18000F1D3
0x18000f150  mov     rcx, [rbp+188h]; this
0x18000f157  lea     r8, aWil; "wil"
0x18000f15e  mov     r9d, eax; char *
0x18000f161  mov     edx, 14Eh; void *
0x18000f166  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f16b  lea     rcx, [rsp+280h+var_250]; this
0x18000f170  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000f175  call    cs:__imp_GetProcessHeap
0x18000f17b  mov     r8, rsi; lpMem
0x18000f17e  xor     edx, edx; dwFlags
0x18000f180  mov     rcx, rax; hHeap
0x18000f183  call    cs:__imp_HeapFree
0x18000f189  mov     rcx, [rbp+188h]; this
0x18000f190  lea     r8, aWil; "wil"
0x18000f197  mov     r9d, r14d; char *
0x18000f19a  mov     edx, 137h; void *
0x18000f19f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f1a4  test    rdi, rdi
0x18000f1a7  jz      short loc_18000F1BA
0x18000f1a9  mov     rcx, rdi; hMutex
0x18000f1ac  call    cs:__imp_ReleaseMutex
0x18000f1b2  test    eax, eax
0x18000f1b4  jz      loc_18000F2E9
0x18000f1ba  mov     rcx, rbx; hObject
0x18000f1bd  call    cs:__imp_CloseHandle
0x18000f1c3  test    eax, eax
0x18000f1c5  jz      loc_18000F302
0x18000f1cb  mov     eax, r14d
0x18000f1ce  jmp     loc_18000F265
0x18000f1d3  mov     rax, [rsp+280h+var_250]
0x18000f1d8  lea     rcx, [rsi+22h]; void *
0x18000f1dc  xor     edx, edx; Val
0x18000f1de  mov     [rsi+10h], rax
0x18000f1e2  mov     rax, [rsp+280h+var_250+8]
0x18000f1e7  mov     dword ptr [rsi], 1
0x18000f1ed  mov     [rsi+8], rbx
0x18000f1f1  lea     r8d, [rdx+56h]; Size
0x18000f1f5  mov     [rsp+280h+var_250], 0
0x18000f1fe  mov     [rsi+18h], rax
0x18000f202  mov     [rsp+280h+var_250+8], 0
0x18000f20b  call    memset_0
0x18000f210  xor     edx, edx; Val
0x18000f212  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000f218  lea     rcx, [rsi+28h]; void *
0x18000f21c  mov     dword ptr [rsi+24h], 1
0x18000f223  lea     r8d, [rdx+50h]; Size
0x18000f227  call    memset_0
0x18000f22c  lea     rcx, [rsp+280h+var_250]; this
0x18000f231  mov     [r15], rsi
0x18000f234  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000f239  xor     ebx, ebx
0x18000f23b  test    rdi, rdi
0x18000f23e  jz      short loc_18000F251
0x18000f240  mov     rcx, rdi; hMutex
0x18000f243  call    cs:__imp_ReleaseMutex
0x18000f249  test    eax, eax
0x18000f24b  jz      loc_18000F31B
0x18000f251  test    rbx, rbx
0x18000f254  jz      short loc_18000F263
0x18000f256  mov     rcx, rbx; hObject
0x18000f259  call    cs:__imp_CloseHandle
0x18000f25f  test    eax, eax
0x18000f261  jz      short loc_18000F28B
0x18000f263  xor     eax, eax
0x18000f265  mov     rcx, [rbp+180h+var_30]
0x18000f26c  xor     rcx, rsp; StackCookie
0x18000f26f  call    __security_check_cookie
0x18000f274  mov     rbx, [rsp+280h+arg_10]
0x18000f27c  add     rsp, 260h
0x18000f283  pop     r15
0x18000f285  pop     r14
0x18000f287  pop     rdi
0x18000f288  pop     rsi
0x18000f289  pop     rbp
0x18000f28a  retn
0x18000f28b  mov     rcx, [rbp+188h]; this
0x18000f292  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f299  mov     edx, 0A0Bh; void *
0x18000f29e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f2a4  mov     rcx, [rbp+188h]; this
0x18000f2ab  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000f2b1  mov     rcx, [rbp+188h]; this
0x18000f2b8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f2bf  mov     edx, 0A15h; void *
0x18000f2c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f2ca  mov     rcx, [rbp+188h]; this
0x18000f2d1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f2d8  mov     edx, 0A0Bh; void *
0x18000f2dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f2e3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000f2e9  mov     rcx, [rbp+188h]; this
0x18000f2f0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f2f7  mov     edx, 0A15h; void *
0x18000f2fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f302  mov     rcx, [rbp+188h]; this
0x18000f309  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f310  mov     edx, 0A0Bh; void *
0x18000f315  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f31b  mov     rcx, [rbp+188h]; this
0x18000f322  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f329  mov     edx, 0A15h; void *
0x18000f32e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
