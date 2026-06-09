# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007c8c`
- end: `0x18000807d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180008084`

## callees

- `0x180002170`
- `0x180002cb4`
- `0x180004258`
- `0x180004544`
- `0x180004b98`
- `0x180005678`
- `0x180005ad4`
- `0x1800064c4`
- `0x18000659c`
- `0x18000697c`
- `0x18000698c`
- `0x180007548`
- `0x180007c8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007dba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007ef6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007f92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007dba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007ef6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007f92`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007d24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007d24`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007d03`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007d03`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007f5f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ebf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ebf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ecd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ecd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007cc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007cc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007eb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007eb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fa8`

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
0x180007c8c  mov     [rsp-8+arg_10], rbx
0x180007c91  push    rbp
0x180007c92  push    rsi
0x180007c93  push    rdi
0x180007c94  push    r14
0x180007c96  push    r15
0x180007c98  lea     rbp, [rsp-160h]
0x180007ca0  sub     rsp, 260h
0x180007ca7  mov     rax, cs:__security_cookie
0x180007cae  xor     rax, rsp
0x180007cb1  mov     [rbp+180h+var_30], rax
0x180007cb8  mov     r15, rdx
0x180007cbb  mov     qword ptr [rdx], 0
0x180007cc2  mov     rbx, rcx
0x180007cc5  call    cs:__imp_GetCurrentProcessId
0x180007ccb  mov     r14d, 130h
0x180007cd1  mov     [rsp+280h+var_258], rbx
0x180007cd6  mov     r9d, eax
0x180007cd9  mov     [rsp+280h+var_260], r14d; int
0x180007cde  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007ce5  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180007cea  lea     edx, [r14-2Ch]; unsigned __int64
0x180007cee  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180007cf3  mov     r9d, 1F0001h; dwDesiredAccess
0x180007cf9  lea     rdx, [rsp+280h+Name]; lpName
0x180007cfe  xor     r8d, r8d; dwFlags
0x180007d01  xor     ecx, ecx; lpMutexAttributes
0x180007d03  call    cs:__imp_CreateMutexExW
0x180007d09  mov     rbx, rax
0x180007d0c  test    rax, rax
0x180007d0f  jnz     short loc_180007D1B
0x180007d11  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007d16  jmp     loc_180007FB4
0x180007d1b  xor     r8d, r8d; bAlertable
0x180007d1e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007d21  mov     rcx, rbx; hHandle
0x180007d24  call    cs:__imp_WaitForSingleObjectEx
0x180007d2a  cmp     eax, 102h
0x180007d2f  jz      short loc_180007D41
0x180007d31  test    eax, 0FFFFFF7Fh
0x180007d36  jnz     loc_180007FFE
0x180007d3c  mov     rdi, rbx
0x180007d3f  jmp     short loc_180007D43
0x180007d41  xor     edi, edi
0x180007d43  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180007d48  mov     [rsp+280h+hObject], 0
0x180007d51  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180007d56  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180007d5b  mov     esi, eax
0x180007d5d  test    eax, eax
0x180007d5f  jns     short loc_180007DE0
0x180007d61  mov     rcx, [rbp+188h]; this
0x180007d68  lea     r8, aWil; "wil"
0x180007d6f  mov     r9d, eax; char *
0x180007d72  mov     edx, 66h ; 'f'; void *
0x180007d77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d7c  mov     rcx, [rbp+188h]; this
0x180007d83  lea     r8, aWil; "wil"
0x180007d8a  mov     r9d, esi; char *
0x180007d8d  mov     edx, 6Fh ; 'o'; void *
0x180007d92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d97  mov     rcx, [rbp+188h]; this
0x180007d9e  lea     r8, aWil; "wil"
0x180007da5  mov     r9d, esi; char *
0x180007da8  mov     edx, 12Eh; void *
0x180007dad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007db2  test    rdi, rdi
0x180007db5  jz      short loc_180007DC8
0x180007db7  mov     rcx, rdi; hMutex
0x180007dba  call    cs:__imp_ReleaseMutex
0x180007dc0  test    eax, eax
0x180007dc2  jz      loc_18000800B
0x180007dc8  mov     rcx, rbx; hObject
0x180007dcb  call    cs:__imp_CloseHandle
0x180007dd1  test    eax, eax
0x180007dd3  jz      loc_18000801D
0x180007dd9  mov     eax, esi
0x180007ddb  jmp     loc_180007FB4
0x180007de0  mov     rax, [rsp+280h+hObject]
0x180007de5  lea     rcx, ds:0[rax*4]
0x180007ded  test    rcx, rcx
0x180007df0  jz      short loc_180007E00
0x180007df2  mov     [r15], rcx
0x180007df5  mov     eax, [rcx]
0x180007df7  inc     eax
0x180007df9  mov     [rcx], eax
0x180007dfb  jmp     loc_180007F8A
0x180007e00  mov     rdx, r14; dwBytes
0x180007e03  mov     qword ptr [r15], 0
0x180007e0a  mov     ecx, 8; dwFlags
0x180007e0f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007e14  mov     r14, rax
0x180007e17  test    rax, rax
0x180007e1a  jnz     short loc_180007E41
0x180007e1c  mov     rcx, [rbp+188h]; this
0x180007e23  lea     r8, aWil; "wil"
0x180007e2a  mov     esi, 8007000Eh
0x180007e2f  mov     edx, 14Bh; void *
0x180007e34  mov     r9d, esi; char *
0x180007e37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e3c  jmp     loc_180007ED3
0x180007e41  xorps   xmm0, xmm0
0x180007e44  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180007e4a  test    r14b, 3
0x180007e4e  jnz     loc_18000802F
0x180007e54  mov     r9, r14
0x180007e57  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180007e5c  shr     r9, 2; unsigned __int64
0x180007e60  lea     rcx, [rsp+280h+hObject]; this
0x180007e65  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180007e6a  mov     esi, eax
0x180007e6c  test    eax, eax
0x180007e6e  jns     loc_180007F1A
0x180007e74  mov     rcx, [rbp+188h]; this
0x180007e7b  lea     r8, aWil; "wil"
0x180007e82  mov     r9d, eax; char *
0x180007e85  mov     edx, 14Eh; void *
0x180007e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e8f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180007e94  test    rcx, rcx
0x180007e97  jz      short loc_180007EA7
0x180007e99  call    cs:__imp_CloseHandle
0x180007e9f  test    eax, eax
0x180007ea1  jz      loc_180008035
0x180007ea7  mov     rcx, [rsp+280h+hObject]; hObject
0x180007eac  test    rcx, rcx
0x180007eaf  jz      short loc_180007EBF
0x180007eb1  call    cs:__imp_CloseHandle
0x180007eb7  test    eax, eax
0x180007eb9  jz      loc_180008047
0x180007ebf  call    cs:__imp_GetProcessHeap
0x180007ec5  mov     r8, r14; lpMem
0x180007ec8  xor     edx, edx; dwFlags
0x180007eca  mov     rcx, rax; hHeap
0x180007ecd  call    cs:__imp_HeapFree
0x180007ed3  mov     rcx, [rbp+188h]; this
0x180007eda  lea     r8, aWil; "wil"
0x180007ee1  mov     r9d, esi; char *
0x180007ee4  mov     edx, 137h; void *
0x180007ee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007eee  test    rdi, rdi
0x180007ef1  jz      short loc_180007F04
0x180007ef3  mov     rcx, rdi; hMutex
0x180007ef6  call    cs:__imp_ReleaseMutex
0x180007efc  test    eax, eax
0x180007efe  jz      loc_180008059
0x180007f04  mov     rcx, rbx; hObject
0x180007f07  call    cs:__imp_CloseHandle
0x180007f0d  test    eax, eax
0x180007f0f  jz      loc_180007FEC
0x180007f15  jmp     loc_180007DD9
0x180007f1a  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180007f1f  lea     rcx, [r14+28h]; void *
0x180007f23  mov     dword ptr [r14], 1
0x180007f2a  xor     edx, edx; Val
0x180007f2c  mov     [r14+8], rbx
0x180007f30  mov     r8d, 108h; Size
0x180007f36  movdqu  xmmword ptr [r14+10h], xmm0
0x180007f3c  call    memset_0
0x180007f41  xor     eax, eax
0x180007f43  lea     rcx, [r14+28h]; this
0x180007f47  mov     [r14+20h], rax
0x180007f4b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007f50  lea     rbx, [r14+0E8h]
0x180007f57  xor     r8d, r8d; Flags
0x180007f5a  mov     rcx, rbx; lpCriticalSection
0x180007f5d  xor     edx, edx; dwSpinCount
0x180007f5f  call    cs:__imp_InitializeCriticalSectionEx
0x180007f65  mov     qword ptr [rbx+28h], 0
0x180007f6d  mov     qword ptr [rbx+30h], 0
0x180007f75  mov     qword ptr [rbx+38h], 0
0x180007f7d  mov     qword ptr [rbx+40h], 0
0x180007f85  xor     ebx, ebx
0x180007f87  mov     [r15], r14
0x180007f8a  test    rdi, rdi
0x180007f8d  jz      short loc_180007FA0
0x180007f8f  mov     rcx, rdi; hMutex
0x180007f92  call    cs:__imp_ReleaseMutex
0x180007f98  test    eax, eax
0x180007f9a  jz      loc_18000806B
0x180007fa0  test    rbx, rbx
0x180007fa3  jz      short loc_180007FB2
0x180007fa5  mov     rcx, rbx; hObject
0x180007fa8  call    cs:__imp_CloseHandle
0x180007fae  test    eax, eax
0x180007fb0  jz      short loc_180007FDA
0x180007fb2  xor     eax, eax
0x180007fb4  mov     rcx, [rbp+180h+var_30]
0x180007fbb  xor     rcx, rsp; StackCookie
0x180007fbe  call    __security_check_cookie
0x180007fc3  mov     rbx, [rsp+280h+arg_10]
0x180007fcb  add     rsp, 260h
0x180007fd2  pop     r15
0x180007fd4  pop     r14
0x180007fd6  pop     rdi
0x180007fd7  pop     rsi
0x180007fd8  pop     rbp
0x180007fd9  retn
0x180007fda  mov     rcx, [rbp+188h]; this
0x180007fe1  mov     edx, 0A0Bh; void *
0x180007fe6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007fec  mov     rcx, [rbp+188h]; this
0x180007ff3  mov     edx, 0A0Bh; void *
0x180007ff8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007ffe  mov     rcx, [rbp+188h]; this
0x180008005  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000800b  mov     rcx, [rbp+188h]; this
0x180008012  mov     edx, 0A15h; void *
0x180008017  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000801d  mov     rcx, [rbp+188h]; this
0x180008024  mov     edx, 0A0Bh; void *
0x180008029  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000802f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008035  mov     rcx, [rbp+188h]; this
0x18000803c  mov     edx, 0A0Bh; void *
0x180008041  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008047  mov     rcx, [rbp+188h]; this
0x18000804e  mov     edx, 0A0Bh; void *
0x180008053  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008059  mov     rcx, [rbp+188h]; this
0x180008060  mov     edx, 0A15h; void *
0x180008065  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000806b  mov     rcx, [rbp+188h]; this
0x180008072  mov     edx, 0A15h; void *
0x180008077  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
