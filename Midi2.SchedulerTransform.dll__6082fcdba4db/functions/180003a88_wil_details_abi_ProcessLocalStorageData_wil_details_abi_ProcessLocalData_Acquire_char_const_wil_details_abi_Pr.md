# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003a88`
- end: `0x180003e55`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005930`

## callees

- `0x180002000`
- `0x180002a68`
- `0x180003a88`
- `0x1800049f0`
- `0x1800050dc`
- `0x1800056c8`
- `0x18000665c`
- `0x180007864`
- `0x1800082a4`
- `0x18000835c`
- `0x180008a04`
- `0x180008a14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b00`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b00`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d65`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b21`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ccc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ccc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ac1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003ac1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d7b`

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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x180003a88  mov     [rsp-8+arg_10], rbx
0x180003a8d  push    rbp
0x180003a8e  push    rsi
0x180003a8f  push    rdi
0x180003a90  push    r14
0x180003a92  push    r15
0x180003a94  lea     rbp, [rsp-160h]
0x180003a9c  sub     rsp, 260h
0x180003aa3  mov     rax, cs:__security_cookie
0x180003aaa  xor     rax, rsp
0x180003aad  mov     [rbp+180h+var_30], rax
0x180003ab4  mov     r15, rdx
0x180003ab7  mov     qword ptr [rdx], 0
0x180003abe  mov     rbx, rcx
0x180003ac1  call    cs:__imp_GetCurrentProcessId
0x180003ac7  mov     r14d, 78h ; 'x'
0x180003acd  mov     [rsp+280h+var_258], rbx
0x180003ad2  mov     r9d, eax
0x180003ad5  mov     [rsp+280h+var_260], r14d; int
0x180003ada  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003ae1  mov     edx, 104h; unsigned __int64
0x180003ae6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003aeb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003af0  mov     r9d, 1F0001h; dwDesiredAccess
0x180003af6  lea     rdx, [rsp+280h+Name]; lpName
0x180003afb  xor     r8d, r8d; dwFlags
0x180003afe  xor     ecx, ecx; lpMutexAttributes
0x180003b00  call    cs:__imp_CreateMutexExW
0x180003b06  mov     rbx, rax
0x180003b09  test    rax, rax
0x180003b0c  jnz     short loc_180003B18
0x180003b0e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b13  jmp     loc_180003D87
0x180003b18  xor     r8d, r8d; bAlertable
0x180003b1b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003b1e  mov     rcx, rbx; hHandle
0x180003b21  call    cs:__imp_WaitForSingleObjectEx
0x180003b27  cmp     eax, 102h
0x180003b2c  jz      short loc_180003B3E
0x180003b2e  test    eax, 0FFFFFF7Fh
0x180003b33  jnz     loc_180003DBF
0x180003b39  mov     rdi, rbx
0x180003b3c  jmp     short loc_180003B40
0x180003b3e  xor     edi, edi
0x180003b40  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003b45  mov     [rsp+280h+hObject], 0
0x180003b4e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003b53  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003b58  mov     esi, eax
0x180003b5a  test    eax, eax
0x180003b5c  jns     short loc_180003BDD
0x180003b5e  mov     rcx, [rbp+188h]; this
0x180003b65  lea     r8, aWil; "wil"
0x180003b6c  mov     r9d, eax; char *
0x180003b6f  mov     edx, 66h ; 'f'; void *
0x180003b74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b79  mov     rcx, [rbp+188h]; this
0x180003b80  lea     r8, aWil; "wil"
0x180003b87  mov     r9d, esi; char *
0x180003b8a  mov     edx, 6Fh ; 'o'; void *
0x180003b8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b94  mov     rcx, [rbp+188h]; this
0x180003b9b  lea     r8, aWil; "wil"
0x180003ba2  mov     r9d, esi; char *
0x180003ba5  mov     edx, 12Eh; void *
0x180003baa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003baf  test    rdi, rdi
0x180003bb2  jz      short loc_180003BC5
0x180003bb4  mov     rcx, rdi; hMutex
0x180003bb7  call    cs:__imp_ReleaseMutex
0x180003bbd  test    eax, eax
0x180003bbf  jz      loc_180003DD1
0x180003bc5  mov     rcx, rbx; hObject
0x180003bc8  call    cs:__imp_CloseHandle
0x180003bce  test    eax, eax
0x180003bd0  jz      loc_180003DE3
0x180003bd6  mov     eax, esi
0x180003bd8  jmp     loc_180003D87
0x180003bdd  mov     rax, [rsp+280h+hObject]
0x180003be2  lea     rcx, ds:0[rax*4]
0x180003bea  test    rcx, rcx
0x180003bed  jz      short loc_180003BFD
0x180003bef  mov     [r15], rcx
0x180003bf2  mov     eax, [rcx]
0x180003bf4  inc     eax
0x180003bf6  mov     [rcx], eax
0x180003bf8  jmp     loc_180003D5D
0x180003bfd  mov     rdx, r14; dwBytes
0x180003c00  mov     qword ptr [r15], 0
0x180003c07  mov     ecx, 8; dwFlags
0x180003c0c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003c11  mov     rsi, rax
0x180003c14  test    rax, rax
0x180003c17  jnz     short loc_180003C3F
0x180003c19  mov     rcx, [rbp+188h]; this
0x180003c20  lea     r8, aWil; "wil"
0x180003c27  mov     r14d, 8007000Eh
0x180003c2d  mov     edx, 14Bh; void *
0x180003c32  mov     r9d, r14d; char *
0x180003c35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c3a  jmp     loc_180003CD2
0x180003c3f  xorps   xmm0, xmm0
0x180003c42  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003c48  test    sil, 3
0x180003c4c  jnz     loc_180003DF5
0x180003c52  mov     r9, rsi
0x180003c55  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003c5a  shr     r9, 2; unsigned __int64
0x180003c5e  lea     rcx, [rsp+280h+hObject]; this
0x180003c63  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003c68  mov     r14d, eax
0x180003c6b  test    eax, eax
0x180003c6d  jns     loc_180003D19
0x180003c73  mov     rcx, [rbp+188h]; this
0x180003c7a  lea     r8, aWil; "wil"
0x180003c81  mov     r9d, eax; char *
0x180003c84  mov     edx, 14Eh; void *
0x180003c89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c8e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003c93  test    rcx, rcx
0x180003c96  jz      short loc_180003CA6
0x180003c98  call    cs:__imp_CloseHandle
0x180003c9e  test    eax, eax
0x180003ca0  jz      loc_180003DFB
0x180003ca6  mov     rcx, [rsp+280h+hObject]; hObject
0x180003cab  test    rcx, rcx
0x180003cae  jz      short loc_180003CBE
0x180003cb0  call    cs:__imp_CloseHandle
0x180003cb6  test    eax, eax
0x180003cb8  jz      loc_180003E0D
0x180003cbe  call    cs:__imp_GetProcessHeap
0x180003cc4  mov     r8, rsi; lpMem
0x180003cc7  xor     edx, edx; dwFlags
0x180003cc9  mov     rcx, rax; hHeap
0x180003ccc  call    cs:__imp_HeapFree
0x180003cd2  mov     rcx, [rbp+188h]; this
0x180003cd9  lea     r8, aWil; "wil"
0x180003ce0  mov     r9d, r14d; char *
0x180003ce3  mov     edx, 137h; void *
0x180003ce8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ced  test    rdi, rdi
0x180003cf0  jz      short loc_180003D03
0x180003cf2  mov     rcx, rdi; hMutex
0x180003cf5  call    cs:__imp_ReleaseMutex
0x180003cfb  test    eax, eax
0x180003cfd  jz      loc_180003E1F
0x180003d03  mov     rcx, rbx; hObject
0x180003d06  call    cs:__imp_CloseHandle
0x180003d0c  test    eax, eax
0x180003d0e  jz      loc_180003E31
0x180003d14  mov     eax, r14d
0x180003d17  jmp     short loc_180003D87
0x180003d19  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003d1e  xor     edx, edx; Val
0x180003d20  mov     dword ptr [rsi], 1
0x180003d26  lea     rcx, [rsi+22h]; void *
0x180003d2a  mov     [rsi+8], rbx
0x180003d2e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003d33  lea     r8d, [rdx+56h]; Size
0x180003d37  call    memset_0
0x180003d3c  xor     edx, edx; Val
0x180003d3e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003d44  lea     rcx, [rsi+28h]; void *
0x180003d48  mov     dword ptr [rsi+24h], 1
0x180003d4f  lea     r8d, [rdx+50h]; Size
0x180003d53  call    memset_0
0x180003d58  xor     ebx, ebx
0x180003d5a  mov     [r15], rsi
0x180003d5d  test    rdi, rdi
0x180003d60  jz      short loc_180003D73
0x180003d62  mov     rcx, rdi; hMutex
0x180003d65  call    cs:__imp_ReleaseMutex
0x180003d6b  test    eax, eax
0x180003d6d  jz      loc_180003E43
0x180003d73  test    rbx, rbx
0x180003d76  jz      short loc_180003D85
0x180003d78  mov     rcx, rbx; hObject
0x180003d7b  call    cs:__imp_CloseHandle
0x180003d81  test    eax, eax
0x180003d83  jz      short loc_180003DAD
0x180003d85  xor     eax, eax
0x180003d87  mov     rcx, [rbp+180h+var_30]
0x180003d8e  xor     rcx, rsp; StackCookie
0x180003d91  call    __security_check_cookie
0x180003d96  mov     rbx, [rsp+280h+arg_10]
0x180003d9e  add     rsp, 260h
0x180003da5  pop     r15
0x180003da7  pop     r14
0x180003da9  pop     rdi
0x180003daa  pop     rsi
0x180003dab  pop     rbp
0x180003dac  retn
0x180003dad  mov     rcx, [rbp+188h]; this
0x180003db4  mov     edx, 0A0Bh; void *
0x180003db9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003dbf  mov     rcx, [rbp+188h]; this
0x180003dc6  mov     edx, 0E01h; void *
0x180003dcb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003dd1  mov     rcx, [rbp+188h]; this
0x180003dd8  mov     edx, 0A15h; void *
0x180003ddd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003de3  mov     rcx, [rbp+188h]; this
0x180003dea  mov     edx, 0A0Bh; void *
0x180003def  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003df5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003dfb  mov     rcx, [rbp+188h]; this
0x180003e02  mov     edx, 0A0Bh; void *
0x180003e07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e0d  mov     rcx, [rbp+188h]; this
0x180003e14  mov     edx, 0A0Bh; void *
0x180003e19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e1f  mov     rcx, [rbp+188h]; this
0x180003e26  mov     edx, 0A15h; void *
0x180003e2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e31  mov     rcx, [rbp+188h]; this
0x180003e38  mov     edx, 0A0Bh; void *
0x180003e3d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e43  mov     rcx, [rbp+188h]; this
0x180003e4a  mov     edx, 0A15h; void *
0x180003e4f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
