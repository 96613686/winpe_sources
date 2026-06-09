# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800109f4`
- end: `0x180010dc7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800134d0`

## callees

- `0x180001d40`
- `0x180002928`
- `0x180007930`
- `0x18000a074`
- `0x18001029c`
- `0x1800109f4`
- `0x1800124b0`
- `0x180014214`
- `0x180014c4c`
- `0x1800165e8`
- `0x180016dd4`
- `0x1800175e8`
- `0x180017f00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010b0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010c34`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010cd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010b0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010c34`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010cd0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010a8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010a8c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180010c9d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180010c9d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010a6b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010a6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010a2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010a2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010c45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010c45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ce6`

## string_xrefs

- `0x180010d43`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  _DWORD *v21; // rcx
  unsigned __int64 v22; // rax
  wil::details::in1diag3 *v23; // rcx
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  __int128 v38; // xmm0
  unsigned int v39; // r8d
  const char *v40; // r9
  unsigned int v41; // r8d
  const char *v42; // r9
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v43);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)v14, v44);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
    return v14;
  }
  v21 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v21;
    ++*v21;
    goto LABEL_28;
  }
  *a2 = 0;
  v22 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v25 = (_DWORD *)v22;
  if ( !v22 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v14, v45);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
    return v14;
  }
  *(_OWORD *)hObject = 0;
  if ( (v22 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
  v27 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v24,
          v22 >> 2);
  v14 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
    goto LABEL_23;
  }
  v38 = *(_OWORD *)hObject;
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  *((_OWORD *)v25 + 1) = v38;
  memset_0(v25 + 10, 0, 0x108u);
  *((_QWORD *)v25 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 58), 0, 0);
  *((_QWORD *)v25 + 34) = 0;
  *((_QWORD *)v25 + 35) = 0;
  *((_QWORD *)v25 + 36) = 0;
  *((_QWORD *)v25 + 37) = 0;
  v6 = 0;
  *a2 = v25;
LABEL_28:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v39, v40);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v41, v42);
  return 0;
}

```

## disassembly

```asm
0x1800109f4  mov     [rsp-8+arg_10], rbx
0x1800109f9  push    rbp
0x1800109fa  push    rsi
0x1800109fb  push    rdi
0x1800109fc  push    r14
0x1800109fe  push    r15
0x180010a00  lea     rbp, [rsp-160h]
0x180010a08  sub     rsp, 260h
0x180010a0f  mov     rax, cs:__security_cookie
0x180010a16  xor     rax, rsp
0x180010a19  mov     [rbp+180h+var_30], rax
0x180010a20  mov     r15, rdx
0x180010a23  mov     qword ptr [rdx], 0
0x180010a2a  mov     rbx, rcx
0x180010a2d  call    cs:__imp_GetCurrentProcessId
0x180010a33  mov     r14d, 130h
0x180010a39  mov     [rsp+280h+var_258], rbx
0x180010a3e  mov     r9d, eax
0x180010a41  mov     [rsp+280h+var_260], r14d; int
0x180010a46  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010a4d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010a52  lea     edx, [r14-2Ch]; unsigned __int64
0x180010a56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010a5b  mov     r9d, 1F0001h; dwDesiredAccess
0x180010a61  lea     rdx, [rsp+280h+Name]; lpName
0x180010a66  xor     r8d, r8d; dwFlags
0x180010a69  xor     ecx, ecx; lpMutexAttributes
0x180010a6b  call    cs:__imp_CreateMutexExW
0x180010a71  mov     rbx, rax
0x180010a74  test    rax, rax
0x180010a77  jnz     short loc_180010A83
0x180010a79  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010a7e  jmp     loc_180010CF2
0x180010a83  xor     r8d, r8d; bAlertable
0x180010a86  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010a89  mov     rcx, rbx; hHandle
0x180010a8c  call    cs:__imp_WaitForSingleObjectEx
0x180010a92  cmp     eax, 102h
0x180010a97  jz      short loc_180010AA9
0x180010a99  test    eax, 0FFFFFF7Fh
0x180010a9e  jnz     loc_180010D3C
0x180010aa4  mov     rdi, rbx
0x180010aa7  jmp     short loc_180010AAB
0x180010aa9  xor     edi, edi
0x180010aab  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180010ab0  mov     [rsp+280h+hObject], 0
0x180010ab9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010abe  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180010ac3  mov     esi, eax
0x180010ac5  test    eax, eax
0x180010ac7  jns     short loc_180010B33
0x180010ac9  mov     rcx, [rbp+188h]; this
0x180010ad0  mov     r9d, eax; char *
0x180010ad3  mov     edx, 66h ; 'f'; void *
0x180010ad8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010add  mov     rcx, [rbp+188h]; this
0x180010ae4  mov     r9d, esi; char *
0x180010ae7  mov     edx, 6Fh ; 'o'; void *
0x180010aec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010af1  mov     rcx, [rbp+188h]; this
0x180010af8  mov     r9d, esi; char *
0x180010afb  mov     edx, 12Eh; void *
0x180010b00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b05  test    rdi, rdi
0x180010b08  jz      short loc_180010B1B
0x180010b0a  mov     rcx, rdi; hMutex
0x180010b0d  call    cs:__imp_ReleaseMutex
0x180010b13  test    eax, eax
0x180010b15  jz      loc_180010D55
0x180010b1b  mov     rcx, rbx; hObject
0x180010b1e  call    cs:__imp_CloseHandle
0x180010b24  test    eax, eax
0x180010b26  jz      loc_180010D67
0x180010b2c  mov     eax, esi
0x180010b2e  jmp     loc_180010CF2
0x180010b33  mov     rax, [rsp+280h+hObject]
0x180010b38  lea     rcx, ds:0[rax*4]
0x180010b40  test    rcx, rcx
0x180010b43  jz      short loc_180010B53
0x180010b45  mov     [r15], rcx
0x180010b48  mov     eax, [rcx]
0x180010b4a  inc     eax
0x180010b4c  mov     [rcx], eax
0x180010b4e  jmp     loc_180010CC8
0x180010b53  mov     rdx, r14; dwBytes
0x180010b56  mov     qword ptr [r15], 0
0x180010b5d  mov     ecx, 8; dwFlags
0x180010b62  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010b67  mov     r14, rax
0x180010b6a  test    rax, rax
0x180010b6d  jnz     short loc_180010B8D
0x180010b6f  mov     rcx, [rbp+188h]; this
0x180010b76  mov     esi, 8007000Eh
0x180010b7b  mov     r9d, esi; char *
0x180010b7e  mov     edx, 14Bh; void *
0x180010b83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b88  jmp     loc_180010C18
0x180010b8d  xorps   xmm0, xmm0
0x180010b90  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180010b96  test    r14b, 3
0x180010b9a  jnz     loc_180010D79
0x180010ba0  mov     r9, r14
0x180010ba3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180010ba8  shr     r9, 2; unsigned __int64
0x180010bac  lea     rcx, [rsp+280h+hObject]; this
0x180010bb1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180010bb6  mov     esi, eax
0x180010bb8  test    eax, eax
0x180010bba  jns     loc_180010C58
0x180010bc0  mov     rcx, [rbp+188h]; this
0x180010bc7  mov     r9d, eax; char *
0x180010bca  mov     edx, 14Eh; void *
0x180010bcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bd4  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180010bd9  test    rcx, rcx
0x180010bdc  jz      short loc_180010BEC
0x180010bde  call    cs:__imp_CloseHandle
0x180010be4  test    eax, eax
0x180010be6  jz      loc_180010D7F
0x180010bec  mov     rcx, [rsp+280h+hObject]; hObject
0x180010bf1  test    rcx, rcx
0x180010bf4  jz      short loc_180010C04
0x180010bf6  call    cs:__imp_CloseHandle
0x180010bfc  test    eax, eax
0x180010bfe  jz      loc_180010D91
0x180010c04  call    cs:__imp_GetProcessHeap
0x180010c0a  mov     r8, r14; lpMem
0x180010c0d  xor     edx, edx; dwFlags
0x180010c0f  mov     rcx, rax; hHeap
0x180010c12  call    cs:__imp_HeapFree
0x180010c18  mov     rcx, [rbp+188h]; this
0x180010c1f  mov     r9d, esi; char *
0x180010c22  mov     edx, 137h; void *
0x180010c27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c2c  test    rdi, rdi
0x180010c2f  jz      short loc_180010C42
0x180010c31  mov     rcx, rdi; hMutex
0x180010c34  call    cs:__imp_ReleaseMutex
0x180010c3a  test    eax, eax
0x180010c3c  jz      loc_180010DA3
0x180010c42  mov     rcx, rbx; hObject
0x180010c45  call    cs:__imp_CloseHandle
0x180010c4b  test    eax, eax
0x180010c4d  jz      loc_180010D2A
0x180010c53  jmp     loc_180010B2C
0x180010c58  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180010c5d  lea     rcx, [r14+28h]; void *
0x180010c61  mov     dword ptr [r14], 1
0x180010c68  xor     edx, edx; Val
0x180010c6a  mov     [r14+8], rbx
0x180010c6e  mov     r8d, 108h; Size
0x180010c74  movdqu  xmmword ptr [r14+10h], xmm0
0x180010c7a  call    memset_0
0x180010c7f  xor     eax, eax
0x180010c81  lea     rcx, [r14+28h]; this
0x180010c85  mov     [r14+20h], rax
0x180010c89  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180010c8e  lea     rbx, [r14+0E8h]
0x180010c95  xor     r8d, r8d; Flags
0x180010c98  mov     rcx, rbx; lpCriticalSection
0x180010c9b  xor     edx, edx; dwSpinCount
0x180010c9d  call    cs:__imp_InitializeCriticalSectionEx
0x180010ca3  mov     qword ptr [rbx+28h], 0
0x180010cab  mov     qword ptr [rbx+30h], 0
0x180010cb3  mov     qword ptr [rbx+38h], 0
0x180010cbb  mov     qword ptr [rbx+40h], 0
0x180010cc3  xor     ebx, ebx
0x180010cc5  mov     [r15], r14
0x180010cc8  test    rdi, rdi
0x180010ccb  jz      short loc_180010CDE
0x180010ccd  mov     rcx, rdi; hMutex
0x180010cd0  call    cs:__imp_ReleaseMutex
0x180010cd6  test    eax, eax
0x180010cd8  jz      loc_180010DB5
0x180010cde  test    rbx, rbx
0x180010ce1  jz      short loc_180010CF0
0x180010ce3  mov     rcx, rbx; hObject
0x180010ce6  call    cs:__imp_CloseHandle
0x180010cec  test    eax, eax
0x180010cee  jz      short loc_180010D18
0x180010cf0  xor     eax, eax
0x180010cf2  mov     rcx, [rbp+180h+var_30]
0x180010cf9  xor     rcx, rsp; StackCookie
0x180010cfc  call    __security_check_cookie
0x180010d01  mov     rbx, [rsp+280h+arg_10]
0x180010d09  add     rsp, 260h
0x180010d10  pop     r15
0x180010d12  pop     r14
0x180010d14  pop     rdi
0x180010d15  pop     rsi
0x180010d16  pop     rbp
0x180010d17  retn
0x180010d18  mov     rcx, [rbp+188h]; this
0x180010d1f  mov     edx, 0A0Bh; void *
0x180010d24  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d2a  mov     rcx, [rbp+188h]; this
0x180010d31  mov     edx, 0A0Bh; void *
0x180010d36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d3c  mov     rcx, [rbp+188h]; this
0x180010d43  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010d4a  mov     edx, 0E01h; void *
0x180010d4f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180010d55  mov     rcx, [rbp+188h]; this
0x180010d5c  mov     edx, 0A15h; void *
0x180010d61  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d67  mov     rcx, [rbp+188h]; this
0x180010d6e  mov     edx, 0A0Bh; void *
0x180010d73  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d79  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180010d7f  mov     rcx, [rbp+188h]; this
0x180010d86  mov     edx, 0A0Bh; void *
0x180010d8b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d91  mov     rcx, [rbp+188h]; this
0x180010d98  mov     edx, 0A0Bh; void *
0x180010d9d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010da3  mov     rcx, [rbp+188h]; this
0x180010daa  mov     edx, 0A15h; void *
0x180010daf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010db5  mov     rcx, [rbp+188h]; this
0x180010dbc  mov     edx, 0A15h; void *
0x180010dc1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
