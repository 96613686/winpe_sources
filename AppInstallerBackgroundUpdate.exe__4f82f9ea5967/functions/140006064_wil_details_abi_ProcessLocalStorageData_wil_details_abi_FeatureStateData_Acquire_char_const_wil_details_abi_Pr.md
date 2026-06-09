# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140006064`
- end: `0x140006455`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14000645c`

## callees

- `0x140001530`
- `0x140001f50`
- `0x1400030e8`
- `0x1400033d4`
- `0x140003a28`
- `0x140004508`
- `0x140004764`
- `0x140005154`
- `0x14000521c`
- `0x1400055dc`
- `0x1400055ec`
- `0x140005a08`
- `0x140006064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140006337`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140006337`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400060db`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400060db`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400060fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400060fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006192`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400062ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000636a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140006192`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400062ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000636a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006297`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006297`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000609d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000609d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400061a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006271`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400062df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006380`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400061a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006271`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400062df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006380`

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
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
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
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x140006064  mov     [rsp-8+arg_10], rbx
0x140006069  push    rbp
0x14000606a  push    rsi
0x14000606b  push    rdi
0x14000606c  push    r14
0x14000606e  push    r15
0x140006070  lea     rbp, [rsp-160h]
0x140006078  sub     rsp, 260h
0x14000607f  mov     rax, cs:__security_cookie
0x140006086  xor     rax, rsp
0x140006089  mov     [rbp+180h+var_30], rax
0x140006090  mov     r15, rdx
0x140006093  mov     qword ptr [rdx], 0
0x14000609a  mov     rbx, rcx
0x14000609d  call    cs:__imp_GetCurrentProcessId
0x1400060a3  mov     r14d, 130h
0x1400060a9  mov     [rsp+280h+var_258], rbx
0x1400060ae  mov     r9d, eax
0x1400060b1  mov     [rsp+280h+var_260], r14d; int
0x1400060b6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400060bd  lea     rcx, [rsp+280h+Name]; Buffer
0x1400060c2  lea     edx, [r14-2Ch]; unsigned __int64
0x1400060c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400060cb  mov     r9d, 1F0001h; dwDesiredAccess
0x1400060d1  lea     rdx, [rsp+280h+Name]; lpName
0x1400060d6  xor     r8d, r8d; dwFlags
0x1400060d9  xor     ecx, ecx; lpMutexAttributes
0x1400060db  call    cs:__imp_CreateMutexExW
0x1400060e1  mov     rbx, rax
0x1400060e4  test    rax, rax
0x1400060e7  jnz     short loc_1400060F3
0x1400060e9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400060ee  jmp     loc_14000638C
0x1400060f3  xor     r8d, r8d; bAlertable
0x1400060f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400060f9  mov     rcx, rbx; hHandle
0x1400060fc  call    cs:__imp_WaitForSingleObjectEx
0x140006102  cmp     eax, 102h
0x140006107  jz      short loc_140006119
0x140006109  test    eax, 0FFFFFF7Fh
0x14000610e  jnz     loc_1400063D6
0x140006114  mov     rdi, rbx
0x140006117  jmp     short loc_14000611B
0x140006119  xor     edi, edi
0x14000611b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140006120  mov     [rsp+280h+hObject], 0
0x140006129  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000612e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140006133  mov     esi, eax
0x140006135  test    eax, eax
0x140006137  jns     short loc_1400061B8
0x140006139  mov     rcx, [rbp+188h]; this
0x140006140  lea     r8, aWil; "wil"
0x140006147  mov     r9d, eax; char *
0x14000614a  mov     edx, 66h ; 'f'; void *
0x14000614f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006154  mov     rcx, [rbp+188h]; this
0x14000615b  lea     r8, aWil; "wil"
0x140006162  mov     r9d, esi; char *
0x140006165  mov     edx, 6Fh ; 'o'; void *
0x14000616a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000616f  mov     rcx, [rbp+188h]; this
0x140006176  lea     r8, aWil; "wil"
0x14000617d  mov     r9d, esi; char *
0x140006180  mov     edx, 12Eh; void *
0x140006185  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000618a  test    rdi, rdi
0x14000618d  jz      short loc_1400061A0
0x14000618f  mov     rcx, rdi; hMutex
0x140006192  call    cs:__imp_ReleaseMutex
0x140006198  test    eax, eax
0x14000619a  jz      loc_1400063E3
0x1400061a0  mov     rcx, rbx; hObject
0x1400061a3  call    cs:__imp_CloseHandle
0x1400061a9  test    eax, eax
0x1400061ab  jz      loc_1400063F5
0x1400061b1  mov     eax, esi
0x1400061b3  jmp     loc_14000638C
0x1400061b8  mov     rax, [rsp+280h+hObject]
0x1400061bd  lea     rcx, ds:0[rax*4]
0x1400061c5  test    rcx, rcx
0x1400061c8  jz      short loc_1400061D8
0x1400061ca  mov     [r15], rcx
0x1400061cd  mov     eax, [rcx]
0x1400061cf  inc     eax
0x1400061d1  mov     [rcx], eax
0x1400061d3  jmp     loc_140006362
0x1400061d8  mov     rdx, r14; dwBytes
0x1400061db  mov     qword ptr [r15], 0
0x1400061e2  mov     ecx, 8; dwFlags
0x1400061e7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400061ec  mov     r14, rax
0x1400061ef  test    rax, rax
0x1400061f2  jnz     short loc_140006219
0x1400061f4  mov     rcx, [rbp+188h]; this
0x1400061fb  lea     r8, aWil; "wil"
0x140006202  mov     esi, 8007000Eh
0x140006207  mov     edx, 14Bh; void *
0x14000620c  mov     r9d, esi; char *
0x14000620f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006214  jmp     loc_1400062AB
0x140006219  xorps   xmm0, xmm0
0x14000621c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140006222  test    r14b, 3
0x140006226  jnz     loc_140006407
0x14000622c  mov     r9, r14
0x14000622f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140006234  shr     r9, 2; unsigned __int64
0x140006238  lea     rcx, [rsp+280h+hObject]; this
0x14000623d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140006242  mov     esi, eax
0x140006244  test    eax, eax
0x140006246  jns     loc_1400062F2
0x14000624c  mov     rcx, [rbp+188h]; this
0x140006253  lea     r8, aWil; "wil"
0x14000625a  mov     r9d, eax; char *
0x14000625d  mov     edx, 14Eh; void *
0x140006262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006267  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14000626c  test    rcx, rcx
0x14000626f  jz      short loc_14000627F
0x140006271  call    cs:__imp_CloseHandle
0x140006277  test    eax, eax
0x140006279  jz      loc_14000640D
0x14000627f  mov     rcx, [rsp+280h+hObject]; hObject
0x140006284  test    rcx, rcx
0x140006287  jz      short loc_140006297
0x140006289  call    cs:__imp_CloseHandle
0x14000628f  test    eax, eax
0x140006291  jz      loc_14000641F
0x140006297  call    cs:__imp_GetProcessHeap
0x14000629d  mov     r8, r14; lpMem
0x1400062a0  xor     edx, edx; dwFlags
0x1400062a2  mov     rcx, rax; hHeap
0x1400062a5  call    cs:__imp_HeapFree
0x1400062ab  mov     rcx, [rbp+188h]; this
0x1400062b2  lea     r8, aWil; "wil"
0x1400062b9  mov     r9d, esi; char *
0x1400062bc  mov     edx, 137h; void *
0x1400062c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400062c6  test    rdi, rdi
0x1400062c9  jz      short loc_1400062DC
0x1400062cb  mov     rcx, rdi; hMutex
0x1400062ce  call    cs:__imp_ReleaseMutex
0x1400062d4  test    eax, eax
0x1400062d6  jz      loc_140006431
0x1400062dc  mov     rcx, rbx; hObject
0x1400062df  call    cs:__imp_CloseHandle
0x1400062e5  test    eax, eax
0x1400062e7  jz      loc_1400063C4
0x1400062ed  jmp     loc_1400061B1
0x1400062f2  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400062f7  lea     rcx, [r14+28h]; void *
0x1400062fb  mov     dword ptr [r14], 1
0x140006302  xor     edx, edx; Val
0x140006304  mov     [r14+8], rbx
0x140006308  mov     r8d, 108h; Size
0x14000630e  movdqu  xmmword ptr [r14+10h], xmm0
0x140006314  call    memset_0
0x140006319  xor     eax, eax
0x14000631b  lea     rcx, [r14+28h]; this
0x14000631f  mov     [r14+20h], rax
0x140006323  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140006328  lea     rbx, [r14+0E8h]
0x14000632f  xor     r8d, r8d; Flags
0x140006332  mov     rcx, rbx; lpCriticalSection
0x140006335  xor     edx, edx; dwSpinCount
0x140006337  call    cs:__imp_InitializeCriticalSectionEx
0x14000633d  mov     qword ptr [rbx+28h], 0
0x140006345  mov     qword ptr [rbx+30h], 0
0x14000634d  mov     qword ptr [rbx+38h], 0
0x140006355  mov     qword ptr [rbx+40h], 0
0x14000635d  xor     ebx, ebx
0x14000635f  mov     [r15], r14
0x140006362  test    rdi, rdi
0x140006365  jz      short loc_140006378
0x140006367  mov     rcx, rdi; hMutex
0x14000636a  call    cs:__imp_ReleaseMutex
0x140006370  test    eax, eax
0x140006372  jz      loc_140006443
0x140006378  test    rbx, rbx
0x14000637b  jz      short loc_14000638A
0x14000637d  mov     rcx, rbx; hObject
0x140006380  call    cs:__imp_CloseHandle
0x140006386  test    eax, eax
0x140006388  jz      short loc_1400063B2
0x14000638a  xor     eax, eax
0x14000638c  mov     rcx, [rbp+180h+var_30]
0x140006393  xor     rcx, rsp; StackCookie
0x140006396  call    __security_check_cookie
0x14000639b  mov     rbx, [rsp+280h+arg_10]
0x1400063a3  add     rsp, 260h
0x1400063aa  pop     r15
0x1400063ac  pop     r14
0x1400063ae  pop     rdi
0x1400063af  pop     rsi
0x1400063b0  pop     rbp
0x1400063b1  retn
0x1400063b2  mov     rcx, [rbp+188h]; this
0x1400063b9  mov     edx, 0A0Bh; void *
0x1400063be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400063c4  mov     rcx, [rbp+188h]; this
0x1400063cb  mov     edx, 0A0Bh; void *
0x1400063d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400063d6  mov     rcx, [rbp+188h]; this
0x1400063dd  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400063e3  mov     rcx, [rbp+188h]; this
0x1400063ea  mov     edx, 0A15h; void *
0x1400063ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400063f5  mov     rcx, [rbp+188h]; this
0x1400063fc  mov     edx, 0A0Bh; void *
0x140006401  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006407  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000640d  mov     rcx, [rbp+188h]; this
0x140006414  mov     edx, 0A0Bh; void *
0x140006419  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000641f  mov     rcx, [rbp+188h]; this
0x140006426  mov     edx, 0A0Bh; void *
0x14000642b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006431  mov     rcx, [rbp+188h]; this
0x140006438  mov     edx, 0A15h; void *
0x14000643d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006443  mov     rcx, [rbp+188h]; this
0x14000644a  mov     edx, 0A15h; void *
0x14000644f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
