# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180002f08`
- end: `0x1800032d0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180003dd0`

## callees

- `0x180001560`
- `0x180001ef2`
- `0x180002f08`
- `0x1800032d8`
- `0x180003520`
- `0x180003b68`
- `0x180004648`
- `0x180004924`
- `0x1800052b0`
- `0x18000536c`
- `0x18000572c`
- `0x18000573c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002f80`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002f80`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003037`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003175`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800031e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003037`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003175`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800031e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002fa1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002fa1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000314c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000314c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000313e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000313e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003048`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003130`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003048`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003130`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031fb`

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
0x180002f08  mov     [rsp-8+arg_10], rbx
0x180002f0d  push    rbp
0x180002f0e  push    rsi
0x180002f0f  push    rdi
0x180002f10  push    r14
0x180002f12  push    r15
0x180002f14  lea     rbp, [rsp-160h]
0x180002f1c  sub     rsp, 260h
0x180002f23  mov     rax, cs:__security_cookie
0x180002f2a  xor     rax, rsp
0x180002f2d  mov     [rbp+180h+var_30], rax
0x180002f34  mov     r15, rdx
0x180002f37  mov     qword ptr [rdx], 0
0x180002f3e  mov     rbx, rcx
0x180002f41  call    cs:__imp_GetCurrentProcessId
0x180002f47  mov     r14d, 78h ; 'x'
0x180002f4d  mov     [rsp+280h+var_258], rbx
0x180002f52  mov     r9d, eax
0x180002f55  mov     [rsp+280h+var_260], r14d; int
0x180002f5a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180002f61  mov     edx, 104h; unsigned __int64
0x180002f66  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180002f6b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002f70  mov     r9d, 1F0001h; dwDesiredAccess
0x180002f76  lea     rdx, [rsp+280h+Name]; lpName
0x180002f7b  xor     r8d, r8d; dwFlags
0x180002f7e  xor     ecx, ecx; lpMutexAttributes
0x180002f80  call    cs:__imp_CreateMutexExW
0x180002f86  mov     rbx, rax
0x180002f89  test    rax, rax
0x180002f8c  jnz     short loc_180002F98
0x180002f8e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180002f93  jmp     loc_180003207
0x180002f98  xor     r8d, r8d; bAlertable
0x180002f9b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002f9e  mov     rcx, rbx; hHandle
0x180002fa1  call    cs:__imp_WaitForSingleObjectEx
0x180002fa7  cmp     eax, 102h
0x180002fac  jz      short loc_180002FBE
0x180002fae  test    eax, 0FFFFFF7Fh
0x180002fb3  jnz     loc_18000323F
0x180002fb9  mov     rdi, rbx
0x180002fbc  jmp     short loc_180002FC0
0x180002fbe  xor     edi, edi
0x180002fc0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180002fc5  mov     [rsp+280h+hObject], 0
0x180002fce  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180002fd3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180002fd8  mov     esi, eax
0x180002fda  test    eax, eax
0x180002fdc  jns     short loc_18000305D
0x180002fde  mov     rcx, [rbp+188h]; this
0x180002fe5  lea     r8, aWil; "wil"
0x180002fec  mov     r9d, eax; char *
0x180002fef  mov     edx, 66h ; 'f'; void *
0x180002ff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002ff9  mov     rcx, [rbp+188h]; this
0x180003000  lea     r8, aWil; "wil"
0x180003007  mov     r9d, esi; char *
0x18000300a  mov     edx, 6Fh ; 'o'; void *
0x18000300f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003014  mov     rcx, [rbp+188h]; this
0x18000301b  lea     r8, aWil; "wil"
0x180003022  mov     r9d, esi; char *
0x180003025  mov     edx, 12Eh; void *
0x18000302a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000302f  test    rdi, rdi
0x180003032  jz      short loc_180003045
0x180003034  mov     rcx, rdi; hMutex
0x180003037  call    cs:__imp_ReleaseMutex
0x18000303d  test    eax, eax
0x18000303f  jz      loc_18000324C
0x180003045  mov     rcx, rbx; hObject
0x180003048  call    cs:__imp_CloseHandle
0x18000304e  test    eax, eax
0x180003050  jz      loc_18000325E
0x180003056  mov     eax, esi
0x180003058  jmp     loc_180003207
0x18000305d  mov     rax, [rsp+280h+hObject]
0x180003062  lea     rcx, ds:0[rax*4]
0x18000306a  test    rcx, rcx
0x18000306d  jz      short loc_18000307D
0x18000306f  mov     [r15], rcx
0x180003072  mov     eax, [rcx]
0x180003074  inc     eax
0x180003076  mov     [rcx], eax
0x180003078  jmp     loc_1800031DD
0x18000307d  mov     rdx, r14; dwBytes
0x180003080  mov     qword ptr [r15], 0
0x180003087  mov     ecx, 8; dwFlags
0x18000308c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003091  mov     rsi, rax
0x180003094  test    rax, rax
0x180003097  jnz     short loc_1800030BF
0x180003099  mov     rcx, [rbp+188h]; this
0x1800030a0  lea     r8, aWil; "wil"
0x1800030a7  mov     r14d, 8007000Eh
0x1800030ad  mov     edx, 14Bh; void *
0x1800030b2  mov     r9d, r14d; char *
0x1800030b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800030ba  jmp     loc_180003152
0x1800030bf  xorps   xmm0, xmm0
0x1800030c2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800030c8  test    sil, 3
0x1800030cc  jnz     loc_180003270
0x1800030d2  mov     r9, rsi
0x1800030d5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800030da  shr     r9, 2; unsigned __int64
0x1800030de  lea     rcx, [rsp+280h+hObject]; this
0x1800030e3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800030e8  mov     r14d, eax
0x1800030eb  test    eax, eax
0x1800030ed  jns     loc_180003199
0x1800030f3  mov     rcx, [rbp+188h]; this
0x1800030fa  lea     r8, aWil; "wil"
0x180003101  mov     r9d, eax; char *
0x180003104  mov     edx, 14Eh; void *
0x180003109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000310e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003113  test    rcx, rcx
0x180003116  jz      short loc_180003126
0x180003118  call    cs:__imp_CloseHandle
0x18000311e  test    eax, eax
0x180003120  jz      loc_180003276
0x180003126  mov     rcx, [rsp+280h+hObject]; hObject
0x18000312b  test    rcx, rcx
0x18000312e  jz      short loc_18000313E
0x180003130  call    cs:__imp_CloseHandle
0x180003136  test    eax, eax
0x180003138  jz      loc_180003288
0x18000313e  call    cs:__imp_GetProcessHeap
0x180003144  mov     r8, rsi; lpMem
0x180003147  xor     edx, edx; dwFlags
0x180003149  mov     rcx, rax; hHeap
0x18000314c  call    cs:__imp_HeapFree
0x180003152  mov     rcx, [rbp+188h]; this
0x180003159  lea     r8, aWil; "wil"
0x180003160  mov     r9d, r14d; char *
0x180003163  mov     edx, 137h; void *
0x180003168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000316d  test    rdi, rdi
0x180003170  jz      short loc_180003183
0x180003172  mov     rcx, rdi; hMutex
0x180003175  call    cs:__imp_ReleaseMutex
0x18000317b  test    eax, eax
0x18000317d  jz      loc_18000329A
0x180003183  mov     rcx, rbx; hObject
0x180003186  call    cs:__imp_CloseHandle
0x18000318c  test    eax, eax
0x18000318e  jz      loc_1800032AC
0x180003194  mov     eax, r14d
0x180003197  jmp     short loc_180003207
0x180003199  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000319e  xor     edx, edx; Val
0x1800031a0  mov     dword ptr [rsi], 1
0x1800031a6  lea     rcx, [rsi+22h]; void *
0x1800031aa  mov     [rsi+8], rbx
0x1800031ae  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800031b3  lea     r8d, [rdx+56h]; Size
0x1800031b7  call    memset_0
0x1800031bc  xor     edx, edx; Val
0x1800031be  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800031c4  lea     rcx, [rsi+28h]; void *
0x1800031c8  mov     dword ptr [rsi+24h], 1
0x1800031cf  lea     r8d, [rdx+50h]; Size
0x1800031d3  call    memset_0
0x1800031d8  xor     ebx, ebx
0x1800031da  mov     [r15], rsi
0x1800031dd  test    rdi, rdi
0x1800031e0  jz      short loc_1800031F3
0x1800031e2  mov     rcx, rdi; hMutex
0x1800031e5  call    cs:__imp_ReleaseMutex
0x1800031eb  test    eax, eax
0x1800031ed  jz      loc_1800032BE
0x1800031f3  test    rbx, rbx
0x1800031f6  jz      short loc_180003205
0x1800031f8  mov     rcx, rbx; hObject
0x1800031fb  call    cs:__imp_CloseHandle
0x180003201  test    eax, eax
0x180003203  jz      short loc_18000322D
0x180003205  xor     eax, eax
0x180003207  mov     rcx, [rbp+180h+var_30]
0x18000320e  xor     rcx, rsp; StackCookie
0x180003211  call    __security_check_cookie
0x180003216  mov     rbx, [rsp+280h+arg_10]
0x18000321e  add     rsp, 260h
0x180003225  pop     r15
0x180003227  pop     r14
0x180003229  pop     rdi
0x18000322a  pop     rsi
0x18000322b  pop     rbp
0x18000322c  retn
0x18000322d  mov     rcx, [rbp+188h]; this
0x180003234  mov     edx, 0A0Bh; void *
0x180003239  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000323f  mov     rcx, [rbp+188h]; this
0x180003246  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000324c  mov     rcx, [rbp+188h]; this
0x180003253  mov     edx, 0A15h; void *
0x180003258  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000325e  mov     rcx, [rbp+188h]; this
0x180003265  mov     edx, 0A0Bh; void *
0x18000326a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003270  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003276  mov     rcx, [rbp+188h]; this
0x18000327d  mov     edx, 0A0Bh; void *
0x180003282  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003288  mov     rcx, [rbp+188h]; this
0x18000328f  mov     edx, 0A0Bh; void *
0x180003294  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000329a  mov     rcx, [rbp+188h]; this
0x1800032a1  mov     edx, 0A15h; void *
0x1800032a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800032ac  mov     rcx, [rbp+188h]; this
0x1800032b3  mov     edx, 0A0Bh; void *
0x1800032b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800032be  mov     rcx, [rbp+188h]; this
0x1800032c5  mov     edx, 0A15h; void *
0x1800032ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
