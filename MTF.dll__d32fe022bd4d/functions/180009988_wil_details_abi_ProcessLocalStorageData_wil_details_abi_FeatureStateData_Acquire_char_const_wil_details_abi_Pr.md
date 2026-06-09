# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009988`
- end: `0x180009d85`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000a2b0`

## callees

- `0x1800043ec`
- `0x1800046d4`
- `0x180004cc8`
- `0x18000599c`
- `0x180006074`
- `0x1800068a4`
- `0x18000697c`
- `0x180006f00`
- `0x180006f10`
- `0x180009088`
- `0x180009988`
- `0x18002bc62`
- `0x18002bca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800099ff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800099ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009a20`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009a20`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009ab6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009bf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009ab6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009bf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c8e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180009c5b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180009c5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bc9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800099c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800099c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ac7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ca4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ac7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ca4`

## string_xrefs

- `0x180009d01`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _DWORD *v23; // r14
  int v24; // eax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  __int128 v34; // xmm0
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
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
      wil::details::in1diag3::_FailFast_Unexpected(
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
0x180009988  mov     [rsp-8+arg_10], rbx
0x18000998d  push    rbp
0x18000998e  push    rsi
0x18000998f  push    rdi
0x180009990  push    r14
0x180009992  push    r15
0x180009994  lea     rbp, [rsp-160h]
0x18000999c  sub     rsp, 260h
0x1800099a3  mov     rax, cs:__security_cookie
0x1800099aa  xor     rax, rsp
0x1800099ad  mov     [rbp+180h+var_30], rax
0x1800099b4  mov     r15, rdx
0x1800099b7  mov     qword ptr [rdx], 0
0x1800099be  mov     rbx, rcx
0x1800099c1  call    cs:__imp_GetCurrentProcessId
0x1800099c7  mov     r14d, 130h
0x1800099cd  mov     [rsp+280h+var_258], rbx
0x1800099d2  mov     r9d, eax
0x1800099d5  mov     [rsp+280h+var_260], r14d; int
0x1800099da  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800099e1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800099e6  lea     edx, [r14-2Ch]; unsigned __int64
0x1800099ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800099ef  mov     r9d, 1F0001h; dwDesiredAccess
0x1800099f5  lea     rdx, [rsp+280h+Name]; lpName
0x1800099fa  xor     r8d, r8d; dwFlags
0x1800099fd  xor     ecx, ecx; lpMutexAttributes
0x1800099ff  call    cs:__imp_CreateMutexExW
0x180009a05  mov     rbx, rax
0x180009a08  test    rax, rax
0x180009a0b  jnz     short loc_180009A17
0x180009a0d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009a12  jmp     loc_180009CB0
0x180009a17  xor     r8d, r8d; bAlertable
0x180009a1a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009a1d  mov     rcx, rbx; hHandle
0x180009a20  call    cs:__imp_WaitForSingleObjectEx
0x180009a26  cmp     eax, 102h
0x180009a2b  jz      short loc_180009A3D
0x180009a2d  test    eax, 0FFFFFF7Fh
0x180009a32  jnz     loc_180009CFA
0x180009a38  mov     rdi, rbx
0x180009a3b  jmp     short loc_180009A3F
0x180009a3d  xor     edi, edi
0x180009a3f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009a44  mov     [rsp+280h+hObject], 0
0x180009a4d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009a52  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009a57  mov     esi, eax
0x180009a59  test    eax, eax
0x180009a5b  jns     short loc_180009ADC
0x180009a5d  mov     rcx, [rbp+188h]; this
0x180009a64  lea     r8, aWil; "wil"
0x180009a6b  mov     r9d, eax; char *
0x180009a6e  mov     edx, 66h ; 'f'; void *
0x180009a73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a78  mov     rcx, [rbp+188h]; this
0x180009a7f  lea     r8, aWil; "wil"
0x180009a86  mov     r9d, esi; char *
0x180009a89  mov     edx, 6Fh ; 'o'; void *
0x180009a8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a93  mov     rcx, [rbp+188h]; this
0x180009a9a  lea     r8, aWil; "wil"
0x180009aa1  mov     r9d, esi; char *
0x180009aa4  mov     edx, 12Eh; void *
0x180009aa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009aae  test    rdi, rdi
0x180009ab1  jz      short loc_180009AC4
0x180009ab3  mov     rcx, rdi; hMutex
0x180009ab6  call    cs:__imp_ReleaseMutex
0x180009abc  test    eax, eax
0x180009abe  jz      loc_180009D13
0x180009ac4  mov     rcx, rbx; hObject
0x180009ac7  call    cs:__imp_CloseHandle
0x180009acd  test    eax, eax
0x180009acf  jz      loc_180009D25
0x180009ad5  mov     eax, esi
0x180009ad7  jmp     loc_180009CB0
0x180009adc  mov     rax, [rsp+280h+hObject]
0x180009ae1  lea     rcx, ds:0[rax*4]
0x180009ae9  test    rcx, rcx
0x180009aec  jz      short loc_180009AFC
0x180009aee  mov     [r15], rcx
0x180009af1  mov     eax, [rcx]
0x180009af3  inc     eax
0x180009af5  mov     [rcx], eax
0x180009af7  jmp     loc_180009C86
0x180009afc  mov     rdx, r14; dwBytes
0x180009aff  mov     qword ptr [r15], 0
0x180009b06  mov     ecx, 8; dwFlags
0x180009b0b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009b10  mov     r14, rax
0x180009b13  test    rax, rax
0x180009b16  jnz     short loc_180009B3D
0x180009b18  mov     rcx, [rbp+188h]; this
0x180009b1f  lea     r8, aWil; "wil"
0x180009b26  mov     esi, 8007000Eh
0x180009b2b  mov     edx, 14Bh; void *
0x180009b30  mov     r9d, esi; char *
0x180009b33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b38  jmp     loc_180009BCF
0x180009b3d  xorps   xmm0, xmm0
0x180009b40  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180009b46  test    r14b, 3
0x180009b4a  jnz     loc_180009D37
0x180009b50  mov     r9, r14
0x180009b53  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180009b58  shr     r9, 2; unsigned __int64
0x180009b5c  lea     rcx, [rsp+280h+hObject]; this
0x180009b61  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180009b66  mov     esi, eax
0x180009b68  test    eax, eax
0x180009b6a  jns     loc_180009C16
0x180009b70  mov     rcx, [rbp+188h]; this
0x180009b77  lea     r8, aWil; "wil"
0x180009b7e  mov     r9d, eax; char *
0x180009b81  mov     edx, 14Eh; void *
0x180009b86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b8b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180009b90  test    rcx, rcx
0x180009b93  jz      short loc_180009BA3
0x180009b95  call    cs:__imp_CloseHandle
0x180009b9b  test    eax, eax
0x180009b9d  jz      loc_180009D3D
0x180009ba3  mov     rcx, [rsp+280h+hObject]; hObject
0x180009ba8  test    rcx, rcx
0x180009bab  jz      short loc_180009BBB
0x180009bad  call    cs:__imp_CloseHandle
0x180009bb3  test    eax, eax
0x180009bb5  jz      loc_180009D4F
0x180009bbb  call    cs:__imp_GetProcessHeap
0x180009bc1  mov     r8, r14; lpMem
0x180009bc4  xor     edx, edx; dwFlags
0x180009bc6  mov     rcx, rax; hHeap
0x180009bc9  call    cs:__imp_HeapFree
0x180009bcf  mov     rcx, [rbp+188h]; this
0x180009bd6  lea     r8, aWil; "wil"
0x180009bdd  mov     r9d, esi; char *
0x180009be0  mov     edx, 137h; void *
0x180009be5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009bea  test    rdi, rdi
0x180009bed  jz      short loc_180009C00
0x180009bef  mov     rcx, rdi; hMutex
0x180009bf2  call    cs:__imp_ReleaseMutex
0x180009bf8  test    eax, eax
0x180009bfa  jz      loc_180009D61
0x180009c00  mov     rcx, rbx; hObject
0x180009c03  call    cs:__imp_CloseHandle
0x180009c09  test    eax, eax
0x180009c0b  jz      loc_180009CE8
0x180009c11  jmp     loc_180009AD5
0x180009c16  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180009c1b  lea     rcx, [r14+28h]; void *
0x180009c1f  mov     dword ptr [r14], 1
0x180009c26  xor     edx, edx; Val
0x180009c28  mov     [r14+8], rbx
0x180009c2c  mov     r8d, 108h; Size
0x180009c32  movdqu  xmmword ptr [r14+10h], xmm0
0x180009c38  call    memset_0
0x180009c3d  xor     eax, eax
0x180009c3f  lea     rcx, [r14+28h]; this
0x180009c43  mov     [r14+20h], rax
0x180009c47  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009c4c  lea     rbx, [r14+0E8h]
0x180009c53  xor     r8d, r8d; Flags
0x180009c56  mov     rcx, rbx; lpCriticalSection
0x180009c59  xor     edx, edx; dwSpinCount
0x180009c5b  call    cs:__imp_InitializeCriticalSectionEx
0x180009c61  mov     qword ptr [rbx+28h], 0
0x180009c69  mov     qword ptr [rbx+30h], 0
0x180009c71  mov     qword ptr [rbx+38h], 0
0x180009c79  mov     qword ptr [rbx+40h], 0
0x180009c81  xor     ebx, ebx
0x180009c83  mov     [r15], r14
0x180009c86  test    rdi, rdi
0x180009c89  jz      short loc_180009C9C
0x180009c8b  mov     rcx, rdi; hMutex
0x180009c8e  call    cs:__imp_ReleaseMutex
0x180009c94  test    eax, eax
0x180009c96  jz      loc_180009D73
0x180009c9c  test    rbx, rbx
0x180009c9f  jz      short loc_180009CAE
0x180009ca1  mov     rcx, rbx; hObject
0x180009ca4  call    cs:__imp_CloseHandle
0x180009caa  test    eax, eax
0x180009cac  jz      short loc_180009CD6
0x180009cae  xor     eax, eax
0x180009cb0  mov     rcx, [rbp+180h+var_30]
0x180009cb7  xor     rcx, rsp; StackCookie
0x180009cba  call    __security_check_cookie
0x180009cbf  mov     rbx, [rsp+280h+arg_10]
0x180009cc7  add     rsp, 260h
0x180009cce  pop     r15
0x180009cd0  pop     r14
0x180009cd2  pop     rdi
0x180009cd3  pop     rsi
0x180009cd4  pop     rbp
0x180009cd5  retn
0x180009cd6  mov     rcx, [rbp+188h]; this
0x180009cdd  mov     edx, 0A0Bh; void *
0x180009ce2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009ce8  mov     rcx, [rbp+188h]; this
0x180009cef  mov     edx, 0A0Bh; void *
0x180009cf4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009cfa  mov     rcx, [rbp+188h]; this
0x180009d01  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009d08  mov     edx, 0E01h; void *
0x180009d0d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009d13  mov     rcx, [rbp+188h]; this
0x180009d1a  mov     edx, 0A15h; void *
0x180009d1f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d25  mov     rcx, [rbp+188h]; this
0x180009d2c  mov     edx, 0A0Bh; void *
0x180009d31  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d37  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009d3d  mov     rcx, [rbp+188h]; this
0x180009d44  mov     edx, 0A0Bh; void *
0x180009d49  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d4f  mov     rcx, [rbp+188h]; this
0x180009d56  mov     edx, 0A0Bh; void *
0x180009d5b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d61  mov     rcx, [rbp+188h]; this
0x180009d68  mov     edx, 0A15h; void *
0x180009d6d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d73  mov     rcx, [rbp+188h]; this
0x180009d7a  mov     edx, 0A15h; void *
0x180009d7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
