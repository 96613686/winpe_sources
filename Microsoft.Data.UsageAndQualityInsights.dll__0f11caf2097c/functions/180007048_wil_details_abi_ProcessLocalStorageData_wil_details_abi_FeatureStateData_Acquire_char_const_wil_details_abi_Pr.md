# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007048`
- end: `0x180007445`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x180007750`

## callees

- `0x1800033d0`
- `0x180003fb8`
- `0x180005ffc`
- `0x180006878`
- `0x180007048`
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

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800070e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800070e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007176`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007289`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007348`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007176`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007289`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007348`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000730b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000730b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800070bf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800070bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007260`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007260`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007252`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007252`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007081`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007187`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000729a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000735e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007187`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000729a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000735e`

## string_xrefs

- `0x180007397`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800073b0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800073c9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800073e2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800073fb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000741a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007433`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  const char *v24; // r9
  const char *v25; // r9
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
  v31[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v31, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v28);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v29);
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
  v17 = (_DWORD *)(4 * v31[0]);
  if ( 4 * v31[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v21 = (_DWORD *)v18;
  if ( !v18 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v31 = 0;
  if ( (v18 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  v22 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v31,
          Name,
          v20,
          v18 >> 2);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v30);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v31[0];
  *((_QWORD *)v21 + 3) = v31[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v31[0] = 0;
  v31[1] = 0;
  memset_0(v21 + 10, 0, 0x108u);
  *((_QWORD *)v21 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v21 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v21 + 58), 0, 0);
  *((_QWORD *)v21 + 34) = 0;
  *((_QWORD *)v21 + 35) = 0;
  *((_QWORD *)v21 + 36) = 0;
  *((_QWORD *)v21 + 37) = 0;
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
  v6 = 0;
LABEL_24:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return 0;
}

```

## disassembly

```asm
0x180007048  mov     [rsp-8+arg_10], rbx
0x18000704d  push    rbp
0x18000704e  push    rsi
0x18000704f  push    rdi
0x180007050  push    r14
0x180007052  push    r15
0x180007054  lea     rbp, [rsp-160h]
0x18000705c  sub     rsp, 260h
0x180007063  mov     rax, cs:__security_cookie
0x18000706a  xor     rax, rsp
0x18000706d  mov     [rbp+180h+var_30], rax
0x180007074  mov     r15, rdx
0x180007077  mov     qword ptr [rdx], 0
0x18000707e  mov     rbx, rcx
0x180007081  call    cs:__imp_GetCurrentProcessId
0x180007087  mov     r14d, 130h
0x18000708d  mov     [rsp+280h+var_258], rbx
0x180007092  mov     r9d, eax
0x180007095  mov     [rsp+280h+var_260], r14d; int
0x18000709a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800070a1  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800070a6  lea     edx, [r14-2Ch]; unsigned __int64
0x1800070aa  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800070af  mov     r9d, 1F0001h; dwDesiredAccess
0x1800070b5  lea     rdx, [rsp+280h+Name]; lpName
0x1800070ba  xor     r8d, r8d; dwFlags
0x1800070bd  xor     ecx, ecx; lpMutexAttributes
0x1800070bf  call    cs:__imp_CreateMutexExW
0x1800070c5  mov     rbx, rax
0x1800070c8  test    rax, rax
0x1800070cb  jnz     short loc_1800070D7
0x1800070cd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800070d2  jmp     loc_18000736A
0x1800070d7  xor     r8d, r8d; bAlertable
0x1800070da  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800070dd  mov     rcx, rbx; hHandle
0x1800070e0  call    cs:__imp_WaitForSingleObjectEx
0x1800070e6  cmp     eax, 102h
0x1800070eb  jz      short loc_1800070FD
0x1800070ed  test    eax, 0FFFFFF7Fh
0x1800070f2  jnz     loc_1800073C2
0x1800070f8  mov     rdi, rbx
0x1800070fb  jmp     short loc_1800070FF
0x1800070fd  xor     edi, edi
0x1800070ff  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180007104  mov     [rsp+280h+var_250], 0
0x18000710d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180007112  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180007117  mov     esi, eax
0x180007119  test    eax, eax
0x18000711b  jns     short loc_18000719C
0x18000711d  mov     rcx, [rbp+188h]; this
0x180007124  lea     r8, aWil; "wil"
0x18000712b  mov     r9d, eax; char *
0x18000712e  mov     edx, 66h ; 'f'; void *
0x180007133  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007138  mov     rcx, [rbp+188h]; this
0x18000713f  lea     r8, aWil; "wil"
0x180007146  mov     r9d, esi; char *
0x180007149  mov     edx, 6Fh ; 'o'; void *
0x18000714e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007153  mov     rcx, [rbp+188h]; this
0x18000715a  lea     r8, aWil; "wil"
0x180007161  mov     r9d, esi; char *
0x180007164  mov     edx, 12Eh; void *
0x180007169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000716e  test    rdi, rdi
0x180007171  jz      short loc_180007184
0x180007173  mov     rcx, rdi; hMutex
0x180007176  call    cs:__imp_ReleaseMutex
0x18000717c  test    eax, eax
0x18000717e  jz      loc_1800073DB
0x180007184  mov     rcx, rbx; hObject
0x180007187  call    cs:__imp_CloseHandle
0x18000718d  test    eax, eax
0x18000718f  jz      loc_1800073F4
0x180007195  mov     eax, esi
0x180007197  jmp     loc_18000736A
0x18000719c  mov     rax, [rsp+280h+var_250]
0x1800071a1  lea     rcx, ds:0[rax*4]
0x1800071a9  test    rcx, rcx
0x1800071ac  jz      short loc_1800071BC
0x1800071ae  mov     [r15], rcx
0x1800071b1  mov     eax, [rcx]
0x1800071b3  inc     eax
0x1800071b5  mov     [rcx], eax
0x1800071b7  jmp     loc_180007340
0x1800071bc  mov     rdx, r14; dwBytes
0x1800071bf  mov     qword ptr [r15], 0
0x1800071c6  mov     ecx, 8; dwFlags
0x1800071cb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800071d0  mov     r14, rax
0x1800071d3  test    rax, rax
0x1800071d6  jnz     short loc_1800071FA
0x1800071d8  mov     rcx, [rbp+188h]; this
0x1800071df  lea     r8, aWil; "wil"
0x1800071e6  mov     esi, 8007000Eh
0x1800071eb  mov     edx, 14Bh; void *
0x1800071f0  mov     r9d, esi; char *
0x1800071f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071f8  jmp     short loc_180007266
0x1800071fa  xorps   xmm0, xmm0
0x1800071fd  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180007203  test    r14b, 3
0x180007207  jnz     loc_18000740D
0x18000720d  mov     r9, r14
0x180007210  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180007215  shr     r9, 2; unsigned __int64
0x180007219  lea     rcx, [rsp+280h+var_250]; this
0x18000721e  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180007223  mov     esi, eax
0x180007225  test    eax, eax
0x180007227  jns     loc_1800072AD
0x18000722d  mov     rcx, [rbp+188h]; this
0x180007234  lea     r8, aWil; "wil"
0x18000723b  mov     r9d, eax; char *
0x18000723e  mov     edx, 14Eh; void *
0x180007243  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007248  lea     rcx, [rsp+280h+var_250]; this
0x18000724d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007252  call    cs:__imp_GetProcessHeap
0x180007258  mov     r8, r14; lpMem
0x18000725b  xor     edx, edx; dwFlags
0x18000725d  mov     rcx, rax; hHeap
0x180007260  call    cs:__imp_HeapFree
0x180007266  mov     rcx, [rbp+188h]; this
0x18000726d  lea     r8, aWil; "wil"
0x180007274  mov     r9d, esi; char *
0x180007277  mov     edx, 137h; void *
0x18000727c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007281  test    rdi, rdi
0x180007284  jz      short loc_180007297
0x180007286  mov     rcx, rdi; hMutex
0x180007289  call    cs:__imp_ReleaseMutex
0x18000728f  test    eax, eax
0x180007291  jz      loc_180007413
0x180007297  mov     rcx, rbx; hObject
0x18000729a  call    cs:__imp_CloseHandle
0x1800072a0  test    eax, eax
0x1800072a2  jz      loc_1800073A9
0x1800072a8  jmp     loc_180007195
0x1800072ad  mov     rax, [rsp+280h+var_250]
0x1800072b2  lea     rcx, [r14+28h]; void *
0x1800072b6  mov     [r14+10h], rax
0x1800072ba  xor     edx, edx; Val
0x1800072bc  mov     rax, [rsp+280h+var_250+8]
0x1800072c1  mov     r8d, 108h; Size
0x1800072c7  mov     [r14+18h], rax
0x1800072cb  mov     dword ptr [r14], 1
0x1800072d2  mov     [r14+8], rbx
0x1800072d6  mov     [rsp+280h+var_250], 0
0x1800072df  mov     [rsp+280h+var_250+8], 0
0x1800072e8  call    memset_0
0x1800072ed  xor     eax, eax
0x1800072ef  lea     rcx, [r14+28h]; this
0x1800072f3  mov     [r14+20h], rax
0x1800072f7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800072fc  lea     rbx, [r14+0E8h]
0x180007303  xor     r8d, r8d; Flags
0x180007306  mov     rcx, rbx; lpCriticalSection
0x180007309  xor     edx, edx; dwSpinCount
0x18000730b  call    cs:__imp_InitializeCriticalSectionEx
0x180007311  mov     qword ptr [rbx+28h], 0
0x180007319  lea     rcx, [rsp+280h+var_250]; this
0x18000731e  mov     qword ptr [rbx+30h], 0
0x180007326  mov     qword ptr [rbx+38h], 0
0x18000732e  mov     qword ptr [rbx+40h], 0
0x180007336  mov     [r15], r14
0x180007339  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000733e  xor     ebx, ebx
0x180007340  test    rdi, rdi
0x180007343  jz      short loc_180007356
0x180007345  mov     rcx, rdi; hMutex
0x180007348  call    cs:__imp_ReleaseMutex
0x18000734e  test    eax, eax
0x180007350  jz      loc_18000742C
0x180007356  test    rbx, rbx
0x180007359  jz      short loc_180007368
0x18000735b  mov     rcx, rbx; hObject
0x18000735e  call    cs:__imp_CloseHandle
0x180007364  test    eax, eax
0x180007366  jz      short loc_180007390
0x180007368  xor     eax, eax
0x18000736a  mov     rcx, [rbp+180h+var_30]
0x180007371  xor     rcx, rsp; StackCookie
0x180007374  call    __security_check_cookie
0x180007379  mov     rbx, [rsp+280h+arg_10]
0x180007381  add     rsp, 260h
0x180007388  pop     r15
0x18000738a  pop     r14
0x18000738c  pop     rdi
0x18000738d  pop     rsi
0x18000738e  pop     rbp
0x18000738f  retn
0x180007390  mov     rcx, [rbp+188h]; this
0x180007397  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000739e  mov     edx, 0A0Bh; void *
0x1800073a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800073a9  mov     rcx, [rbp+188h]; this
0x1800073b0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800073b7  mov     edx, 0A0Bh; void *
0x1800073bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800073c2  mov     rcx, [rbp+188h]; this
0x1800073c9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800073d0  mov     edx, 0E01h; void *
0x1800073d5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800073db  mov     rcx, [rbp+188h]; this
0x1800073e2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800073e9  mov     edx, 0A15h; void *
0x1800073ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800073f4  mov     rcx, [rbp+188h]; this
0x1800073fb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007402  mov     edx, 0A0Bh; void *
0x180007407  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000740d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007413  mov     rcx, [rbp+188h]; this
0x18000741a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007421  mov     edx, 0A15h; void *
0x180007426  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000742c  mov     rcx, [rbp+188h]; this
0x180007433  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000743a  mov     edx, 0A15h; void *
0x18000743f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
