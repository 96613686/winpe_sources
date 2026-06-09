# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003978`
- end: `0x180003d40`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005820`

## callees

- `0x180001ef0`
- `0x180002958`
- `0x180003978`
- `0x1800048e0`
- `0x180004fcc`
- `0x1800055b8`
- `0x18000654c`
- `0x180007744`
- `0x180008184`
- `0x18000823c`
- `0x1800088e4`
- `0x1800088f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003aa7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003be5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c55`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003aa7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003be5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003a11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003a11`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800039f0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800039f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003bae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003bae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003bbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003bbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800039b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800039b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c6b`

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
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x180003978  mov     [rsp-8+arg_10], rbx
0x18000397d  push    rbp
0x18000397e  push    rsi
0x18000397f  push    rdi
0x180003980  push    r14
0x180003982  push    r15
0x180003984  lea     rbp, [rsp-160h]
0x18000398c  sub     rsp, 260h
0x180003993  mov     rax, cs:__security_cookie
0x18000399a  xor     rax, rsp
0x18000399d  mov     [rbp+180h+var_30], rax
0x1800039a4  mov     r15, rdx
0x1800039a7  mov     qword ptr [rdx], 0
0x1800039ae  mov     rbx, rcx
0x1800039b1  call    cs:__imp_GetCurrentProcessId
0x1800039b7  mov     r14d, 78h ; 'x'
0x1800039bd  mov     [rsp+280h+var_258], rbx
0x1800039c2  mov     r9d, eax
0x1800039c5  mov     [rsp+280h+var_260], r14d; int
0x1800039ca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800039d1  mov     edx, 104h; unsigned __int64
0x1800039d6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800039db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800039e0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800039e6  lea     rdx, [rsp+280h+Name]; lpName
0x1800039eb  xor     r8d, r8d; dwFlags
0x1800039ee  xor     ecx, ecx; lpMutexAttributes
0x1800039f0  call    cs:__imp_CreateMutexExW
0x1800039f6  mov     rbx, rax
0x1800039f9  test    rax, rax
0x1800039fc  jnz     short loc_180003A08
0x1800039fe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003a03  jmp     loc_180003C77
0x180003a08  xor     r8d, r8d; bAlertable
0x180003a0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003a0e  mov     rcx, rbx; hHandle
0x180003a11  call    cs:__imp_WaitForSingleObjectEx
0x180003a17  cmp     eax, 102h
0x180003a1c  jz      short loc_180003A2E
0x180003a1e  test    eax, 0FFFFFF7Fh
0x180003a23  jnz     loc_180003CAF
0x180003a29  mov     rdi, rbx
0x180003a2c  jmp     short loc_180003A30
0x180003a2e  xor     edi, edi
0x180003a30  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003a35  mov     [rsp+280h+hObject], 0
0x180003a3e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003a43  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003a48  mov     esi, eax
0x180003a4a  test    eax, eax
0x180003a4c  jns     short loc_180003ACD
0x180003a4e  mov     rcx, [rbp+188h]; this
0x180003a55  lea     r8, aWil; "wil"
0x180003a5c  mov     r9d, eax; char *
0x180003a5f  mov     edx, 66h ; 'f'; void *
0x180003a64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a69  mov     rcx, [rbp+188h]; this
0x180003a70  lea     r8, aWil; "wil"
0x180003a77  mov     r9d, esi; char *
0x180003a7a  mov     edx, 6Fh ; 'o'; void *
0x180003a7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a84  mov     rcx, [rbp+188h]; this
0x180003a8b  lea     r8, aWil; "wil"
0x180003a92  mov     r9d, esi; char *
0x180003a95  mov     edx, 12Eh; void *
0x180003a9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a9f  test    rdi, rdi
0x180003aa2  jz      short loc_180003AB5
0x180003aa4  mov     rcx, rdi; hMutex
0x180003aa7  call    cs:__imp_ReleaseMutex
0x180003aad  test    eax, eax
0x180003aaf  jz      loc_180003CBC
0x180003ab5  mov     rcx, rbx; hObject
0x180003ab8  call    cs:__imp_CloseHandle
0x180003abe  test    eax, eax
0x180003ac0  jz      loc_180003CCE
0x180003ac6  mov     eax, esi
0x180003ac8  jmp     loc_180003C77
0x180003acd  mov     rax, [rsp+280h+hObject]
0x180003ad2  lea     rcx, ds:0[rax*4]
0x180003ada  test    rcx, rcx
0x180003add  jz      short loc_180003AED
0x180003adf  mov     [r15], rcx
0x180003ae2  mov     eax, [rcx]
0x180003ae4  inc     eax
0x180003ae6  mov     [rcx], eax
0x180003ae8  jmp     loc_180003C4D
0x180003aed  mov     rdx, r14; dwBytes
0x180003af0  mov     qword ptr [r15], 0
0x180003af7  mov     ecx, 8; dwFlags
0x180003afc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003b01  mov     rsi, rax
0x180003b04  test    rax, rax
0x180003b07  jnz     short loc_180003B2F
0x180003b09  mov     rcx, [rbp+188h]; this
0x180003b10  lea     r8, aWil; "wil"
0x180003b17  mov     r14d, 8007000Eh
0x180003b1d  mov     edx, 14Bh; void *
0x180003b22  mov     r9d, r14d; char *
0x180003b25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b2a  jmp     loc_180003BC2
0x180003b2f  xorps   xmm0, xmm0
0x180003b32  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003b38  test    sil, 3
0x180003b3c  jnz     loc_180003CE0
0x180003b42  mov     r9, rsi
0x180003b45  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003b4a  shr     r9, 2; unsigned __int64
0x180003b4e  lea     rcx, [rsp+280h+hObject]; this
0x180003b53  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003b58  mov     r14d, eax
0x180003b5b  test    eax, eax
0x180003b5d  jns     loc_180003C09
0x180003b63  mov     rcx, [rbp+188h]; this
0x180003b6a  lea     r8, aWil; "wil"
0x180003b71  mov     r9d, eax; char *
0x180003b74  mov     edx, 14Eh; void *
0x180003b79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b7e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003b83  test    rcx, rcx
0x180003b86  jz      short loc_180003B96
0x180003b88  call    cs:__imp_CloseHandle
0x180003b8e  test    eax, eax
0x180003b90  jz      loc_180003CE6
0x180003b96  mov     rcx, [rsp+280h+hObject]; hObject
0x180003b9b  test    rcx, rcx
0x180003b9e  jz      short loc_180003BAE
0x180003ba0  call    cs:__imp_CloseHandle
0x180003ba6  test    eax, eax
0x180003ba8  jz      loc_180003CF8
0x180003bae  call    cs:__imp_GetProcessHeap
0x180003bb4  mov     r8, rsi; lpMem
0x180003bb7  xor     edx, edx; dwFlags
0x180003bb9  mov     rcx, rax; hHeap
0x180003bbc  call    cs:__imp_HeapFree
0x180003bc2  mov     rcx, [rbp+188h]; this
0x180003bc9  lea     r8, aWil; "wil"
0x180003bd0  mov     r9d, r14d; char *
0x180003bd3  mov     edx, 137h; void *
0x180003bd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bdd  test    rdi, rdi
0x180003be0  jz      short loc_180003BF3
0x180003be2  mov     rcx, rdi; hMutex
0x180003be5  call    cs:__imp_ReleaseMutex
0x180003beb  test    eax, eax
0x180003bed  jz      loc_180003D0A
0x180003bf3  mov     rcx, rbx; hObject
0x180003bf6  call    cs:__imp_CloseHandle
0x180003bfc  test    eax, eax
0x180003bfe  jz      loc_180003D1C
0x180003c04  mov     eax, r14d
0x180003c07  jmp     short loc_180003C77
0x180003c09  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003c0e  xor     edx, edx; Val
0x180003c10  mov     dword ptr [rsi], 1
0x180003c16  lea     rcx, [rsi+22h]; void *
0x180003c1a  mov     [rsi+8], rbx
0x180003c1e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003c23  lea     r8d, [rdx+56h]; Size
0x180003c27  call    memset_0
0x180003c2c  xor     edx, edx; Val
0x180003c2e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003c34  lea     rcx, [rsi+28h]; void *
0x180003c38  mov     dword ptr [rsi+24h], 1
0x180003c3f  lea     r8d, [rdx+50h]; Size
0x180003c43  call    memset_0
0x180003c48  xor     ebx, ebx
0x180003c4a  mov     [r15], rsi
0x180003c4d  test    rdi, rdi
0x180003c50  jz      short loc_180003C63
0x180003c52  mov     rcx, rdi; hMutex
0x180003c55  call    cs:__imp_ReleaseMutex
0x180003c5b  test    eax, eax
0x180003c5d  jz      loc_180003D2E
0x180003c63  test    rbx, rbx
0x180003c66  jz      short loc_180003C75
0x180003c68  mov     rcx, rbx; hObject
0x180003c6b  call    cs:__imp_CloseHandle
0x180003c71  test    eax, eax
0x180003c73  jz      short loc_180003C9D
0x180003c75  xor     eax, eax
0x180003c77  mov     rcx, [rbp+180h+var_30]
0x180003c7e  xor     rcx, rsp; StackCookie
0x180003c81  call    __security_check_cookie
0x180003c86  mov     rbx, [rsp+280h+arg_10]
0x180003c8e  add     rsp, 260h
0x180003c95  pop     r15
0x180003c97  pop     r14
0x180003c99  pop     rdi
0x180003c9a  pop     rsi
0x180003c9b  pop     rbp
0x180003c9c  retn
0x180003c9d  mov     rcx, [rbp+188h]; this
0x180003ca4  mov     edx, 0A0Bh; void *
0x180003ca9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003caf  mov     rcx, [rbp+188h]; this
0x180003cb6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003cbc  mov     rcx, [rbp+188h]; this
0x180003cc3  mov     edx, 0A15h; void *
0x180003cc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003cce  mov     rcx, [rbp+188h]; this
0x180003cd5  mov     edx, 0A0Bh; void *
0x180003cda  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ce0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003ce6  mov     rcx, [rbp+188h]; this
0x180003ced  mov     edx, 0A0Bh; void *
0x180003cf2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003cf8  mov     rcx, [rbp+188h]; this
0x180003cff  mov     edx, 0A0Bh; void *
0x180003d04  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d0a  mov     rcx, [rbp+188h]; this
0x180003d11  mov     edx, 0A15h; void *
0x180003d16  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d1c  mov     rcx, [rbp+188h]; this
0x180003d23  mov     edx, 0A0Bh; void *
0x180003d28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d2e  mov     rcx, [rbp+188h]; this
0x180003d35  mov     edx, 0A15h; void *
0x180003d3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
