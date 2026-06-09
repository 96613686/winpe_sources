# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14005f364`
- end: `0x14005f72b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400603cc`

## callees

- `0x140004280`
- `0x1400050e0`
- `0x14000a998`
- `0x14000baec`
- `0x14000ca7c`
- `0x14001102c`
- `0x140011564`
- `0x140013384`
- `0x14001347c`
- `0x140013c48`
- `0x140013c58`
- `0x14005ecd4`
- `0x14005f364`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14005f574`
- `KERNEL32!GetProcessHeap` at `0x14005f574`
- `KERNEL32!CreateMutexExW` at `0x14005f3db`
- `KERNEL32!CreateMutexExW` at `0x14005f3db`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14005f60d`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14005f60d`
- `KERNEL32!CloseHandle` at `0x14005f48e`
- `KERNEL32!CloseHandle` at `0x14005f54e`
- `KERNEL32!CloseHandle` at `0x14005f566`
- `KERNEL32!CloseHandle` at `0x14005f5b5`
- `KERNEL32!CloseHandle` at `0x14005f656`
- `KERNEL32!CloseHandle` at `0x14005f48e`
- `KERNEL32!CloseHandle` at `0x14005f54e`
- `KERNEL32!CloseHandle` at `0x14005f566`
- `KERNEL32!CloseHandle` at `0x14005f5b5`
- `KERNEL32!CloseHandle` at `0x14005f656`
- `KERNEL32!WaitForSingleObjectEx` at `0x14005f3fc`
- `KERNEL32!WaitForSingleObjectEx` at `0x14005f3fc`
- `KERNEL32!ReleaseMutex` at `0x14005f47d`
- `KERNEL32!ReleaseMutex` at `0x14005f5a4`
- `KERNEL32!ReleaseMutex` at `0x14005f640`
- `KERNEL32!ReleaseMutex` at `0x14005f47d`
- `KERNEL32!ReleaseMutex` at `0x14005f5a4`
- `KERNEL32!ReleaseMutex` at `0x14005f640`
- `KERNEL32!GetCurrentProcessId` at `0x14005f39d`
- `KERNEL32!GetCurrentProcessId` at `0x14005f39d`
- `KERNEL32!HeapFree` at `0x14005f582`
- `KERNEL32!HeapFree` at `0x14005f582`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
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
0x14005f364  mov     [rsp-8+arg_10], rbx
0x14005f369  push    rbp
0x14005f36a  push    rsi
0x14005f36b  push    rdi
0x14005f36c  push    r14
0x14005f36e  push    r15
0x14005f370  lea     rbp, [rsp-160h]
0x14005f378  sub     rsp, 260h
0x14005f37f  mov     rax, cs:__security_cookie
0x14005f386  xor     rax, rsp
0x14005f389  mov     [rbp+180h+var_30], rax
0x14005f390  mov     r15, rdx
0x14005f393  mov     qword ptr [rdx], 0
0x14005f39a  mov     rbx, rcx
0x14005f39d  call    cs:__imp_GetCurrentProcessId
0x14005f3a3  mov     r14d, 130h
0x14005f3a9  mov     [rsp+280h+var_258], rbx
0x14005f3ae  mov     r9d, eax
0x14005f3b1  mov     [rsp+280h+var_260], r14d; int
0x14005f3b6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14005f3bd  lea     rcx, [rsp+280h+Name]; Buffer
0x14005f3c2  lea     edx, [r14-2Ch]; unsigned __int64
0x14005f3c6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14005f3cb  mov     r9d, 1F0001h; dwDesiredAccess
0x14005f3d1  lea     rdx, [rsp+280h+Name]; lpName
0x14005f3d6  xor     r8d, r8d; dwFlags
0x14005f3d9  xor     ecx, ecx; lpMutexAttributes
0x14005f3db  call    cs:__imp_CreateMutexExW
0x14005f3e1  mov     rbx, rax
0x14005f3e4  test    rax, rax
0x14005f3e7  jnz     short loc_14005F3F3
0x14005f3e9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14005f3ee  jmp     loc_14005F662
0x14005f3f3  xor     r8d, r8d; bAlertable
0x14005f3f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14005f3f9  mov     rcx, rbx; hHandle
0x14005f3fc  call    cs:__imp_WaitForSingleObjectEx
0x14005f402  cmp     eax, 102h
0x14005f407  jz      short loc_14005F419
0x14005f409  test    eax, 0FFFFFF7Fh
0x14005f40e  jnz     loc_14005F6AC
0x14005f414  mov     rdi, rbx
0x14005f417  jmp     short loc_14005F41B
0x14005f419  xor     edi, edi
0x14005f41b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14005f420  mov     [rsp+280h+hObject], 0
0x14005f429  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14005f42e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x14005f433  mov     esi, eax
0x14005f435  test    eax, eax
0x14005f437  jns     short loc_14005F4A3
0x14005f439  mov     rcx, [rbp+188h]; this
0x14005f440  mov     r9d, eax; char *
0x14005f443  mov     edx, 66h ; 'f'; void *
0x14005f448  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005f44d  mov     rcx, [rbp+188h]; this
0x14005f454  mov     r9d, esi; char *
0x14005f457  mov     edx, 6Fh ; 'o'; void *
0x14005f45c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005f461  mov     rcx, [rbp+188h]; this
0x14005f468  mov     r9d, esi; char *
0x14005f46b  mov     edx, 12Eh; void *
0x14005f470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005f475  test    rdi, rdi
0x14005f478  jz      short loc_14005F48B
0x14005f47a  mov     rcx, rdi; hMutex
0x14005f47d  call    cs:__imp_ReleaseMutex
0x14005f483  test    eax, eax
0x14005f485  jz      loc_14005F6B9
0x14005f48b  mov     rcx, rbx; hObject
0x14005f48e  call    cs:__imp_CloseHandle
0x14005f494  test    eax, eax
0x14005f496  jz      loc_14005F6CB
0x14005f49c  mov     eax, esi
0x14005f49e  jmp     loc_14005F662
0x14005f4a3  mov     rax, [rsp+280h+hObject]
0x14005f4a8  lea     rcx, ds:0[rax*4]
0x14005f4b0  test    rcx, rcx
0x14005f4b3  jz      short loc_14005F4C3
0x14005f4b5  mov     [r15], rcx
0x14005f4b8  mov     eax, [rcx]
0x14005f4ba  inc     eax
0x14005f4bc  mov     [rcx], eax
0x14005f4be  jmp     loc_14005F638
0x14005f4c3  mov     rdx, r14; dwBytes
0x14005f4c6  mov     qword ptr [r15], 0
0x14005f4cd  mov     ecx, 8; dwFlags
0x14005f4d2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14005f4d7  mov     r14, rax
0x14005f4da  test    rax, rax
0x14005f4dd  jnz     short loc_14005F4FD
0x14005f4df  mov     rcx, [rbp+188h]; this
0x14005f4e6  mov     esi, 8007000Eh
0x14005f4eb  mov     r9d, esi; char *
0x14005f4ee  mov     edx, 14Bh; void *
0x14005f4f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005f4f8  jmp     loc_14005F588
0x14005f4fd  xorps   xmm0, xmm0
0x14005f500  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14005f506  test    r14b, 3
0x14005f50a  jnz     loc_14005F6DD
0x14005f510  mov     r9, r14
0x14005f513  lea     rdx, [rsp+280h+Name]; wchar_t *
0x14005f518  shr     r9, 2; unsigned __int64
0x14005f51c  lea     rcx, [rsp+280h+hObject]; this
0x14005f521  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x14005f526  mov     esi, eax
0x14005f528  test    eax, eax
0x14005f52a  jns     loc_14005F5C8
0x14005f530  mov     rcx, [rbp+188h]; this
0x14005f537  mov     r9d, eax; char *
0x14005f53a  mov     edx, 14Eh; void *
0x14005f53f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005f544  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14005f549  test    rcx, rcx
0x14005f54c  jz      short loc_14005F55C
0x14005f54e  call    cs:__imp_CloseHandle
0x14005f554  test    eax, eax
0x14005f556  jz      loc_14005F6E3
0x14005f55c  mov     rcx, [rsp+280h+hObject]; hObject
0x14005f561  test    rcx, rcx
0x14005f564  jz      short loc_14005F574
0x14005f566  call    cs:__imp_CloseHandle
0x14005f56c  test    eax, eax
0x14005f56e  jz      loc_14005F6F5
0x14005f574  call    cs:__imp_GetProcessHeap
0x14005f57a  mov     r8, r14; lpMem
0x14005f57d  xor     edx, edx; dwFlags
0x14005f57f  mov     rcx, rax; hHeap
0x14005f582  call    cs:__imp_HeapFree
0x14005f588  mov     rcx, [rbp+188h]; this
0x14005f58f  mov     r9d, esi; char *
0x14005f592  mov     edx, 137h; void *
0x14005f597  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005f59c  test    rdi, rdi
0x14005f59f  jz      short loc_14005F5B2
0x14005f5a1  mov     rcx, rdi; hMutex
0x14005f5a4  call    cs:__imp_ReleaseMutex
0x14005f5aa  test    eax, eax
0x14005f5ac  jz      loc_14005F707
0x14005f5b2  mov     rcx, rbx; hObject
0x14005f5b5  call    cs:__imp_CloseHandle
0x14005f5bb  test    eax, eax
0x14005f5bd  jz      loc_14005F69A
0x14005f5c3  jmp     loc_14005F49C
0x14005f5c8  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14005f5cd  lea     rcx, [r14+28h]; void *
0x14005f5d1  mov     dword ptr [r14], 1
0x14005f5d8  xor     edx, edx; Val
0x14005f5da  mov     [r14+8], rbx
0x14005f5de  mov     r8d, 108h; Size
0x14005f5e4  movdqu  xmmword ptr [r14+10h], xmm0
0x14005f5ea  call    memset_0
0x14005f5ef  xor     eax, eax
0x14005f5f1  lea     rcx, [r14+28h]; this
0x14005f5f5  mov     [r14+20h], rax
0x14005f5f9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14005f5fe  lea     rbx, [r14+0E8h]
0x14005f605  xor     r8d, r8d; Flags
0x14005f608  mov     rcx, rbx; lpCriticalSection
0x14005f60b  xor     edx, edx; dwSpinCount
0x14005f60d  call    cs:__imp_InitializeCriticalSectionEx
0x14005f613  mov     qword ptr [rbx+28h], 0
0x14005f61b  mov     qword ptr [rbx+30h], 0
0x14005f623  mov     qword ptr [rbx+38h], 0
0x14005f62b  mov     qword ptr [rbx+40h], 0
0x14005f633  xor     ebx, ebx
0x14005f635  mov     [r15], r14
0x14005f638  test    rdi, rdi
0x14005f63b  jz      short loc_14005F64E
0x14005f63d  mov     rcx, rdi; hMutex
0x14005f640  call    cs:__imp_ReleaseMutex
0x14005f646  test    eax, eax
0x14005f648  jz      loc_14005F719
0x14005f64e  test    rbx, rbx
0x14005f651  jz      short loc_14005F660
0x14005f653  mov     rcx, rbx; hObject
0x14005f656  call    cs:__imp_CloseHandle
0x14005f65c  test    eax, eax
0x14005f65e  jz      short loc_14005F688
0x14005f660  xor     eax, eax
0x14005f662  mov     rcx, [rbp+180h+var_30]
0x14005f669  xor     rcx, rsp; StackCookie
0x14005f66c  call    __security_check_cookie
0x14005f671  mov     rbx, [rsp+280h+arg_10]
0x14005f679  add     rsp, 260h
0x14005f680  pop     r15
0x14005f682  pop     r14
0x14005f684  pop     rdi
0x14005f685  pop     rsi
0x14005f686  pop     rbp
0x14005f687  retn
0x14005f688  mov     rcx, [rbp+188h]; this
0x14005f68f  mov     edx, 0A0Bh; void *
0x14005f694  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14005f69a  mov     rcx, [rbp+188h]; this
0x14005f6a1  mov     edx, 0A0Bh; void *
0x14005f6a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14005f6ac  mov     rcx, [rbp+188h]; this
0x14005f6b3  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14005f6b9  mov     rcx, [rbp+188h]; this
0x14005f6c0  mov     edx, 0A15h; void *
0x14005f6c5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14005f6cb  mov     rcx, [rbp+188h]; this
0x14005f6d2  mov     edx, 0A0Bh; void *
0x14005f6d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14005f6dd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14005f6e3  mov     rcx, [rbp+188h]; this
0x14005f6ea  mov     edx, 0A0Bh; void *
0x14005f6ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14005f6f5  mov     rcx, [rbp+188h]; this
0x14005f6fc  mov     edx, 0A0Bh; void *
0x14005f701  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14005f707  mov     rcx, [rbp+188h]; this
0x14005f70e  mov     edx, 0A15h; void *
0x14005f713  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14005f719  mov     rcx, [rbp+188h]; this
0x14005f720  mov     edx, 0A15h; void *
0x14005f725  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
