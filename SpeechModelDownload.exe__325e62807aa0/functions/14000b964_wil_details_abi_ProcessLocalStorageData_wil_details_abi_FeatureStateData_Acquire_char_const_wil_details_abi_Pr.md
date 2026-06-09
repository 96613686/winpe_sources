# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000b964`
- end: `0x14000bd55`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14000e684`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x1400059c4`
- `0x140006120`
- `0x140006898`
- `0x14000770c`
- `0x140007dc8`
- `0x140008e98`
- `0x140008f5c`
- `0x1400093e8`
- `0x1400093f8`
- `0x14000b050`
- `0x14000b964`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000b9fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000b9fc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000b9db`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000b9db`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000bc37`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000bc37`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ba92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000bbce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000bc6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ba92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000bbce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000bc6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bb97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bb97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bba5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000b99d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000b99d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000baa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bbdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000baa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bbdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc80`

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
0x14000b964  mov     [rsp-8+arg_10], rbx
0x14000b969  push    rbp
0x14000b96a  push    rsi
0x14000b96b  push    rdi
0x14000b96c  push    r14
0x14000b96e  push    r15
0x14000b970  lea     rbp, [rsp-160h]
0x14000b978  sub     rsp, 260h
0x14000b97f  mov     rax, cs:__security_cookie
0x14000b986  xor     rax, rsp
0x14000b989  mov     [rbp+180h+var_30], rax
0x14000b990  mov     r15, rdx
0x14000b993  mov     qword ptr [rdx], 0
0x14000b99a  mov     rbx, rcx
0x14000b99d  call    cs:__imp_GetCurrentProcessId
0x14000b9a3  mov     r14d, 130h
0x14000b9a9  mov     [rsp+280h+var_258], rbx
0x14000b9ae  mov     r9d, eax
0x14000b9b1  mov     [rsp+280h+var_260], r14d; int
0x14000b9b6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000b9bd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000b9c2  lea     edx, [r14-2Ch]; unsigned __int64
0x14000b9c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b9cb  mov     r9d, 1F0001h; dwDesiredAccess
0x14000b9d1  lea     rdx, [rsp+280h+Name]; lpName
0x14000b9d6  xor     r8d, r8d; dwFlags
0x14000b9d9  xor     ecx, ecx; lpMutexAttributes
0x14000b9db  call    cs:__imp_CreateMutexExW
0x14000b9e1  mov     rbx, rax
0x14000b9e4  test    rax, rax
0x14000b9e7  jnz     short loc_14000B9F3
0x14000b9e9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000b9ee  jmp     loc_14000BC8C
0x14000b9f3  xor     r8d, r8d; bAlertable
0x14000b9f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000b9f9  mov     rcx, rbx; hHandle
0x14000b9fc  call    cs:__imp_WaitForSingleObjectEx
0x14000ba02  cmp     eax, 102h
0x14000ba07  jz      short loc_14000BA19
0x14000ba09  test    eax, 0FFFFFF7Fh
0x14000ba0e  jnz     loc_14000BCD6
0x14000ba14  mov     rdi, rbx
0x14000ba17  jmp     short loc_14000BA1B
0x14000ba19  xor     edi, edi
0x14000ba1b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14000ba20  mov     [rsp+280h+hObject], 0
0x14000ba29  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000ba2e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000ba33  mov     esi, eax
0x14000ba35  test    eax, eax
0x14000ba37  jns     short loc_14000BAB8
0x14000ba39  mov     rcx, [rbp+188h]; this
0x14000ba40  lea     r8, aWil; "wil"
0x14000ba47  mov     r9d, eax; char *
0x14000ba4a  mov     edx, 66h ; 'f'; void *
0x14000ba4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ba54  mov     rcx, [rbp+188h]; this
0x14000ba5b  lea     r8, aWil; "wil"
0x14000ba62  mov     r9d, esi; char *
0x14000ba65  mov     edx, 6Fh ; 'o'; void *
0x14000ba6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ba6f  mov     rcx, [rbp+188h]; this
0x14000ba76  lea     r8, aWil; "wil"
0x14000ba7d  mov     r9d, esi; char *
0x14000ba80  mov     edx, 12Eh; void *
0x14000ba85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ba8a  test    rdi, rdi
0x14000ba8d  jz      short loc_14000BAA0
0x14000ba8f  mov     rcx, rdi; hMutex
0x14000ba92  call    cs:__imp_ReleaseMutex
0x14000ba98  test    eax, eax
0x14000ba9a  jz      loc_14000BCE3
0x14000baa0  mov     rcx, rbx; hObject
0x14000baa3  call    cs:__imp_CloseHandle
0x14000baa9  test    eax, eax
0x14000baab  jz      loc_14000BCF5
0x14000bab1  mov     eax, esi
0x14000bab3  jmp     loc_14000BC8C
0x14000bab8  mov     rax, [rsp+280h+hObject]
0x14000babd  lea     rcx, ds:0[rax*4]
0x14000bac5  test    rcx, rcx
0x14000bac8  jz      short loc_14000BAD8
0x14000baca  mov     [r15], rcx
0x14000bacd  mov     eax, [rcx]
0x14000bacf  inc     eax
0x14000bad1  mov     [rcx], eax
0x14000bad3  jmp     loc_14000BC62
0x14000bad8  mov     rdx, r14; dwBytes
0x14000badb  mov     qword ptr [r15], 0
0x14000bae2  mov     ecx, 8; dwFlags
0x14000bae7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000baec  mov     r14, rax
0x14000baef  test    rax, rax
0x14000baf2  jnz     short loc_14000BB19
0x14000baf4  mov     rcx, [rbp+188h]; this
0x14000bafb  lea     r8, aWil; "wil"
0x14000bb02  mov     esi, 8007000Eh
0x14000bb07  mov     edx, 14Bh; void *
0x14000bb0c  mov     r9d, esi; char *
0x14000bb0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bb14  jmp     loc_14000BBAB
0x14000bb19  xorps   xmm0, xmm0
0x14000bb1c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000bb22  test    r14b, 3
0x14000bb26  jnz     loc_14000BD07
0x14000bb2c  mov     r9, r14
0x14000bb2f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000bb34  shr     r9, 2; unsigned __int64
0x14000bb38  lea     rcx, [rsp+280h+hObject]; this
0x14000bb3d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000bb42  mov     esi, eax
0x14000bb44  test    eax, eax
0x14000bb46  jns     loc_14000BBF2
0x14000bb4c  mov     rcx, [rbp+188h]; this
0x14000bb53  lea     r8, aWil; "wil"
0x14000bb5a  mov     r9d, eax; char *
0x14000bb5d  mov     edx, 14Eh; void *
0x14000bb62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bb67  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14000bb6c  test    rcx, rcx
0x14000bb6f  jz      short loc_14000BB7F
0x14000bb71  call    cs:__imp_CloseHandle
0x14000bb77  test    eax, eax
0x14000bb79  jz      loc_14000BD0D
0x14000bb7f  mov     rcx, [rsp+280h+hObject]; hObject
0x14000bb84  test    rcx, rcx
0x14000bb87  jz      short loc_14000BB97
0x14000bb89  call    cs:__imp_CloseHandle
0x14000bb8f  test    eax, eax
0x14000bb91  jz      loc_14000BD1F
0x14000bb97  call    cs:__imp_GetProcessHeap
0x14000bb9d  mov     r8, r14; lpMem
0x14000bba0  xor     edx, edx; dwFlags
0x14000bba2  mov     rcx, rax; hHeap
0x14000bba5  call    cs:__imp_HeapFree
0x14000bbab  mov     rcx, [rbp+188h]; this
0x14000bbb2  lea     r8, aWil; "wil"
0x14000bbb9  mov     r9d, esi; char *
0x14000bbbc  mov     edx, 137h; void *
0x14000bbc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bbc6  test    rdi, rdi
0x14000bbc9  jz      short loc_14000BBDC
0x14000bbcb  mov     rcx, rdi; hMutex
0x14000bbce  call    cs:__imp_ReleaseMutex
0x14000bbd4  test    eax, eax
0x14000bbd6  jz      loc_14000BD31
0x14000bbdc  mov     rcx, rbx; hObject
0x14000bbdf  call    cs:__imp_CloseHandle
0x14000bbe5  test    eax, eax
0x14000bbe7  jz      loc_14000BCC4
0x14000bbed  jmp     loc_14000BAB1
0x14000bbf2  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000bbf7  lea     rcx, [r14+28h]; void *
0x14000bbfb  mov     dword ptr [r14], 1
0x14000bc02  xor     edx, edx; Val
0x14000bc04  mov     [r14+8], rbx
0x14000bc08  mov     r8d, 108h; Size
0x14000bc0e  movdqu  xmmword ptr [r14+10h], xmm0
0x14000bc14  call    memset_0
0x14000bc19  xor     eax, eax
0x14000bc1b  lea     rcx, [r14+28h]; this
0x14000bc1f  mov     [r14+20h], rax
0x14000bc23  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000bc28  lea     rbx, [r14+0E8h]
0x14000bc2f  xor     r8d, r8d; Flags
0x14000bc32  mov     rcx, rbx; lpCriticalSection
0x14000bc35  xor     edx, edx; dwSpinCount
0x14000bc37  call    cs:__imp_InitializeCriticalSectionEx
0x14000bc3d  mov     qword ptr [rbx+28h], 0
0x14000bc45  mov     qword ptr [rbx+30h], 0
0x14000bc4d  mov     qword ptr [rbx+38h], 0
0x14000bc55  mov     qword ptr [rbx+40h], 0
0x14000bc5d  xor     ebx, ebx
0x14000bc5f  mov     [r15], r14
0x14000bc62  test    rdi, rdi
0x14000bc65  jz      short loc_14000BC78
0x14000bc67  mov     rcx, rdi; hMutex
0x14000bc6a  call    cs:__imp_ReleaseMutex
0x14000bc70  test    eax, eax
0x14000bc72  jz      loc_14000BD43
0x14000bc78  test    rbx, rbx
0x14000bc7b  jz      short loc_14000BC8A
0x14000bc7d  mov     rcx, rbx; hObject
0x14000bc80  call    cs:__imp_CloseHandle
0x14000bc86  test    eax, eax
0x14000bc88  jz      short loc_14000BCB2
0x14000bc8a  xor     eax, eax
0x14000bc8c  mov     rcx, [rbp+180h+var_30]
0x14000bc93  xor     rcx, rsp; StackCookie
0x14000bc96  call    __security_check_cookie
0x14000bc9b  mov     rbx, [rsp+280h+arg_10]
0x14000bca3  add     rsp, 260h
0x14000bcaa  pop     r15
0x14000bcac  pop     r14
0x14000bcae  pop     rdi
0x14000bcaf  pop     rsi
0x14000bcb0  pop     rbp
0x14000bcb1  retn
0x14000bcb2  mov     rcx, [rbp+188h]; this
0x14000bcb9  mov     edx, 0A0Bh; void *
0x14000bcbe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bcc4  mov     rcx, [rbp+188h]; this
0x14000bccb  mov     edx, 0A0Bh; void *
0x14000bcd0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bcd6  mov     rcx, [rbp+188h]; this
0x14000bcdd  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000bce3  mov     rcx, [rbp+188h]; this
0x14000bcea  mov     edx, 0A15h; void *
0x14000bcef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bcf5  mov     rcx, [rbp+188h]; this
0x14000bcfc  mov     edx, 0A0Bh; void *
0x14000bd01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bd07  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000bd0d  mov     rcx, [rbp+188h]; this
0x14000bd14  mov     edx, 0A0Bh; void *
0x14000bd19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bd1f  mov     rcx, [rbp+188h]; this
0x14000bd26  mov     edx, 0A0Bh; void *
0x14000bd2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bd31  mov     rcx, [rbp+188h]; this
0x14000bd38  mov     edx, 0A15h; void *
0x14000bd3d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bd43  mov     rcx, [rbp+188h]; this
0x14000bd4a  mov     edx, 0A15h; void *
0x14000bd4f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
