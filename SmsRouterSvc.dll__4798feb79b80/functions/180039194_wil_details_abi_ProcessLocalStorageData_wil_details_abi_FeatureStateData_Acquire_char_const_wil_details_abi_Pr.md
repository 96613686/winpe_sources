# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180039194`
- end: `0x180039585`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18003958c`

## callees

- `0x180003a60`
- `0x180004998`
- `0x1800071c8`
- `0x1800074b4`
- `0x180007b18`
- `0x1800085f8`
- `0x1800089e4`
- `0x1800093d4`
- `0x18000948c`
- `0x18000986c`
- `0x18000987c`
- `0x18003897c`
- `0x180039194`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003920b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003920b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003922c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003922c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180039467`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180039467`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800392c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800393fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003949a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800392c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800393fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003949a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800393c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800393c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800393d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800393d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800391cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800391cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800392d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800393a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800393b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003940f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800394b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800392d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800393a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800393b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003940f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800394b0`

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
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
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
0x180039194  mov     [rsp-8+arg_10], rbx
0x180039199  push    rbp
0x18003919a  push    rsi
0x18003919b  push    rdi
0x18003919c  push    r14
0x18003919e  push    r15
0x1800391a0  lea     rbp, [rsp-160h]
0x1800391a8  sub     rsp, 260h
0x1800391af  mov     rax, cs:__security_cookie
0x1800391b6  xor     rax, rsp
0x1800391b9  mov     [rbp+180h+var_30], rax
0x1800391c0  mov     r15, rdx
0x1800391c3  mov     qword ptr [rdx], 0
0x1800391ca  mov     rbx, rcx
0x1800391cd  call    cs:__imp_GetCurrentProcessId
0x1800391d3  mov     r14d, 130h
0x1800391d9  mov     [rsp+280h+var_258], rbx
0x1800391de  mov     r9d, eax
0x1800391e1  mov     [rsp+280h+var_260], r14d; int
0x1800391e6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800391ed  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800391f2  lea     edx, [r14-2Ch]; unsigned __int64
0x1800391f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800391fb  mov     r9d, 1F0001h; dwDesiredAccess
0x180039201  lea     rdx, [rsp+280h+Name]; lpName
0x180039206  xor     r8d, r8d; dwFlags
0x180039209  xor     ecx, ecx; lpMutexAttributes
0x18003920b  call    cs:__imp_CreateMutexExW
0x180039211  mov     rbx, rax
0x180039214  test    rax, rax
0x180039217  jnz     short loc_180039223
0x180039219  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003921e  jmp     loc_1800394BC
0x180039223  xor     r8d, r8d; bAlertable
0x180039226  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180039229  mov     rcx, rbx; hHandle
0x18003922c  call    cs:__imp_WaitForSingleObjectEx
0x180039232  cmp     eax, 102h
0x180039237  jz      short loc_180039249
0x180039239  test    eax, 0FFFFFF7Fh
0x18003923e  jnz     loc_180039506
0x180039244  mov     rdi, rbx
0x180039247  jmp     short loc_18003924B
0x180039249  xor     edi, edi
0x18003924b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180039250  mov     [rsp+280h+hObject], 0
0x180039259  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003925e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180039263  mov     esi, eax
0x180039265  test    eax, eax
0x180039267  jns     short loc_1800392E8
0x180039269  mov     rcx, [rbp+188h]; this
0x180039270  lea     r8, aWil; "wil"
0x180039277  mov     r9d, eax; char *
0x18003927a  mov     edx, 66h ; 'f'; void *
0x18003927f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039284  mov     rcx, [rbp+188h]; this
0x18003928b  lea     r8, aWil; "wil"
0x180039292  mov     r9d, esi; char *
0x180039295  mov     edx, 6Fh ; 'o'; void *
0x18003929a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003929f  mov     rcx, [rbp+188h]; this
0x1800392a6  lea     r8, aWil; "wil"
0x1800392ad  mov     r9d, esi; char *
0x1800392b0  mov     edx, 12Eh; void *
0x1800392b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800392ba  test    rdi, rdi
0x1800392bd  jz      short loc_1800392D0
0x1800392bf  mov     rcx, rdi; hMutex
0x1800392c2  call    cs:__imp_ReleaseMutex
0x1800392c8  test    eax, eax
0x1800392ca  jz      loc_180039513
0x1800392d0  mov     rcx, rbx; hObject
0x1800392d3  call    cs:__imp_CloseHandle
0x1800392d9  test    eax, eax
0x1800392db  jz      loc_180039525
0x1800392e1  mov     eax, esi
0x1800392e3  jmp     loc_1800394BC
0x1800392e8  mov     rax, [rsp+280h+hObject]
0x1800392ed  lea     rcx, ds:0[rax*4]
0x1800392f5  test    rcx, rcx
0x1800392f8  jz      short loc_180039308
0x1800392fa  mov     [r15], rcx
0x1800392fd  mov     eax, [rcx]
0x1800392ff  inc     eax
0x180039301  mov     [rcx], eax
0x180039303  jmp     loc_180039492
0x180039308  mov     rdx, r14; dwBytes
0x18003930b  mov     qword ptr [r15], 0
0x180039312  mov     ecx, 8; dwFlags
0x180039317  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18003931c  mov     r14, rax
0x18003931f  test    rax, rax
0x180039322  jnz     short loc_180039349
0x180039324  mov     rcx, [rbp+188h]; this
0x18003932b  lea     r8, aWil; "wil"
0x180039332  mov     esi, 8007000Eh
0x180039337  mov     edx, 14Bh; void *
0x18003933c  mov     r9d, esi; char *
0x18003933f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039344  jmp     loc_1800393DB
0x180039349  xorps   xmm0, xmm0
0x18003934c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180039352  test    r14b, 3
0x180039356  jnz     loc_180039537
0x18003935c  mov     r9, r14
0x18003935f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180039364  shr     r9, 2; unsigned __int64
0x180039368  lea     rcx, [rsp+280h+hObject]; this
0x18003936d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180039372  mov     esi, eax
0x180039374  test    eax, eax
0x180039376  jns     loc_180039422
0x18003937c  mov     rcx, [rbp+188h]; this
0x180039383  lea     r8, aWil; "wil"
0x18003938a  mov     r9d, eax; char *
0x18003938d  mov     edx, 14Eh; void *
0x180039392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039397  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18003939c  test    rcx, rcx
0x18003939f  jz      short loc_1800393AF
0x1800393a1  call    cs:__imp_CloseHandle
0x1800393a7  test    eax, eax
0x1800393a9  jz      loc_18003953D
0x1800393af  mov     rcx, [rsp+280h+hObject]; hObject
0x1800393b4  test    rcx, rcx
0x1800393b7  jz      short loc_1800393C7
0x1800393b9  call    cs:__imp_CloseHandle
0x1800393bf  test    eax, eax
0x1800393c1  jz      loc_18003954F
0x1800393c7  call    cs:__imp_GetProcessHeap
0x1800393cd  mov     r8, r14; lpMem
0x1800393d0  xor     edx, edx; dwFlags
0x1800393d2  mov     rcx, rax; hHeap
0x1800393d5  call    cs:__imp_HeapFree
0x1800393db  mov     rcx, [rbp+188h]; this
0x1800393e2  lea     r8, aWil; "wil"
0x1800393e9  mov     r9d, esi; char *
0x1800393ec  mov     edx, 137h; void *
0x1800393f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800393f6  test    rdi, rdi
0x1800393f9  jz      short loc_18003940C
0x1800393fb  mov     rcx, rdi; hMutex
0x1800393fe  call    cs:__imp_ReleaseMutex
0x180039404  test    eax, eax
0x180039406  jz      loc_180039561
0x18003940c  mov     rcx, rbx; hObject
0x18003940f  call    cs:__imp_CloseHandle
0x180039415  test    eax, eax
0x180039417  jz      loc_1800394F4
0x18003941d  jmp     loc_1800392E1
0x180039422  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180039427  lea     rcx, [r14+28h]; void *
0x18003942b  mov     dword ptr [r14], 1
0x180039432  xor     edx, edx; Val
0x180039434  mov     [r14+8], rbx
0x180039438  mov     r8d, 108h; Size
0x18003943e  movdqu  xmmword ptr [r14+10h], xmm0
0x180039444  call    memset_0
0x180039449  xor     eax, eax
0x18003944b  lea     rcx, [r14+28h]; this
0x18003944f  mov     [r14+20h], rax
0x180039453  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180039458  lea     rbx, [r14+0E8h]
0x18003945f  xor     r8d, r8d; Flags
0x180039462  mov     rcx, rbx; lpCriticalSection
0x180039465  xor     edx, edx; dwSpinCount
0x180039467  call    cs:__imp_InitializeCriticalSectionEx
0x18003946d  mov     qword ptr [rbx+28h], 0
0x180039475  mov     qword ptr [rbx+30h], 0
0x18003947d  mov     qword ptr [rbx+38h], 0
0x180039485  mov     qword ptr [rbx+40h], 0
0x18003948d  xor     ebx, ebx
0x18003948f  mov     [r15], r14
0x180039492  test    rdi, rdi
0x180039495  jz      short loc_1800394A8
0x180039497  mov     rcx, rdi; hMutex
0x18003949a  call    cs:__imp_ReleaseMutex
0x1800394a0  test    eax, eax
0x1800394a2  jz      loc_180039573
0x1800394a8  test    rbx, rbx
0x1800394ab  jz      short loc_1800394BA
0x1800394ad  mov     rcx, rbx; hObject
0x1800394b0  call    cs:__imp_CloseHandle
0x1800394b6  test    eax, eax
0x1800394b8  jz      short loc_1800394E2
0x1800394ba  xor     eax, eax
0x1800394bc  mov     rcx, [rbp+180h+var_30]
0x1800394c3  xor     rcx, rsp; StackCookie
0x1800394c6  call    __security_check_cookie
0x1800394cb  mov     rbx, [rsp+280h+arg_10]
0x1800394d3  add     rsp, 260h
0x1800394da  pop     r15
0x1800394dc  pop     r14
0x1800394de  pop     rdi
0x1800394df  pop     rsi
0x1800394e0  pop     rbp
0x1800394e1  retn
0x1800394e2  mov     rcx, [rbp+188h]; this
0x1800394e9  mov     edx, 0A0Bh; void *
0x1800394ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800394f4  mov     rcx, [rbp+188h]; this
0x1800394fb  mov     edx, 0A0Bh; void *
0x180039500  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180039506  mov     rcx, [rbp+188h]; this
0x18003950d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180039513  mov     rcx, [rbp+188h]; this
0x18003951a  mov     edx, 0A15h; void *
0x18003951f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180039525  mov     rcx, [rbp+188h]; this
0x18003952c  mov     edx, 0A0Bh; void *
0x180039531  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180039537  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003953d  mov     rcx, [rbp+188h]; this
0x180039544  mov     edx, 0A0Bh; void *
0x180039549  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003954f  mov     rcx, [rbp+188h]; this
0x180039556  mov     edx, 0A0Bh; void *
0x18003955b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180039561  mov     rcx, [rbp+188h]; this
0x180039568  mov     edx, 0A15h; void *
0x18003956d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180039573  mov     rcx, [rbp+188h]; this
0x18003957a  mov     edx, 0A15h; void *
0x18003957f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
