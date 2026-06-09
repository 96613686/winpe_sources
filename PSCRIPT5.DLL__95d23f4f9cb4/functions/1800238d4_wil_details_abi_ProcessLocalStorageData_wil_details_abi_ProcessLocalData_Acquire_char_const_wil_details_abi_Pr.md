# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800238d4`
- end: `0x180023c9c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180025170`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x1800238d4`
- `0x18002409c`
- `0x180024524`
- `0x180024f0c`
- `0x180025b78`
- `0x180026e80`
- `0x180027598`
- `0x180027dac`
- `0x180027dbc`
- `0x180028418`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180023b0a`
- `KERNEL32!GetProcessHeap` at `0x180023b0a`
- `KERNEL32!GetCurrentProcessId` at `0x18002390d`
- `KERNEL32!GetCurrentProcessId` at `0x18002390d`
- `KERNEL32!CreateMutexExW` at `0x18002394c`
- `KERNEL32!CreateMutexExW` at `0x18002394c`
- `KERNEL32!WaitForSingleObjectEx` at `0x18002396d`
- `KERNEL32!WaitForSingleObjectEx` at `0x18002396d`
- `KERNEL32!ReleaseMutex` at `0x180023a03`
- `KERNEL32!ReleaseMutex` at `0x180023b41`
- `KERNEL32!ReleaseMutex` at `0x180023bb1`
- `KERNEL32!ReleaseMutex` at `0x180023a03`
- `KERNEL32!ReleaseMutex` at `0x180023b41`
- `KERNEL32!ReleaseMutex` at `0x180023bb1`
- `KERNEL32!HeapFree` at `0x180023b18`
- `KERNEL32!HeapFree` at `0x180023b18`
- `KERNEL32!CloseHandle` at `0x180023a14`
- `KERNEL32!CloseHandle` at `0x180023ae4`
- `KERNEL32!CloseHandle` at `0x180023afc`
- `KERNEL32!CloseHandle` at `0x180023b52`
- `KERNEL32!CloseHandle` at `0x180023bc7`
- `KERNEL32!CloseHandle` at `0x180023a14`
- `KERNEL32!CloseHandle` at `0x180023ae4`
- `KERNEL32!CloseHandle` at `0x180023afc`
- `KERNEL32!CloseHandle` at `0x180023b52`
- `KERNEL32!CloseHandle` at `0x180023bc7`

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
0x1800238d4  mov     [rsp-8+arg_10], rbx
0x1800238d9  push    rbp
0x1800238da  push    rsi
0x1800238db  push    rdi
0x1800238dc  push    r14
0x1800238de  push    r15
0x1800238e0  lea     rbp, [rsp-160h]
0x1800238e8  sub     rsp, 260h
0x1800238ef  mov     rax, cs:__security_cookie
0x1800238f6  xor     rax, rsp
0x1800238f9  mov     [rbp+180h+var_30], rax
0x180023900  mov     r15, rdx
0x180023903  mov     qword ptr [rdx], 0
0x18002390a  mov     rbx, rcx
0x18002390d  call    cs:__imp_GetCurrentProcessId
0x180023913  mov     r14d, 78h ; 'x'
0x180023919  mov     [rsp+280h+var_258], rbx
0x18002391e  mov     r9d, eax
0x180023921  mov     [rsp+280h+var_260], r14d; int
0x180023926  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002392d  mov     edx, 104h; cchDest
0x180023932  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180023937  call    StringCchPrintfW
0x18002393c  mov     r9d, 1F0001h; dwDesiredAccess
0x180023942  lea     rdx, [rsp+280h+pszDest]; lpName
0x180023947  xor     r8d, r8d; dwFlags
0x18002394a  xor     ecx, ecx; lpMutexAttributes
0x18002394c  call    cs:__imp_CreateMutexExW
0x180023952  mov     rbx, rax
0x180023955  test    rax, rax
0x180023958  jnz     short loc_180023964
0x18002395a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002395f  jmp     loc_180023BD3
0x180023964  xor     r8d, r8d; bAlertable
0x180023967  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002396a  mov     rcx, rbx; hHandle
0x18002396d  call    cs:__imp_WaitForSingleObjectEx
0x180023973  cmp     eax, 102h
0x180023978  jz      short loc_18002398A
0x18002397a  test    eax, 0FFFFFF7Fh
0x18002397f  jnz     loc_180023C0B
0x180023985  mov     rdi, rbx
0x180023988  jmp     short loc_18002398C
0x18002398a  xor     edi, edi
0x18002398c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180023991  mov     [rsp+280h+hObject], 0
0x18002399a  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x18002399f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800239a4  mov     esi, eax
0x1800239a6  test    eax, eax
0x1800239a8  jns     short loc_180023A29
0x1800239aa  mov     rcx, [rbp+188h]; this
0x1800239b1  lea     r8, aWil; "wil"
0x1800239b8  mov     r9d, eax; char *
0x1800239bb  mov     edx, 66h ; 'f'; void *
0x1800239c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239c5  mov     rcx, [rbp+188h]; this
0x1800239cc  lea     r8, aWil; "wil"
0x1800239d3  mov     r9d, esi; char *
0x1800239d6  mov     edx, 6Fh ; 'o'; void *
0x1800239db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239e0  mov     rcx, [rbp+188h]; this
0x1800239e7  lea     r8, aWil; "wil"
0x1800239ee  mov     r9d, esi; char *
0x1800239f1  mov     edx, 12Eh; void *
0x1800239f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239fb  test    rdi, rdi
0x1800239fe  jz      short loc_180023A11
0x180023a00  mov     rcx, rdi; hMutex
0x180023a03  call    cs:__imp_ReleaseMutex
0x180023a09  test    eax, eax
0x180023a0b  jz      loc_180023C18
0x180023a11  mov     rcx, rbx; hObject
0x180023a14  call    cs:__imp_CloseHandle
0x180023a1a  test    eax, eax
0x180023a1c  jz      loc_180023C2A
0x180023a22  mov     eax, esi
0x180023a24  jmp     loc_180023BD3
0x180023a29  mov     rax, [rsp+280h+hObject]
0x180023a2e  lea     rcx, ds:0[rax*4]
0x180023a36  test    rcx, rcx
0x180023a39  jz      short loc_180023A49
0x180023a3b  mov     [r15], rcx
0x180023a3e  mov     eax, [rcx]
0x180023a40  inc     eax
0x180023a42  mov     [rcx], eax
0x180023a44  jmp     loc_180023BA9
0x180023a49  mov     rdx, r14; dwBytes
0x180023a4c  mov     qword ptr [r15], 0
0x180023a53  mov     ecx, 8; dwFlags
0x180023a58  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180023a5d  mov     rsi, rax
0x180023a60  test    rax, rax
0x180023a63  jnz     short loc_180023A8B
0x180023a65  mov     rcx, [rbp+188h]; this
0x180023a6c  lea     r8, aWil; "wil"
0x180023a73  mov     r14d, 8007000Eh
0x180023a79  mov     edx, 14Bh; void *
0x180023a7e  mov     r9d, r14d; char *
0x180023a81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023a86  jmp     loc_180023B1E
0x180023a8b  xorps   xmm0, xmm0
0x180023a8e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180023a94  test    sil, 3
0x180023a98  jnz     loc_180023C3C
0x180023a9e  mov     r9, rsi
0x180023aa1  lea     rdx, [rsp+280h+pszDest]; unsigned __int16 *
0x180023aa6  shr     r9, 2; unsigned __int64
0x180023aaa  lea     rcx, [rsp+280h+hObject]; this
0x180023aaf  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180023ab4  mov     r14d, eax
0x180023ab7  test    eax, eax
0x180023ab9  jns     loc_180023B65
0x180023abf  mov     rcx, [rbp+188h]; this
0x180023ac6  lea     r8, aWil; "wil"
0x180023acd  mov     r9d, eax; char *
0x180023ad0  mov     edx, 14Eh; void *
0x180023ad5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ada  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180023adf  test    rcx, rcx
0x180023ae2  jz      short loc_180023AF2
0x180023ae4  call    cs:__imp_CloseHandle
0x180023aea  test    eax, eax
0x180023aec  jz      loc_180023C42
0x180023af2  mov     rcx, [rsp+280h+hObject]; hObject
0x180023af7  test    rcx, rcx
0x180023afa  jz      short loc_180023B0A
0x180023afc  call    cs:__imp_CloseHandle
0x180023b02  test    eax, eax
0x180023b04  jz      loc_180023C54
0x180023b0a  call    cs:__imp_GetProcessHeap
0x180023b10  mov     r8, rsi; lpMem
0x180023b13  xor     edx, edx; dwFlags
0x180023b15  mov     rcx, rax; hHeap
0x180023b18  call    cs:__imp_HeapFree
0x180023b1e  mov     rcx, [rbp+188h]; this
0x180023b25  lea     r8, aWil; "wil"
0x180023b2c  mov     r9d, r14d; char *
0x180023b2f  mov     edx, 137h; void *
0x180023b34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b39  test    rdi, rdi
0x180023b3c  jz      short loc_180023B4F
0x180023b3e  mov     rcx, rdi; hMutex
0x180023b41  call    cs:__imp_ReleaseMutex
0x180023b47  test    eax, eax
0x180023b49  jz      loc_180023C66
0x180023b4f  mov     rcx, rbx; hObject
0x180023b52  call    cs:__imp_CloseHandle
0x180023b58  test    eax, eax
0x180023b5a  jz      loc_180023C78
0x180023b60  mov     eax, r14d
0x180023b63  jmp     short loc_180023BD3
0x180023b65  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180023b6a  xor     edx, edx; Val
0x180023b6c  mov     dword ptr [rsi], 1
0x180023b72  lea     rcx, [rsi+22h]; void *
0x180023b76  mov     [rsi+8], rbx
0x180023b7a  movdqu  xmmword ptr [rsi+10h], xmm0
0x180023b7f  lea     r8d, [rdx+56h]; Size
0x180023b83  call    memset_0
0x180023b88  xor     edx, edx; Val
0x180023b8a  mov     word ptr [rsi+20h], 58h ; 'X'
0x180023b90  lea     rcx, [rsi+28h]; void *
0x180023b94  mov     dword ptr [rsi+24h], 1
0x180023b9b  lea     r8d, [rdx+50h]; Size
0x180023b9f  call    memset_0
0x180023ba4  xor     ebx, ebx
0x180023ba6  mov     [r15], rsi
0x180023ba9  test    rdi, rdi
0x180023bac  jz      short loc_180023BBF
0x180023bae  mov     rcx, rdi; hMutex
0x180023bb1  call    cs:__imp_ReleaseMutex
0x180023bb7  test    eax, eax
0x180023bb9  jz      loc_180023C8A
0x180023bbf  test    rbx, rbx
0x180023bc2  jz      short loc_180023BD1
0x180023bc4  mov     rcx, rbx; hObject
0x180023bc7  call    cs:__imp_CloseHandle
0x180023bcd  test    eax, eax
0x180023bcf  jz      short loc_180023BF9
0x180023bd1  xor     eax, eax
0x180023bd3  mov     rcx, [rbp+180h+var_30]
0x180023bda  xor     rcx, rsp; StackCookie
0x180023bdd  call    __security_check_cookie
0x180023be2  mov     rbx, [rsp+280h+arg_10]
0x180023bea  add     rsp, 260h
0x180023bf1  pop     r15
0x180023bf3  pop     r14
0x180023bf5  pop     rdi
0x180023bf6  pop     rsi
0x180023bf7  pop     rbp
0x180023bf8  retn
0x180023bf9  mov     rcx, [rbp+188h]; this
0x180023c00  mov     edx, 0A0Bh; void *
0x180023c05  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023c0b  mov     rcx, [rbp+188h]; this
0x180023c12  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180023c18  mov     rcx, [rbp+188h]; this
0x180023c1f  mov     edx, 0A15h; void *
0x180023c24  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023c2a  mov     rcx, [rbp+188h]; this
0x180023c31  mov     edx, 0A0Bh; void *
0x180023c36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023c3c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180023c42  mov     rcx, [rbp+188h]; this
0x180023c49  mov     edx, 0A0Bh; void *
0x180023c4e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023c54  mov     rcx, [rbp+188h]; this
0x180023c5b  mov     edx, 0A0Bh; void *
0x180023c60  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023c66  mov     rcx, [rbp+188h]; this
0x180023c6d  mov     edx, 0A15h; void *
0x180023c72  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023c78  mov     rcx, [rbp+188h]; this
0x180023c7f  mov     edx, 0A0Bh; void *
0x180023c84  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180023c8a  mov     rcx, [rbp+188h]; this
0x180023c91  mov     edx, 0A15h; void *
0x180023c96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
