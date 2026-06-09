# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007dd8`
- end: `0x18000819f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800081a8`

## callees

- `0x180004334`
- `0x180004604`
- `0x180004b98`
- `0x180005678`
- `0x1800058d4`
- `0x180006104`
- `0x1800061bc`
- `0x18000669c`
- `0x1800066ac`
- `0x180007768`
- `0x180007dd8`
- `0x18000b612`
- `0x18000b640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007e11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007e11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007e70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007e70`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007ef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008018`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800080b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007ef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008018`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800080b4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007e4f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007e4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008081`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008081`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fe8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ff6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ff6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008029`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008029`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080ca`

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
0x180007dd8  mov     [rsp-8+arg_10], rbx
0x180007ddd  push    rbp
0x180007dde  push    rsi
0x180007ddf  push    rdi
0x180007de0  push    r14
0x180007de2  push    r15
0x180007de4  lea     rbp, [rsp-160h]
0x180007dec  sub     rsp, 260h
0x180007df3  mov     rax, cs:__security_cookie
0x180007dfa  xor     rax, rsp
0x180007dfd  mov     [rbp+180h+var_30], rax
0x180007e04  mov     r15, rdx
0x180007e07  mov     qword ptr [rdx], 0
0x180007e0e  mov     rbx, rcx
0x180007e11  call    cs:__imp_GetCurrentProcessId
0x180007e17  mov     r14d, 130h
0x180007e1d  mov     [rsp+280h+var_258], rbx
0x180007e22  mov     r9d, eax
0x180007e25  mov     [rsp+280h+var_260], r14d; int
0x180007e2a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007e31  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007e36  lea     edx, [r14-2Ch]; unsigned __int64
0x180007e3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007e3f  mov     r9d, 1F0001h; dwDesiredAccess
0x180007e45  lea     rdx, [rsp+280h+Name]; lpName
0x180007e4a  xor     r8d, r8d; dwFlags
0x180007e4d  xor     ecx, ecx; lpMutexAttributes
0x180007e4f  call    cs:__imp_CreateMutexExW
0x180007e55  mov     rbx, rax
0x180007e58  test    rax, rax
0x180007e5b  jnz     short loc_180007E67
0x180007e5d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007e62  jmp     loc_1800080D6
0x180007e67  xor     r8d, r8d; bAlertable
0x180007e6a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007e6d  mov     rcx, rbx; hHandle
0x180007e70  call    cs:__imp_WaitForSingleObjectEx
0x180007e76  cmp     eax, 102h
0x180007e7b  jz      short loc_180007E8D
0x180007e7d  test    eax, 0FFFFFF7Fh
0x180007e82  jnz     loc_180008120
0x180007e88  mov     rdi, rbx
0x180007e8b  jmp     short loc_180007E8F
0x180007e8d  xor     edi, edi
0x180007e8f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180007e94  mov     [rsp+280h+hObject], 0
0x180007e9d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007ea2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007ea7  mov     esi, eax
0x180007ea9  test    eax, eax
0x180007eab  jns     short loc_180007F17
0x180007ead  mov     rcx, [rbp+188h]; this
0x180007eb4  mov     r9d, eax; char *
0x180007eb7  mov     edx, 66h ; 'f'; void *
0x180007ebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ec1  mov     rcx, [rbp+188h]; this
0x180007ec8  mov     r9d, esi; char *
0x180007ecb  mov     edx, 6Fh ; 'o'; void *
0x180007ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ed5  mov     rcx, [rbp+188h]; this
0x180007edc  mov     r9d, esi; char *
0x180007edf  mov     edx, 12Eh; void *
0x180007ee4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ee9  test    rdi, rdi
0x180007eec  jz      short loc_180007EFF
0x180007eee  mov     rcx, rdi; hMutex
0x180007ef1  call    cs:__imp_ReleaseMutex
0x180007ef7  test    eax, eax
0x180007ef9  jz      loc_18000812D
0x180007eff  mov     rcx, rbx; hObject
0x180007f02  call    cs:__imp_CloseHandle
0x180007f08  test    eax, eax
0x180007f0a  jz      loc_18000813F
0x180007f10  mov     eax, esi
0x180007f12  jmp     loc_1800080D6
0x180007f17  mov     rax, [rsp+280h+hObject]
0x180007f1c  lea     rcx, ds:0[rax*4]
0x180007f24  test    rcx, rcx
0x180007f27  jz      short loc_180007F37
0x180007f29  mov     [r15], rcx
0x180007f2c  mov     eax, [rcx]
0x180007f2e  inc     eax
0x180007f30  mov     [rcx], eax
0x180007f32  jmp     loc_1800080AC
0x180007f37  mov     rdx, r14; dwBytes
0x180007f3a  mov     qword ptr [r15], 0
0x180007f41  mov     ecx, 8; dwFlags
0x180007f46  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007f4b  mov     r14, rax
0x180007f4e  test    rax, rax
0x180007f51  jnz     short loc_180007F71
0x180007f53  mov     rcx, [rbp+188h]; this
0x180007f5a  mov     esi, 8007000Eh
0x180007f5f  mov     r9d, esi; char *
0x180007f62  mov     edx, 14Bh; void *
0x180007f67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f6c  jmp     loc_180007FFC
0x180007f71  xorps   xmm0, xmm0
0x180007f74  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180007f7a  test    r14b, 3
0x180007f7e  jnz     loc_180008151
0x180007f84  mov     r9, r14
0x180007f87  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180007f8c  shr     r9, 2; unsigned __int64
0x180007f90  lea     rcx, [rsp+280h+hObject]; this
0x180007f95  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180007f9a  mov     esi, eax
0x180007f9c  test    eax, eax
0x180007f9e  jns     loc_18000803C
0x180007fa4  mov     rcx, [rbp+188h]; this
0x180007fab  mov     r9d, eax; char *
0x180007fae  mov     edx, 14Eh; void *
0x180007fb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007fb8  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180007fbd  test    rcx, rcx
0x180007fc0  jz      short loc_180007FD0
0x180007fc2  call    cs:__imp_CloseHandle
0x180007fc8  test    eax, eax
0x180007fca  jz      loc_180008157
0x180007fd0  mov     rcx, [rsp+280h+hObject]; hObject
0x180007fd5  test    rcx, rcx
0x180007fd8  jz      short loc_180007FE8
0x180007fda  call    cs:__imp_CloseHandle
0x180007fe0  test    eax, eax
0x180007fe2  jz      loc_180008169
0x180007fe8  call    cs:__imp_GetProcessHeap
0x180007fee  mov     r8, r14; lpMem
0x180007ff1  xor     edx, edx; dwFlags
0x180007ff3  mov     rcx, rax; hHeap
0x180007ff6  call    cs:__imp_HeapFree
0x180007ffc  mov     rcx, [rbp+188h]; this
0x180008003  mov     r9d, esi; char *
0x180008006  mov     edx, 137h; void *
0x18000800b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008010  test    rdi, rdi
0x180008013  jz      short loc_180008026
0x180008015  mov     rcx, rdi; hMutex
0x180008018  call    cs:__imp_ReleaseMutex
0x18000801e  test    eax, eax
0x180008020  jz      loc_18000817B
0x180008026  mov     rcx, rbx; hObject
0x180008029  call    cs:__imp_CloseHandle
0x18000802f  test    eax, eax
0x180008031  jz      loc_18000810E
0x180008037  jmp     loc_180007F10
0x18000803c  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008041  lea     rcx, [r14+28h]; void *
0x180008045  mov     dword ptr [r14], 1
0x18000804c  xor     edx, edx; Val
0x18000804e  mov     [r14+8], rbx
0x180008052  mov     r8d, 108h; Size
0x180008058  movdqu  xmmword ptr [r14+10h], xmm0
0x18000805e  call    memset_0
0x180008063  xor     eax, eax
0x180008065  lea     rcx, [r14+28h]; this
0x180008069  mov     [r14+20h], rax
0x18000806d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008072  lea     rbx, [r14+0E8h]
0x180008079  xor     r8d, r8d; Flags
0x18000807c  mov     rcx, rbx; lpCriticalSection
0x18000807f  xor     edx, edx; dwSpinCount
0x180008081  call    cs:__imp_InitializeCriticalSectionEx
0x180008087  mov     qword ptr [rbx+28h], 0
0x18000808f  mov     qword ptr [rbx+30h], 0
0x180008097  mov     qword ptr [rbx+38h], 0
0x18000809f  mov     qword ptr [rbx+40h], 0
0x1800080a7  xor     ebx, ebx
0x1800080a9  mov     [r15], r14
0x1800080ac  test    rdi, rdi
0x1800080af  jz      short loc_1800080C2
0x1800080b1  mov     rcx, rdi; hMutex
0x1800080b4  call    cs:__imp_ReleaseMutex
0x1800080ba  test    eax, eax
0x1800080bc  jz      loc_18000818D
0x1800080c2  test    rbx, rbx
0x1800080c5  jz      short loc_1800080D4
0x1800080c7  mov     rcx, rbx; hObject
0x1800080ca  call    cs:__imp_CloseHandle
0x1800080d0  test    eax, eax
0x1800080d2  jz      short loc_1800080FC
0x1800080d4  xor     eax, eax
0x1800080d6  mov     rcx, [rbp+180h+var_30]
0x1800080dd  xor     rcx, rsp; StackCookie
0x1800080e0  call    __security_check_cookie
0x1800080e5  mov     rbx, [rsp+280h+arg_10]
0x1800080ed  add     rsp, 260h
0x1800080f4  pop     r15
0x1800080f6  pop     r14
0x1800080f8  pop     rdi
0x1800080f9  pop     rsi
0x1800080fa  pop     rbp
0x1800080fb  retn
0x1800080fc  mov     rcx, [rbp+188h]; this
0x180008103  mov     edx, 0A0Bh; void *
0x180008108  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000810e  mov     rcx, [rbp+188h]; this
0x180008115  mov     edx, 0A0Bh; void *
0x18000811a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008120  mov     rcx, [rbp+188h]; this
0x180008127  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000812d  mov     rcx, [rbp+188h]; this
0x180008134  mov     edx, 0A15h; void *
0x180008139  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000813f  mov     rcx, [rbp+188h]; this
0x180008146  mov     edx, 0A0Bh; void *
0x18000814b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008151  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008157  mov     rcx, [rbp+188h]; this
0x18000815e  mov     edx, 0A0Bh; void *
0x180008163  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008169  mov     rcx, [rbp+188h]; this
0x180008170  mov     edx, 0A0Bh; void *
0x180008175  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000817b  mov     rcx, [rbp+188h]; this
0x180008182  mov     edx, 0A15h; void *
0x180008187  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000818d  mov     rcx, [rbp+188h]; this
0x180008194  mov     edx, 0A15h; void *
0x180008199  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
