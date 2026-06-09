# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000321c`
- end: `0x1800035ba`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004a3c`

## callees

- `0x18000321c`
- `0x180003990`
- `0x180003eb8`
- `0x1800047d8`
- `0x1800054b8`
- `0x1800069d4`
- `0x180006fc0`
- `0x1800073a8`
- `0x180007c4c`
- `0x180007c5c`
- `0x18000c4a4`
- `0x18000c560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800032b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800032b5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003294`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003294`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003336`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000345f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800034cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003336`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000345f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800034cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000343d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000343d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000342f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000342f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003255`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003347`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003409`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003421`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003347`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003409`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003421`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034e5`

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
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x18000321c  mov     [rsp-8+arg_10], rbx
0x180003221  push    rbp
0x180003222  push    rsi
0x180003223  push    rdi
0x180003224  push    r14
0x180003226  push    r15
0x180003228  lea     rbp, [rsp-160h]
0x180003230  sub     rsp, 260h
0x180003237  mov     rax, cs:__security_cookie
0x18000323e  xor     rax, rsp
0x180003241  mov     [rbp+180h+var_30], rax
0x180003248  mov     r15, rdx
0x18000324b  mov     qword ptr [rdx], 0
0x180003252  mov     rbx, rcx
0x180003255  call    cs:__imp_GetCurrentProcessId
0x18000325b  mov     r14d, 78h ; 'x'
0x180003261  mov     [rsp+280h+var_258], rbx
0x180003266  mov     r9d, eax
0x180003269  mov     [rsp+280h+var_260], r14d; int
0x18000326e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003275  mov     edx, 104h; unsigned __int64
0x18000327a  lea     rcx, [rsp+280h+Name]; Buffer
0x18000327f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003284  mov     r9d, 1F0001h; dwDesiredAccess
0x18000328a  lea     rdx, [rsp+280h+Name]; lpName
0x18000328f  xor     r8d, r8d; dwFlags
0x180003292  xor     ecx, ecx; lpMutexAttributes
0x180003294  call    cs:__imp_CreateMutexExW
0x18000329a  mov     rbx, rax
0x18000329d  test    rax, rax
0x1800032a0  jnz     short loc_1800032AC
0x1800032a2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800032a7  jmp     loc_1800034F1
0x1800032ac  xor     r8d, r8d; bAlertable
0x1800032af  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800032b2  mov     rcx, rbx; hHandle
0x1800032b5  call    cs:__imp_WaitForSingleObjectEx
0x1800032bb  cmp     eax, 102h
0x1800032c0  jz      short loc_1800032D2
0x1800032c2  test    eax, 0FFFFFF7Fh
0x1800032c7  jnz     loc_180003529
0x1800032cd  mov     rdi, rbx
0x1800032d0  jmp     short loc_1800032D4
0x1800032d2  xor     edi, edi
0x1800032d4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800032d9  mov     [rsp+280h+hObject], 0
0x1800032e2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800032e7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800032ec  mov     esi, eax
0x1800032ee  test    eax, eax
0x1800032f0  jns     short loc_18000335C
0x1800032f2  mov     rcx, [rbp+188h]; this
0x1800032f9  mov     r9d, eax; char *
0x1800032fc  mov     edx, 66h ; 'f'; void *
0x180003301  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003306  mov     rcx, [rbp+188h]; this
0x18000330d  mov     r9d, esi; char *
0x180003310  mov     edx, 6Fh ; 'o'; void *
0x180003315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000331a  mov     rcx, [rbp+188h]; this
0x180003321  mov     r9d, esi; char *
0x180003324  mov     edx, 12Eh; void *
0x180003329  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000332e  test    rdi, rdi
0x180003331  jz      short loc_180003344
0x180003333  mov     rcx, rdi; hMutex
0x180003336  call    cs:__imp_ReleaseMutex
0x18000333c  test    eax, eax
0x18000333e  jz      loc_180003536
0x180003344  mov     rcx, rbx; hObject
0x180003347  call    cs:__imp_CloseHandle
0x18000334d  test    eax, eax
0x18000334f  jz      loc_180003548
0x180003355  mov     eax, esi
0x180003357  jmp     loc_1800034F1
0x18000335c  mov     rax, [rsp+280h+hObject]
0x180003361  lea     rcx, ds:0[rax*4]
0x180003369  test    rcx, rcx
0x18000336c  jz      short loc_18000337C
0x18000336e  mov     [r15], rcx
0x180003371  mov     eax, [rcx]
0x180003373  inc     eax
0x180003375  mov     [rcx], eax
0x180003377  jmp     loc_1800034C7
0x18000337c  mov     rdx, r14; dwBytes
0x18000337f  mov     qword ptr [r15], 0
0x180003386  mov     ecx, 8; dwFlags
0x18000338b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003390  mov     rsi, rax
0x180003393  test    rax, rax
0x180003396  jnz     short loc_1800033B7
0x180003398  mov     rcx, [rbp+188h]; this
0x18000339f  mov     r14d, 8007000Eh
0x1800033a5  mov     r9d, r14d; char *
0x1800033a8  mov     edx, 14Bh; void *
0x1800033ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033b2  jmp     loc_180003443
0x1800033b7  xorps   xmm0, xmm0
0x1800033ba  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800033c0  test    sil, 3
0x1800033c4  jnz     loc_18000355A
0x1800033ca  mov     r9, rsi
0x1800033cd  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800033d2  shr     r9, 2; unsigned __int64
0x1800033d6  lea     rcx, [rsp+280h+hObject]; this
0x1800033db  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800033e0  mov     r14d, eax
0x1800033e3  test    eax, eax
0x1800033e5  jns     loc_180003483
0x1800033eb  mov     rcx, [rbp+188h]; this
0x1800033f2  mov     r9d, eax; char *
0x1800033f5  mov     edx, 14Eh; void *
0x1800033fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800033ff  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003404  test    rcx, rcx
0x180003407  jz      short loc_180003417
0x180003409  call    cs:__imp_CloseHandle
0x18000340f  test    eax, eax
0x180003411  jz      loc_180003560
0x180003417  mov     rcx, [rsp+280h+hObject]; hObject
0x18000341c  test    rcx, rcx
0x18000341f  jz      short loc_18000342F
0x180003421  call    cs:__imp_CloseHandle
0x180003427  test    eax, eax
0x180003429  jz      loc_180003572
0x18000342f  call    cs:__imp_GetProcessHeap
0x180003435  mov     r8, rsi; lpMem
0x180003438  xor     edx, edx; dwFlags
0x18000343a  mov     rcx, rax; hHeap
0x18000343d  call    cs:__imp_HeapFree
0x180003443  mov     rcx, [rbp+188h]; this
0x18000344a  mov     r9d, r14d; char *
0x18000344d  mov     edx, 137h; void *
0x180003452  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003457  test    rdi, rdi
0x18000345a  jz      short loc_18000346D
0x18000345c  mov     rcx, rdi; hMutex
0x18000345f  call    cs:__imp_ReleaseMutex
0x180003465  test    eax, eax
0x180003467  jz      loc_180003584
0x18000346d  mov     rcx, rbx; hObject
0x180003470  call    cs:__imp_CloseHandle
0x180003476  test    eax, eax
0x180003478  jz      loc_180003596
0x18000347e  mov     eax, r14d
0x180003481  jmp     short loc_1800034F1
0x180003483  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003488  xor     edx, edx; Val
0x18000348a  mov     dword ptr [rsi], 1
0x180003490  lea     rcx, [rsi+22h]; void *
0x180003494  mov     [rsi+8], rbx
0x180003498  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000349d  lea     r8d, [rdx+56h]; Size
0x1800034a1  call    memset_0
0x1800034a6  xor     edx, edx; Val
0x1800034a8  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800034ae  lea     rcx, [rsi+28h]; void *
0x1800034b2  mov     dword ptr [rsi+24h], 1
0x1800034b9  lea     r8d, [rdx+50h]; Size
0x1800034bd  call    memset_0
0x1800034c2  xor     ebx, ebx
0x1800034c4  mov     [r15], rsi
0x1800034c7  test    rdi, rdi
0x1800034ca  jz      short loc_1800034DD
0x1800034cc  mov     rcx, rdi; hMutex
0x1800034cf  call    cs:__imp_ReleaseMutex
0x1800034d5  test    eax, eax
0x1800034d7  jz      loc_1800035A8
0x1800034dd  test    rbx, rbx
0x1800034e0  jz      short loc_1800034EF
0x1800034e2  mov     rcx, rbx; hObject
0x1800034e5  call    cs:__imp_CloseHandle
0x1800034eb  test    eax, eax
0x1800034ed  jz      short loc_180003517
0x1800034ef  xor     eax, eax
0x1800034f1  mov     rcx, [rbp+180h+var_30]
0x1800034f8  xor     rcx, rsp; StackCookie
0x1800034fb  call    __security_check_cookie
0x180003500  mov     rbx, [rsp+280h+arg_10]
0x180003508  add     rsp, 260h
0x18000350f  pop     r15
0x180003511  pop     r14
0x180003513  pop     rdi
0x180003514  pop     rsi
0x180003515  pop     rbp
0x180003516  retn
0x180003517  mov     rcx, [rbp+188h]; this
0x18000351e  mov     edx, 0A0Bh; void *
0x180003523  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003529  mov     rcx, [rbp+188h]; this
0x180003530  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003536  mov     rcx, [rbp+188h]; this
0x18000353d  mov     edx, 0A15h; void *
0x180003542  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003548  mov     rcx, [rbp+188h]; this
0x18000354f  mov     edx, 0A0Bh; void *
0x180003554  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000355a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003560  mov     rcx, [rbp+188h]; this
0x180003567  mov     edx, 0A0Bh; void *
0x18000356c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003572  mov     rcx, [rbp+188h]; this
0x180003579  mov     edx, 0A0Bh; void *
0x18000357e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003584  mov     rcx, [rbp+188h]; this
0x18000358b  mov     edx, 0A15h; void *
0x180003590  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003596  mov     rcx, [rbp+188h]; this
0x18000359d  mov     edx, 0A0Bh; void *
0x1800035a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800035a8  mov     rcx, [rbp+188h]; this
0x1800035af  mov     edx, 0A15h; void *
0x1800035b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
