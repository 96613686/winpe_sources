# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003e88`
- end: `0x180004250`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004e00`

## callees

- `0x180002170`
- `0x180002cb4`
- `0x180003e88`
- `0x180004258`
- `0x180004544`
- `0x180004b98`
- `0x180005678`
- `0x180005ad4`
- `0x1800064c4`
- `0x18000659c`
- `0x18000697c`
- `0x18000698c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004165`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004165`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003f21`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003f21`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003f00`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003f00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ec1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004106`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000417b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004106`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000417b`

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
0x180003e88  mov     [rsp-8+arg_10], rbx
0x180003e8d  push    rbp
0x180003e8e  push    rsi
0x180003e8f  push    rdi
0x180003e90  push    r14
0x180003e92  push    r15
0x180003e94  lea     rbp, [rsp-160h]
0x180003e9c  sub     rsp, 260h
0x180003ea3  mov     rax, cs:__security_cookie
0x180003eaa  xor     rax, rsp
0x180003ead  mov     [rbp+180h+var_30], rax
0x180003eb4  mov     r15, rdx
0x180003eb7  mov     qword ptr [rdx], 0
0x180003ebe  mov     rbx, rcx
0x180003ec1  call    cs:__imp_GetCurrentProcessId
0x180003ec7  mov     r14d, 78h ; 'x'
0x180003ecd  mov     [rsp+280h+var_258], rbx
0x180003ed2  mov     r9d, eax
0x180003ed5  mov     [rsp+280h+var_260], r14d; int
0x180003eda  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003ee1  mov     edx, 104h; unsigned __int64
0x180003ee6  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180003eeb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180003ef0  mov     r9d, 1F0001h; dwDesiredAccess
0x180003ef6  lea     rdx, [rsp+280h+Name]; lpName
0x180003efb  xor     r8d, r8d; dwFlags
0x180003efe  xor     ecx, ecx; lpMutexAttributes
0x180003f00  call    cs:__imp_CreateMutexExW
0x180003f06  mov     rbx, rax
0x180003f09  test    rax, rax
0x180003f0c  jnz     short loc_180003F18
0x180003f0e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003f13  jmp     loc_180004187
0x180003f18  xor     r8d, r8d; bAlertable
0x180003f1b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003f1e  mov     rcx, rbx; hHandle
0x180003f21  call    cs:__imp_WaitForSingleObjectEx
0x180003f27  cmp     eax, 102h
0x180003f2c  jz      short loc_180003F3E
0x180003f2e  test    eax, 0FFFFFF7Fh
0x180003f33  jnz     loc_1800041BF
0x180003f39  mov     rdi, rbx
0x180003f3c  jmp     short loc_180003F40
0x180003f3e  xor     edi, edi
0x180003f40  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003f45  mov     [rsp+280h+hObject], 0
0x180003f4e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180003f53  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180003f58  mov     esi, eax
0x180003f5a  test    eax, eax
0x180003f5c  jns     short loc_180003FDD
0x180003f5e  mov     rcx, [rbp+188h]; this
0x180003f65  lea     r8, aWil; "wil"
0x180003f6c  mov     r9d, eax; char *
0x180003f6f  mov     edx, 66h ; 'f'; void *
0x180003f74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f79  mov     rcx, [rbp+188h]; this
0x180003f80  lea     r8, aWil; "wil"
0x180003f87  mov     r9d, esi; char *
0x180003f8a  mov     edx, 6Fh ; 'o'; void *
0x180003f8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f94  mov     rcx, [rbp+188h]; this
0x180003f9b  lea     r8, aWil; "wil"
0x180003fa2  mov     r9d, esi; char *
0x180003fa5  mov     edx, 12Eh; void *
0x180003faa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003faf  test    rdi, rdi
0x180003fb2  jz      short loc_180003FC5
0x180003fb4  mov     rcx, rdi; hMutex
0x180003fb7  call    cs:__imp_ReleaseMutex
0x180003fbd  test    eax, eax
0x180003fbf  jz      loc_1800041CC
0x180003fc5  mov     rcx, rbx; hObject
0x180003fc8  call    cs:__imp_CloseHandle
0x180003fce  test    eax, eax
0x180003fd0  jz      loc_1800041DE
0x180003fd6  mov     eax, esi
0x180003fd8  jmp     loc_180004187
0x180003fdd  mov     rax, [rsp+280h+hObject]
0x180003fe2  lea     rcx, ds:0[rax*4]
0x180003fea  test    rcx, rcx
0x180003fed  jz      short loc_180003FFD
0x180003fef  mov     [r15], rcx
0x180003ff2  mov     eax, [rcx]
0x180003ff4  inc     eax
0x180003ff6  mov     [rcx], eax
0x180003ff8  jmp     loc_18000415D
0x180003ffd  mov     rdx, r14; dwBytes
0x180004000  mov     qword ptr [r15], 0
0x180004007  mov     ecx, 8; dwFlags
0x18000400c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004011  mov     rsi, rax
0x180004014  test    rax, rax
0x180004017  jnz     short loc_18000403F
0x180004019  mov     rcx, [rbp+188h]; this
0x180004020  lea     r8, aWil; "wil"
0x180004027  mov     r14d, 8007000Eh
0x18000402d  mov     edx, 14Bh; void *
0x180004032  mov     r9d, r14d; char *
0x180004035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000403a  jmp     loc_1800040D2
0x18000403f  xorps   xmm0, xmm0
0x180004042  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004048  test    sil, 3
0x18000404c  jnz     loc_1800041F0
0x180004052  mov     r9, rsi
0x180004055  lea     rdx, [rsp+280h+Name]; wchar_t *
0x18000405a  shr     r9, 2; unsigned __int64
0x18000405e  lea     rcx, [rsp+280h+hObject]; this
0x180004063  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180004068  mov     r14d, eax
0x18000406b  test    eax, eax
0x18000406d  jns     loc_180004119
0x180004073  mov     rcx, [rbp+188h]; this
0x18000407a  lea     r8, aWil; "wil"
0x180004081  mov     r9d, eax; char *
0x180004084  mov     edx, 14Eh; void *
0x180004089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000408e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004093  test    rcx, rcx
0x180004096  jz      short loc_1800040A6
0x180004098  call    cs:__imp_CloseHandle
0x18000409e  test    eax, eax
0x1800040a0  jz      loc_1800041F6
0x1800040a6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800040ab  test    rcx, rcx
0x1800040ae  jz      short loc_1800040BE
0x1800040b0  call    cs:__imp_CloseHandle
0x1800040b6  test    eax, eax
0x1800040b8  jz      loc_180004208
0x1800040be  call    cs:__imp_GetProcessHeap
0x1800040c4  mov     r8, rsi; lpMem
0x1800040c7  xor     edx, edx; dwFlags
0x1800040c9  mov     rcx, rax; hHeap
0x1800040cc  call    cs:__imp_HeapFree
0x1800040d2  mov     rcx, [rbp+188h]; this
0x1800040d9  lea     r8, aWil; "wil"
0x1800040e0  mov     r9d, r14d; char *
0x1800040e3  mov     edx, 137h; void *
0x1800040e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040ed  test    rdi, rdi
0x1800040f0  jz      short loc_180004103
0x1800040f2  mov     rcx, rdi; hMutex
0x1800040f5  call    cs:__imp_ReleaseMutex
0x1800040fb  test    eax, eax
0x1800040fd  jz      loc_18000421A
0x180004103  mov     rcx, rbx; hObject
0x180004106  call    cs:__imp_CloseHandle
0x18000410c  test    eax, eax
0x18000410e  jz      loc_18000422C
0x180004114  mov     eax, r14d
0x180004117  jmp     short loc_180004187
0x180004119  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000411e  xor     edx, edx; Val
0x180004120  mov     dword ptr [rsi], 1
0x180004126  lea     rcx, [rsi+22h]; void *
0x18000412a  mov     [rsi+8], rbx
0x18000412e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004133  lea     r8d, [rdx+56h]; Size
0x180004137  call    memset_0
0x18000413c  xor     edx, edx; Val
0x18000413e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004144  lea     rcx, [rsi+28h]; void *
0x180004148  mov     dword ptr [rsi+24h], 1
0x18000414f  lea     r8d, [rdx+50h]; Size
0x180004153  call    memset_0
0x180004158  xor     ebx, ebx
0x18000415a  mov     [r15], rsi
0x18000415d  test    rdi, rdi
0x180004160  jz      short loc_180004173
0x180004162  mov     rcx, rdi; hMutex
0x180004165  call    cs:__imp_ReleaseMutex
0x18000416b  test    eax, eax
0x18000416d  jz      loc_18000423E
0x180004173  test    rbx, rbx
0x180004176  jz      short loc_180004185
0x180004178  mov     rcx, rbx; hObject
0x18000417b  call    cs:__imp_CloseHandle
0x180004181  test    eax, eax
0x180004183  jz      short loc_1800041AD
0x180004185  xor     eax, eax
0x180004187  mov     rcx, [rbp+180h+var_30]
0x18000418e  xor     rcx, rsp; StackCookie
0x180004191  call    __security_check_cookie
0x180004196  mov     rbx, [rsp+280h+arg_10]
0x18000419e  add     rsp, 260h
0x1800041a5  pop     r15
0x1800041a7  pop     r14
0x1800041a9  pop     rdi
0x1800041aa  pop     rsi
0x1800041ab  pop     rbp
0x1800041ac  retn
0x1800041ad  mov     rcx, [rbp+188h]; this
0x1800041b4  mov     edx, 0A0Bh; void *
0x1800041b9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041bf  mov     rcx, [rbp+188h]; this
0x1800041c6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800041cc  mov     rcx, [rbp+188h]; this
0x1800041d3  mov     edx, 0A15h; void *
0x1800041d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041de  mov     rcx, [rbp+188h]; this
0x1800041e5  mov     edx, 0A0Bh; void *
0x1800041ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041f0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800041f6  mov     rcx, [rbp+188h]; this
0x1800041fd  mov     edx, 0A0Bh; void *
0x180004202  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004208  mov     rcx, [rbp+188h]; this
0x18000420f  mov     edx, 0A0Bh; void *
0x180004214  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000421a  mov     rcx, [rbp+188h]; this
0x180004221  mov     edx, 0A15h; void *
0x180004226  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000422c  mov     rcx, [rbp+188h]; this
0x180004233  mov     edx, 0A0Bh; void *
0x180004238  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000423e  mov     rcx, [rbp+188h]; this
0x180004245  mov     edx, 0A15h; void *
0x18000424a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
