# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800035c0`
- end: `0x180003987`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180003c64`

## callees

- `0x1800029c0`
- `0x1800035c0`
- `0x180003990`
- `0x180003eb8`
- `0x1800047d8`
- `0x1800054b8`
- `0x1800069d4`
- `0x180006fc0`
- `0x1800073a8`
- `0x180007c4c`
- `0x180007c5c`
- `0x18000c4a4`
- `0x18000c560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003658`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003658`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003637`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003637`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003869`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003869`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800036d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003800`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000389c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800036d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003800`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000389c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800035f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800035f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800036ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038b2`

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
0x1800035c0  mov     [rsp-8+arg_10], rbx
0x1800035c5  push    rbp
0x1800035c6  push    rsi
0x1800035c7  push    rdi
0x1800035c8  push    r14
0x1800035ca  push    r15
0x1800035cc  lea     rbp, [rsp-160h]
0x1800035d4  sub     rsp, 260h
0x1800035db  mov     rax, cs:__security_cookie
0x1800035e2  xor     rax, rsp
0x1800035e5  mov     [rbp+180h+var_30], rax
0x1800035ec  mov     r15, rdx
0x1800035ef  mov     qword ptr [rdx], 0
0x1800035f6  mov     rbx, rcx
0x1800035f9  call    cs:__imp_GetCurrentProcessId
0x1800035ff  mov     r14d, 130h
0x180003605  mov     [rsp+280h+var_258], rbx
0x18000360a  mov     r9d, eax
0x18000360d  mov     [rsp+280h+var_260], r14d; int
0x180003612  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003619  lea     rcx, [rsp+280h+Name]; Buffer
0x18000361e  lea     edx, [r14-2Ch]; unsigned __int64
0x180003622  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003627  mov     r9d, 1F0001h; dwDesiredAccess
0x18000362d  lea     rdx, [rsp+280h+Name]; lpName
0x180003632  xor     r8d, r8d; dwFlags
0x180003635  xor     ecx, ecx; lpMutexAttributes
0x180003637  call    cs:__imp_CreateMutexExW
0x18000363d  mov     rbx, rax
0x180003640  test    rax, rax
0x180003643  jnz     short loc_18000364F
0x180003645  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000364a  jmp     loc_1800038BE
0x18000364f  xor     r8d, r8d; bAlertable
0x180003652  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003655  mov     rcx, rbx; hHandle
0x180003658  call    cs:__imp_WaitForSingleObjectEx
0x18000365e  cmp     eax, 102h
0x180003663  jz      short loc_180003675
0x180003665  test    eax, 0FFFFFF7Fh
0x18000366a  jnz     loc_180003908
0x180003670  mov     rdi, rbx
0x180003673  jmp     short loc_180003677
0x180003675  xor     edi, edi
0x180003677  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000367c  mov     [rsp+280h+hObject], 0
0x180003685  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000368a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000368f  mov     esi, eax
0x180003691  test    eax, eax
0x180003693  jns     short loc_1800036FF
0x180003695  mov     rcx, [rbp+188h]; this
0x18000369c  mov     r9d, eax; char *
0x18000369f  mov     edx, 66h ; 'f'; void *
0x1800036a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800036a9  mov     rcx, [rbp+188h]; this
0x1800036b0  mov     r9d, esi; char *
0x1800036b3  mov     edx, 6Fh ; 'o'; void *
0x1800036b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800036bd  mov     rcx, [rbp+188h]; this
0x1800036c4  mov     r9d, esi; char *
0x1800036c7  mov     edx, 12Eh; void *
0x1800036cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800036d1  test    rdi, rdi
0x1800036d4  jz      short loc_1800036E7
0x1800036d6  mov     rcx, rdi; hMutex
0x1800036d9  call    cs:__imp_ReleaseMutex
0x1800036df  test    eax, eax
0x1800036e1  jz      loc_180003915
0x1800036e7  mov     rcx, rbx; hObject
0x1800036ea  call    cs:__imp_CloseHandle
0x1800036f0  test    eax, eax
0x1800036f2  jz      loc_180003927
0x1800036f8  mov     eax, esi
0x1800036fa  jmp     loc_1800038BE
0x1800036ff  mov     rax, [rsp+280h+hObject]
0x180003704  lea     rcx, ds:0[rax*4]
0x18000370c  test    rcx, rcx
0x18000370f  jz      short loc_18000371F
0x180003711  mov     [r15], rcx
0x180003714  mov     eax, [rcx]
0x180003716  inc     eax
0x180003718  mov     [rcx], eax
0x18000371a  jmp     loc_180003894
0x18000371f  mov     rdx, r14; dwBytes
0x180003722  mov     qword ptr [r15], 0
0x180003729  mov     ecx, 8; dwFlags
0x18000372e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003733  mov     r14, rax
0x180003736  test    rax, rax
0x180003739  jnz     short loc_180003759
0x18000373b  mov     rcx, [rbp+188h]; this
0x180003742  mov     esi, 8007000Eh
0x180003747  mov     r9d, esi; char *
0x18000374a  mov     edx, 14Bh; void *
0x18000374f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003754  jmp     loc_1800037E4
0x180003759  xorps   xmm0, xmm0
0x18000375c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003762  test    r14b, 3
0x180003766  jnz     loc_180003939
0x18000376c  mov     r9, r14
0x18000376f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003774  shr     r9, 2; unsigned __int64
0x180003778  lea     rcx, [rsp+280h+hObject]; this
0x18000377d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003782  mov     esi, eax
0x180003784  test    eax, eax
0x180003786  jns     loc_180003824
0x18000378c  mov     rcx, [rbp+188h]; this
0x180003793  mov     r9d, eax; char *
0x180003796  mov     edx, 14Eh; void *
0x18000379b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037a0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800037a5  test    rcx, rcx
0x1800037a8  jz      short loc_1800037B8
0x1800037aa  call    cs:__imp_CloseHandle
0x1800037b0  test    eax, eax
0x1800037b2  jz      loc_18000393F
0x1800037b8  mov     rcx, [rsp+280h+hObject]; hObject
0x1800037bd  test    rcx, rcx
0x1800037c0  jz      short loc_1800037D0
0x1800037c2  call    cs:__imp_CloseHandle
0x1800037c8  test    eax, eax
0x1800037ca  jz      loc_180003951
0x1800037d0  call    cs:__imp_GetProcessHeap
0x1800037d6  mov     r8, r14; lpMem
0x1800037d9  xor     edx, edx; dwFlags
0x1800037db  mov     rcx, rax; hHeap
0x1800037de  call    cs:__imp_HeapFree
0x1800037e4  mov     rcx, [rbp+188h]; this
0x1800037eb  mov     r9d, esi; char *
0x1800037ee  mov     edx, 137h; void *
0x1800037f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037f8  test    rdi, rdi
0x1800037fb  jz      short loc_18000380E
0x1800037fd  mov     rcx, rdi; hMutex
0x180003800  call    cs:__imp_ReleaseMutex
0x180003806  test    eax, eax
0x180003808  jz      loc_180003963
0x18000380e  mov     rcx, rbx; hObject
0x180003811  call    cs:__imp_CloseHandle
0x180003817  test    eax, eax
0x180003819  jz      loc_1800038F6
0x18000381f  jmp     loc_1800036F8
0x180003824  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003829  lea     rcx, [r14+28h]; void *
0x18000382d  mov     dword ptr [r14], 1
0x180003834  xor     edx, edx; Val
0x180003836  mov     [r14+8], rbx
0x18000383a  mov     r8d, 108h; Size
0x180003840  movdqu  xmmword ptr [r14+10h], xmm0
0x180003846  call    memset_0
0x18000384b  xor     eax, eax
0x18000384d  lea     rcx, [r14+28h]; this
0x180003851  mov     [r14+20h], rax
0x180003855  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000385a  lea     rbx, [r14+0E8h]
0x180003861  xor     r8d, r8d; Flags
0x180003864  mov     rcx, rbx; lpCriticalSection
0x180003867  xor     edx, edx; dwSpinCount
0x180003869  call    cs:__imp_InitializeCriticalSectionEx
0x18000386f  mov     qword ptr [rbx+28h], 0
0x180003877  mov     qword ptr [rbx+30h], 0
0x18000387f  mov     qword ptr [rbx+38h], 0
0x180003887  mov     qword ptr [rbx+40h], 0
0x18000388f  xor     ebx, ebx
0x180003891  mov     [r15], r14
0x180003894  test    rdi, rdi
0x180003897  jz      short loc_1800038AA
0x180003899  mov     rcx, rdi; hMutex
0x18000389c  call    cs:__imp_ReleaseMutex
0x1800038a2  test    eax, eax
0x1800038a4  jz      loc_180003975
0x1800038aa  test    rbx, rbx
0x1800038ad  jz      short loc_1800038BC
0x1800038af  mov     rcx, rbx; hObject
0x1800038b2  call    cs:__imp_CloseHandle
0x1800038b8  test    eax, eax
0x1800038ba  jz      short loc_1800038E4
0x1800038bc  xor     eax, eax
0x1800038be  mov     rcx, [rbp+180h+var_30]
0x1800038c5  xor     rcx, rsp; StackCookie
0x1800038c8  call    __security_check_cookie
0x1800038cd  mov     rbx, [rsp+280h+arg_10]
0x1800038d5  add     rsp, 260h
0x1800038dc  pop     r15
0x1800038de  pop     r14
0x1800038e0  pop     rdi
0x1800038e1  pop     rsi
0x1800038e2  pop     rbp
0x1800038e3  retn
0x1800038e4  mov     rcx, [rbp+188h]; this
0x1800038eb  mov     edx, 0A0Bh; void *
0x1800038f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800038f6  mov     rcx, [rbp+188h]; this
0x1800038fd  mov     edx, 0A0Bh; void *
0x180003902  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003908  mov     rcx, [rbp+188h]; this
0x18000390f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003915  mov     rcx, [rbp+188h]; this
0x18000391c  mov     edx, 0A15h; void *
0x180003921  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003927  mov     rcx, [rbp+188h]; this
0x18000392e  mov     edx, 0A0Bh; void *
0x180003933  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003939  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000393f  mov     rcx, [rbp+188h]; this
0x180003946  mov     edx, 0A0Bh; void *
0x18000394b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003951  mov     rcx, [rbp+188h]; this
0x180003958  mov     edx, 0A0Bh; void *
0x18000395d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003963  mov     rcx, [rbp+188h]; this
0x18000396a  mov     edx, 0A15h; void *
0x18000396f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003975  mov     rcx, [rbp+188h]; this
0x18000397c  mov     edx, 0A15h; void *
0x180003981  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
