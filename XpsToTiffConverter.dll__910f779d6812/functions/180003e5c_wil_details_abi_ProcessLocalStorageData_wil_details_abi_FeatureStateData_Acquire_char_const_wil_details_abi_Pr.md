# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003e5c`
- end: `0x180004223`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800044f4`

## callees

- `0x1800016a0`
- `0x1800020e4`
- `0x180002f54`
- `0x180003e5c`
- `0x18000422c`
- `0x180004684`
- `0x180004fa8`
- `0x180005b98`
- `0x1800070c4`
- `0x180007bb8`
- `0x180007f2c`
- `0x18000870c`
- `0x18000871c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ef4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ef4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004105`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004105`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000409c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004138`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000409c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004138`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ed3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ed3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000407a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000407a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000406c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000406c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004046`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000405e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000414e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004046`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000405e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000414e`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
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
0x180003e5c  mov     [rsp-8+arg_10], rbx
0x180003e61  push    rbp
0x180003e62  push    rsi
0x180003e63  push    rdi
0x180003e64  push    r14
0x180003e66  push    r15
0x180003e68  lea     rbp, [rsp-160h]
0x180003e70  sub     rsp, 260h
0x180003e77  mov     rax, cs:__security_cookie
0x180003e7e  xor     rax, rsp
0x180003e81  mov     [rbp+180h+var_30], rax
0x180003e88  mov     r15, rdx
0x180003e8b  mov     qword ptr [rdx], 0
0x180003e92  mov     rbx, rcx
0x180003e95  call    cs:__imp_GetCurrentProcessId
0x180003e9b  mov     r14d, 130h
0x180003ea1  mov     [rsp+280h+var_258], rbx
0x180003ea6  mov     r9d, eax
0x180003ea9  mov     [rsp+280h+var_260], r14d; int
0x180003eae  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003eb5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003eba  lea     edx, [r14-2Ch]; unsigned __int64
0x180003ebe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003ec3  mov     r9d, 1F0001h; dwDesiredAccess
0x180003ec9  lea     rdx, [rsp+280h+Name]; lpName
0x180003ece  xor     r8d, r8d; dwFlags
0x180003ed1  xor     ecx, ecx; lpMutexAttributes
0x180003ed3  call    cs:__imp_CreateMutexExW
0x180003ed9  mov     rbx, rax
0x180003edc  test    rax, rax
0x180003edf  jnz     short loc_180003EEB
0x180003ee1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003ee6  jmp     loc_18000415A
0x180003eeb  xor     r8d, r8d; bAlertable
0x180003eee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003ef1  mov     rcx, rbx; hHandle
0x180003ef4  call    cs:__imp_WaitForSingleObjectEx
0x180003efa  cmp     eax, 102h
0x180003eff  jz      short loc_180003F11
0x180003f01  test    eax, 0FFFFFF7Fh
0x180003f06  jnz     loc_1800041A4
0x180003f0c  mov     rdi, rbx
0x180003f0f  jmp     short loc_180003F13
0x180003f11  xor     edi, edi
0x180003f13  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003f18  mov     [rsp+280h+hObject], 0
0x180003f21  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003f26  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003f2b  mov     esi, eax
0x180003f2d  test    eax, eax
0x180003f2f  jns     short loc_180003F9B
0x180003f31  mov     rcx, [rbp+188h]; this
0x180003f38  mov     r9d, eax; char *
0x180003f3b  mov     edx, 66h ; 'f'; void *
0x180003f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f45  mov     rcx, [rbp+188h]; this
0x180003f4c  mov     r9d, esi; char *
0x180003f4f  mov     edx, 6Fh ; 'o'; void *
0x180003f54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f59  mov     rcx, [rbp+188h]; this
0x180003f60  mov     r9d, esi; char *
0x180003f63  mov     edx, 12Eh; void *
0x180003f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f6d  test    rdi, rdi
0x180003f70  jz      short loc_180003F83
0x180003f72  mov     rcx, rdi; hMutex
0x180003f75  call    cs:__imp_ReleaseMutex
0x180003f7b  test    eax, eax
0x180003f7d  jz      loc_1800041B1
0x180003f83  mov     rcx, rbx; hObject
0x180003f86  call    cs:__imp_CloseHandle
0x180003f8c  test    eax, eax
0x180003f8e  jz      loc_1800041C3
0x180003f94  mov     eax, esi
0x180003f96  jmp     loc_18000415A
0x180003f9b  mov     rax, [rsp+280h+hObject]
0x180003fa0  lea     rcx, ds:0[rax*4]
0x180003fa8  test    rcx, rcx
0x180003fab  jz      short loc_180003FBB
0x180003fad  mov     [r15], rcx
0x180003fb0  mov     eax, [rcx]
0x180003fb2  inc     eax
0x180003fb4  mov     [rcx], eax
0x180003fb6  jmp     loc_180004130
0x180003fbb  mov     rdx, r14; dwBytes
0x180003fbe  mov     qword ptr [r15], 0
0x180003fc5  mov     ecx, 8; dwFlags
0x180003fca  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003fcf  mov     r14, rax
0x180003fd2  test    rax, rax
0x180003fd5  jnz     short loc_180003FF5
0x180003fd7  mov     rcx, [rbp+188h]; this
0x180003fde  mov     esi, 8007000Eh
0x180003fe3  mov     r9d, esi; char *
0x180003fe6  mov     edx, 14Bh; void *
0x180003feb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ff0  jmp     loc_180004080
0x180003ff5  xorps   xmm0, xmm0
0x180003ff8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003ffe  test    r14b, 3
0x180004002  jnz     loc_1800041D5
0x180004008  mov     r9, r14
0x18000400b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004010  shr     r9, 2; unsigned __int64
0x180004014  lea     rcx, [rsp+280h+hObject]; this
0x180004019  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000401e  mov     esi, eax
0x180004020  test    eax, eax
0x180004022  jns     loc_1800040C0
0x180004028  mov     rcx, [rbp+188h]; this
0x18000402f  mov     r9d, eax; char *
0x180004032  mov     edx, 14Eh; void *
0x180004037  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000403c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004041  test    rcx, rcx
0x180004044  jz      short loc_180004054
0x180004046  call    cs:__imp_CloseHandle
0x18000404c  test    eax, eax
0x18000404e  jz      loc_1800041DB
0x180004054  mov     rcx, [rsp+280h+hObject]; hObject
0x180004059  test    rcx, rcx
0x18000405c  jz      short loc_18000406C
0x18000405e  call    cs:__imp_CloseHandle
0x180004064  test    eax, eax
0x180004066  jz      loc_1800041ED
0x18000406c  call    cs:__imp_GetProcessHeap
0x180004072  mov     r8, r14; lpMem
0x180004075  xor     edx, edx; dwFlags
0x180004077  mov     rcx, rax; hHeap
0x18000407a  call    cs:__imp_HeapFree
0x180004080  mov     rcx, [rbp+188h]; this
0x180004087  mov     r9d, esi; char *
0x18000408a  mov     edx, 137h; void *
0x18000408f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004094  test    rdi, rdi
0x180004097  jz      short loc_1800040AA
0x180004099  mov     rcx, rdi; hMutex
0x18000409c  call    cs:__imp_ReleaseMutex
0x1800040a2  test    eax, eax
0x1800040a4  jz      loc_1800041FF
0x1800040aa  mov     rcx, rbx; hObject
0x1800040ad  call    cs:__imp_CloseHandle
0x1800040b3  test    eax, eax
0x1800040b5  jz      loc_180004192
0x1800040bb  jmp     loc_180003F94
0x1800040c0  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800040c5  lea     rcx, [r14+28h]; void *
0x1800040c9  mov     dword ptr [r14], 1
0x1800040d0  xor     edx, edx; Val
0x1800040d2  mov     [r14+8], rbx
0x1800040d6  mov     r8d, 108h; Size
0x1800040dc  movdqu  xmmword ptr [r14+10h], xmm0
0x1800040e2  call    memset_0
0x1800040e7  xor     eax, eax
0x1800040e9  lea     rcx, [r14+28h]; this
0x1800040ed  mov     [r14+20h], rax
0x1800040f1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800040f6  lea     rbx, [r14+0E8h]
0x1800040fd  xor     r8d, r8d; Flags
0x180004100  mov     rcx, rbx; lpCriticalSection
0x180004103  xor     edx, edx; dwSpinCount
0x180004105  call    cs:__imp_InitializeCriticalSectionEx
0x18000410b  mov     qword ptr [rbx+28h], 0
0x180004113  mov     qword ptr [rbx+30h], 0
0x18000411b  mov     qword ptr [rbx+38h], 0
0x180004123  mov     qword ptr [rbx+40h], 0
0x18000412b  xor     ebx, ebx
0x18000412d  mov     [r15], r14
0x180004130  test    rdi, rdi
0x180004133  jz      short loc_180004146
0x180004135  mov     rcx, rdi; hMutex
0x180004138  call    cs:__imp_ReleaseMutex
0x18000413e  test    eax, eax
0x180004140  jz      loc_180004211
0x180004146  test    rbx, rbx
0x180004149  jz      short loc_180004158
0x18000414b  mov     rcx, rbx; hObject
0x18000414e  call    cs:__imp_CloseHandle
0x180004154  test    eax, eax
0x180004156  jz      short loc_180004180
0x180004158  xor     eax, eax
0x18000415a  mov     rcx, [rbp+180h+var_30]
0x180004161  xor     rcx, rsp; StackCookie
0x180004164  call    __security_check_cookie
0x180004169  mov     rbx, [rsp+280h+arg_10]
0x180004171  add     rsp, 260h
0x180004178  pop     r15
0x18000417a  pop     r14
0x18000417c  pop     rdi
0x18000417d  pop     rsi
0x18000417e  pop     rbp
0x18000417f  retn
0x180004180  mov     rcx, [rbp+188h]; this
0x180004187  mov     edx, 0A0Bh; void *
0x18000418c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004192  mov     rcx, [rbp+188h]; this
0x180004199  mov     edx, 0A0Bh; void *
0x18000419e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041a4  mov     rcx, [rbp+188h]; this
0x1800041ab  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800041b1  mov     rcx, [rbp+188h]; this
0x1800041b8  mov     edx, 0A15h; void *
0x1800041bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041c3  mov     rcx, [rbp+188h]; this
0x1800041ca  mov     edx, 0A0Bh; void *
0x1800041cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041d5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800041db  mov     rcx, [rbp+188h]; this
0x1800041e2  mov     edx, 0A0Bh; void *
0x1800041e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041ed  mov     rcx, [rbp+188h]; this
0x1800041f4  mov     edx, 0A0Bh; void *
0x1800041f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041ff  mov     rcx, [rbp+188h]; this
0x180004206  mov     edx, 0A15h; void *
0x18000420b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004211  mov     rcx, [rbp+188h]; this
0x180004218  mov     edx, 0A15h; void *
0x18000421d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
