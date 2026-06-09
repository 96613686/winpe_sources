# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001928c`
- end: `0x180019654`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18001a408`

## callees

- `0x180001800`
- `0x180002678`
- `0x18001928c`
- `0x180019934`
- `0x180019ba4`
- `0x18001a270`
- `0x18001bf38`
- `0x18001c4c4`
- `0x18001ce84`
- `0x18001cf3c`
- `0x18001e14c`
- `0x18001e15c`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x1800193bb`
- `KERNEL32!ReleaseMutex` at `0x1800194f9`
- `KERNEL32!ReleaseMutex` at `0x180019569`
- `KERNEL32!ReleaseMutex` at `0x1800193bb`
- `KERNEL32!ReleaseMutex` at `0x1800194f9`
- `KERNEL32!ReleaseMutex` at `0x180019569`
- `KERNEL32!CloseHandle` at `0x1800193cc`
- `KERNEL32!CloseHandle` at `0x18001949c`
- `KERNEL32!CloseHandle` at `0x1800194b4`
- `KERNEL32!CloseHandle` at `0x18001950a`
- `KERNEL32!CloseHandle` at `0x18001957f`
- `KERNEL32!CloseHandle` at `0x1800193cc`
- `KERNEL32!CloseHandle` at `0x18001949c`
- `KERNEL32!CloseHandle` at `0x1800194b4`
- `KERNEL32!CloseHandle` at `0x18001950a`
- `KERNEL32!CloseHandle` at `0x18001957f`
- `KERNEL32!WaitForSingleObjectEx` at `0x180019325`
- `KERNEL32!WaitForSingleObjectEx` at `0x180019325`
- `KERNEL32!GetProcessHeap` at `0x1800194c2`
- `KERNEL32!GetProcessHeap` at `0x1800194c2`
- `KERNEL32!HeapFree` at `0x1800194d0`
- `KERNEL32!HeapFree` at `0x1800194d0`
- `KERNEL32!GetCurrentProcessId` at `0x1800192c5`
- `KERNEL32!GetCurrentProcessId` at `0x1800192c5`
- `KERNEL32!CreateMutexExW` at `0x180019304`
- `KERNEL32!CreateMutexExW` at `0x180019304`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
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
0x18001928c  mov     [rsp-8+arg_10], rbx
0x180019291  push    rbp
0x180019292  push    rsi
0x180019293  push    rdi
0x180019294  push    r14
0x180019296  push    r15
0x180019298  lea     rbp, [rsp-160h]
0x1800192a0  sub     rsp, 260h
0x1800192a7  mov     rax, cs:__security_cookie
0x1800192ae  xor     rax, rsp
0x1800192b1  mov     [rbp+180h+var_30], rax
0x1800192b8  mov     r15, rdx
0x1800192bb  mov     qword ptr [rdx], 0
0x1800192c2  mov     rbx, rcx
0x1800192c5  call    cs:__imp_GetCurrentProcessId
0x1800192cb  mov     r14d, 78h ; 'x'
0x1800192d1  mov     [rsp+280h+var_258], rbx
0x1800192d6  mov     r9d, eax
0x1800192d9  mov     [rsp+280h+var_260], r14d; int
0x1800192de  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800192e5  mov     edx, 104h; unsigned __int64
0x1800192ea  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800192ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800192f4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800192fa  lea     rdx, [rsp+280h+Name]; lpName
0x1800192ff  xor     r8d, r8d; dwFlags
0x180019302  xor     ecx, ecx; lpMutexAttributes
0x180019304  call    cs:__imp_CreateMutexExW
0x18001930a  mov     rbx, rax
0x18001930d  test    rax, rax
0x180019310  jnz     short loc_18001931C
0x180019312  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180019317  jmp     loc_18001958B
0x18001931c  xor     r8d, r8d; bAlertable
0x18001931f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019322  mov     rcx, rbx; hHandle
0x180019325  call    cs:__imp_WaitForSingleObjectEx
0x18001932b  cmp     eax, 102h
0x180019330  jz      short loc_180019342
0x180019332  test    eax, 0FFFFFF7Fh
0x180019337  jnz     loc_1800195C3
0x18001933d  mov     rdi, rbx
0x180019340  jmp     short loc_180019344
0x180019342  xor     edi, edi
0x180019344  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180019349  mov     [rsp+280h+hObject], 0
0x180019352  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019357  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001935c  mov     esi, eax
0x18001935e  test    eax, eax
0x180019360  jns     short loc_1800193E1
0x180019362  mov     rcx, [rbp+188h]; this
0x180019369  lea     r8, aWil; "wil"
0x180019370  mov     r9d, eax; char *
0x180019373  mov     edx, 66h ; 'f'; void *
0x180019378  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001937d  mov     rcx, [rbp+188h]; this
0x180019384  lea     r8, aWil; "wil"
0x18001938b  mov     r9d, esi; char *
0x18001938e  mov     edx, 6Fh ; 'o'; void *
0x180019393  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019398  mov     rcx, [rbp+188h]; this
0x18001939f  lea     r8, aWil; "wil"
0x1800193a6  mov     r9d, esi; char *
0x1800193a9  mov     edx, 12Eh; void *
0x1800193ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800193b3  test    rdi, rdi
0x1800193b6  jz      short loc_1800193C9
0x1800193b8  mov     rcx, rdi; hMutex
0x1800193bb  call    cs:__imp_ReleaseMutex
0x1800193c1  test    eax, eax
0x1800193c3  jz      loc_1800195D0
0x1800193c9  mov     rcx, rbx; hObject
0x1800193cc  call    cs:__imp_CloseHandle
0x1800193d2  test    eax, eax
0x1800193d4  jz      loc_1800195E2
0x1800193da  mov     eax, esi
0x1800193dc  jmp     loc_18001958B
0x1800193e1  mov     rax, [rsp+280h+hObject]
0x1800193e6  lea     rcx, ds:0[rax*4]
0x1800193ee  test    rcx, rcx
0x1800193f1  jz      short loc_180019401
0x1800193f3  mov     [r15], rcx
0x1800193f6  mov     eax, [rcx]
0x1800193f8  inc     eax
0x1800193fa  mov     [rcx], eax
0x1800193fc  jmp     loc_180019561
0x180019401  mov     rdx, r14; dwBytes
0x180019404  mov     qword ptr [r15], 0
0x18001940b  mov     ecx, 8; dwFlags
0x180019410  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180019415  mov     rsi, rax
0x180019418  test    rax, rax
0x18001941b  jnz     short loc_180019443
0x18001941d  mov     rcx, [rbp+188h]; this
0x180019424  lea     r8, aWil; "wil"
0x18001942b  mov     r14d, 8007000Eh
0x180019431  mov     edx, 14Bh; void *
0x180019436  mov     r9d, r14d; char *
0x180019439  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001943e  jmp     loc_1800194D6
0x180019443  xorps   xmm0, xmm0
0x180019446  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18001944c  test    sil, 3
0x180019450  jnz     loc_1800195F4
0x180019456  mov     r9, rsi
0x180019459  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18001945e  shr     r9, 2; unsigned __int64
0x180019462  lea     rcx, [rsp+280h+hObject]; this
0x180019467  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18001946c  mov     r14d, eax
0x18001946f  test    eax, eax
0x180019471  jns     loc_18001951D
0x180019477  mov     rcx, [rbp+188h]; this
0x18001947e  lea     r8, aWil; "wil"
0x180019485  mov     r9d, eax; char *
0x180019488  mov     edx, 14Eh; void *
0x18001948d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019492  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180019497  test    rcx, rcx
0x18001949a  jz      short loc_1800194AA
0x18001949c  call    cs:__imp_CloseHandle
0x1800194a2  test    eax, eax
0x1800194a4  jz      loc_1800195FA
0x1800194aa  mov     rcx, [rsp+280h+hObject]; hObject
0x1800194af  test    rcx, rcx
0x1800194b2  jz      short loc_1800194C2
0x1800194b4  call    cs:__imp_CloseHandle
0x1800194ba  test    eax, eax
0x1800194bc  jz      loc_18001960C
0x1800194c2  call    cs:__imp_GetProcessHeap
0x1800194c8  mov     r8, rsi; lpMem
0x1800194cb  xor     edx, edx; dwFlags
0x1800194cd  mov     rcx, rax; hHeap
0x1800194d0  call    cs:__imp_HeapFree
0x1800194d6  mov     rcx, [rbp+188h]; this
0x1800194dd  lea     r8, aWil; "wil"
0x1800194e4  mov     r9d, r14d; char *
0x1800194e7  mov     edx, 137h; void *
0x1800194ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194f1  test    rdi, rdi
0x1800194f4  jz      short loc_180019507
0x1800194f6  mov     rcx, rdi; hMutex
0x1800194f9  call    cs:__imp_ReleaseMutex
0x1800194ff  test    eax, eax
0x180019501  jz      loc_18001961E
0x180019507  mov     rcx, rbx; hObject
0x18001950a  call    cs:__imp_CloseHandle
0x180019510  test    eax, eax
0x180019512  jz      loc_180019630
0x180019518  mov     eax, r14d
0x18001951b  jmp     short loc_18001958B
0x18001951d  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180019522  xor     edx, edx; Val
0x180019524  mov     dword ptr [rsi], 1
0x18001952a  lea     rcx, [rsi+22h]; void *
0x18001952e  mov     [rsi+8], rbx
0x180019532  movdqu  xmmword ptr [rsi+10h], xmm0
0x180019537  lea     r8d, [rdx+56h]; Size
0x18001953b  call    memset_0
0x180019540  xor     edx, edx; Val
0x180019542  mov     word ptr [rsi+20h], 58h ; 'X'
0x180019548  lea     rcx, [rsi+28h]; void *
0x18001954c  mov     dword ptr [rsi+24h], 1
0x180019553  lea     r8d, [rdx+50h]; Size
0x180019557  call    memset_0
0x18001955c  xor     ebx, ebx
0x18001955e  mov     [r15], rsi
0x180019561  test    rdi, rdi
0x180019564  jz      short loc_180019577
0x180019566  mov     rcx, rdi; hMutex
0x180019569  call    cs:__imp_ReleaseMutex
0x18001956f  test    eax, eax
0x180019571  jz      loc_180019642
0x180019577  test    rbx, rbx
0x18001957a  jz      short loc_180019589
0x18001957c  mov     rcx, rbx; hObject
0x18001957f  call    cs:__imp_CloseHandle
0x180019585  test    eax, eax
0x180019587  jz      short loc_1800195B1
0x180019589  xor     eax, eax
0x18001958b  mov     rcx, [rbp+180h+var_30]
0x180019592  xor     rcx, rsp; StackCookie
0x180019595  call    __security_check_cookie
0x18001959a  mov     rbx, [rsp+280h+arg_10]
0x1800195a2  add     rsp, 260h
0x1800195a9  pop     r15
0x1800195ab  pop     r14
0x1800195ad  pop     rdi
0x1800195ae  pop     rsi
0x1800195af  pop     rbp
0x1800195b0  retn
0x1800195b1  mov     rcx, [rbp+188h]; this
0x1800195b8  mov     edx, 0A0Bh; void *
0x1800195bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800195c3  mov     rcx, [rbp+188h]; this
0x1800195ca  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800195d0  mov     rcx, [rbp+188h]; this
0x1800195d7  mov     edx, 0A15h; void *
0x1800195dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800195e2  mov     rcx, [rbp+188h]; this
0x1800195e9  mov     edx, 0A0Bh; void *
0x1800195ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800195f4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800195fa  mov     rcx, [rbp+188h]; this
0x180019601  mov     edx, 0A0Bh; void *
0x180019606  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001960c  mov     rcx, [rbp+188h]; this
0x180019613  mov     edx, 0A0Bh; void *
0x180019618  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001961e  mov     rcx, [rbp+188h]; this
0x180019625  mov     edx, 0A15h; void *
0x18001962a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019630  mov     rcx, [rbp+188h]; this
0x180019637  mov     edx, 0A0Bh; void *
0x18001963c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019642  mov     rcx, [rbp+188h]; this
0x180019649  mov     edx, 0A15h; void *
0x18001964e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
