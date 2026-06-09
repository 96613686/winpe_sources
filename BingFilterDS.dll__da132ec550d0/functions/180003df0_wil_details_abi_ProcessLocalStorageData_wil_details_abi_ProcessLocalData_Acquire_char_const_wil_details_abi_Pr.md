# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003df0`
- end: `0x1800041b8`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004f74`

## callees

- `0x180003df0`
- `0x18000421c`
- `0x180004534`
- `0x180004cd8`
- `0x1800059dc`
- `0x180006264`
- `0x180006a30`
- `0x180006c2c`
- `0x1800070e4`
- `0x1800070f4`
- `0x18000c4f2`
- `0x18000c530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000405d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000405d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040cd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003e68`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003e68`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003e89`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003e89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004026`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004026`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004034`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004034`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000406e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000406e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040e3`

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
0x180003df0  mov     [rsp-8+arg_10], rbx
0x180003df5  push    rbp
0x180003df6  push    rsi
0x180003df7  push    rdi
0x180003df8  push    r14
0x180003dfa  push    r15
0x180003dfc  lea     rbp, [rsp-160h]
0x180003e04  sub     rsp, 260h
0x180003e0b  mov     rax, cs:__security_cookie
0x180003e12  xor     rax, rsp
0x180003e15  mov     [rbp+180h+var_30], rax
0x180003e1c  mov     r15, rdx
0x180003e1f  mov     qword ptr [rdx], 0
0x180003e26  mov     rbx, rcx
0x180003e29  call    cs:__imp_GetCurrentProcessId
0x180003e2f  mov     r14d, 78h ; 'x'
0x180003e35  mov     [rsp+280h+var_258], rbx
0x180003e3a  mov     r9d, eax
0x180003e3d  mov     [rsp+280h+var_260], r14d; int
0x180003e42  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003e49  mov     edx, 104h; unsigned __int64
0x180003e4e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003e53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003e58  mov     r9d, 1F0001h; dwDesiredAccess
0x180003e5e  lea     rdx, [rsp+280h+Name]; lpName
0x180003e63  xor     r8d, r8d; dwFlags
0x180003e66  xor     ecx, ecx; lpMutexAttributes
0x180003e68  call    cs:__imp_CreateMutexExW
0x180003e6e  mov     rbx, rax
0x180003e71  test    rax, rax
0x180003e74  jnz     short loc_180003E80
0x180003e76  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003e7b  jmp     loc_1800040EF
0x180003e80  xor     r8d, r8d; bAlertable
0x180003e83  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003e86  mov     rcx, rbx; hHandle
0x180003e89  call    cs:__imp_WaitForSingleObjectEx
0x180003e8f  cmp     eax, 102h
0x180003e94  jz      short loc_180003EA6
0x180003e96  test    eax, 0FFFFFF7Fh
0x180003e9b  jnz     loc_180004127
0x180003ea1  mov     rdi, rbx
0x180003ea4  jmp     short loc_180003EA8
0x180003ea6  xor     edi, edi
0x180003ea8  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003ead  mov     [rsp+280h+hObject], 0
0x180003eb6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003ebb  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003ec0  mov     esi, eax
0x180003ec2  test    eax, eax
0x180003ec4  jns     short loc_180003F45
0x180003ec6  mov     rcx, [rbp+188h]; this
0x180003ecd  lea     r8, aWil; "wil"
0x180003ed4  mov     r9d, eax; char *
0x180003ed7  mov     edx, 66h ; 'f'; void *
0x180003edc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ee1  mov     rcx, [rbp+188h]; this
0x180003ee8  lea     r8, aWil; "wil"
0x180003eef  mov     r9d, esi; char *
0x180003ef2  mov     edx, 6Fh ; 'o'; void *
0x180003ef7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003efc  mov     rcx, [rbp+188h]; this
0x180003f03  lea     r8, aWil; "wil"
0x180003f0a  mov     r9d, esi; char *
0x180003f0d  mov     edx, 12Eh; void *
0x180003f12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f17  test    rdi, rdi
0x180003f1a  jz      short loc_180003F2D
0x180003f1c  mov     rcx, rdi; hMutex
0x180003f1f  call    cs:__imp_ReleaseMutex
0x180003f25  test    eax, eax
0x180003f27  jz      loc_180004134
0x180003f2d  mov     rcx, rbx; hObject
0x180003f30  call    cs:__imp_CloseHandle
0x180003f36  test    eax, eax
0x180003f38  jz      loc_180004146
0x180003f3e  mov     eax, esi
0x180003f40  jmp     loc_1800040EF
0x180003f45  mov     rax, [rsp+280h+hObject]
0x180003f4a  lea     rcx, ds:0[rax*4]
0x180003f52  test    rcx, rcx
0x180003f55  jz      short loc_180003F65
0x180003f57  mov     [r15], rcx
0x180003f5a  mov     eax, [rcx]
0x180003f5c  inc     eax
0x180003f5e  mov     [rcx], eax
0x180003f60  jmp     loc_1800040C5
0x180003f65  mov     rdx, r14; dwBytes
0x180003f68  mov     qword ptr [r15], 0
0x180003f6f  mov     ecx, 8; dwFlags
0x180003f74  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003f79  mov     rsi, rax
0x180003f7c  test    rax, rax
0x180003f7f  jnz     short loc_180003FA7
0x180003f81  mov     rcx, [rbp+188h]; this
0x180003f88  lea     r8, aWil; "wil"
0x180003f8f  mov     r14d, 8007000Eh
0x180003f95  mov     edx, 14Bh; void *
0x180003f9a  mov     r9d, r14d; char *
0x180003f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fa2  jmp     loc_18000403A
0x180003fa7  xorps   xmm0, xmm0
0x180003faa  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003fb0  test    sil, 3
0x180003fb4  jnz     loc_180004158
0x180003fba  mov     r9, rsi
0x180003fbd  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003fc2  shr     r9, 2; unsigned __int64
0x180003fc6  lea     rcx, [rsp+280h+hObject]; this
0x180003fcb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003fd0  mov     r14d, eax
0x180003fd3  test    eax, eax
0x180003fd5  jns     loc_180004081
0x180003fdb  mov     rcx, [rbp+188h]; this
0x180003fe2  lea     r8, aWil; "wil"
0x180003fe9  mov     r9d, eax; char *
0x180003fec  mov     edx, 14Eh; void *
0x180003ff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ff6  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003ffb  test    rcx, rcx
0x180003ffe  jz      short loc_18000400E
0x180004000  call    cs:__imp_CloseHandle
0x180004006  test    eax, eax
0x180004008  jz      loc_18000415E
0x18000400e  mov     rcx, [rsp+280h+hObject]; hObject
0x180004013  test    rcx, rcx
0x180004016  jz      short loc_180004026
0x180004018  call    cs:__imp_CloseHandle
0x18000401e  test    eax, eax
0x180004020  jz      loc_180004170
0x180004026  call    cs:__imp_GetProcessHeap
0x18000402c  mov     r8, rsi; lpMem
0x18000402f  xor     edx, edx; dwFlags
0x180004031  mov     rcx, rax; hHeap
0x180004034  call    cs:__imp_HeapFree
0x18000403a  mov     rcx, [rbp+188h]; this
0x180004041  lea     r8, aWil; "wil"
0x180004048  mov     r9d, r14d; char *
0x18000404b  mov     edx, 137h; void *
0x180004050  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004055  test    rdi, rdi
0x180004058  jz      short loc_18000406B
0x18000405a  mov     rcx, rdi; hMutex
0x18000405d  call    cs:__imp_ReleaseMutex
0x180004063  test    eax, eax
0x180004065  jz      loc_180004182
0x18000406b  mov     rcx, rbx; hObject
0x18000406e  call    cs:__imp_CloseHandle
0x180004074  test    eax, eax
0x180004076  jz      loc_180004194
0x18000407c  mov     eax, r14d
0x18000407f  jmp     short loc_1800040EF
0x180004081  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004086  xor     edx, edx; Val
0x180004088  mov     dword ptr [rsi], 1
0x18000408e  lea     rcx, [rsi+22h]; void *
0x180004092  mov     [rsi+8], rbx
0x180004096  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000409b  lea     r8d, [rdx+56h]; Size
0x18000409f  call    memset_0
0x1800040a4  xor     edx, edx; Val
0x1800040a6  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800040ac  lea     rcx, [rsi+28h]; void *
0x1800040b0  mov     dword ptr [rsi+24h], 1
0x1800040b7  lea     r8d, [rdx+50h]; Size
0x1800040bb  call    memset_0
0x1800040c0  xor     ebx, ebx
0x1800040c2  mov     [r15], rsi
0x1800040c5  test    rdi, rdi
0x1800040c8  jz      short loc_1800040DB
0x1800040ca  mov     rcx, rdi; hMutex
0x1800040cd  call    cs:__imp_ReleaseMutex
0x1800040d3  test    eax, eax
0x1800040d5  jz      loc_1800041A6
0x1800040db  test    rbx, rbx
0x1800040de  jz      short loc_1800040ED
0x1800040e0  mov     rcx, rbx; hObject
0x1800040e3  call    cs:__imp_CloseHandle
0x1800040e9  test    eax, eax
0x1800040eb  jz      short loc_180004115
0x1800040ed  xor     eax, eax
0x1800040ef  mov     rcx, [rbp+180h+var_30]
0x1800040f6  xor     rcx, rsp; StackCookie
0x1800040f9  call    __security_check_cookie
0x1800040fe  mov     rbx, [rsp+280h+arg_10]
0x180004106  add     rsp, 260h
0x18000410d  pop     r15
0x18000410f  pop     r14
0x180004111  pop     rdi
0x180004112  pop     rsi
0x180004113  pop     rbp
0x180004114  retn
0x180004115  mov     rcx, [rbp+188h]; this
0x18000411c  mov     edx, 0A0Bh; void *
0x180004121  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004127  mov     rcx, [rbp+188h]; this
0x18000412e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004134  mov     rcx, [rbp+188h]; this
0x18000413b  mov     edx, 0A15h; void *
0x180004140  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004146  mov     rcx, [rbp+188h]; this
0x18000414d  mov     edx, 0A0Bh; void *
0x180004152  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004158  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000415e  mov     rcx, [rbp+188h]; this
0x180004165  mov     edx, 0A0Bh; void *
0x18000416a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004170  mov     rcx, [rbp+188h]; this
0x180004177  mov     edx, 0A0Bh; void *
0x18000417c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004182  mov     rcx, [rbp+188h]; this
0x180004189  mov     edx, 0A15h; void *
0x18000418e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004194  mov     rcx, [rbp+188h]; this
0x18000419b  mov     edx, 0A0Bh; void *
0x1800041a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041a6  mov     rcx, [rbp+188h]; this
0x1800041ad  mov     edx, 0A15h; void *
0x1800041b2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
