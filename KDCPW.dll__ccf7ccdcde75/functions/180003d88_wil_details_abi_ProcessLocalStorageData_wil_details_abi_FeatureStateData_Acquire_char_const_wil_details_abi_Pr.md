# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003d88`
- end: `0x18000414f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004564`

## callees

- `0x180001630`
- `0x180001f88`
- `0x180003140`
- `0x180003d88`
- `0x180004158`
- `0x1800047b8`
- `0x180005258`
- `0x1800061a8`
- `0x180007bd4`
- `0x18000809c`
- `0x1800085f8`
- `0x180008eac`
- `0x180008ebc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003dff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003dff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003e20`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003e20`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ea1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004064`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ea1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003fc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004064`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004031`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004031`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003dc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003dc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003eb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000407a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003eb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000407a`

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
0x180003d88  mov     [rsp-8+arg_10], rbx
0x180003d8d  push    rbp
0x180003d8e  push    rsi
0x180003d8f  push    rdi
0x180003d90  push    r14
0x180003d92  push    r15
0x180003d94  lea     rbp, [rsp-160h]
0x180003d9c  sub     rsp, 260h
0x180003da3  mov     rax, cs:__security_cookie
0x180003daa  xor     rax, rsp
0x180003dad  mov     [rbp+180h+var_30], rax
0x180003db4  mov     r15, rdx
0x180003db7  mov     qword ptr [rdx], 0
0x180003dbe  mov     rbx, rcx
0x180003dc1  call    cs:__imp_GetCurrentProcessId
0x180003dc7  mov     r14d, 130h
0x180003dcd  mov     [rsp+280h+var_258], rbx
0x180003dd2  mov     r9d, eax
0x180003dd5  mov     [rsp+280h+var_260], r14d; int
0x180003dda  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003de1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003de6  lea     edx, [r14-2Ch]; unsigned __int64
0x180003dea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003def  mov     r9d, 1F0001h; dwDesiredAccess
0x180003df5  lea     rdx, [rsp+280h+Name]; lpName
0x180003dfa  xor     r8d, r8d; dwFlags
0x180003dfd  xor     ecx, ecx; lpMutexAttributes
0x180003dff  call    cs:__imp_CreateMutexExW
0x180003e05  mov     rbx, rax
0x180003e08  test    rax, rax
0x180003e0b  jnz     short loc_180003E17
0x180003e0d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003e12  jmp     loc_180004086
0x180003e17  xor     r8d, r8d; bAlertable
0x180003e1a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003e1d  mov     rcx, rbx; hHandle
0x180003e20  call    cs:__imp_WaitForSingleObjectEx
0x180003e26  cmp     eax, 102h
0x180003e2b  jz      short loc_180003E3D
0x180003e2d  test    eax, 0FFFFFF7Fh
0x180003e32  jnz     loc_1800040D0
0x180003e38  mov     rdi, rbx
0x180003e3b  jmp     short loc_180003E3F
0x180003e3d  xor     edi, edi
0x180003e3f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003e44  mov     [rsp+280h+hObject], 0
0x180003e4d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003e52  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003e57  mov     esi, eax
0x180003e59  test    eax, eax
0x180003e5b  jns     short loc_180003EC7
0x180003e5d  mov     rcx, [rbp+188h]; this
0x180003e64  mov     r9d, eax; char *
0x180003e67  mov     edx, 66h ; 'f'; void *
0x180003e6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e71  mov     rcx, [rbp+188h]; this
0x180003e78  mov     r9d, esi; char *
0x180003e7b  mov     edx, 6Fh ; 'o'; void *
0x180003e80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e85  mov     rcx, [rbp+188h]; this
0x180003e8c  mov     r9d, esi; char *
0x180003e8f  mov     edx, 12Eh; void *
0x180003e94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e99  test    rdi, rdi
0x180003e9c  jz      short loc_180003EAF
0x180003e9e  mov     rcx, rdi; hMutex
0x180003ea1  call    cs:__imp_ReleaseMutex
0x180003ea7  test    eax, eax
0x180003ea9  jz      loc_1800040DD
0x180003eaf  mov     rcx, rbx; hObject
0x180003eb2  call    cs:__imp_CloseHandle
0x180003eb8  test    eax, eax
0x180003eba  jz      loc_1800040EF
0x180003ec0  mov     eax, esi
0x180003ec2  jmp     loc_180004086
0x180003ec7  mov     rax, [rsp+280h+hObject]
0x180003ecc  lea     rcx, ds:0[rax*4]
0x180003ed4  test    rcx, rcx
0x180003ed7  jz      short loc_180003EE7
0x180003ed9  mov     [r15], rcx
0x180003edc  mov     eax, [rcx]
0x180003ede  inc     eax
0x180003ee0  mov     [rcx], eax
0x180003ee2  jmp     loc_18000405C
0x180003ee7  mov     rdx, r14; dwBytes
0x180003eea  mov     qword ptr [r15], 0
0x180003ef1  mov     ecx, 8; dwFlags
0x180003ef6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003efb  mov     r14, rax
0x180003efe  test    rax, rax
0x180003f01  jnz     short loc_180003F21
0x180003f03  mov     rcx, [rbp+188h]; this
0x180003f0a  mov     esi, 8007000Eh
0x180003f0f  mov     r9d, esi; char *
0x180003f12  mov     edx, 14Bh; void *
0x180003f17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f1c  jmp     loc_180003FAC
0x180003f21  xorps   xmm0, xmm0
0x180003f24  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003f2a  test    r14b, 3
0x180003f2e  jnz     loc_180004101
0x180003f34  mov     r9, r14
0x180003f37  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003f3c  shr     r9, 2; unsigned __int64
0x180003f40  lea     rcx, [rsp+280h+hObject]; this
0x180003f45  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003f4a  mov     esi, eax
0x180003f4c  test    eax, eax
0x180003f4e  jns     loc_180003FEC
0x180003f54  mov     rcx, [rbp+188h]; this
0x180003f5b  mov     r9d, eax; char *
0x180003f5e  mov     edx, 14Eh; void *
0x180003f63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f68  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003f6d  test    rcx, rcx
0x180003f70  jz      short loc_180003F80
0x180003f72  call    cs:__imp_CloseHandle
0x180003f78  test    eax, eax
0x180003f7a  jz      loc_180004107
0x180003f80  mov     rcx, [rsp+280h+hObject]; hObject
0x180003f85  test    rcx, rcx
0x180003f88  jz      short loc_180003F98
0x180003f8a  call    cs:__imp_CloseHandle
0x180003f90  test    eax, eax
0x180003f92  jz      loc_180004119
0x180003f98  call    cs:__imp_GetProcessHeap
0x180003f9e  mov     r8, r14; lpMem
0x180003fa1  xor     edx, edx; dwFlags
0x180003fa3  mov     rcx, rax; hHeap
0x180003fa6  call    cs:__imp_HeapFree
0x180003fac  mov     rcx, [rbp+188h]; this
0x180003fb3  mov     r9d, esi; char *
0x180003fb6  mov     edx, 137h; void *
0x180003fbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fc0  test    rdi, rdi
0x180003fc3  jz      short loc_180003FD6
0x180003fc5  mov     rcx, rdi; hMutex
0x180003fc8  call    cs:__imp_ReleaseMutex
0x180003fce  test    eax, eax
0x180003fd0  jz      loc_18000412B
0x180003fd6  mov     rcx, rbx; hObject
0x180003fd9  call    cs:__imp_CloseHandle
0x180003fdf  test    eax, eax
0x180003fe1  jz      loc_1800040BE
0x180003fe7  jmp     loc_180003EC0
0x180003fec  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003ff1  lea     rcx, [r14+28h]; void *
0x180003ff5  mov     dword ptr [r14], 1
0x180003ffc  xor     edx, edx; Val
0x180003ffe  mov     [r14+8], rbx
0x180004002  mov     r8d, 108h; Size
0x180004008  movdqu  xmmword ptr [r14+10h], xmm0
0x18000400e  call    memset_0
0x180004013  xor     eax, eax
0x180004015  lea     rcx, [r14+28h]; this
0x180004019  mov     [r14+20h], rax
0x18000401d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004022  lea     rbx, [r14+0E8h]
0x180004029  xor     r8d, r8d; Flags
0x18000402c  mov     rcx, rbx; lpCriticalSection
0x18000402f  xor     edx, edx; dwSpinCount
0x180004031  call    cs:__imp_InitializeCriticalSectionEx
0x180004037  mov     qword ptr [rbx+28h], 0
0x18000403f  mov     qword ptr [rbx+30h], 0
0x180004047  mov     qword ptr [rbx+38h], 0
0x18000404f  mov     qword ptr [rbx+40h], 0
0x180004057  xor     ebx, ebx
0x180004059  mov     [r15], r14
0x18000405c  test    rdi, rdi
0x18000405f  jz      short loc_180004072
0x180004061  mov     rcx, rdi; hMutex
0x180004064  call    cs:__imp_ReleaseMutex
0x18000406a  test    eax, eax
0x18000406c  jz      loc_18000413D
0x180004072  test    rbx, rbx
0x180004075  jz      short loc_180004084
0x180004077  mov     rcx, rbx; hObject
0x18000407a  call    cs:__imp_CloseHandle
0x180004080  test    eax, eax
0x180004082  jz      short loc_1800040AC
0x180004084  xor     eax, eax
0x180004086  mov     rcx, [rbp+180h+var_30]
0x18000408d  xor     rcx, rsp; StackCookie
0x180004090  call    __security_check_cookie
0x180004095  mov     rbx, [rsp+280h+arg_10]
0x18000409d  add     rsp, 260h
0x1800040a4  pop     r15
0x1800040a6  pop     r14
0x1800040a8  pop     rdi
0x1800040a9  pop     rsi
0x1800040aa  pop     rbp
0x1800040ab  retn
0x1800040ac  mov     rcx, [rbp+188h]; this
0x1800040b3  mov     edx, 0A0Bh; void *
0x1800040b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040be  mov     rcx, [rbp+188h]; this
0x1800040c5  mov     edx, 0A0Bh; void *
0x1800040ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040d0  mov     rcx, [rbp+188h]; this
0x1800040d7  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800040dd  mov     rcx, [rbp+188h]; this
0x1800040e4  mov     edx, 0A15h; void *
0x1800040e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800040ef  mov     rcx, [rbp+188h]; this
0x1800040f6  mov     edx, 0A0Bh; void *
0x1800040fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004101  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004107  mov     rcx, [rbp+188h]; this
0x18000410e  mov     edx, 0A0Bh; void *
0x180004113  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004119  mov     rcx, [rbp+188h]; this
0x180004120  mov     edx, 0A0Bh; void *
0x180004125  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000412b  mov     rcx, [rbp+188h]; this
0x180004132  mov     edx, 0A15h; void *
0x180004137  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000413d  mov     rcx, [rbp+188h]; this
0x180004144  mov     edx, 0A15h; void *
0x180004149  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
