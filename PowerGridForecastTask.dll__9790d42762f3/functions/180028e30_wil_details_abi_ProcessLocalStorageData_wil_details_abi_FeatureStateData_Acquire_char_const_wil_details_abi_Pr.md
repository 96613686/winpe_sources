# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180028e30`
- end: `0x180029221`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180029980`

## callees

- `0x1800268ef`
- `0x180027bfc`
- `0x180028e30`
- `0x180029264`
- `0x180029bd4`
- `0x18002aaa8`
- `0x18002bdbc`
- `0x18002dcd4`
- `0x18002edf0`
- `0x18002f1fc`
- `0x18002febc`
- `0x18002fecc`
- `0x1800350e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002903d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029055`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800290ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002914c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002903d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029055`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800290ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002914c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028e69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028e69`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180029103`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180029103`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028f5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002909a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180029136`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028f5e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002909a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180029136`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180028ea7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180028ea7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180028ec8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180028ec8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029071`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029071`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029063`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029063`

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
0x180028e30  mov     [rsp-8+arg_10], rbx
0x180028e35  push    rbp
0x180028e36  push    rsi
0x180028e37  push    rdi
0x180028e38  push    r14
0x180028e3a  push    r15
0x180028e3c  lea     rbp, [rsp-160h]
0x180028e44  sub     rsp, 260h
0x180028e4b  mov     rax, cs:__security_cookie
0x180028e52  xor     rax, rsp
0x180028e55  mov     [rbp+180h+var_30], rax
0x180028e5c  mov     r15, rdx
0x180028e5f  mov     qword ptr [rdx], 0
0x180028e66  mov     rbx, rcx
0x180028e69  call    cs:__imp_GetCurrentProcessId
0x180028e6f  mov     r14d, 130h
0x180028e75  mov     [rsp+280h+var_258], rbx
0x180028e7a  mov     r9d, eax
0x180028e7d  mov     [rsp+280h+var_260], r14d; int
0x180028e82  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180028e89  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180028e8e  lea     edx, [r14-2Ch]; unsigned __int64
0x180028e92  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028e97  mov     r9d, 1F0001h; dwDesiredAccess
0x180028e9d  lea     rdx, [rsp+280h+Name]; lpName
0x180028ea2  xor     r8d, r8d; dwFlags
0x180028ea5  xor     ecx, ecx; lpMutexAttributes
0x180028ea7  call    cs:__imp_CreateMutexExW
0x180028ead  mov     rbx, rax
0x180028eb0  test    rax, rax
0x180028eb3  jnz     short loc_180028EBF
0x180028eb5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180028eba  jmp     loc_180029158
0x180028ebf  xor     r8d, r8d; bAlertable
0x180028ec2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180028ec5  mov     rcx, rbx; hHandle
0x180028ec8  call    cs:__imp_WaitForSingleObjectEx
0x180028ece  cmp     eax, 102h
0x180028ed3  jz      short loc_180028EE5
0x180028ed5  test    eax, 0FFFFFF7Fh
0x180028eda  jnz     loc_1800291A2
0x180028ee0  mov     rdi, rbx
0x180028ee3  jmp     short loc_180028EE7
0x180028ee5  xor     edi, edi
0x180028ee7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180028eec  mov     [rsp+280h+hObject], 0
0x180028ef5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180028efa  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180028eff  mov     esi, eax
0x180028f01  test    eax, eax
0x180028f03  jns     short loc_180028F84
0x180028f05  mov     rcx, [rbp+188h]; this
0x180028f0c  lea     r8, aWil; "wil"
0x180028f13  mov     r9d, eax; char *
0x180028f16  mov     edx, 66h ; 'f'; void *
0x180028f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028f20  mov     rcx, [rbp+188h]; this
0x180028f27  lea     r8, aWil; "wil"
0x180028f2e  mov     r9d, esi; char *
0x180028f31  mov     edx, 6Fh ; 'o'; void *
0x180028f36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028f3b  mov     rcx, [rbp+188h]; this
0x180028f42  lea     r8, aWil; "wil"
0x180028f49  mov     r9d, esi; char *
0x180028f4c  mov     edx, 12Eh; void *
0x180028f51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028f56  test    rdi, rdi
0x180028f59  jz      short loc_180028F6C
0x180028f5b  mov     rcx, rdi; hMutex
0x180028f5e  call    cs:__imp_ReleaseMutex
0x180028f64  test    eax, eax
0x180028f66  jz      loc_1800291AF
0x180028f6c  mov     rcx, rbx; hObject
0x180028f6f  call    cs:__imp_CloseHandle
0x180028f75  test    eax, eax
0x180028f77  jz      loc_1800291C1
0x180028f7d  mov     eax, esi
0x180028f7f  jmp     loc_180029158
0x180028f84  mov     rax, [rsp+280h+hObject]
0x180028f89  lea     rcx, ds:0[rax*4]
0x180028f91  test    rcx, rcx
0x180028f94  jz      short loc_180028FA4
0x180028f96  mov     [r15], rcx
0x180028f99  mov     eax, [rcx]
0x180028f9b  inc     eax
0x180028f9d  mov     [rcx], eax
0x180028f9f  jmp     loc_18002912E
0x180028fa4  mov     rdx, r14; dwBytes
0x180028fa7  mov     qword ptr [r15], 0
0x180028fae  mov     ecx, 8; dwFlags
0x180028fb3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180028fb8  mov     r14, rax
0x180028fbb  test    rax, rax
0x180028fbe  jnz     short loc_180028FE5
0x180028fc0  mov     rcx, [rbp+188h]; this
0x180028fc7  lea     r8, aWil; "wil"
0x180028fce  mov     esi, 8007000Eh
0x180028fd3  mov     edx, 14Bh; void *
0x180028fd8  mov     r9d, esi; char *
0x180028fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028fe0  jmp     loc_180029077
0x180028fe5  xorps   xmm0, xmm0
0x180028fe8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180028fee  test    r14b, 3
0x180028ff2  jnz     loc_1800291D3
0x180028ff8  mov     r9, r14
0x180028ffb  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180029000  shr     r9, 2; unsigned __int64
0x180029004  lea     rcx, [rsp+280h+hObject]; this
0x180029009  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18002900e  mov     esi, eax
0x180029010  test    eax, eax
0x180029012  jns     loc_1800290BE
0x180029018  mov     rcx, [rbp+188h]; this
0x18002901f  lea     r8, aWil; "wil"
0x180029026  mov     r9d, eax; char *
0x180029029  mov     edx, 14Eh; void *
0x18002902e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029033  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180029038  test    rcx, rcx
0x18002903b  jz      short loc_18002904B
0x18002903d  call    cs:__imp_CloseHandle
0x180029043  test    eax, eax
0x180029045  jz      loc_1800291D9
0x18002904b  mov     rcx, [rsp+280h+hObject]; hObject
0x180029050  test    rcx, rcx
0x180029053  jz      short loc_180029063
0x180029055  call    cs:__imp_CloseHandle
0x18002905b  test    eax, eax
0x18002905d  jz      loc_1800291EB
0x180029063  call    cs:__imp_GetProcessHeap
0x180029069  mov     r8, r14; lpMem
0x18002906c  xor     edx, edx; dwFlags
0x18002906e  mov     rcx, rax; hHeap
0x180029071  call    cs:__imp_HeapFree
0x180029077  mov     rcx, [rbp+188h]; this
0x18002907e  lea     r8, aWil; "wil"
0x180029085  mov     r9d, esi; char *
0x180029088  mov     edx, 137h; void *
0x18002908d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029092  test    rdi, rdi
0x180029095  jz      short loc_1800290A8
0x180029097  mov     rcx, rdi; hMutex
0x18002909a  call    cs:__imp_ReleaseMutex
0x1800290a0  test    eax, eax
0x1800290a2  jz      loc_1800291FD
0x1800290a8  mov     rcx, rbx; hObject
0x1800290ab  call    cs:__imp_CloseHandle
0x1800290b1  test    eax, eax
0x1800290b3  jz      loc_180029190
0x1800290b9  jmp     loc_180028F7D
0x1800290be  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800290c3  lea     rcx, [r14+28h]; void *
0x1800290c7  mov     dword ptr [r14], 1
0x1800290ce  xor     edx, edx; Val
0x1800290d0  mov     [r14+8], rbx
0x1800290d4  mov     r8d, 108h; Size
0x1800290da  movdqu  xmmword ptr [r14+10h], xmm0
0x1800290e0  call    memset_0
0x1800290e5  xor     eax, eax
0x1800290e7  lea     rcx, [r14+28h]; this
0x1800290eb  mov     [r14+20h], rax
0x1800290ef  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800290f4  lea     rbx, [r14+0E8h]
0x1800290fb  xor     r8d, r8d; Flags
0x1800290fe  mov     rcx, rbx; lpCriticalSection
0x180029101  xor     edx, edx; dwSpinCount
0x180029103  call    cs:__imp_InitializeCriticalSectionEx
0x180029109  mov     qword ptr [rbx+28h], 0
0x180029111  mov     qword ptr [rbx+30h], 0
0x180029119  mov     qword ptr [rbx+38h], 0
0x180029121  mov     qword ptr [rbx+40h], 0
0x180029129  xor     ebx, ebx
0x18002912b  mov     [r15], r14
0x18002912e  test    rdi, rdi
0x180029131  jz      short loc_180029144
0x180029133  mov     rcx, rdi; hMutex
0x180029136  call    cs:__imp_ReleaseMutex
0x18002913c  test    eax, eax
0x18002913e  jz      loc_18002920F
0x180029144  test    rbx, rbx
0x180029147  jz      short loc_180029156
0x180029149  mov     rcx, rbx; hObject
0x18002914c  call    cs:__imp_CloseHandle
0x180029152  test    eax, eax
0x180029154  jz      short loc_18002917E
0x180029156  xor     eax, eax
0x180029158  mov     rcx, [rbp+180h+var_30]
0x18002915f  xor     rcx, rsp; StackCookie
0x180029162  call    __security_check_cookie
0x180029167  mov     rbx, [rsp+280h+arg_10]
0x18002916f  add     rsp, 260h
0x180029176  pop     r15
0x180029178  pop     r14
0x18002917a  pop     rdi
0x18002917b  pop     rsi
0x18002917c  pop     rbp
0x18002917d  retn
0x18002917e  mov     rcx, [rbp+188h]; this
0x180029185  mov     edx, 0A0Bh; void *
0x18002918a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029190  mov     rcx, [rbp+188h]; this
0x180029197  mov     edx, 0A0Bh; void *
0x18002919c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800291a2  mov     rcx, [rbp+188h]; this
0x1800291a9  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800291af  mov     rcx, [rbp+188h]; this
0x1800291b6  mov     edx, 0A15h; void *
0x1800291bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800291c1  mov     rcx, [rbp+188h]; this
0x1800291c8  mov     edx, 0A0Bh; void *
0x1800291cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800291d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800291d9  mov     rcx, [rbp+188h]; this
0x1800291e0  mov     edx, 0A0Bh; void *
0x1800291e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800291eb  mov     rcx, [rbp+188h]; this
0x1800291f2  mov     edx, 0A0Bh; void *
0x1800291f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800291fd  mov     rcx, [rbp+188h]; this
0x180029204  mov     edx, 0A15h; void *
0x180029209  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002920f  mov     rcx, [rbp+188h]; this
0x180029216  mov     edx, 0A15h; void *
0x18002921b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
