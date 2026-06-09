# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003f9c`
- end: `0x180004363`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004634`

## callees

- `0x1800017c0`
- `0x180002570`
- `0x180003274`
- `0x180003f9c`
- `0x18000436c`
- `0x1800047c4`
- `0x1800050e8`
- `0x180005cd8`
- `0x180007004`
- `0x180007af8`
- `0x180007e4c`
- `0x18000862c`
- `0x18000863c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004013`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004013`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004034`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004034`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800041dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004278`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800041dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004278`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004245`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004245`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003fd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003fd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000419e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000428e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000419e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000428e`

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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x180003f9c  mov     [rsp-8+arg_10], rbx
0x180003fa1  push    rbp
0x180003fa2  push    rsi
0x180003fa3  push    rdi
0x180003fa4  push    r14
0x180003fa6  push    r15
0x180003fa8  lea     rbp, [rsp-160h]
0x180003fb0  sub     rsp, 260h
0x180003fb7  mov     rax, cs:__security_cookie
0x180003fbe  xor     rax, rsp
0x180003fc1  mov     [rbp+180h+var_30], rax
0x180003fc8  mov     r15, rdx
0x180003fcb  mov     qword ptr [rdx], 0
0x180003fd2  mov     rbx, rcx
0x180003fd5  call    cs:__imp_GetCurrentProcessId
0x180003fdb  mov     r14d, 130h
0x180003fe1  mov     [rsp+280h+var_258], rbx
0x180003fe6  mov     r9d, eax
0x180003fe9  mov     [rsp+280h+var_260], r14d; int
0x180003fee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003ff5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003ffa  lea     edx, [r14-2Ch]; unsigned __int64
0x180003ffe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004003  mov     r9d, 1F0001h; dwDesiredAccess
0x180004009  lea     rdx, [rsp+280h+Name]; lpName
0x18000400e  xor     r8d, r8d; dwFlags
0x180004011  xor     ecx, ecx; lpMutexAttributes
0x180004013  call    cs:__imp_CreateMutexExW
0x180004019  mov     rbx, rax
0x18000401c  test    rax, rax
0x18000401f  jnz     short loc_18000402B
0x180004021  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004026  jmp     loc_18000429A
0x18000402b  xor     r8d, r8d; bAlertable
0x18000402e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004031  mov     rcx, rbx; hHandle
0x180004034  call    cs:__imp_WaitForSingleObjectEx
0x18000403a  cmp     eax, 102h
0x18000403f  jz      short loc_180004051
0x180004041  test    eax, 0FFFFFF7Fh
0x180004046  jnz     loc_1800042E4
0x18000404c  mov     rdi, rbx
0x18000404f  jmp     short loc_180004053
0x180004051  xor     edi, edi
0x180004053  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004058  mov     [rsp+280h+hObject], 0
0x180004061  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004066  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000406b  mov     esi, eax
0x18000406d  test    eax, eax
0x18000406f  jns     short loc_1800040DB
0x180004071  mov     rcx, [rbp+188h]; this
0x180004078  mov     r9d, eax; char *
0x18000407b  mov     edx, 66h ; 'f'; void *
0x180004080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004085  mov     rcx, [rbp+188h]; this
0x18000408c  mov     r9d, esi; char *
0x18000408f  mov     edx, 6Fh ; 'o'; void *
0x180004094  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004099  mov     rcx, [rbp+188h]; this
0x1800040a0  mov     r9d, esi; char *
0x1800040a3  mov     edx, 12Eh; void *
0x1800040a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040ad  test    rdi, rdi
0x1800040b0  jz      short loc_1800040C3
0x1800040b2  mov     rcx, rdi; hMutex
0x1800040b5  call    cs:__imp_ReleaseMutex
0x1800040bb  test    eax, eax
0x1800040bd  jz      loc_1800042F1
0x1800040c3  mov     rcx, rbx; hObject
0x1800040c6  call    cs:__imp_CloseHandle
0x1800040cc  test    eax, eax
0x1800040ce  jz      loc_180004303
0x1800040d4  mov     eax, esi
0x1800040d6  jmp     loc_18000429A
0x1800040db  mov     rax, [rsp+280h+hObject]
0x1800040e0  lea     rcx, ds:0[rax*4]
0x1800040e8  test    rcx, rcx
0x1800040eb  jz      short loc_1800040FB
0x1800040ed  mov     [r15], rcx
0x1800040f0  mov     eax, [rcx]
0x1800040f2  inc     eax
0x1800040f4  mov     [rcx], eax
0x1800040f6  jmp     loc_180004270
0x1800040fb  mov     rdx, r14; dwBytes
0x1800040fe  mov     qword ptr [r15], 0
0x180004105  mov     ecx, 8; dwFlags
0x18000410a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000410f  mov     r14, rax
0x180004112  test    rax, rax
0x180004115  jnz     short loc_180004135
0x180004117  mov     rcx, [rbp+188h]; this
0x18000411e  mov     esi, 8007000Eh
0x180004123  mov     r9d, esi; char *
0x180004126  mov     edx, 14Bh; void *
0x18000412b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004130  jmp     loc_1800041C0
0x180004135  xorps   xmm0, xmm0
0x180004138  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000413e  test    r14b, 3
0x180004142  jnz     loc_180004315
0x180004148  mov     r9, r14
0x18000414b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004150  shr     r9, 2; unsigned __int64
0x180004154  lea     rcx, [rsp+280h+hObject]; this
0x180004159  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000415e  mov     esi, eax
0x180004160  test    eax, eax
0x180004162  jns     loc_180004200
0x180004168  mov     rcx, [rbp+188h]; this
0x18000416f  mov     r9d, eax; char *
0x180004172  mov     edx, 14Eh; void *
0x180004177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000417c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004181  test    rcx, rcx
0x180004184  jz      short loc_180004194
0x180004186  call    cs:__imp_CloseHandle
0x18000418c  test    eax, eax
0x18000418e  jz      loc_18000431B
0x180004194  mov     rcx, [rsp+280h+hObject]; hObject
0x180004199  test    rcx, rcx
0x18000419c  jz      short loc_1800041AC
0x18000419e  call    cs:__imp_CloseHandle
0x1800041a4  test    eax, eax
0x1800041a6  jz      loc_18000432D
0x1800041ac  call    cs:__imp_GetProcessHeap
0x1800041b2  mov     r8, r14; lpMem
0x1800041b5  xor     edx, edx; dwFlags
0x1800041b7  mov     rcx, rax; hHeap
0x1800041ba  call    cs:__imp_HeapFree
0x1800041c0  mov     rcx, [rbp+188h]; this
0x1800041c7  mov     r9d, esi; char *
0x1800041ca  mov     edx, 137h; void *
0x1800041cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041d4  test    rdi, rdi
0x1800041d7  jz      short loc_1800041EA
0x1800041d9  mov     rcx, rdi; hMutex
0x1800041dc  call    cs:__imp_ReleaseMutex
0x1800041e2  test    eax, eax
0x1800041e4  jz      loc_18000433F
0x1800041ea  mov     rcx, rbx; hObject
0x1800041ed  call    cs:__imp_CloseHandle
0x1800041f3  test    eax, eax
0x1800041f5  jz      loc_1800042D2
0x1800041fb  jmp     loc_1800040D4
0x180004200  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004205  lea     rcx, [r14+28h]; void *
0x180004209  mov     dword ptr [r14], 1
0x180004210  xor     edx, edx; Val
0x180004212  mov     [r14+8], rbx
0x180004216  mov     r8d, 108h; Size
0x18000421c  movdqu  xmmword ptr [r14+10h], xmm0
0x180004222  call    memset_0
0x180004227  xor     eax, eax
0x180004229  lea     rcx, [r14+28h]; this
0x18000422d  mov     [r14+20h], rax
0x180004231  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004236  lea     rbx, [r14+0E8h]
0x18000423d  xor     r8d, r8d; Flags
0x180004240  mov     rcx, rbx; lpCriticalSection
0x180004243  xor     edx, edx; dwSpinCount
0x180004245  call    cs:__imp_InitializeCriticalSectionEx
0x18000424b  mov     qword ptr [rbx+28h], 0
0x180004253  mov     qword ptr [rbx+30h], 0
0x18000425b  mov     qword ptr [rbx+38h], 0
0x180004263  mov     qword ptr [rbx+40h], 0
0x18000426b  xor     ebx, ebx
0x18000426d  mov     [r15], r14
0x180004270  test    rdi, rdi
0x180004273  jz      short loc_180004286
0x180004275  mov     rcx, rdi; hMutex
0x180004278  call    cs:__imp_ReleaseMutex
0x18000427e  test    eax, eax
0x180004280  jz      loc_180004351
0x180004286  test    rbx, rbx
0x180004289  jz      short loc_180004298
0x18000428b  mov     rcx, rbx; hObject
0x18000428e  call    cs:__imp_CloseHandle
0x180004294  test    eax, eax
0x180004296  jz      short loc_1800042C0
0x180004298  xor     eax, eax
0x18000429a  mov     rcx, [rbp+180h+var_30]
0x1800042a1  xor     rcx, rsp; StackCookie
0x1800042a4  call    __security_check_cookie
0x1800042a9  mov     rbx, [rsp+280h+arg_10]
0x1800042b1  add     rsp, 260h
0x1800042b8  pop     r15
0x1800042ba  pop     r14
0x1800042bc  pop     rdi
0x1800042bd  pop     rsi
0x1800042be  pop     rbp
0x1800042bf  retn
0x1800042c0  mov     rcx, [rbp+188h]; this
0x1800042c7  mov     edx, 0A0Bh; void *
0x1800042cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042d2  mov     rcx, [rbp+188h]; this
0x1800042d9  mov     edx, 0A0Bh; void *
0x1800042de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042e4  mov     rcx, [rbp+188h]; this
0x1800042eb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800042f1  mov     rcx, [rbp+188h]; this
0x1800042f8  mov     edx, 0A15h; void *
0x1800042fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004303  mov     rcx, [rbp+188h]; this
0x18000430a  mov     edx, 0A0Bh; void *
0x18000430f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004315  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000431b  mov     rcx, [rbp+188h]; this
0x180004322  mov     edx, 0A0Bh; void *
0x180004327  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000432d  mov     rcx, [rbp+188h]; this
0x180004334  mov     edx, 0A0Bh; void *
0x180004339  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000433f  mov     rcx, [rbp+188h]; this
0x180004346  mov     edx, 0A15h; void *
0x18000434b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004351  mov     rcx, [rbp+188h]; this
0x180004358  mov     edx, 0A15h; void *
0x18000435d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
