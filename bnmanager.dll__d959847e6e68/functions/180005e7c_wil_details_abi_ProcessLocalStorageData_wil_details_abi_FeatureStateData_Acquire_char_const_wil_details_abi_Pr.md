# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005e7c`
- end: `0x180006243`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800076c4`

## callees

- `0x1800017c0`
- `0x180002290`
- `0x180004800`
- `0x180005e7c`
- `0x180006e6c`
- `0x180007854`
- `0x180008178`
- `0x180008e98`
- `0x18000a534`
- `0x18000b040`
- `0x18000b39c`
- `0x18000bb7c`
- `0x18000bb8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005eb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000609a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000609a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000608c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000608c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000607e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000616e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000607e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000616e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005ef3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005ef3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005f14`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005f14`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006125`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006125`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800060bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006158`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800060bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006158`

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
0x180005e7c  mov     [rsp-8+arg_10], rbx
0x180005e81  push    rbp
0x180005e82  push    rsi
0x180005e83  push    rdi
0x180005e84  push    r14
0x180005e86  push    r15
0x180005e88  lea     rbp, [rsp-160h]
0x180005e90  sub     rsp, 260h
0x180005e97  mov     rax, cs:__security_cookie
0x180005e9e  xor     rax, rsp
0x180005ea1  mov     [rbp+180h+var_30], rax
0x180005ea8  mov     r15, rdx
0x180005eab  mov     qword ptr [rdx], 0
0x180005eb2  mov     rbx, rcx
0x180005eb5  call    cs:__imp_GetCurrentProcessId
0x180005ebb  mov     r14d, 130h
0x180005ec1  mov     [rsp+280h+var_258], rbx
0x180005ec6  mov     r9d, eax
0x180005ec9  mov     [rsp+280h+var_260], r14d; int
0x180005ece  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005ed5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005eda  lea     edx, [r14-2Ch]; unsigned __int64
0x180005ede  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005ee3  mov     r9d, 1F0001h; dwDesiredAccess
0x180005ee9  lea     rdx, [rsp+280h+Name]; lpName
0x180005eee  xor     r8d, r8d; dwFlags
0x180005ef1  xor     ecx, ecx; lpMutexAttributes
0x180005ef3  call    cs:__imp_CreateMutexExW
0x180005ef9  mov     rbx, rax
0x180005efc  test    rax, rax
0x180005eff  jnz     short loc_180005F0B
0x180005f01  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005f06  jmp     loc_18000617A
0x180005f0b  xor     r8d, r8d; bAlertable
0x180005f0e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005f11  mov     rcx, rbx; hHandle
0x180005f14  call    cs:__imp_WaitForSingleObjectEx
0x180005f1a  cmp     eax, 102h
0x180005f1f  jz      short loc_180005F31
0x180005f21  test    eax, 0FFFFFF7Fh
0x180005f26  jnz     loc_1800061C4
0x180005f2c  mov     rdi, rbx
0x180005f2f  jmp     short loc_180005F33
0x180005f31  xor     edi, edi
0x180005f33  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005f38  mov     [rsp+280h+hObject], 0
0x180005f41  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005f46  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005f4b  mov     esi, eax
0x180005f4d  test    eax, eax
0x180005f4f  jns     short loc_180005FBB
0x180005f51  mov     rcx, [rbp+188h]; this
0x180005f58  mov     r9d, eax; char *
0x180005f5b  mov     edx, 66h ; 'f'; void *
0x180005f60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f65  mov     rcx, [rbp+188h]; this
0x180005f6c  mov     r9d, esi; char *
0x180005f6f  mov     edx, 6Fh ; 'o'; void *
0x180005f74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f79  mov     rcx, [rbp+188h]; this
0x180005f80  mov     r9d, esi; char *
0x180005f83  mov     edx, 12Eh; void *
0x180005f88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f8d  test    rdi, rdi
0x180005f90  jz      short loc_180005FA3
0x180005f92  mov     rcx, rdi; hMutex
0x180005f95  call    cs:__imp_ReleaseMutex
0x180005f9b  test    eax, eax
0x180005f9d  jz      loc_1800061D1
0x180005fa3  mov     rcx, rbx; hObject
0x180005fa6  call    cs:__imp_CloseHandle
0x180005fac  test    eax, eax
0x180005fae  jz      loc_1800061E3
0x180005fb4  mov     eax, esi
0x180005fb6  jmp     loc_18000617A
0x180005fbb  mov     rax, [rsp+280h+hObject]
0x180005fc0  lea     rcx, ds:0[rax*4]
0x180005fc8  test    rcx, rcx
0x180005fcb  jz      short loc_180005FDB
0x180005fcd  mov     [r15], rcx
0x180005fd0  mov     eax, [rcx]
0x180005fd2  inc     eax
0x180005fd4  mov     [rcx], eax
0x180005fd6  jmp     loc_180006150
0x180005fdb  mov     rdx, r14; dwBytes
0x180005fde  mov     qword ptr [r15], 0
0x180005fe5  mov     ecx, 8; dwFlags
0x180005fea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005fef  mov     r14, rax
0x180005ff2  test    rax, rax
0x180005ff5  jnz     short loc_180006015
0x180005ff7  mov     rcx, [rbp+188h]; this
0x180005ffe  mov     esi, 8007000Eh
0x180006003  mov     r9d, esi; char *
0x180006006  mov     edx, 14Bh; void *
0x18000600b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006010  jmp     loc_1800060A0
0x180006015  xorps   xmm0, xmm0
0x180006018  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000601e  test    r14b, 3
0x180006022  jnz     loc_1800061F5
0x180006028  mov     r9, r14
0x18000602b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006030  shr     r9, 2; unsigned __int64
0x180006034  lea     rcx, [rsp+280h+hObject]; this
0x180006039  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000603e  mov     esi, eax
0x180006040  test    eax, eax
0x180006042  jns     loc_1800060E0
0x180006048  mov     rcx, [rbp+188h]; this
0x18000604f  mov     r9d, eax; char *
0x180006052  mov     edx, 14Eh; void *
0x180006057  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000605c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006061  test    rcx, rcx
0x180006064  jz      short loc_180006074
0x180006066  call    cs:__imp_CloseHandle
0x18000606c  test    eax, eax
0x18000606e  jz      loc_1800061FB
0x180006074  mov     rcx, [rsp+280h+hObject]; hObject
0x180006079  test    rcx, rcx
0x18000607c  jz      short loc_18000608C
0x18000607e  call    cs:__imp_CloseHandle
0x180006084  test    eax, eax
0x180006086  jz      loc_18000620D
0x18000608c  call    cs:__imp_GetProcessHeap
0x180006092  mov     r8, r14; lpMem
0x180006095  xor     edx, edx; dwFlags
0x180006097  mov     rcx, rax; hHeap
0x18000609a  call    cs:__imp_HeapFree
0x1800060a0  mov     rcx, [rbp+188h]; this
0x1800060a7  mov     r9d, esi; char *
0x1800060aa  mov     edx, 137h; void *
0x1800060af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060b4  test    rdi, rdi
0x1800060b7  jz      short loc_1800060CA
0x1800060b9  mov     rcx, rdi; hMutex
0x1800060bc  call    cs:__imp_ReleaseMutex
0x1800060c2  test    eax, eax
0x1800060c4  jz      loc_18000621F
0x1800060ca  mov     rcx, rbx; hObject
0x1800060cd  call    cs:__imp_CloseHandle
0x1800060d3  test    eax, eax
0x1800060d5  jz      loc_1800061B2
0x1800060db  jmp     loc_180005FB4
0x1800060e0  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800060e5  lea     rcx, [r14+28h]; void *
0x1800060e9  mov     dword ptr [r14], 1
0x1800060f0  xor     edx, edx; Val
0x1800060f2  mov     [r14+8], rbx
0x1800060f6  mov     r8d, 108h; Size
0x1800060fc  movdqu  xmmword ptr [r14+10h], xmm0
0x180006102  call    memset_0
0x180006107  xor     eax, eax
0x180006109  lea     rcx, [r14+28h]; this
0x18000610d  mov     [r14+20h], rax
0x180006111  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006116  lea     rbx, [r14+0E8h]
0x18000611d  xor     r8d, r8d; Flags
0x180006120  mov     rcx, rbx; lpCriticalSection
0x180006123  xor     edx, edx; dwSpinCount
0x180006125  call    cs:__imp_InitializeCriticalSectionEx
0x18000612b  mov     qword ptr [rbx+28h], 0
0x180006133  mov     qword ptr [rbx+30h], 0
0x18000613b  mov     qword ptr [rbx+38h], 0
0x180006143  mov     qword ptr [rbx+40h], 0
0x18000614b  xor     ebx, ebx
0x18000614d  mov     [r15], r14
0x180006150  test    rdi, rdi
0x180006153  jz      short loc_180006166
0x180006155  mov     rcx, rdi; hMutex
0x180006158  call    cs:__imp_ReleaseMutex
0x18000615e  test    eax, eax
0x180006160  jz      loc_180006231
0x180006166  test    rbx, rbx
0x180006169  jz      short loc_180006178
0x18000616b  mov     rcx, rbx; hObject
0x18000616e  call    cs:__imp_CloseHandle
0x180006174  test    eax, eax
0x180006176  jz      short loc_1800061A0
0x180006178  xor     eax, eax
0x18000617a  mov     rcx, [rbp+180h+var_30]
0x180006181  xor     rcx, rsp; StackCookie
0x180006184  call    __security_check_cookie
0x180006189  mov     rbx, [rsp+280h+arg_10]
0x180006191  add     rsp, 260h
0x180006198  pop     r15
0x18000619a  pop     r14
0x18000619c  pop     rdi
0x18000619d  pop     rsi
0x18000619e  pop     rbp
0x18000619f  retn
0x1800061a0  mov     rcx, [rbp+188h]; this
0x1800061a7  mov     edx, 0A0Bh; void *
0x1800061ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800061b2  mov     rcx, [rbp+188h]; this
0x1800061b9  mov     edx, 0A0Bh; void *
0x1800061be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800061c4  mov     rcx, [rbp+188h]; this
0x1800061cb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800061d1  mov     rcx, [rbp+188h]; this
0x1800061d8  mov     edx, 0A15h; void *
0x1800061dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800061e3  mov     rcx, [rbp+188h]; this
0x1800061ea  mov     edx, 0A0Bh; void *
0x1800061ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800061f5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800061fb  mov     rcx, [rbp+188h]; this
0x180006202  mov     edx, 0A0Bh; void *
0x180006207  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000620d  mov     rcx, [rbp+188h]; this
0x180006214  mov     edx, 0A0Bh; void *
0x180006219  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000621f  mov     rcx, [rbp+188h]; this
0x180006226  mov     edx, 0A15h; void *
0x18000622b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006231  mov     rcx, [rbp+188h]; this
0x180006238  mov     edx, 0A15h; void *
0x18000623d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
