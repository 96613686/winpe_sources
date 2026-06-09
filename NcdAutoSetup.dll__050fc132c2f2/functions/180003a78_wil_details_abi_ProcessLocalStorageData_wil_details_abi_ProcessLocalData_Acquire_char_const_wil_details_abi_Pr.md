# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003a78`
- end: `0x180003e16`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800053cc`

## callees

- `0x180002514`
- `0x180003a78`
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

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ab1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b11`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003af0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003af0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ba3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ccc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ba3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ccc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d41`

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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x180003a78  mov     [rsp-8+arg_10], rbx
0x180003a7d  push    rbp
0x180003a7e  push    rsi
0x180003a7f  push    rdi
0x180003a80  push    r14
0x180003a82  push    r15
0x180003a84  lea     rbp, [rsp-160h]
0x180003a8c  sub     rsp, 260h
0x180003a93  mov     rax, cs:__security_cookie
0x180003a9a  xor     rax, rsp
0x180003a9d  mov     [rbp+180h+var_30], rax
0x180003aa4  mov     r15, rdx
0x180003aa7  mov     qword ptr [rdx], 0
0x180003aae  mov     rbx, rcx
0x180003ab1  call    cs:__imp_GetCurrentProcessId
0x180003ab7  mov     r14d, 78h ; 'x'
0x180003abd  mov     [rsp+280h+var_258], rbx
0x180003ac2  mov     r9d, eax
0x180003ac5  mov     [rsp+280h+var_260], r14d; int
0x180003aca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003ad1  mov     edx, 104h; unsigned __int64
0x180003ad6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003adb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003ae0  mov     r9d, 1F0001h; dwDesiredAccess
0x180003ae6  lea     rdx, [rsp+280h+Name]; lpName
0x180003aeb  xor     r8d, r8d; dwFlags
0x180003aee  xor     ecx, ecx; lpMutexAttributes
0x180003af0  call    cs:__imp_CreateMutexExW
0x180003af6  mov     rbx, rax
0x180003af9  test    rax, rax
0x180003afc  jnz     short loc_180003B08
0x180003afe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b03  jmp     loc_180003D4D
0x180003b08  xor     r8d, r8d; bAlertable
0x180003b0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003b0e  mov     rcx, rbx; hHandle
0x180003b11  call    cs:__imp_WaitForSingleObjectEx
0x180003b17  cmp     eax, 102h
0x180003b1c  jz      short loc_180003B2E
0x180003b1e  test    eax, 0FFFFFF7Fh
0x180003b23  jnz     loc_180003D85
0x180003b29  mov     rdi, rbx
0x180003b2c  jmp     short loc_180003B30
0x180003b2e  xor     edi, edi
0x180003b30  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003b35  mov     [rsp+280h+hObject], 0
0x180003b3e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003b43  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003b48  mov     esi, eax
0x180003b4a  test    eax, eax
0x180003b4c  jns     short loc_180003BB8
0x180003b4e  mov     rcx, [rbp+188h]; this
0x180003b55  mov     r9d, eax; char *
0x180003b58  mov     edx, 66h ; 'f'; void *
0x180003b5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b62  mov     rcx, [rbp+188h]; this
0x180003b69  mov     r9d, esi; char *
0x180003b6c  mov     edx, 6Fh ; 'o'; void *
0x180003b71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b76  mov     rcx, [rbp+188h]; this
0x180003b7d  mov     r9d, esi; char *
0x180003b80  mov     edx, 12Eh; void *
0x180003b85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b8a  test    rdi, rdi
0x180003b8d  jz      short loc_180003BA0
0x180003b8f  mov     rcx, rdi; hMutex
0x180003b92  call    cs:__imp_ReleaseMutex
0x180003b98  test    eax, eax
0x180003b9a  jz      loc_180003D92
0x180003ba0  mov     rcx, rbx; hObject
0x180003ba3  call    cs:__imp_CloseHandle
0x180003ba9  test    eax, eax
0x180003bab  jz      loc_180003DA4
0x180003bb1  mov     eax, esi
0x180003bb3  jmp     loc_180003D4D
0x180003bb8  mov     rax, [rsp+280h+hObject]
0x180003bbd  lea     rcx, ds:0[rax*4]
0x180003bc5  test    rcx, rcx
0x180003bc8  jz      short loc_180003BD8
0x180003bca  mov     [r15], rcx
0x180003bcd  mov     eax, [rcx]
0x180003bcf  inc     eax
0x180003bd1  mov     [rcx], eax
0x180003bd3  jmp     loc_180003D23
0x180003bd8  mov     rdx, r14; dwBytes
0x180003bdb  mov     qword ptr [r15], 0
0x180003be2  mov     ecx, 8; dwFlags
0x180003be7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003bec  mov     rsi, rax
0x180003bef  test    rax, rax
0x180003bf2  jnz     short loc_180003C13
0x180003bf4  mov     rcx, [rbp+188h]; this
0x180003bfb  mov     r14d, 8007000Eh
0x180003c01  mov     r9d, r14d; char *
0x180003c04  mov     edx, 14Bh; void *
0x180003c09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c0e  jmp     loc_180003C9F
0x180003c13  xorps   xmm0, xmm0
0x180003c16  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003c1c  test    sil, 3
0x180003c20  jnz     loc_180003DB6
0x180003c26  mov     r9, rsi
0x180003c29  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003c2e  shr     r9, 2; unsigned __int64
0x180003c32  lea     rcx, [rsp+280h+hObject]; this
0x180003c37  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003c3c  mov     r14d, eax
0x180003c3f  test    eax, eax
0x180003c41  jns     loc_180003CDF
0x180003c47  mov     rcx, [rbp+188h]; this
0x180003c4e  mov     r9d, eax; char *
0x180003c51  mov     edx, 14Eh; void *
0x180003c56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c5b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003c60  test    rcx, rcx
0x180003c63  jz      short loc_180003C73
0x180003c65  call    cs:__imp_CloseHandle
0x180003c6b  test    eax, eax
0x180003c6d  jz      loc_180003DBC
0x180003c73  mov     rcx, [rsp+280h+hObject]; hObject
0x180003c78  test    rcx, rcx
0x180003c7b  jz      short loc_180003C8B
0x180003c7d  call    cs:__imp_CloseHandle
0x180003c83  test    eax, eax
0x180003c85  jz      loc_180003DCE
0x180003c8b  call    cs:__imp_GetProcessHeap
0x180003c91  mov     r8, rsi; lpMem
0x180003c94  xor     edx, edx; dwFlags
0x180003c96  mov     rcx, rax; hHeap
0x180003c99  call    cs:__imp_HeapFree
0x180003c9f  mov     rcx, [rbp+188h]; this
0x180003ca6  mov     r9d, r14d; char *
0x180003ca9  mov     edx, 137h; void *
0x180003cae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cb3  test    rdi, rdi
0x180003cb6  jz      short loc_180003CC9
0x180003cb8  mov     rcx, rdi; hMutex
0x180003cbb  call    cs:__imp_ReleaseMutex
0x180003cc1  test    eax, eax
0x180003cc3  jz      loc_180003DE0
0x180003cc9  mov     rcx, rbx; hObject
0x180003ccc  call    cs:__imp_CloseHandle
0x180003cd2  test    eax, eax
0x180003cd4  jz      loc_180003DF2
0x180003cda  mov     eax, r14d
0x180003cdd  jmp     short loc_180003D4D
0x180003cdf  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003ce4  xor     edx, edx; Val
0x180003ce6  mov     dword ptr [rsi], 1
0x180003cec  lea     rcx, [rsi+22h]; void *
0x180003cf0  mov     [rsi+8], rbx
0x180003cf4  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003cf9  lea     r8d, [rdx+56h]; Size
0x180003cfd  call    memset_0
0x180003d02  xor     edx, edx; Val
0x180003d04  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003d0a  lea     rcx, [rsi+28h]; void *
0x180003d0e  mov     dword ptr [rsi+24h], 1
0x180003d15  lea     r8d, [rdx+50h]; Size
0x180003d19  call    memset_0
0x180003d1e  xor     ebx, ebx
0x180003d20  mov     [r15], rsi
0x180003d23  test    rdi, rdi
0x180003d26  jz      short loc_180003D39
0x180003d28  mov     rcx, rdi; hMutex
0x180003d2b  call    cs:__imp_ReleaseMutex
0x180003d31  test    eax, eax
0x180003d33  jz      loc_180003E04
0x180003d39  test    rbx, rbx
0x180003d3c  jz      short loc_180003D4B
0x180003d3e  mov     rcx, rbx; hObject
0x180003d41  call    cs:__imp_CloseHandle
0x180003d47  test    eax, eax
0x180003d49  jz      short loc_180003D73
0x180003d4b  xor     eax, eax
0x180003d4d  mov     rcx, [rbp+180h+var_30]
0x180003d54  xor     rcx, rsp; StackCookie
0x180003d57  call    __security_check_cookie
0x180003d5c  mov     rbx, [rsp+280h+arg_10]
0x180003d64  add     rsp, 260h
0x180003d6b  pop     r15
0x180003d6d  pop     r14
0x180003d6f  pop     rdi
0x180003d70  pop     rsi
0x180003d71  pop     rbp
0x180003d72  retn
0x180003d73  mov     rcx, [rbp+188h]; this
0x180003d7a  mov     edx, 0A0Bh; void *
0x180003d7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d85  mov     rcx, [rbp+188h]; this
0x180003d8c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003d92  mov     rcx, [rbp+188h]; this
0x180003d99  mov     edx, 0A15h; void *
0x180003d9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003da4  mov     rcx, [rbp+188h]; this
0x180003dab  mov     edx, 0A0Bh; void *
0x180003db0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003db6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003dbc  mov     rcx, [rbp+188h]; this
0x180003dc3  mov     edx, 0A0Bh; void *
0x180003dc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003dce  mov     rcx, [rbp+188h]; this
0x180003dd5  mov     edx, 0A0Bh; void *
0x180003dda  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003de0  mov     rcx, [rbp+188h]; this
0x180003de7  mov     edx, 0A15h; void *
0x180003dec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003df2  mov     rcx, [rbp+188h]; this
0x180003df9  mov     edx, 0A0Bh; void *
0x180003dfe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e04  mov     rcx, [rbp+188h]; this
0x180003e0b  mov     edx, 0A15h; void *
0x180003e10  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
