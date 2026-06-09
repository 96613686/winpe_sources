# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004df8`
- end: `0x1800051e9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800054e4`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x180003de0`
- `0x180004df8`
- `0x1800051f0`
- `0x180005748`
- `0x1800060a0`
- `0x180006db4`
- `0x1800085bc`
- `0x18000940c`
- `0x180009ccc`
- `0x180009cdc`
- `0x18000a654`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000502b`
- `KERNEL32!GetProcessHeap` at `0x18000502b`
- `KERNEL32!GetCurrentProcessId` at `0x180004e31`
- `KERNEL32!GetCurrentProcessId` at `0x180004e31`
- `KERNEL32!CreateMutexExW` at `0x180004e6f`
- `KERNEL32!CreateMutexExW` at `0x180004e6f`
- `KERNEL32!CloseHandle` at `0x180004f37`
- `KERNEL32!CloseHandle` at `0x180005005`
- `KERNEL32!CloseHandle` at `0x18000501d`
- `KERNEL32!CloseHandle` at `0x180005073`
- `KERNEL32!CloseHandle` at `0x180005114`
- `KERNEL32!CloseHandle` at `0x180004f37`
- `KERNEL32!CloseHandle` at `0x180005005`
- `KERNEL32!CloseHandle` at `0x18000501d`
- `KERNEL32!CloseHandle` at `0x180005073`
- `KERNEL32!CloseHandle` at `0x180005114`
- `KERNEL32!WaitForSingleObjectEx` at `0x180004e90`
- `KERNEL32!WaitForSingleObjectEx` at `0x180004e90`
- `KERNEL32!ReleaseMutex` at `0x180004f26`
- `KERNEL32!ReleaseMutex` at `0x180005062`
- `KERNEL32!ReleaseMutex` at `0x1800050fe`
- `KERNEL32!ReleaseMutex` at `0x180004f26`
- `KERNEL32!ReleaseMutex` at `0x180005062`
- `KERNEL32!ReleaseMutex` at `0x1800050fe`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800050cb`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800050cb`
- `KERNEL32!HeapFree` at `0x180005039`
- `KERNEL32!HeapFree` at `0x180005039`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
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
                    pszDest,
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
          pszDest,
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
0x180004df8  mov     [rsp-8+arg_10], rbx
0x180004dfd  push    rbp
0x180004dfe  push    rsi
0x180004dff  push    rdi
0x180004e00  push    r14
0x180004e02  push    r15
0x180004e04  lea     rbp, [rsp-160h]
0x180004e0c  sub     rsp, 260h
0x180004e13  mov     rax, cs:__security_cookie
0x180004e1a  xor     rax, rsp
0x180004e1d  mov     [rbp+180h+var_30], rax
0x180004e24  mov     r15, rdx
0x180004e27  mov     qword ptr [rdx], 0
0x180004e2e  mov     rbx, rcx
0x180004e31  call    cs:__imp_GetCurrentProcessId
0x180004e37  mov     r14d, 130h
0x180004e3d  mov     [rsp+280h+var_258], rbx
0x180004e42  mov     r9d, eax
0x180004e45  mov     [rsp+280h+var_260], r14d; int
0x180004e4a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004e51  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180004e56  lea     edx, [r14-2Ch]; cchDest
0x180004e5a  call    StringCchPrintfW
0x180004e5f  mov     r9d, 1F0001h; dwDesiredAccess
0x180004e65  lea     rdx, [rsp+280h+pszDest]; lpName
0x180004e6a  xor     r8d, r8d; dwFlags
0x180004e6d  xor     ecx, ecx; lpMutexAttributes
0x180004e6f  call    cs:__imp_CreateMutexExW
0x180004e75  mov     rbx, rax
0x180004e78  test    rax, rax
0x180004e7b  jnz     short loc_180004E87
0x180004e7d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004e82  jmp     loc_180005120
0x180004e87  xor     r8d, r8d; bAlertable
0x180004e8a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004e8d  mov     rcx, rbx; hHandle
0x180004e90  call    cs:__imp_WaitForSingleObjectEx
0x180004e96  cmp     eax, 102h
0x180004e9b  jz      short loc_180004EAD
0x180004e9d  test    eax, 0FFFFFF7Fh
0x180004ea2  jnz     loc_18000516A
0x180004ea8  mov     rdi, rbx
0x180004eab  jmp     short loc_180004EAF
0x180004ead  xor     edi, edi
0x180004eaf  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004eb4  mov     [rsp+280h+hObject], 0
0x180004ebd  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180004ec2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004ec7  mov     esi, eax
0x180004ec9  test    eax, eax
0x180004ecb  jns     short loc_180004F4C
0x180004ecd  mov     rcx, [rbp+188h]; this
0x180004ed4  lea     r8, aWil; "wil"
0x180004edb  mov     r9d, eax; char *
0x180004ede  mov     edx, 66h ; 'f'; void *
0x180004ee3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ee8  mov     rcx, [rbp+188h]; this
0x180004eef  lea     r8, aWil; "wil"
0x180004ef6  mov     r9d, esi; char *
0x180004ef9  mov     edx, 6Fh ; 'o'; void *
0x180004efe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f03  mov     rcx, [rbp+188h]; this
0x180004f0a  lea     r8, aWil; "wil"
0x180004f11  mov     r9d, esi; char *
0x180004f14  mov     edx, 12Eh; void *
0x180004f19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f1e  test    rdi, rdi
0x180004f21  jz      short loc_180004F34
0x180004f23  mov     rcx, rdi; hMutex
0x180004f26  call    cs:__imp_ReleaseMutex
0x180004f2c  test    eax, eax
0x180004f2e  jz      loc_180005177
0x180004f34  mov     rcx, rbx; hObject
0x180004f37  call    cs:__imp_CloseHandle
0x180004f3d  test    eax, eax
0x180004f3f  jz      loc_180005189
0x180004f45  mov     eax, esi
0x180004f47  jmp     loc_180005120
0x180004f4c  mov     rax, [rsp+280h+hObject]
0x180004f51  lea     rcx, ds:0[rax*4]
0x180004f59  test    rcx, rcx
0x180004f5c  jz      short loc_180004F6C
0x180004f5e  mov     [r15], rcx
0x180004f61  mov     eax, [rcx]
0x180004f63  inc     eax
0x180004f65  mov     [rcx], eax
0x180004f67  jmp     loc_1800050F6
0x180004f6c  mov     rdx, r14; dwBytes
0x180004f6f  mov     qword ptr [r15], 0
0x180004f76  mov     ecx, 8; dwFlags
0x180004f7b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004f80  mov     r14, rax
0x180004f83  test    rax, rax
0x180004f86  jnz     short loc_180004FAD
0x180004f88  mov     rcx, [rbp+188h]; this
0x180004f8f  lea     r8, aWil; "wil"
0x180004f96  mov     esi, 8007000Eh
0x180004f9b  mov     edx, 14Bh; void *
0x180004fa0  mov     r9d, esi; char *
0x180004fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004fa8  jmp     loc_18000503F
0x180004fad  xorps   xmm0, xmm0
0x180004fb0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004fb6  test    r14b, 3
0x180004fba  jnz     loc_18000519B
0x180004fc0  mov     r9, r14
0x180004fc3  lea     rdx, [rsp+280h+pszDest]; unsigned __int16 *
0x180004fc8  shr     r9, 2; unsigned __int64
0x180004fcc  lea     rcx, [rsp+280h+hObject]; this
0x180004fd1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004fd6  mov     esi, eax
0x180004fd8  test    eax, eax
0x180004fda  jns     loc_180005086
0x180004fe0  mov     rcx, [rbp+188h]; this
0x180004fe7  lea     r8, aWil; "wil"
0x180004fee  mov     r9d, eax; char *
0x180004ff1  mov     edx, 14Eh; void *
0x180004ff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ffb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005000  test    rcx, rcx
0x180005003  jz      short loc_180005013
0x180005005  call    cs:__imp_CloseHandle
0x18000500b  test    eax, eax
0x18000500d  jz      loc_1800051A1
0x180005013  mov     rcx, [rsp+280h+hObject]; hObject
0x180005018  test    rcx, rcx
0x18000501b  jz      short loc_18000502B
0x18000501d  call    cs:__imp_CloseHandle
0x180005023  test    eax, eax
0x180005025  jz      loc_1800051B3
0x18000502b  call    cs:__imp_GetProcessHeap
0x180005031  mov     r8, r14; lpMem
0x180005034  xor     edx, edx; dwFlags
0x180005036  mov     rcx, rax; hHeap
0x180005039  call    cs:__imp_HeapFree
0x18000503f  mov     rcx, [rbp+188h]; this
0x180005046  lea     r8, aWil; "wil"
0x18000504d  mov     r9d, esi; char *
0x180005050  mov     edx, 137h; void *
0x180005055  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000505a  test    rdi, rdi
0x18000505d  jz      short loc_180005070
0x18000505f  mov     rcx, rdi; hMutex
0x180005062  call    cs:__imp_ReleaseMutex
0x180005068  test    eax, eax
0x18000506a  jz      loc_1800051C5
0x180005070  mov     rcx, rbx; hObject
0x180005073  call    cs:__imp_CloseHandle
0x180005079  test    eax, eax
0x18000507b  jz      loc_180005158
0x180005081  jmp     loc_180004F45
0x180005086  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000508b  lea     rcx, [r14+28h]; void *
0x18000508f  mov     dword ptr [r14], 1
0x180005096  xor     edx, edx; Val
0x180005098  mov     [r14+8], rbx
0x18000509c  mov     r8d, 108h; Size
0x1800050a2  movdqu  xmmword ptr [r14+10h], xmm0
0x1800050a8  call    memset_0
0x1800050ad  xor     eax, eax
0x1800050af  lea     rcx, [r14+28h]; this
0x1800050b3  mov     [r14+20h], rax
0x1800050b7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800050bc  lea     rbx, [r14+0E8h]
0x1800050c3  xor     r8d, r8d; Flags
0x1800050c6  mov     rcx, rbx; lpCriticalSection
0x1800050c9  xor     edx, edx; dwSpinCount
0x1800050cb  call    cs:__imp_InitializeCriticalSectionEx
0x1800050d1  mov     qword ptr [rbx+28h], 0
0x1800050d9  mov     qword ptr [rbx+30h], 0
0x1800050e1  mov     qword ptr [rbx+38h], 0
0x1800050e9  mov     qword ptr [rbx+40h], 0
0x1800050f1  xor     ebx, ebx
0x1800050f3  mov     [r15], r14
0x1800050f6  test    rdi, rdi
0x1800050f9  jz      short loc_18000510C
0x1800050fb  mov     rcx, rdi; hMutex
0x1800050fe  call    cs:__imp_ReleaseMutex
0x180005104  test    eax, eax
0x180005106  jz      loc_1800051D7
0x18000510c  test    rbx, rbx
0x18000510f  jz      short loc_18000511E
0x180005111  mov     rcx, rbx; hObject
0x180005114  call    cs:__imp_CloseHandle
0x18000511a  test    eax, eax
0x18000511c  jz      short loc_180005146
0x18000511e  xor     eax, eax
0x180005120  mov     rcx, [rbp+180h+var_30]
0x180005127  xor     rcx, rsp; StackCookie
0x18000512a  call    __security_check_cookie
0x18000512f  mov     rbx, [rsp+280h+arg_10]
0x180005137  add     rsp, 260h
0x18000513e  pop     r15
0x180005140  pop     r14
0x180005142  pop     rdi
0x180005143  pop     rsi
0x180005144  pop     rbp
0x180005145  retn
0x180005146  mov     rcx, [rbp+188h]; this
0x18000514d  mov     edx, 0A0Bh; void *
0x180005152  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005158  mov     rcx, [rbp+188h]; this
0x18000515f  mov     edx, 0A0Bh; void *
0x180005164  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000516a  mov     rcx, [rbp+188h]; this
0x180005171  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005177  mov     rcx, [rbp+188h]; this
0x18000517e  mov     edx, 0A15h; void *
0x180005183  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005189  mov     rcx, [rbp+188h]; this
0x180005190  mov     edx, 0A0Bh; void *
0x180005195  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000519b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800051a1  mov     rcx, [rbp+188h]; this
0x1800051a8  mov     edx, 0A0Bh; void *
0x1800051ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051b3  mov     rcx, [rbp+188h]; this
0x1800051ba  mov     edx, 0A0Bh; void *
0x1800051bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051c5  mov     rcx, [rbp+188h]; this
0x1800051cc  mov     edx, 0A15h; void *
0x1800051d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800051d7  mov     rcx, [rbp+188h]; this
0x1800051de  mov     edx, 0A15h; void *
0x1800051e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
