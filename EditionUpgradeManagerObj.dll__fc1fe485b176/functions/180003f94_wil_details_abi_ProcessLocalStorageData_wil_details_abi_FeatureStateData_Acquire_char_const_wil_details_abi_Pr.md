# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003f94`
- end: `0x180004385`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004674`

## callees

- `0x180001ac0`
- `0x1800026b4`
- `0x180003320`
- `0x180003f94`
- `0x18000438c`
- `0x1800048c8`
- `0x1800051f8`
- `0x180005ea8`
- `0x180007434`
- `0x180007970`
- `0x180007e20`
- `0x1800086ec`
- `0x1800086fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004267`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004267`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000400b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000400b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800041fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000429a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800041fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000429a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000402c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000402c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003fcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003fcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000420f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000420f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042b0`

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
0x180003f94  mov     [rsp-8+arg_10], rbx
0x180003f99  push    rbp
0x180003f9a  push    rsi
0x180003f9b  push    rdi
0x180003f9c  push    r14
0x180003f9e  push    r15
0x180003fa0  lea     rbp, [rsp-160h]
0x180003fa8  sub     rsp, 260h
0x180003faf  mov     rax, cs:__security_cookie
0x180003fb6  xor     rax, rsp
0x180003fb9  mov     [rbp+180h+var_30], rax
0x180003fc0  mov     r15, rdx
0x180003fc3  mov     qword ptr [rdx], 0
0x180003fca  mov     rbx, rcx
0x180003fcd  call    cs:__imp_GetCurrentProcessId
0x180003fd3  mov     r14d, 130h
0x180003fd9  mov     [rsp+280h+var_258], rbx
0x180003fde  mov     r9d, eax
0x180003fe1  mov     [rsp+280h+var_260], r14d; int
0x180003fe6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003fed  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003ff2  lea     edx, [r14-2Ch]; unsigned __int64
0x180003ff6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003ffb  mov     r9d, 1F0001h; dwDesiredAccess
0x180004001  lea     rdx, [rsp+280h+Name]; lpName
0x180004006  xor     r8d, r8d; dwFlags
0x180004009  xor     ecx, ecx; lpMutexAttributes
0x18000400b  call    cs:__imp_CreateMutexExW
0x180004011  mov     rbx, rax
0x180004014  test    rax, rax
0x180004017  jnz     short loc_180004023
0x180004019  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000401e  jmp     loc_1800042BC
0x180004023  xor     r8d, r8d; bAlertable
0x180004026  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004029  mov     rcx, rbx; hHandle
0x18000402c  call    cs:__imp_WaitForSingleObjectEx
0x180004032  cmp     eax, 102h
0x180004037  jz      short loc_180004049
0x180004039  test    eax, 0FFFFFF7Fh
0x18000403e  jnz     loc_180004306
0x180004044  mov     rdi, rbx
0x180004047  jmp     short loc_18000404B
0x180004049  xor     edi, edi
0x18000404b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004050  mov     [rsp+280h+hObject], 0
0x180004059  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000405e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004063  mov     esi, eax
0x180004065  test    eax, eax
0x180004067  jns     short loc_1800040E8
0x180004069  mov     rcx, [rbp+188h]; this
0x180004070  lea     r8, aWil; "wil"
0x180004077  mov     r9d, eax; char *
0x18000407a  mov     edx, 66h ; 'f'; void *
0x18000407f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004084  mov     rcx, [rbp+188h]; this
0x18000408b  lea     r8, aWil; "wil"
0x180004092  mov     r9d, esi; char *
0x180004095  mov     edx, 6Fh ; 'o'; void *
0x18000409a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000409f  mov     rcx, [rbp+188h]; this
0x1800040a6  lea     r8, aWil; "wil"
0x1800040ad  mov     r9d, esi; char *
0x1800040b0  mov     edx, 12Eh; void *
0x1800040b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040ba  test    rdi, rdi
0x1800040bd  jz      short loc_1800040D0
0x1800040bf  mov     rcx, rdi; hMutex
0x1800040c2  call    cs:__imp_ReleaseMutex
0x1800040c8  test    eax, eax
0x1800040ca  jz      loc_180004313
0x1800040d0  mov     rcx, rbx; hObject
0x1800040d3  call    cs:__imp_CloseHandle
0x1800040d9  test    eax, eax
0x1800040db  jz      loc_180004325
0x1800040e1  mov     eax, esi
0x1800040e3  jmp     loc_1800042BC
0x1800040e8  mov     rax, [rsp+280h+hObject]
0x1800040ed  lea     rcx, ds:0[rax*4]
0x1800040f5  test    rcx, rcx
0x1800040f8  jz      short loc_180004108
0x1800040fa  mov     [r15], rcx
0x1800040fd  mov     eax, [rcx]
0x1800040ff  inc     eax
0x180004101  mov     [rcx], eax
0x180004103  jmp     loc_180004292
0x180004108  mov     rdx, r14; dwBytes
0x18000410b  mov     qword ptr [r15], 0
0x180004112  mov     ecx, 8; dwFlags
0x180004117  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000411c  mov     r14, rax
0x18000411f  test    rax, rax
0x180004122  jnz     short loc_180004149
0x180004124  mov     rcx, [rbp+188h]; this
0x18000412b  lea     r8, aWil; "wil"
0x180004132  mov     esi, 8007000Eh
0x180004137  mov     edx, 14Bh; void *
0x18000413c  mov     r9d, esi; char *
0x18000413f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004144  jmp     loc_1800041DB
0x180004149  xorps   xmm0, xmm0
0x18000414c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004152  test    r14b, 3
0x180004156  jnz     loc_180004337
0x18000415c  mov     r9, r14
0x18000415f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004164  shr     r9, 2; unsigned __int64
0x180004168  lea     rcx, [rsp+280h+hObject]; this
0x18000416d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004172  mov     esi, eax
0x180004174  test    eax, eax
0x180004176  jns     loc_180004222
0x18000417c  mov     rcx, [rbp+188h]; this
0x180004183  lea     r8, aWil; "wil"
0x18000418a  mov     r9d, eax; char *
0x18000418d  mov     edx, 14Eh; void *
0x180004192  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004197  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000419c  test    rcx, rcx
0x18000419f  jz      short loc_1800041AF
0x1800041a1  call    cs:__imp_CloseHandle
0x1800041a7  test    eax, eax
0x1800041a9  jz      loc_18000433D
0x1800041af  mov     rcx, [rsp+280h+hObject]; hObject
0x1800041b4  test    rcx, rcx
0x1800041b7  jz      short loc_1800041C7
0x1800041b9  call    cs:__imp_CloseHandle
0x1800041bf  test    eax, eax
0x1800041c1  jz      loc_18000434F
0x1800041c7  call    cs:__imp_GetProcessHeap
0x1800041cd  mov     r8, r14; lpMem
0x1800041d0  xor     edx, edx; dwFlags
0x1800041d2  mov     rcx, rax; hHeap
0x1800041d5  call    cs:__imp_HeapFree
0x1800041db  mov     rcx, [rbp+188h]; this
0x1800041e2  lea     r8, aWil; "wil"
0x1800041e9  mov     r9d, esi; char *
0x1800041ec  mov     edx, 137h; void *
0x1800041f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041f6  test    rdi, rdi
0x1800041f9  jz      short loc_18000420C
0x1800041fb  mov     rcx, rdi; hMutex
0x1800041fe  call    cs:__imp_ReleaseMutex
0x180004204  test    eax, eax
0x180004206  jz      loc_180004361
0x18000420c  mov     rcx, rbx; hObject
0x18000420f  call    cs:__imp_CloseHandle
0x180004215  test    eax, eax
0x180004217  jz      loc_1800042F4
0x18000421d  jmp     loc_1800040E1
0x180004222  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004227  lea     rcx, [r14+28h]; void *
0x18000422b  mov     dword ptr [r14], 1
0x180004232  xor     edx, edx; Val
0x180004234  mov     [r14+8], rbx
0x180004238  mov     r8d, 108h; Size
0x18000423e  movdqu  xmmword ptr [r14+10h], xmm0
0x180004244  call    memset_0
0x180004249  xor     eax, eax
0x18000424b  lea     rcx, [r14+28h]; this
0x18000424f  mov     [r14+20h], rax
0x180004253  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004258  lea     rbx, [r14+0E8h]
0x18000425f  xor     r8d, r8d; Flags
0x180004262  mov     rcx, rbx; lpCriticalSection
0x180004265  xor     edx, edx; dwSpinCount
0x180004267  call    cs:__imp_InitializeCriticalSectionEx
0x18000426d  mov     qword ptr [rbx+28h], 0
0x180004275  mov     qword ptr [rbx+30h], 0
0x18000427d  mov     qword ptr [rbx+38h], 0
0x180004285  mov     qword ptr [rbx+40h], 0
0x18000428d  xor     ebx, ebx
0x18000428f  mov     [r15], r14
0x180004292  test    rdi, rdi
0x180004295  jz      short loc_1800042A8
0x180004297  mov     rcx, rdi; hMutex
0x18000429a  call    cs:__imp_ReleaseMutex
0x1800042a0  test    eax, eax
0x1800042a2  jz      loc_180004373
0x1800042a8  test    rbx, rbx
0x1800042ab  jz      short loc_1800042BA
0x1800042ad  mov     rcx, rbx; hObject
0x1800042b0  call    cs:__imp_CloseHandle
0x1800042b6  test    eax, eax
0x1800042b8  jz      short loc_1800042E2
0x1800042ba  xor     eax, eax
0x1800042bc  mov     rcx, [rbp+180h+var_30]
0x1800042c3  xor     rcx, rsp; StackCookie
0x1800042c6  call    __security_check_cookie
0x1800042cb  mov     rbx, [rsp+280h+arg_10]
0x1800042d3  add     rsp, 260h
0x1800042da  pop     r15
0x1800042dc  pop     r14
0x1800042de  pop     rdi
0x1800042df  pop     rsi
0x1800042e0  pop     rbp
0x1800042e1  retn
0x1800042e2  mov     rcx, [rbp+188h]; this
0x1800042e9  mov     edx, 0A0Bh; void *
0x1800042ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042f4  mov     rcx, [rbp+188h]; this
0x1800042fb  mov     edx, 0A0Bh; void *
0x180004300  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004306  mov     rcx, [rbp+188h]; this
0x18000430d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004313  mov     rcx, [rbp+188h]; this
0x18000431a  mov     edx, 0A15h; void *
0x18000431f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004325  mov     rcx, [rbp+188h]; this
0x18000432c  mov     edx, 0A0Bh; void *
0x180004331  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004337  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000433d  mov     rcx, [rbp+188h]; this
0x180004344  mov     edx, 0A0Bh; void *
0x180004349  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000434f  mov     rcx, [rbp+188h]; this
0x180004356  mov     edx, 0A0Bh; void *
0x18000435b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004361  mov     rcx, [rbp+188h]; this
0x180004368  mov     edx, 0A15h; void *
0x18000436d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004373  mov     rcx, [rbp+188h]; this
0x18000437a  mov     edx, 0A15h; void *
0x18000437f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
