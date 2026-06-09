# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003eac`
- end: `0x180004273`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004544`

## callees

- `0x180001670`
- `0x180002034`
- `0x180002fd8`
- `0x180003eac`
- `0x18000427c`
- `0x180004798`
- `0x180005288`
- `0x180005f68`
- `0x180007964`
- `0x180008458`
- `0x1800088bc`
- `0x18000916c`
- `0x18000917c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ee5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ee5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004188`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004188`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004155`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004155`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003f44`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003f44`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003f23`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000419e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000419e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x180003eac  mov     [rsp-8+arg_10], rbx
0x180003eb1  push    rbp
0x180003eb2  push    rsi
0x180003eb3  push    rdi
0x180003eb4  push    r14
0x180003eb6  push    r15
0x180003eb8  lea     rbp, [rsp-160h]
0x180003ec0  sub     rsp, 260h
0x180003ec7  mov     rax, cs:__security_cookie
0x180003ece  xor     rax, rsp
0x180003ed1  mov     [rbp+180h+var_30], rax
0x180003ed8  mov     r15, rdx
0x180003edb  mov     qword ptr [rdx], 0
0x180003ee2  mov     rbx, rcx
0x180003ee5  call    cs:__imp_GetCurrentProcessId
0x180003eeb  mov     r14d, 130h
0x180003ef1  mov     [rsp+280h+var_258], rbx
0x180003ef6  mov     r9d, eax
0x180003ef9  mov     [rsp+280h+var_260], r14d; int
0x180003efe  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003f05  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003f0a  lea     edx, [r14-2Ch]; unsigned __int64
0x180003f0e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003f13  mov     r9d, 1F0001h; dwDesiredAccess
0x180003f19  lea     rdx, [rsp+280h+Name]; lpName
0x180003f1e  xor     r8d, r8d; dwFlags
0x180003f21  xor     ecx, ecx; lpMutexAttributes
0x180003f23  call    cs:__imp_CreateMutexExW
0x180003f29  mov     rbx, rax
0x180003f2c  test    rax, rax
0x180003f2f  jnz     short loc_180003F3B
0x180003f31  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003f36  jmp     loc_1800041AA
0x180003f3b  xor     r8d, r8d; bAlertable
0x180003f3e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003f41  mov     rcx, rbx; hHandle
0x180003f44  call    cs:__imp_WaitForSingleObjectEx
0x180003f4a  cmp     eax, 102h
0x180003f4f  jz      short loc_180003F61
0x180003f51  test    eax, 0FFFFFF7Fh
0x180003f56  jnz     loc_1800041F4
0x180003f5c  mov     rdi, rbx
0x180003f5f  jmp     short loc_180003F63
0x180003f61  xor     edi, edi
0x180003f63  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003f68  mov     [rsp+280h+hObject], 0
0x180003f71  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003f76  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003f7b  mov     esi, eax
0x180003f7d  test    eax, eax
0x180003f7f  jns     short loc_180003FEB
0x180003f81  mov     rcx, [rbp+188h]; this
0x180003f88  mov     r9d, eax; char *
0x180003f8b  mov     edx, 66h ; 'f'; void *
0x180003f90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f95  mov     rcx, [rbp+188h]; this
0x180003f9c  mov     r9d, esi; char *
0x180003f9f  mov     edx, 6Fh ; 'o'; void *
0x180003fa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fa9  mov     rcx, [rbp+188h]; this
0x180003fb0  mov     r9d, esi; char *
0x180003fb3  mov     edx, 12Eh; void *
0x180003fb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fbd  test    rdi, rdi
0x180003fc0  jz      short loc_180003FD3
0x180003fc2  mov     rcx, rdi; hMutex
0x180003fc5  call    cs:__imp_ReleaseMutex
0x180003fcb  test    eax, eax
0x180003fcd  jz      loc_180004201
0x180003fd3  mov     rcx, rbx; hObject
0x180003fd6  call    cs:__imp_CloseHandle
0x180003fdc  test    eax, eax
0x180003fde  jz      loc_180004213
0x180003fe4  mov     eax, esi
0x180003fe6  jmp     loc_1800041AA
0x180003feb  mov     rax, [rsp+280h+hObject]
0x180003ff0  lea     rcx, ds:0[rax*4]
0x180003ff8  test    rcx, rcx
0x180003ffb  jz      short loc_18000400B
0x180003ffd  mov     [r15], rcx
0x180004000  mov     eax, [rcx]
0x180004002  inc     eax
0x180004004  mov     [rcx], eax
0x180004006  jmp     loc_180004180
0x18000400b  mov     rdx, r14; dwBytes
0x18000400e  mov     qword ptr [r15], 0
0x180004015  mov     ecx, 8; dwFlags
0x18000401a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000401f  mov     r14, rax
0x180004022  test    rax, rax
0x180004025  jnz     short loc_180004045
0x180004027  mov     rcx, [rbp+188h]; this
0x18000402e  mov     esi, 8007000Eh
0x180004033  mov     r9d, esi; char *
0x180004036  mov     edx, 14Bh; void *
0x18000403b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004040  jmp     loc_1800040D0
0x180004045  xorps   xmm0, xmm0
0x180004048  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000404e  test    r14b, 3
0x180004052  jnz     loc_180004225
0x180004058  mov     r9, r14
0x18000405b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004060  shr     r9, 2; unsigned __int64
0x180004064  lea     rcx, [rsp+280h+hObject]; this
0x180004069  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000406e  mov     esi, eax
0x180004070  test    eax, eax
0x180004072  jns     loc_180004110
0x180004078  mov     rcx, [rbp+188h]; this
0x18000407f  mov     r9d, eax; char *
0x180004082  mov     edx, 14Eh; void *
0x180004087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000408c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004091  test    rcx, rcx
0x180004094  jz      short loc_1800040A4
0x180004096  call    cs:__imp_CloseHandle
0x18000409c  test    eax, eax
0x18000409e  jz      loc_18000422B
0x1800040a4  mov     rcx, [rsp+280h+hObject]; hObject
0x1800040a9  test    rcx, rcx
0x1800040ac  jz      short loc_1800040BC
0x1800040ae  call    cs:__imp_CloseHandle
0x1800040b4  test    eax, eax
0x1800040b6  jz      loc_18000423D
0x1800040bc  call    cs:__imp_GetProcessHeap
0x1800040c2  mov     r8, r14; lpMem
0x1800040c5  xor     edx, edx; dwFlags
0x1800040c7  mov     rcx, rax; hHeap
0x1800040ca  call    cs:__imp_HeapFree
0x1800040d0  mov     rcx, [rbp+188h]; this
0x1800040d7  mov     r9d, esi; char *
0x1800040da  mov     edx, 137h; void *
0x1800040df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040e4  test    rdi, rdi
0x1800040e7  jz      short loc_1800040FA
0x1800040e9  mov     rcx, rdi; hMutex
0x1800040ec  call    cs:__imp_ReleaseMutex
0x1800040f2  test    eax, eax
0x1800040f4  jz      loc_18000424F
0x1800040fa  mov     rcx, rbx; hObject
0x1800040fd  call    cs:__imp_CloseHandle
0x180004103  test    eax, eax
0x180004105  jz      loc_1800041E2
0x18000410b  jmp     loc_180003FE4
0x180004110  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004115  lea     rcx, [r14+28h]; void *
0x180004119  mov     dword ptr [r14], 1
0x180004120  xor     edx, edx; Val
0x180004122  mov     [r14+8], rbx
0x180004126  mov     r8d, 108h; Size
0x18000412c  movdqu  xmmword ptr [r14+10h], xmm0
0x180004132  call    memset_0
0x180004137  xor     eax, eax
0x180004139  lea     rcx, [r14+28h]; this
0x18000413d  mov     [r14+20h], rax
0x180004141  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004146  lea     rbx, [r14+0E8h]
0x18000414d  xor     r8d, r8d; Flags
0x180004150  mov     rcx, rbx; lpCriticalSection
0x180004153  xor     edx, edx; dwSpinCount
0x180004155  call    cs:__imp_InitializeCriticalSectionEx
0x18000415b  mov     qword ptr [rbx+28h], 0
0x180004163  mov     qword ptr [rbx+30h], 0
0x18000416b  mov     qword ptr [rbx+38h], 0
0x180004173  mov     qword ptr [rbx+40h], 0
0x18000417b  xor     ebx, ebx
0x18000417d  mov     [r15], r14
0x180004180  test    rdi, rdi
0x180004183  jz      short loc_180004196
0x180004185  mov     rcx, rdi; hMutex
0x180004188  call    cs:__imp_ReleaseMutex
0x18000418e  test    eax, eax
0x180004190  jz      loc_180004261
0x180004196  test    rbx, rbx
0x180004199  jz      short loc_1800041A8
0x18000419b  mov     rcx, rbx; hObject
0x18000419e  call    cs:__imp_CloseHandle
0x1800041a4  test    eax, eax
0x1800041a6  jz      short loc_1800041D0
0x1800041a8  xor     eax, eax
0x1800041aa  mov     rcx, [rbp+180h+var_30]
0x1800041b1  xor     rcx, rsp; StackCookie
0x1800041b4  call    __security_check_cookie
0x1800041b9  mov     rbx, [rsp+280h+arg_10]
0x1800041c1  add     rsp, 260h
0x1800041c8  pop     r15
0x1800041ca  pop     r14
0x1800041cc  pop     rdi
0x1800041cd  pop     rsi
0x1800041ce  pop     rbp
0x1800041cf  retn
0x1800041d0  mov     rcx, [rbp+188h]; this
0x1800041d7  mov     edx, 0A0Bh; void *
0x1800041dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041e2  mov     rcx, [rbp+188h]; this
0x1800041e9  mov     edx, 0A0Bh; void *
0x1800041ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041f4  mov     rcx, [rbp+188h]; this
0x1800041fb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004201  mov     rcx, [rbp+188h]; this
0x180004208  mov     edx, 0A15h; void *
0x18000420d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004213  mov     rcx, [rbp+188h]; this
0x18000421a  mov     edx, 0A0Bh; void *
0x18000421f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004225  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000422b  mov     rcx, [rbp+188h]; this
0x180004232  mov     edx, 0A0Bh; void *
0x180004237  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000423d  mov     rcx, [rbp+188h]; this
0x180004244  mov     edx, 0A0Bh; void *
0x180004249  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000424f  mov     rcx, [rbp+188h]; this
0x180004256  mov     edx, 0A15h; void *
0x18000425b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004261  mov     rcx, [rbp+188h]; this
0x180004268  mov     edx, 0A15h; void *
0x18000426d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
