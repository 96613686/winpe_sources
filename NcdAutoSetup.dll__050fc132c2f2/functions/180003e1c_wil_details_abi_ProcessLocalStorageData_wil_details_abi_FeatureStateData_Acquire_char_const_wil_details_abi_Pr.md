# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003e1c`
- end: `0x1800041e3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004624`

## callees

- `0x180002514`
- `0x180003164`
- `0x180003e1c`
- `0x180004350`
- `0x1800047b4`
- `0x180005168`
- `0x180005ef0`
- `0x1800075c0`
- `0x18000847c`
- `0x180009474`
- `0x180009484`
- `0x18001380e`
- `0x180013840`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000403a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000403a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000402c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000402c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800040c5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800040c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000405c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000405c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003eb4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003eb4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003e93`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003e93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000401e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000406d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000410e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000401e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000406d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000410e`

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
0x180003e1c  mov     [rsp-8+arg_10], rbx
0x180003e21  push    rbp
0x180003e22  push    rsi
0x180003e23  push    rdi
0x180003e24  push    r14
0x180003e26  push    r15
0x180003e28  lea     rbp, [rsp-160h]
0x180003e30  sub     rsp, 260h
0x180003e37  mov     rax, cs:__security_cookie
0x180003e3e  xor     rax, rsp
0x180003e41  mov     [rbp+180h+var_30], rax
0x180003e48  mov     r15, rdx
0x180003e4b  mov     qword ptr [rdx], 0
0x180003e52  mov     rbx, rcx
0x180003e55  call    cs:__imp_GetCurrentProcessId
0x180003e5b  mov     r14d, 130h
0x180003e61  mov     [rsp+280h+var_258], rbx
0x180003e66  mov     r9d, eax
0x180003e69  mov     [rsp+280h+var_260], r14d; int
0x180003e6e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003e75  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003e7a  lea     edx, [r14-2Ch]; unsigned __int64
0x180003e7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003e83  mov     r9d, 1F0001h; dwDesiredAccess
0x180003e89  lea     rdx, [rsp+280h+Name]; lpName
0x180003e8e  xor     r8d, r8d; dwFlags
0x180003e91  xor     ecx, ecx; lpMutexAttributes
0x180003e93  call    cs:__imp_CreateMutexExW
0x180003e99  mov     rbx, rax
0x180003e9c  test    rax, rax
0x180003e9f  jnz     short loc_180003EAB
0x180003ea1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003ea6  jmp     loc_18000411A
0x180003eab  xor     r8d, r8d; bAlertable
0x180003eae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003eb1  mov     rcx, rbx; hHandle
0x180003eb4  call    cs:__imp_WaitForSingleObjectEx
0x180003eba  cmp     eax, 102h
0x180003ebf  jz      short loc_180003ED1
0x180003ec1  test    eax, 0FFFFFF7Fh
0x180003ec6  jnz     loc_180004164
0x180003ecc  mov     rdi, rbx
0x180003ecf  jmp     short loc_180003ED3
0x180003ed1  xor     edi, edi
0x180003ed3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003ed8  mov     [rsp+280h+hObject], 0
0x180003ee1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003ee6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003eeb  mov     esi, eax
0x180003eed  test    eax, eax
0x180003eef  jns     short loc_180003F5B
0x180003ef1  mov     rcx, [rbp+188h]; this
0x180003ef8  mov     r9d, eax; char *
0x180003efb  mov     edx, 66h ; 'f'; void *
0x180003f00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f05  mov     rcx, [rbp+188h]; this
0x180003f0c  mov     r9d, esi; char *
0x180003f0f  mov     edx, 6Fh ; 'o'; void *
0x180003f14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f19  mov     rcx, [rbp+188h]; this
0x180003f20  mov     r9d, esi; char *
0x180003f23  mov     edx, 12Eh; void *
0x180003f28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f2d  test    rdi, rdi
0x180003f30  jz      short loc_180003F43
0x180003f32  mov     rcx, rdi; hMutex
0x180003f35  call    cs:__imp_ReleaseMutex
0x180003f3b  test    eax, eax
0x180003f3d  jz      loc_180004171
0x180003f43  mov     rcx, rbx; hObject
0x180003f46  call    cs:__imp_CloseHandle
0x180003f4c  test    eax, eax
0x180003f4e  jz      loc_180004183
0x180003f54  mov     eax, esi
0x180003f56  jmp     loc_18000411A
0x180003f5b  mov     rax, [rsp+280h+hObject]
0x180003f60  lea     rcx, ds:0[rax*4]
0x180003f68  test    rcx, rcx
0x180003f6b  jz      short loc_180003F7B
0x180003f6d  mov     [r15], rcx
0x180003f70  mov     eax, [rcx]
0x180003f72  inc     eax
0x180003f74  mov     [rcx], eax
0x180003f76  jmp     loc_1800040F0
0x180003f7b  mov     rdx, r14; dwBytes
0x180003f7e  mov     qword ptr [r15], 0
0x180003f85  mov     ecx, 8; dwFlags
0x180003f8a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003f8f  mov     r14, rax
0x180003f92  test    rax, rax
0x180003f95  jnz     short loc_180003FB5
0x180003f97  mov     rcx, [rbp+188h]; this
0x180003f9e  mov     esi, 8007000Eh
0x180003fa3  mov     r9d, esi; char *
0x180003fa6  mov     edx, 14Bh; void *
0x180003fab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fb0  jmp     loc_180004040
0x180003fb5  xorps   xmm0, xmm0
0x180003fb8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003fbe  test    r14b, 3
0x180003fc2  jnz     loc_180004195
0x180003fc8  mov     r9, r14
0x180003fcb  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003fd0  shr     r9, 2; unsigned __int64
0x180003fd4  lea     rcx, [rsp+280h+hObject]; this
0x180003fd9  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003fde  mov     esi, eax
0x180003fe0  test    eax, eax
0x180003fe2  jns     loc_180004080
0x180003fe8  mov     rcx, [rbp+188h]; this
0x180003fef  mov     r9d, eax; char *
0x180003ff2  mov     edx, 14Eh; void *
0x180003ff7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ffc  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004001  test    rcx, rcx
0x180004004  jz      short loc_180004014
0x180004006  call    cs:__imp_CloseHandle
0x18000400c  test    eax, eax
0x18000400e  jz      loc_18000419B
0x180004014  mov     rcx, [rsp+280h+hObject]; hObject
0x180004019  test    rcx, rcx
0x18000401c  jz      short loc_18000402C
0x18000401e  call    cs:__imp_CloseHandle
0x180004024  test    eax, eax
0x180004026  jz      loc_1800041AD
0x18000402c  call    cs:__imp_GetProcessHeap
0x180004032  mov     r8, r14; lpMem
0x180004035  xor     edx, edx; dwFlags
0x180004037  mov     rcx, rax; hHeap
0x18000403a  call    cs:__imp_HeapFree
0x180004040  mov     rcx, [rbp+188h]; this
0x180004047  mov     r9d, esi; char *
0x18000404a  mov     edx, 137h; void *
0x18000404f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004054  test    rdi, rdi
0x180004057  jz      short loc_18000406A
0x180004059  mov     rcx, rdi; hMutex
0x18000405c  call    cs:__imp_ReleaseMutex
0x180004062  test    eax, eax
0x180004064  jz      loc_1800041BF
0x18000406a  mov     rcx, rbx; hObject
0x18000406d  call    cs:__imp_CloseHandle
0x180004073  test    eax, eax
0x180004075  jz      loc_180004152
0x18000407b  jmp     loc_180003F54
0x180004080  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004085  lea     rcx, [r14+28h]; void *
0x180004089  mov     dword ptr [r14], 1
0x180004090  xor     edx, edx; Val
0x180004092  mov     [r14+8], rbx
0x180004096  mov     r8d, 108h; Size
0x18000409c  movdqu  xmmword ptr [r14+10h], xmm0
0x1800040a2  call    memset_0
0x1800040a7  xor     eax, eax
0x1800040a9  lea     rcx, [r14+28h]; this
0x1800040ad  mov     [r14+20h], rax
0x1800040b1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800040b6  lea     rbx, [r14+0E8h]
0x1800040bd  xor     r8d, r8d; Flags
0x1800040c0  mov     rcx, rbx; lpCriticalSection
0x1800040c3  xor     edx, edx; dwSpinCount
0x1800040c5  call    cs:__imp_InitializeCriticalSectionEx
0x1800040cb  mov     qword ptr [rbx+28h], 0
0x1800040d3  mov     qword ptr [rbx+30h], 0
0x1800040db  mov     qword ptr [rbx+38h], 0
0x1800040e3  mov     qword ptr [rbx+40h], 0
0x1800040eb  xor     ebx, ebx
0x1800040ed  mov     [r15], r14
0x1800040f0  test    rdi, rdi
0x1800040f3  jz      short loc_180004106
0x1800040f5  mov     rcx, rdi; hMutex
0x1800040f8  call    cs:__imp_ReleaseMutex
0x1800040fe  test    eax, eax
0x180004100  jz      loc_1800041D1
0x180004106  test    rbx, rbx
0x180004109  jz      short loc_180004118
0x18000410b  mov     rcx, rbx; hObject
0x18000410e  call    cs:__imp_CloseHandle
0x180004114  test    eax, eax
0x180004116  jz      short loc_180004140
0x180004118  xor     eax, eax
0x18000411a  mov     rcx, [rbp+180h+var_30]
0x180004121  xor     rcx, rsp; StackCookie
0x180004124  call    __security_check_cookie
0x180004129  mov     rbx, [rsp+280h+arg_10]
0x180004131  add     rsp, 260h
0x180004138  pop     r15
0x18000413a  pop     r14
0x18000413c  pop     rdi
0x18000413d  pop     rsi
0x18000413e  pop     rbp
0x18000413f  retn
0x180004140  mov     rcx, [rbp+188h]; this
0x180004147  mov     edx, 0A0Bh; void *
0x18000414c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004152  mov     rcx, [rbp+188h]; this
0x180004159  mov     edx, 0A0Bh; void *
0x18000415e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004164  mov     rcx, [rbp+188h]; this
0x18000416b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004171  mov     rcx, [rbp+188h]; this
0x180004178  mov     edx, 0A15h; void *
0x18000417d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004183  mov     rcx, [rbp+188h]; this
0x18000418a  mov     edx, 0A0Bh; void *
0x18000418f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004195  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000419b  mov     rcx, [rbp+188h]; this
0x1800041a2  mov     edx, 0A0Bh; void *
0x1800041a7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041ad  mov     rcx, [rbp+188h]; this
0x1800041b4  mov     edx, 0A0Bh; void *
0x1800041b9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041bf  mov     rcx, [rbp+188h]; this
0x1800041c6  mov     edx, 0A15h; void *
0x1800041cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800041d1  mov     rcx, [rbp+188h]; this
0x1800041d8  mov     edx, 0A15h; void *
0x1800041dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
