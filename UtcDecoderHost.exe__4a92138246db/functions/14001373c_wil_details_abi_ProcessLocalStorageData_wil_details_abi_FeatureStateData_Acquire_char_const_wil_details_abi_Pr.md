# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14001373c`
- end: `0x140013b39`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140013b40`

## callees

- `0x140008660`
- `0x1400090ec`
- `0x14000aea4`
- `0x14000b194`
- `0x14000b7e8`
- `0x14000bfc8`
- `0x14000c434`
- `0x14000ce24`
- `0x14000cefc`
- `0x14000d2dc`
- `0x14000d2ec`
- `0x140012d54`
- `0x14001373c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140013a0f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140013a0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14001386a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400139a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140013a42`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14001386a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400139a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140013a42`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400137d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400137d4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400137b3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400137b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001397d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001397d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001396f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001396f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140013775`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140013775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001387b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013949`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013961`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400139b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013a58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001387b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013949`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013961`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400139b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013a58`

## string_xrefs

- `0x140013ab5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // r8
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _DWORD *v23; // r14
  int v24; // eax
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  HANDLE ProcessHeap; // rax
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  __int128 v34; // xmm0
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v40);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v23 = (_DWORD *)v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v14;
  }
  *(_OWORD *)hObject = 0;
  if ( (v20 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
  v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v22,
          v20 >> 2);
  v14 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v24, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
    goto LABEL_23;
  }
  v34 = *(_OWORD *)hObject;
  *v23 = 1;
  *((_QWORD *)v23 + 1) = v6;
  *((_OWORD *)v23 + 1) = v34;
  memset_0(v23 + 10, 0, 0x108u);
  *((_QWORD *)v23 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v23 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v23 + 58), 0, 0);
  *((_QWORD *)v23 + 34) = 0;
  *((_QWORD *)v23 + 35) = 0;
  *((_QWORD *)v23 + 36) = 0;
  *((_QWORD *)v23 + 37) = 0;
  v6 = 0;
  *a2 = v23;
LABEL_28:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x14001373c  mov     [rsp-8+arg_10], rbx
0x140013741  push    rbp
0x140013742  push    rsi
0x140013743  push    rdi
0x140013744  push    r14
0x140013746  push    r15
0x140013748  lea     rbp, [rsp-160h]
0x140013750  sub     rsp, 260h
0x140013757  mov     rax, cs:__security_cookie
0x14001375e  xor     rax, rsp
0x140013761  mov     [rbp+180h+var_30], rax
0x140013768  mov     r15, rdx
0x14001376b  mov     qword ptr [rdx], 0
0x140013772  mov     rbx, rcx
0x140013775  call    cs:__imp_GetCurrentProcessId
0x14001377b  mov     r14d, 130h
0x140013781  mov     [rsp+280h+var_258], rbx
0x140013786  mov     r9d, eax
0x140013789  mov     [rsp+280h+var_260], r14d; int
0x14001378e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140013795  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14001379a  lea     edx, [r14-2Ch]; unsigned __int64
0x14001379e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400137a3  mov     r9d, 1F0001h; dwDesiredAccess
0x1400137a9  lea     rdx, [rsp+280h+Name]; lpName
0x1400137ae  xor     r8d, r8d; dwFlags
0x1400137b1  xor     ecx, ecx; lpMutexAttributes
0x1400137b3  call    cs:__imp_CreateMutexExW
0x1400137b9  mov     rbx, rax
0x1400137bc  test    rax, rax
0x1400137bf  jnz     short loc_1400137CB
0x1400137c1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400137c6  jmp     loc_140013A64
0x1400137cb  xor     r8d, r8d; bAlertable
0x1400137ce  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400137d1  mov     rcx, rbx; hHandle
0x1400137d4  call    cs:__imp_WaitForSingleObjectEx
0x1400137da  cmp     eax, 102h
0x1400137df  jz      short loc_1400137F1
0x1400137e1  test    eax, 0FFFFFF7Fh
0x1400137e6  jnz     loc_140013AAE
0x1400137ec  mov     rdi, rbx
0x1400137ef  jmp     short loc_1400137F3
0x1400137f1  xor     edi, edi
0x1400137f3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400137f8  mov     [rsp+280h+hObject], 0
0x140013801  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140013806  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14001380b  mov     esi, eax
0x14001380d  test    eax, eax
0x14001380f  jns     short loc_140013890
0x140013811  mov     rcx, [rbp+188h]; this
0x140013818  lea     r8, aWil; "wil"
0x14001381f  mov     r9d, eax; char *
0x140013822  mov     edx, 66h ; 'f'; void *
0x140013827  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001382c  mov     rcx, [rbp+188h]; this
0x140013833  lea     r8, aWil; "wil"
0x14001383a  mov     r9d, esi; char *
0x14001383d  mov     edx, 6Fh ; 'o'; void *
0x140013842  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013847  mov     rcx, [rbp+188h]; this
0x14001384e  lea     r8, aWil; "wil"
0x140013855  mov     r9d, esi; char *
0x140013858  mov     edx, 12Eh; void *
0x14001385d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013862  test    rdi, rdi
0x140013865  jz      short loc_140013878
0x140013867  mov     rcx, rdi; hMutex
0x14001386a  call    cs:__imp_ReleaseMutex
0x140013870  test    eax, eax
0x140013872  jz      loc_140013AC7
0x140013878  mov     rcx, rbx; hObject
0x14001387b  call    cs:__imp_CloseHandle
0x140013881  test    eax, eax
0x140013883  jz      loc_140013AD9
0x140013889  mov     eax, esi
0x14001388b  jmp     loc_140013A64
0x140013890  mov     rax, [rsp+280h+hObject]
0x140013895  lea     rcx, ds:0[rax*4]
0x14001389d  test    rcx, rcx
0x1400138a0  jz      short loc_1400138B0
0x1400138a2  mov     [r15], rcx
0x1400138a5  mov     eax, [rcx]
0x1400138a7  inc     eax
0x1400138a9  mov     [rcx], eax
0x1400138ab  jmp     loc_140013A3A
0x1400138b0  mov     rdx, r14; dwBytes
0x1400138b3  mov     qword ptr [r15], 0
0x1400138ba  mov     ecx, 8; dwFlags
0x1400138bf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400138c4  mov     r14, rax
0x1400138c7  test    rax, rax
0x1400138ca  jnz     short loc_1400138F1
0x1400138cc  mov     rcx, [rbp+188h]; this
0x1400138d3  lea     r8, aWil; "wil"
0x1400138da  mov     esi, 8007000Eh
0x1400138df  mov     edx, 14Bh; void *
0x1400138e4  mov     r9d, esi; char *
0x1400138e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400138ec  jmp     loc_140013983
0x1400138f1  xorps   xmm0, xmm0
0x1400138f4  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400138fa  test    r14b, 3
0x1400138fe  jnz     loc_140013AEB
0x140013904  mov     r9, r14
0x140013907  lea     rdx, [rsp+280h+Name]; wchar_t *
0x14001390c  shr     r9, 2; unsigned __int64
0x140013910  lea     rcx, [rsp+280h+hObject]; this
0x140013915  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x14001391a  mov     esi, eax
0x14001391c  test    eax, eax
0x14001391e  jns     loc_1400139CA
0x140013924  mov     rcx, [rbp+188h]; this
0x14001392b  lea     r8, aWil; "wil"
0x140013932  mov     r9d, eax; char *
0x140013935  mov     edx, 14Eh; void *
0x14001393a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001393f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140013944  test    rcx, rcx
0x140013947  jz      short loc_140013957
0x140013949  call    cs:__imp_CloseHandle
0x14001394f  test    eax, eax
0x140013951  jz      loc_140013AF1
0x140013957  mov     rcx, [rsp+280h+hObject]; hObject
0x14001395c  test    rcx, rcx
0x14001395f  jz      short loc_14001396F
0x140013961  call    cs:__imp_CloseHandle
0x140013967  test    eax, eax
0x140013969  jz      loc_140013B03
0x14001396f  call    cs:__imp_GetProcessHeap
0x140013975  mov     r8, r14; lpMem
0x140013978  xor     edx, edx; dwFlags
0x14001397a  mov     rcx, rax; hHeap
0x14001397d  call    cs:__imp_HeapFree
0x140013983  mov     rcx, [rbp+188h]; this
0x14001398a  lea     r8, aWil; "wil"
0x140013991  mov     r9d, esi; char *
0x140013994  mov     edx, 137h; void *
0x140013999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001399e  test    rdi, rdi
0x1400139a1  jz      short loc_1400139B4
0x1400139a3  mov     rcx, rdi; hMutex
0x1400139a6  call    cs:__imp_ReleaseMutex
0x1400139ac  test    eax, eax
0x1400139ae  jz      loc_140013B15
0x1400139b4  mov     rcx, rbx; hObject
0x1400139b7  call    cs:__imp_CloseHandle
0x1400139bd  test    eax, eax
0x1400139bf  jz      loc_140013A9C
0x1400139c5  jmp     loc_140013889
0x1400139ca  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400139cf  lea     rcx, [r14+28h]; void *
0x1400139d3  mov     dword ptr [r14], 1
0x1400139da  xor     edx, edx; Val
0x1400139dc  mov     [r14+8], rbx
0x1400139e0  mov     r8d, 108h; Size
0x1400139e6  movdqu  xmmword ptr [r14+10h], xmm0
0x1400139ec  call    memset_0
0x1400139f1  xor     eax, eax
0x1400139f3  lea     rcx, [r14+28h]; this
0x1400139f7  mov     [r14+20h], rax
0x1400139fb  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140013a00  lea     rbx, [r14+0E8h]
0x140013a07  xor     r8d, r8d; Flags
0x140013a0a  mov     rcx, rbx; lpCriticalSection
0x140013a0d  xor     edx, edx; dwSpinCount
0x140013a0f  call    cs:__imp_InitializeCriticalSectionEx
0x140013a15  mov     qword ptr [rbx+28h], 0
0x140013a1d  mov     qword ptr [rbx+30h], 0
0x140013a25  mov     qword ptr [rbx+38h], 0
0x140013a2d  mov     qword ptr [rbx+40h], 0
0x140013a35  xor     ebx, ebx
0x140013a37  mov     [r15], r14
0x140013a3a  test    rdi, rdi
0x140013a3d  jz      short loc_140013A50
0x140013a3f  mov     rcx, rdi; hMutex
0x140013a42  call    cs:__imp_ReleaseMutex
0x140013a48  test    eax, eax
0x140013a4a  jz      loc_140013B27
0x140013a50  test    rbx, rbx
0x140013a53  jz      short loc_140013A62
0x140013a55  mov     rcx, rbx; hObject
0x140013a58  call    cs:__imp_CloseHandle
0x140013a5e  test    eax, eax
0x140013a60  jz      short loc_140013A8A
0x140013a62  xor     eax, eax
0x140013a64  mov     rcx, [rbp+180h+var_30]
0x140013a6b  xor     rcx, rsp; StackCookie
0x140013a6e  call    __security_check_cookie
0x140013a73  mov     rbx, [rsp+280h+arg_10]
0x140013a7b  add     rsp, 260h
0x140013a82  pop     r15
0x140013a84  pop     r14
0x140013a86  pop     rdi
0x140013a87  pop     rsi
0x140013a88  pop     rbp
0x140013a89  retn
0x140013a8a  mov     rcx, [rbp+188h]; this
0x140013a91  mov     edx, 0A0Bh; void *
0x140013a96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013a9c  mov     rcx, [rbp+188h]; this
0x140013aa3  mov     edx, 0A0Bh; void *
0x140013aa8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013aae  mov     rcx, [rbp+188h]; this
0x140013ab5  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140013abc  mov     edx, 0E01h; void *
0x140013ac1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140013ac7  mov     rcx, [rbp+188h]; this
0x140013ace  mov     edx, 0A15h; void *
0x140013ad3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013ad9  mov     rcx, [rbp+188h]; this
0x140013ae0  mov     edx, 0A0Bh; void *
0x140013ae5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013aeb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140013af1  mov     rcx, [rbp+188h]; this
0x140013af8  mov     edx, 0A0Bh; void *
0x140013afd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013b03  mov     rcx, [rbp+188h]; this
0x140013b0a  mov     edx, 0A0Bh; void *
0x140013b0f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013b15  mov     rcx, [rbp+188h]; this
0x140013b1c  mov     edx, 0A15h; void *
0x140013b21  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140013b27  mov     rcx, [rbp+188h]; this
0x140013b2e  mov     edx, 0A15h; void *
0x140013b33  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
