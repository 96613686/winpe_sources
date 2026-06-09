# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009dec`
- end: `0x18000a1dd`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000a8d8`

## callees

- `0x180002240`
- `0x180002db8`
- `0x180004e7c`
- `0x180005194`
- `0x1800058a4`
- `0x1800065d8`
- `0x180006a14`
- `0x180007404`
- `0x1800075ac`
- `0x180007a48`
- `0x180007a58`
- `0x180008e40`
- `0x180009dec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009e84`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009e84`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009e63`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009e63`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009f1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a056`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a0f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009f1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a056`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a0f2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a0bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a0bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a02d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a02d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a01f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a01f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009e25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009e25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ff9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a011`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a067`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a108`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ff9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a011`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a067`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a108`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
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
0x180009dec  mov     [rsp-8+arg_10], rbx
0x180009df1  push    rbp
0x180009df2  push    rsi
0x180009df3  push    rdi
0x180009df4  push    r14
0x180009df6  push    r15
0x180009df8  lea     rbp, [rsp-160h]
0x180009e00  sub     rsp, 260h
0x180009e07  mov     rax, cs:__security_cookie
0x180009e0e  xor     rax, rsp
0x180009e11  mov     [rbp+180h+var_30], rax
0x180009e18  mov     r15, rdx
0x180009e1b  mov     qword ptr [rdx], 0
0x180009e22  mov     rbx, rcx
0x180009e25  call    cs:__imp_GetCurrentProcessId
0x180009e2b  mov     r14d, 130h
0x180009e31  mov     [rsp+280h+var_258], rbx
0x180009e36  mov     r9d, eax
0x180009e39  mov     [rsp+280h+var_260], r14d; int
0x180009e3e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009e45  lea     rcx, [rsp+280h+Name]; Buffer
0x180009e4a  lea     edx, [r14-2Ch]; unsigned __int64
0x180009e4e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009e53  mov     r9d, 1F0001h; dwDesiredAccess
0x180009e59  lea     rdx, [rsp+280h+Name]; lpName
0x180009e5e  xor     r8d, r8d; dwFlags
0x180009e61  xor     ecx, ecx; lpMutexAttributes
0x180009e63  call    cs:__imp_CreateMutexExW
0x180009e69  mov     rbx, rax
0x180009e6c  test    rax, rax
0x180009e6f  jnz     short loc_180009E7B
0x180009e71  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009e76  jmp     loc_18000A114
0x180009e7b  xor     r8d, r8d; bAlertable
0x180009e7e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009e81  mov     rcx, rbx; hHandle
0x180009e84  call    cs:__imp_WaitForSingleObjectEx
0x180009e8a  cmp     eax, 102h
0x180009e8f  jz      short loc_180009EA1
0x180009e91  test    eax, 0FFFFFF7Fh
0x180009e96  jnz     loc_18000A15E
0x180009e9c  mov     rdi, rbx
0x180009e9f  jmp     short loc_180009EA3
0x180009ea1  xor     edi, edi
0x180009ea3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009ea8  mov     [rsp+280h+hObject], 0
0x180009eb1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009eb6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009ebb  mov     esi, eax
0x180009ebd  test    eax, eax
0x180009ebf  jns     short loc_180009F40
0x180009ec1  mov     rcx, [rbp+188h]; this
0x180009ec8  lea     r8, aWil; "wil"
0x180009ecf  mov     r9d, eax; char *
0x180009ed2  mov     edx, 66h ; 'f'; void *
0x180009ed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009edc  mov     rcx, [rbp+188h]; this
0x180009ee3  lea     r8, aWil; "wil"
0x180009eea  mov     r9d, esi; char *
0x180009eed  mov     edx, 6Fh ; 'o'; void *
0x180009ef2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ef7  mov     rcx, [rbp+188h]; this
0x180009efe  lea     r8, aWil; "wil"
0x180009f05  mov     r9d, esi; char *
0x180009f08  mov     edx, 12Eh; void *
0x180009f0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f12  test    rdi, rdi
0x180009f15  jz      short loc_180009F28
0x180009f17  mov     rcx, rdi; hMutex
0x180009f1a  call    cs:__imp_ReleaseMutex
0x180009f20  test    eax, eax
0x180009f22  jz      loc_18000A16B
0x180009f28  mov     rcx, rbx; hObject
0x180009f2b  call    cs:__imp_CloseHandle
0x180009f31  test    eax, eax
0x180009f33  jz      loc_18000A17D
0x180009f39  mov     eax, esi
0x180009f3b  jmp     loc_18000A114
0x180009f40  mov     rax, [rsp+280h+hObject]
0x180009f45  lea     rcx, ds:0[rax*4]
0x180009f4d  test    rcx, rcx
0x180009f50  jz      short loc_180009F60
0x180009f52  mov     [r15], rcx
0x180009f55  mov     eax, [rcx]
0x180009f57  inc     eax
0x180009f59  mov     [rcx], eax
0x180009f5b  jmp     loc_18000A0EA
0x180009f60  mov     rdx, r14; dwBytes
0x180009f63  mov     qword ptr [r15], 0
0x180009f6a  mov     ecx, 8; dwFlags
0x180009f6f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009f74  mov     r14, rax
0x180009f77  test    rax, rax
0x180009f7a  jnz     short loc_180009FA1
0x180009f7c  mov     rcx, [rbp+188h]; this
0x180009f83  lea     r8, aWil; "wil"
0x180009f8a  mov     esi, 8007000Eh
0x180009f8f  mov     edx, 14Bh; void *
0x180009f94  mov     r9d, esi; char *
0x180009f97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f9c  jmp     loc_18000A033
0x180009fa1  xorps   xmm0, xmm0
0x180009fa4  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180009faa  test    r14b, 3
0x180009fae  jnz     loc_18000A18F
0x180009fb4  mov     r9, r14
0x180009fb7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180009fbc  shr     r9, 2; unsigned __int64
0x180009fc0  lea     rcx, [rsp+280h+hObject]; this
0x180009fc5  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180009fca  mov     esi, eax
0x180009fcc  test    eax, eax
0x180009fce  jns     loc_18000A07A
0x180009fd4  mov     rcx, [rbp+188h]; this
0x180009fdb  lea     r8, aWil; "wil"
0x180009fe2  mov     r9d, eax; char *
0x180009fe5  mov     edx, 14Eh; void *
0x180009fea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fef  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180009ff4  test    rcx, rcx
0x180009ff7  jz      short loc_18000A007
0x180009ff9  call    cs:__imp_CloseHandle
0x180009fff  test    eax, eax
0x18000a001  jz      loc_18000A195
0x18000a007  mov     rcx, [rsp+280h+hObject]; hObject
0x18000a00c  test    rcx, rcx
0x18000a00f  jz      short loc_18000A01F
0x18000a011  call    cs:__imp_CloseHandle
0x18000a017  test    eax, eax
0x18000a019  jz      loc_18000A1A7
0x18000a01f  call    cs:__imp_GetProcessHeap
0x18000a025  mov     r8, r14; lpMem
0x18000a028  xor     edx, edx; dwFlags
0x18000a02a  mov     rcx, rax; hHeap
0x18000a02d  call    cs:__imp_HeapFree
0x18000a033  mov     rcx, [rbp+188h]; this
0x18000a03a  lea     r8, aWil; "wil"
0x18000a041  mov     r9d, esi; char *
0x18000a044  mov     edx, 137h; void *
0x18000a049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a04e  test    rdi, rdi
0x18000a051  jz      short loc_18000A064
0x18000a053  mov     rcx, rdi; hMutex
0x18000a056  call    cs:__imp_ReleaseMutex
0x18000a05c  test    eax, eax
0x18000a05e  jz      loc_18000A1B9
0x18000a064  mov     rcx, rbx; hObject
0x18000a067  call    cs:__imp_CloseHandle
0x18000a06d  test    eax, eax
0x18000a06f  jz      loc_18000A14C
0x18000a075  jmp     loc_180009F39
0x18000a07a  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000a07f  lea     rcx, [r14+28h]; void *
0x18000a083  mov     dword ptr [r14], 1
0x18000a08a  xor     edx, edx; Val
0x18000a08c  mov     [r14+8], rbx
0x18000a090  mov     r8d, 108h; Size
0x18000a096  movdqu  xmmword ptr [r14+10h], xmm0
0x18000a09c  call    memset_0
0x18000a0a1  xor     eax, eax
0x18000a0a3  lea     rcx, [r14+28h]; this
0x18000a0a7  mov     [r14+20h], rax
0x18000a0ab  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a0b0  lea     rbx, [r14+0E8h]
0x18000a0b7  xor     r8d, r8d; Flags
0x18000a0ba  mov     rcx, rbx; lpCriticalSection
0x18000a0bd  xor     edx, edx; dwSpinCount
0x18000a0bf  call    cs:__imp_InitializeCriticalSectionEx
0x18000a0c5  mov     qword ptr [rbx+28h], 0
0x18000a0cd  mov     qword ptr [rbx+30h], 0
0x18000a0d5  mov     qword ptr [rbx+38h], 0
0x18000a0dd  mov     qword ptr [rbx+40h], 0
0x18000a0e5  xor     ebx, ebx
0x18000a0e7  mov     [r15], r14
0x18000a0ea  test    rdi, rdi
0x18000a0ed  jz      short loc_18000A100
0x18000a0ef  mov     rcx, rdi; hMutex
0x18000a0f2  call    cs:__imp_ReleaseMutex
0x18000a0f8  test    eax, eax
0x18000a0fa  jz      loc_18000A1CB
0x18000a100  test    rbx, rbx
0x18000a103  jz      short loc_18000A112
0x18000a105  mov     rcx, rbx; hObject
0x18000a108  call    cs:__imp_CloseHandle
0x18000a10e  test    eax, eax
0x18000a110  jz      short loc_18000A13A
0x18000a112  xor     eax, eax
0x18000a114  mov     rcx, [rbp+180h+var_30]
0x18000a11b  xor     rcx, rsp; StackCookie
0x18000a11e  call    __security_check_cookie
0x18000a123  mov     rbx, [rsp+280h+arg_10]
0x18000a12b  add     rsp, 260h
0x18000a132  pop     r15
0x18000a134  pop     r14
0x18000a136  pop     rdi
0x18000a137  pop     rsi
0x18000a138  pop     rbp
0x18000a139  retn
0x18000a13a  mov     rcx, [rbp+188h]; this
0x18000a141  mov     edx, 0A0Bh; void *
0x18000a146  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a14c  mov     rcx, [rbp+188h]; this
0x18000a153  mov     edx, 0A0Bh; void *
0x18000a158  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a15e  mov     rcx, [rbp+188h]; this
0x18000a165  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a16b  mov     rcx, [rbp+188h]; this
0x18000a172  mov     edx, 0A15h; void *
0x18000a177  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a17d  mov     rcx, [rbp+188h]; this
0x18000a184  mov     edx, 0A0Bh; void *
0x18000a189  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a18f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a195  mov     rcx, [rbp+188h]; this
0x18000a19c  mov     edx, 0A0Bh; void *
0x18000a1a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a1a7  mov     rcx, [rbp+188h]; this
0x18000a1ae  mov     edx, 0A0Bh; void *
0x18000a1b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a1b9  mov     rcx, [rbp+188h]; this
0x18000a1c0  mov     edx, 0A15h; void *
0x18000a1c5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a1cb  mov     rcx, [rbp+188h]; this
0x18000a1d2  mov     edx, 0A15h; void *
0x18000a1d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
