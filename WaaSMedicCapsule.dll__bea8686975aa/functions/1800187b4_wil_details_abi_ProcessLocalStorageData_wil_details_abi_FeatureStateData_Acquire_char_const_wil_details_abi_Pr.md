# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800187b4`
- end: `0x180018ba5`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180018bac`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180007be8`
- `0x180007f18`
- `0x180008578`
- `0x180009664`
- `0x180009a54`
- `0x18000a5d0`
- `0x18000a6ac`
- `0x18000ab38`
- `0x18000ab48`
- `0x180018158`
- `0x1800187b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180018a87`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180018a87`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800188e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018a1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018aba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800188e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018a1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018aba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001884c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001884c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001882b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001882b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800189f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800189f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800189e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800189e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800187ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800187ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800188f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800189c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800189d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018a2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018ad0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800188f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800189c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800189d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018a2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018ad0`

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
0x1800187b4  mov     [rsp-8+arg_10], rbx
0x1800187b9  push    rbp
0x1800187ba  push    rsi
0x1800187bb  push    rdi
0x1800187bc  push    r14
0x1800187be  push    r15
0x1800187c0  lea     rbp, [rsp-160h]
0x1800187c8  sub     rsp, 260h
0x1800187cf  mov     rax, cs:__security_cookie
0x1800187d6  xor     rax, rsp
0x1800187d9  mov     [rbp+180h+var_30], rax
0x1800187e0  mov     r15, rdx
0x1800187e3  mov     qword ptr [rdx], 0
0x1800187ea  mov     rbx, rcx
0x1800187ed  call    cs:__imp_GetCurrentProcessId
0x1800187f3  mov     r14d, 130h
0x1800187f9  mov     [rsp+280h+var_258], rbx
0x1800187fe  mov     r9d, eax
0x180018801  mov     [rsp+280h+var_260], r14d; int
0x180018806  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001880d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180018812  lea     edx, [r14-2Ch]; unsigned __int64
0x180018816  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001881b  mov     r9d, 1F0001h; dwDesiredAccess
0x180018821  lea     rdx, [rsp+280h+Name]; lpName
0x180018826  xor     r8d, r8d; dwFlags
0x180018829  xor     ecx, ecx; lpMutexAttributes
0x18001882b  call    cs:__imp_CreateMutexExW
0x180018831  mov     rbx, rax
0x180018834  test    rax, rax
0x180018837  jnz     short loc_180018843
0x180018839  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001883e  jmp     loc_180018ADC
0x180018843  xor     r8d, r8d; bAlertable
0x180018846  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180018849  mov     rcx, rbx; hHandle
0x18001884c  call    cs:__imp_WaitForSingleObjectEx
0x180018852  cmp     eax, 102h
0x180018857  jz      short loc_180018869
0x180018859  test    eax, 0FFFFFF7Fh
0x18001885e  jnz     loc_180018B26
0x180018864  mov     rdi, rbx
0x180018867  jmp     short loc_18001886B
0x180018869  xor     edi, edi
0x18001886b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180018870  mov     [rsp+280h+hObject], 0
0x180018879  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001887e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180018883  mov     esi, eax
0x180018885  test    eax, eax
0x180018887  jns     short loc_180018908
0x180018889  mov     rcx, [rbp+188h]; this
0x180018890  lea     r8, aWil; "wil"
0x180018897  mov     r9d, eax; char *
0x18001889a  mov     edx, 66h ; 'f'; void *
0x18001889f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188a4  mov     rcx, [rbp+188h]; this
0x1800188ab  lea     r8, aWil; "wil"
0x1800188b2  mov     r9d, esi; char *
0x1800188b5  mov     edx, 6Fh ; 'o'; void *
0x1800188ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188bf  mov     rcx, [rbp+188h]; this
0x1800188c6  lea     r8, aWil; "wil"
0x1800188cd  mov     r9d, esi; char *
0x1800188d0  mov     edx, 12Eh; void *
0x1800188d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188da  test    rdi, rdi
0x1800188dd  jz      short loc_1800188F0
0x1800188df  mov     rcx, rdi; hMutex
0x1800188e2  call    cs:__imp_ReleaseMutex
0x1800188e8  test    eax, eax
0x1800188ea  jz      loc_180018B33
0x1800188f0  mov     rcx, rbx; hObject
0x1800188f3  call    cs:__imp_CloseHandle
0x1800188f9  test    eax, eax
0x1800188fb  jz      loc_180018B45
0x180018901  mov     eax, esi
0x180018903  jmp     loc_180018ADC
0x180018908  mov     rax, [rsp+280h+hObject]
0x18001890d  lea     rcx, ds:0[rax*4]
0x180018915  test    rcx, rcx
0x180018918  jz      short loc_180018928
0x18001891a  mov     [r15], rcx
0x18001891d  mov     eax, [rcx]
0x18001891f  inc     eax
0x180018921  mov     [rcx], eax
0x180018923  jmp     loc_180018AB2
0x180018928  mov     rdx, r14; dwBytes
0x18001892b  mov     qword ptr [r15], 0
0x180018932  mov     ecx, 8; dwFlags
0x180018937  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001893c  mov     r14, rax
0x18001893f  test    rax, rax
0x180018942  jnz     short loc_180018969
0x180018944  mov     rcx, [rbp+188h]; this
0x18001894b  lea     r8, aWil; "wil"
0x180018952  mov     esi, 8007000Eh
0x180018957  mov     edx, 14Bh; void *
0x18001895c  mov     r9d, esi; char *
0x18001895f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018964  jmp     loc_1800189FB
0x180018969  xorps   xmm0, xmm0
0x18001896c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180018972  test    r14b, 3
0x180018976  jnz     loc_180018B57
0x18001897c  mov     r9, r14
0x18001897f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180018984  shr     r9, 2; unsigned __int64
0x180018988  lea     rcx, [rsp+280h+hObject]; this
0x18001898d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180018992  mov     esi, eax
0x180018994  test    eax, eax
0x180018996  jns     loc_180018A42
0x18001899c  mov     rcx, [rbp+188h]; this
0x1800189a3  lea     r8, aWil; "wil"
0x1800189aa  mov     r9d, eax; char *
0x1800189ad  mov     edx, 14Eh; void *
0x1800189b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800189b7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800189bc  test    rcx, rcx
0x1800189bf  jz      short loc_1800189CF
0x1800189c1  call    cs:__imp_CloseHandle
0x1800189c7  test    eax, eax
0x1800189c9  jz      loc_180018B5D
0x1800189cf  mov     rcx, [rsp+280h+hObject]; hObject
0x1800189d4  test    rcx, rcx
0x1800189d7  jz      short loc_1800189E7
0x1800189d9  call    cs:__imp_CloseHandle
0x1800189df  test    eax, eax
0x1800189e1  jz      loc_180018B6F
0x1800189e7  call    cs:__imp_GetProcessHeap
0x1800189ed  mov     r8, r14; lpMem
0x1800189f0  xor     edx, edx; dwFlags
0x1800189f2  mov     rcx, rax; hHeap
0x1800189f5  call    cs:__imp_HeapFree
0x1800189fb  mov     rcx, [rbp+188h]; this
0x180018a02  lea     r8, aWil; "wil"
0x180018a09  mov     r9d, esi; char *
0x180018a0c  mov     edx, 137h; void *
0x180018a11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a16  test    rdi, rdi
0x180018a19  jz      short loc_180018A2C
0x180018a1b  mov     rcx, rdi; hMutex
0x180018a1e  call    cs:__imp_ReleaseMutex
0x180018a24  test    eax, eax
0x180018a26  jz      loc_180018B81
0x180018a2c  mov     rcx, rbx; hObject
0x180018a2f  call    cs:__imp_CloseHandle
0x180018a35  test    eax, eax
0x180018a37  jz      loc_180018B14
0x180018a3d  jmp     loc_180018901
0x180018a42  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180018a47  lea     rcx, [r14+28h]; void *
0x180018a4b  mov     dword ptr [r14], 1
0x180018a52  xor     edx, edx; Val
0x180018a54  mov     [r14+8], rbx
0x180018a58  mov     r8d, 108h; Size
0x180018a5e  movdqu  xmmword ptr [r14+10h], xmm0
0x180018a64  call    memset_0
0x180018a69  xor     eax, eax
0x180018a6b  lea     rcx, [r14+28h]; this
0x180018a6f  mov     [r14+20h], rax
0x180018a73  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180018a78  lea     rbx, [r14+0E8h]
0x180018a7f  xor     r8d, r8d; Flags
0x180018a82  mov     rcx, rbx; lpCriticalSection
0x180018a85  xor     edx, edx; dwSpinCount
0x180018a87  call    cs:__imp_InitializeCriticalSectionEx
0x180018a8d  mov     qword ptr [rbx+28h], 0
0x180018a95  mov     qword ptr [rbx+30h], 0
0x180018a9d  mov     qword ptr [rbx+38h], 0
0x180018aa5  mov     qword ptr [rbx+40h], 0
0x180018aad  xor     ebx, ebx
0x180018aaf  mov     [r15], r14
0x180018ab2  test    rdi, rdi
0x180018ab5  jz      short loc_180018AC8
0x180018ab7  mov     rcx, rdi; hMutex
0x180018aba  call    cs:__imp_ReleaseMutex
0x180018ac0  test    eax, eax
0x180018ac2  jz      loc_180018B93
0x180018ac8  test    rbx, rbx
0x180018acb  jz      short loc_180018ADA
0x180018acd  mov     rcx, rbx; hObject
0x180018ad0  call    cs:__imp_CloseHandle
0x180018ad6  test    eax, eax
0x180018ad8  jz      short loc_180018B02
0x180018ada  xor     eax, eax
0x180018adc  mov     rcx, [rbp+180h+var_30]
0x180018ae3  xor     rcx, rsp; StackCookie
0x180018ae6  call    __security_check_cookie
0x180018aeb  mov     rbx, [rsp+280h+arg_10]
0x180018af3  add     rsp, 260h
0x180018afa  pop     r15
0x180018afc  pop     r14
0x180018afe  pop     rdi
0x180018aff  pop     rsi
0x180018b00  pop     rbp
0x180018b01  retn
0x180018b02  mov     rcx, [rbp+188h]; this
0x180018b09  mov     edx, 0A0Bh; void *
0x180018b0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018b14  mov     rcx, [rbp+188h]; this
0x180018b1b  mov     edx, 0A0Bh; void *
0x180018b20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018b26  mov     rcx, [rbp+188h]; this
0x180018b2d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180018b33  mov     rcx, [rbp+188h]; this
0x180018b3a  mov     edx, 0A15h; void *
0x180018b3f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018b45  mov     rcx, [rbp+188h]; this
0x180018b4c  mov     edx, 0A0Bh; void *
0x180018b51  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018b57  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180018b5d  mov     rcx, [rbp+188h]; this
0x180018b64  mov     edx, 0A0Bh; void *
0x180018b69  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018b6f  mov     rcx, [rbp+188h]; this
0x180018b76  mov     edx, 0A0Bh; void *
0x180018b7b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018b81  mov     rcx, [rbp+188h]; this
0x180018b88  mov     edx, 0A15h; void *
0x180018b8d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018b93  mov     rcx, [rbp+188h]; this
0x180018b9a  mov     edx, 0A15h; void *
0x180018b9f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
