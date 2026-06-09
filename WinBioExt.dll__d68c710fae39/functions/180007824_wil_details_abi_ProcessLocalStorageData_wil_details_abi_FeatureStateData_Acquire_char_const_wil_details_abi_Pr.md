# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007824`
- end: `0x180007bf7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180007c00`

## callees

- `0x180001610`
- `0x180002084`
- `0x180003518`
- `0x1800037e4`
- `0x180003e28`
- `0x1800048f8`
- `0x180004cf4`
- `0x1800056e4`
- `0x18000579c`
- `0x180005b4c`
- `0x180005b5c`
- `0x1800071c8`
- `0x180007824`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000793d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007a64`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007b00`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000793d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007a64`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007b00`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007acd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180007acd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000789b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000789b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800078bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800078bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000785d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000785d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000794e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000794e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b16`

## string_xrefs

- `0x180007b73`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      wil::details::in1diag3::_FailFast_Unexpected(
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
0x180007824  mov     [rsp-8+arg_10], rbx
0x180007829  push    rbp
0x18000782a  push    rsi
0x18000782b  push    rdi
0x18000782c  push    r14
0x18000782e  push    r15
0x180007830  lea     rbp, [rsp-160h]
0x180007838  sub     rsp, 260h
0x18000783f  mov     rax, cs:__security_cookie
0x180007846  xor     rax, rsp
0x180007849  mov     [rbp+180h+var_30], rax
0x180007850  mov     r15, rdx
0x180007853  mov     qword ptr [rdx], 0
0x18000785a  mov     rbx, rcx
0x18000785d  call    cs:__imp_GetCurrentProcessId
0x180007863  mov     r14d, 130h
0x180007869  mov     [rsp+280h+var_258], rbx
0x18000786e  mov     r9d, eax
0x180007871  mov     [rsp+280h+var_260], r14d; int
0x180007876  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000787d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007882  lea     edx, [r14-2Ch]; unsigned __int64
0x180007886  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000788b  mov     r9d, 1F0001h; dwDesiredAccess
0x180007891  lea     rdx, [rsp+280h+Name]; lpName
0x180007896  xor     r8d, r8d; dwFlags
0x180007899  xor     ecx, ecx; lpMutexAttributes
0x18000789b  call    cs:__imp_CreateMutexExW
0x1800078a1  mov     rbx, rax
0x1800078a4  test    rax, rax
0x1800078a7  jnz     short loc_1800078B3
0x1800078a9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800078ae  jmp     loc_180007B22
0x1800078b3  xor     r8d, r8d; bAlertable
0x1800078b6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800078b9  mov     rcx, rbx; hHandle
0x1800078bc  call    cs:__imp_WaitForSingleObjectEx
0x1800078c2  cmp     eax, 102h
0x1800078c7  jz      short loc_1800078D9
0x1800078c9  test    eax, 0FFFFFF7Fh
0x1800078ce  jnz     loc_180007B6C
0x1800078d4  mov     rdi, rbx
0x1800078d7  jmp     short loc_1800078DB
0x1800078d9  xor     edi, edi
0x1800078db  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800078e0  mov     [rsp+280h+hObject], 0
0x1800078e9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800078ee  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800078f3  mov     esi, eax
0x1800078f5  test    eax, eax
0x1800078f7  jns     short loc_180007963
0x1800078f9  mov     rcx, [rbp+188h]; this
0x180007900  mov     r9d, eax; char *
0x180007903  mov     edx, 66h ; 'f'; void *
0x180007908  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000790d  mov     rcx, [rbp+188h]; this
0x180007914  mov     r9d, esi; char *
0x180007917  mov     edx, 6Fh ; 'o'; void *
0x18000791c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007921  mov     rcx, [rbp+188h]; this
0x180007928  mov     r9d, esi; char *
0x18000792b  mov     edx, 12Eh; void *
0x180007930  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007935  test    rdi, rdi
0x180007938  jz      short loc_18000794B
0x18000793a  mov     rcx, rdi; hMutex
0x18000793d  call    cs:__imp_ReleaseMutex
0x180007943  test    eax, eax
0x180007945  jz      loc_180007B85
0x18000794b  mov     rcx, rbx; hObject
0x18000794e  call    cs:__imp_CloseHandle
0x180007954  test    eax, eax
0x180007956  jz      loc_180007B97
0x18000795c  mov     eax, esi
0x18000795e  jmp     loc_180007B22
0x180007963  mov     rax, [rsp+280h+hObject]
0x180007968  lea     rcx, ds:0[rax*4]
0x180007970  test    rcx, rcx
0x180007973  jz      short loc_180007983
0x180007975  mov     [r15], rcx
0x180007978  mov     eax, [rcx]
0x18000797a  inc     eax
0x18000797c  mov     [rcx], eax
0x18000797e  jmp     loc_180007AF8
0x180007983  mov     rdx, r14; dwBytes
0x180007986  mov     qword ptr [r15], 0
0x18000798d  mov     ecx, 8; dwFlags
0x180007992  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007997  mov     r14, rax
0x18000799a  test    rax, rax
0x18000799d  jnz     short loc_1800079BD
0x18000799f  mov     rcx, [rbp+188h]; this
0x1800079a6  mov     esi, 8007000Eh
0x1800079ab  mov     r9d, esi; char *
0x1800079ae  mov     edx, 14Bh; void *
0x1800079b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800079b8  jmp     loc_180007A48
0x1800079bd  xorps   xmm0, xmm0
0x1800079c0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800079c6  test    r14b, 3
0x1800079ca  jnz     loc_180007BA9
0x1800079d0  mov     r9, r14
0x1800079d3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800079d8  shr     r9, 2; unsigned __int64
0x1800079dc  lea     rcx, [rsp+280h+hObject]; this
0x1800079e1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800079e6  mov     esi, eax
0x1800079e8  test    eax, eax
0x1800079ea  jns     loc_180007A88
0x1800079f0  mov     rcx, [rbp+188h]; this
0x1800079f7  mov     r9d, eax; char *
0x1800079fa  mov     edx, 14Eh; void *
0x1800079ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a04  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180007a09  test    rcx, rcx
0x180007a0c  jz      short loc_180007A1C
0x180007a0e  call    cs:__imp_CloseHandle
0x180007a14  test    eax, eax
0x180007a16  jz      loc_180007BAF
0x180007a1c  mov     rcx, [rsp+280h+hObject]; hObject
0x180007a21  test    rcx, rcx
0x180007a24  jz      short loc_180007A34
0x180007a26  call    cs:__imp_CloseHandle
0x180007a2c  test    eax, eax
0x180007a2e  jz      loc_180007BC1
0x180007a34  call    cs:__imp_GetProcessHeap
0x180007a3a  mov     r8, r14; lpMem
0x180007a3d  xor     edx, edx; dwFlags
0x180007a3f  mov     rcx, rax; hHeap
0x180007a42  call    cs:__imp_HeapFree
0x180007a48  mov     rcx, [rbp+188h]; this
0x180007a4f  mov     r9d, esi; char *
0x180007a52  mov     edx, 137h; void *
0x180007a57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a5c  test    rdi, rdi
0x180007a5f  jz      short loc_180007A72
0x180007a61  mov     rcx, rdi; hMutex
0x180007a64  call    cs:__imp_ReleaseMutex
0x180007a6a  test    eax, eax
0x180007a6c  jz      loc_180007BD3
0x180007a72  mov     rcx, rbx; hObject
0x180007a75  call    cs:__imp_CloseHandle
0x180007a7b  test    eax, eax
0x180007a7d  jz      loc_180007B5A
0x180007a83  jmp     loc_18000795C
0x180007a88  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180007a8d  lea     rcx, [r14+28h]; void *
0x180007a91  mov     dword ptr [r14], 1
0x180007a98  xor     edx, edx; Val
0x180007a9a  mov     [r14+8], rbx
0x180007a9e  mov     r8d, 108h; Size
0x180007aa4  movdqu  xmmword ptr [r14+10h], xmm0
0x180007aaa  call    memset_0
0x180007aaf  xor     eax, eax
0x180007ab1  lea     rcx, [r14+28h]; this
0x180007ab5  mov     [r14+20h], rax
0x180007ab9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007abe  lea     rbx, [r14+0E8h]
0x180007ac5  xor     r8d, r8d; Flags
0x180007ac8  mov     rcx, rbx; lpCriticalSection
0x180007acb  xor     edx, edx; dwSpinCount
0x180007acd  call    cs:__imp_InitializeCriticalSectionEx
0x180007ad3  mov     qword ptr [rbx+28h], 0
0x180007adb  mov     qword ptr [rbx+30h], 0
0x180007ae3  mov     qword ptr [rbx+38h], 0
0x180007aeb  mov     qword ptr [rbx+40h], 0
0x180007af3  xor     ebx, ebx
0x180007af5  mov     [r15], r14
0x180007af8  test    rdi, rdi
0x180007afb  jz      short loc_180007B0E
0x180007afd  mov     rcx, rdi; hMutex
0x180007b00  call    cs:__imp_ReleaseMutex
0x180007b06  test    eax, eax
0x180007b08  jz      loc_180007BE5
0x180007b0e  test    rbx, rbx
0x180007b11  jz      short loc_180007B20
0x180007b13  mov     rcx, rbx; hObject
0x180007b16  call    cs:__imp_CloseHandle
0x180007b1c  test    eax, eax
0x180007b1e  jz      short loc_180007B48
0x180007b20  xor     eax, eax
0x180007b22  mov     rcx, [rbp+180h+var_30]
0x180007b29  xor     rcx, rsp; StackCookie
0x180007b2c  call    __security_check_cookie
0x180007b31  mov     rbx, [rsp+280h+arg_10]
0x180007b39  add     rsp, 260h
0x180007b40  pop     r15
0x180007b42  pop     r14
0x180007b44  pop     rdi
0x180007b45  pop     rsi
0x180007b46  pop     rbp
0x180007b47  retn
0x180007b48  mov     rcx, [rbp+188h]; this
0x180007b4f  mov     edx, 0A0Bh; void *
0x180007b54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007b5a  mov     rcx, [rbp+188h]; this
0x180007b61  mov     edx, 0A0Bh; void *
0x180007b66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007b6c  mov     rcx, [rbp+188h]; this
0x180007b73  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007b7a  mov     edx, 0E01h; void *
0x180007b7f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180007b85  mov     rcx, [rbp+188h]; this
0x180007b8c  mov     edx, 0A15h; void *
0x180007b91  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007b97  mov     rcx, [rbp+188h]; this
0x180007b9e  mov     edx, 0A0Bh; void *
0x180007ba3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007ba9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007baf  mov     rcx, [rbp+188h]; this
0x180007bb6  mov     edx, 0A0Bh; void *
0x180007bbb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007bc1  mov     rcx, [rbp+188h]; this
0x180007bc8  mov     edx, 0A0Bh; void *
0x180007bcd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007bd3  mov     rcx, [rbp+188h]; this
0x180007bda  mov     edx, 0A15h; void *
0x180007bdf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007be5  mov     rcx, [rbp+188h]; this
0x180007bec  mov     edx, 0A15h; void *
0x180007bf1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
