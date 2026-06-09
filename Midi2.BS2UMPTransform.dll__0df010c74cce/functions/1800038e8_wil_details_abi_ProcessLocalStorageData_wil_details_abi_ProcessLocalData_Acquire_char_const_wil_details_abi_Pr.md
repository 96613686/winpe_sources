# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800038e8`
- end: `0x180003cb0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005790`

## callees

- `0x180001e60`
- `0x1800028c8`
- `0x1800038e8`
- `0x180004850`
- `0x180004f3c`
- `0x180005528`
- `0x1800064bc`
- `0x1800076b4`
- `0x1800080f4`
- `0x1800081ac`
- `0x180008854`
- `0x180008864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003960`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003960`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003981`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003981`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a17`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b55`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a17`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b55`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003921`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003af8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003af8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bdb`

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
0x1800038e8  mov     [rsp-8+arg_10], rbx
0x1800038ed  push    rbp
0x1800038ee  push    rsi
0x1800038ef  push    rdi
0x1800038f0  push    r14
0x1800038f2  push    r15
0x1800038f4  lea     rbp, [rsp-160h]
0x1800038fc  sub     rsp, 260h
0x180003903  mov     rax, cs:__security_cookie
0x18000390a  xor     rax, rsp
0x18000390d  mov     [rbp+180h+var_30], rax
0x180003914  mov     r15, rdx
0x180003917  mov     qword ptr [rdx], 0
0x18000391e  mov     rbx, rcx
0x180003921  call    cs:__imp_GetCurrentProcessId
0x180003927  mov     r14d, 78h ; 'x'
0x18000392d  mov     [rsp+280h+var_258], rbx
0x180003932  mov     r9d, eax
0x180003935  mov     [rsp+280h+var_260], r14d; int
0x18000393a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003941  mov     edx, 104h; unsigned __int64
0x180003946  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000394b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003950  mov     r9d, 1F0001h; dwDesiredAccess
0x180003956  lea     rdx, [rsp+280h+Name]; lpName
0x18000395b  xor     r8d, r8d; dwFlags
0x18000395e  xor     ecx, ecx; lpMutexAttributes
0x180003960  call    cs:__imp_CreateMutexExW
0x180003966  mov     rbx, rax
0x180003969  test    rax, rax
0x18000396c  jnz     short loc_180003978
0x18000396e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003973  jmp     loc_180003BE7
0x180003978  xor     r8d, r8d; bAlertable
0x18000397b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000397e  mov     rcx, rbx; hHandle
0x180003981  call    cs:__imp_WaitForSingleObjectEx
0x180003987  cmp     eax, 102h
0x18000398c  jz      short loc_18000399E
0x18000398e  test    eax, 0FFFFFF7Fh
0x180003993  jnz     loc_180003C1F
0x180003999  mov     rdi, rbx
0x18000399c  jmp     short loc_1800039A0
0x18000399e  xor     edi, edi
0x1800039a0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800039a5  mov     [rsp+280h+hObject], 0
0x1800039ae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800039b3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800039b8  mov     esi, eax
0x1800039ba  test    eax, eax
0x1800039bc  jns     short loc_180003A3D
0x1800039be  mov     rcx, [rbp+188h]; this
0x1800039c5  lea     r8, aWil; "wil"
0x1800039cc  mov     r9d, eax; char *
0x1800039cf  mov     edx, 66h ; 'f'; void *
0x1800039d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039d9  mov     rcx, [rbp+188h]; this
0x1800039e0  lea     r8, aWil; "wil"
0x1800039e7  mov     r9d, esi; char *
0x1800039ea  mov     edx, 6Fh ; 'o'; void *
0x1800039ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039f4  mov     rcx, [rbp+188h]; this
0x1800039fb  lea     r8, aWil; "wil"
0x180003a02  mov     r9d, esi; char *
0x180003a05  mov     edx, 12Eh; void *
0x180003a0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a0f  test    rdi, rdi
0x180003a12  jz      short loc_180003A25
0x180003a14  mov     rcx, rdi; hMutex
0x180003a17  call    cs:__imp_ReleaseMutex
0x180003a1d  test    eax, eax
0x180003a1f  jz      loc_180003C2C
0x180003a25  mov     rcx, rbx; hObject
0x180003a28  call    cs:__imp_CloseHandle
0x180003a2e  test    eax, eax
0x180003a30  jz      loc_180003C3E
0x180003a36  mov     eax, esi
0x180003a38  jmp     loc_180003BE7
0x180003a3d  mov     rax, [rsp+280h+hObject]
0x180003a42  lea     rcx, ds:0[rax*4]
0x180003a4a  test    rcx, rcx
0x180003a4d  jz      short loc_180003A5D
0x180003a4f  mov     [r15], rcx
0x180003a52  mov     eax, [rcx]
0x180003a54  inc     eax
0x180003a56  mov     [rcx], eax
0x180003a58  jmp     loc_180003BBD
0x180003a5d  mov     rdx, r14; dwBytes
0x180003a60  mov     qword ptr [r15], 0
0x180003a67  mov     ecx, 8; dwFlags
0x180003a6c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003a71  mov     rsi, rax
0x180003a74  test    rax, rax
0x180003a77  jnz     short loc_180003A9F
0x180003a79  mov     rcx, [rbp+188h]; this
0x180003a80  lea     r8, aWil; "wil"
0x180003a87  mov     r14d, 8007000Eh
0x180003a8d  mov     edx, 14Bh; void *
0x180003a92  mov     r9d, r14d; char *
0x180003a95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a9a  jmp     loc_180003B32
0x180003a9f  xorps   xmm0, xmm0
0x180003aa2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003aa8  test    sil, 3
0x180003aac  jnz     loc_180003C50
0x180003ab2  mov     r9, rsi
0x180003ab5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003aba  shr     r9, 2; unsigned __int64
0x180003abe  lea     rcx, [rsp+280h+hObject]; this
0x180003ac3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003ac8  mov     r14d, eax
0x180003acb  test    eax, eax
0x180003acd  jns     loc_180003B79
0x180003ad3  mov     rcx, [rbp+188h]; this
0x180003ada  lea     r8, aWil; "wil"
0x180003ae1  mov     r9d, eax; char *
0x180003ae4  mov     edx, 14Eh; void *
0x180003ae9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003aee  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003af3  test    rcx, rcx
0x180003af6  jz      short loc_180003B06
0x180003af8  call    cs:__imp_CloseHandle
0x180003afe  test    eax, eax
0x180003b00  jz      loc_180003C56
0x180003b06  mov     rcx, [rsp+280h+hObject]; hObject
0x180003b0b  test    rcx, rcx
0x180003b0e  jz      short loc_180003B1E
0x180003b10  call    cs:__imp_CloseHandle
0x180003b16  test    eax, eax
0x180003b18  jz      loc_180003C68
0x180003b1e  call    cs:__imp_GetProcessHeap
0x180003b24  mov     r8, rsi; lpMem
0x180003b27  xor     edx, edx; dwFlags
0x180003b29  mov     rcx, rax; hHeap
0x180003b2c  call    cs:__imp_HeapFree
0x180003b32  mov     rcx, [rbp+188h]; this
0x180003b39  lea     r8, aWil; "wil"
0x180003b40  mov     r9d, r14d; char *
0x180003b43  mov     edx, 137h; void *
0x180003b48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b4d  test    rdi, rdi
0x180003b50  jz      short loc_180003B63
0x180003b52  mov     rcx, rdi; hMutex
0x180003b55  call    cs:__imp_ReleaseMutex
0x180003b5b  test    eax, eax
0x180003b5d  jz      loc_180003C7A
0x180003b63  mov     rcx, rbx; hObject
0x180003b66  call    cs:__imp_CloseHandle
0x180003b6c  test    eax, eax
0x180003b6e  jz      loc_180003C8C
0x180003b74  mov     eax, r14d
0x180003b77  jmp     short loc_180003BE7
0x180003b79  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003b7e  xor     edx, edx; Val
0x180003b80  mov     dword ptr [rsi], 1
0x180003b86  lea     rcx, [rsi+22h]; void *
0x180003b8a  mov     [rsi+8], rbx
0x180003b8e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003b93  lea     r8d, [rdx+56h]; Size
0x180003b97  call    memset_0
0x180003b9c  xor     edx, edx; Val
0x180003b9e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003ba4  lea     rcx, [rsi+28h]; void *
0x180003ba8  mov     dword ptr [rsi+24h], 1
0x180003baf  lea     r8d, [rdx+50h]; Size
0x180003bb3  call    memset_0
0x180003bb8  xor     ebx, ebx
0x180003bba  mov     [r15], rsi
0x180003bbd  test    rdi, rdi
0x180003bc0  jz      short loc_180003BD3
0x180003bc2  mov     rcx, rdi; hMutex
0x180003bc5  call    cs:__imp_ReleaseMutex
0x180003bcb  test    eax, eax
0x180003bcd  jz      loc_180003C9E
0x180003bd3  test    rbx, rbx
0x180003bd6  jz      short loc_180003BE5
0x180003bd8  mov     rcx, rbx; hObject
0x180003bdb  call    cs:__imp_CloseHandle
0x180003be1  test    eax, eax
0x180003be3  jz      short loc_180003C0D
0x180003be5  xor     eax, eax
0x180003be7  mov     rcx, [rbp+180h+var_30]
0x180003bee  xor     rcx, rsp; StackCookie
0x180003bf1  call    __security_check_cookie
0x180003bf6  mov     rbx, [rsp+280h+arg_10]
0x180003bfe  add     rsp, 260h
0x180003c05  pop     r15
0x180003c07  pop     r14
0x180003c09  pop     rdi
0x180003c0a  pop     rsi
0x180003c0b  pop     rbp
0x180003c0c  retn
0x180003c0d  mov     rcx, [rbp+188h]; this
0x180003c14  mov     edx, 0A0Bh; void *
0x180003c19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c1f  mov     rcx, [rbp+188h]; this
0x180003c26  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003c2c  mov     rcx, [rbp+188h]; this
0x180003c33  mov     edx, 0A15h; void *
0x180003c38  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c3e  mov     rcx, [rbp+188h]; this
0x180003c45  mov     edx, 0A0Bh; void *
0x180003c4a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c50  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003c56  mov     rcx, [rbp+188h]; this
0x180003c5d  mov     edx, 0A0Bh; void *
0x180003c62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c68  mov     rcx, [rbp+188h]; this
0x180003c6f  mov     edx, 0A0Bh; void *
0x180003c74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c7a  mov     rcx, [rbp+188h]; this
0x180003c81  mov     edx, 0A15h; void *
0x180003c86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c8c  mov     rcx, [rbp+188h]; this
0x180003c93  mov     edx, 0A0Bh; void *
0x180003c98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c9e  mov     rcx, [rbp+188h]; this
0x180003ca5  mov     edx, 0A15h; void *
0x180003caa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
