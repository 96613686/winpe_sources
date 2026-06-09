# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003eb0`
- end: `0x18000424e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800065e0`

## callees

- `0x180003eb0`
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

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003f28`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003f28`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004163`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004163`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003f49`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003f49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ee9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000409d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000409d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004179`

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
0x180003eb0  mov     [rsp-8+arg_10], rbx
0x180003eb5  push    rbp
0x180003eb6  push    rsi
0x180003eb7  push    rdi
0x180003eb8  push    r14
0x180003eba  push    r15
0x180003ebc  lea     rbp, [rsp-160h]
0x180003ec4  sub     rsp, 260h
0x180003ecb  mov     rax, cs:__security_cookie
0x180003ed2  xor     rax, rsp
0x180003ed5  mov     [rbp+180h+var_30], rax
0x180003edc  mov     r15, rdx
0x180003edf  mov     qword ptr [rdx], 0
0x180003ee6  mov     rbx, rcx
0x180003ee9  call    cs:__imp_GetCurrentProcessId
0x180003eef  mov     r14d, 78h ; 'x'
0x180003ef5  mov     [rsp+280h+var_258], rbx
0x180003efa  mov     r9d, eax
0x180003efd  mov     [rsp+280h+var_260], r14d; int
0x180003f02  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003f09  mov     edx, 104h; unsigned __int64
0x180003f0e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003f13  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003f18  mov     r9d, 1F0001h; dwDesiredAccess
0x180003f1e  lea     rdx, [rsp+280h+Name]; lpName
0x180003f23  xor     r8d, r8d; dwFlags
0x180003f26  xor     ecx, ecx; lpMutexAttributes
0x180003f28  call    cs:__imp_CreateMutexExW
0x180003f2e  mov     rbx, rax
0x180003f31  test    rax, rax
0x180003f34  jnz     short loc_180003F40
0x180003f36  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003f3b  jmp     loc_180004185
0x180003f40  xor     r8d, r8d; bAlertable
0x180003f43  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003f46  mov     rcx, rbx; hHandle
0x180003f49  call    cs:__imp_WaitForSingleObjectEx
0x180003f4f  cmp     eax, 102h
0x180003f54  jz      short loc_180003F66
0x180003f56  test    eax, 0FFFFFF7Fh
0x180003f5b  jnz     loc_1800041BD
0x180003f61  mov     rdi, rbx
0x180003f64  jmp     short loc_180003F68
0x180003f66  xor     edi, edi
0x180003f68  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003f6d  mov     [rsp+280h+hObject], 0
0x180003f76  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003f7b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003f80  mov     esi, eax
0x180003f82  test    eax, eax
0x180003f84  jns     short loc_180003FF0
0x180003f86  mov     rcx, [rbp+188h]; this
0x180003f8d  mov     r9d, eax; char *
0x180003f90  mov     edx, 66h ; 'f'; void *
0x180003f95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f9a  mov     rcx, [rbp+188h]; this
0x180003fa1  mov     r9d, esi; char *
0x180003fa4  mov     edx, 6Fh ; 'o'; void *
0x180003fa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fae  mov     rcx, [rbp+188h]; this
0x180003fb5  mov     r9d, esi; char *
0x180003fb8  mov     edx, 12Eh; void *
0x180003fbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fc2  test    rdi, rdi
0x180003fc5  jz      short loc_180003FD8
0x180003fc7  mov     rcx, rdi; hMutex
0x180003fca  call    cs:__imp_ReleaseMutex
0x180003fd0  test    eax, eax
0x180003fd2  jz      loc_1800041CA
0x180003fd8  mov     rcx, rbx; hObject
0x180003fdb  call    cs:__imp_CloseHandle
0x180003fe1  test    eax, eax
0x180003fe3  jz      loc_1800041DC
0x180003fe9  mov     eax, esi
0x180003feb  jmp     loc_180004185
0x180003ff0  mov     rax, [rsp+280h+hObject]
0x180003ff5  lea     rcx, ds:0[rax*4]
0x180003ffd  test    rcx, rcx
0x180004000  jz      short loc_180004010
0x180004002  mov     [r15], rcx
0x180004005  mov     eax, [rcx]
0x180004007  inc     eax
0x180004009  mov     [rcx], eax
0x18000400b  jmp     loc_18000415B
0x180004010  mov     rdx, r14; dwBytes
0x180004013  mov     qword ptr [r15], 0
0x18000401a  mov     ecx, 8; dwFlags
0x18000401f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004024  mov     rsi, rax
0x180004027  test    rax, rax
0x18000402a  jnz     short loc_18000404B
0x18000402c  mov     rcx, [rbp+188h]; this
0x180004033  mov     r14d, 8007000Eh
0x180004039  mov     r9d, r14d; char *
0x18000403c  mov     edx, 14Bh; void *
0x180004041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004046  jmp     loc_1800040D7
0x18000404b  xorps   xmm0, xmm0
0x18000404e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004054  test    sil, 3
0x180004058  jnz     loc_1800041EE
0x18000405e  mov     r9, rsi
0x180004061  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004066  shr     r9, 2; unsigned __int64
0x18000406a  lea     rcx, [rsp+280h+hObject]; this
0x18000406f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004074  mov     r14d, eax
0x180004077  test    eax, eax
0x180004079  jns     loc_180004117
0x18000407f  mov     rcx, [rbp+188h]; this
0x180004086  mov     r9d, eax; char *
0x180004089  mov     edx, 14Eh; void *
0x18000408e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004093  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004098  test    rcx, rcx
0x18000409b  jz      short loc_1800040AB
0x18000409d  call    cs:__imp_CloseHandle
0x1800040a3  test    eax, eax
0x1800040a5  jz      loc_1800041F4
0x1800040ab  mov     rcx, [rsp+280h+hObject]; hObject
0x1800040b0  test    rcx, rcx
0x1800040b3  jz      short loc_1800040C3
0x1800040b5  call    cs:__imp_CloseHandle
0x1800040bb  test    eax, eax
0x1800040bd  jz      loc_180004206
0x1800040c3  call    cs:__imp_GetProcessHeap
0x1800040c9  mov     r8, rsi; lpMem
0x1800040cc  xor     edx, edx; dwFlags
0x1800040ce  mov     rcx, rax; hHeap
0x1800040d1  call    cs:__imp_HeapFree
0x1800040d7  mov     rcx, [rbp+188h]; this
0x1800040de  mov     r9d, r14d; char *
0x1800040e1  mov     edx, 137h; void *
0x1800040e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040eb  test    rdi, rdi
0x1800040ee  jz      short loc_180004101
0x1800040f0  mov     rcx, rdi; hMutex
0x1800040f3  call    cs:__imp_ReleaseMutex
0x1800040f9  test    eax, eax
0x1800040fb  jz      loc_180004218
0x180004101  mov     rcx, rbx; hObject
0x180004104  call    cs:__imp_CloseHandle
0x18000410a  test    eax, eax
0x18000410c  jz      loc_18000422A
0x180004112  mov     eax, r14d
0x180004115  jmp     short loc_180004185
0x180004117  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000411c  xor     edx, edx; Val
0x18000411e  mov     dword ptr [rsi], 1
0x180004124  lea     rcx, [rsi+22h]; void *
0x180004128  mov     [rsi+8], rbx
0x18000412c  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004131  lea     r8d, [rdx+56h]; Size
0x180004135  call    memset_0
0x18000413a  xor     edx, edx; Val
0x18000413c  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004142  lea     rcx, [rsi+28h]; void *
0x180004146  mov     dword ptr [rsi+24h], 1
0x18000414d  lea     r8d, [rdx+50h]; Size
0x180004151  call    memset_0
0x180004156  xor     ebx, ebx
0x180004158  mov     [r15], rsi
0x18000415b  test    rdi, rdi
0x18000415e  jz      short loc_180004171
0x180004160  mov     rcx, rdi; hMutex
0x180004163  call    cs:__imp_ReleaseMutex
0x180004169  test    eax, eax
0x18000416b  jz      loc_18000423C
0x180004171  test    rbx, rbx
0x180004174  jz      short loc_180004183
0x180004176  mov     rcx, rbx; hObject
0x180004179  call    cs:__imp_CloseHandle
0x18000417f  test    eax, eax
0x180004181  jz      short loc_1800041AB
0x180004183  xor     eax, eax
0x180004185  mov     rcx, [rbp+180h+var_30]
0x18000418c  xor     rcx, rsp; StackCookie
0x18000418f  call    __security_check_cookie
0x180004194  mov     rbx, [rsp+280h+arg_10]
0x18000419c  add     rsp, 260h
0x1800041a3  pop     r15
0x1800041a5  pop     r14
0x1800041a7  pop     rdi
0x1800041a8  pop     rsi
0x1800041a9  pop     rbp
0x1800041aa  retn
0x1800041ab  mov     rcx, [rbp+188h]; this
0x1800041b2  mov     edx, 0A0Bh; void *
0x1800041b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041bd  mov     rcx, [rbp+188h]; this
0x1800041c4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800041ca  mov     rcx, [rbp+188h]; this
0x1800041d1  mov     edx, 0A15h; void *
0x1800041d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041dc  mov     rcx, [rbp+188h]; this
0x1800041e3  mov     edx, 0A0Bh; void *
0x1800041e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041ee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800041f4  mov     rcx, [rbp+188h]; this
0x1800041fb  mov     edx, 0A0Bh; void *
0x180004200  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004206  mov     rcx, [rbp+188h]; this
0x18000420d  mov     edx, 0A0Bh; void *
0x180004212  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004218  mov     rcx, [rbp+188h]; this
0x18000421f  mov     edx, 0A15h; void *
0x180004224  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000422a  mov     rcx, [rbp+188h]; this
0x180004231  mov     edx, 0A0Bh; void *
0x180004236  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000423c  mov     rcx, [rbp+188h]; this
0x180004243  mov     edx, 0A15h; void *
0x180004248  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
