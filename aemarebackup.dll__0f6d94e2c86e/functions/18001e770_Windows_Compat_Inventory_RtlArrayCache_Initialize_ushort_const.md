# Windows::Compat::Inventory::RtlArrayCache::Initialize(ushort const *)

- ea: `0x18001e770`
- end: `0x18001eb74`
- name: `?Initialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `1028`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::RtlArrayCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001efb4`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x180006d30`
- `0x180009970`
- `0x18000a2a8`
- `0x18000d62c`
- `0x18000e54c`
- `0x18001e770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001e7ee`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001e7ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001e83d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001e83d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001e8b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001e92e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001e98e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ea8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001eaac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001e8b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001e92e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001e98e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ea8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001eaac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e9e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e9e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e826`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e80b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e96d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e80b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e96d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e7ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e7ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e816`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e816`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001e95e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001e95e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001e8fe`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001e8fe`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18001e8d0`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18001e8d0`

## string_xrefs

- `0x18001e7b9`: `RtlArrayCache%lsMutex%d`
- `0x18001e889`: `RtlArrayCache%lsMemory%d`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::RtlArrayCache::Initialize(
        Windows::Compat::Inventory::RtlArrayCache *this,
        const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  wil::details *v5; // rcx
  HANDLE Mutex; // rdi
  void *v7; // rbx
  DWORD LastError; // ebp
  unsigned int v9; // r8d
  const char *v10; // r9
  void *v11; // rdi
  DWORD v12; // eax
  void *v13; // rdx
  __int64 v14; // r8
  const char *v15; // r9
  signed int v16; // eax
  unsigned int v17; // r8d
  const char *v18; // r9
  HANDLE FileMappingW; // rax
  signed int v20; // eax
  unsigned int v21; // r8d
  const char *v22; // r9
  char v23; // bl
  _DWORD *v24; // rax
  signed int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  _OWORD *v28; // rax
  _QWORD *v29; // rbx
  _OWORD *v30; // rax
  _QWORD *v31; // rbx
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  _QWORD *v36; // rcx
  DWORD dwMaximumSizeLowa; // [rsp+20h] [rbp-258h]
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  memset_0(Name, 0, 0x208u);
  dwMaximumSizeLowa = GetCurrentProcessId();
  v4 = StringCchPrintfW(Name, 0x104u, L"RtlArrayCache%lsMutex%d", a2, dwMaximumSizeLowa);
  if ( (v4 & 0x80000000) != 0 )
    return v4;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  if ( Mutex )
  {
    GetLastError();
    v7 = (void *)*((_QWORD *)this + 5);
    if ( v7 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v7) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 5) = Mutex;
  }
  else if ( (int)wil::details::GetLastErrorFailHr(v5) < 0 )
  {
    v16 = GetLastError();
    v4 = v16;
    if ( v16 > 0 )
      return (unsigned __int16)v16 | 0x80070000;
    return v4;
  }
  v11 = (void *)*((_QWORD *)this + 5);
  v12 = WaitForSingleObjectEx(v11, 0xFFFFFFFF, 0);
  if ( v12 == 258 )
  {
    v11 = 0;
  }
  else if ( (v12 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::FailFast_Unexpected(retaddr, v13, v14, v15);
  }
  dwMaximumSizeLow[0] = GetCurrentProcessId();
  v4 = StringCchPrintfW(Name, 0x104u, L"RtlArrayCache%lsMemory%d", a2, *(_QWORD *)dwMaximumSizeLow);
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
    return v4;
  }
  FileMappingW = OpenFileMappingW(2u, 0, Name);
  *((_QWORD *)this + 4) = FileMappingW;
  if ( FileMappingW )
  {
    v23 = 1;
  }
  else
  {
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x18u, Name);
    *((_QWORD *)this + 4) = FileMappingW;
    if ( !FileMappingW )
    {
      v20 = GetLastError();
      v4 = v20;
      if ( v20 > 0 )
        v4 = (unsigned __int16)v20 | 0x80070000;
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v21, v22);
      return v4;
    }
    v23 = 0;
  }
  v24 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
  *((_QWORD *)this + 6) = v24;
  if ( v24 )
  {
    if ( v23 )
      goto LABEL_45;
    v24[4] = 0;
    v28 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v29 = v28;
    if ( v28 )
    {
      *v28 = 0;
      v28[1] = 0;
      v28[2] = 0;
      *(_QWORD *)v28 = GetProcessHeap();
      v29[4] = 16;
      v29[2] = 0;
      v29[3] = 0;
      v29[5] = 0;
      v29[1] = 8;
    }
    else
    {
      v29 = 0;
    }
    **((_QWORD **)this + 6) = v29;
    v30 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v31 = v30;
    if ( v30 )
    {
      *v30 = 0;
      v30[1] = 0;
      v30[2] = 0;
      *(_QWORD *)v30 = GetProcessHeap();
      v31[4] = 16;
      v31[2] = 0;
      v31[3] = 0;
      v31[5] = 0;
      v31[1] = 8;
    }
    else
    {
      v31 = 0;
    }
    *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = v31;
    v24 = (_DWORD *)*((_QWORD *)this + 6);
    if ( *(_QWORD *)v24 && *((_QWORD *)v24 + 1) )
    {
LABEL_45:
      ++v24[4];
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
      v36 = (_QWORD *)*((_QWORD *)this + 6);
      v4 = 0;
      *((_QWORD *)this + 2) = v36[1];
      *((_QWORD *)this + 1) = *v36;
    }
    else
    {
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v25 = GetLastError();
    v4 = v25;
    if ( v25 > 0 )
      v4 = (unsigned __int16)v25 | 0x80070000;
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
  }
  return v4;
}

```

## disassembly

```asm
0x18001e770  mov     [rsp+arg_10], rbx
0x18001e775  push    rbp
0x18001e776  push    rsi
0x18001e777  push    rdi
0x18001e778  push    r12
0x18001e77a  push    r14
0x18001e77c  sub     rsp, 250h
0x18001e783  mov     rax, cs:__security_cookie
0x18001e78a  xor     rax, rsp
0x18001e78d  mov     [rsp+278h+var_38], rax
0x18001e795  mov     r14, rdx
0x18001e798  mov     rsi, rcx
0x18001e79b  xor     edx, edx; Val
0x18001e79d  lea     rcx, [rsp+278h+Name]; void *
0x18001e7a2  mov     r8d, 208h; Size
0x18001e7a8  call    memset_0
0x18001e7ad  call    cs:__imp_GetCurrentProcessId
0x18001e7b3  mov     r12d, 104h
0x18001e7b9  lea     r8, aRtlarraycacheL; "RtlArrayCache%lsMutex%d"
0x18001e7c0  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18001e7c5  mov     [rsp+278h+dwMaximumSizeLow], eax
0x18001e7c9  mov     edx, r12d; unsigned __int64
0x18001e7cc  mov     r9, r14
0x18001e7cf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e7d4  mov     ebx, eax
0x18001e7d6  test    eax, eax
0x18001e7d8  js      loc_18001EACB
0x18001e7de  mov     r9d, 1F0001h; dwDesiredAccess
0x18001e7e4  lea     rdx, [rsp+278h+Name]; lpName
0x18001e7e9  xor     r8d, r8d; dwFlags
0x18001e7ec  xor     ecx, ecx; lpMutexAttributes
0x18001e7ee  call    cs:__imp_CreateMutexExW
0x18001e7f4  mov     rdi, rax
0x18001e7f7  test    rax, rax
0x18001e7fa  jz      short loc_18001E857
0x18001e7fc  call    cs:__imp_GetLastError
0x18001e802  mov     rbx, [rsi+28h]
0x18001e806  test    rbx, rbx
0x18001e809  jz      short loc_18001E82C
0x18001e80b  call    cs:__imp_GetLastError
0x18001e811  mov     rcx, rbx; hObject
0x18001e814  mov     ebp, eax
0x18001e816  call    cs:__imp_CloseHandle
0x18001e81c  test    eax, eax
0x18001e81e  jz      loc_18001EB4E
0x18001e824  mov     ecx, ebp; dwErrCode
0x18001e826  call    cs:__imp_SetLastError
0x18001e82c  mov     [rsi+28h], rdi
0x18001e830  mov     rdi, [rsi+28h]
0x18001e834  xor     r8d, r8d; bAlertable
0x18001e837  mov     rcx, rdi; hHandle
0x18001e83a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001e83d  call    cs:__imp_WaitForSingleObjectEx
0x18001e843  cmp     eax, 102h
0x18001e848  jz      short loc_18001E87E
0x18001e84a  test    eax, 0FFFFFF7Fh
0x18001e84f  jnz     loc_18001EB07
0x18001e855  jmp     short loc_18001E880
0x18001e857  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001e85c  test    eax, eax
0x18001e85e  jns     short loc_18001E830
0x18001e860  call    cs:__imp_GetLastError
0x18001e866  mov     ebx, eax
0x18001e868  test    eax, eax
0x18001e86a  jle     loc_18001EACB
0x18001e870  movzx   ebx, ax
0x18001e873  or      ebx, 80070000h
0x18001e879  jmp     loc_18001EACB
0x18001e87e  xor     edi, edi
0x18001e880  call    cs:__imp_GetCurrentProcessId
0x18001e886  mov     r9, r14
0x18001e889  lea     r8, aRtlarraycacheL_0; "RtlArrayCache%lsMemory%d"
0x18001e890  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18001e895  mov     [rsp+278h+dwMaximumSizeLow], eax
0x18001e899  mov     rdx, r12; unsigned __int64
0x18001e89c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e8a1  mov     ebx, eax
0x18001e8a3  test    eax, eax
0x18001e8a5  jns     short loc_18001E8C6
0x18001e8a7  test    rdi, rdi
0x18001e8aa  jz      loc_18001EACB
0x18001e8b0  mov     rcx, rdi; hMutex
0x18001e8b3  call    cs:__imp_ReleaseMutex
0x18001e8b9  test    eax, eax
0x18001e8bb  jz      loc_18001EB15
0x18001e8c1  jmp     loc_18001EACB
0x18001e8c6  xor     edx, edx; bInheritHandle
0x18001e8c8  lea     r8, [rsp+278h+Name]; lpName
0x18001e8cd  lea     ecx, [rdx+2]; dwDesiredAccess
0x18001e8d0  call    cs:__imp_OpenFileMappingW
0x18001e8d6  mov     [rsi+20h], rax
0x18001e8da  test    rax, rax
0x18001e8dd  jnz     short loc_18001E945
0x18001e8df  xor     r9d, r9d; dwMaximumSizeHigh
0x18001e8e2  lea     rax, [rsp+278h+Name]
0x18001e8e7  mov     [rsp+278h+lpName], rax; lpName
0x18001e8ec  xor     edx, edx; lpFileMappingAttributes
0x18001e8ee  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001e8f2  mov     [rsp+278h+dwMaximumSizeLow], 18h; dwMaximumSizeLow
0x18001e8fa  lea     r8d, [r9+4]; flProtect
0x18001e8fe  call    cs:__imp_CreateFileMappingW
0x18001e904  mov     [rsi+20h], rax
0x18001e908  test    rax, rax
0x18001e90b  jnz     short loc_18001E941
0x18001e90d  call    cs:__imp_GetLastError
0x18001e913  mov     ebx, eax
0x18001e915  test    eax, eax
0x18001e917  jle     short loc_18001E922
0x18001e919  movzx   ebx, ax
0x18001e91c  or      ebx, 80070000h
0x18001e922  test    rdi, rdi
0x18001e925  jz      loc_18001EACB
0x18001e92b  mov     rcx, rdi; hMutex
0x18001e92e  call    cs:__imp_ReleaseMutex
0x18001e934  test    eax, eax
0x18001e936  jz      loc_18001EB28
0x18001e93c  jmp     loc_18001EACB
0x18001e941  xor     bl, bl
0x18001e943  jmp     short loc_18001E947
0x18001e945  mov     bl, 1
0x18001e947  xor     r9d, r9d; dwFileOffsetLow
0x18001e94a  mov     qword ptr [rsp+278h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18001e953  xor     r8d, r8d; dwFileOffsetHigh
0x18001e956  mov     edx, 0F001Fh; dwDesiredAccess
0x18001e95b  mov     rcx, rax; hFileMappingObject
0x18001e95e  call    cs:__imp_MapViewOfFile
0x18001e964  mov     [rsi+30h], rax
0x18001e968  test    rax, rax
0x18001e96b  jnz     short loc_18001E9A1
0x18001e96d  call    cs:__imp_GetLastError
0x18001e973  mov     ebx, eax
0x18001e975  test    eax, eax
0x18001e977  jle     short loc_18001E982
0x18001e979  movzx   ebx, ax
0x18001e97c  or      ebx, 80070000h
0x18001e982  test    rdi, rdi
0x18001e985  jz      loc_18001EACB
0x18001e98b  mov     rcx, rdi; hMutex
0x18001e98e  call    cs:__imp_ReleaseMutex
0x18001e994  test    eax, eax
0x18001e996  jz      loc_18001EB3B
0x18001e99c  jmp     loc_18001EACB
0x18001e9a1  test    bl, bl
0x18001e9a3  jnz     loc_18001EAA1
0x18001e9a9  mov     r12d, 30h ; '0'
0x18001e9af  mov     dword ptr [rax+10h], 0
0x18001e9b6  mov     ecx, r12d; unsigned __int64
0x18001e9b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e9c0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e9c5  lea     ebp, [r12-20h]
0x18001e9ca  mov     rbx, rax
0x18001e9cd  lea     r14d, [r12-28h]
0x18001e9d2  test    rax, rax
0x18001e9d5  jz      short loc_18001EA10
0x18001e9d7  xorps   xmm0, xmm0
0x18001e9da  movups  xmmword ptr [rax], xmm0
0x18001e9dd  movups  xmmword ptr [rax+10h], xmm0
0x18001e9e1  movups  xmmword ptr [rax+20h], xmm0
0x18001e9e5  call    cs:__imp_GetProcessHeap
0x18001e9eb  mov     [rbx], rax
0x18001e9ee  mov     [rbx+20h], rbp
0x18001e9f2  mov     qword ptr [rbx+10h], 0
0x18001e9fa  mov     qword ptr [rbx+18h], 0
0x18001ea02  mov     qword ptr [rbx+28h], 0
0x18001ea0a  mov     [rbx+8], r14
0x18001ea0e  jmp     short loc_18001EA12
0x18001ea10  xor     ebx, ebx
0x18001ea12  mov     rax, [rsi+30h]
0x18001ea16  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ea1d  mov     rcx, r12; unsigned __int64
0x18001ea20  mov     [rax], rbx
0x18001ea23  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ea28  mov     rbx, rax
0x18001ea2b  test    rax, rax
0x18001ea2e  jz      short loc_18001EA69
0x18001ea30  xorps   xmm0, xmm0
0x18001ea33  movups  xmmword ptr [rax], xmm0
0x18001ea36  movups  xmmword ptr [rax+10h], xmm0
0x18001ea3a  movups  xmmword ptr [rax+20h], xmm0
0x18001ea3e  call    cs:__imp_GetProcessHeap
0x18001ea44  mov     [rbx], rax
0x18001ea47  mov     [rbx+20h], rbp
0x18001ea4b  mov     qword ptr [rbx+10h], 0
0x18001ea53  mov     qword ptr [rbx+18h], 0
0x18001ea5b  mov     qword ptr [rbx+28h], 0
0x18001ea63  mov     [rbx+8], r14
0x18001ea67  jmp     short loc_18001EA6B
0x18001ea69  xor     ebx, ebx
0x18001ea6b  mov     rax, [rsi+30h]
0x18001ea6f  mov     [rax+8], rbx
0x18001ea73  mov     rax, [rsi+30h]
0x18001ea77  cmp     qword ptr [rax], 0
0x18001ea7b  jz      short loc_18001EA84
0x18001ea7d  cmp     qword ptr [rax+8], 0
0x18001ea82  jnz     short loc_18001EAA1
0x18001ea84  test    rdi, rdi
0x18001ea87  jz      short loc_18001EA9A
0x18001ea89  mov     rcx, rdi; hMutex
0x18001ea8c  call    cs:__imp_ReleaseMutex
0x18001ea92  test    eax, eax
0x18001ea94  jz      loc_18001EB61
0x18001ea9a  mov     ebx, 8007000Eh
0x18001ea9f  jmp     short loc_18001EACB
0x18001eaa1  inc     dword ptr [rax+10h]
0x18001eaa4  test    rdi, rdi
0x18001eaa7  jz      short loc_18001EAB6
0x18001eaa9  mov     rcx, rdi; hMutex
0x18001eaac  call    cs:__imp_ReleaseMutex
0x18001eab2  test    eax, eax
0x18001eab4  jz      short loc_18001EAF4
0x18001eab6  mov     rcx, [rsi+30h]
0x18001eaba  xor     ebx, ebx
0x18001eabc  mov     rax, [rcx+8]
0x18001eac0  mov     [rsi+10h], rax
0x18001eac4  mov     rax, [rcx]
0x18001eac7  mov     [rsi+8], rax
0x18001eacb  mov     eax, ebx
0x18001eacd  mov     rcx, [rsp+278h+var_38]
0x18001ead5  xor     rcx, rsp; StackCookie
0x18001ead8  call    __security_check_cookie
0x18001eadd  mov     rbx, [rsp+278h+arg_10]
0x18001eae5  add     rsp, 250h
0x18001eaec  pop     r14
0x18001eaee  pop     r12
0x18001eaf0  pop     rdi
0x18001eaf1  pop     rsi
0x18001eaf2  pop     rbp
0x18001eaf3  retn
0x18001eaf4  mov     rcx, [rsp+278h]; this
0x18001eafc  mov     edx, 0A15h; void *
0x18001eb01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001eb07  mov     rcx, [rsp+278h]; this
0x18001eb0f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001eb15  mov     rcx, [rsp+278h]; this
0x18001eb1d  mov     edx, 0A15h; void *
0x18001eb22  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001eb28  mov     rcx, [rsp+278h]; this
0x18001eb30  mov     edx, 0A15h; void *
0x18001eb35  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001eb3b  mov     rcx, [rsp+278h]; this
0x18001eb43  mov     edx, 0A15h; void *
0x18001eb48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001eb4e  mov     rcx, [rsp+278h]; this
0x18001eb56  mov     edx, 0A0Bh; void *
0x18001eb5b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001eb61  mov     rcx, [rsp+278h]; this
0x18001eb69  mov     edx, 0A15h; void *
0x18001eb6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
