# Windows::Compat::Inventory::RtlArrayCache::Initialize(ushort const *)

- ea: `0x180106a78`
- end: `0x180106e81`
- name: `?Initialize@RtlArrayCache@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `1033`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::RtlArrayCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801072ac`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x18000a594`
- `0x18000d5a4`
- `0x18000e470`
- `0x180011d94`
- `0x180012bdc`
- `0x180106a78`

## import_xrefs

- `KERNEL32!OpenFileMappingW` at `0x180106bdf`
- `KERNEL32!OpenFileMappingW` at `0x180106bdf`
- `KERNEL32!CreateFileMappingW` at `0x180106c0d`
- `KERNEL32!CreateFileMappingW` at `0x180106c0d`
- `KERNEL32!MapViewOfFile` at `0x180106c6d`
- `KERNEL32!MapViewOfFile` at `0x180106c6d`
- `KERNEL32!GetProcessHeap` at `0x180106cef`
- `KERNEL32!GetProcessHeap` at `0x180106d4a`
- `KERNEL32!GetProcessHeap` at `0x180106cef`
- `KERNEL32!GetProcessHeap` at `0x180106d4a`
- `KERNEL32!GetCurrentProcessId` at `0x180106ab4`
- `KERNEL32!GetCurrentProcessId` at `0x180106b8b`
- `KERNEL32!GetCurrentProcessId` at `0x180106ab4`
- `KERNEL32!GetCurrentProcessId` at `0x180106b8b`
- `KERNEL32!CreateMutexExW` at `0x180106af9`
- `KERNEL32!CreateMutexExW` at `0x180106af9`
- `KERNEL32!CloseHandle` at `0x180106b21`
- `KERNEL32!CloseHandle` at `0x180106b21`
- `KERNEL32!WaitForSingleObjectEx` at `0x180106b48`
- `KERNEL32!WaitForSingleObjectEx` at `0x180106b48`
- `KERNEL32!GetLastError` at `0x180106b07`
- `KERNEL32!GetLastError` at `0x180106b16`
- `KERNEL32!GetLastError` at `0x180106b6b`
- `KERNEL32!GetLastError` at `0x180106c1c`
- `KERNEL32!GetLastError` at `0x180106c7c`
- `KERNEL32!GetLastError` at `0x180106b07`
- `KERNEL32!GetLastError` at `0x180106b16`
- `KERNEL32!GetLastError` at `0x180106b6b`
- `KERNEL32!GetLastError` at `0x180106c1c`
- `KERNEL32!GetLastError` at `0x180106c7c`
- `KERNEL32!ReleaseMutex` at `0x180106bc2`
- `KERNEL32!ReleaseMutex` at `0x180106c3d`
- `KERNEL32!ReleaseMutex` at `0x180106c9d`
- `KERNEL32!ReleaseMutex` at `0x180106d98`
- `KERNEL32!ReleaseMutex` at `0x180106db8`
- `KERNEL32!ReleaseMutex` at `0x180106bc2`
- `KERNEL32!ReleaseMutex` at `0x180106c3d`
- `KERNEL32!ReleaseMutex` at `0x180106c9d`
- `KERNEL32!ReleaseMutex` at `0x180106d98`
- `KERNEL32!ReleaseMutex` at `0x180106db8`
- `KERNEL32!SetLastError` at `0x180106b31`
- `KERNEL32!SetLastError` at `0x180106b31`

## string_xrefs

- `0x180106ac7`: `RtlArrayCache%lsMutex%d`
- `0x180106b9b`: `RtlArrayCache%lsMemory%d`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::RtlArrayCache::Initialize(
        Windows::Compat::Inventory::RtlArrayCache *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  wil::details *v4; // rcx
  HANDLE Mutex; // rdi
  void *v6; // rbx
  DWORD LastError; // ebp
  unsigned int v8; // r8d
  const char *v9; // r9
  void *v10; // rdi
  DWORD v11; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  const char *v14; // r9
  signed int v15; // eax
  unsigned int v16; // r8d
  const char *v17; // r9
  HANDLE FileMappingW; // rax
  signed int v19; // eax
  unsigned int v20; // r8d
  const char *v21; // r9
  char v22; // bl
  _DWORD *v23; // rax
  signed int v24; // eax
  unsigned int v25; // r8d
  const char *v26; // r9
  _OWORD *v27; // rax
  _QWORD *v28; // rbx
  _OWORD *v29; // rax
  _QWORD *v30; // rbx
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  _QWORD *v35; // rcx
  DWORD dwMaximumSizeLowa; // [rsp+20h] [rbp-248h]
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-248h]
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  memset_0(Name, 0, 0x208u);
  dwMaximumSizeLowa = GetCurrentProcessId();
  v3 = StringCchPrintfW(Name, 0x104u, L"RtlArrayCache%lsMutex%d", L"Mare", dwMaximumSizeLowa);
  if ( (v3 & 0x80000000) != 0 )
    return v3;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  if ( Mutex )
  {
    GetLastError();
    v6 = (void *)*((_QWORD *)this + 5);
    if ( v6 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 5) = Mutex;
  }
  else if ( (int)wil::details::GetLastErrorFailHr(v4) < 0 )
  {
    v15 = GetLastError();
    v3 = v15;
    if ( v15 > 0 )
      return (unsigned __int16)v15 | 0x80070000;
    return v3;
  }
  v10 = (void *)*((_QWORD *)this + 5);
  v11 = WaitForSingleObjectEx(v10, 0xFFFFFFFF, 0);
  if ( v11 == 258 )
  {
    v10 = 0;
  }
  else if ( (v11 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::FailFast_Unexpected(retaddr, v12, v13, v14);
  }
  dwMaximumSizeLow[0] = GetCurrentProcessId();
  v3 = StringCchPrintfW(Name, 0x104u, L"RtlArrayCache%lsMemory%d", L"Mare", *(_QWORD *)dwMaximumSizeLow);
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( v10 && !ReleaseMutex(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    return v3;
  }
  FileMappingW = OpenFileMappingW(2u, 0, Name);
  *((_QWORD *)this + 4) = FileMappingW;
  if ( FileMappingW )
  {
    v22 = 1;
  }
  else
  {
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x18u, Name);
    *((_QWORD *)this + 4) = FileMappingW;
    if ( !FileMappingW )
    {
      v19 = GetLastError();
      v3 = v19;
      if ( v19 > 0 )
        v3 = (unsigned __int16)v19 | 0x80070000;
      if ( v10 && !ReleaseMutex(v10) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v20, v21);
      return v3;
    }
    v22 = 0;
  }
  v23 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
  *((_QWORD *)this + 6) = v23;
  if ( v23 )
  {
    if ( v22 )
      goto LABEL_45;
    v23[4] = 0;
    v27 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v28 = v27;
    if ( v27 )
    {
      *v27 = 0;
      v27[1] = 0;
      v27[2] = 0;
      *(_QWORD *)v27 = GetProcessHeap();
      v28[4] = 16;
      v28[2] = 0;
      v28[3] = 0;
      v28[5] = 0;
      v28[1] = 8;
    }
    else
    {
      v28 = 0;
    }
    **((_QWORD **)this + 6) = v28;
    v29 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v30 = v29;
    if ( v29 )
    {
      *v29 = 0;
      v29[1] = 0;
      v29[2] = 0;
      *(_QWORD *)v29 = GetProcessHeap();
      v30[4] = 16;
      v30[2] = 0;
      v30[3] = 0;
      v30[5] = 0;
      v30[1] = 8;
    }
    else
    {
      v30 = 0;
    }
    *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = v30;
    v23 = (_DWORD *)*((_QWORD *)this + 6);
    if ( *(_QWORD *)v23 && *((_QWORD *)v23 + 1) )
    {
LABEL_45:
      ++v23[4];
      if ( v10 && !ReleaseMutex(v10) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v33, v34);
      v35 = (_QWORD *)*((_QWORD *)this + 6);
      v3 = 0;
      *((_QWORD *)this + 2) = v35[1];
      *((_QWORD *)this + 1) = *v35;
    }
    else
    {
      if ( v10 && !ReleaseMutex(v10) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v24 = GetLastError();
    v3 = v24;
    if ( v24 > 0 )
      v3 = (unsigned __int16)v24 | 0x80070000;
    if ( v10 && !ReleaseMutex(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
  }
  return v3;
}

```

## disassembly

```asm
0x180106a78  mov     [rsp+arg_8], rbx
0x180106a7d  mov     [rsp+arg_10], rbp
0x180106a82  push    rsi
0x180106a83  push    rdi
0x180106a84  push    r15
0x180106a86  sub     rsp, 250h
0x180106a8d  mov     rax, cs:__security_cookie
0x180106a94  xor     rax, rsp
0x180106a97  mov     [rsp+268h+var_28], rax
0x180106a9f  mov     rsi, rcx
0x180106aa2  xor     edx, edx; Val
0x180106aa4  lea     rcx, [rsp+268h+Name]; void *
0x180106aa9  mov     r8d, 208h; Size
0x180106aaf  call    memset_0
0x180106ab4  call    cs:__imp_GetCurrentProcessId
0x180106aba  mov     r15d, 104h
0x180106ac0  lea     r9, aMare; "Mare"
0x180106ac7  lea     r8, aRtlarraycacheL; "RtlArrayCache%lsMutex%d"
0x180106ace  mov     [rsp+268h+dwMaximumSizeLow], eax
0x180106ad2  mov     edx, r15d; unsigned __int64
0x180106ad5  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180106ada  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180106adf  mov     ebx, eax
0x180106ae1  test    eax, eax
0x180106ae3  js      loc_180106DD7
0x180106ae9  mov     r9d, 1F0001h; dwDesiredAccess
0x180106aef  lea     rdx, [rsp+268h+Name]; lpName
0x180106af4  xor     r8d, r8d; dwFlags
0x180106af7  xor     ecx, ecx; lpMutexAttributes
0x180106af9  call    cs:__imp_CreateMutexExW
0x180106aff  mov     rdi, rax
0x180106b02  test    rax, rax
0x180106b05  jz      short loc_180106B62
0x180106b07  call    cs:__imp_GetLastError
0x180106b0d  mov     rbx, [rsi+28h]
0x180106b11  test    rbx, rbx
0x180106b14  jz      short loc_180106B37
0x180106b16  call    cs:__imp_GetLastError
0x180106b1c  mov     rcx, rbx; hObject
0x180106b1f  mov     ebp, eax
0x180106b21  call    cs:__imp_CloseHandle
0x180106b27  test    eax, eax
0x180106b29  jz      loc_180106E5B
0x180106b2f  mov     ecx, ebp; dwErrCode
0x180106b31  call    cs:__imp_SetLastError
0x180106b37  mov     [rsi+28h], rdi
0x180106b3b  mov     rdi, [rsi+28h]
0x180106b3f  xor     r8d, r8d; bAlertable
0x180106b42  mov     rcx, rdi; hHandle
0x180106b45  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180106b48  call    cs:__imp_WaitForSingleObjectEx
0x180106b4e  cmp     eax, 102h
0x180106b53  jz      short loc_180106B89
0x180106b55  test    eax, 0FFFFFF7Fh
0x180106b5a  jnz     loc_180106E14
0x180106b60  jmp     short loc_180106B8B
0x180106b62  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180106b67  test    eax, eax
0x180106b69  jns     short loc_180106B3B
0x180106b6b  call    cs:__imp_GetLastError
0x180106b71  mov     ebx, eax
0x180106b73  test    eax, eax
0x180106b75  jle     loc_180106DD7
0x180106b7b  movzx   ebx, ax
0x180106b7e  or      ebx, 80070000h
0x180106b84  jmp     loc_180106DD7
0x180106b89  xor     edi, edi
0x180106b8b  call    cs:__imp_GetCurrentProcessId
0x180106b91  lea     r9, aMare; "Mare"
0x180106b98  mov     rdx, r15; unsigned __int64
0x180106b9b  lea     r8, aRtlarraycacheL_0; "RtlArrayCache%lsMemory%d"
0x180106ba2  mov     [rsp+268h+dwMaximumSizeLow], eax
0x180106ba6  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180106bab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180106bb0  mov     ebx, eax
0x180106bb2  test    eax, eax
0x180106bb4  jns     short loc_180106BD5
0x180106bb6  test    rdi, rdi
0x180106bb9  jz      loc_180106DD7
0x180106bbf  mov     rcx, rdi; hMutex
0x180106bc2  call    cs:__imp_ReleaseMutex
0x180106bc8  test    eax, eax
0x180106bca  jz      loc_180106E22
0x180106bd0  jmp     loc_180106DD7
0x180106bd5  xor     edx, edx; bInheritHandle
0x180106bd7  lea     r8, [rsp+268h+Name]; lpName
0x180106bdc  lea     ecx, [rdx+2]; dwDesiredAccess
0x180106bdf  call    cs:__imp_OpenFileMappingW
0x180106be5  mov     [rsi+20h], rax
0x180106be9  test    rax, rax
0x180106bec  jnz     short loc_180106C54
0x180106bee  xor     r9d, r9d; dwMaximumSizeHigh
0x180106bf1  lea     rax, [rsp+268h+Name]
0x180106bf6  mov     [rsp+268h+lpName], rax; lpName
0x180106bfb  xor     edx, edx; lpFileMappingAttributes
0x180106bfd  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180106c01  mov     [rsp+268h+dwMaximumSizeLow], 18h; dwMaximumSizeLow
0x180106c09  lea     r8d, [r9+4]; flProtect
0x180106c0d  call    cs:__imp_CreateFileMappingW
0x180106c13  mov     [rsi+20h], rax
0x180106c17  test    rax, rax
0x180106c1a  jnz     short loc_180106C50
0x180106c1c  call    cs:__imp_GetLastError
0x180106c22  mov     ebx, eax
0x180106c24  test    eax, eax
0x180106c26  jle     short loc_180106C31
0x180106c28  movzx   ebx, ax
0x180106c2b  or      ebx, 80070000h
0x180106c31  test    rdi, rdi
0x180106c34  jz      loc_180106DD7
0x180106c3a  mov     rcx, rdi; hMutex
0x180106c3d  call    cs:__imp_ReleaseMutex
0x180106c43  test    eax, eax
0x180106c45  jz      loc_180106E35
0x180106c4b  jmp     loc_180106DD7
0x180106c50  xor     bl, bl
0x180106c52  jmp     short loc_180106C56
0x180106c54  mov     bl, 1
0x180106c56  xor     r9d, r9d; dwFileOffsetLow
0x180106c59  mov     qword ptr [rsp+268h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180106c62  xor     r8d, r8d; dwFileOffsetHigh
0x180106c65  mov     edx, 0F001Fh; dwDesiredAccess
0x180106c6a  mov     rcx, rax; hFileMappingObject
0x180106c6d  call    cs:__imp_MapViewOfFile
0x180106c73  mov     [rsi+30h], rax
0x180106c77  test    rax, rax
0x180106c7a  jnz     short loc_180106CB0
0x180106c7c  call    cs:__imp_GetLastError
0x180106c82  mov     ebx, eax
0x180106c84  test    eax, eax
0x180106c86  jle     short loc_180106C91
0x180106c88  movzx   ebx, ax
0x180106c8b  or      ebx, 80070000h
0x180106c91  test    rdi, rdi
0x180106c94  jz      loc_180106DD7
0x180106c9a  mov     rcx, rdi; hMutex
0x180106c9d  call    cs:__imp_ReleaseMutex
0x180106ca3  test    eax, eax
0x180106ca5  jz      loc_180106E48
0x180106cab  jmp     loc_180106DD7
0x180106cb0  test    bl, bl
0x180106cb2  jnz     loc_180106DAD
0x180106cb8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180106cbf  mov     dword ptr [rax+10h], 0
0x180106cc6  mov     ecx, 30h ; '0'; unsigned __int64
0x180106ccb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180106cd0  mov     ebp, 10h
0x180106cd5  mov     rbx, rax
0x180106cd8  lea     r15d, [rbp-8]
0x180106cdc  test    rax, rax
0x180106cdf  jz      short loc_180106D1A
0x180106ce1  xorps   xmm0, xmm0
0x180106ce4  movups  xmmword ptr [rax], xmm0
0x180106ce7  movups  xmmword ptr [rax+10h], xmm0
0x180106ceb  movups  xmmword ptr [rax+20h], xmm0
0x180106cef  call    cs:__imp_GetProcessHeap
0x180106cf5  mov     [rbx], rax
0x180106cf8  mov     [rbx+20h], rbp
0x180106cfc  mov     qword ptr [rbx+10h], 0
0x180106d04  mov     qword ptr [rbx+18h], 0
0x180106d0c  mov     qword ptr [rbx+28h], 0
0x180106d14  mov     [rbx+8], r15
0x180106d18  jmp     short loc_180106D1C
0x180106d1a  xor     ebx, ebx
0x180106d1c  mov     rax, [rsi+30h]
0x180106d20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180106d27  mov     ecx, 30h ; '0'; unsigned __int64
0x180106d2c  mov     [rax], rbx
0x180106d2f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180106d34  mov     rbx, rax
0x180106d37  test    rax, rax
0x180106d3a  jz      short loc_180106D75
0x180106d3c  xorps   xmm0, xmm0
0x180106d3f  movups  xmmword ptr [rax], xmm0
0x180106d42  movups  xmmword ptr [rax+10h], xmm0
0x180106d46  movups  xmmword ptr [rax+20h], xmm0
0x180106d4a  call    cs:__imp_GetProcessHeap
0x180106d50  mov     [rbx], rax
0x180106d53  mov     [rbx+20h], rbp
0x180106d57  mov     qword ptr [rbx+10h], 0
0x180106d5f  mov     qword ptr [rbx+18h], 0
0x180106d67  mov     qword ptr [rbx+28h], 0
0x180106d6f  mov     [rbx+8], r15
0x180106d73  jmp     short loc_180106D77
0x180106d75  xor     ebx, ebx
0x180106d77  mov     rax, [rsi+30h]
0x180106d7b  mov     [rax+8], rbx
0x180106d7f  mov     rax, [rsi+30h]
0x180106d83  cmp     qword ptr [rax], 0
0x180106d87  jz      short loc_180106D90
0x180106d89  cmp     qword ptr [rax+8], 0
0x180106d8e  jnz     short loc_180106DAD
0x180106d90  test    rdi, rdi
0x180106d93  jz      short loc_180106DA6
0x180106d95  mov     rcx, rdi; hMutex
0x180106d98  call    cs:__imp_ReleaseMutex
0x180106d9e  test    eax, eax
0x180106da0  jz      loc_180106E6E
0x180106da6  mov     ebx, 8007000Eh
0x180106dab  jmp     short loc_180106DD7
0x180106dad  inc     dword ptr [rax+10h]
0x180106db0  test    rdi, rdi
0x180106db3  jz      short loc_180106DC2
0x180106db5  mov     rcx, rdi; hMutex
0x180106db8  call    cs:__imp_ReleaseMutex
0x180106dbe  test    eax, eax
0x180106dc0  jz      short loc_180106E01
0x180106dc2  mov     rcx, [rsi+30h]
0x180106dc6  xor     ebx, ebx
0x180106dc8  mov     rax, [rcx+8]
0x180106dcc  mov     [rsi+10h], rax
0x180106dd0  mov     rax, [rcx]
0x180106dd3  mov     [rsi+8], rax
0x180106dd7  mov     eax, ebx
0x180106dd9  mov     rcx, [rsp+268h+var_28]
0x180106de1  xor     rcx, rsp; StackCookie
0x180106de4  call    __security_check_cookie
0x180106de9  lea     r11, [rsp+268h+var_18]
0x180106df1  mov     rbx, [r11+28h]
0x180106df5  mov     rbp, [r11+30h]
0x180106df9  mov     rsp, r11
0x180106dfc  pop     r15
0x180106dfe  pop     rdi
0x180106dff  pop     rsi
0x180106e00  retn
0x180106e01  mov     rcx, [rsp+268h]; this
0x180106e09  mov     edx, 0A15h; void *
0x180106e0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180106e14  mov     rcx, [rsp+268h]; this
0x180106e1c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180106e22  mov     rcx, [rsp+268h]; this
0x180106e2a  mov     edx, 0A15h; void *
0x180106e2f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180106e35  mov     rcx, [rsp+268h]; this
0x180106e3d  mov     edx, 0A15h; void *
0x180106e42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180106e48  mov     rcx, [rsp+268h]; this
0x180106e50  mov     edx, 0A15h; void *
0x180106e55  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180106e5b  mov     rcx, [rsp+268h]; this
0x180106e63  mov     edx, 0A0Bh; void *
0x180106e68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180106e6e  mov     rcx, [rsp+268h]; this
0x180106e76  mov     edx, 0A15h; void *
0x180106e7b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
