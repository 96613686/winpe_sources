# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800071fc`
- end: `0x1800075f2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1014`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800079d4`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x1800061b0`
- `0x1800071fc`
- `0x1800076e8`
- `0x180007d5c`
- `0x1800088b0`
- `0x1800098e4`
- `0x18000b29c`
- `0x18000bed0`
- `0x18000c35c`
- `0x18000cce0`
- `0x18000ccf0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180007273`
- `KERNEL32!CreateMutexExW` at `0x180007273`
- `KERNEL32!GetCurrentProcessId` at `0x180007235`
- `KERNEL32!GetCurrentProcessId` at `0x180007235`
- `KERNEL32!GetProcessHeap` at `0x18000742f`
- `KERNEL32!GetProcessHeap` at `0x18000742f`
- `KERNEL32!WaitForSingleObjectEx` at `0x180007294`
- `KERNEL32!WaitForSingleObjectEx` at `0x180007294`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800074cf`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800074cf`
- `KERNEL32!ReleaseMutex` at `0x18000732a`
- `KERNEL32!ReleaseMutex` at `0x180007466`
- `KERNEL32!ReleaseMutex` at `0x180007502`
- `KERNEL32!ReleaseMutex` at `0x18000732a`
- `KERNEL32!ReleaseMutex` at `0x180007466`
- `KERNEL32!ReleaseMutex` at `0x180007502`
- `KERNEL32!HeapFree` at `0x18000743d`
- `KERNEL32!HeapFree` at `0x18000743d`
- `KERNEL32!CloseHandle` at `0x18000733b`
- `KERNEL32!CloseHandle` at `0x180007409`
- `KERNEL32!CloseHandle` at `0x180007421`
- `KERNEL32!CloseHandle` at `0x180007477`
- `KERNEL32!CloseHandle` at `0x180007518`
- `KERNEL32!CloseHandle` at `0x18000733b`
- `KERNEL32!CloseHandle` at `0x180007409`
- `KERNEL32!CloseHandle` at `0x180007421`
- `KERNEL32!CloseHandle` at `0x180007477`
- `KERNEL32!CloseHandle` at `0x180007518`

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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x1800071fc  mov     [rsp-8+arg_10], rbx
0x180007201  push    rbp
0x180007202  push    rsi
0x180007203  push    rdi
0x180007204  push    r14
0x180007206  push    r15
0x180007208  lea     rbp, [rsp-160h]
0x180007210  sub     rsp, 260h
0x180007217  mov     rax, cs:__security_cookie
0x18000721e  xor     rax, rsp
0x180007221  mov     [rbp+180h+var_30], rax
0x180007228  mov     r15, rdx
0x18000722b  mov     qword ptr [rdx], 0
0x180007232  mov     rbx, rcx
0x180007235  call    cs:__imp_GetCurrentProcessId
0x18000723b  mov     r14d, 130h
0x180007241  mov     [rsp+280h+var_258], rbx
0x180007246  mov     r9d, eax
0x180007249  mov     [rsp+280h+var_260], r14d; int
0x18000724e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007255  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000725a  lea     edx, [r14-2Ch]; unsigned __int64
0x18000725e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007263  mov     r9d, 1F0001h; dwDesiredAccess
0x180007269  lea     rdx, [rsp+280h+Name]; lpName
0x18000726e  xor     r8d, r8d; dwFlags
0x180007271  xor     ecx, ecx; lpMutexAttributes
0x180007273  call    cs:__imp_CreateMutexExW
0x180007279  mov     rbx, rax
0x18000727c  test    rax, rax
0x18000727f  jnz     short loc_18000728B
0x180007281  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007286  jmp     loc_180007524
0x18000728b  xor     r8d, r8d; bAlertable
0x18000728e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007291  mov     rcx, rbx; hHandle
0x180007294  call    cs:__imp_WaitForSingleObjectEx
0x18000729a  cmp     eax, 102h
0x18000729f  jz      short loc_1800072B1
0x1800072a1  test    eax, 0FFFFFF7Fh
0x1800072a6  jnz     loc_18000756E
0x1800072ac  mov     rdi, rbx
0x1800072af  jmp     short loc_1800072B3
0x1800072b1  xor     edi, edi
0x1800072b3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800072b8  mov     [rsp+280h+hObject], 0
0x1800072c1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800072c6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800072cb  mov     esi, eax
0x1800072cd  test    eax, eax
0x1800072cf  jns     short loc_180007350
0x1800072d1  mov     rcx, [rbp+188h]; this
0x1800072d8  lea     r8, aWil; "wil"
0x1800072df  mov     r9d, eax; char *
0x1800072e2  mov     edx, 66h ; 'f'; void *
0x1800072e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072ec  mov     rcx, [rbp+188h]; this
0x1800072f3  lea     r8, aWil; "wil"
0x1800072fa  mov     r9d, esi; char *
0x1800072fd  mov     edx, 6Fh ; 'o'; void *
0x180007302  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007307  mov     rcx, [rbp+188h]; this
0x18000730e  lea     r8, aWil; "wil"
0x180007315  mov     r9d, esi; char *
0x180007318  mov     edx, 12Eh; void *
0x18000731d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007322  test    rdi, rdi
0x180007325  jz      short loc_180007338
0x180007327  mov     rcx, rdi; hMutex
0x18000732a  call    cs:__imp_ReleaseMutex
0x180007330  test    eax, eax
0x180007332  jz      loc_180007580
0x180007338  mov     rcx, rbx; hObject
0x18000733b  call    cs:__imp_CloseHandle
0x180007341  test    eax, eax
0x180007343  jz      loc_180007592
0x180007349  mov     eax, esi
0x18000734b  jmp     loc_180007524
0x180007350  mov     rax, [rsp+280h+hObject]
0x180007355  lea     rcx, ds:0[rax*4]
0x18000735d  test    rcx, rcx
0x180007360  jz      short loc_180007370
0x180007362  mov     [r15], rcx
0x180007365  mov     eax, [rcx]
0x180007367  inc     eax
0x180007369  mov     [rcx], eax
0x18000736b  jmp     loc_1800074FA
0x180007370  mov     rdx, r14; dwBytes
0x180007373  mov     qword ptr [r15], 0
0x18000737a  mov     ecx, 8; dwFlags
0x18000737f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007384  mov     r14, rax
0x180007387  test    rax, rax
0x18000738a  jnz     short loc_1800073B1
0x18000738c  mov     rcx, [rbp+188h]; this
0x180007393  lea     r8, aWil; "wil"
0x18000739a  mov     esi, 8007000Eh
0x18000739f  mov     edx, 14Bh; void *
0x1800073a4  mov     r9d, esi; char *
0x1800073a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073ac  jmp     loc_180007443
0x1800073b1  xorps   xmm0, xmm0
0x1800073b4  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800073ba  test    r14b, 3
0x1800073be  jnz     loc_1800075A4
0x1800073c4  mov     r9, r14
0x1800073c7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800073cc  shr     r9, 2; unsigned __int64
0x1800073d0  lea     rcx, [rsp+280h+hObject]; this
0x1800073d5  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800073da  mov     esi, eax
0x1800073dc  test    eax, eax
0x1800073de  jns     loc_18000748A
0x1800073e4  mov     rcx, [rbp+188h]; this
0x1800073eb  lea     r8, aWil; "wil"
0x1800073f2  mov     r9d, eax; char *
0x1800073f5  mov     edx, 14Eh; void *
0x1800073fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073ff  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180007404  test    rcx, rcx
0x180007407  jz      short loc_180007417
0x180007409  call    cs:__imp_CloseHandle
0x18000740f  test    eax, eax
0x180007411  jz      loc_1800075AA
0x180007417  mov     rcx, [rsp+280h+hObject]; hObject
0x18000741c  test    rcx, rcx
0x18000741f  jz      short loc_18000742F
0x180007421  call    cs:__imp_CloseHandle
0x180007427  test    eax, eax
0x180007429  jz      loc_1800075BC
0x18000742f  call    cs:__imp_GetProcessHeap
0x180007435  mov     r8, r14; lpMem
0x180007438  xor     edx, edx; dwFlags
0x18000743a  mov     rcx, rax; hHeap
0x18000743d  call    cs:__imp_HeapFree
0x180007443  mov     rcx, [rbp+188h]; this
0x18000744a  lea     r8, aWil; "wil"
0x180007451  mov     r9d, esi; char *
0x180007454  mov     edx, 137h; void *
0x180007459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000745e  test    rdi, rdi
0x180007461  jz      short loc_180007474
0x180007463  mov     rcx, rdi; hMutex
0x180007466  call    cs:__imp_ReleaseMutex
0x18000746c  test    eax, eax
0x18000746e  jz      loc_1800075CE
0x180007474  mov     rcx, rbx; hObject
0x180007477  call    cs:__imp_CloseHandle
0x18000747d  test    eax, eax
0x18000747f  jz      loc_18000755C
0x180007485  jmp     loc_180007349
0x18000748a  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000748f  lea     rcx, [r14+28h]; void *
0x180007493  mov     dword ptr [r14], 1
0x18000749a  xor     edx, edx; Val
0x18000749c  mov     [r14+8], rbx
0x1800074a0  mov     r8d, 108h; Size
0x1800074a6  movdqu  xmmword ptr [r14+10h], xmm0
0x1800074ac  call    memset_0
0x1800074b1  xor     eax, eax
0x1800074b3  lea     rcx, [r14+28h]; this
0x1800074b7  mov     [r14+20h], rax
0x1800074bb  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800074c0  lea     rbx, [r14+0E8h]
0x1800074c7  xor     r8d, r8d; Flags
0x1800074ca  mov     rcx, rbx; lpCriticalSection
0x1800074cd  xor     edx, edx; dwSpinCount
0x1800074cf  call    cs:__imp_InitializeCriticalSectionEx
0x1800074d5  mov     qword ptr [rbx+28h], 0
0x1800074dd  mov     qword ptr [rbx+30h], 0
0x1800074e5  mov     qword ptr [rbx+38h], 0
0x1800074ed  mov     qword ptr [rbx+40h], 0
0x1800074f5  xor     ebx, ebx
0x1800074f7  mov     [r15], r14
0x1800074fa  test    rdi, rdi
0x1800074fd  jz      short loc_180007510
0x1800074ff  mov     rcx, rdi; hMutex
0x180007502  call    cs:__imp_ReleaseMutex
0x180007508  test    eax, eax
0x18000750a  jz      loc_1800075E0
0x180007510  test    rbx, rbx
0x180007513  jz      short loc_180007522
0x180007515  mov     rcx, rbx; hObject
0x180007518  call    cs:__imp_CloseHandle
0x18000751e  test    eax, eax
0x180007520  jz      short loc_18000754A
0x180007522  xor     eax, eax
0x180007524  mov     rcx, [rbp+180h+var_30]
0x18000752b  xor     rcx, rsp; StackCookie
0x18000752e  call    __security_check_cookie
0x180007533  mov     rbx, [rsp+280h+arg_10]
0x18000753b  add     rsp, 260h
0x180007542  pop     r15
0x180007544  pop     r14
0x180007546  pop     rdi
0x180007547  pop     rsi
0x180007548  pop     rbp
0x180007549  retn
0x18000754a  mov     rcx, [rbp+188h]; this
0x180007551  mov     edx, 0A0Bh; void *
0x180007556  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000755c  mov     rcx, [rbp+188h]; this
0x180007563  mov     edx, 0A0Bh; void *
0x180007568  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000756e  mov     rcx, [rbp+188h]; this
0x180007575  mov     edx, 0E01h; void *
0x18000757a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007580  mov     rcx, [rbp+188h]; this
0x180007587  mov     edx, 0A15h; void *
0x18000758c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007592  mov     rcx, [rbp+188h]; this
0x180007599  mov     edx, 0A0Bh; void *
0x18000759e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075a4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800075aa  mov     rcx, [rbp+188h]; this
0x1800075b1  mov     edx, 0A0Bh; void *
0x1800075b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075bc  mov     rcx, [rbp+188h]; this
0x1800075c3  mov     edx, 0A0Bh; void *
0x1800075c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075ce  mov     rcx, [rbp+188h]; this
0x1800075d5  mov     edx, 0A15h; void *
0x1800075da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075e0  mov     rcx, [rbp+188h]; this
0x1800075e7  mov     edx, 0A15h; void *
0x1800075ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
