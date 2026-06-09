# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004254`
- end: `0x18000461b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004eb0`

## callees

- `0x180003368`
- `0x180004254`
- `0x1800046b0`
- `0x180005218`
- `0x180006378`
- `0x1800070ec`
- `0x180008c84`
- `0x180009758`
- `0x180009bac`
- `0x18000b848`
- `0x18000b858`
- `0x180010792`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800044fd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800044fd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800042cb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800042cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000436d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004494`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004530`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000436d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004494`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004530`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800042ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800042ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004464`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004464`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004472`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000428d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000428d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000437e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000443e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004456`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004546`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000437e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000443e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004456`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004546`

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
0x180004254  mov     [rsp-8+arg_10], rbx
0x180004259  push    rbp
0x18000425a  push    rsi
0x18000425b  push    rdi
0x18000425c  push    r14
0x18000425e  push    r15
0x180004260  lea     rbp, [rsp-160h]
0x180004268  sub     rsp, 260h
0x18000426f  mov     rax, cs:__security_cookie
0x180004276  xor     rax, rsp
0x180004279  mov     [rbp+180h+var_30], rax
0x180004280  mov     r15, rdx
0x180004283  mov     qword ptr [rdx], 0
0x18000428a  mov     rbx, rcx
0x18000428d  call    cs:__imp_GetCurrentProcessId
0x180004293  mov     r14d, 130h
0x180004299  mov     [rsp+280h+var_258], rbx
0x18000429e  mov     r9d, eax
0x1800042a1  mov     [rsp+280h+var_260], r14d; int
0x1800042a6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800042ad  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800042b2  lea     edx, [r14-2Ch]; unsigned __int64
0x1800042b6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800042bb  mov     r9d, 1F0001h; dwDesiredAccess
0x1800042c1  lea     rdx, [rsp+280h+Name]; lpName
0x1800042c6  xor     r8d, r8d; dwFlags
0x1800042c9  xor     ecx, ecx; lpMutexAttributes
0x1800042cb  call    cs:__imp_CreateMutexExW
0x1800042d1  mov     rbx, rax
0x1800042d4  test    rax, rax
0x1800042d7  jnz     short loc_1800042E3
0x1800042d9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800042de  jmp     loc_180004552
0x1800042e3  xor     r8d, r8d; bAlertable
0x1800042e6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800042e9  mov     rcx, rbx; hHandle
0x1800042ec  call    cs:__imp_WaitForSingleObjectEx
0x1800042f2  cmp     eax, 102h
0x1800042f7  jz      short loc_180004309
0x1800042f9  test    eax, 0FFFFFF7Fh
0x1800042fe  jnz     loc_18000459C
0x180004304  mov     rdi, rbx
0x180004307  jmp     short loc_18000430B
0x180004309  xor     edi, edi
0x18000430b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004310  mov     [rsp+280h+hObject], 0
0x180004319  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000431e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004323  mov     esi, eax
0x180004325  test    eax, eax
0x180004327  jns     short loc_180004393
0x180004329  mov     rcx, [rbp+188h]; this
0x180004330  mov     r9d, eax; char *
0x180004333  mov     edx, 66h ; 'f'; void *
0x180004338  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000433d  mov     rcx, [rbp+188h]; this
0x180004344  mov     r9d, esi; char *
0x180004347  mov     edx, 6Fh ; 'o'; void *
0x18000434c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004351  mov     rcx, [rbp+188h]; this
0x180004358  mov     r9d, esi; char *
0x18000435b  mov     edx, 12Eh; void *
0x180004360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004365  test    rdi, rdi
0x180004368  jz      short loc_18000437B
0x18000436a  mov     rcx, rdi; hMutex
0x18000436d  call    cs:__imp_ReleaseMutex
0x180004373  test    eax, eax
0x180004375  jz      loc_1800045A9
0x18000437b  mov     rcx, rbx; hObject
0x18000437e  call    cs:__imp_CloseHandle
0x180004384  test    eax, eax
0x180004386  jz      loc_1800045BB
0x18000438c  mov     eax, esi
0x18000438e  jmp     loc_180004552
0x180004393  mov     rax, [rsp+280h+hObject]
0x180004398  lea     rcx, ds:0[rax*4]
0x1800043a0  test    rcx, rcx
0x1800043a3  jz      short loc_1800043B3
0x1800043a5  mov     [r15], rcx
0x1800043a8  mov     eax, [rcx]
0x1800043aa  inc     eax
0x1800043ac  mov     [rcx], eax
0x1800043ae  jmp     loc_180004528
0x1800043b3  mov     rdx, r14; dwBytes
0x1800043b6  mov     qword ptr [r15], 0
0x1800043bd  mov     ecx, 8; dwFlags
0x1800043c2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800043c7  mov     r14, rax
0x1800043ca  test    rax, rax
0x1800043cd  jnz     short loc_1800043ED
0x1800043cf  mov     rcx, [rbp+188h]; this
0x1800043d6  mov     esi, 8007000Eh
0x1800043db  mov     r9d, esi; char *
0x1800043de  mov     edx, 14Bh; void *
0x1800043e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043e8  jmp     loc_180004478
0x1800043ed  xorps   xmm0, xmm0
0x1800043f0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800043f6  test    r14b, 3
0x1800043fa  jnz     loc_1800045CD
0x180004400  mov     r9, r14
0x180004403  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004408  shr     r9, 2; unsigned __int64
0x18000440c  lea     rcx, [rsp+280h+hObject]; this
0x180004411  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004416  mov     esi, eax
0x180004418  test    eax, eax
0x18000441a  jns     loc_1800044B8
0x180004420  mov     rcx, [rbp+188h]; this
0x180004427  mov     r9d, eax; char *
0x18000442a  mov     edx, 14Eh; void *
0x18000442f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004434  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004439  test    rcx, rcx
0x18000443c  jz      short loc_18000444C
0x18000443e  call    cs:__imp_CloseHandle
0x180004444  test    eax, eax
0x180004446  jz      loc_1800045D3
0x18000444c  mov     rcx, [rsp+280h+hObject]; hObject
0x180004451  test    rcx, rcx
0x180004454  jz      short loc_180004464
0x180004456  call    cs:__imp_CloseHandle
0x18000445c  test    eax, eax
0x18000445e  jz      loc_1800045E5
0x180004464  call    cs:__imp_GetProcessHeap
0x18000446a  mov     r8, r14; lpMem
0x18000446d  xor     edx, edx; dwFlags
0x18000446f  mov     rcx, rax; hHeap
0x180004472  call    cs:__imp_HeapFree
0x180004478  mov     rcx, [rbp+188h]; this
0x18000447f  mov     r9d, esi; char *
0x180004482  mov     edx, 137h; void *
0x180004487  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000448c  test    rdi, rdi
0x18000448f  jz      short loc_1800044A2
0x180004491  mov     rcx, rdi; hMutex
0x180004494  call    cs:__imp_ReleaseMutex
0x18000449a  test    eax, eax
0x18000449c  jz      loc_1800045F7
0x1800044a2  mov     rcx, rbx; hObject
0x1800044a5  call    cs:__imp_CloseHandle
0x1800044ab  test    eax, eax
0x1800044ad  jz      loc_18000458A
0x1800044b3  jmp     loc_18000438C
0x1800044b8  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800044bd  lea     rcx, [r14+28h]; void *
0x1800044c1  mov     dword ptr [r14], 1
0x1800044c8  xor     edx, edx; Val
0x1800044ca  mov     [r14+8], rbx
0x1800044ce  mov     r8d, 108h; Size
0x1800044d4  movdqu  xmmword ptr [r14+10h], xmm0
0x1800044da  call    memset_0
0x1800044df  xor     eax, eax
0x1800044e1  lea     rcx, [r14+28h]; this
0x1800044e5  mov     [r14+20h], rax
0x1800044e9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800044ee  lea     rbx, [r14+0E8h]
0x1800044f5  xor     r8d, r8d; Flags
0x1800044f8  mov     rcx, rbx; lpCriticalSection
0x1800044fb  xor     edx, edx; dwSpinCount
0x1800044fd  call    cs:__imp_InitializeCriticalSectionEx
0x180004503  mov     qword ptr [rbx+28h], 0
0x18000450b  mov     qword ptr [rbx+30h], 0
0x180004513  mov     qword ptr [rbx+38h], 0
0x18000451b  mov     qword ptr [rbx+40h], 0
0x180004523  xor     ebx, ebx
0x180004525  mov     [r15], r14
0x180004528  test    rdi, rdi
0x18000452b  jz      short loc_18000453E
0x18000452d  mov     rcx, rdi; hMutex
0x180004530  call    cs:__imp_ReleaseMutex
0x180004536  test    eax, eax
0x180004538  jz      loc_180004609
0x18000453e  test    rbx, rbx
0x180004541  jz      short loc_180004550
0x180004543  mov     rcx, rbx; hObject
0x180004546  call    cs:__imp_CloseHandle
0x18000454c  test    eax, eax
0x18000454e  jz      short loc_180004578
0x180004550  xor     eax, eax
0x180004552  mov     rcx, [rbp+180h+var_30]
0x180004559  xor     rcx, rsp; StackCookie
0x18000455c  call    __security_check_cookie
0x180004561  mov     rbx, [rsp+280h+arg_10]
0x180004569  add     rsp, 260h
0x180004570  pop     r15
0x180004572  pop     r14
0x180004574  pop     rdi
0x180004575  pop     rsi
0x180004576  pop     rbp
0x180004577  retn
0x180004578  mov     rcx, [rbp+188h]; this
0x18000457f  mov     edx, 0A0Bh; void *
0x180004584  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000458a  mov     rcx, [rbp+188h]; this
0x180004591  mov     edx, 0A0Bh; void *
0x180004596  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000459c  mov     rcx, [rbp+188h]; this
0x1800045a3  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800045a9  mov     rcx, [rbp+188h]; this
0x1800045b0  mov     edx, 0A15h; void *
0x1800045b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800045bb  mov     rcx, [rbp+188h]; this
0x1800045c2  mov     edx, 0A0Bh; void *
0x1800045c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800045cd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800045d3  mov     rcx, [rbp+188h]; this
0x1800045da  mov     edx, 0A0Bh; void *
0x1800045df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800045e5  mov     rcx, [rbp+188h]; this
0x1800045ec  mov     edx, 0A0Bh; void *
0x1800045f1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800045f7  mov     rcx, [rbp+188h]; this
0x1800045fe  mov     edx, 0A15h; void *
0x180004603  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004609  mov     rcx, [rbp+188h]; this
0x180004610  mov     edx, 0A15h; void *
0x180004615  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
