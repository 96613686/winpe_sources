# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003ce4`
- end: `0x1800040ab`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004930`

## callees

- `0x180002eb4`
- `0x180003ce4`
- `0x180004140`
- `0x180004c98`
- `0x180005908`
- `0x180006ffc`
- `0x180008a34`
- `0x180009480`
- `0x1800098dc`
- `0x18000ab0c`
- `0x18000ab1c`
- `0x18000c5e2`
- `0x18000c610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003dfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f24`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003dfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f24`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fc0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003f8d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003f8d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003d5b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003d5b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003d7c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003d7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ef4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ef4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fd6`

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
0x180003ce4  mov     [rsp-8+arg_10], rbx
0x180003ce9  push    rbp
0x180003cea  push    rsi
0x180003ceb  push    rdi
0x180003cec  push    r14
0x180003cee  push    r15
0x180003cf0  lea     rbp, [rsp-160h]
0x180003cf8  sub     rsp, 260h
0x180003cff  mov     rax, cs:__security_cookie
0x180003d06  xor     rax, rsp
0x180003d09  mov     [rbp+180h+var_30], rax
0x180003d10  mov     r15, rdx
0x180003d13  mov     qword ptr [rdx], 0
0x180003d1a  mov     rbx, rcx
0x180003d1d  call    cs:__imp_GetCurrentProcessId
0x180003d23  mov     r14d, 130h
0x180003d29  mov     [rsp+280h+var_258], rbx
0x180003d2e  mov     r9d, eax
0x180003d31  mov     [rsp+280h+var_260], r14d; int
0x180003d36  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003d3d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003d42  lea     edx, [r14-2Ch]; unsigned __int64
0x180003d46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003d4b  mov     r9d, 1F0001h; dwDesiredAccess
0x180003d51  lea     rdx, [rsp+280h+Name]; lpName
0x180003d56  xor     r8d, r8d; dwFlags
0x180003d59  xor     ecx, ecx; lpMutexAttributes
0x180003d5b  call    cs:__imp_CreateMutexExW
0x180003d61  mov     rbx, rax
0x180003d64  test    rax, rax
0x180003d67  jnz     short loc_180003D73
0x180003d69  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003d6e  jmp     loc_180003FE2
0x180003d73  xor     r8d, r8d; bAlertable
0x180003d76  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003d79  mov     rcx, rbx; hHandle
0x180003d7c  call    cs:__imp_WaitForSingleObjectEx
0x180003d82  cmp     eax, 102h
0x180003d87  jz      short loc_180003D99
0x180003d89  test    eax, 0FFFFFF7Fh
0x180003d8e  jnz     loc_18000402C
0x180003d94  mov     rdi, rbx
0x180003d97  jmp     short loc_180003D9B
0x180003d99  xor     edi, edi
0x180003d9b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003da0  mov     [rsp+280h+hObject], 0
0x180003da9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003dae  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003db3  mov     esi, eax
0x180003db5  test    eax, eax
0x180003db7  jns     short loc_180003E23
0x180003db9  mov     rcx, [rbp+188h]; this
0x180003dc0  mov     r9d, eax; char *
0x180003dc3  mov     edx, 66h ; 'f'; void *
0x180003dc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003dcd  mov     rcx, [rbp+188h]; this
0x180003dd4  mov     r9d, esi; char *
0x180003dd7  mov     edx, 6Fh ; 'o'; void *
0x180003ddc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003de1  mov     rcx, [rbp+188h]; this
0x180003de8  mov     r9d, esi; char *
0x180003deb  mov     edx, 12Eh; void *
0x180003df0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003df5  test    rdi, rdi
0x180003df8  jz      short loc_180003E0B
0x180003dfa  mov     rcx, rdi; hMutex
0x180003dfd  call    cs:__imp_ReleaseMutex
0x180003e03  test    eax, eax
0x180003e05  jz      loc_180004039
0x180003e0b  mov     rcx, rbx; hObject
0x180003e0e  call    cs:__imp_CloseHandle
0x180003e14  test    eax, eax
0x180003e16  jz      loc_18000404B
0x180003e1c  mov     eax, esi
0x180003e1e  jmp     loc_180003FE2
0x180003e23  mov     rax, [rsp+280h+hObject]
0x180003e28  lea     rcx, ds:0[rax*4]
0x180003e30  test    rcx, rcx
0x180003e33  jz      short loc_180003E43
0x180003e35  mov     [r15], rcx
0x180003e38  mov     eax, [rcx]
0x180003e3a  inc     eax
0x180003e3c  mov     [rcx], eax
0x180003e3e  jmp     loc_180003FB8
0x180003e43  mov     rdx, r14; dwBytes
0x180003e46  mov     qword ptr [r15], 0
0x180003e4d  mov     ecx, 8; dwFlags
0x180003e52  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003e57  mov     r14, rax
0x180003e5a  test    rax, rax
0x180003e5d  jnz     short loc_180003E7D
0x180003e5f  mov     rcx, [rbp+188h]; this
0x180003e66  mov     esi, 8007000Eh
0x180003e6b  mov     r9d, esi; char *
0x180003e6e  mov     edx, 14Bh; void *
0x180003e73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e78  jmp     loc_180003F08
0x180003e7d  xorps   xmm0, xmm0
0x180003e80  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003e86  test    r14b, 3
0x180003e8a  jnz     loc_18000405D
0x180003e90  mov     r9, r14
0x180003e93  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003e98  shr     r9, 2; unsigned __int64
0x180003e9c  lea     rcx, [rsp+280h+hObject]; this
0x180003ea1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003ea6  mov     esi, eax
0x180003ea8  test    eax, eax
0x180003eaa  jns     loc_180003F48
0x180003eb0  mov     rcx, [rbp+188h]; this
0x180003eb7  mov     r9d, eax; char *
0x180003eba  mov     edx, 14Eh; void *
0x180003ebf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ec4  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003ec9  test    rcx, rcx
0x180003ecc  jz      short loc_180003EDC
0x180003ece  call    cs:__imp_CloseHandle
0x180003ed4  test    eax, eax
0x180003ed6  jz      loc_180004063
0x180003edc  mov     rcx, [rsp+280h+hObject]; hObject
0x180003ee1  test    rcx, rcx
0x180003ee4  jz      short loc_180003EF4
0x180003ee6  call    cs:__imp_CloseHandle
0x180003eec  test    eax, eax
0x180003eee  jz      loc_180004075
0x180003ef4  call    cs:__imp_GetProcessHeap
0x180003efa  mov     r8, r14; lpMem
0x180003efd  xor     edx, edx; dwFlags
0x180003eff  mov     rcx, rax; hHeap
0x180003f02  call    cs:__imp_HeapFree
0x180003f08  mov     rcx, [rbp+188h]; this
0x180003f0f  mov     r9d, esi; char *
0x180003f12  mov     edx, 137h; void *
0x180003f17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f1c  test    rdi, rdi
0x180003f1f  jz      short loc_180003F32
0x180003f21  mov     rcx, rdi; hMutex
0x180003f24  call    cs:__imp_ReleaseMutex
0x180003f2a  test    eax, eax
0x180003f2c  jz      loc_180004087
0x180003f32  mov     rcx, rbx; hObject
0x180003f35  call    cs:__imp_CloseHandle
0x180003f3b  test    eax, eax
0x180003f3d  jz      loc_18000401A
0x180003f43  jmp     loc_180003E1C
0x180003f48  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003f4d  lea     rcx, [r14+28h]; void *
0x180003f51  mov     dword ptr [r14], 1
0x180003f58  xor     edx, edx; Val
0x180003f5a  mov     [r14+8], rbx
0x180003f5e  mov     r8d, 108h; Size
0x180003f64  movdqu  xmmword ptr [r14+10h], xmm0
0x180003f6a  call    memset_0
0x180003f6f  xor     eax, eax
0x180003f71  lea     rcx, [r14+28h]; this
0x180003f75  mov     [r14+20h], rax
0x180003f79  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003f7e  lea     rbx, [r14+0E8h]
0x180003f85  xor     r8d, r8d; Flags
0x180003f88  mov     rcx, rbx; lpCriticalSection
0x180003f8b  xor     edx, edx; dwSpinCount
0x180003f8d  call    cs:__imp_InitializeCriticalSectionEx
0x180003f93  mov     qword ptr [rbx+28h], 0
0x180003f9b  mov     qword ptr [rbx+30h], 0
0x180003fa3  mov     qword ptr [rbx+38h], 0
0x180003fab  mov     qword ptr [rbx+40h], 0
0x180003fb3  xor     ebx, ebx
0x180003fb5  mov     [r15], r14
0x180003fb8  test    rdi, rdi
0x180003fbb  jz      short loc_180003FCE
0x180003fbd  mov     rcx, rdi; hMutex
0x180003fc0  call    cs:__imp_ReleaseMutex
0x180003fc6  test    eax, eax
0x180003fc8  jz      loc_180004099
0x180003fce  test    rbx, rbx
0x180003fd1  jz      short loc_180003FE0
0x180003fd3  mov     rcx, rbx; hObject
0x180003fd6  call    cs:__imp_CloseHandle
0x180003fdc  test    eax, eax
0x180003fde  jz      short loc_180004008
0x180003fe0  xor     eax, eax
0x180003fe2  mov     rcx, [rbp+180h+var_30]
0x180003fe9  xor     rcx, rsp; StackCookie
0x180003fec  call    __security_check_cookie
0x180003ff1  mov     rbx, [rsp+280h+arg_10]
0x180003ff9  add     rsp, 260h
0x180004000  pop     r15
0x180004002  pop     r14
0x180004004  pop     rdi
0x180004005  pop     rsi
0x180004006  pop     rbp
0x180004007  retn
0x180004008  mov     rcx, [rbp+188h]; this
0x18000400f  mov     edx, 0A0Bh; void *
0x180004014  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000401a  mov     rcx, [rbp+188h]; this
0x180004021  mov     edx, 0A0Bh; void *
0x180004026  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000402c  mov     rcx, [rbp+188h]; this
0x180004033  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004039  mov     rcx, [rbp+188h]; this
0x180004040  mov     edx, 0A15h; void *
0x180004045  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000404b  mov     rcx, [rbp+188h]; this
0x180004052  mov     edx, 0A0Bh; void *
0x180004057  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000405d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004063  mov     rcx, [rbp+188h]; this
0x18000406a  mov     edx, 0A0Bh; void *
0x18000406f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004075  mov     rcx, [rbp+188h]; this
0x18000407c  mov     edx, 0A0Bh; void *
0x180004081  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004087  mov     rcx, [rbp+188h]; this
0x18000408e  mov     edx, 0A15h; void *
0x180004093  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004099  mov     rcx, [rbp+188h]; this
0x1800040a0  mov     edx, 0A15h; void *
0x1800040a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
