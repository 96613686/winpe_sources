# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004d38`
- end: `0x18000510b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800053e4`

## callees

- `0x180001d40`
- `0x180002a28`
- `0x180003ec4`
- `0x180004d38`
- `0x180005114`
- `0x180005638`
- `0x180005f58`
- `0x180006c38`
- `0x1800083b4`
- `0x180008ea8`
- `0x18000930c`
- `0x180009bbc`
- `0x180009bcc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000502a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000502a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d71`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004daf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004daf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004dd0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004dd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e51`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005014`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e51`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005014`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004fe1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004fe1`

## string_xrefs

- `0x180005087`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v17; // r8
  const char *v18; // r9
  __int64 v19; // r8
  const char *v20; // r9
  _DWORD *v21; // rcx
  unsigned __int64 v22; // rax
  wil::details::in1diag3 *v23; // rcx
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  HANDLE ProcessHeap; // rax
  __int64 v34; // r8
  const char *v35; // r9
  __int64 v36; // r8
  const char *v37; // r9
  __int128 v38; // xmm0
  __int64 v39; // r8
  const char *v40; // r9
  __int64 v41; // r8
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
      wil::details::in1diag3::FailFast_Unexpected(
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
0x180004d38  mov     [rsp-8+arg_10], rbx
0x180004d3d  push    rbp
0x180004d3e  push    rsi
0x180004d3f  push    rdi
0x180004d40  push    r14
0x180004d42  push    r15
0x180004d44  lea     rbp, [rsp-160h]
0x180004d4c  sub     rsp, 260h
0x180004d53  mov     rax, cs:__security_cookie
0x180004d5a  xor     rax, rsp
0x180004d5d  mov     [rbp+180h+var_30], rax
0x180004d64  mov     r15, rdx
0x180004d67  mov     qword ptr [rdx], 0
0x180004d6e  mov     rbx, rcx
0x180004d71  call    cs:__imp_GetCurrentProcessId
0x180004d77  mov     r14d, 130h
0x180004d7d  mov     [rsp+280h+var_258], rbx
0x180004d82  mov     r9d, eax
0x180004d85  mov     [rsp+280h+var_260], r14d; int
0x180004d8a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004d91  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004d96  lea     edx, [r14-2Ch]; unsigned __int64
0x180004d9a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004d9f  mov     r9d, 1F0001h; dwDesiredAccess
0x180004da5  lea     rdx, [rsp+280h+Name]; lpName
0x180004daa  xor     r8d, r8d; dwFlags
0x180004dad  xor     ecx, ecx; lpMutexAttributes
0x180004daf  call    cs:__imp_CreateMutexExW
0x180004db5  mov     rbx, rax
0x180004db8  test    rax, rax
0x180004dbb  jnz     short loc_180004DC7
0x180004dbd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004dc2  jmp     loc_180005036
0x180004dc7  xor     r8d, r8d; bAlertable
0x180004dca  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004dcd  mov     rcx, rbx; hHandle
0x180004dd0  call    cs:__imp_WaitForSingleObjectEx
0x180004dd6  cmp     eax, 102h
0x180004ddb  jz      short loc_180004DED
0x180004ddd  test    eax, 0FFFFFF7Fh
0x180004de2  jnz     loc_180005080
0x180004de8  mov     rdi, rbx
0x180004deb  jmp     short loc_180004DEF
0x180004ded  xor     edi, edi
0x180004def  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004df4  mov     [rsp+280h+hObject], 0
0x180004dfd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004e02  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004e07  mov     esi, eax
0x180004e09  test    eax, eax
0x180004e0b  jns     short loc_180004E77
0x180004e0d  mov     rcx, [rbp+188h]; this
0x180004e14  mov     r9d, eax; char *
0x180004e17  mov     edx, 66h ; 'f'; void *
0x180004e1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e21  mov     rcx, [rbp+188h]; this
0x180004e28  mov     r9d, esi; char *
0x180004e2b  mov     edx, 6Fh ; 'o'; void *
0x180004e30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e35  mov     rcx, [rbp+188h]; this
0x180004e3c  mov     r9d, esi; char *
0x180004e3f  mov     edx, 12Eh; void *
0x180004e44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e49  test    rdi, rdi
0x180004e4c  jz      short loc_180004E5F
0x180004e4e  mov     rcx, rdi; hMutex
0x180004e51  call    cs:__imp_ReleaseMutex
0x180004e57  test    eax, eax
0x180004e59  jz      loc_180005099
0x180004e5f  mov     rcx, rbx; hObject
0x180004e62  call    cs:__imp_CloseHandle
0x180004e68  test    eax, eax
0x180004e6a  jz      loc_1800050AB
0x180004e70  mov     eax, esi
0x180004e72  jmp     loc_180005036
0x180004e77  mov     rax, [rsp+280h+hObject]
0x180004e7c  lea     rcx, ds:0[rax*4]
0x180004e84  test    rcx, rcx
0x180004e87  jz      short loc_180004E97
0x180004e89  mov     [r15], rcx
0x180004e8c  mov     eax, [rcx]
0x180004e8e  inc     eax
0x180004e90  mov     [rcx], eax
0x180004e92  jmp     loc_18000500C
0x180004e97  mov     rdx, r14; dwBytes
0x180004e9a  mov     qword ptr [r15], 0
0x180004ea1  mov     ecx, 8; dwFlags
0x180004ea6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004eab  mov     r14, rax
0x180004eae  test    rax, rax
0x180004eb1  jnz     short loc_180004ED1
0x180004eb3  mov     rcx, [rbp+188h]; this
0x180004eba  mov     esi, 8007000Eh
0x180004ebf  mov     r9d, esi; char *
0x180004ec2  mov     edx, 14Bh; void *
0x180004ec7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ecc  jmp     loc_180004F5C
0x180004ed1  xorps   xmm0, xmm0
0x180004ed4  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004eda  test    r14b, 3
0x180004ede  jnz     loc_1800050BD
0x180004ee4  mov     r9, r14
0x180004ee7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004eec  shr     r9, 2; unsigned __int64
0x180004ef0  lea     rcx, [rsp+280h+hObject]; this
0x180004ef5  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004efa  mov     esi, eax
0x180004efc  test    eax, eax
0x180004efe  jns     loc_180004F9C
0x180004f04  mov     rcx, [rbp+188h]; this
0x180004f0b  mov     r9d, eax; char *
0x180004f0e  mov     edx, 14Eh; void *
0x180004f13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f18  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004f1d  test    rcx, rcx
0x180004f20  jz      short loc_180004F30
0x180004f22  call    cs:__imp_CloseHandle
0x180004f28  test    eax, eax
0x180004f2a  jz      loc_1800050C3
0x180004f30  mov     rcx, [rsp+280h+hObject]; hObject
0x180004f35  test    rcx, rcx
0x180004f38  jz      short loc_180004F48
0x180004f3a  call    cs:__imp_CloseHandle
0x180004f40  test    eax, eax
0x180004f42  jz      loc_1800050D5
0x180004f48  call    cs:__imp_GetProcessHeap
0x180004f4e  mov     r8, r14; lpMem
0x180004f51  xor     edx, edx; dwFlags
0x180004f53  mov     rcx, rax; hHeap
0x180004f56  call    cs:__imp_HeapFree
0x180004f5c  mov     rcx, [rbp+188h]; this
0x180004f63  mov     r9d, esi; char *
0x180004f66  mov     edx, 137h; void *
0x180004f6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f70  test    rdi, rdi
0x180004f73  jz      short loc_180004F86
0x180004f75  mov     rcx, rdi; hMutex
0x180004f78  call    cs:__imp_ReleaseMutex
0x180004f7e  test    eax, eax
0x180004f80  jz      loc_1800050E7
0x180004f86  mov     rcx, rbx; hObject
0x180004f89  call    cs:__imp_CloseHandle
0x180004f8f  test    eax, eax
0x180004f91  jz      loc_18000506E
0x180004f97  jmp     loc_180004E70
0x180004f9c  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004fa1  lea     rcx, [r14+28h]; void *
0x180004fa5  mov     dword ptr [r14], 1
0x180004fac  xor     edx, edx; Val
0x180004fae  mov     [r14+8], rbx
0x180004fb2  mov     r8d, 108h; Size
0x180004fb8  movdqu  xmmword ptr [r14+10h], xmm0
0x180004fbe  call    memset_0
0x180004fc3  xor     eax, eax
0x180004fc5  lea     rcx, [r14+28h]; this
0x180004fc9  mov     [r14+20h], rax
0x180004fcd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004fd2  lea     rbx, [r14+0E8h]
0x180004fd9  xor     r8d, r8d; Flags
0x180004fdc  mov     rcx, rbx; lpCriticalSection
0x180004fdf  xor     edx, edx; dwSpinCount
0x180004fe1  call    cs:__imp_InitializeCriticalSectionEx
0x180004fe7  mov     qword ptr [rbx+28h], 0
0x180004fef  mov     qword ptr [rbx+30h], 0
0x180004ff7  mov     qword ptr [rbx+38h], 0
0x180004fff  mov     qword ptr [rbx+40h], 0
0x180005007  xor     ebx, ebx
0x180005009  mov     [r15], r14
0x18000500c  test    rdi, rdi
0x18000500f  jz      short loc_180005022
0x180005011  mov     rcx, rdi; hMutex
0x180005014  call    cs:__imp_ReleaseMutex
0x18000501a  test    eax, eax
0x18000501c  jz      loc_1800050F9
0x180005022  test    rbx, rbx
0x180005025  jz      short loc_180005034
0x180005027  mov     rcx, rbx; hObject
0x18000502a  call    cs:__imp_CloseHandle
0x180005030  test    eax, eax
0x180005032  jz      short loc_18000505C
0x180005034  xor     eax, eax
0x180005036  mov     rcx, [rbp+180h+var_30]
0x18000503d  xor     rcx, rsp; StackCookie
0x180005040  call    __security_check_cookie
0x180005045  mov     rbx, [rsp+280h+arg_10]
0x18000504d  add     rsp, 260h
0x180005054  pop     r15
0x180005056  pop     r14
0x180005058  pop     rdi
0x180005059  pop     rsi
0x18000505a  pop     rbp
0x18000505b  retn
0x18000505c  mov     rcx, [rbp+188h]; this
0x180005063  mov     edx, 0A0Bh; void *
0x180005068  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000506e  mov     rcx, [rbp+188h]; this
0x180005075  mov     edx, 0A0Bh; void *
0x18000507a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005080  mov     rcx, [rbp+188h]; this
0x180005087  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000508e  mov     edx, 0E01h; void *
0x180005093  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005099  mov     rcx, [rbp+188h]; this
0x1800050a0  mov     edx, 0A15h; void *
0x1800050a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050ab  mov     rcx, [rbp+188h]; this
0x1800050b2  mov     edx, 0A0Bh; void *
0x1800050b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050bd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800050c3  mov     rcx, [rbp+188h]; this
0x1800050ca  mov     edx, 0A0Bh; void *
0x1800050cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050d5  mov     rcx, [rbp+188h]; this
0x1800050dc  mov     edx, 0A0Bh; void *
0x1800050e1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050e7  mov     rcx, [rbp+188h]; this
0x1800050ee  mov     edx, 0A15h; void *
0x1800050f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800050f9  mov     rcx, [rbp+188h]; this
0x180005100  mov     edx, 0A15h; void *
0x180005105  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
