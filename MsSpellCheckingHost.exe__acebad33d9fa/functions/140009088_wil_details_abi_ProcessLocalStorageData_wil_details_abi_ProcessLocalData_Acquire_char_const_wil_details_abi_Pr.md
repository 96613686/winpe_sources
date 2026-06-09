# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140009088`
- end: `0x140009426`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14000aa6c`

## callees

- `0x1400023f3`
- `0x140009088`
- `0x14000992c`
- `0x140009f68`
- `0x14000a7c8`
- `0x14000bc90`
- `0x14000d2a4`
- `0x14000dc80`
- `0x14000e0ac`
- `0x14000ecd4`
- `0x14000ece4`
- `0x140011e10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400090c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400090c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000928d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400092dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009351`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000928d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400092dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009351`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400091a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400092cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000933b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400091a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400092cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000933b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009121`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009121`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009100`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009100`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400092a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400092a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000929b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000929b`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
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
0x140009088  mov     [rsp-8+arg_10], rbx
0x14000908d  push    rbp
0x14000908e  push    rsi
0x14000908f  push    rdi
0x140009090  push    r14
0x140009092  push    r15
0x140009094  lea     rbp, [rsp-160h]
0x14000909c  sub     rsp, 260h
0x1400090a3  mov     rax, cs:__security_cookie
0x1400090aa  xor     rax, rsp
0x1400090ad  mov     [rbp+180h+var_30], rax
0x1400090b4  mov     r15, rdx
0x1400090b7  mov     qword ptr [rdx], 0
0x1400090be  mov     rbx, rcx
0x1400090c1  call    cs:__imp_GetCurrentProcessId
0x1400090c7  mov     r14d, 78h ; 'x'
0x1400090cd  mov     [rsp+280h+var_258], rbx
0x1400090d2  mov     r9d, eax
0x1400090d5  mov     [rsp+280h+var_260], r14d; int
0x1400090da  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400090e1  mov     edx, 104h; unsigned __int64
0x1400090e6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400090eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400090f0  mov     r9d, 1F0001h; dwDesiredAccess
0x1400090f6  lea     rdx, [rsp+280h+Name]; lpName
0x1400090fb  xor     r8d, r8d; dwFlags
0x1400090fe  xor     ecx, ecx; lpMutexAttributes
0x140009100  call    cs:__imp_CreateMutexExW
0x140009106  mov     rbx, rax
0x140009109  test    rax, rax
0x14000910c  jnz     short loc_140009118
0x14000910e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009113  jmp     loc_14000935D
0x140009118  xor     r8d, r8d; bAlertable
0x14000911b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000911e  mov     rcx, rbx; hHandle
0x140009121  call    cs:__imp_WaitForSingleObjectEx
0x140009127  cmp     eax, 102h
0x14000912c  jz      short loc_14000913E
0x14000912e  test    eax, 0FFFFFF7Fh
0x140009133  jnz     loc_140009395
0x140009139  mov     rdi, rbx
0x14000913c  jmp     short loc_140009140
0x14000913e  xor     edi, edi
0x140009140  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140009145  mov     [rsp+280h+hObject], 0
0x14000914e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140009153  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140009158  mov     esi, eax
0x14000915a  test    eax, eax
0x14000915c  jns     short loc_1400091C8
0x14000915e  mov     rcx, [rbp+188h]; this
0x140009165  mov     r9d, eax; char *
0x140009168  mov     edx, 66h ; 'f'; void *
0x14000916d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009172  mov     rcx, [rbp+188h]; this
0x140009179  mov     r9d, esi; char *
0x14000917c  mov     edx, 6Fh ; 'o'; void *
0x140009181  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009186  mov     rcx, [rbp+188h]; this
0x14000918d  mov     r9d, esi; char *
0x140009190  mov     edx, 12Eh; void *
0x140009195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000919a  test    rdi, rdi
0x14000919d  jz      short loc_1400091B0
0x14000919f  mov     rcx, rdi; hMutex
0x1400091a2  call    cs:__imp_ReleaseMutex
0x1400091a8  test    eax, eax
0x1400091aa  jz      loc_1400093A2
0x1400091b0  mov     rcx, rbx; hObject
0x1400091b3  call    cs:__imp_CloseHandle
0x1400091b9  test    eax, eax
0x1400091bb  jz      loc_1400093B4
0x1400091c1  mov     eax, esi
0x1400091c3  jmp     loc_14000935D
0x1400091c8  mov     rax, [rsp+280h+hObject]
0x1400091cd  lea     rcx, ds:0[rax*4]
0x1400091d5  test    rcx, rcx
0x1400091d8  jz      short loc_1400091E8
0x1400091da  mov     [r15], rcx
0x1400091dd  mov     eax, [rcx]
0x1400091df  inc     eax
0x1400091e1  mov     [rcx], eax
0x1400091e3  jmp     loc_140009333
0x1400091e8  mov     rdx, r14; dwBytes
0x1400091eb  mov     qword ptr [r15], 0
0x1400091f2  mov     ecx, 8; dwFlags
0x1400091f7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400091fc  mov     rsi, rax
0x1400091ff  test    rax, rax
0x140009202  jnz     short loc_140009223
0x140009204  mov     rcx, [rbp+188h]; this
0x14000920b  mov     r14d, 8007000Eh
0x140009211  mov     r9d, r14d; char *
0x140009214  mov     edx, 14Bh; void *
0x140009219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000921e  jmp     loc_1400092AF
0x140009223  xorps   xmm0, xmm0
0x140009226  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000922c  test    sil, 3
0x140009230  jnz     loc_1400093C6
0x140009236  mov     r9, rsi
0x140009239  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000923e  shr     r9, 2; unsigned __int64
0x140009242  lea     rcx, [rsp+280h+hObject]; this
0x140009247  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000924c  mov     r14d, eax
0x14000924f  test    eax, eax
0x140009251  jns     loc_1400092EF
0x140009257  mov     rcx, [rbp+188h]; this
0x14000925e  mov     r9d, eax; char *
0x140009261  mov     edx, 14Eh; void *
0x140009266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000926b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140009270  test    rcx, rcx
0x140009273  jz      short loc_140009283
0x140009275  call    cs:__imp_CloseHandle
0x14000927b  test    eax, eax
0x14000927d  jz      loc_1400093CC
0x140009283  mov     rcx, [rsp+280h+hObject]; hObject
0x140009288  test    rcx, rcx
0x14000928b  jz      short loc_14000929B
0x14000928d  call    cs:__imp_CloseHandle
0x140009293  test    eax, eax
0x140009295  jz      loc_1400093DE
0x14000929b  call    cs:__imp_GetProcessHeap
0x1400092a1  mov     r8, rsi; lpMem
0x1400092a4  xor     edx, edx; dwFlags
0x1400092a6  mov     rcx, rax; hHeap
0x1400092a9  call    cs:__imp_HeapFree
0x1400092af  mov     rcx, [rbp+188h]; this
0x1400092b6  mov     r9d, r14d; char *
0x1400092b9  mov     edx, 137h; void *
0x1400092be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400092c3  test    rdi, rdi
0x1400092c6  jz      short loc_1400092D9
0x1400092c8  mov     rcx, rdi; hMutex
0x1400092cb  call    cs:__imp_ReleaseMutex
0x1400092d1  test    eax, eax
0x1400092d3  jz      loc_1400093F0
0x1400092d9  mov     rcx, rbx; hObject
0x1400092dc  call    cs:__imp_CloseHandle
0x1400092e2  test    eax, eax
0x1400092e4  jz      loc_140009402
0x1400092ea  mov     eax, r14d
0x1400092ed  jmp     short loc_14000935D
0x1400092ef  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400092f4  xor     edx, edx; Val
0x1400092f6  mov     dword ptr [rsi], 1
0x1400092fc  lea     rcx, [rsi+22h]; void *
0x140009300  mov     [rsi+8], rbx
0x140009304  movdqu  xmmword ptr [rsi+10h], xmm0
0x140009309  lea     r8d, [rdx+56h]; Size
0x14000930d  call    memset_0
0x140009312  xor     edx, edx; Val
0x140009314  mov     word ptr [rsi+20h], 58h ; 'X'
0x14000931a  lea     rcx, [rsi+28h]; void *
0x14000931e  mov     dword ptr [rsi+24h], 1
0x140009325  lea     r8d, [rdx+50h]; Size
0x140009329  call    memset_0
0x14000932e  xor     ebx, ebx
0x140009330  mov     [r15], rsi
0x140009333  test    rdi, rdi
0x140009336  jz      short loc_140009349
0x140009338  mov     rcx, rdi; hMutex
0x14000933b  call    cs:__imp_ReleaseMutex
0x140009341  test    eax, eax
0x140009343  jz      loc_140009414
0x140009349  test    rbx, rbx
0x14000934c  jz      short loc_14000935B
0x14000934e  mov     rcx, rbx; hObject
0x140009351  call    cs:__imp_CloseHandle
0x140009357  test    eax, eax
0x140009359  jz      short loc_140009383
0x14000935b  xor     eax, eax
0x14000935d  mov     rcx, [rbp+180h+var_30]
0x140009364  xor     rcx, rsp; StackCookie
0x140009367  call    __security_check_cookie
0x14000936c  mov     rbx, [rsp+280h+arg_10]
0x140009374  add     rsp, 260h
0x14000937b  pop     r15
0x14000937d  pop     r14
0x14000937f  pop     rdi
0x140009380  pop     rsi
0x140009381  pop     rbp
0x140009382  retn
0x140009383  mov     rcx, [rbp+188h]; this
0x14000938a  mov     edx, 0A0Bh; void *
0x14000938f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009395  mov     rcx, [rbp+188h]; this
0x14000939c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400093a2  mov     rcx, [rbp+188h]; this
0x1400093a9  mov     edx, 0A15h; void *
0x1400093ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400093b4  mov     rcx, [rbp+188h]; this
0x1400093bb  mov     edx, 0A0Bh; void *
0x1400093c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400093c6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400093cc  mov     rcx, [rbp+188h]; this
0x1400093d3  mov     edx, 0A0Bh; void *
0x1400093d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400093de  mov     rcx, [rbp+188h]; this
0x1400093e5  mov     edx, 0A0Bh; void *
0x1400093ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400093f0  mov     rcx, [rbp+188h]; this
0x1400093f7  mov     edx, 0A15h; void *
0x1400093fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009402  mov     rcx, [rbp+188h]; this
0x140009409  mov     edx, 0A0Bh; void *
0x14000940e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009414  mov     rcx, [rbp+188h]; this
0x14000941b  mov     edx, 0A15h; void *
0x140009420  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
