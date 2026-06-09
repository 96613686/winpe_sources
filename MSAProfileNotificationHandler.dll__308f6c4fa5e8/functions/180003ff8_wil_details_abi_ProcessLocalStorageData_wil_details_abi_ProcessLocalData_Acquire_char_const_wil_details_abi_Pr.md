# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003ff8`
- end: `0x180004396`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004e70`

## callees

- `0x180001cb0`
- `0x1800028f0`
- `0x180003ff8`
- `0x18000439c`
- `0x1800045c0`
- `0x180004c08`
- `0x18000577c`
- `0x180005dc4`
- `0x180006120`
- `0x180006460`
- `0x180006efc`
- `0x180006f0c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004123`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000424c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004123`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000424c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004031`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004031`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004070`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004070`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004091`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004091`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004112`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000423b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800042ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004112`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000423b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800042ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000420b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000420b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004219`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004219`

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
0x180003ff8  mov     [rsp-8+arg_10], rbx
0x180003ffd  push    rbp
0x180003ffe  push    rsi
0x180003fff  push    rdi
0x180004000  push    r14
0x180004002  push    r15
0x180004004  lea     rbp, [rsp-160h]
0x18000400c  sub     rsp, 260h
0x180004013  mov     rax, cs:__security_cookie
0x18000401a  xor     rax, rsp
0x18000401d  mov     [rbp+180h+var_30], rax
0x180004024  mov     r15, rdx
0x180004027  mov     qword ptr [rdx], 0
0x18000402e  mov     rbx, rcx
0x180004031  call    cs:__imp_GetCurrentProcessId
0x180004037  mov     r14d, 78h ; 'x'
0x18000403d  mov     [rsp+280h+var_258], rbx
0x180004042  mov     r9d, eax
0x180004045  mov     [rsp+280h+var_260], r14d; int
0x18000404a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004051  mov     edx, 104h; unsigned __int64
0x180004056  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000405b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004060  mov     r9d, 1F0001h; dwDesiredAccess
0x180004066  lea     rdx, [rsp+280h+Name]; lpName
0x18000406b  xor     r8d, r8d; dwFlags
0x18000406e  xor     ecx, ecx; lpMutexAttributes
0x180004070  call    cs:__imp_CreateMutexExW
0x180004076  mov     rbx, rax
0x180004079  test    rax, rax
0x18000407c  jnz     short loc_180004088
0x18000407e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004083  jmp     loc_1800042CD
0x180004088  xor     r8d, r8d; bAlertable
0x18000408b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000408e  mov     rcx, rbx; hHandle
0x180004091  call    cs:__imp_WaitForSingleObjectEx
0x180004097  cmp     eax, 102h
0x18000409c  jz      short loc_1800040AE
0x18000409e  test    eax, 0FFFFFF7Fh
0x1800040a3  jnz     loc_180004305
0x1800040a9  mov     rdi, rbx
0x1800040ac  jmp     short loc_1800040B0
0x1800040ae  xor     edi, edi
0x1800040b0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800040b5  mov     [rsp+280h+hObject], 0
0x1800040be  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800040c3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800040c8  mov     esi, eax
0x1800040ca  test    eax, eax
0x1800040cc  jns     short loc_180004138
0x1800040ce  mov     rcx, [rbp+188h]; this
0x1800040d5  mov     r9d, eax; char *
0x1800040d8  mov     edx, 66h ; 'f'; void *
0x1800040dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040e2  mov     rcx, [rbp+188h]; this
0x1800040e9  mov     r9d, esi; char *
0x1800040ec  mov     edx, 6Fh ; 'o'; void *
0x1800040f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040f6  mov     rcx, [rbp+188h]; this
0x1800040fd  mov     r9d, esi; char *
0x180004100  mov     edx, 12Eh; void *
0x180004105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000410a  test    rdi, rdi
0x18000410d  jz      short loc_180004120
0x18000410f  mov     rcx, rdi; hMutex
0x180004112  call    cs:__imp_ReleaseMutex
0x180004118  test    eax, eax
0x18000411a  jz      loc_180004312
0x180004120  mov     rcx, rbx; hObject
0x180004123  call    cs:__imp_CloseHandle
0x180004129  test    eax, eax
0x18000412b  jz      loc_180004324
0x180004131  mov     eax, esi
0x180004133  jmp     loc_1800042CD
0x180004138  mov     rax, [rsp+280h+hObject]
0x18000413d  lea     rcx, ds:0[rax*4]
0x180004145  test    rcx, rcx
0x180004148  jz      short loc_180004158
0x18000414a  mov     [r15], rcx
0x18000414d  mov     eax, [rcx]
0x18000414f  inc     eax
0x180004151  mov     [rcx], eax
0x180004153  jmp     loc_1800042A3
0x180004158  mov     rdx, r14; dwBytes
0x18000415b  mov     qword ptr [r15], 0
0x180004162  mov     ecx, 8; dwFlags
0x180004167  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000416c  mov     rsi, rax
0x18000416f  test    rax, rax
0x180004172  jnz     short loc_180004193
0x180004174  mov     rcx, [rbp+188h]; this
0x18000417b  mov     r14d, 8007000Eh
0x180004181  mov     r9d, r14d; char *
0x180004184  mov     edx, 14Bh; void *
0x180004189  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000418e  jmp     loc_18000421F
0x180004193  xorps   xmm0, xmm0
0x180004196  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000419c  test    sil, 3
0x1800041a0  jnz     loc_180004336
0x1800041a6  mov     r9, rsi
0x1800041a9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800041ae  shr     r9, 2; unsigned __int64
0x1800041b2  lea     rcx, [rsp+280h+hObject]; this
0x1800041b7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800041bc  mov     r14d, eax
0x1800041bf  test    eax, eax
0x1800041c1  jns     loc_18000425F
0x1800041c7  mov     rcx, [rbp+188h]; this
0x1800041ce  mov     r9d, eax; char *
0x1800041d1  mov     edx, 14Eh; void *
0x1800041d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041db  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800041e0  test    rcx, rcx
0x1800041e3  jz      short loc_1800041F3
0x1800041e5  call    cs:__imp_CloseHandle
0x1800041eb  test    eax, eax
0x1800041ed  jz      loc_18000433C
0x1800041f3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800041f8  test    rcx, rcx
0x1800041fb  jz      short loc_18000420B
0x1800041fd  call    cs:__imp_CloseHandle
0x180004203  test    eax, eax
0x180004205  jz      loc_18000434E
0x18000420b  call    cs:__imp_GetProcessHeap
0x180004211  mov     r8, rsi; lpMem
0x180004214  xor     edx, edx; dwFlags
0x180004216  mov     rcx, rax; hHeap
0x180004219  call    cs:__imp_HeapFree
0x18000421f  mov     rcx, [rbp+188h]; this
0x180004226  mov     r9d, r14d; char *
0x180004229  mov     edx, 137h; void *
0x18000422e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004233  test    rdi, rdi
0x180004236  jz      short loc_180004249
0x180004238  mov     rcx, rdi; hMutex
0x18000423b  call    cs:__imp_ReleaseMutex
0x180004241  test    eax, eax
0x180004243  jz      loc_180004360
0x180004249  mov     rcx, rbx; hObject
0x18000424c  call    cs:__imp_CloseHandle
0x180004252  test    eax, eax
0x180004254  jz      loc_180004372
0x18000425a  mov     eax, r14d
0x18000425d  jmp     short loc_1800042CD
0x18000425f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004264  xor     edx, edx; Val
0x180004266  mov     dword ptr [rsi], 1
0x18000426c  lea     rcx, [rsi+22h]; void *
0x180004270  mov     [rsi+8], rbx
0x180004274  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004279  lea     r8d, [rdx+56h]; Size
0x18000427d  call    memset_0
0x180004282  xor     edx, edx; Val
0x180004284  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000428a  lea     rcx, [rsi+28h]; void *
0x18000428e  mov     dword ptr [rsi+24h], 1
0x180004295  lea     r8d, [rdx+50h]; Size
0x180004299  call    memset_0
0x18000429e  xor     ebx, ebx
0x1800042a0  mov     [r15], rsi
0x1800042a3  test    rdi, rdi
0x1800042a6  jz      short loc_1800042B9
0x1800042a8  mov     rcx, rdi; hMutex
0x1800042ab  call    cs:__imp_ReleaseMutex
0x1800042b1  test    eax, eax
0x1800042b3  jz      loc_180004384
0x1800042b9  test    rbx, rbx
0x1800042bc  jz      short loc_1800042CB
0x1800042be  mov     rcx, rbx; hObject
0x1800042c1  call    cs:__imp_CloseHandle
0x1800042c7  test    eax, eax
0x1800042c9  jz      short loc_1800042F3
0x1800042cb  xor     eax, eax
0x1800042cd  mov     rcx, [rbp+180h+var_30]
0x1800042d4  xor     rcx, rsp; StackCookie
0x1800042d7  call    __security_check_cookie
0x1800042dc  mov     rbx, [rsp+280h+arg_10]
0x1800042e4  add     rsp, 260h
0x1800042eb  pop     r15
0x1800042ed  pop     r14
0x1800042ef  pop     rdi
0x1800042f0  pop     rsi
0x1800042f1  pop     rbp
0x1800042f2  retn
0x1800042f3  mov     rcx, [rbp+188h]; this
0x1800042fa  mov     edx, 0A0Bh; void *
0x1800042ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004305  mov     rcx, [rbp+188h]; this
0x18000430c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004312  mov     rcx, [rbp+188h]; this
0x180004319  mov     edx, 0A15h; void *
0x18000431e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004324  mov     rcx, [rbp+188h]; this
0x18000432b  mov     edx, 0A0Bh; void *
0x180004330  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004336  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000433c  mov     rcx, [rbp+188h]; this
0x180004343  mov     edx, 0A0Bh; void *
0x180004348  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000434e  mov     rcx, [rbp+188h]; this
0x180004355  mov     edx, 0A0Bh; void *
0x18000435a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004360  mov     rcx, [rbp+188h]; this
0x180004367  mov     edx, 0A15h; void *
0x18000436c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004372  mov     rcx, [rbp+188h]; this
0x180004379  mov     edx, 0A0Bh; void *
0x18000437e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004384  mov     rcx, [rbp+188h]; this
0x18000438b  mov     edx, 0A15h; void *
0x180004390  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
