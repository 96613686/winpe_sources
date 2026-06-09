# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004a28`
- end: `0x180004df0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006310`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x180004a28`
- `0x1800051f0`
- `0x180005748`
- `0x1800060a0`
- `0x180006db4`
- `0x1800085bc`
- `0x18000940c`
- `0x180009ccc`
- `0x180009cdc`
- `0x18000a654`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180004c5e`
- `KERNEL32!GetProcessHeap` at `0x180004c5e`
- `KERNEL32!GetCurrentProcessId` at `0x180004a61`
- `KERNEL32!GetCurrentProcessId` at `0x180004a61`
- `KERNEL32!CreateMutexExW` at `0x180004aa0`
- `KERNEL32!CreateMutexExW` at `0x180004aa0`
- `KERNEL32!CloseHandle` at `0x180004b68`
- `KERNEL32!CloseHandle` at `0x180004c38`
- `KERNEL32!CloseHandle` at `0x180004c50`
- `KERNEL32!CloseHandle` at `0x180004ca6`
- `KERNEL32!CloseHandle` at `0x180004d1b`
- `KERNEL32!CloseHandle` at `0x180004b68`
- `KERNEL32!CloseHandle` at `0x180004c38`
- `KERNEL32!CloseHandle` at `0x180004c50`
- `KERNEL32!CloseHandle` at `0x180004ca6`
- `KERNEL32!CloseHandle` at `0x180004d1b`
- `KERNEL32!WaitForSingleObjectEx` at `0x180004ac1`
- `KERNEL32!WaitForSingleObjectEx` at `0x180004ac1`
- `KERNEL32!ReleaseMutex` at `0x180004b57`
- `KERNEL32!ReleaseMutex` at `0x180004c95`
- `KERNEL32!ReleaseMutex` at `0x180004d05`
- `KERNEL32!ReleaseMutex` at `0x180004b57`
- `KERNEL32!ReleaseMutex` at `0x180004c95`
- `KERNEL32!ReleaseMutex` at `0x180004d05`
- `KERNEL32!HeapFree` at `0x180004c6c`
- `KERNEL32!HeapFree` at `0x180004c6c`

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
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
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
                    pszDest,
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
            pszDest,
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
0x180004a28  mov     [rsp-8+arg_10], rbx
0x180004a2d  push    rbp
0x180004a2e  push    rsi
0x180004a2f  push    rdi
0x180004a30  push    r14
0x180004a32  push    r15
0x180004a34  lea     rbp, [rsp-160h]
0x180004a3c  sub     rsp, 260h
0x180004a43  mov     rax, cs:__security_cookie
0x180004a4a  xor     rax, rsp
0x180004a4d  mov     [rbp+180h+var_30], rax
0x180004a54  mov     r15, rdx
0x180004a57  mov     qword ptr [rdx], 0
0x180004a5e  mov     rbx, rcx
0x180004a61  call    cs:__imp_GetCurrentProcessId
0x180004a67  mov     r14d, 78h ; 'x'
0x180004a6d  mov     [rsp+280h+var_258], rbx
0x180004a72  mov     r9d, eax
0x180004a75  mov     [rsp+280h+var_260], r14d; int
0x180004a7a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004a81  mov     edx, 104h; cchDest
0x180004a86  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180004a8b  call    StringCchPrintfW
0x180004a90  mov     r9d, 1F0001h; dwDesiredAccess
0x180004a96  lea     rdx, [rsp+280h+pszDest]; lpName
0x180004a9b  xor     r8d, r8d; dwFlags
0x180004a9e  xor     ecx, ecx; lpMutexAttributes
0x180004aa0  call    cs:__imp_CreateMutexExW
0x180004aa6  mov     rbx, rax
0x180004aa9  test    rax, rax
0x180004aac  jnz     short loc_180004AB8
0x180004aae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004ab3  jmp     loc_180004D27
0x180004ab8  xor     r8d, r8d; bAlertable
0x180004abb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004abe  mov     rcx, rbx; hHandle
0x180004ac1  call    cs:__imp_WaitForSingleObjectEx
0x180004ac7  cmp     eax, 102h
0x180004acc  jz      short loc_180004ADE
0x180004ace  test    eax, 0FFFFFF7Fh
0x180004ad3  jnz     loc_180004D5F
0x180004ad9  mov     rdi, rbx
0x180004adc  jmp     short loc_180004AE0
0x180004ade  xor     edi, edi
0x180004ae0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004ae5  mov     [rsp+280h+hObject], 0
0x180004aee  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180004af3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004af8  mov     esi, eax
0x180004afa  test    eax, eax
0x180004afc  jns     short loc_180004B7D
0x180004afe  mov     rcx, [rbp+188h]; this
0x180004b05  lea     r8, aWil; "wil"
0x180004b0c  mov     r9d, eax; char *
0x180004b0f  mov     edx, 66h ; 'f'; void *
0x180004b14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b19  mov     rcx, [rbp+188h]; this
0x180004b20  lea     r8, aWil; "wil"
0x180004b27  mov     r9d, esi; char *
0x180004b2a  mov     edx, 6Fh ; 'o'; void *
0x180004b2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b34  mov     rcx, [rbp+188h]; this
0x180004b3b  lea     r8, aWil; "wil"
0x180004b42  mov     r9d, esi; char *
0x180004b45  mov     edx, 12Eh; void *
0x180004b4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b4f  test    rdi, rdi
0x180004b52  jz      short loc_180004B65
0x180004b54  mov     rcx, rdi; hMutex
0x180004b57  call    cs:__imp_ReleaseMutex
0x180004b5d  test    eax, eax
0x180004b5f  jz      loc_180004D6C
0x180004b65  mov     rcx, rbx; hObject
0x180004b68  call    cs:__imp_CloseHandle
0x180004b6e  test    eax, eax
0x180004b70  jz      loc_180004D7E
0x180004b76  mov     eax, esi
0x180004b78  jmp     loc_180004D27
0x180004b7d  mov     rax, [rsp+280h+hObject]
0x180004b82  lea     rcx, ds:0[rax*4]
0x180004b8a  test    rcx, rcx
0x180004b8d  jz      short loc_180004B9D
0x180004b8f  mov     [r15], rcx
0x180004b92  mov     eax, [rcx]
0x180004b94  inc     eax
0x180004b96  mov     [rcx], eax
0x180004b98  jmp     loc_180004CFD
0x180004b9d  mov     rdx, r14; dwBytes
0x180004ba0  mov     qword ptr [r15], 0
0x180004ba7  mov     ecx, 8; dwFlags
0x180004bac  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004bb1  mov     rsi, rax
0x180004bb4  test    rax, rax
0x180004bb7  jnz     short loc_180004BDF
0x180004bb9  mov     rcx, [rbp+188h]; this
0x180004bc0  lea     r8, aWil; "wil"
0x180004bc7  mov     r14d, 8007000Eh
0x180004bcd  mov     edx, 14Bh; void *
0x180004bd2  mov     r9d, r14d; char *
0x180004bd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004bda  jmp     loc_180004C72
0x180004bdf  xorps   xmm0, xmm0
0x180004be2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004be8  test    sil, 3
0x180004bec  jnz     loc_180004D90
0x180004bf2  mov     r9, rsi
0x180004bf5  lea     rdx, [rsp+280h+pszDest]; unsigned __int16 *
0x180004bfa  shr     r9, 2; unsigned __int64
0x180004bfe  lea     rcx, [rsp+280h+hObject]; this
0x180004c03  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004c08  mov     r14d, eax
0x180004c0b  test    eax, eax
0x180004c0d  jns     loc_180004CB9
0x180004c13  mov     rcx, [rbp+188h]; this
0x180004c1a  lea     r8, aWil; "wil"
0x180004c21  mov     r9d, eax; char *
0x180004c24  mov     edx, 14Eh; void *
0x180004c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c2e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004c33  test    rcx, rcx
0x180004c36  jz      short loc_180004C46
0x180004c38  call    cs:__imp_CloseHandle
0x180004c3e  test    eax, eax
0x180004c40  jz      loc_180004D96
0x180004c46  mov     rcx, [rsp+280h+hObject]; hObject
0x180004c4b  test    rcx, rcx
0x180004c4e  jz      short loc_180004C5E
0x180004c50  call    cs:__imp_CloseHandle
0x180004c56  test    eax, eax
0x180004c58  jz      loc_180004DA8
0x180004c5e  call    cs:__imp_GetProcessHeap
0x180004c64  mov     r8, rsi; lpMem
0x180004c67  xor     edx, edx; dwFlags
0x180004c69  mov     rcx, rax; hHeap
0x180004c6c  call    cs:__imp_HeapFree
0x180004c72  mov     rcx, [rbp+188h]; this
0x180004c79  lea     r8, aWil; "wil"
0x180004c80  mov     r9d, r14d; char *
0x180004c83  mov     edx, 137h; void *
0x180004c88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c8d  test    rdi, rdi
0x180004c90  jz      short loc_180004CA3
0x180004c92  mov     rcx, rdi; hMutex
0x180004c95  call    cs:__imp_ReleaseMutex
0x180004c9b  test    eax, eax
0x180004c9d  jz      loc_180004DBA
0x180004ca3  mov     rcx, rbx; hObject
0x180004ca6  call    cs:__imp_CloseHandle
0x180004cac  test    eax, eax
0x180004cae  jz      loc_180004DCC
0x180004cb4  mov     eax, r14d
0x180004cb7  jmp     short loc_180004D27
0x180004cb9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004cbe  xor     edx, edx; Val
0x180004cc0  mov     dword ptr [rsi], 1
0x180004cc6  lea     rcx, [rsi+22h]; void *
0x180004cca  mov     [rsi+8], rbx
0x180004cce  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004cd3  lea     r8d, [rdx+56h]; Size
0x180004cd7  call    memset_0
0x180004cdc  xor     edx, edx; Val
0x180004cde  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004ce4  lea     rcx, [rsi+28h]; void *
0x180004ce8  mov     dword ptr [rsi+24h], 1
0x180004cef  lea     r8d, [rdx+50h]; Size
0x180004cf3  call    memset_0
0x180004cf8  xor     ebx, ebx
0x180004cfa  mov     [r15], rsi
0x180004cfd  test    rdi, rdi
0x180004d00  jz      short loc_180004D13
0x180004d02  mov     rcx, rdi; hMutex
0x180004d05  call    cs:__imp_ReleaseMutex
0x180004d0b  test    eax, eax
0x180004d0d  jz      loc_180004DDE
0x180004d13  test    rbx, rbx
0x180004d16  jz      short loc_180004D25
0x180004d18  mov     rcx, rbx; hObject
0x180004d1b  call    cs:__imp_CloseHandle
0x180004d21  test    eax, eax
0x180004d23  jz      short loc_180004D4D
0x180004d25  xor     eax, eax
0x180004d27  mov     rcx, [rbp+180h+var_30]
0x180004d2e  xor     rcx, rsp; StackCookie
0x180004d31  call    __security_check_cookie
0x180004d36  mov     rbx, [rsp+280h+arg_10]
0x180004d3e  add     rsp, 260h
0x180004d45  pop     r15
0x180004d47  pop     r14
0x180004d49  pop     rdi
0x180004d4a  pop     rsi
0x180004d4b  pop     rbp
0x180004d4c  retn
0x180004d4d  mov     rcx, [rbp+188h]; this
0x180004d54  mov     edx, 0A0Bh; void *
0x180004d59  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d5f  mov     rcx, [rbp+188h]; this
0x180004d66  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004d6c  mov     rcx, [rbp+188h]; this
0x180004d73  mov     edx, 0A15h; void *
0x180004d78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d7e  mov     rcx, [rbp+188h]; this
0x180004d85  mov     edx, 0A0Bh; void *
0x180004d8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004d90  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004d96  mov     rcx, [rbp+188h]; this
0x180004d9d  mov     edx, 0A0Bh; void *
0x180004da2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004da8  mov     rcx, [rbp+188h]; this
0x180004daf  mov     edx, 0A0Bh; void *
0x180004db4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004dba  mov     rcx, [rbp+188h]; this
0x180004dc1  mov     edx, 0A15h; void *
0x180004dc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004dcc  mov     rcx, [rbp+188h]; this
0x180004dd3  mov     edx, 0A0Bh; void *
0x180004dd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004dde  mov     rcx, [rbp+188h]; this
0x180004de5  mov     edx, 0A15h; void *
0x180004dea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
