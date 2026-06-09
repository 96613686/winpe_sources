# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14001c61c`
- end: `0x14001c9ba`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14001d4ac`

## callees

- `0x140003e50`
- `0x140004a78`
- `0x14001c61c`
- `0x14001c9c0`
- `0x14001cbf0`
- `0x14001d244`
- `0x14001dd18`
- `0x14001dff4`
- `0x14001e9f4`
- `0x14001eaac`
- `0x14001ee5c`
- `0x14001ee6c`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14001c655`
- `KERNEL32!GetCurrentProcessId` at `0x14001c655`
- `KERNEL32!CloseHandle` at `0x14001c747`
- `KERNEL32!CloseHandle` at `0x14001c809`
- `KERNEL32!CloseHandle` at `0x14001c821`
- `KERNEL32!CloseHandle` at `0x14001c870`
- `KERNEL32!CloseHandle` at `0x14001c8e5`
- `KERNEL32!CloseHandle` at `0x14001c747`
- `KERNEL32!CloseHandle` at `0x14001c809`
- `KERNEL32!CloseHandle` at `0x14001c821`
- `KERNEL32!CloseHandle` at `0x14001c870`
- `KERNEL32!CloseHandle` at `0x14001c8e5`
- `KERNEL32!GetProcessHeap` at `0x14001c82f`
- `KERNEL32!GetProcessHeap` at `0x14001c82f`
- `KERNEL32!CreateMutexExW` at `0x14001c694`
- `KERNEL32!CreateMutexExW` at `0x14001c694`
- `KERNEL32!WaitForSingleObjectEx` at `0x14001c6b5`
- `KERNEL32!WaitForSingleObjectEx` at `0x14001c6b5`
- `KERNEL32!ReleaseMutex` at `0x14001c736`
- `KERNEL32!ReleaseMutex` at `0x14001c85f`
- `KERNEL32!ReleaseMutex` at `0x14001c8cf`
- `KERNEL32!ReleaseMutex` at `0x14001c736`
- `KERNEL32!ReleaseMutex` at `0x14001c85f`
- `KERNEL32!ReleaseMutex` at `0x14001c8cf`
- `KERNEL32!HeapFree` at `0x14001c83d`
- `KERNEL32!HeapFree` at `0x14001c83d`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
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
0x14001c61c  mov     [rsp-8+arg_10], rbx
0x14001c621  push    rbp
0x14001c622  push    rsi
0x14001c623  push    rdi
0x14001c624  push    r14
0x14001c626  push    r15
0x14001c628  lea     rbp, [rsp-160h]
0x14001c630  sub     rsp, 260h
0x14001c637  mov     rax, cs:__security_cookie
0x14001c63e  xor     rax, rsp
0x14001c641  mov     [rbp+180h+var_30], rax
0x14001c648  mov     r15, rdx
0x14001c64b  mov     qword ptr [rdx], 0
0x14001c652  mov     rbx, rcx
0x14001c655  call    cs:__imp_GetCurrentProcessId
0x14001c65b  mov     r14d, 78h ; 'x'
0x14001c661  mov     [rsp+280h+var_258], rbx
0x14001c666  mov     r9d, eax
0x14001c669  mov     [rsp+280h+var_260], r14d; int
0x14001c66e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14001c675  mov     edx, 104h; unsigned __int64
0x14001c67a  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14001c67f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14001c684  mov     r9d, 1F0001h; dwDesiredAccess
0x14001c68a  lea     rdx, [rsp+280h+Name]; lpName
0x14001c68f  xor     r8d, r8d; dwFlags
0x14001c692  xor     ecx, ecx; lpMutexAttributes
0x14001c694  call    cs:__imp_CreateMutexExW
0x14001c69a  mov     rbx, rax
0x14001c69d  test    rax, rax
0x14001c6a0  jnz     short loc_14001C6AC
0x14001c6a2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14001c6a7  jmp     loc_14001C8F1
0x14001c6ac  xor     r8d, r8d; bAlertable
0x14001c6af  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001c6b2  mov     rcx, rbx; hHandle
0x14001c6b5  call    cs:__imp_WaitForSingleObjectEx
0x14001c6bb  cmp     eax, 102h
0x14001c6c0  jz      short loc_14001C6D2
0x14001c6c2  test    eax, 0FFFFFF7Fh
0x14001c6c7  jnz     loc_14001C929
0x14001c6cd  mov     rdi, rbx
0x14001c6d0  jmp     short loc_14001C6D4
0x14001c6d2  xor     edi, edi
0x14001c6d4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14001c6d9  mov     [rsp+280h+hObject], 0
0x14001c6e2  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14001c6e7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x14001c6ec  mov     esi, eax
0x14001c6ee  test    eax, eax
0x14001c6f0  jns     short loc_14001C75C
0x14001c6f2  mov     rcx, [rbp+188h]; this
0x14001c6f9  mov     r9d, eax; char *
0x14001c6fc  mov     edx, 66h ; 'f'; void *
0x14001c701  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c706  mov     rcx, [rbp+188h]; this
0x14001c70d  mov     r9d, esi; char *
0x14001c710  mov     edx, 6Fh ; 'o'; void *
0x14001c715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c71a  mov     rcx, [rbp+188h]; this
0x14001c721  mov     r9d, esi; char *
0x14001c724  mov     edx, 12Eh; void *
0x14001c729  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c72e  test    rdi, rdi
0x14001c731  jz      short loc_14001C744
0x14001c733  mov     rcx, rdi; hMutex
0x14001c736  call    cs:__imp_ReleaseMutex
0x14001c73c  test    eax, eax
0x14001c73e  jz      loc_14001C936
0x14001c744  mov     rcx, rbx; hObject
0x14001c747  call    cs:__imp_CloseHandle
0x14001c74d  test    eax, eax
0x14001c74f  jz      loc_14001C948
0x14001c755  mov     eax, esi
0x14001c757  jmp     loc_14001C8F1
0x14001c75c  mov     rax, [rsp+280h+hObject]
0x14001c761  lea     rcx, ds:0[rax*4]
0x14001c769  test    rcx, rcx
0x14001c76c  jz      short loc_14001C77C
0x14001c76e  mov     [r15], rcx
0x14001c771  mov     eax, [rcx]
0x14001c773  inc     eax
0x14001c775  mov     [rcx], eax
0x14001c777  jmp     loc_14001C8C7
0x14001c77c  mov     rdx, r14; dwBytes
0x14001c77f  mov     qword ptr [r15], 0
0x14001c786  mov     ecx, 8; dwFlags
0x14001c78b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001c790  mov     rsi, rax
0x14001c793  test    rax, rax
0x14001c796  jnz     short loc_14001C7B7
0x14001c798  mov     rcx, [rbp+188h]; this
0x14001c79f  mov     r14d, 8007000Eh
0x14001c7a5  mov     r9d, r14d; char *
0x14001c7a8  mov     edx, 14Bh; void *
0x14001c7ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c7b2  jmp     loc_14001C843
0x14001c7b7  xorps   xmm0, xmm0
0x14001c7ba  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14001c7c0  test    sil, 3
0x14001c7c4  jnz     loc_14001C95A
0x14001c7ca  mov     r9, rsi
0x14001c7cd  lea     rdx, [rsp+280h+Name]; wchar_t *
0x14001c7d2  shr     r9, 2; unsigned __int64
0x14001c7d6  lea     rcx, [rsp+280h+hObject]; this
0x14001c7db  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x14001c7e0  mov     r14d, eax
0x14001c7e3  test    eax, eax
0x14001c7e5  jns     loc_14001C883
0x14001c7eb  mov     rcx, [rbp+188h]; this
0x14001c7f2  mov     r9d, eax; char *
0x14001c7f5  mov     edx, 14Eh; void *
0x14001c7fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c7ff  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14001c804  test    rcx, rcx
0x14001c807  jz      short loc_14001C817
0x14001c809  call    cs:__imp_CloseHandle
0x14001c80f  test    eax, eax
0x14001c811  jz      loc_14001C960
0x14001c817  mov     rcx, [rsp+280h+hObject]; hObject
0x14001c81c  test    rcx, rcx
0x14001c81f  jz      short loc_14001C82F
0x14001c821  call    cs:__imp_CloseHandle
0x14001c827  test    eax, eax
0x14001c829  jz      loc_14001C972
0x14001c82f  call    cs:__imp_GetProcessHeap
0x14001c835  mov     r8, rsi; lpMem
0x14001c838  xor     edx, edx; dwFlags
0x14001c83a  mov     rcx, rax; hHeap
0x14001c83d  call    cs:__imp_HeapFree
0x14001c843  mov     rcx, [rbp+188h]; this
0x14001c84a  mov     r9d, r14d; char *
0x14001c84d  mov     edx, 137h; void *
0x14001c852  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c857  test    rdi, rdi
0x14001c85a  jz      short loc_14001C86D
0x14001c85c  mov     rcx, rdi; hMutex
0x14001c85f  call    cs:__imp_ReleaseMutex
0x14001c865  test    eax, eax
0x14001c867  jz      loc_14001C984
0x14001c86d  mov     rcx, rbx; hObject
0x14001c870  call    cs:__imp_CloseHandle
0x14001c876  test    eax, eax
0x14001c878  jz      loc_14001C996
0x14001c87e  mov     eax, r14d
0x14001c881  jmp     short loc_14001C8F1
0x14001c883  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14001c888  xor     edx, edx; Val
0x14001c88a  mov     dword ptr [rsi], 1
0x14001c890  lea     rcx, [rsi+22h]; void *
0x14001c894  mov     [rsi+8], rbx
0x14001c898  movdqu  xmmword ptr [rsi+10h], xmm0
0x14001c89d  lea     r8d, [rdx+56h]; Size
0x14001c8a1  call    memset_0
0x14001c8a6  xor     edx, edx; Val
0x14001c8a8  mov     word ptr [rsi+20h], 58h ; 'X'
0x14001c8ae  lea     rcx, [rsi+28h]; void *
0x14001c8b2  mov     dword ptr [rsi+24h], 1
0x14001c8b9  lea     r8d, [rdx+50h]; Size
0x14001c8bd  call    memset_0
0x14001c8c2  xor     ebx, ebx
0x14001c8c4  mov     [r15], rsi
0x14001c8c7  test    rdi, rdi
0x14001c8ca  jz      short loc_14001C8DD
0x14001c8cc  mov     rcx, rdi; hMutex
0x14001c8cf  call    cs:__imp_ReleaseMutex
0x14001c8d5  test    eax, eax
0x14001c8d7  jz      loc_14001C9A8
0x14001c8dd  test    rbx, rbx
0x14001c8e0  jz      short loc_14001C8EF
0x14001c8e2  mov     rcx, rbx; hObject
0x14001c8e5  call    cs:__imp_CloseHandle
0x14001c8eb  test    eax, eax
0x14001c8ed  jz      short loc_14001C917
0x14001c8ef  xor     eax, eax
0x14001c8f1  mov     rcx, [rbp+180h+var_30]
0x14001c8f8  xor     rcx, rsp; StackCookie
0x14001c8fb  call    __security_check_cookie
0x14001c900  mov     rbx, [rsp+280h+arg_10]
0x14001c908  add     rsp, 260h
0x14001c90f  pop     r15
0x14001c911  pop     r14
0x14001c913  pop     rdi
0x14001c914  pop     rsi
0x14001c915  pop     rbp
0x14001c916  retn
0x14001c917  mov     rcx, [rbp+188h]; this
0x14001c91e  mov     edx, 0A0Bh; void *
0x14001c923  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001c929  mov     rcx, [rbp+188h]; this
0x14001c930  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14001c936  mov     rcx, [rbp+188h]; this
0x14001c93d  mov     edx, 0A15h; void *
0x14001c942  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001c948  mov     rcx, [rbp+188h]; this
0x14001c94f  mov     edx, 0A0Bh; void *
0x14001c954  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001c95a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14001c960  mov     rcx, [rbp+188h]; this
0x14001c967  mov     edx, 0A0Bh; void *
0x14001c96c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001c972  mov     rcx, [rbp+188h]; this
0x14001c979  mov     edx, 0A0Bh; void *
0x14001c97e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001c984  mov     rcx, [rbp+188h]; this
0x14001c98b  mov     edx, 0A15h; void *
0x14001c990  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001c996  mov     rcx, [rbp+188h]; this
0x14001c99d  mov     edx, 0A0Bh; void *
0x14001c9a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001c9a8  mov     rcx, [rbp+188h]; this
0x14001c9af  mov     edx, 0A15h; void *
0x14001c9b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
