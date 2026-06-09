# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000936c`
- end: `0x14000975d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140009a38`

## callees

- `0x1400023d0`
- `0x140002fcc`
- `0x140004664`
- `0x140006008`
- `0x140008654`
- `0x14000936c`
- `0x140009764`
- `0x140009bc8`
- `0x14000a628`
- `0x14000ac10`
- `0x14000c188`
- `0x14000c81c`
- `0x14000db34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000959f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000959f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400095ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400095ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400093a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400093a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400094ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400095e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400094ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400095e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009688`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009404`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009404`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000949a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400095d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009672`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000949a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400095d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009672`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000963f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000963f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400093e3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400093e3`

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
  wil::details::in1diag4 *v22; // rcx
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
    wil::details::in1diag4::_FailFastImmediate_Unexpected(v22);
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
0x14000936c  mov     [rsp-8+arg_10], rbx
0x140009371  push    rbp
0x140009372  push    rsi
0x140009373  push    rdi
0x140009374  push    r14
0x140009376  push    r15
0x140009378  lea     rbp, [rsp-160h]
0x140009380  sub     rsp, 260h
0x140009387  mov     rax, cs:__security_cookie
0x14000938e  xor     rax, rsp
0x140009391  mov     [rbp+180h+var_30], rax
0x140009398  mov     r15, rdx
0x14000939b  mov     qword ptr [rdx], 0
0x1400093a2  mov     rbx, rcx
0x1400093a5  call    cs:__imp_GetCurrentProcessId
0x1400093ab  mov     r14d, 130h
0x1400093b1  mov     [rsp+280h+var_258], rbx
0x1400093b6  mov     r9d, eax
0x1400093b9  mov     [rsp+280h+var_260], r14d; int
0x1400093be  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400093c5  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1400093ca  lea     edx, [r14-2Ch]; unsigned __int64
0x1400093ce  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400093d3  mov     r9d, 1F0001h; dwDesiredAccess
0x1400093d9  lea     rdx, [rsp+280h+Name]; lpName
0x1400093de  xor     r8d, r8d; dwFlags
0x1400093e1  xor     ecx, ecx; lpMutexAttributes
0x1400093e3  call    cs:__imp_CreateMutexExW
0x1400093e9  mov     rbx, rax
0x1400093ec  test    rax, rax
0x1400093ef  jnz     short loc_1400093FB
0x1400093f1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400093f6  jmp     loc_140009694
0x1400093fb  xor     r8d, r8d; bAlertable
0x1400093fe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140009401  mov     rcx, rbx; hHandle
0x140009404  call    cs:__imp_WaitForSingleObjectEx
0x14000940a  cmp     eax, 102h
0x14000940f  jz      short loc_140009421
0x140009411  test    eax, 0FFFFFF7Fh
0x140009416  jnz     loc_1400096DE
0x14000941c  mov     rdi, rbx
0x14000941f  jmp     short loc_140009423
0x140009421  xor     edi, edi
0x140009423  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140009428  mov     [rsp+280h+hObject], 0
0x140009431  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140009436  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x14000943b  mov     esi, eax
0x14000943d  test    eax, eax
0x14000943f  jns     short loc_1400094C0
0x140009441  mov     rcx, [rbp+188h]; this
0x140009448  lea     r8, aWil; "wil"
0x14000944f  mov     r9d, eax; char *
0x140009452  mov     edx, 66h ; 'f'; void *
0x140009457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000945c  mov     rcx, [rbp+188h]; this
0x140009463  lea     r8, aWil; "wil"
0x14000946a  mov     r9d, esi; char *
0x14000946d  mov     edx, 6Fh ; 'o'; void *
0x140009472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009477  mov     rcx, [rbp+188h]; this
0x14000947e  lea     r8, aWil; "wil"
0x140009485  mov     r9d, esi; char *
0x140009488  mov     edx, 12Eh; void *
0x14000948d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009492  test    rdi, rdi
0x140009495  jz      short loc_1400094A8
0x140009497  mov     rcx, rdi; hMutex
0x14000949a  call    cs:__imp_ReleaseMutex
0x1400094a0  test    eax, eax
0x1400094a2  jz      loc_1400096EB
0x1400094a8  mov     rcx, rbx; hObject
0x1400094ab  call    cs:__imp_CloseHandle
0x1400094b1  test    eax, eax
0x1400094b3  jz      loc_1400096FD
0x1400094b9  mov     eax, esi
0x1400094bb  jmp     loc_140009694
0x1400094c0  mov     rax, [rsp+280h+hObject]
0x1400094c5  lea     rcx, ds:0[rax*4]
0x1400094cd  test    rcx, rcx
0x1400094d0  jz      short loc_1400094E0
0x1400094d2  mov     [r15], rcx
0x1400094d5  mov     eax, [rcx]
0x1400094d7  inc     eax
0x1400094d9  mov     [rcx], eax
0x1400094db  jmp     loc_14000966A
0x1400094e0  mov     rdx, r14; dwBytes
0x1400094e3  mov     qword ptr [r15], 0
0x1400094ea  mov     ecx, 8; dwFlags
0x1400094ef  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400094f4  mov     r14, rax
0x1400094f7  test    rax, rax
0x1400094fa  jnz     short loc_140009521
0x1400094fc  mov     rcx, [rbp+188h]; this
0x140009503  lea     r8, aWil; "wil"
0x14000950a  mov     esi, 8007000Eh
0x14000950f  mov     edx, 14Bh; void *
0x140009514  mov     r9d, esi; char *
0x140009517  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000951c  jmp     loc_1400095B3
0x140009521  xorps   xmm0, xmm0
0x140009524  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000952a  test    r14b, 3
0x14000952e  jnz     loc_14000970F
0x140009534  mov     r9, r14
0x140009537  lea     rdx, [rsp+280h+Name]; wchar_t *
0x14000953c  shr     r9, 2; unsigned __int64
0x140009540  lea     rcx, [rsp+280h+hObject]; this
0x140009545  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x14000954a  mov     esi, eax
0x14000954c  test    eax, eax
0x14000954e  jns     loc_1400095FA
0x140009554  mov     rcx, [rbp+188h]; this
0x14000955b  lea     r8, aWil; "wil"
0x140009562  mov     r9d, eax; char *
0x140009565  mov     edx, 14Eh; void *
0x14000956a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000956f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140009574  test    rcx, rcx
0x140009577  jz      short loc_140009587
0x140009579  call    cs:__imp_CloseHandle
0x14000957f  test    eax, eax
0x140009581  jz      loc_140009715
0x140009587  mov     rcx, [rsp+280h+hObject]; hObject
0x14000958c  test    rcx, rcx
0x14000958f  jz      short loc_14000959F
0x140009591  call    cs:__imp_CloseHandle
0x140009597  test    eax, eax
0x140009599  jz      loc_140009727
0x14000959f  call    cs:__imp_GetProcessHeap
0x1400095a5  mov     r8, r14; lpMem
0x1400095a8  xor     edx, edx; dwFlags
0x1400095aa  mov     rcx, rax; hHeap
0x1400095ad  call    cs:__imp_HeapFree
0x1400095b3  mov     rcx, [rbp+188h]; this
0x1400095ba  lea     r8, aWil; "wil"
0x1400095c1  mov     r9d, esi; char *
0x1400095c4  mov     edx, 137h; void *
0x1400095c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400095ce  test    rdi, rdi
0x1400095d1  jz      short loc_1400095E4
0x1400095d3  mov     rcx, rdi; hMutex
0x1400095d6  call    cs:__imp_ReleaseMutex
0x1400095dc  test    eax, eax
0x1400095de  jz      loc_140009739
0x1400095e4  mov     rcx, rbx; hObject
0x1400095e7  call    cs:__imp_CloseHandle
0x1400095ed  test    eax, eax
0x1400095ef  jz      loc_1400096CC
0x1400095f5  jmp     loc_1400094B9
0x1400095fa  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400095ff  lea     rcx, [r14+28h]; void *
0x140009603  mov     dword ptr [r14], 1
0x14000960a  xor     edx, edx; Val
0x14000960c  mov     [r14+8], rbx
0x140009610  mov     r8d, 108h; Size
0x140009616  movdqu  xmmword ptr [r14+10h], xmm0
0x14000961c  call    memset_0
0x140009621  xor     eax, eax
0x140009623  lea     rcx, [r14+28h]; this
0x140009627  mov     [r14+20h], rax
0x14000962b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140009630  lea     rbx, [r14+0E8h]
0x140009637  xor     r8d, r8d; Flags
0x14000963a  mov     rcx, rbx; lpCriticalSection
0x14000963d  xor     edx, edx; dwSpinCount
0x14000963f  call    cs:__imp_InitializeCriticalSectionEx
0x140009645  mov     qword ptr [rbx+28h], 0
0x14000964d  mov     qword ptr [rbx+30h], 0
0x140009655  mov     qword ptr [rbx+38h], 0
0x14000965d  mov     qword ptr [rbx+40h], 0
0x140009665  xor     ebx, ebx
0x140009667  mov     [r15], r14
0x14000966a  test    rdi, rdi
0x14000966d  jz      short loc_140009680
0x14000966f  mov     rcx, rdi; hMutex
0x140009672  call    cs:__imp_ReleaseMutex
0x140009678  test    eax, eax
0x14000967a  jz      loc_14000974B
0x140009680  test    rbx, rbx
0x140009683  jz      short loc_140009692
0x140009685  mov     rcx, rbx; hObject
0x140009688  call    cs:__imp_CloseHandle
0x14000968e  test    eax, eax
0x140009690  jz      short loc_1400096BA
0x140009692  xor     eax, eax
0x140009694  mov     rcx, [rbp+180h+var_30]
0x14000969b  xor     rcx, rsp; StackCookie
0x14000969e  call    __security_check_cookie
0x1400096a3  mov     rbx, [rsp+280h+arg_10]
0x1400096ab  add     rsp, 260h
0x1400096b2  pop     r15
0x1400096b4  pop     r14
0x1400096b6  pop     rdi
0x1400096b7  pop     rsi
0x1400096b8  pop     rbp
0x1400096b9  retn
0x1400096ba  mov     rcx, [rbp+188h]; this
0x1400096c1  mov     edx, 0A0Bh; void *
0x1400096c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400096cc  mov     rcx, [rbp+188h]; this
0x1400096d3  mov     edx, 0A0Bh; void *
0x1400096d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400096de  mov     rcx, [rbp+188h]; this
0x1400096e5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400096eb  mov     rcx, [rbp+188h]; this
0x1400096f2  mov     edx, 0A15h; void *
0x1400096f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400096fd  mov     rcx, [rbp+188h]; this
0x140009704  mov     edx, 0A0Bh; void *
0x140009709  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000970f  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
0x140009715  mov     rcx, [rbp+188h]; this
0x14000971c  mov     edx, 0A0Bh; void *
0x140009721  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009727  mov     rcx, [rbp+188h]; this
0x14000972e  mov     edx, 0A0Bh; void *
0x140009733  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009739  mov     rcx, [rbp+188h]; this
0x140009740  mov     edx, 0A15h; void *
0x140009745  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000974b  mov     rcx, [rbp+188h]; this
0x140009752  mov     edx, 0A15h; void *
0x140009757  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
