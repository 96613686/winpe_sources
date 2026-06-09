# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004e58`
- end: `0x180005224`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180006890`

## callees

- `0x180002350`
- `0x180002ed4`
- `0x180004ab8`
- `0x180004e58`
- `0x18000568c`
- `0x180005cf0`
- `0x180006628`
- `0x180007358`
- `0x180008c24`
- `0x180009718`
- `0x180009bac`
- `0x18000a48c`
- `0x18000a49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004ef1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004ef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f87`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000509c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005133`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f87`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000509c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005133`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004ed0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004ed0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005065`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005073`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005073`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005149`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005149`

## string_xrefs

- `0x180005182`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800051a8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800051c1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800051e0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800051f9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005212`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180004e58  mov     [rsp-8+arg_10], rbx
0x180004e5d  push    rbp
0x180004e5e  push    rsi
0x180004e5f  push    rdi
0x180004e60  push    r14
0x180004e62  push    r15
0x180004e64  lea     rbp, [rsp-160h]
0x180004e6c  sub     rsp, 260h
0x180004e73  mov     rax, cs:__security_cookie
0x180004e7a  xor     rax, rsp
0x180004e7d  mov     [rbp+180h+var_30], rax
0x180004e84  mov     r15, rdx
0x180004e87  mov     qword ptr [rdx], 0
0x180004e8e  mov     rbx, rcx
0x180004e91  call    cs:__imp_GetCurrentProcessId
0x180004e97  mov     r14d, 78h ; 'x'
0x180004e9d  mov     [rsp+280h+var_258], rbx
0x180004ea2  mov     r9d, eax
0x180004ea5  mov     [rsp+280h+var_260], r14d; int
0x180004eaa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004eb1  mov     edx, 104h; unsigned __int64
0x180004eb6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004ebb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004ec0  mov     r9d, 1F0001h; dwDesiredAccess
0x180004ec6  lea     rdx, [rsp+280h+Name]; lpName
0x180004ecb  xor     r8d, r8d; dwFlags
0x180004ece  xor     ecx, ecx; lpMutexAttributes
0x180004ed0  call    cs:__imp_CreateMutexExW
0x180004ed6  mov     rbx, rax
0x180004ed9  test    rax, rax
0x180004edc  jnz     short loc_180004EE8
0x180004ede  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004ee3  jmp     loc_180005155
0x180004ee8  xor     r8d, r8d; bAlertable
0x180004eeb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004eee  mov     rcx, rbx; hHandle
0x180004ef1  call    cs:__imp_WaitForSingleObjectEx
0x180004ef7  cmp     eax, 102h
0x180004efc  jz      short loc_180004F0E
0x180004efe  test    eax, 0FFFFFF7Fh
0x180004f03  jnz     loc_180005194
0x180004f09  mov     rdi, rbx
0x180004f0c  jmp     short loc_180004F10
0x180004f0e  xor     edi, edi
0x180004f10  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180004f15  mov     [rsp+280h+var_250], 0
0x180004f1e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004f23  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004f28  mov     esi, eax
0x180004f2a  test    eax, eax
0x180004f2c  jns     short loc_180004FAD
0x180004f2e  mov     rcx, [rbp+188h]; this
0x180004f35  lea     r8, aWil; "wil"
0x180004f3c  mov     r9d, eax; char *
0x180004f3f  mov     edx, 66h ; 'f'; void *
0x180004f44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f49  mov     rcx, [rbp+188h]; this
0x180004f50  lea     r8, aWil; "wil"
0x180004f57  mov     r9d, esi; char *
0x180004f5a  mov     edx, 6Fh ; 'o'; void *
0x180004f5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f64  mov     rcx, [rbp+188h]; this
0x180004f6b  lea     r8, aWil; "wil"
0x180004f72  mov     r9d, esi; char *
0x180004f75  mov     edx, 12Eh; void *
0x180004f7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f7f  test    rdi, rdi
0x180004f82  jz      short loc_180004F95
0x180004f84  mov     rcx, rdi; hMutex
0x180004f87  call    cs:__imp_ReleaseMutex
0x180004f8d  test    eax, eax
0x180004f8f  jz      loc_1800051A1
0x180004f95  mov     rcx, rbx; hObject
0x180004f98  call    cs:__imp_CloseHandle
0x180004f9e  test    eax, eax
0x180004fa0  jz      loc_1800051BA
0x180004fa6  mov     eax, esi
0x180004fa8  jmp     loc_180005155
0x180004fad  mov     rax, [rsp+280h+var_250]
0x180004fb2  lea     rcx, ds:0[rax*4]
0x180004fba  test    rcx, rcx
0x180004fbd  jz      short loc_180004FCD
0x180004fbf  mov     [r15], rcx
0x180004fc2  mov     eax, [rcx]
0x180004fc4  inc     eax
0x180004fc6  mov     [rcx], eax
0x180004fc8  jmp     loc_18000512B
0x180004fcd  mov     rdx, r14; dwBytes
0x180004fd0  mov     qword ptr [r15], 0
0x180004fd7  mov     ecx, 8; dwFlags
0x180004fdc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004fe1  mov     rsi, rax
0x180004fe4  test    rax, rax
0x180004fe7  jnz     short loc_18000500C
0x180004fe9  mov     rcx, [rbp+188h]; this
0x180004ff0  lea     r8, aWil; "wil"
0x180004ff7  mov     r14d, 8007000Eh
0x180004ffd  mov     edx, 14Bh; void *
0x180005002  mov     r9d, r14d; char *
0x180005005  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000500a  jmp     short loc_180005079
0x18000500c  xorps   xmm0, xmm0
0x18000500f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180005015  test    sil, 3
0x180005019  jnz     loc_1800051D3
0x18000501f  mov     r9, rsi
0x180005022  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005027  shr     r9, 2; unsigned __int64
0x18000502b  lea     rcx, [rsp+280h+var_250]; this
0x180005030  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005035  mov     r14d, eax
0x180005038  test    eax, eax
0x18000503a  jns     loc_1800050C3
0x180005040  mov     rcx, [rbp+188h]; this
0x180005047  lea     r8, aWil; "wil"
0x18000504e  mov     r9d, eax; char *
0x180005051  mov     edx, 14Eh; void *
0x180005056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000505b  lea     rcx, [rsp+280h+var_250]; this
0x180005060  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005065  call    cs:__imp_GetProcessHeap
0x18000506b  mov     r8, rsi; lpMem
0x18000506e  xor     edx, edx; dwFlags
0x180005070  mov     rcx, rax; hHeap
0x180005073  call    cs:__imp_HeapFree
0x180005079  mov     rcx, [rbp+188h]; this
0x180005080  lea     r8, aWil; "wil"
0x180005087  mov     r9d, r14d; char *
0x18000508a  mov     edx, 137h; void *
0x18000508f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005094  test    rdi, rdi
0x180005097  jz      short loc_1800050AA
0x180005099  mov     rcx, rdi; hMutex
0x18000509c  call    cs:__imp_ReleaseMutex
0x1800050a2  test    eax, eax
0x1800050a4  jz      loc_1800051D9
0x1800050aa  mov     rcx, rbx; hObject
0x1800050ad  call    cs:__imp_CloseHandle
0x1800050b3  test    eax, eax
0x1800050b5  jz      loc_1800051F2
0x1800050bb  mov     eax, r14d
0x1800050be  jmp     loc_180005155
0x1800050c3  mov     rax, [rsp+280h+var_250]
0x1800050c8  lea     rcx, [rsi+22h]; void *
0x1800050cc  xor     edx, edx; Val
0x1800050ce  mov     [rsi+10h], rax
0x1800050d2  mov     rax, [rsp+280h+var_250+8]
0x1800050d7  mov     dword ptr [rsi], 1
0x1800050dd  mov     [rsi+8], rbx
0x1800050e1  lea     r8d, [rdx+56h]; Size
0x1800050e5  mov     [rsp+280h+var_250], 0
0x1800050ee  mov     [rsi+18h], rax
0x1800050f2  mov     [rsp+280h+var_250+8], 0
0x1800050fb  call    memset_0
0x180005100  xor     edx, edx; Val
0x180005102  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005108  lea     rcx, [rsi+28h]; void *
0x18000510c  mov     dword ptr [rsi+24h], 1
0x180005113  lea     r8d, [rdx+50h]; Size
0x180005117  call    memset_0
0x18000511c  lea     rcx, [rsp+280h+var_250]; this
0x180005121  mov     [r15], rsi
0x180005124  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005129  xor     ebx, ebx
0x18000512b  test    rdi, rdi
0x18000512e  jz      short loc_180005141
0x180005130  mov     rcx, rdi; hMutex
0x180005133  call    cs:__imp_ReleaseMutex
0x180005139  test    eax, eax
0x18000513b  jz      loc_18000520B
0x180005141  test    rbx, rbx
0x180005144  jz      short loc_180005153
0x180005146  mov     rcx, rbx; hObject
0x180005149  call    cs:__imp_CloseHandle
0x18000514f  test    eax, eax
0x180005151  jz      short loc_18000517B
0x180005153  xor     eax, eax
0x180005155  mov     rcx, [rbp+180h+var_30]
0x18000515c  xor     rcx, rsp; StackCookie
0x18000515f  call    __security_check_cookie
0x180005164  mov     rbx, [rsp+280h+arg_10]
0x18000516c  add     rsp, 260h
0x180005173  pop     r15
0x180005175  pop     r14
0x180005177  pop     rdi
0x180005178  pop     rsi
0x180005179  pop     rbp
0x18000517a  retn
0x18000517b  mov     rcx, [rbp+188h]; this
0x180005182  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005189  mov     edx, 0A0Bh; void *
0x18000518e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005194  mov     rcx, [rbp+188h]; this
0x18000519b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800051a1  mov     rcx, [rbp+188h]; this
0x1800051a8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800051af  mov     edx, 0A15h; void *
0x1800051b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051ba  mov     rcx, [rbp+188h]; this
0x1800051c1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800051c8  mov     edx, 0A0Bh; void *
0x1800051cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800051d9  mov     rcx, [rbp+188h]; this
0x1800051e0  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800051e7  mov     edx, 0A15h; void *
0x1800051ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051f2  mov     rcx, [rbp+188h]; this
0x1800051f9  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005200  mov     edx, 0A0Bh; void *
0x180005205  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000520b  mov     rcx, [rbp+188h]; this
0x180005212  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005219  mov     edx, 0A15h; void *
0x18000521e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
