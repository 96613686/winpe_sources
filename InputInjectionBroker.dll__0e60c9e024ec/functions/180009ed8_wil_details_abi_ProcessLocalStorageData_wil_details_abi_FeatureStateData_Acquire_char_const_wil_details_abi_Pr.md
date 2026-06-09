# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009ed8`
- end: `0x18000a2c9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000a498`

## callees

- `0x180003470`
- `0x180003754`
- `0x180003cf8`
- `0x1800047d8`
- `0x180004a34`
- `0x180005264`
- `0x18000531c`
- `0x1800057d4`
- `0x1800057e4`
- `0x18000971c`
- `0x180009ed8`
- `0x18001143a`
- `0x180011460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a1ab`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a1ab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009f70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009f70`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a006`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a142`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1de`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a006`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a142`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1de`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009f4f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009f4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a10b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a10b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a119`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a119`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009f11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009f11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a017`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a153`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a017`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a153`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1f4`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x180009ed8  mov     [rsp-8+arg_10], rbx
0x180009edd  push    rbp
0x180009ede  push    rsi
0x180009edf  push    rdi
0x180009ee0  push    r14
0x180009ee2  push    r15
0x180009ee4  lea     rbp, [rsp-160h]
0x180009eec  sub     rsp, 260h
0x180009ef3  mov     rax, cs:__security_cookie
0x180009efa  xor     rax, rsp
0x180009efd  mov     [rbp+180h+var_30], rax
0x180009f04  mov     r15, rdx
0x180009f07  mov     qword ptr [rdx], 0
0x180009f0e  mov     rbx, rcx
0x180009f11  call    cs:__imp_GetCurrentProcessId
0x180009f17  mov     r14d, 130h
0x180009f1d  mov     [rsp+280h+var_258], rbx
0x180009f22  mov     r9d, eax
0x180009f25  mov     [rsp+280h+var_260], r14d; int
0x180009f2a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009f31  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009f36  lea     edx, [r14-2Ch]; unsigned __int64
0x180009f3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009f3f  mov     r9d, 1F0001h; dwDesiredAccess
0x180009f45  lea     rdx, [rsp+280h+Name]; lpName
0x180009f4a  xor     r8d, r8d; dwFlags
0x180009f4d  xor     ecx, ecx; lpMutexAttributes
0x180009f4f  call    cs:__imp_CreateMutexExW
0x180009f55  mov     rbx, rax
0x180009f58  test    rax, rax
0x180009f5b  jnz     short loc_180009F67
0x180009f5d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009f62  jmp     loc_18000A200
0x180009f67  xor     r8d, r8d; bAlertable
0x180009f6a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009f6d  mov     rcx, rbx; hHandle
0x180009f70  call    cs:__imp_WaitForSingleObjectEx
0x180009f76  cmp     eax, 102h
0x180009f7b  jz      short loc_180009F8D
0x180009f7d  test    eax, 0FFFFFF7Fh
0x180009f82  jnz     loc_18000A24A
0x180009f88  mov     rdi, rbx
0x180009f8b  jmp     short loc_180009F8F
0x180009f8d  xor     edi, edi
0x180009f8f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009f94  mov     [rsp+280h+hObject], 0
0x180009f9d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009fa2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009fa7  mov     esi, eax
0x180009fa9  test    eax, eax
0x180009fab  jns     short loc_18000A02C
0x180009fad  mov     rcx, [rbp+188h]; this
0x180009fb4  lea     r8, aWil; "wil"
0x180009fbb  mov     r9d, eax; char *
0x180009fbe  mov     edx, 66h ; 'f'; void *
0x180009fc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fc8  mov     rcx, [rbp+188h]; this
0x180009fcf  lea     r8, aWil; "wil"
0x180009fd6  mov     r9d, esi; char *
0x180009fd9  mov     edx, 6Fh ; 'o'; void *
0x180009fde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fe3  mov     rcx, [rbp+188h]; this
0x180009fea  lea     r8, aWil; "wil"
0x180009ff1  mov     r9d, esi; char *
0x180009ff4  mov     edx, 12Eh; void *
0x180009ff9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ffe  test    rdi, rdi
0x18000a001  jz      short loc_18000A014
0x18000a003  mov     rcx, rdi; hMutex
0x18000a006  call    cs:__imp_ReleaseMutex
0x18000a00c  test    eax, eax
0x18000a00e  jz      loc_18000A257
0x18000a014  mov     rcx, rbx; hObject
0x18000a017  call    cs:__imp_CloseHandle
0x18000a01d  test    eax, eax
0x18000a01f  jz      loc_18000A269
0x18000a025  mov     eax, esi
0x18000a027  jmp     loc_18000A200
0x18000a02c  mov     rax, [rsp+280h+hObject]
0x18000a031  lea     rcx, ds:0[rax*4]
0x18000a039  test    rcx, rcx
0x18000a03c  jz      short loc_18000A04C
0x18000a03e  mov     [r15], rcx
0x18000a041  mov     eax, [rcx]
0x18000a043  inc     eax
0x18000a045  mov     [rcx], eax
0x18000a047  jmp     loc_18000A1D6
0x18000a04c  mov     rdx, r14; dwBytes
0x18000a04f  mov     qword ptr [r15], 0
0x18000a056  mov     ecx, 8; dwFlags
0x18000a05b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a060  mov     r14, rax
0x18000a063  test    rax, rax
0x18000a066  jnz     short loc_18000A08D
0x18000a068  mov     rcx, [rbp+188h]; this
0x18000a06f  lea     r8, aWil; "wil"
0x18000a076  mov     esi, 8007000Eh
0x18000a07b  mov     edx, 14Bh; void *
0x18000a080  mov     r9d, esi; char *
0x18000a083  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a088  jmp     loc_18000A11F
0x18000a08d  xorps   xmm0, xmm0
0x18000a090  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000a096  test    r14b, 3
0x18000a09a  jnz     loc_18000A27B
0x18000a0a0  mov     r9, r14
0x18000a0a3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000a0a8  shr     r9, 2; unsigned __int64
0x18000a0ac  lea     rcx, [rsp+280h+hObject]; this
0x18000a0b1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000a0b6  mov     esi, eax
0x18000a0b8  test    eax, eax
0x18000a0ba  jns     loc_18000A166
0x18000a0c0  mov     rcx, [rbp+188h]; this
0x18000a0c7  lea     r8, aWil; "wil"
0x18000a0ce  mov     r9d, eax; char *
0x18000a0d1  mov     edx, 14Eh; void *
0x18000a0d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0db  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000a0e0  test    rcx, rcx
0x18000a0e3  jz      short loc_18000A0F3
0x18000a0e5  call    cs:__imp_CloseHandle
0x18000a0eb  test    eax, eax
0x18000a0ed  jz      loc_18000A281
0x18000a0f3  mov     rcx, [rsp+280h+hObject]; hObject
0x18000a0f8  test    rcx, rcx
0x18000a0fb  jz      short loc_18000A10B
0x18000a0fd  call    cs:__imp_CloseHandle
0x18000a103  test    eax, eax
0x18000a105  jz      loc_18000A293
0x18000a10b  call    cs:__imp_GetProcessHeap
0x18000a111  mov     r8, r14; lpMem
0x18000a114  xor     edx, edx; dwFlags
0x18000a116  mov     rcx, rax; hHeap
0x18000a119  call    cs:__imp_HeapFree
0x18000a11f  mov     rcx, [rbp+188h]; this
0x18000a126  lea     r8, aWil; "wil"
0x18000a12d  mov     r9d, esi; char *
0x18000a130  mov     edx, 137h; void *
0x18000a135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a13a  test    rdi, rdi
0x18000a13d  jz      short loc_18000A150
0x18000a13f  mov     rcx, rdi; hMutex
0x18000a142  call    cs:__imp_ReleaseMutex
0x18000a148  test    eax, eax
0x18000a14a  jz      loc_18000A2A5
0x18000a150  mov     rcx, rbx; hObject
0x18000a153  call    cs:__imp_CloseHandle
0x18000a159  test    eax, eax
0x18000a15b  jz      loc_18000A238
0x18000a161  jmp     loc_18000A025
0x18000a166  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000a16b  lea     rcx, [r14+28h]; void *
0x18000a16f  mov     dword ptr [r14], 1
0x18000a176  xor     edx, edx; Val
0x18000a178  mov     [r14+8], rbx
0x18000a17c  mov     r8d, 108h; Size
0x18000a182  movdqu  xmmword ptr [r14+10h], xmm0
0x18000a188  call    memset_0
0x18000a18d  xor     eax, eax
0x18000a18f  lea     rcx, [r14+28h]; this
0x18000a193  mov     [r14+20h], rax
0x18000a197  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a19c  lea     rbx, [r14+0E8h]
0x18000a1a3  xor     r8d, r8d; Flags
0x18000a1a6  mov     rcx, rbx; lpCriticalSection
0x18000a1a9  xor     edx, edx; dwSpinCount
0x18000a1ab  call    cs:__imp_InitializeCriticalSectionEx
0x18000a1b1  mov     qword ptr [rbx+28h], 0
0x18000a1b9  mov     qword ptr [rbx+30h], 0
0x18000a1c1  mov     qword ptr [rbx+38h], 0
0x18000a1c9  mov     qword ptr [rbx+40h], 0
0x18000a1d1  xor     ebx, ebx
0x18000a1d3  mov     [r15], r14
0x18000a1d6  test    rdi, rdi
0x18000a1d9  jz      short loc_18000A1EC
0x18000a1db  mov     rcx, rdi; hMutex
0x18000a1de  call    cs:__imp_ReleaseMutex
0x18000a1e4  test    eax, eax
0x18000a1e6  jz      loc_18000A2B7
0x18000a1ec  test    rbx, rbx
0x18000a1ef  jz      short loc_18000A1FE
0x18000a1f1  mov     rcx, rbx; hObject
0x18000a1f4  call    cs:__imp_CloseHandle
0x18000a1fa  test    eax, eax
0x18000a1fc  jz      short loc_18000A226
0x18000a1fe  xor     eax, eax
0x18000a200  mov     rcx, [rbp+180h+var_30]
0x18000a207  xor     rcx, rsp; StackCookie
0x18000a20a  call    __security_check_cookie
0x18000a20f  mov     rbx, [rsp+280h+arg_10]
0x18000a217  add     rsp, 260h
0x18000a21e  pop     r15
0x18000a220  pop     r14
0x18000a222  pop     rdi
0x18000a223  pop     rsi
0x18000a224  pop     rbp
0x18000a225  retn
0x18000a226  mov     rcx, [rbp+188h]; this
0x18000a22d  mov     edx, 0A0Bh; void *
0x18000a232  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a238  mov     rcx, [rbp+188h]; this
0x18000a23f  mov     edx, 0A0Bh; void *
0x18000a244  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a24a  mov     rcx, [rbp+188h]; this
0x18000a251  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a257  mov     rcx, [rbp+188h]; this
0x18000a25e  mov     edx, 0A15h; void *
0x18000a263  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a269  mov     rcx, [rbp+188h]; this
0x18000a270  mov     edx, 0A0Bh; void *
0x18000a275  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a27b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a281  mov     rcx, [rbp+188h]; this
0x18000a288  mov     edx, 0A0Bh; void *
0x18000a28d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a293  mov     rcx, [rbp+188h]; this
0x18000a29a  mov     edx, 0A0Bh; void *
0x18000a29f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2a5  mov     rcx, [rbp+188h]; this
0x18000a2ac  mov     edx, 0A15h; void *
0x18000a2b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a2b7  mov     rcx, [rbp+188h]; this
0x18000a2be  mov     edx, 0A15h; void *
0x18000a2c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
