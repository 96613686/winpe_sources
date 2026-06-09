# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000fa9c`
- end: `0x18000fe63`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180010024`

## callees

- `0x1800032a0`
- `0x180003d14`
- `0x180006b30`
- `0x180007164`
- `0x180007a98`
- `0x180008b08`
- `0x180009434`
- `0x180009e24`
- `0x18000a040`
- `0x18000a8dc`
- `0x18000a8ec`
- `0x18000ec8c`
- `0x18000fa9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000fb13`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000fb13`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000fd45`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000fd45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fb34`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fb34`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fbb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fcdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fd78`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fbb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fcdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000fd78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fcac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fcac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fcba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fad5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fad5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fbc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fced`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fbc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fced`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd8e`

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
0x18000fa9c  mov     [rsp-8+arg_10], rbx
0x18000faa1  push    rbp
0x18000faa2  push    rsi
0x18000faa3  push    rdi
0x18000faa4  push    r14
0x18000faa6  push    r15
0x18000faa8  lea     rbp, [rsp-160h]
0x18000fab0  sub     rsp, 260h
0x18000fab7  mov     rax, cs:__security_cookie
0x18000fabe  xor     rax, rsp
0x18000fac1  mov     [rbp+180h+var_30], rax
0x18000fac8  mov     r15, rdx
0x18000facb  mov     qword ptr [rdx], 0
0x18000fad2  mov     rbx, rcx
0x18000fad5  call    cs:__imp_GetCurrentProcessId
0x18000fadb  mov     r14d, 130h
0x18000fae1  mov     [rsp+280h+var_258], rbx
0x18000fae6  mov     r9d, eax
0x18000fae9  mov     [rsp+280h+var_260], r14d; int
0x18000faee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000faf5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000fafa  lea     edx, [r14-2Ch]; unsigned __int64
0x18000fafe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fb03  mov     r9d, 1F0001h; dwDesiredAccess
0x18000fb09  lea     rdx, [rsp+280h+Name]; lpName
0x18000fb0e  xor     r8d, r8d; dwFlags
0x18000fb11  xor     ecx, ecx; lpMutexAttributes
0x18000fb13  call    cs:__imp_CreateMutexExW
0x18000fb19  mov     rbx, rax
0x18000fb1c  test    rax, rax
0x18000fb1f  jnz     short loc_18000FB2B
0x18000fb21  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000fb26  jmp     loc_18000FD9A
0x18000fb2b  xor     r8d, r8d; bAlertable
0x18000fb2e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000fb31  mov     rcx, rbx; hHandle
0x18000fb34  call    cs:__imp_WaitForSingleObjectEx
0x18000fb3a  cmp     eax, 102h
0x18000fb3f  jz      short loc_18000FB51
0x18000fb41  test    eax, 0FFFFFF7Fh
0x18000fb46  jnz     loc_18000FDE4
0x18000fb4c  mov     rdi, rbx
0x18000fb4f  jmp     short loc_18000FB53
0x18000fb51  xor     edi, edi
0x18000fb53  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000fb58  mov     [rsp+280h+hObject], 0
0x18000fb61  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000fb66  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000fb6b  mov     esi, eax
0x18000fb6d  test    eax, eax
0x18000fb6f  jns     short loc_18000FBDB
0x18000fb71  mov     rcx, [rbp+188h]; this
0x18000fb78  mov     r9d, eax; char *
0x18000fb7b  mov     edx, 66h ; 'f'; void *
0x18000fb80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fb85  mov     rcx, [rbp+188h]; this
0x18000fb8c  mov     r9d, esi; char *
0x18000fb8f  mov     edx, 6Fh ; 'o'; void *
0x18000fb94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fb99  mov     rcx, [rbp+188h]; this
0x18000fba0  mov     r9d, esi; char *
0x18000fba3  mov     edx, 12Eh; void *
0x18000fba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fbad  test    rdi, rdi
0x18000fbb0  jz      short loc_18000FBC3
0x18000fbb2  mov     rcx, rdi; hMutex
0x18000fbb5  call    cs:__imp_ReleaseMutex
0x18000fbbb  test    eax, eax
0x18000fbbd  jz      loc_18000FDF1
0x18000fbc3  mov     rcx, rbx; hObject
0x18000fbc6  call    cs:__imp_CloseHandle
0x18000fbcc  test    eax, eax
0x18000fbce  jz      loc_18000FE03
0x18000fbd4  mov     eax, esi
0x18000fbd6  jmp     loc_18000FD9A
0x18000fbdb  mov     rax, [rsp+280h+hObject]
0x18000fbe0  lea     rcx, ds:0[rax*4]
0x18000fbe8  test    rcx, rcx
0x18000fbeb  jz      short loc_18000FBFB
0x18000fbed  mov     [r15], rcx
0x18000fbf0  mov     eax, [rcx]
0x18000fbf2  inc     eax
0x18000fbf4  mov     [rcx], eax
0x18000fbf6  jmp     loc_18000FD70
0x18000fbfb  mov     rdx, r14; dwBytes
0x18000fbfe  mov     qword ptr [r15], 0
0x18000fc05  mov     ecx, 8; dwFlags
0x18000fc0a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000fc0f  mov     r14, rax
0x18000fc12  test    rax, rax
0x18000fc15  jnz     short loc_18000FC35
0x18000fc17  mov     rcx, [rbp+188h]; this
0x18000fc1e  mov     esi, 8007000Eh
0x18000fc23  mov     r9d, esi; char *
0x18000fc26  mov     edx, 14Bh; void *
0x18000fc2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc30  jmp     loc_18000FCC0
0x18000fc35  xorps   xmm0, xmm0
0x18000fc38  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000fc3e  test    r14b, 3
0x18000fc42  jnz     loc_18000FE15
0x18000fc48  mov     r9, r14
0x18000fc4b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000fc50  shr     r9, 2; unsigned __int64
0x18000fc54  lea     rcx, [rsp+280h+hObject]; this
0x18000fc59  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000fc5e  mov     esi, eax
0x18000fc60  test    eax, eax
0x18000fc62  jns     loc_18000FD00
0x18000fc68  mov     rcx, [rbp+188h]; this
0x18000fc6f  mov     r9d, eax; char *
0x18000fc72  mov     edx, 14Eh; void *
0x18000fc77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc7c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000fc81  test    rcx, rcx
0x18000fc84  jz      short loc_18000FC94
0x18000fc86  call    cs:__imp_CloseHandle
0x18000fc8c  test    eax, eax
0x18000fc8e  jz      loc_18000FE1B
0x18000fc94  mov     rcx, [rsp+280h+hObject]; hObject
0x18000fc99  test    rcx, rcx
0x18000fc9c  jz      short loc_18000FCAC
0x18000fc9e  call    cs:__imp_CloseHandle
0x18000fca4  test    eax, eax
0x18000fca6  jz      loc_18000FE2D
0x18000fcac  call    cs:__imp_GetProcessHeap
0x18000fcb2  mov     r8, r14; lpMem
0x18000fcb5  xor     edx, edx; dwFlags
0x18000fcb7  mov     rcx, rax; hHeap
0x18000fcba  call    cs:__imp_HeapFree
0x18000fcc0  mov     rcx, [rbp+188h]; this
0x18000fcc7  mov     r9d, esi; char *
0x18000fcca  mov     edx, 137h; void *
0x18000fccf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fcd4  test    rdi, rdi
0x18000fcd7  jz      short loc_18000FCEA
0x18000fcd9  mov     rcx, rdi; hMutex
0x18000fcdc  call    cs:__imp_ReleaseMutex
0x18000fce2  test    eax, eax
0x18000fce4  jz      loc_18000FE3F
0x18000fcea  mov     rcx, rbx; hObject
0x18000fced  call    cs:__imp_CloseHandle
0x18000fcf3  test    eax, eax
0x18000fcf5  jz      loc_18000FDD2
0x18000fcfb  jmp     loc_18000FBD4
0x18000fd00  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000fd05  lea     rcx, [r14+28h]; void *
0x18000fd09  mov     dword ptr [r14], 1
0x18000fd10  xor     edx, edx; Val
0x18000fd12  mov     [r14+8], rbx
0x18000fd16  mov     r8d, 108h; Size
0x18000fd1c  movdqu  xmmword ptr [r14+10h], xmm0
0x18000fd22  call    memset_0
0x18000fd27  xor     eax, eax
0x18000fd29  lea     rcx, [r14+28h]; this
0x18000fd2d  mov     [r14+20h], rax
0x18000fd31  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000fd36  lea     rbx, [r14+0E8h]
0x18000fd3d  xor     r8d, r8d; Flags
0x18000fd40  mov     rcx, rbx; lpCriticalSection
0x18000fd43  xor     edx, edx; dwSpinCount
0x18000fd45  call    cs:__imp_InitializeCriticalSectionEx
0x18000fd4b  mov     qword ptr [rbx+28h], 0
0x18000fd53  mov     qword ptr [rbx+30h], 0
0x18000fd5b  mov     qword ptr [rbx+38h], 0
0x18000fd63  mov     qword ptr [rbx+40h], 0
0x18000fd6b  xor     ebx, ebx
0x18000fd6d  mov     [r15], r14
0x18000fd70  test    rdi, rdi
0x18000fd73  jz      short loc_18000FD86
0x18000fd75  mov     rcx, rdi; hMutex
0x18000fd78  call    cs:__imp_ReleaseMutex
0x18000fd7e  test    eax, eax
0x18000fd80  jz      loc_18000FE51
0x18000fd86  test    rbx, rbx
0x18000fd89  jz      short loc_18000FD98
0x18000fd8b  mov     rcx, rbx; hObject
0x18000fd8e  call    cs:__imp_CloseHandle
0x18000fd94  test    eax, eax
0x18000fd96  jz      short loc_18000FDC0
0x18000fd98  xor     eax, eax
0x18000fd9a  mov     rcx, [rbp+180h+var_30]
0x18000fda1  xor     rcx, rsp; StackCookie
0x18000fda4  call    __security_check_cookie
0x18000fda9  mov     rbx, [rsp+280h+arg_10]
0x18000fdb1  add     rsp, 260h
0x18000fdb8  pop     r15
0x18000fdba  pop     r14
0x18000fdbc  pop     rdi
0x18000fdbd  pop     rsi
0x18000fdbe  pop     rbp
0x18000fdbf  retn
0x18000fdc0  mov     rcx, [rbp+188h]; this
0x18000fdc7  mov     edx, 0A0Bh; void *
0x18000fdcc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fdd2  mov     rcx, [rbp+188h]; this
0x18000fdd9  mov     edx, 0A0Bh; void *
0x18000fdde  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fde4  mov     rcx, [rbp+188h]; this
0x18000fdeb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000fdf1  mov     rcx, [rbp+188h]; this
0x18000fdf8  mov     edx, 0A15h; void *
0x18000fdfd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fe03  mov     rcx, [rbp+188h]; this
0x18000fe0a  mov     edx, 0A0Bh; void *
0x18000fe0f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fe15  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000fe1b  mov     rcx, [rbp+188h]; this
0x18000fe22  mov     edx, 0A0Bh; void *
0x18000fe27  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fe2d  mov     rcx, [rbp+188h]; this
0x18000fe34  mov     edx, 0A0Bh; void *
0x18000fe39  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fe3f  mov     rcx, [rbp+188h]; this
0x18000fe46  mov     edx, 0A15h; void *
0x18000fe4b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fe51  mov     rcx, [rbp+188h]; this
0x18000fe58  mov     edx, 0A15h; void *
0x18000fe5d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
