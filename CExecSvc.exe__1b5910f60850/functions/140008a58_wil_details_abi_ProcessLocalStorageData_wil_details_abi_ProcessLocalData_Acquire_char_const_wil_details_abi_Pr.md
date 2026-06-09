# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140008a58`
- end: `0x140008e02`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `938`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140009d20`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x140008a58`
- `0x140009108`
- `0x140009490`
- `0x140009b40`
- `0x14000ba08`
- `0x14000bf34`
- `0x14000d17c`
- `0x14000d358`
- `0x14000e394`
- `0x14000e3a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008b72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008c9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008d0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008b72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008c9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008d0b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140008af1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140008af1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140008ad0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140008ad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008c6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008c6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008a91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008a91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008cac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008d21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008cac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008d21`

## string_xrefs

- `0x140008d6c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int v16; // r8d
  __int64 v17; // r8
  const char *v18; // r9
  __int64 v19; // r8
  const char *v20; // r9
  _DWORD *v21; // rcx
  unsigned __int64 v22; // rax
  wil::details::in1diag3 *v23; // rcx
  unsigned int v24; // r8d
  _QWORD *v25; // rsi
  unsigned int v26; // r14d
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)v14, v45);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
    return v14;
  }
  v21 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v21;
    ++*v21;
    goto LABEL_28;
  }
  *a2 = 0;
  v22 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v25 = (_QWORD *)v22;
  if ( v22 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v22 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v24,
            v22 >> 2);
    v26 = v28;
    if ( v28 >= 0 )
    {
      v39 = *(_OWORD *)hObject;
      *(_DWORD *)v25 = 1;
      v25[1] = v6;
      *((_OWORD *)v25 + 1) = v39;
      memset_0((char *)v25 + 34, 0, 0x56u);
      *((_WORD *)v25 + 16) = 88;
      *((_DWORD *)v25 + 9) = 1;
      memset_0(v25 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v25;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
  }
  else
  {
    v26 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v26, v46);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return v26;
}

```

## disassembly

```asm
0x140008a58  mov     [rsp-8+arg_10], rbx
0x140008a5d  push    rbp
0x140008a5e  push    rsi
0x140008a5f  push    rdi
0x140008a60  push    r14
0x140008a62  push    r15
0x140008a64  lea     rbp, [rsp-160h]
0x140008a6c  sub     rsp, 260h
0x140008a73  mov     rax, cs:__security_cookie
0x140008a7a  xor     rax, rsp
0x140008a7d  mov     [rbp+180h+var_30], rax
0x140008a84  mov     r15, rdx
0x140008a87  mov     qword ptr [rdx], 0
0x140008a8e  mov     rbx, rcx
0x140008a91  call    cs:__imp_GetCurrentProcessId
0x140008a97  mov     r14d, 78h ; 'x'
0x140008a9d  mov     [rsp+280h+var_258], rbx
0x140008aa2  mov     r9d, eax
0x140008aa5  mov     [rsp+280h+var_260], r14d; int
0x140008aaa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140008ab1  mov     edx, 104h; unsigned __int64
0x140008ab6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008abb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008ac0  mov     r9d, 1F0001h; dwDesiredAccess
0x140008ac6  lea     rdx, [rsp+280h+Name]; lpName
0x140008acb  xor     r8d, r8d; dwFlags
0x140008ace  xor     ecx, ecx; lpMutexAttributes
0x140008ad0  call    cs:__imp_CreateMutexExW
0x140008ad6  mov     rbx, rax
0x140008ad9  test    rax, rax
0x140008adc  jnz     short loc_140008AE8
0x140008ade  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140008ae3  jmp     loc_140008D2D
0x140008ae8  xor     r8d, r8d; bAlertable
0x140008aeb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140008aee  mov     rcx, rbx; hHandle
0x140008af1  call    cs:__imp_WaitForSingleObjectEx
0x140008af7  cmp     eax, 102h
0x140008afc  jz      short loc_140008B0E
0x140008afe  test    eax, 0FFFFFF7Fh
0x140008b03  jnz     loc_140008D65
0x140008b09  mov     rdi, rbx
0x140008b0c  jmp     short loc_140008B10
0x140008b0e  xor     edi, edi
0x140008b10  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140008b15  mov     [rsp+280h+hObject], 0
0x140008b1e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008b23  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140008b28  mov     esi, eax
0x140008b2a  test    eax, eax
0x140008b2c  jns     short loc_140008B98
0x140008b2e  mov     rcx, [rbp+188h]; this
0x140008b35  mov     r9d, eax; char *
0x140008b38  mov     edx, 66h ; 'f'; void *
0x140008b3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008b42  mov     rcx, [rbp+188h]; this
0x140008b49  mov     r9d, esi; char *
0x140008b4c  mov     edx, 6Fh ; 'o'; void *
0x140008b51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008b56  mov     rcx, [rbp+188h]; this
0x140008b5d  mov     r9d, esi; char *
0x140008b60  mov     edx, 12Eh; void *
0x140008b65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008b6a  test    rdi, rdi
0x140008b6d  jz      short loc_140008B80
0x140008b6f  mov     rcx, rdi; hMutex
0x140008b72  call    cs:__imp_ReleaseMutex
0x140008b78  test    eax, eax
0x140008b7a  jz      loc_140008D7E
0x140008b80  mov     rcx, rbx; hObject
0x140008b83  call    cs:__imp_CloseHandle
0x140008b89  test    eax, eax
0x140008b8b  jz      loc_140008D90
0x140008b91  mov     eax, esi
0x140008b93  jmp     loc_140008D2D
0x140008b98  mov     rax, [rsp+280h+hObject]
0x140008b9d  lea     rcx, ds:0[rax*4]
0x140008ba5  test    rcx, rcx
0x140008ba8  jz      short loc_140008BB8
0x140008baa  mov     [r15], rcx
0x140008bad  mov     eax, [rcx]
0x140008baf  inc     eax
0x140008bb1  mov     [rcx], eax
0x140008bb3  jmp     loc_140008D03
0x140008bb8  mov     rdx, r14; dwBytes
0x140008bbb  mov     qword ptr [r15], 0
0x140008bc2  mov     ecx, 8; dwFlags
0x140008bc7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008bcc  mov     rsi, rax
0x140008bcf  test    rax, rax
0x140008bd2  jnz     short loc_140008BF3
0x140008bd4  mov     rcx, [rbp+188h]; this
0x140008bdb  mov     r14d, 8007000Eh
0x140008be1  mov     r9d, r14d; char *
0x140008be4  mov     edx, 14Bh; void *
0x140008be9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008bee  jmp     loc_140008C7F
0x140008bf3  xorps   xmm0, xmm0
0x140008bf6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140008bfc  test    sil, 3
0x140008c00  jnz     loc_140008DA2
0x140008c06  mov     r9, rsi
0x140008c09  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140008c0e  shr     r9, 2; unsigned __int64
0x140008c12  lea     rcx, [rsp+280h+hObject]; this
0x140008c17  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140008c1c  mov     r14d, eax
0x140008c1f  test    eax, eax
0x140008c21  jns     loc_140008CBF
0x140008c27  mov     rcx, [rbp+188h]; this
0x140008c2e  mov     r9d, eax; char *
0x140008c31  mov     edx, 14Eh; void *
0x140008c36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008c3b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140008c40  test    rcx, rcx
0x140008c43  jz      short loc_140008C53
0x140008c45  call    cs:__imp_CloseHandle
0x140008c4b  test    eax, eax
0x140008c4d  jz      loc_140008DA8
0x140008c53  mov     rcx, [rsp+280h+hObject]; hObject
0x140008c58  test    rcx, rcx
0x140008c5b  jz      short loc_140008C6B
0x140008c5d  call    cs:__imp_CloseHandle
0x140008c63  test    eax, eax
0x140008c65  jz      loc_140008DBA
0x140008c6b  call    cs:__imp_GetProcessHeap
0x140008c71  mov     r8, rsi; lpMem
0x140008c74  xor     edx, edx; dwFlags
0x140008c76  mov     rcx, rax; hHeap
0x140008c79  call    cs:__imp_HeapFree
0x140008c7f  mov     rcx, [rbp+188h]; this
0x140008c86  mov     r9d, r14d; char *
0x140008c89  mov     edx, 137h; void *
0x140008c8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008c93  test    rdi, rdi
0x140008c96  jz      short loc_140008CA9
0x140008c98  mov     rcx, rdi; hMutex
0x140008c9b  call    cs:__imp_ReleaseMutex
0x140008ca1  test    eax, eax
0x140008ca3  jz      loc_140008DCC
0x140008ca9  mov     rcx, rbx; hObject
0x140008cac  call    cs:__imp_CloseHandle
0x140008cb2  test    eax, eax
0x140008cb4  jz      loc_140008DDE
0x140008cba  mov     eax, r14d
0x140008cbd  jmp     short loc_140008D2D
0x140008cbf  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140008cc4  xor     edx, edx; Val
0x140008cc6  mov     dword ptr [rsi], 1
0x140008ccc  lea     rcx, [rsi+22h]; void *
0x140008cd0  mov     [rsi+8], rbx
0x140008cd4  movdqu  xmmword ptr [rsi+10h], xmm0
0x140008cd9  lea     r8d, [rdx+56h]; Size
0x140008cdd  call    memset_0
0x140008ce2  xor     edx, edx; Val
0x140008ce4  mov     word ptr [rsi+20h], 58h ; 'X'
0x140008cea  lea     rcx, [rsi+28h]; void *
0x140008cee  mov     dword ptr [rsi+24h], 1
0x140008cf5  lea     r8d, [rdx+50h]; Size
0x140008cf9  call    memset_0
0x140008cfe  xor     ebx, ebx
0x140008d00  mov     [r15], rsi
0x140008d03  test    rdi, rdi
0x140008d06  jz      short loc_140008D19
0x140008d08  mov     rcx, rdi; hMutex
0x140008d0b  call    cs:__imp_ReleaseMutex
0x140008d11  test    eax, eax
0x140008d13  jz      loc_140008DF0
0x140008d19  test    rbx, rbx
0x140008d1c  jz      short loc_140008D2B
0x140008d1e  mov     rcx, rbx; hObject
0x140008d21  call    cs:__imp_CloseHandle
0x140008d27  test    eax, eax
0x140008d29  jz      short loc_140008D53
0x140008d2b  xor     eax, eax
0x140008d2d  mov     rcx, [rbp+180h+var_30]
0x140008d34  xor     rcx, rsp; StackCookie
0x140008d37  call    __security_check_cookie
0x140008d3c  mov     rbx, [rsp+280h+arg_10]
0x140008d44  add     rsp, 260h
0x140008d4b  pop     r15
0x140008d4d  pop     r14
0x140008d4f  pop     rdi
0x140008d50  pop     rsi
0x140008d51  pop     rbp
0x140008d52  retn
0x140008d53  mov     rcx, [rbp+188h]; this
0x140008d5a  mov     edx, 0A0Bh; void *
0x140008d5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008d65  mov     rcx, [rbp+188h]; this
0x140008d6c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140008d73  mov     edx, 0E01h; void *
0x140008d78  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140008d7e  mov     rcx, [rbp+188h]; this
0x140008d85  mov     edx, 0A15h; void *
0x140008d8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008d90  mov     rcx, [rbp+188h]; this
0x140008d97  mov     edx, 0A0Bh; void *
0x140008d9c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008da2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140008da8  mov     rcx, [rbp+188h]; this
0x140008daf  mov     edx, 0A0Bh; void *
0x140008db4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008dba  mov     rcx, [rbp+188h]; this
0x140008dc1  mov     edx, 0A0Bh; void *
0x140008dc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008dcc  mov     rcx, [rbp+188h]; this
0x140008dd3  mov     edx, 0A15h; void *
0x140008dd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008dde  mov     rcx, [rbp+188h]; this
0x140008de5  mov     edx, 0A0Bh; void *
0x140008dea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008df0  mov     rcx, [rbp+188h]; this
0x140008df7  mov     edx, 0A15h; void *
0x140008dfc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
