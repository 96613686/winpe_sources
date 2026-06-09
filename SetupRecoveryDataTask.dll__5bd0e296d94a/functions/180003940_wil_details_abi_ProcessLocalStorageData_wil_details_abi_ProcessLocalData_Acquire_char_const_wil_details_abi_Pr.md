# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003940`
- end: `0x180003cde`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005b70`

## callees

- `0x180003940`
- `0x180004140`
- `0x180004c98`
- `0x180005908`
- `0x180006ffc`
- `0x180008a34`
- `0x180009480`
- `0x1800098dc`
- `0x18000ab0c`
- `0x18000ab1c`
- `0x18000c5e2`
- `0x18000c610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bf3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800039b8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800039b8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800039d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800039d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003979`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003979`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c09`

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
0x180003940  mov     [rsp-8+arg_10], rbx
0x180003945  push    rbp
0x180003946  push    rsi
0x180003947  push    rdi
0x180003948  push    r14
0x18000394a  push    r15
0x18000394c  lea     rbp, [rsp-160h]
0x180003954  sub     rsp, 260h
0x18000395b  mov     rax, cs:__security_cookie
0x180003962  xor     rax, rsp
0x180003965  mov     [rbp+180h+var_30], rax
0x18000396c  mov     r15, rdx
0x18000396f  mov     qword ptr [rdx], 0
0x180003976  mov     rbx, rcx
0x180003979  call    cs:__imp_GetCurrentProcessId
0x18000397f  mov     r14d, 78h ; 'x'
0x180003985  mov     [rsp+280h+var_258], rbx
0x18000398a  mov     r9d, eax
0x18000398d  mov     [rsp+280h+var_260], r14d; int
0x180003992  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003999  mov     edx, 104h; unsigned __int64
0x18000399e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800039a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800039a8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800039ae  lea     rdx, [rsp+280h+Name]; lpName
0x1800039b3  xor     r8d, r8d; dwFlags
0x1800039b6  xor     ecx, ecx; lpMutexAttributes
0x1800039b8  call    cs:__imp_CreateMutexExW
0x1800039be  mov     rbx, rax
0x1800039c1  test    rax, rax
0x1800039c4  jnz     short loc_1800039D0
0x1800039c6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800039cb  jmp     loc_180003C15
0x1800039d0  xor     r8d, r8d; bAlertable
0x1800039d3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800039d6  mov     rcx, rbx; hHandle
0x1800039d9  call    cs:__imp_WaitForSingleObjectEx
0x1800039df  cmp     eax, 102h
0x1800039e4  jz      short loc_1800039F6
0x1800039e6  test    eax, 0FFFFFF7Fh
0x1800039eb  jnz     loc_180003C4D
0x1800039f1  mov     rdi, rbx
0x1800039f4  jmp     short loc_1800039F8
0x1800039f6  xor     edi, edi
0x1800039f8  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800039fd  mov     [rsp+280h+hObject], 0
0x180003a06  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003a0b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003a10  mov     esi, eax
0x180003a12  test    eax, eax
0x180003a14  jns     short loc_180003A80
0x180003a16  mov     rcx, [rbp+188h]; this
0x180003a1d  mov     r9d, eax; char *
0x180003a20  mov     edx, 66h ; 'f'; void *
0x180003a25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a2a  mov     rcx, [rbp+188h]; this
0x180003a31  mov     r9d, esi; char *
0x180003a34  mov     edx, 6Fh ; 'o'; void *
0x180003a39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a3e  mov     rcx, [rbp+188h]; this
0x180003a45  mov     r9d, esi; char *
0x180003a48  mov     edx, 12Eh; void *
0x180003a4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a52  test    rdi, rdi
0x180003a55  jz      short loc_180003A68
0x180003a57  mov     rcx, rdi; hMutex
0x180003a5a  call    cs:__imp_ReleaseMutex
0x180003a60  test    eax, eax
0x180003a62  jz      loc_180003C5A
0x180003a68  mov     rcx, rbx; hObject
0x180003a6b  call    cs:__imp_CloseHandle
0x180003a71  test    eax, eax
0x180003a73  jz      loc_180003C6C
0x180003a79  mov     eax, esi
0x180003a7b  jmp     loc_180003C15
0x180003a80  mov     rax, [rsp+280h+hObject]
0x180003a85  lea     rcx, ds:0[rax*4]
0x180003a8d  test    rcx, rcx
0x180003a90  jz      short loc_180003AA0
0x180003a92  mov     [r15], rcx
0x180003a95  mov     eax, [rcx]
0x180003a97  inc     eax
0x180003a99  mov     [rcx], eax
0x180003a9b  jmp     loc_180003BEB
0x180003aa0  mov     rdx, r14; dwBytes
0x180003aa3  mov     qword ptr [r15], 0
0x180003aaa  mov     ecx, 8; dwFlags
0x180003aaf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003ab4  mov     rsi, rax
0x180003ab7  test    rax, rax
0x180003aba  jnz     short loc_180003ADB
0x180003abc  mov     rcx, [rbp+188h]; this
0x180003ac3  mov     r14d, 8007000Eh
0x180003ac9  mov     r9d, r14d; char *
0x180003acc  mov     edx, 14Bh; void *
0x180003ad1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ad6  jmp     loc_180003B67
0x180003adb  xorps   xmm0, xmm0
0x180003ade  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003ae4  test    sil, 3
0x180003ae8  jnz     loc_180003C7E
0x180003aee  mov     r9, rsi
0x180003af1  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003af6  shr     r9, 2; unsigned __int64
0x180003afa  lea     rcx, [rsp+280h+hObject]; this
0x180003aff  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003b04  mov     r14d, eax
0x180003b07  test    eax, eax
0x180003b09  jns     loc_180003BA7
0x180003b0f  mov     rcx, [rbp+188h]; this
0x180003b16  mov     r9d, eax; char *
0x180003b19  mov     edx, 14Eh; void *
0x180003b1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b23  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003b28  test    rcx, rcx
0x180003b2b  jz      short loc_180003B3B
0x180003b2d  call    cs:__imp_CloseHandle
0x180003b33  test    eax, eax
0x180003b35  jz      loc_180003C84
0x180003b3b  mov     rcx, [rsp+280h+hObject]; hObject
0x180003b40  test    rcx, rcx
0x180003b43  jz      short loc_180003B53
0x180003b45  call    cs:__imp_CloseHandle
0x180003b4b  test    eax, eax
0x180003b4d  jz      loc_180003C96
0x180003b53  call    cs:__imp_GetProcessHeap
0x180003b59  mov     r8, rsi; lpMem
0x180003b5c  xor     edx, edx; dwFlags
0x180003b5e  mov     rcx, rax; hHeap
0x180003b61  call    cs:__imp_HeapFree
0x180003b67  mov     rcx, [rbp+188h]; this
0x180003b6e  mov     r9d, r14d; char *
0x180003b71  mov     edx, 137h; void *
0x180003b76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b7b  test    rdi, rdi
0x180003b7e  jz      short loc_180003B91
0x180003b80  mov     rcx, rdi; hMutex
0x180003b83  call    cs:__imp_ReleaseMutex
0x180003b89  test    eax, eax
0x180003b8b  jz      loc_180003CA8
0x180003b91  mov     rcx, rbx; hObject
0x180003b94  call    cs:__imp_CloseHandle
0x180003b9a  test    eax, eax
0x180003b9c  jz      loc_180003CBA
0x180003ba2  mov     eax, r14d
0x180003ba5  jmp     short loc_180003C15
0x180003ba7  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003bac  xor     edx, edx; Val
0x180003bae  mov     dword ptr [rsi], 1
0x180003bb4  lea     rcx, [rsi+22h]; void *
0x180003bb8  mov     [rsi+8], rbx
0x180003bbc  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003bc1  lea     r8d, [rdx+56h]; Size
0x180003bc5  call    memset_0
0x180003bca  xor     edx, edx; Val
0x180003bcc  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003bd2  lea     rcx, [rsi+28h]; void *
0x180003bd6  mov     dword ptr [rsi+24h], 1
0x180003bdd  lea     r8d, [rdx+50h]; Size
0x180003be1  call    memset_0
0x180003be6  xor     ebx, ebx
0x180003be8  mov     [r15], rsi
0x180003beb  test    rdi, rdi
0x180003bee  jz      short loc_180003C01
0x180003bf0  mov     rcx, rdi; hMutex
0x180003bf3  call    cs:__imp_ReleaseMutex
0x180003bf9  test    eax, eax
0x180003bfb  jz      loc_180003CCC
0x180003c01  test    rbx, rbx
0x180003c04  jz      short loc_180003C13
0x180003c06  mov     rcx, rbx; hObject
0x180003c09  call    cs:__imp_CloseHandle
0x180003c0f  test    eax, eax
0x180003c11  jz      short loc_180003C3B
0x180003c13  xor     eax, eax
0x180003c15  mov     rcx, [rbp+180h+var_30]
0x180003c1c  xor     rcx, rsp; StackCookie
0x180003c1f  call    __security_check_cookie
0x180003c24  mov     rbx, [rsp+280h+arg_10]
0x180003c2c  add     rsp, 260h
0x180003c33  pop     r15
0x180003c35  pop     r14
0x180003c37  pop     rdi
0x180003c38  pop     rsi
0x180003c39  pop     rbp
0x180003c3a  retn
0x180003c3b  mov     rcx, [rbp+188h]; this
0x180003c42  mov     edx, 0A0Bh; void *
0x180003c47  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c4d  mov     rcx, [rbp+188h]; this
0x180003c54  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003c5a  mov     rcx, [rbp+188h]; this
0x180003c61  mov     edx, 0A15h; void *
0x180003c66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c6c  mov     rcx, [rbp+188h]; this
0x180003c73  mov     edx, 0A0Bh; void *
0x180003c78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c7e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003c84  mov     rcx, [rbp+188h]; this
0x180003c8b  mov     edx, 0A0Bh; void *
0x180003c90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c96  mov     rcx, [rbp+188h]; this
0x180003c9d  mov     edx, 0A0Bh; void *
0x180003ca2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ca8  mov     rcx, [rbp+188h]; this
0x180003caf  mov     edx, 0A15h; void *
0x180003cb4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003cba  mov     rcx, [rbp+188h]; this
0x180003cc1  mov     edx, 0A0Bh; void *
0x180003cc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ccc  mov     rcx, [rbp+188h]; this
0x180003cd3  mov     edx, 0A15h; void *
0x180003cd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
