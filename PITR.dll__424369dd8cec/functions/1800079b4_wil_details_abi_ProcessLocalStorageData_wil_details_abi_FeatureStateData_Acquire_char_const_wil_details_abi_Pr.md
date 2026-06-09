# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800079b4`
- end: `0x180007d7b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000cb08`

## callees

- `0x180005b58`
- `0x1800079b4`
- `0x18000a3bc`
- `0x18000d398`
- `0x18000ea90`
- `0x180012424`
- `0x18001b214`
- `0x18001c5bc`
- `0x18001cab0`
- `0x18001dd64`
- `0x18001dd74`
- `0x1800502c2`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007c5d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007c5d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007a2b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007a2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007acd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007bf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007c90`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007acd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007bf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007c90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007a4c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007a4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800079ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800079ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007bb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ca6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007bb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ca6`

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
0x1800079b4  mov     [rsp-8+arg_10], rbx
0x1800079b9  push    rbp
0x1800079ba  push    rsi
0x1800079bb  push    rdi
0x1800079bc  push    r14
0x1800079be  push    r15
0x1800079c0  lea     rbp, [rsp-160h]
0x1800079c8  sub     rsp, 260h
0x1800079cf  mov     rax, cs:__security_cookie
0x1800079d6  xor     rax, rsp
0x1800079d9  mov     [rbp+180h+var_30], rax
0x1800079e0  mov     r15, rdx
0x1800079e3  mov     qword ptr [rdx], 0
0x1800079ea  mov     rbx, rcx
0x1800079ed  call    cs:__imp_GetCurrentProcessId
0x1800079f3  mov     r14d, 130h
0x1800079f9  mov     [rsp+280h+var_258], rbx
0x1800079fe  mov     r9d, eax
0x180007a01  mov     [rsp+280h+var_260], r14d; int
0x180007a06  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007a0d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007a12  lea     edx, [r14-2Ch]; unsigned __int64
0x180007a16  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007a1b  mov     r9d, 1F0001h; dwDesiredAccess
0x180007a21  lea     rdx, [rsp+280h+Name]; lpName
0x180007a26  xor     r8d, r8d; dwFlags
0x180007a29  xor     ecx, ecx; lpMutexAttributes
0x180007a2b  call    cs:__imp_CreateMutexExW
0x180007a31  mov     rbx, rax
0x180007a34  test    rax, rax
0x180007a37  jnz     short loc_180007A43
0x180007a39  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007a3e  jmp     loc_180007CB2
0x180007a43  xor     r8d, r8d; bAlertable
0x180007a46  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007a49  mov     rcx, rbx; hHandle
0x180007a4c  call    cs:__imp_WaitForSingleObjectEx
0x180007a52  cmp     eax, 102h
0x180007a57  jz      short loc_180007A69
0x180007a59  test    eax, 0FFFFFF7Fh
0x180007a5e  jnz     loc_180007CFC
0x180007a64  mov     rdi, rbx
0x180007a67  jmp     short loc_180007A6B
0x180007a69  xor     edi, edi
0x180007a6b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180007a70  mov     [rsp+280h+hObject], 0
0x180007a79  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007a7e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007a83  mov     esi, eax
0x180007a85  test    eax, eax
0x180007a87  jns     short loc_180007AF3
0x180007a89  mov     rcx, [rbp+188h]; this
0x180007a90  mov     r9d, eax; char *
0x180007a93  mov     edx, 66h ; 'f'; void *
0x180007a98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a9d  mov     rcx, [rbp+188h]; this
0x180007aa4  mov     r9d, esi; char *
0x180007aa7  mov     edx, 6Fh ; 'o'; void *
0x180007aac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ab1  mov     rcx, [rbp+188h]; this
0x180007ab8  mov     r9d, esi; char *
0x180007abb  mov     edx, 12Eh; void *
0x180007ac0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ac5  test    rdi, rdi
0x180007ac8  jz      short loc_180007ADB
0x180007aca  mov     rcx, rdi; hMutex
0x180007acd  call    cs:__imp_ReleaseMutex
0x180007ad3  test    eax, eax
0x180007ad5  jz      loc_180007D09
0x180007adb  mov     rcx, rbx; hObject
0x180007ade  call    cs:__imp_CloseHandle
0x180007ae4  test    eax, eax
0x180007ae6  jz      loc_180007D1B
0x180007aec  mov     eax, esi
0x180007aee  jmp     loc_180007CB2
0x180007af3  mov     rax, [rsp+280h+hObject]
0x180007af8  lea     rcx, ds:0[rax*4]
0x180007b00  test    rcx, rcx
0x180007b03  jz      short loc_180007B13
0x180007b05  mov     [r15], rcx
0x180007b08  mov     eax, [rcx]
0x180007b0a  inc     eax
0x180007b0c  mov     [rcx], eax
0x180007b0e  jmp     loc_180007C88
0x180007b13  mov     rdx, r14; dwBytes
0x180007b16  mov     qword ptr [r15], 0
0x180007b1d  mov     ecx, 8; dwFlags
0x180007b22  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007b27  mov     r14, rax
0x180007b2a  test    rax, rax
0x180007b2d  jnz     short loc_180007B4D
0x180007b2f  mov     rcx, [rbp+188h]; this
0x180007b36  mov     esi, 8007000Eh
0x180007b3b  mov     r9d, esi; char *
0x180007b3e  mov     edx, 14Bh; void *
0x180007b43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b48  jmp     loc_180007BD8
0x180007b4d  xorps   xmm0, xmm0
0x180007b50  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180007b56  test    r14b, 3
0x180007b5a  jnz     loc_180007D2D
0x180007b60  mov     r9, r14
0x180007b63  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180007b68  shr     r9, 2; unsigned __int64
0x180007b6c  lea     rcx, [rsp+280h+hObject]; this
0x180007b71  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180007b76  mov     esi, eax
0x180007b78  test    eax, eax
0x180007b7a  jns     loc_180007C18
0x180007b80  mov     rcx, [rbp+188h]; this
0x180007b87  mov     r9d, eax; char *
0x180007b8a  mov     edx, 14Eh; void *
0x180007b8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b94  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180007b99  test    rcx, rcx
0x180007b9c  jz      short loc_180007BAC
0x180007b9e  call    cs:__imp_CloseHandle
0x180007ba4  test    eax, eax
0x180007ba6  jz      loc_180007D33
0x180007bac  mov     rcx, [rsp+280h+hObject]; hObject
0x180007bb1  test    rcx, rcx
0x180007bb4  jz      short loc_180007BC4
0x180007bb6  call    cs:__imp_CloseHandle
0x180007bbc  test    eax, eax
0x180007bbe  jz      loc_180007D45
0x180007bc4  call    cs:__imp_GetProcessHeap
0x180007bca  mov     r8, r14; lpMem
0x180007bcd  xor     edx, edx; dwFlags
0x180007bcf  mov     rcx, rax; hHeap
0x180007bd2  call    cs:__imp_HeapFree
0x180007bd8  mov     rcx, [rbp+188h]; this
0x180007bdf  mov     r9d, esi; char *
0x180007be2  mov     edx, 137h; void *
0x180007be7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007bec  test    rdi, rdi
0x180007bef  jz      short loc_180007C02
0x180007bf1  mov     rcx, rdi; hMutex
0x180007bf4  call    cs:__imp_ReleaseMutex
0x180007bfa  test    eax, eax
0x180007bfc  jz      loc_180007D57
0x180007c02  mov     rcx, rbx; hObject
0x180007c05  call    cs:__imp_CloseHandle
0x180007c0b  test    eax, eax
0x180007c0d  jz      loc_180007CEA
0x180007c13  jmp     loc_180007AEC
0x180007c18  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180007c1d  lea     rcx, [r14+28h]; void *
0x180007c21  mov     dword ptr [r14], 1
0x180007c28  xor     edx, edx; Val
0x180007c2a  mov     [r14+8], rbx
0x180007c2e  mov     r8d, 108h; Size
0x180007c34  movdqu  xmmword ptr [r14+10h], xmm0
0x180007c3a  call    memset_0
0x180007c3f  xor     eax, eax
0x180007c41  lea     rcx, [r14+28h]; this
0x180007c45  mov     [r14+20h], rax
0x180007c49  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007c4e  lea     rbx, [r14+0E8h]
0x180007c55  xor     r8d, r8d; Flags
0x180007c58  mov     rcx, rbx; lpCriticalSection
0x180007c5b  xor     edx, edx; dwSpinCount
0x180007c5d  call    cs:__imp_InitializeCriticalSectionEx
0x180007c63  mov     qword ptr [rbx+28h], 0
0x180007c6b  mov     qword ptr [rbx+30h], 0
0x180007c73  mov     qword ptr [rbx+38h], 0
0x180007c7b  mov     qword ptr [rbx+40h], 0
0x180007c83  xor     ebx, ebx
0x180007c85  mov     [r15], r14
0x180007c88  test    rdi, rdi
0x180007c8b  jz      short loc_180007C9E
0x180007c8d  mov     rcx, rdi; hMutex
0x180007c90  call    cs:__imp_ReleaseMutex
0x180007c96  test    eax, eax
0x180007c98  jz      loc_180007D69
0x180007c9e  test    rbx, rbx
0x180007ca1  jz      short loc_180007CB0
0x180007ca3  mov     rcx, rbx; hObject
0x180007ca6  call    cs:__imp_CloseHandle
0x180007cac  test    eax, eax
0x180007cae  jz      short loc_180007CD8
0x180007cb0  xor     eax, eax
0x180007cb2  mov     rcx, [rbp+180h+var_30]
0x180007cb9  xor     rcx, rsp; StackCookie
0x180007cbc  call    __security_check_cookie
0x180007cc1  mov     rbx, [rsp+280h+arg_10]
0x180007cc9  add     rsp, 260h
0x180007cd0  pop     r15
0x180007cd2  pop     r14
0x180007cd4  pop     rdi
0x180007cd5  pop     rsi
0x180007cd6  pop     rbp
0x180007cd7  retn
0x180007cd8  mov     rcx, [rbp+188h]; this
0x180007cdf  mov     edx, 0A0Bh; void *
0x180007ce4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007cea  mov     rcx, [rbp+188h]; this
0x180007cf1  mov     edx, 0A0Bh; void *
0x180007cf6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007cfc  mov     rcx, [rbp+188h]; this
0x180007d03  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007d09  mov     rcx, [rbp+188h]; this
0x180007d10  mov     edx, 0A15h; void *
0x180007d15  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d1b  mov     rcx, [rbp+188h]; this
0x180007d22  mov     edx, 0A0Bh; void *
0x180007d27  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d2d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007d33  mov     rcx, [rbp+188h]; this
0x180007d3a  mov     edx, 0A0Bh; void *
0x180007d3f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d45  mov     rcx, [rbp+188h]; this
0x180007d4c  mov     edx, 0A0Bh; void *
0x180007d51  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d57  mov     rcx, [rbp+188h]; this
0x180007d5e  mov     edx, 0A15h; void *
0x180007d63  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d69  mov     rcx, [rbp+188h]; this
0x180007d70  mov     edx, 0A15h; void *
0x180007d75  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
