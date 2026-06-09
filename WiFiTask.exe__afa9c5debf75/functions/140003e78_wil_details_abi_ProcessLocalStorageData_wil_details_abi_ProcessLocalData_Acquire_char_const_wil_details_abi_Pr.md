# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003e78`
- end: `0x140004216`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140006930`

## callees

- `0x1400016a0`
- `0x140002168`
- `0x140003e78`
- `0x140004600`
- `0x140004b80`
- `0x140006560`
- `0x140007d2c`
- `0x1400098a4`
- `0x14000a800`
- `0x14000ac6c`
- `0x14000b51c`
- `0x14000b52c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003ef0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003ef0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003f11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003f11`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003f92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400040bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000412b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003f92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400040bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000412b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004099`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004099`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000408b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000408b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003eb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004065`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000407d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400040cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004065`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000407d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400040cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004141`

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
0x140003e78  mov     [rsp-8+arg_10], rbx
0x140003e7d  push    rbp
0x140003e7e  push    rsi
0x140003e7f  push    rdi
0x140003e80  push    r14
0x140003e82  push    r15
0x140003e84  lea     rbp, [rsp-160h]
0x140003e8c  sub     rsp, 260h
0x140003e93  mov     rax, cs:__security_cookie
0x140003e9a  xor     rax, rsp
0x140003e9d  mov     [rbp+180h+var_30], rax
0x140003ea4  mov     r15, rdx
0x140003ea7  mov     qword ptr [rdx], 0
0x140003eae  mov     rbx, rcx
0x140003eb1  call    cs:__imp_GetCurrentProcessId
0x140003eb7  mov     r14d, 78h ; 'x'
0x140003ebd  mov     [rsp+280h+var_258], rbx
0x140003ec2  mov     r9d, eax
0x140003ec5  mov     [rsp+280h+var_260], r14d; int
0x140003eca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003ed1  mov     edx, 104h; unsigned __int64
0x140003ed6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003edb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003ee0  mov     r9d, 1F0001h; dwDesiredAccess
0x140003ee6  lea     rdx, [rsp+280h+Name]; lpName
0x140003eeb  xor     r8d, r8d; dwFlags
0x140003eee  xor     ecx, ecx; lpMutexAttributes
0x140003ef0  call    cs:__imp_CreateMutexExW
0x140003ef6  mov     rbx, rax
0x140003ef9  test    rax, rax
0x140003efc  jnz     short loc_140003F08
0x140003efe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003f03  jmp     loc_14000414D
0x140003f08  xor     r8d, r8d; bAlertable
0x140003f0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003f0e  mov     rcx, rbx; hHandle
0x140003f11  call    cs:__imp_WaitForSingleObjectEx
0x140003f17  cmp     eax, 102h
0x140003f1c  jz      short loc_140003F2E
0x140003f1e  test    eax, 0FFFFFF7Fh
0x140003f23  jnz     loc_140004185
0x140003f29  mov     rdi, rbx
0x140003f2c  jmp     short loc_140003F30
0x140003f2e  xor     edi, edi
0x140003f30  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003f35  mov     [rsp+280h+hObject], 0
0x140003f3e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003f43  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003f48  mov     esi, eax
0x140003f4a  test    eax, eax
0x140003f4c  jns     short loc_140003FB8
0x140003f4e  mov     rcx, [rbp+188h]; this
0x140003f55  mov     r9d, eax; char *
0x140003f58  mov     edx, 66h ; 'f'; void *
0x140003f5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f62  mov     rcx, [rbp+188h]; this
0x140003f69  mov     r9d, esi; char *
0x140003f6c  mov     edx, 6Fh ; 'o'; void *
0x140003f71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f76  mov     rcx, [rbp+188h]; this
0x140003f7d  mov     r9d, esi; char *
0x140003f80  mov     edx, 12Eh; void *
0x140003f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003f8a  test    rdi, rdi
0x140003f8d  jz      short loc_140003FA0
0x140003f8f  mov     rcx, rdi; hMutex
0x140003f92  call    cs:__imp_ReleaseMutex
0x140003f98  test    eax, eax
0x140003f9a  jz      loc_140004192
0x140003fa0  mov     rcx, rbx; hObject
0x140003fa3  call    cs:__imp_CloseHandle
0x140003fa9  test    eax, eax
0x140003fab  jz      loc_1400041A4
0x140003fb1  mov     eax, esi
0x140003fb3  jmp     loc_14000414D
0x140003fb8  mov     rax, [rsp+280h+hObject]
0x140003fbd  lea     rcx, ds:0[rax*4]
0x140003fc5  test    rcx, rcx
0x140003fc8  jz      short loc_140003FD8
0x140003fca  mov     [r15], rcx
0x140003fcd  mov     eax, [rcx]
0x140003fcf  inc     eax
0x140003fd1  mov     [rcx], eax
0x140003fd3  jmp     loc_140004123
0x140003fd8  mov     rdx, r14; dwBytes
0x140003fdb  mov     qword ptr [r15], 0
0x140003fe2  mov     ecx, 8; dwFlags
0x140003fe7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003fec  mov     rsi, rax
0x140003fef  test    rax, rax
0x140003ff2  jnz     short loc_140004013
0x140003ff4  mov     rcx, [rbp+188h]; this
0x140003ffb  mov     r14d, 8007000Eh
0x140004001  mov     r9d, r14d; char *
0x140004004  mov     edx, 14Bh; void *
0x140004009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000400e  jmp     loc_14000409F
0x140004013  xorps   xmm0, xmm0
0x140004016  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000401c  test    sil, 3
0x140004020  jnz     loc_1400041B6
0x140004026  mov     r9, rsi
0x140004029  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000402e  shr     r9, 2; unsigned __int64
0x140004032  lea     rcx, [rsp+280h+hObject]; this
0x140004037  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000403c  mov     r14d, eax
0x14000403f  test    eax, eax
0x140004041  jns     loc_1400040DF
0x140004047  mov     rcx, [rbp+188h]; this
0x14000404e  mov     r9d, eax; char *
0x140004051  mov     edx, 14Eh; void *
0x140004056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000405b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140004060  test    rcx, rcx
0x140004063  jz      short loc_140004073
0x140004065  call    cs:__imp_CloseHandle
0x14000406b  test    eax, eax
0x14000406d  jz      loc_1400041BC
0x140004073  mov     rcx, [rsp+280h+hObject]; hObject
0x140004078  test    rcx, rcx
0x14000407b  jz      short loc_14000408B
0x14000407d  call    cs:__imp_CloseHandle
0x140004083  test    eax, eax
0x140004085  jz      loc_1400041CE
0x14000408b  call    cs:__imp_GetProcessHeap
0x140004091  mov     r8, rsi; lpMem
0x140004094  xor     edx, edx; dwFlags
0x140004096  mov     rcx, rax; hHeap
0x140004099  call    cs:__imp_HeapFree
0x14000409f  mov     rcx, [rbp+188h]; this
0x1400040a6  mov     r9d, r14d; char *
0x1400040a9  mov     edx, 137h; void *
0x1400040ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400040b3  test    rdi, rdi
0x1400040b6  jz      short loc_1400040C9
0x1400040b8  mov     rcx, rdi; hMutex
0x1400040bb  call    cs:__imp_ReleaseMutex
0x1400040c1  test    eax, eax
0x1400040c3  jz      loc_1400041E0
0x1400040c9  mov     rcx, rbx; hObject
0x1400040cc  call    cs:__imp_CloseHandle
0x1400040d2  test    eax, eax
0x1400040d4  jz      loc_1400041F2
0x1400040da  mov     eax, r14d
0x1400040dd  jmp     short loc_14000414D
0x1400040df  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400040e4  xor     edx, edx; Val
0x1400040e6  mov     dword ptr [rsi], 1
0x1400040ec  lea     rcx, [rsi+22h]; void *
0x1400040f0  mov     [rsi+8], rbx
0x1400040f4  movdqu  xmmword ptr [rsi+10h], xmm0
0x1400040f9  lea     r8d, [rdx+56h]; Size
0x1400040fd  call    memset_0
0x140004102  xor     edx, edx; Val
0x140004104  mov     word ptr [rsi+20h], 58h ; 'X'
0x14000410a  lea     rcx, [rsi+28h]; void *
0x14000410e  mov     dword ptr [rsi+24h], 1
0x140004115  lea     r8d, [rdx+50h]; Size
0x140004119  call    memset_0
0x14000411e  xor     ebx, ebx
0x140004120  mov     [r15], rsi
0x140004123  test    rdi, rdi
0x140004126  jz      short loc_140004139
0x140004128  mov     rcx, rdi; hMutex
0x14000412b  call    cs:__imp_ReleaseMutex
0x140004131  test    eax, eax
0x140004133  jz      loc_140004204
0x140004139  test    rbx, rbx
0x14000413c  jz      short loc_14000414B
0x14000413e  mov     rcx, rbx; hObject
0x140004141  call    cs:__imp_CloseHandle
0x140004147  test    eax, eax
0x140004149  jz      short loc_140004173
0x14000414b  xor     eax, eax
0x14000414d  mov     rcx, [rbp+180h+var_30]
0x140004154  xor     rcx, rsp; StackCookie
0x140004157  call    __security_check_cookie
0x14000415c  mov     rbx, [rsp+280h+arg_10]
0x140004164  add     rsp, 260h
0x14000416b  pop     r15
0x14000416d  pop     r14
0x14000416f  pop     rdi
0x140004170  pop     rsi
0x140004171  pop     rbp
0x140004172  retn
0x140004173  mov     rcx, [rbp+188h]; this
0x14000417a  mov     edx, 0A0Bh; void *
0x14000417f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004185  mov     rcx, [rbp+188h]; this
0x14000418c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004192  mov     rcx, [rbp+188h]; this
0x140004199  mov     edx, 0A15h; void *
0x14000419e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400041a4  mov     rcx, [rbp+188h]; this
0x1400041ab  mov     edx, 0A0Bh; void *
0x1400041b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400041b6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400041bc  mov     rcx, [rbp+188h]; this
0x1400041c3  mov     edx, 0A0Bh; void *
0x1400041c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400041ce  mov     rcx, [rbp+188h]; this
0x1400041d5  mov     edx, 0A0Bh; void *
0x1400041da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400041e0  mov     rcx, [rbp+188h]; this
0x1400041e7  mov     edx, 0A15h; void *
0x1400041ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400041f2  mov     rcx, [rbp+188h]; this
0x1400041f9  mov     edx, 0A0Bh; void *
0x1400041fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004204  mov     rcx, [rbp+188h]; this
0x14000420b  mov     edx, 0A15h; void *
0x140004210  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
