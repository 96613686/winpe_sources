# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800088b8`
- end: `0x180008c8c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000a454`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x1800088b8`
- `0x180009098`
- `0x180009634`
- `0x18000a0f8`
- `0x18000aff8`
- `0x18000c964`
- `0x18000d4ec`
- `0x18000dacc`
- `0x18000e4b8`
- `0x18000e4c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800089e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008b25`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008b95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800089e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008b25`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008b95`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008930`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008930`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008951`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008951`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008aee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008aee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008afc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008afc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800088f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800088f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ac8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ae0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ac8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ae0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bab`

## string_xrefs

- `0x180008bf6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v41);
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
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v35 = *(_OWORD *)hObject;
      *(_DWORD *)v23 = 1;
      v23[1] = v6;
      *((_OWORD *)v23 + 1) = v35;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v23;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v24, v42);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v24;
}

```

## disassembly

```asm
0x1800088b8  mov     [rsp-8+arg_10], rbx
0x1800088bd  push    rbp
0x1800088be  push    rsi
0x1800088bf  push    rdi
0x1800088c0  push    r14
0x1800088c2  push    r15
0x1800088c4  lea     rbp, [rsp-160h]
0x1800088cc  sub     rsp, 260h
0x1800088d3  mov     rax, cs:__security_cookie
0x1800088da  xor     rax, rsp
0x1800088dd  mov     [rbp+180h+var_30], rax
0x1800088e4  mov     r15, rdx
0x1800088e7  mov     qword ptr [rdx], 0
0x1800088ee  mov     rbx, rcx
0x1800088f1  call    cs:__imp_GetCurrentProcessId
0x1800088f7  mov     r14d, 78h ; 'x'
0x1800088fd  mov     [rsp+280h+var_258], rbx
0x180008902  mov     r9d, eax
0x180008905  mov     [rsp+280h+var_260], r14d; int
0x18000890a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008911  mov     edx, 104h; unsigned __int64
0x180008916  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000891b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008920  mov     r9d, 1F0001h; dwDesiredAccess
0x180008926  lea     rdx, [rsp+280h+Name]; lpName
0x18000892b  xor     r8d, r8d; dwFlags
0x18000892e  xor     ecx, ecx; lpMutexAttributes
0x180008930  call    cs:__imp_CreateMutexExW
0x180008936  mov     rbx, rax
0x180008939  test    rax, rax
0x18000893c  jnz     short loc_180008948
0x18000893e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008943  jmp     loc_180008BB7
0x180008948  xor     r8d, r8d; bAlertable
0x18000894b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000894e  mov     rcx, rbx; hHandle
0x180008951  call    cs:__imp_WaitForSingleObjectEx
0x180008957  cmp     eax, 102h
0x18000895c  jz      short loc_18000896E
0x18000895e  test    eax, 0FFFFFF7Fh
0x180008963  jnz     loc_180008BEF
0x180008969  mov     rdi, rbx
0x18000896c  jmp     short loc_180008970
0x18000896e  xor     edi, edi
0x180008970  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008975  mov     [rsp+280h+hObject], 0
0x18000897e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008983  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008988  mov     esi, eax
0x18000898a  test    eax, eax
0x18000898c  jns     short loc_180008A0D
0x18000898e  mov     rcx, [rbp+188h]; this
0x180008995  lea     r8, aWil; "wil"
0x18000899c  mov     r9d, eax; char *
0x18000899f  mov     edx, 66h ; 'f'; void *
0x1800089a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089a9  mov     rcx, [rbp+188h]; this
0x1800089b0  lea     r8, aWil; "wil"
0x1800089b7  mov     r9d, esi; char *
0x1800089ba  mov     edx, 6Fh ; 'o'; void *
0x1800089bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089c4  mov     rcx, [rbp+188h]; this
0x1800089cb  lea     r8, aWil; "wil"
0x1800089d2  mov     r9d, esi; char *
0x1800089d5  mov     edx, 12Eh; void *
0x1800089da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089df  test    rdi, rdi
0x1800089e2  jz      short loc_1800089F5
0x1800089e4  mov     rcx, rdi; hMutex
0x1800089e7  call    cs:__imp_ReleaseMutex
0x1800089ed  test    eax, eax
0x1800089ef  jz      loc_180008C08
0x1800089f5  mov     rcx, rbx; hObject
0x1800089f8  call    cs:__imp_CloseHandle
0x1800089fe  test    eax, eax
0x180008a00  jz      loc_180008C1A
0x180008a06  mov     eax, esi
0x180008a08  jmp     loc_180008BB7
0x180008a0d  mov     rax, [rsp+280h+hObject]
0x180008a12  lea     rcx, ds:0[rax*4]
0x180008a1a  test    rcx, rcx
0x180008a1d  jz      short loc_180008A2D
0x180008a1f  mov     [r15], rcx
0x180008a22  mov     eax, [rcx]
0x180008a24  inc     eax
0x180008a26  mov     [rcx], eax
0x180008a28  jmp     loc_180008B8D
0x180008a2d  mov     rdx, r14; dwBytes
0x180008a30  mov     qword ptr [r15], 0
0x180008a37  mov     ecx, 8; dwFlags
0x180008a3c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008a41  mov     rsi, rax
0x180008a44  test    rax, rax
0x180008a47  jnz     short loc_180008A6F
0x180008a49  mov     rcx, [rbp+188h]; this
0x180008a50  lea     r8, aWil; "wil"
0x180008a57  mov     r14d, 8007000Eh
0x180008a5d  mov     edx, 14Bh; void *
0x180008a62  mov     r9d, r14d; char *
0x180008a65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a6a  jmp     loc_180008B02
0x180008a6f  xorps   xmm0, xmm0
0x180008a72  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180008a78  test    sil, 3
0x180008a7c  jnz     loc_180008C2C
0x180008a82  mov     r9, rsi
0x180008a85  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180008a8a  shr     r9, 2; unsigned __int64
0x180008a8e  lea     rcx, [rsp+280h+hObject]; this
0x180008a93  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180008a98  mov     r14d, eax
0x180008a9b  test    eax, eax
0x180008a9d  jns     loc_180008B49
0x180008aa3  mov     rcx, [rbp+188h]; this
0x180008aaa  lea     r8, aWil; "wil"
0x180008ab1  mov     r9d, eax; char *
0x180008ab4  mov     edx, 14Eh; void *
0x180008ab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008abe  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180008ac3  test    rcx, rcx
0x180008ac6  jz      short loc_180008AD6
0x180008ac8  call    cs:__imp_CloseHandle
0x180008ace  test    eax, eax
0x180008ad0  jz      loc_180008C32
0x180008ad6  mov     rcx, [rsp+280h+hObject]; hObject
0x180008adb  test    rcx, rcx
0x180008ade  jz      short loc_180008AEE
0x180008ae0  call    cs:__imp_CloseHandle
0x180008ae6  test    eax, eax
0x180008ae8  jz      loc_180008C44
0x180008aee  call    cs:__imp_GetProcessHeap
0x180008af4  mov     r8, rsi; lpMem
0x180008af7  xor     edx, edx; dwFlags
0x180008af9  mov     rcx, rax; hHeap
0x180008afc  call    cs:__imp_HeapFree
0x180008b02  mov     rcx, [rbp+188h]; this
0x180008b09  lea     r8, aWil; "wil"
0x180008b10  mov     r9d, r14d; char *
0x180008b13  mov     edx, 137h; void *
0x180008b18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b1d  test    rdi, rdi
0x180008b20  jz      short loc_180008B33
0x180008b22  mov     rcx, rdi; hMutex
0x180008b25  call    cs:__imp_ReleaseMutex
0x180008b2b  test    eax, eax
0x180008b2d  jz      loc_180008C56
0x180008b33  mov     rcx, rbx; hObject
0x180008b36  call    cs:__imp_CloseHandle
0x180008b3c  test    eax, eax
0x180008b3e  jz      loc_180008C68
0x180008b44  mov     eax, r14d
0x180008b47  jmp     short loc_180008BB7
0x180008b49  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008b4e  xor     edx, edx; Val
0x180008b50  mov     dword ptr [rsi], 1
0x180008b56  lea     rcx, [rsi+22h]; void *
0x180008b5a  mov     [rsi+8], rbx
0x180008b5e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180008b63  lea     r8d, [rdx+56h]; Size
0x180008b67  call    memset_0
0x180008b6c  xor     edx, edx; Val
0x180008b6e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180008b74  lea     rcx, [rsi+28h]; void *
0x180008b78  mov     dword ptr [rsi+24h], 1
0x180008b7f  lea     r8d, [rdx+50h]; Size
0x180008b83  call    memset_0
0x180008b88  xor     ebx, ebx
0x180008b8a  mov     [r15], rsi
0x180008b8d  test    rdi, rdi
0x180008b90  jz      short loc_180008BA3
0x180008b92  mov     rcx, rdi; hMutex
0x180008b95  call    cs:__imp_ReleaseMutex
0x180008b9b  test    eax, eax
0x180008b9d  jz      loc_180008C7A
0x180008ba3  test    rbx, rbx
0x180008ba6  jz      short loc_180008BB5
0x180008ba8  mov     rcx, rbx; hObject
0x180008bab  call    cs:__imp_CloseHandle
0x180008bb1  test    eax, eax
0x180008bb3  jz      short loc_180008BDD
0x180008bb5  xor     eax, eax
0x180008bb7  mov     rcx, [rbp+180h+var_30]
0x180008bbe  xor     rcx, rsp; StackCookie
0x180008bc1  call    __security_check_cookie
0x180008bc6  mov     rbx, [rsp+280h+arg_10]
0x180008bce  add     rsp, 260h
0x180008bd5  pop     r15
0x180008bd7  pop     r14
0x180008bd9  pop     rdi
0x180008bda  pop     rsi
0x180008bdb  pop     rbp
0x180008bdc  retn
0x180008bdd  mov     rcx, [rbp+188h]; this
0x180008be4  mov     edx, 0A0Bh; void *
0x180008be9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008bef  mov     rcx, [rbp+188h]; this
0x180008bf6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008bfd  mov     edx, 0E01h; void *
0x180008c02  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180008c08  mov     rcx, [rbp+188h]; this
0x180008c0f  mov     edx, 0A15h; void *
0x180008c14  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008c1a  mov     rcx, [rbp+188h]; this
0x180008c21  mov     edx, 0A0Bh; void *
0x180008c26  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008c2c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008c32  mov     rcx, [rbp+188h]; this
0x180008c39  mov     edx, 0A0Bh; void *
0x180008c3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008c44  mov     rcx, [rbp+188h]; this
0x180008c4b  mov     edx, 0A0Bh; void *
0x180008c50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008c56  mov     rcx, [rbp+188h]; this
0x180008c5d  mov     edx, 0A15h; void *
0x180008c62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008c68  mov     rcx, [rbp+188h]; this
0x180008c6f  mov     edx, 0A0Bh; void *
0x180008c74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008c7a  mov     rcx, [rbp+188h]; this
0x180008c81  mov     edx, 0A15h; void *
0x180008c86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
