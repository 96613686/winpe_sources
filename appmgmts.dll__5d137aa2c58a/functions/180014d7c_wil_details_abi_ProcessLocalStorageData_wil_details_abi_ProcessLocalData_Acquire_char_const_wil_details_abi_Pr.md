# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180014d7c`
- end: `0x18001511a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180016500`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180008f58`
- `0x180014d7c`
- `0x1800154f0`
- `0x180015964`
- `0x180016298`
- `0x180016e88`
- `0x1800181b4`
- `0x180018ecc`
- `0x1800196ac`
- `0x1800196bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014db5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014db5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ea7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014fd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ea7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014fd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015045`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014e96`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014fbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001502f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014e96`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014fbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001502f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180014df4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180014df4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014e15`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014e15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014f9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014f9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014f8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014f8f`

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
0x180014d7c  mov     [rsp-8+arg_10], rbx
0x180014d81  push    rbp
0x180014d82  push    rsi
0x180014d83  push    rdi
0x180014d84  push    r14
0x180014d86  push    r15
0x180014d88  lea     rbp, [rsp-160h]
0x180014d90  sub     rsp, 260h
0x180014d97  mov     rax, cs:__security_cookie
0x180014d9e  xor     rax, rsp
0x180014da1  mov     [rbp+180h+var_30], rax
0x180014da8  mov     r15, rdx
0x180014dab  mov     qword ptr [rdx], 0
0x180014db2  mov     rbx, rcx
0x180014db5  call    cs:__imp_GetCurrentProcessId
0x180014dbb  mov     r14d, 78h ; 'x'
0x180014dc1  mov     [rsp+280h+var_258], rbx
0x180014dc6  mov     r9d, eax
0x180014dc9  mov     [rsp+280h+var_260], r14d; int
0x180014dce  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180014dd5  mov     edx, 104h; unsigned __int64
0x180014dda  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180014ddf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014de4  mov     r9d, 1F0001h; dwDesiredAccess
0x180014dea  lea     rdx, [rsp+280h+Name]; lpName
0x180014def  xor     r8d, r8d; dwFlags
0x180014df2  xor     ecx, ecx; lpMutexAttributes
0x180014df4  call    cs:__imp_CreateMutexExW
0x180014dfa  mov     rbx, rax
0x180014dfd  test    rax, rax
0x180014e00  jnz     short loc_180014E0C
0x180014e02  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180014e07  jmp     loc_180015051
0x180014e0c  xor     r8d, r8d; bAlertable
0x180014e0f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014e12  mov     rcx, rbx; hHandle
0x180014e15  call    cs:__imp_WaitForSingleObjectEx
0x180014e1b  cmp     eax, 102h
0x180014e20  jz      short loc_180014E32
0x180014e22  test    eax, 0FFFFFF7Fh
0x180014e27  jnz     loc_180015089
0x180014e2d  mov     rdi, rbx
0x180014e30  jmp     short loc_180014E34
0x180014e32  xor     edi, edi
0x180014e34  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180014e39  mov     [rsp+280h+hObject], 0
0x180014e42  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180014e47  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180014e4c  mov     esi, eax
0x180014e4e  test    eax, eax
0x180014e50  jns     short loc_180014EBC
0x180014e52  mov     rcx, [rbp+188h]; this
0x180014e59  mov     r9d, eax; char *
0x180014e5c  mov     edx, 66h ; 'f'; void *
0x180014e61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e66  mov     rcx, [rbp+188h]; this
0x180014e6d  mov     r9d, esi; char *
0x180014e70  mov     edx, 6Fh ; 'o'; void *
0x180014e75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e7a  mov     rcx, [rbp+188h]; this
0x180014e81  mov     r9d, esi; char *
0x180014e84  mov     edx, 12Eh; void *
0x180014e89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e8e  test    rdi, rdi
0x180014e91  jz      short loc_180014EA4
0x180014e93  mov     rcx, rdi; hMutex
0x180014e96  call    cs:__imp_ReleaseMutex
0x180014e9c  test    eax, eax
0x180014e9e  jz      loc_180015096
0x180014ea4  mov     rcx, rbx; hObject
0x180014ea7  call    cs:__imp_CloseHandle
0x180014ead  test    eax, eax
0x180014eaf  jz      loc_1800150A8
0x180014eb5  mov     eax, esi
0x180014eb7  jmp     loc_180015051
0x180014ebc  mov     rax, [rsp+280h+hObject]
0x180014ec1  lea     rcx, ds:0[rax*4]
0x180014ec9  test    rcx, rcx
0x180014ecc  jz      short loc_180014EDC
0x180014ece  mov     [r15], rcx
0x180014ed1  mov     eax, [rcx]
0x180014ed3  inc     eax
0x180014ed5  mov     [rcx], eax
0x180014ed7  jmp     loc_180015027
0x180014edc  mov     rdx, r14; dwBytes
0x180014edf  mov     qword ptr [r15], 0
0x180014ee6  mov     ecx, 8; dwFlags
0x180014eeb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180014ef0  mov     rsi, rax
0x180014ef3  test    rax, rax
0x180014ef6  jnz     short loc_180014F17
0x180014ef8  mov     rcx, [rbp+188h]; this
0x180014eff  mov     r14d, 8007000Eh
0x180014f05  mov     r9d, r14d; char *
0x180014f08  mov     edx, 14Bh; void *
0x180014f0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014f12  jmp     loc_180014FA3
0x180014f17  xorps   xmm0, xmm0
0x180014f1a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180014f20  test    sil, 3
0x180014f24  jnz     loc_1800150BA
0x180014f2a  mov     r9, rsi
0x180014f2d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180014f32  shr     r9, 2; unsigned __int64
0x180014f36  lea     rcx, [rsp+280h+hObject]; this
0x180014f3b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180014f40  mov     r14d, eax
0x180014f43  test    eax, eax
0x180014f45  jns     loc_180014FE3
0x180014f4b  mov     rcx, [rbp+188h]; this
0x180014f52  mov     r9d, eax; char *
0x180014f55  mov     edx, 14Eh; void *
0x180014f5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014f5f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180014f64  test    rcx, rcx
0x180014f67  jz      short loc_180014F77
0x180014f69  call    cs:__imp_CloseHandle
0x180014f6f  test    eax, eax
0x180014f71  jz      loc_1800150C0
0x180014f77  mov     rcx, [rsp+280h+hObject]; hObject
0x180014f7c  test    rcx, rcx
0x180014f7f  jz      short loc_180014F8F
0x180014f81  call    cs:__imp_CloseHandle
0x180014f87  test    eax, eax
0x180014f89  jz      loc_1800150D2
0x180014f8f  call    cs:__imp_GetProcessHeap
0x180014f95  mov     r8, rsi; lpMem
0x180014f98  xor     edx, edx; dwFlags
0x180014f9a  mov     rcx, rax; hHeap
0x180014f9d  call    cs:__imp_HeapFree
0x180014fa3  mov     rcx, [rbp+188h]; this
0x180014faa  mov     r9d, r14d; char *
0x180014fad  mov     edx, 137h; void *
0x180014fb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014fb7  test    rdi, rdi
0x180014fba  jz      short loc_180014FCD
0x180014fbc  mov     rcx, rdi; hMutex
0x180014fbf  call    cs:__imp_ReleaseMutex
0x180014fc5  test    eax, eax
0x180014fc7  jz      loc_1800150E4
0x180014fcd  mov     rcx, rbx; hObject
0x180014fd0  call    cs:__imp_CloseHandle
0x180014fd6  test    eax, eax
0x180014fd8  jz      loc_1800150F6
0x180014fde  mov     eax, r14d
0x180014fe1  jmp     short loc_180015051
0x180014fe3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180014fe8  xor     edx, edx; Val
0x180014fea  mov     dword ptr [rsi], 1
0x180014ff0  lea     rcx, [rsi+22h]; void *
0x180014ff4  mov     [rsi+8], rbx
0x180014ff8  movdqu  xmmword ptr [rsi+10h], xmm0
0x180014ffd  lea     r8d, [rdx+56h]; Size
0x180015001  call    memset_0
0x180015006  xor     edx, edx; Val
0x180015008  mov     word ptr [rsi+20h], 58h ; 'X'
0x18001500e  lea     rcx, [rsi+28h]; void *
0x180015012  mov     dword ptr [rsi+24h], 1
0x180015019  lea     r8d, [rdx+50h]; Size
0x18001501d  call    memset_0
0x180015022  xor     ebx, ebx
0x180015024  mov     [r15], rsi
0x180015027  test    rdi, rdi
0x18001502a  jz      short loc_18001503D
0x18001502c  mov     rcx, rdi; hMutex
0x18001502f  call    cs:__imp_ReleaseMutex
0x180015035  test    eax, eax
0x180015037  jz      loc_180015108
0x18001503d  test    rbx, rbx
0x180015040  jz      short loc_18001504F
0x180015042  mov     rcx, rbx; hObject
0x180015045  call    cs:__imp_CloseHandle
0x18001504b  test    eax, eax
0x18001504d  jz      short loc_180015077
0x18001504f  xor     eax, eax
0x180015051  mov     rcx, [rbp+180h+var_30]
0x180015058  xor     rcx, rsp; StackCookie
0x18001505b  call    __security_check_cookie
0x180015060  mov     rbx, [rsp+280h+arg_10]
0x180015068  add     rsp, 260h
0x18001506f  pop     r15
0x180015071  pop     r14
0x180015073  pop     rdi
0x180015074  pop     rsi
0x180015075  pop     rbp
0x180015076  retn
0x180015077  mov     rcx, [rbp+188h]; this
0x18001507e  mov     edx, 0A0Bh; void *
0x180015083  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015089  mov     rcx, [rbp+188h]; this
0x180015090  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180015096  mov     rcx, [rbp+188h]; this
0x18001509d  mov     edx, 0A15h; void *
0x1800150a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800150a8  mov     rcx, [rbp+188h]; this
0x1800150af  mov     edx, 0A0Bh; void *
0x1800150b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800150ba  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800150c0  mov     rcx, [rbp+188h]; this
0x1800150c7  mov     edx, 0A0Bh; void *
0x1800150cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800150d2  mov     rcx, [rbp+188h]; this
0x1800150d9  mov     edx, 0A0Bh; void *
0x1800150de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800150e4  mov     rcx, [rbp+188h]; this
0x1800150eb  mov     edx, 0A15h; void *
0x1800150f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800150f6  mov     rcx, [rbp+188h]; this
0x1800150fd  mov     edx, 0A0Bh; void *
0x180015102  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180015108  mov     rcx, [rbp+188h]; this
0x18001510f  mov     edx, 0A15h; void *
0x180015114  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
