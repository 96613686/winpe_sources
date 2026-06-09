# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004df8`
- end: `0x180005196`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006660`

## callees

- `0x1800026f0`
- `0x18000329c`
- `0x180004df8`
- `0x18000556c`
- `0x180005a90`
- `0x1800063f0`
- `0x1800070f4`
- `0x1800086cc`
- `0x1800091e4`
- `0x18000964c`
- `0x180009efc`
- `0x180009f0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000503b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800050ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000503b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800050ab`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004e70`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004e70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004e91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004e91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000500b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000500b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005019`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005019`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ffd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000504c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ffd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000504c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180004df8  mov     [rsp-8+arg_10], rbx
0x180004dfd  push    rbp
0x180004dfe  push    rsi
0x180004dff  push    rdi
0x180004e00  push    r14
0x180004e02  push    r15
0x180004e04  lea     rbp, [rsp-160h]
0x180004e0c  sub     rsp, 260h
0x180004e13  mov     rax, cs:__security_cookie
0x180004e1a  xor     rax, rsp
0x180004e1d  mov     [rbp+180h+var_30], rax
0x180004e24  mov     r15, rdx
0x180004e27  mov     qword ptr [rdx], 0
0x180004e2e  mov     rbx, rcx
0x180004e31  call    cs:__imp_GetCurrentProcessId
0x180004e37  mov     r14d, 78h ; 'x'
0x180004e3d  mov     [rsp+280h+var_258], rbx
0x180004e42  mov     r9d, eax
0x180004e45  mov     [rsp+280h+var_260], r14d; int
0x180004e4a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004e51  mov     edx, 104h; unsigned __int64
0x180004e56  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180004e5b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004e60  mov     r9d, 1F0001h; dwDesiredAccess
0x180004e66  lea     rdx, [rsp+280h+Name]; lpName
0x180004e6b  xor     r8d, r8d; dwFlags
0x180004e6e  xor     ecx, ecx; lpMutexAttributes
0x180004e70  call    cs:__imp_CreateMutexExW
0x180004e76  mov     rbx, rax
0x180004e79  test    rax, rax
0x180004e7c  jnz     short loc_180004E88
0x180004e7e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004e83  jmp     loc_1800050CD
0x180004e88  xor     r8d, r8d; bAlertable
0x180004e8b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004e8e  mov     rcx, rbx; hHandle
0x180004e91  call    cs:__imp_WaitForSingleObjectEx
0x180004e97  cmp     eax, 102h
0x180004e9c  jz      short loc_180004EAE
0x180004e9e  test    eax, 0FFFFFF7Fh
0x180004ea3  jnz     loc_180005105
0x180004ea9  mov     rdi, rbx
0x180004eac  jmp     short loc_180004EB0
0x180004eae  xor     edi, edi
0x180004eb0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004eb5  mov     [rsp+280h+hObject], 0
0x180004ebe  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180004ec3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180004ec8  mov     esi, eax
0x180004eca  test    eax, eax
0x180004ecc  jns     short loc_180004F38
0x180004ece  mov     rcx, [rbp+188h]; this
0x180004ed5  mov     r9d, eax; char *
0x180004ed8  mov     edx, 66h ; 'f'; void *
0x180004edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ee2  mov     rcx, [rbp+188h]; this
0x180004ee9  mov     r9d, esi; char *
0x180004eec  mov     edx, 6Fh ; 'o'; void *
0x180004ef1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ef6  mov     rcx, [rbp+188h]; this
0x180004efd  mov     r9d, esi; char *
0x180004f00  mov     edx, 12Eh; void *
0x180004f05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f0a  test    rdi, rdi
0x180004f0d  jz      short loc_180004F20
0x180004f0f  mov     rcx, rdi; hMutex
0x180004f12  call    cs:__imp_ReleaseMutex
0x180004f18  test    eax, eax
0x180004f1a  jz      loc_180005112
0x180004f20  mov     rcx, rbx; hObject
0x180004f23  call    cs:__imp_CloseHandle
0x180004f29  test    eax, eax
0x180004f2b  jz      loc_180005124
0x180004f31  mov     eax, esi
0x180004f33  jmp     loc_1800050CD
0x180004f38  mov     rax, [rsp+280h+hObject]
0x180004f3d  lea     rcx, ds:0[rax*4]
0x180004f45  test    rcx, rcx
0x180004f48  jz      short loc_180004F58
0x180004f4a  mov     [r15], rcx
0x180004f4d  mov     eax, [rcx]
0x180004f4f  inc     eax
0x180004f51  mov     [rcx], eax
0x180004f53  jmp     loc_1800050A3
0x180004f58  mov     rdx, r14; dwBytes
0x180004f5b  mov     qword ptr [r15], 0
0x180004f62  mov     ecx, 8; dwFlags
0x180004f67  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004f6c  mov     rsi, rax
0x180004f6f  test    rax, rax
0x180004f72  jnz     short loc_180004F93
0x180004f74  mov     rcx, [rbp+188h]; this
0x180004f7b  mov     r14d, 8007000Eh
0x180004f81  mov     r9d, r14d; char *
0x180004f84  mov     edx, 14Bh; void *
0x180004f89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f8e  jmp     loc_18000501F
0x180004f93  xorps   xmm0, xmm0
0x180004f96  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004f9c  test    sil, 3
0x180004fa0  jnz     loc_180005136
0x180004fa6  mov     r9, rsi
0x180004fa9  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180004fae  shr     r9, 2; unsigned __int64
0x180004fb2  lea     rcx, [rsp+280h+hObject]; this
0x180004fb7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180004fbc  mov     r14d, eax
0x180004fbf  test    eax, eax
0x180004fc1  jns     loc_18000505F
0x180004fc7  mov     rcx, [rbp+188h]; this
0x180004fce  mov     r9d, eax; char *
0x180004fd1  mov     edx, 14Eh; void *
0x180004fd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004fdb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004fe0  test    rcx, rcx
0x180004fe3  jz      short loc_180004FF3
0x180004fe5  call    cs:__imp_CloseHandle
0x180004feb  test    eax, eax
0x180004fed  jz      loc_18000513C
0x180004ff3  mov     rcx, [rsp+280h+hObject]; hObject
0x180004ff8  test    rcx, rcx
0x180004ffb  jz      short loc_18000500B
0x180004ffd  call    cs:__imp_CloseHandle
0x180005003  test    eax, eax
0x180005005  jz      loc_18000514E
0x18000500b  call    cs:__imp_GetProcessHeap
0x180005011  mov     r8, rsi; lpMem
0x180005014  xor     edx, edx; dwFlags
0x180005016  mov     rcx, rax; hHeap
0x180005019  call    cs:__imp_HeapFree
0x18000501f  mov     rcx, [rbp+188h]; this
0x180005026  mov     r9d, r14d; char *
0x180005029  mov     edx, 137h; void *
0x18000502e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005033  test    rdi, rdi
0x180005036  jz      short loc_180005049
0x180005038  mov     rcx, rdi; hMutex
0x18000503b  call    cs:__imp_ReleaseMutex
0x180005041  test    eax, eax
0x180005043  jz      loc_180005160
0x180005049  mov     rcx, rbx; hObject
0x18000504c  call    cs:__imp_CloseHandle
0x180005052  test    eax, eax
0x180005054  jz      loc_180005172
0x18000505a  mov     eax, r14d
0x18000505d  jmp     short loc_1800050CD
0x18000505f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005064  xor     edx, edx; Val
0x180005066  mov     dword ptr [rsi], 1
0x18000506c  lea     rcx, [rsi+22h]; void *
0x180005070  mov     [rsi+8], rbx
0x180005074  movdqu  xmmword ptr [rsi+10h], xmm0
0x180005079  lea     r8d, [rdx+56h]; Size
0x18000507d  call    memset_0
0x180005082  xor     edx, edx; Val
0x180005084  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000508a  lea     rcx, [rsi+28h]; void *
0x18000508e  mov     dword ptr [rsi+24h], 1
0x180005095  lea     r8d, [rdx+50h]; Size
0x180005099  call    memset_0
0x18000509e  xor     ebx, ebx
0x1800050a0  mov     [r15], rsi
0x1800050a3  test    rdi, rdi
0x1800050a6  jz      short loc_1800050B9
0x1800050a8  mov     rcx, rdi; hMutex
0x1800050ab  call    cs:__imp_ReleaseMutex
0x1800050b1  test    eax, eax
0x1800050b3  jz      loc_180005184
0x1800050b9  test    rbx, rbx
0x1800050bc  jz      short loc_1800050CB
0x1800050be  mov     rcx, rbx; hObject
0x1800050c1  call    cs:__imp_CloseHandle
0x1800050c7  test    eax, eax
0x1800050c9  jz      short loc_1800050F3
0x1800050cb  xor     eax, eax
0x1800050cd  mov     rcx, [rbp+180h+var_30]
0x1800050d4  xor     rcx, rsp; StackCookie
0x1800050d7  call    __security_check_cookie
0x1800050dc  mov     rbx, [rsp+280h+arg_10]
0x1800050e4  add     rsp, 260h
0x1800050eb  pop     r15
0x1800050ed  pop     r14
0x1800050ef  pop     rdi
0x1800050f0  pop     rsi
0x1800050f1  pop     rbp
0x1800050f2  retn
0x1800050f3  mov     rcx, [rbp+188h]; this
0x1800050fa  mov     edx, 0A0Bh; void *
0x1800050ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005105  mov     rcx, [rbp+188h]; this
0x18000510c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005112  mov     rcx, [rbp+188h]; this
0x180005119  mov     edx, 0A15h; void *
0x18000511e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005124  mov     rcx, [rbp+188h]; this
0x18000512b  mov     edx, 0A0Bh; void *
0x180005130  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005136  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000513c  mov     rcx, [rbp+188h]; this
0x180005143  mov     edx, 0A0Bh; void *
0x180005148  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000514e  mov     rcx, [rbp+188h]; this
0x180005155  mov     edx, 0A0Bh; void *
0x18000515a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005160  mov     rcx, [rbp+188h]; this
0x180005167  mov     edx, 0A15h; void *
0x18000516c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005172  mov     rcx, [rbp+188h]; this
0x180005179  mov     edx, 0A0Bh; void *
0x18000517e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005184  mov     rcx, [rbp+188h]; this
0x18000518b  mov     edx, 0A15h; void *
0x180005190  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
