# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180002eb8`
- end: `0x180003280`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180003d90`

## callees

- `0x180001570`
- `0x180001fde`
- `0x180002eb8`
- `0x180003288`
- `0x1800034d0`
- `0x180003b28`
- `0x180004608`
- `0x1800048e4`
- `0x180005270`
- `0x18000532c`
- `0x1800056ec`
- `0x1800056fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002f51`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002f51`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002f30`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180002f30`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002fe7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003125`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003195`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180002fe7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003125`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003195`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800030ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800030ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ef1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ef1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ff8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ff8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031ab`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
0x180002eb8  mov     [rsp-8+arg_10], rbx
0x180002ebd  push    rbp
0x180002ebe  push    rsi
0x180002ebf  push    rdi
0x180002ec0  push    r14
0x180002ec2  push    r15
0x180002ec4  lea     rbp, [rsp-160h]
0x180002ecc  sub     rsp, 260h
0x180002ed3  mov     rax, cs:__security_cookie
0x180002eda  xor     rax, rsp
0x180002edd  mov     [rbp+180h+var_30], rax
0x180002ee4  mov     r15, rdx
0x180002ee7  mov     qword ptr [rdx], 0
0x180002eee  mov     rbx, rcx
0x180002ef1  call    cs:__imp_GetCurrentProcessId
0x180002ef7  mov     r14d, 78h ; 'x'
0x180002efd  mov     [rsp+280h+var_258], rbx
0x180002f02  mov     r9d, eax
0x180002f05  mov     [rsp+280h+var_260], r14d; int
0x180002f0a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180002f11  mov     edx, 104h; unsigned __int64
0x180002f16  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180002f1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002f20  mov     r9d, 1F0001h; dwDesiredAccess
0x180002f26  lea     rdx, [rsp+280h+Name]; lpName
0x180002f2b  xor     r8d, r8d; dwFlags
0x180002f2e  xor     ecx, ecx; lpMutexAttributes
0x180002f30  call    cs:__imp_CreateMutexExW
0x180002f36  mov     rbx, rax
0x180002f39  test    rax, rax
0x180002f3c  jnz     short loc_180002F48
0x180002f3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180002f43  jmp     loc_1800031B7
0x180002f48  xor     r8d, r8d; bAlertable
0x180002f4b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002f4e  mov     rcx, rbx; hHandle
0x180002f51  call    cs:__imp_WaitForSingleObjectEx
0x180002f57  cmp     eax, 102h
0x180002f5c  jz      short loc_180002F6E
0x180002f5e  test    eax, 0FFFFFF7Fh
0x180002f63  jnz     loc_1800031EF
0x180002f69  mov     rdi, rbx
0x180002f6c  jmp     short loc_180002F70
0x180002f6e  xor     edi, edi
0x180002f70  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180002f75  mov     [rsp+280h+hObject], 0
0x180002f7e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180002f83  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180002f88  mov     esi, eax
0x180002f8a  test    eax, eax
0x180002f8c  jns     short loc_18000300D
0x180002f8e  mov     rcx, [rbp+188h]; this
0x180002f95  lea     r8, aWil; "wil"
0x180002f9c  mov     r9d, eax; char *
0x180002f9f  mov     edx, 66h ; 'f'; void *
0x180002fa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002fa9  mov     rcx, [rbp+188h]; this
0x180002fb0  lea     r8, aWil; "wil"
0x180002fb7  mov     r9d, esi; char *
0x180002fba  mov     edx, 6Fh ; 'o'; void *
0x180002fbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002fc4  mov     rcx, [rbp+188h]; this
0x180002fcb  lea     r8, aWil; "wil"
0x180002fd2  mov     r9d, esi; char *
0x180002fd5  mov     edx, 12Eh; void *
0x180002fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002fdf  test    rdi, rdi
0x180002fe2  jz      short loc_180002FF5
0x180002fe4  mov     rcx, rdi; hMutex
0x180002fe7  call    cs:__imp_ReleaseMutex
0x180002fed  test    eax, eax
0x180002fef  jz      loc_1800031FC
0x180002ff5  mov     rcx, rbx; hObject
0x180002ff8  call    cs:__imp_CloseHandle
0x180002ffe  test    eax, eax
0x180003000  jz      loc_18000320E
0x180003006  mov     eax, esi
0x180003008  jmp     loc_1800031B7
0x18000300d  mov     rax, [rsp+280h+hObject]
0x180003012  lea     rcx, ds:0[rax*4]
0x18000301a  test    rcx, rcx
0x18000301d  jz      short loc_18000302D
0x18000301f  mov     [r15], rcx
0x180003022  mov     eax, [rcx]
0x180003024  inc     eax
0x180003026  mov     [rcx], eax
0x180003028  jmp     loc_18000318D
0x18000302d  mov     rdx, r14; dwBytes
0x180003030  mov     qword ptr [r15], 0
0x180003037  mov     ecx, 8; dwFlags
0x18000303c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003041  mov     rsi, rax
0x180003044  test    rax, rax
0x180003047  jnz     short loc_18000306F
0x180003049  mov     rcx, [rbp+188h]; this
0x180003050  lea     r8, aWil; "wil"
0x180003057  mov     r14d, 8007000Eh
0x18000305d  mov     edx, 14Bh; void *
0x180003062  mov     r9d, r14d; char *
0x180003065  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000306a  jmp     loc_180003102
0x18000306f  xorps   xmm0, xmm0
0x180003072  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003078  test    sil, 3
0x18000307c  jnz     loc_180003220
0x180003082  mov     r9, rsi
0x180003085  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000308a  shr     r9, 2; unsigned __int64
0x18000308e  lea     rcx, [rsp+280h+hObject]; this
0x180003093  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003098  mov     r14d, eax
0x18000309b  test    eax, eax
0x18000309d  jns     loc_180003149
0x1800030a3  mov     rcx, [rbp+188h]; this
0x1800030aa  lea     r8, aWil; "wil"
0x1800030b1  mov     r9d, eax; char *
0x1800030b4  mov     edx, 14Eh; void *
0x1800030b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800030be  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800030c3  test    rcx, rcx
0x1800030c6  jz      short loc_1800030D6
0x1800030c8  call    cs:__imp_CloseHandle
0x1800030ce  test    eax, eax
0x1800030d0  jz      loc_180003226
0x1800030d6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800030db  test    rcx, rcx
0x1800030de  jz      short loc_1800030EE
0x1800030e0  call    cs:__imp_CloseHandle
0x1800030e6  test    eax, eax
0x1800030e8  jz      loc_180003238
0x1800030ee  call    cs:__imp_GetProcessHeap
0x1800030f4  mov     r8, rsi; lpMem
0x1800030f7  xor     edx, edx; dwFlags
0x1800030f9  mov     rcx, rax; hHeap
0x1800030fc  call    cs:__imp_HeapFree
0x180003102  mov     rcx, [rbp+188h]; this
0x180003109  lea     r8, aWil; "wil"
0x180003110  mov     r9d, r14d; char *
0x180003113  mov     edx, 137h; void *
0x180003118  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000311d  test    rdi, rdi
0x180003120  jz      short loc_180003133
0x180003122  mov     rcx, rdi; hMutex
0x180003125  call    cs:__imp_ReleaseMutex
0x18000312b  test    eax, eax
0x18000312d  jz      loc_18000324A
0x180003133  mov     rcx, rbx; hObject
0x180003136  call    cs:__imp_CloseHandle
0x18000313c  test    eax, eax
0x18000313e  jz      loc_18000325C
0x180003144  mov     eax, r14d
0x180003147  jmp     short loc_1800031B7
0x180003149  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000314e  xor     edx, edx; Val
0x180003150  mov     dword ptr [rsi], 1
0x180003156  lea     rcx, [rsi+22h]; void *
0x18000315a  mov     [rsi+8], rbx
0x18000315e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003163  lea     r8d, [rdx+56h]; Size
0x180003167  call    memset_0
0x18000316c  xor     edx, edx; Val
0x18000316e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003174  lea     rcx, [rsi+28h]; void *
0x180003178  mov     dword ptr [rsi+24h], 1
0x18000317f  lea     r8d, [rdx+50h]; Size
0x180003183  call    memset_0
0x180003188  xor     ebx, ebx
0x18000318a  mov     [r15], rsi
0x18000318d  test    rdi, rdi
0x180003190  jz      short loc_1800031A3
0x180003192  mov     rcx, rdi; hMutex
0x180003195  call    cs:__imp_ReleaseMutex
0x18000319b  test    eax, eax
0x18000319d  jz      loc_18000326E
0x1800031a3  test    rbx, rbx
0x1800031a6  jz      short loc_1800031B5
0x1800031a8  mov     rcx, rbx; hObject
0x1800031ab  call    cs:__imp_CloseHandle
0x1800031b1  test    eax, eax
0x1800031b3  jz      short loc_1800031DD
0x1800031b5  xor     eax, eax
0x1800031b7  mov     rcx, [rbp+180h+var_30]
0x1800031be  xor     rcx, rsp; StackCookie
0x1800031c1  call    __security_check_cookie
0x1800031c6  mov     rbx, [rsp+280h+arg_10]
0x1800031ce  add     rsp, 260h
0x1800031d5  pop     r15
0x1800031d7  pop     r14
0x1800031d9  pop     rdi
0x1800031da  pop     rsi
0x1800031db  pop     rbp
0x1800031dc  retn
0x1800031dd  mov     rcx, [rbp+188h]; this
0x1800031e4  mov     edx, 0A0Bh; void *
0x1800031e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800031ef  mov     rcx, [rbp+188h]; this
0x1800031f6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800031fc  mov     rcx, [rbp+188h]; this
0x180003203  mov     edx, 0A15h; void *
0x180003208  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000320e  mov     rcx, [rbp+188h]; this
0x180003215  mov     edx, 0A0Bh; void *
0x18000321a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003220  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003226  mov     rcx, [rbp+188h]; this
0x18000322d  mov     edx, 0A0Bh; void *
0x180003232  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003238  mov     rcx, [rbp+188h]; this
0x18000323f  mov     edx, 0A0Bh; void *
0x180003244  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000324a  mov     rcx, [rbp+188h]; this
0x180003251  mov     edx, 0A15h; void *
0x180003256  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000325c  mov     rcx, [rbp+188h]; this
0x180003263  mov     edx, 0A0Bh; void *
0x180003268  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000326e  mov     rcx, [rbp+188h]; this
0x180003275  mov     edx, 0A15h; void *
0x18000327a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
