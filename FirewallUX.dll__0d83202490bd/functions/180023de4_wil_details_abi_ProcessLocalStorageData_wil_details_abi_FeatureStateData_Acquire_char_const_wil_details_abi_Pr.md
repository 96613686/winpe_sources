# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180023de4`
- end: `0x1800241d5`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800241dc`

## callees

- `0x1800021c0`
- `0x180002c04`
- `0x1800065d4`
- `0x180006d04`
- `0x1800076b8`
- `0x18000877c`
- `0x180009544`
- `0x18000a368`
- `0x18000a44c`
- `0x18000a938`
- `0x18000a948`
- `0x1800237c4`
- `0x180023de4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023e5b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023e5b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800240b7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800240b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180023f12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002404e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800240ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180023f12`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002404e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800240ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180023e7c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180023e7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024017`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024017`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024025`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024025`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023e1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023e1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ff1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002405f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024100`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ff1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002405f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024100`

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
0x180023de4  mov     [rsp-8+arg_10], rbx
0x180023de9  push    rbp
0x180023dea  push    rsi
0x180023deb  push    rdi
0x180023dec  push    r14
0x180023dee  push    r15
0x180023df0  lea     rbp, [rsp-160h]
0x180023df8  sub     rsp, 260h
0x180023dff  mov     rax, cs:__security_cookie
0x180023e06  xor     rax, rsp
0x180023e09  mov     [rbp+180h+var_30], rax
0x180023e10  mov     r15, rdx
0x180023e13  mov     qword ptr [rdx], 0
0x180023e1a  mov     rbx, rcx
0x180023e1d  call    cs:__imp_GetCurrentProcessId
0x180023e23  mov     r14d, 130h
0x180023e29  mov     [rsp+280h+var_258], rbx
0x180023e2e  mov     r9d, eax
0x180023e31  mov     [rsp+280h+var_260], r14d; int
0x180023e36  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180023e3d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180023e42  lea     edx, [r14-2Ch]; unsigned __int64
0x180023e46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023e4b  mov     r9d, 1F0001h; dwDesiredAccess
0x180023e51  lea     rdx, [rsp+280h+Name]; lpName
0x180023e56  xor     r8d, r8d; dwFlags
0x180023e59  xor     ecx, ecx; lpMutexAttributes
0x180023e5b  call    cs:__imp_CreateMutexExW
0x180023e61  mov     rbx, rax
0x180023e64  test    rax, rax
0x180023e67  jnz     short loc_180023E73
0x180023e69  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023e6e  jmp     loc_18002410C
0x180023e73  xor     r8d, r8d; bAlertable
0x180023e76  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023e79  mov     rcx, rbx; hHandle
0x180023e7c  call    cs:__imp_WaitForSingleObjectEx
0x180023e82  cmp     eax, 102h
0x180023e87  jz      short loc_180023E99
0x180023e89  test    eax, 0FFFFFF7Fh
0x180023e8e  jnz     loc_180024156
0x180023e94  mov     rdi, rbx
0x180023e97  jmp     short loc_180023E9B
0x180023e99  xor     edi, edi
0x180023e9b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180023ea0  mov     [rsp+280h+hObject], 0
0x180023ea9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180023eae  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180023eb3  mov     esi, eax
0x180023eb5  test    eax, eax
0x180023eb7  jns     short loc_180023F38
0x180023eb9  mov     rcx, [rbp+188h]; this
0x180023ec0  lea     r8, aWil; "wil"
0x180023ec7  mov     r9d, eax; char *
0x180023eca  mov     edx, 66h ; 'f'; void *
0x180023ecf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ed4  mov     rcx, [rbp+188h]; this
0x180023edb  lea     r8, aWil; "wil"
0x180023ee2  mov     r9d, esi; char *
0x180023ee5  mov     edx, 6Fh ; 'o'; void *
0x180023eea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023eef  mov     rcx, [rbp+188h]; this
0x180023ef6  lea     r8, aWil; "wil"
0x180023efd  mov     r9d, esi; char *
0x180023f00  mov     edx, 12Eh; void *
0x180023f05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f0a  test    rdi, rdi
0x180023f0d  jz      short loc_180023F20
0x180023f0f  mov     rcx, rdi; hMutex
0x180023f12  call    cs:__imp_ReleaseMutex
0x180023f18  test    eax, eax
0x180023f1a  jz      loc_180024163
0x180023f20  mov     rcx, rbx; hObject
0x180023f23  call    cs:__imp_CloseHandle
0x180023f29  test    eax, eax
0x180023f2b  jz      loc_180024175
0x180023f31  mov     eax, esi
0x180023f33  jmp     loc_18002410C
0x180023f38  mov     rax, [rsp+280h+hObject]
0x180023f3d  lea     rcx, ds:0[rax*4]
0x180023f45  test    rcx, rcx
0x180023f48  jz      short loc_180023F58
0x180023f4a  mov     [r15], rcx
0x180023f4d  mov     eax, [rcx]
0x180023f4f  inc     eax
0x180023f51  mov     [rcx], eax
0x180023f53  jmp     loc_1800240E2
0x180023f58  mov     rdx, r14; dwBytes
0x180023f5b  mov     qword ptr [r15], 0
0x180023f62  mov     ecx, 8; dwFlags
0x180023f67  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180023f6c  mov     r14, rax
0x180023f6f  test    rax, rax
0x180023f72  jnz     short loc_180023F99
0x180023f74  mov     rcx, [rbp+188h]; this
0x180023f7b  lea     r8, aWil; "wil"
0x180023f82  mov     esi, 8007000Eh
0x180023f87  mov     edx, 14Bh; void *
0x180023f8c  mov     r9d, esi; char *
0x180023f8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f94  jmp     loc_18002402B
0x180023f99  xorps   xmm0, xmm0
0x180023f9c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180023fa2  test    r14b, 3
0x180023fa6  jnz     loc_180024187
0x180023fac  mov     r9, r14
0x180023faf  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180023fb4  shr     r9, 2; unsigned __int64
0x180023fb8  lea     rcx, [rsp+280h+hObject]; this
0x180023fbd  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180023fc2  mov     esi, eax
0x180023fc4  test    eax, eax
0x180023fc6  jns     loc_180024072
0x180023fcc  mov     rcx, [rbp+188h]; this
0x180023fd3  lea     r8, aWil; "wil"
0x180023fda  mov     r9d, eax; char *
0x180023fdd  mov     edx, 14Eh; void *
0x180023fe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023fe7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180023fec  test    rcx, rcx
0x180023fef  jz      short loc_180023FFF
0x180023ff1  call    cs:__imp_CloseHandle
0x180023ff7  test    eax, eax
0x180023ff9  jz      loc_18002418D
0x180023fff  mov     rcx, [rsp+280h+hObject]; hObject
0x180024004  test    rcx, rcx
0x180024007  jz      short loc_180024017
0x180024009  call    cs:__imp_CloseHandle
0x18002400f  test    eax, eax
0x180024011  jz      loc_18002419F
0x180024017  call    cs:__imp_GetProcessHeap
0x18002401d  mov     r8, r14; lpMem
0x180024020  xor     edx, edx; dwFlags
0x180024022  mov     rcx, rax; hHeap
0x180024025  call    cs:__imp_HeapFree
0x18002402b  mov     rcx, [rbp+188h]; this
0x180024032  lea     r8, aWil; "wil"
0x180024039  mov     r9d, esi; char *
0x18002403c  mov     edx, 137h; void *
0x180024041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024046  test    rdi, rdi
0x180024049  jz      short loc_18002405C
0x18002404b  mov     rcx, rdi; hMutex
0x18002404e  call    cs:__imp_ReleaseMutex
0x180024054  test    eax, eax
0x180024056  jz      loc_1800241B1
0x18002405c  mov     rcx, rbx; hObject
0x18002405f  call    cs:__imp_CloseHandle
0x180024065  test    eax, eax
0x180024067  jz      loc_180024144
0x18002406d  jmp     loc_180023F31
0x180024072  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180024077  lea     rcx, [r14+28h]; void *
0x18002407b  mov     dword ptr [r14], 1
0x180024082  xor     edx, edx; Val
0x180024084  mov     [r14+8], rbx
0x180024088  mov     r8d, 108h; Size
0x18002408e  movdqu  xmmword ptr [r14+10h], xmm0
0x180024094  call    memset_0
0x180024099  xor     eax, eax
0x18002409b  lea     rcx, [r14+28h]; this
0x18002409f  mov     [r14+20h], rax
0x1800240a3  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800240a8  lea     rbx, [r14+0E8h]
0x1800240af  xor     r8d, r8d; Flags
0x1800240b2  mov     rcx, rbx; lpCriticalSection
0x1800240b5  xor     edx, edx; dwSpinCount
0x1800240b7  call    cs:__imp_InitializeCriticalSectionEx
0x1800240bd  mov     qword ptr [rbx+28h], 0
0x1800240c5  mov     qword ptr [rbx+30h], 0
0x1800240cd  mov     qword ptr [rbx+38h], 0
0x1800240d5  mov     qword ptr [rbx+40h], 0
0x1800240dd  xor     ebx, ebx
0x1800240df  mov     [r15], r14
0x1800240e2  test    rdi, rdi
0x1800240e5  jz      short loc_1800240F8
0x1800240e7  mov     rcx, rdi; hMutex
0x1800240ea  call    cs:__imp_ReleaseMutex
0x1800240f0  test    eax, eax
0x1800240f2  jz      loc_1800241C3
0x1800240f8  test    rbx, rbx
0x1800240fb  jz      short loc_18002410A
0x1800240fd  mov     rcx, rbx; hObject
0x180024100  call    cs:__imp_CloseHandle
0x180024106  test    eax, eax
0x180024108  jz      short loc_180024132
0x18002410a  xor     eax, eax
0x18002410c  mov     rcx, [rbp+180h+var_30]
0x180024113  xor     rcx, rsp; StackCookie
0x180024116  call    __security_check_cookie
0x18002411b  mov     rbx, [rsp+280h+arg_10]
0x180024123  add     rsp, 260h
0x18002412a  pop     r15
0x18002412c  pop     r14
0x18002412e  pop     rdi
0x18002412f  pop     rsi
0x180024130  pop     rbp
0x180024131  retn
0x180024132  mov     rcx, [rbp+188h]; this
0x180024139  mov     edx, 0A0Bh; void *
0x18002413e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024144  mov     rcx, [rbp+188h]; this
0x18002414b  mov     edx, 0A0Bh; void *
0x180024150  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024156  mov     rcx, [rbp+188h]; this
0x18002415d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180024163  mov     rcx, [rbp+188h]; this
0x18002416a  mov     edx, 0A15h; void *
0x18002416f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024175  mov     rcx, [rbp+188h]; this
0x18002417c  mov     edx, 0A0Bh; void *
0x180024181  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024187  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002418d  mov     rcx, [rbp+188h]; this
0x180024194  mov     edx, 0A0Bh; void *
0x180024199  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002419f  mov     rcx, [rbp+188h]; this
0x1800241a6  mov     edx, 0A0Bh; void *
0x1800241ab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800241b1  mov     rcx, [rbp+188h]; this
0x1800241b8  mov     edx, 0A15h; void *
0x1800241bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800241c3  mov     rcx, [rbp+188h]; this
0x1800241ca  mov     edx, 0A15h; void *
0x1800241cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
