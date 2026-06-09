# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005ad8`
- end: `0x180005e76`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800084b0`

## callees

- `0x1800017c0`
- `0x180002290`
- `0x180005ad8`
- `0x180006e6c`
- `0x180007854`
- `0x180008178`
- `0x180008e98`
- `0x18000a534`
- `0x18000b040`
- `0x18000b39c`
- `0x18000bb7c`
- `0x18000bb8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005b11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005cf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005cf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ceb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ceb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005da1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005da1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005b50`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005b50`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005b71`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005b71`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005bf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005bf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d8b`

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
0x180005ad8  mov     [rsp-8+arg_10], rbx
0x180005add  push    rbp
0x180005ade  push    rsi
0x180005adf  push    rdi
0x180005ae0  push    r14
0x180005ae2  push    r15
0x180005ae4  lea     rbp, [rsp-160h]
0x180005aec  sub     rsp, 260h
0x180005af3  mov     rax, cs:__security_cookie
0x180005afa  xor     rax, rsp
0x180005afd  mov     [rbp+180h+var_30], rax
0x180005b04  mov     r15, rdx
0x180005b07  mov     qword ptr [rdx], 0
0x180005b0e  mov     rbx, rcx
0x180005b11  call    cs:__imp_GetCurrentProcessId
0x180005b17  mov     r14d, 78h ; 'x'
0x180005b1d  mov     [rsp+280h+var_258], rbx
0x180005b22  mov     r9d, eax
0x180005b25  mov     [rsp+280h+var_260], r14d; int
0x180005b2a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005b31  mov     edx, 104h; unsigned __int64
0x180005b36  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005b3b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005b40  mov     r9d, 1F0001h; dwDesiredAccess
0x180005b46  lea     rdx, [rsp+280h+Name]; lpName
0x180005b4b  xor     r8d, r8d; dwFlags
0x180005b4e  xor     ecx, ecx; lpMutexAttributes
0x180005b50  call    cs:__imp_CreateMutexExW
0x180005b56  mov     rbx, rax
0x180005b59  test    rax, rax
0x180005b5c  jnz     short loc_180005B68
0x180005b5e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005b63  jmp     loc_180005DAD
0x180005b68  xor     r8d, r8d; bAlertable
0x180005b6b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005b6e  mov     rcx, rbx; hHandle
0x180005b71  call    cs:__imp_WaitForSingleObjectEx
0x180005b77  cmp     eax, 102h
0x180005b7c  jz      short loc_180005B8E
0x180005b7e  test    eax, 0FFFFFF7Fh
0x180005b83  jnz     loc_180005DE5
0x180005b89  mov     rdi, rbx
0x180005b8c  jmp     short loc_180005B90
0x180005b8e  xor     edi, edi
0x180005b90  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005b95  mov     [rsp+280h+hObject], 0
0x180005b9e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005ba3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005ba8  mov     esi, eax
0x180005baa  test    eax, eax
0x180005bac  jns     short loc_180005C18
0x180005bae  mov     rcx, [rbp+188h]; this
0x180005bb5  mov     r9d, eax; char *
0x180005bb8  mov     edx, 66h ; 'f'; void *
0x180005bbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bc2  mov     rcx, [rbp+188h]; this
0x180005bc9  mov     r9d, esi; char *
0x180005bcc  mov     edx, 6Fh ; 'o'; void *
0x180005bd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bd6  mov     rcx, [rbp+188h]; this
0x180005bdd  mov     r9d, esi; char *
0x180005be0  mov     edx, 12Eh; void *
0x180005be5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bea  test    rdi, rdi
0x180005bed  jz      short loc_180005C00
0x180005bef  mov     rcx, rdi; hMutex
0x180005bf2  call    cs:__imp_ReleaseMutex
0x180005bf8  test    eax, eax
0x180005bfa  jz      loc_180005DF2
0x180005c00  mov     rcx, rbx; hObject
0x180005c03  call    cs:__imp_CloseHandle
0x180005c09  test    eax, eax
0x180005c0b  jz      loc_180005E04
0x180005c11  mov     eax, esi
0x180005c13  jmp     loc_180005DAD
0x180005c18  mov     rax, [rsp+280h+hObject]
0x180005c1d  lea     rcx, ds:0[rax*4]
0x180005c25  test    rcx, rcx
0x180005c28  jz      short loc_180005C38
0x180005c2a  mov     [r15], rcx
0x180005c2d  mov     eax, [rcx]
0x180005c2f  inc     eax
0x180005c31  mov     [rcx], eax
0x180005c33  jmp     loc_180005D83
0x180005c38  mov     rdx, r14; dwBytes
0x180005c3b  mov     qword ptr [r15], 0
0x180005c42  mov     ecx, 8; dwFlags
0x180005c47  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005c4c  mov     rsi, rax
0x180005c4f  test    rax, rax
0x180005c52  jnz     short loc_180005C73
0x180005c54  mov     rcx, [rbp+188h]; this
0x180005c5b  mov     r14d, 8007000Eh
0x180005c61  mov     r9d, r14d; char *
0x180005c64  mov     edx, 14Bh; void *
0x180005c69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c6e  jmp     loc_180005CFF
0x180005c73  xorps   xmm0, xmm0
0x180005c76  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005c7c  test    sil, 3
0x180005c80  jnz     loc_180005E16
0x180005c86  mov     r9, rsi
0x180005c89  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005c8e  shr     r9, 2; unsigned __int64
0x180005c92  lea     rcx, [rsp+280h+hObject]; this
0x180005c97  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005c9c  mov     r14d, eax
0x180005c9f  test    eax, eax
0x180005ca1  jns     loc_180005D3F
0x180005ca7  mov     rcx, [rbp+188h]; this
0x180005cae  mov     r9d, eax; char *
0x180005cb1  mov     edx, 14Eh; void *
0x180005cb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005cbb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005cc0  test    rcx, rcx
0x180005cc3  jz      short loc_180005CD3
0x180005cc5  call    cs:__imp_CloseHandle
0x180005ccb  test    eax, eax
0x180005ccd  jz      loc_180005E1C
0x180005cd3  mov     rcx, [rsp+280h+hObject]; hObject
0x180005cd8  test    rcx, rcx
0x180005cdb  jz      short loc_180005CEB
0x180005cdd  call    cs:__imp_CloseHandle
0x180005ce3  test    eax, eax
0x180005ce5  jz      loc_180005E2E
0x180005ceb  call    cs:__imp_GetProcessHeap
0x180005cf1  mov     r8, rsi; lpMem
0x180005cf4  xor     edx, edx; dwFlags
0x180005cf6  mov     rcx, rax; hHeap
0x180005cf9  call    cs:__imp_HeapFree
0x180005cff  mov     rcx, [rbp+188h]; this
0x180005d06  mov     r9d, r14d; char *
0x180005d09  mov     edx, 137h; void *
0x180005d0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d13  test    rdi, rdi
0x180005d16  jz      short loc_180005D29
0x180005d18  mov     rcx, rdi; hMutex
0x180005d1b  call    cs:__imp_ReleaseMutex
0x180005d21  test    eax, eax
0x180005d23  jz      loc_180005E40
0x180005d29  mov     rcx, rbx; hObject
0x180005d2c  call    cs:__imp_CloseHandle
0x180005d32  test    eax, eax
0x180005d34  jz      loc_180005E52
0x180005d3a  mov     eax, r14d
0x180005d3d  jmp     short loc_180005DAD
0x180005d3f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005d44  xor     edx, edx; Val
0x180005d46  mov     dword ptr [rsi], 1
0x180005d4c  lea     rcx, [rsi+22h]; void *
0x180005d50  mov     [rsi+8], rbx
0x180005d54  movdqu  xmmword ptr [rsi+10h], xmm0
0x180005d59  lea     r8d, [rdx+56h]; Size
0x180005d5d  call    memset_0
0x180005d62  xor     edx, edx; Val
0x180005d64  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005d6a  lea     rcx, [rsi+28h]; void *
0x180005d6e  mov     dword ptr [rsi+24h], 1
0x180005d75  lea     r8d, [rdx+50h]; Size
0x180005d79  call    memset_0
0x180005d7e  xor     ebx, ebx
0x180005d80  mov     [r15], rsi
0x180005d83  test    rdi, rdi
0x180005d86  jz      short loc_180005D99
0x180005d88  mov     rcx, rdi; hMutex
0x180005d8b  call    cs:__imp_ReleaseMutex
0x180005d91  test    eax, eax
0x180005d93  jz      loc_180005E64
0x180005d99  test    rbx, rbx
0x180005d9c  jz      short loc_180005DAB
0x180005d9e  mov     rcx, rbx; hObject
0x180005da1  call    cs:__imp_CloseHandle
0x180005da7  test    eax, eax
0x180005da9  jz      short loc_180005DD3
0x180005dab  xor     eax, eax
0x180005dad  mov     rcx, [rbp+180h+var_30]
0x180005db4  xor     rcx, rsp; StackCookie
0x180005db7  call    __security_check_cookie
0x180005dbc  mov     rbx, [rsp+280h+arg_10]
0x180005dc4  add     rsp, 260h
0x180005dcb  pop     r15
0x180005dcd  pop     r14
0x180005dcf  pop     rdi
0x180005dd0  pop     rsi
0x180005dd1  pop     rbp
0x180005dd2  retn
0x180005dd3  mov     rcx, [rbp+188h]; this
0x180005dda  mov     edx, 0A0Bh; void *
0x180005ddf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005de5  mov     rcx, [rbp+188h]; this
0x180005dec  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005df2  mov     rcx, [rbp+188h]; this
0x180005df9  mov     edx, 0A15h; void *
0x180005dfe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e04  mov     rcx, [rbp+188h]; this
0x180005e0b  mov     edx, 0A0Bh; void *
0x180005e10  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e16  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005e1c  mov     rcx, [rbp+188h]; this
0x180005e23  mov     edx, 0A0Bh; void *
0x180005e28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e2e  mov     rcx, [rbp+188h]; this
0x180005e35  mov     edx, 0A0Bh; void *
0x180005e3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e40  mov     rcx, [rbp+188h]; this
0x180005e47  mov     edx, 0A15h; void *
0x180005e4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e52  mov     rcx, [rbp+188h]; this
0x180005e59  mov     edx, 0A0Bh; void *
0x180005e5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e64  mov     rcx, [rbp+188h]; this
0x180005e6b  mov     edx, 0A15h; void *
0x180005e70  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
