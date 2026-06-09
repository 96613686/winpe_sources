# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007238`
- end: `0x180007605`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800091b4`

## callees

- `0x180005020`
- `0x180005e9c`
- `0x180007238`
- `0x1800081a0`
- `0x180008950`
- `0x180008f4c`
- `0x180009ee8`
- `0x18000b394`
- `0x18000bdd4`
- `0x18000bf4c`
- `0x18000c674`
- `0x18000c684`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800072b0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800072b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007367`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800074a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007515`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007367`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800074a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007515`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800072d1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800072d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000746e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000746e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000747c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000747c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007271`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007271`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007378`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007460`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000752b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007378`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007460`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000752b`

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
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x180007238  mov     [rsp-8+arg_10], rbx
0x18000723d  push    rbp
0x18000723e  push    rsi
0x18000723f  push    rdi
0x180007240  push    r14
0x180007242  push    r15
0x180007244  lea     rbp, [rsp-160h]
0x18000724c  sub     rsp, 260h
0x180007253  mov     rax, cs:__security_cookie
0x18000725a  xor     rax, rsp
0x18000725d  mov     [rbp+180h+var_30], rax
0x180007264  mov     r15, rdx
0x180007267  mov     qword ptr [rdx], 0
0x18000726e  mov     rbx, rcx
0x180007271  call    cs:__imp_GetCurrentProcessId
0x180007277  mov     r14d, 78h ; 'x'
0x18000727d  mov     [rsp+280h+var_258], rbx
0x180007282  mov     r9d, eax
0x180007285  mov     [rsp+280h+var_260], r14d; int
0x18000728a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007291  mov     edx, 104h; unsigned __int64
0x180007296  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000729b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800072a0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800072a6  lea     rdx, [rsp+280h+Name]; lpName
0x1800072ab  xor     r8d, r8d; dwFlags
0x1800072ae  xor     ecx, ecx; lpMutexAttributes
0x1800072b0  call    cs:__imp_CreateMutexExW
0x1800072b6  mov     rbx, rax
0x1800072b9  test    rax, rax
0x1800072bc  jnz     short loc_1800072C8
0x1800072be  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800072c3  jmp     loc_180007537
0x1800072c8  xor     r8d, r8d; bAlertable
0x1800072cb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800072ce  mov     rcx, rbx; hHandle
0x1800072d1  call    cs:__imp_WaitForSingleObjectEx
0x1800072d7  cmp     eax, 102h
0x1800072dc  jz      short loc_1800072EE
0x1800072de  test    eax, 0FFFFFF7Fh
0x1800072e3  jnz     loc_18000756F
0x1800072e9  mov     rdi, rbx
0x1800072ec  jmp     short loc_1800072F0
0x1800072ee  xor     edi, edi
0x1800072f0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800072f5  mov     [rsp+280h+hObject], 0
0x1800072fe  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007303  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007308  mov     esi, eax
0x18000730a  test    eax, eax
0x18000730c  jns     short loc_18000738D
0x18000730e  mov     rcx, [rbp+188h]; this
0x180007315  lea     r8, aWil; "wil"
0x18000731c  mov     r9d, eax; char *
0x18000731f  mov     edx, 66h ; 'f'; void *
0x180007324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007329  mov     rcx, [rbp+188h]; this
0x180007330  lea     r8, aWil; "wil"
0x180007337  mov     r9d, esi; char *
0x18000733a  mov     edx, 6Fh ; 'o'; void *
0x18000733f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007344  mov     rcx, [rbp+188h]; this
0x18000734b  lea     r8, aWil; "wil"
0x180007352  mov     r9d, esi; char *
0x180007355  mov     edx, 12Eh; void *
0x18000735a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000735f  test    rdi, rdi
0x180007362  jz      short loc_180007375
0x180007364  mov     rcx, rdi; hMutex
0x180007367  call    cs:__imp_ReleaseMutex
0x18000736d  test    eax, eax
0x18000736f  jz      loc_180007581
0x180007375  mov     rcx, rbx; hObject
0x180007378  call    cs:__imp_CloseHandle
0x18000737e  test    eax, eax
0x180007380  jz      loc_180007593
0x180007386  mov     eax, esi
0x180007388  jmp     loc_180007537
0x18000738d  mov     rax, [rsp+280h+hObject]
0x180007392  lea     rcx, ds:0[rax*4]
0x18000739a  test    rcx, rcx
0x18000739d  jz      short loc_1800073AD
0x18000739f  mov     [r15], rcx
0x1800073a2  mov     eax, [rcx]
0x1800073a4  inc     eax
0x1800073a6  mov     [rcx], eax
0x1800073a8  jmp     loc_18000750D
0x1800073ad  mov     rdx, r14; dwBytes
0x1800073b0  mov     qword ptr [r15], 0
0x1800073b7  mov     ecx, 8; dwFlags
0x1800073bc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800073c1  mov     rsi, rax
0x1800073c4  test    rax, rax
0x1800073c7  jnz     short loc_1800073EF
0x1800073c9  mov     rcx, [rbp+188h]; this
0x1800073d0  lea     r8, aWil; "wil"
0x1800073d7  mov     r14d, 8007000Eh
0x1800073dd  mov     edx, 14Bh; void *
0x1800073e2  mov     r9d, r14d; char *
0x1800073e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073ea  jmp     loc_180007482
0x1800073ef  xorps   xmm0, xmm0
0x1800073f2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800073f8  test    sil, 3
0x1800073fc  jnz     loc_1800075A5
0x180007402  mov     r9, rsi
0x180007405  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000740a  shr     r9, 2; unsigned __int64
0x18000740e  lea     rcx, [rsp+280h+hObject]; this
0x180007413  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180007418  mov     r14d, eax
0x18000741b  test    eax, eax
0x18000741d  jns     loc_1800074C9
0x180007423  mov     rcx, [rbp+188h]; this
0x18000742a  lea     r8, aWil; "wil"
0x180007431  mov     r9d, eax; char *
0x180007434  mov     edx, 14Eh; void *
0x180007439  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000743e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180007443  test    rcx, rcx
0x180007446  jz      short loc_180007456
0x180007448  call    cs:__imp_CloseHandle
0x18000744e  test    eax, eax
0x180007450  jz      loc_1800075AB
0x180007456  mov     rcx, [rsp+280h+hObject]; hObject
0x18000745b  test    rcx, rcx
0x18000745e  jz      short loc_18000746E
0x180007460  call    cs:__imp_CloseHandle
0x180007466  test    eax, eax
0x180007468  jz      loc_1800075BD
0x18000746e  call    cs:__imp_GetProcessHeap
0x180007474  mov     r8, rsi; lpMem
0x180007477  xor     edx, edx; dwFlags
0x180007479  mov     rcx, rax; hHeap
0x18000747c  call    cs:__imp_HeapFree
0x180007482  mov     rcx, [rbp+188h]; this
0x180007489  lea     r8, aWil; "wil"
0x180007490  mov     r9d, r14d; char *
0x180007493  mov     edx, 137h; void *
0x180007498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000749d  test    rdi, rdi
0x1800074a0  jz      short loc_1800074B3
0x1800074a2  mov     rcx, rdi; hMutex
0x1800074a5  call    cs:__imp_ReleaseMutex
0x1800074ab  test    eax, eax
0x1800074ad  jz      loc_1800075CF
0x1800074b3  mov     rcx, rbx; hObject
0x1800074b6  call    cs:__imp_CloseHandle
0x1800074bc  test    eax, eax
0x1800074be  jz      loc_1800075E1
0x1800074c4  mov     eax, r14d
0x1800074c7  jmp     short loc_180007537
0x1800074c9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800074ce  xor     edx, edx; Val
0x1800074d0  mov     dword ptr [rsi], 1
0x1800074d6  lea     rcx, [rsi+22h]; void *
0x1800074da  mov     [rsi+8], rbx
0x1800074de  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800074e3  lea     r8d, [rdx+56h]; Size
0x1800074e7  call    memset_0
0x1800074ec  xor     edx, edx; Val
0x1800074ee  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800074f4  lea     rcx, [rsi+28h]; void *
0x1800074f8  mov     dword ptr [rsi+24h], 1
0x1800074ff  lea     r8d, [rdx+50h]; Size
0x180007503  call    memset_0
0x180007508  xor     ebx, ebx
0x18000750a  mov     [r15], rsi
0x18000750d  test    rdi, rdi
0x180007510  jz      short loc_180007523
0x180007512  mov     rcx, rdi; hMutex
0x180007515  call    cs:__imp_ReleaseMutex
0x18000751b  test    eax, eax
0x18000751d  jz      loc_1800075F3
0x180007523  test    rbx, rbx
0x180007526  jz      short loc_180007535
0x180007528  mov     rcx, rbx; hObject
0x18000752b  call    cs:__imp_CloseHandle
0x180007531  test    eax, eax
0x180007533  jz      short loc_18000755D
0x180007535  xor     eax, eax
0x180007537  mov     rcx, [rbp+180h+var_30]
0x18000753e  xor     rcx, rsp; StackCookie
0x180007541  call    __security_check_cookie
0x180007546  mov     rbx, [rsp+280h+arg_10]
0x18000754e  add     rsp, 260h
0x180007555  pop     r15
0x180007557  pop     r14
0x180007559  pop     rdi
0x18000755a  pop     rsi
0x18000755b  pop     rbp
0x18000755c  retn
0x18000755d  mov     rcx, [rbp+188h]; this
0x180007564  mov     edx, 0A0Bh; void *
0x180007569  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000756f  mov     rcx, [rbp+188h]; this
0x180007576  mov     edx, 0E01h; void *
0x18000757b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007581  mov     rcx, [rbp+188h]; this
0x180007588  mov     edx, 0A15h; void *
0x18000758d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007593  mov     rcx, [rbp+188h]; this
0x18000759a  mov     edx, 0A0Bh; void *
0x18000759f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075a5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800075ab  mov     rcx, [rbp+188h]; this
0x1800075b2  mov     edx, 0A0Bh; void *
0x1800075b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075bd  mov     rcx, [rbp+188h]; this
0x1800075c4  mov     edx, 0A0Bh; void *
0x1800075c9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075cf  mov     rcx, [rbp+188h]; this
0x1800075d6  mov     edx, 0A15h; void *
0x1800075db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075e1  mov     rcx, [rbp+188h]; this
0x1800075e8  mov     edx, 0A0Bh; void *
0x1800075ed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075f3  mov     rcx, [rbp+188h]; this
0x1800075fa  mov     edx, 0A15h; void *
0x1800075ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
