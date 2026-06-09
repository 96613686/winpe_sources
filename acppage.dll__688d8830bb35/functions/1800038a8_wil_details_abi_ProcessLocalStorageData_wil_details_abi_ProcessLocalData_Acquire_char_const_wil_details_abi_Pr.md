# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800038a8`
- end: `0x180003c46`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000529c`

## callees

- `0x1800038a8`
- `0x180004044`
- `0x180004684`
- `0x180005024`
- `0x180005d58`
- `0x180007274`
- `0x1800079e0`
- `0x1800082c4`
- `0x1800082d4`
- `0x18000893c`
- `0x18001623a`
- `0x180016280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180003ac9`
- `KERNEL32!HeapFree` at `0x180003ac9`
- `KERNEL32!ReleaseMutex` at `0x1800039c2`
- `KERNEL32!ReleaseMutex` at `0x180003aeb`
- `KERNEL32!ReleaseMutex` at `0x180003b5b`
- `KERNEL32!ReleaseMutex` at `0x1800039c2`
- `KERNEL32!ReleaseMutex` at `0x180003aeb`
- `KERNEL32!ReleaseMutex` at `0x180003b5b`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003941`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003941`
- `KERNEL32!CloseHandle` at `0x1800039d3`
- `KERNEL32!CloseHandle` at `0x180003a95`
- `KERNEL32!CloseHandle` at `0x180003aad`
- `KERNEL32!CloseHandle` at `0x180003afc`
- `KERNEL32!CloseHandle` at `0x180003b71`
- `KERNEL32!CloseHandle` at `0x1800039d3`
- `KERNEL32!CloseHandle` at `0x180003a95`
- `KERNEL32!CloseHandle` at `0x180003aad`
- `KERNEL32!CloseHandle` at `0x180003afc`
- `KERNEL32!CloseHandle` at `0x180003b71`
- `KERNEL32!CreateMutexExW` at `0x180003920`
- `KERNEL32!CreateMutexExW` at `0x180003920`
- `KERNEL32!GetCurrentProcessId` at `0x1800038e1`
- `KERNEL32!GetCurrentProcessId` at `0x1800038e1`
- `KERNEL32!GetProcessHeap` at `0x180003abb`
- `KERNEL32!GetProcessHeap` at `0x180003abb`

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
            pszDest,
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
0x1800038a8  mov     [rsp-8+arg_10], rbx
0x1800038ad  push    rbp
0x1800038ae  push    rsi
0x1800038af  push    rdi
0x1800038b0  push    r14
0x1800038b2  push    r15
0x1800038b4  lea     rbp, [rsp-160h]
0x1800038bc  sub     rsp, 260h
0x1800038c3  mov     rax, cs:__security_cookie
0x1800038ca  xor     rax, rsp
0x1800038cd  mov     [rbp+180h+var_30], rax
0x1800038d4  mov     r15, rdx
0x1800038d7  mov     qword ptr [rdx], 0
0x1800038de  mov     rbx, rcx
0x1800038e1  call    cs:__imp_GetCurrentProcessId
0x1800038e7  mov     r14d, 78h ; 'x'
0x1800038ed  mov     [rsp+280h+var_258], rbx
0x1800038f2  mov     r9d, eax
0x1800038f5  mov     [rsp+280h+var_260], r14d; int
0x1800038fa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003901  mov     edx, 104h; cchDest
0x180003906  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18000390b  call    StringCchPrintfW
0x180003910  mov     r9d, 1F0001h; dwDesiredAccess
0x180003916  lea     rdx, [rsp+280h+pszDest]; lpName
0x18000391b  xor     r8d, r8d; dwFlags
0x18000391e  xor     ecx, ecx; lpMutexAttributes
0x180003920  call    cs:__imp_CreateMutexExW
0x180003926  mov     rbx, rax
0x180003929  test    rax, rax
0x18000392c  jnz     short loc_180003938
0x18000392e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003933  jmp     loc_180003B7D
0x180003938  xor     r8d, r8d; bAlertable
0x18000393b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000393e  mov     rcx, rbx; hHandle
0x180003941  call    cs:__imp_WaitForSingleObjectEx
0x180003947  cmp     eax, 102h
0x18000394c  jz      short loc_18000395E
0x18000394e  test    eax, 0FFFFFF7Fh
0x180003953  jnz     loc_180003BB5
0x180003959  mov     rdi, rbx
0x18000395c  jmp     short loc_180003960
0x18000395e  xor     edi, edi
0x180003960  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003965  mov     [rsp+280h+hObject], 0
0x18000396e  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180003973  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003978  mov     esi, eax
0x18000397a  test    eax, eax
0x18000397c  jns     short loc_1800039E8
0x18000397e  mov     rcx, [rbp+188h]; this
0x180003985  mov     r9d, eax; char *
0x180003988  mov     edx, 66h ; 'f'; void *
0x18000398d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003992  mov     rcx, [rbp+188h]; this
0x180003999  mov     r9d, esi; char *
0x18000399c  mov     edx, 6Fh ; 'o'; void *
0x1800039a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039a6  mov     rcx, [rbp+188h]; this
0x1800039ad  mov     r9d, esi; char *
0x1800039b0  mov     edx, 12Eh; void *
0x1800039b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039ba  test    rdi, rdi
0x1800039bd  jz      short loc_1800039D0
0x1800039bf  mov     rcx, rdi; hMutex
0x1800039c2  call    cs:__imp_ReleaseMutex
0x1800039c8  test    eax, eax
0x1800039ca  jz      loc_180003BC2
0x1800039d0  mov     rcx, rbx; hObject
0x1800039d3  call    cs:__imp_CloseHandle
0x1800039d9  test    eax, eax
0x1800039db  jz      loc_180003BD4
0x1800039e1  mov     eax, esi
0x1800039e3  jmp     loc_180003B7D
0x1800039e8  mov     rax, [rsp+280h+hObject]
0x1800039ed  lea     rcx, ds:0[rax*4]
0x1800039f5  test    rcx, rcx
0x1800039f8  jz      short loc_180003A08
0x1800039fa  mov     [r15], rcx
0x1800039fd  mov     eax, [rcx]
0x1800039ff  inc     eax
0x180003a01  mov     [rcx], eax
0x180003a03  jmp     loc_180003B53
0x180003a08  mov     rdx, r14; dwBytes
0x180003a0b  mov     qword ptr [r15], 0
0x180003a12  mov     ecx, 8; dwFlags
0x180003a17  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003a1c  mov     rsi, rax
0x180003a1f  test    rax, rax
0x180003a22  jnz     short loc_180003A43
0x180003a24  mov     rcx, [rbp+188h]; this
0x180003a2b  mov     r14d, 8007000Eh
0x180003a31  mov     r9d, r14d; char *
0x180003a34  mov     edx, 14Bh; void *
0x180003a39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a3e  jmp     loc_180003ACF
0x180003a43  xorps   xmm0, xmm0
0x180003a46  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003a4c  test    sil, 3
0x180003a50  jnz     loc_180003BE6
0x180003a56  mov     r9, rsi
0x180003a59  lea     rdx, [rsp+280h+pszDest]; unsigned __int16 *
0x180003a5e  shr     r9, 2; unsigned __int64
0x180003a62  lea     rcx, [rsp+280h+hObject]; this
0x180003a67  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003a6c  mov     r14d, eax
0x180003a6f  test    eax, eax
0x180003a71  jns     loc_180003B0F
0x180003a77  mov     rcx, [rbp+188h]; this
0x180003a7e  mov     r9d, eax; char *
0x180003a81  mov     edx, 14Eh; void *
0x180003a86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a8b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003a90  test    rcx, rcx
0x180003a93  jz      short loc_180003AA3
0x180003a95  call    cs:__imp_CloseHandle
0x180003a9b  test    eax, eax
0x180003a9d  jz      loc_180003BEC
0x180003aa3  mov     rcx, [rsp+280h+hObject]; hObject
0x180003aa8  test    rcx, rcx
0x180003aab  jz      short loc_180003ABB
0x180003aad  call    cs:__imp_CloseHandle
0x180003ab3  test    eax, eax
0x180003ab5  jz      loc_180003BFE
0x180003abb  call    cs:__imp_GetProcessHeap
0x180003ac1  mov     r8, rsi; lpMem
0x180003ac4  xor     edx, edx; dwFlags
0x180003ac6  mov     rcx, rax; hHeap
0x180003ac9  call    cs:__imp_HeapFree
0x180003acf  mov     rcx, [rbp+188h]; this
0x180003ad6  mov     r9d, r14d; char *
0x180003ad9  mov     edx, 137h; void *
0x180003ade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ae3  test    rdi, rdi
0x180003ae6  jz      short loc_180003AF9
0x180003ae8  mov     rcx, rdi; hMutex
0x180003aeb  call    cs:__imp_ReleaseMutex
0x180003af1  test    eax, eax
0x180003af3  jz      loc_180003C10
0x180003af9  mov     rcx, rbx; hObject
0x180003afc  call    cs:__imp_CloseHandle
0x180003b02  test    eax, eax
0x180003b04  jz      loc_180003C22
0x180003b0a  mov     eax, r14d
0x180003b0d  jmp     short loc_180003B7D
0x180003b0f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003b14  xor     edx, edx; Val
0x180003b16  mov     dword ptr [rsi], 1
0x180003b1c  lea     rcx, [rsi+22h]; void *
0x180003b20  mov     [rsi+8], rbx
0x180003b24  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003b29  lea     r8d, [rdx+56h]; Size
0x180003b2d  call    memset_0
0x180003b32  xor     edx, edx; Val
0x180003b34  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003b3a  lea     rcx, [rsi+28h]; void *
0x180003b3e  mov     dword ptr [rsi+24h], 1
0x180003b45  lea     r8d, [rdx+50h]; Size
0x180003b49  call    memset_0
0x180003b4e  xor     ebx, ebx
0x180003b50  mov     [r15], rsi
0x180003b53  test    rdi, rdi
0x180003b56  jz      short loc_180003B69
0x180003b58  mov     rcx, rdi; hMutex
0x180003b5b  call    cs:__imp_ReleaseMutex
0x180003b61  test    eax, eax
0x180003b63  jz      loc_180003C34
0x180003b69  test    rbx, rbx
0x180003b6c  jz      short loc_180003B7B
0x180003b6e  mov     rcx, rbx; hObject
0x180003b71  call    cs:__imp_CloseHandle
0x180003b77  test    eax, eax
0x180003b79  jz      short loc_180003BA3
0x180003b7b  xor     eax, eax
0x180003b7d  mov     rcx, [rbp+180h+var_30]
0x180003b84  xor     rcx, rsp; StackCookie
0x180003b87  call    __security_check_cookie
0x180003b8c  mov     rbx, [rsp+280h+arg_10]
0x180003b94  add     rsp, 260h
0x180003b9b  pop     r15
0x180003b9d  pop     r14
0x180003b9f  pop     rdi
0x180003ba0  pop     rsi
0x180003ba1  pop     rbp
0x180003ba2  retn
0x180003ba3  mov     rcx, [rbp+188h]; this
0x180003baa  mov     edx, 0A0Bh; void *
0x180003baf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003bb5  mov     rcx, [rbp+188h]; this
0x180003bbc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003bc2  mov     rcx, [rbp+188h]; this
0x180003bc9  mov     edx, 0A15h; void *
0x180003bce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003bd4  mov     rcx, [rbp+188h]; this
0x180003bdb  mov     edx, 0A0Bh; void *
0x180003be0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003be6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003bec  mov     rcx, [rbp+188h]; this
0x180003bf3  mov     edx, 0A0Bh; void *
0x180003bf8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003bfe  mov     rcx, [rbp+188h]; this
0x180003c05  mov     edx, 0A0Bh; void *
0x180003c0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c10  mov     rcx, [rbp+188h]; this
0x180003c17  mov     edx, 0A15h; void *
0x180003c1c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c22  mov     rcx, [rbp+188h]; this
0x180003c29  mov     edx, 0A0Bh; void *
0x180003c2e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c34  mov     rcx, [rbp+188h]; this
0x180003c3b  mov     edx, 0A15h; void *
0x180003c40  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
