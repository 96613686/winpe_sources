# RecursiveCopyDirectoryCallback(ulong,wchar_t const *,wchar_t const *,void *,int)

- ea: `0x180048d20`
- end: `0x180048f11`
- name: `?RecursiveCopyDirectoryCallback@@YAJKPEB_W0PEAXH@Z`
- size: `497`
- prototype: `__int64 __fastcall(unsigned int, const wchar_t *, const wchar_t *, void *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x18001e51c`
- `0x180022d80`
- `0x1800243c0`
- `0x1800293a0`
- `0x180041a74`
- `0x180041c30`
- `0x180041de8`
- `0x180048d20`
- `0x18004c9e0`
- `0x18004d3a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180048e54`
- `KERNEL32!GetLastError` at `0x180048e54`
- `KERNEL32!PrivCopyFileExW` at `0x180048e40`
- `KERNEL32!PrivCopyFileExW` at `0x180048e40`

## string_xrefs

- `0x180048d9a`: `No full directory path specified`
- `0x180048e9b`: `Failed creating directory {}`

## pseudocode

```c
__int64 __fastcall RecursiveCopyDirectoryCallback(__int64 a1, const wchar_t *a2, const wchar_t *a3, _QWORD *a4, int a5)
{
  const wchar_t *v7; // rcx
  size_t v8; // r8
  unsigned int v9; // edi
  int v10; // edx
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  int *v14; // rbx
  signed int LastError; // eax
  int v16; // edx
  int v18; // [rsp+20h] [rbp-40h]
  int *v19; // [rsp+30h] [rbp-30h] BYREF
  int *v20; // [rsp+38h] [rbp-28h] BYREF
  int *v21; // [rsp+40h] [rbp-20h] BYREF
  int v22; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v19 = 0;
  if ( !a5 )
    goto LABEL_23;
  v7 = (const wchar_t *)a4[1];
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  if ( !wcsnicmp(v7, a2, v8) )
    goto LABEL_23;
  if ( !a2 )
  {
    v9 = -2147024809;
    v22 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No full directory path specified");
      v20 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {}",
        (__int64)&v20);
    }
    v11 = 2147942487LL;
    v12 = 645;
    goto LABEL_12;
  }
  v13 = SczAllocFromSz(&v19, a4[1]);
  v9 = v13;
  if ( v13 < 0 )
  {
    v12 = 648;
LABEL_11:
    v11 = (unsigned int)v13;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
      (const char *)v11,
      v18);
    goto LABEL_24;
  }
  v13 = SczAllocConcatSz(&v19, &a2[*(unsigned int *)a4]);
  v9 = v13;
  if ( v13 < 0 )
  {
    v12 = 649;
    goto LABEL_11;
  }
  v14 = v19;
  v18 = 0;
  if ( (unsigned int)PrivCopyFileExW(a2, v19, 0, 0) )
    goto LABEL_23;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 == -2147024713 )
  {
LABEL_23:
    v9 = 0;
    goto LABEL_24;
  }
  v22 = v9;
  if ( LogAdapter::g_Logger )
  {
    v20 = v14;
    LogAdapter::Logger::LogNumObjects<wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed creating directory {}",
      (__int64)&v20);
    v21 = &v22;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v16,
      3,
      (unsigned int)": {}",
      (__int64)&v21);
  }
  if ( (v9 & 0x80000000) != 0 )
  {
    v11 = v9;
    v12 = 669;
    goto LABEL_12;
  }
LABEL_24:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v19);
  return v9;
}

```

## disassembly

```asm
0x180048d20  mov     [rsp-18h+arg_0], rbx
0x180048d25  mov     [rsp-18h+arg_10], rsi
0x180048d2a  push    rbp
0x180048d2b  push    rdi
0x180048d2c  push    r14
0x180048d2e  mov     rbp, rsp
0x180048d31  sub     rsp, 60h
0x180048d35  mov     rax, cs:__security_cookie
0x180048d3c  xor     rax, rsp
0x180048d3f  mov     [rbp+var_10], rax
0x180048d43  xor     r14d, r14d
0x180048d46  mov     rbx, r9
0x180048d49  mov     rsi, rdx
0x180048d4c  mov     [rbp+var_30], r14
0x180048d50  cmp     [rbp+arg_20], r14d
0x180048d54  jz      loc_180048EE1
0x180048d5a  mov     rcx, [r9+8]; String1
0x180048d5e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180048d62  inc     r8; MaxCount
0x180048d65  cmp     [rcx+r8*2], r14w
0x180048d6a  jnz     short loc_180048D62
0x180048d6c  call    _wcsnicmp
0x180048d71  test    eax, eax
0x180048d73  jz      loc_180048EE1
0x180048d79  test    rsi, rsi
0x180048d7c  jnz     short loc_180048DD7
0x180048d7e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180048d85  mov     edi, 80070057h
0x180048d8a  mov     [rbp+var_18], edi
0x180048d8d  test    rcx, rcx
0x180048d90  jz      short loc_180048DCD
0x180048d92  lea     ebx, [rsi+3]
0x180048d95  xor     edx, edx
0x180048d97  mov     r8d, ebx
0x180048d9a  lea     r9, aNoFullDirector; "No full directory path specified"
0x180048da1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180048da6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180048dad  lea     rax, [rbp+var_18]
0x180048db1  mov     [rbp+var_28], rax
0x180048db5  lea     r9, asc_1800AFB70; ": {}"
0x180048dbc  lea     rax, [rbp+var_28]
0x180048dc0  mov     r8d, ebx
0x180048dc3  mov     [rsp+60h+var_40], rax
0x180048dc8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180048dcd  mov     r9d, edi
0x180048dd0  mov     edx, 285h
0x180048dd5  jmp     short loc_180048DF2
0x180048dd7  mov     rdx, [rbx+8]
0x180048ddb  lea     rcx, [rbp+var_30]
0x180048ddf  call    SczAllocFromSz
0x180048de4  mov     edi, eax
0x180048de6  test    eax, eax
0x180048de8  jns     short loc_180048E07
0x180048dea  mov     edx, 288h; void *
0x180048def  mov     r9d, eax; char *
0x180048df2  mov     rcx, [rbp+18h]; this
0x180048df6  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x180048dfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048e02  jmp     loc_180048EE4
0x180048e07  mov     eax, [rbx]
0x180048e09  lea     rcx, [rbp+var_30]
0x180048e0d  lea     rdx, [rsi+rax*2]
0x180048e11  call    SczAllocConcatSz
0x180048e16  mov     edi, eax
0x180048e18  test    eax, eax
0x180048e1a  jns     short loc_180048E23
0x180048e1c  mov     edx, 289h
0x180048e21  jmp     short loc_180048DEF
0x180048e23  mov     rbx, [rbp+var_30]
0x180048e27  xor     r9d, r9d
0x180048e2a  mov     rdx, rbx
0x180048e2d  mov     [rsp+60h+var_38], 9F0h
0x180048e35  xor     r8d, r8d
0x180048e38  mov     [rsp+60h+var_40], r14
0x180048e3d  mov     rcx, rsi
0x180048e40  call    cs:__imp_PrivCopyFileExW
0x180048e47  nop     dword ptr [rax+rax+00h]
0x180048e4c  test    eax, eax
0x180048e4e  jnz     loc_180048EE1
0x180048e54  call    cs:__imp_GetLastError
0x180048e5b  nop     dword ptr [rax+rax+00h]
0x180048e60  mov     edi, eax
0x180048e62  test    eax, eax
0x180048e64  jle     short loc_180048E6F
0x180048e66  movzx   edi, ax
0x180048e69  or      edi, 80070000h
0x180048e6f  cmp     edi, 800700B7h
0x180048e75  jz      short loc_180048EE1
0x180048e77  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180048e7e  mov     [rbp+var_18], edi
0x180048e81  test    rcx, rcx
0x180048e84  jz      short loc_180048ED0
0x180048e86  mov     [rbp+var_28], rbx
0x180048e8a  lea     rax, [rbp+var_28]
0x180048e8e  mov     ebx, 3
0x180048e93  mov     [rsp+60h+var_40], rax
0x180048e98  mov     r8d, ebx
0x180048e9b  lea     r9, aFailedCreating; "Failed creating directory {}"
0x180048ea2  xor     edx, edx
0x180048ea4  call    ??$LogNumObjects@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x180048ea9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180048eb0  lea     rax, [rbp+var_18]
0x180048eb4  mov     [rbp+var_20], rax
0x180048eb8  lea     r9, asc_1800AFB70; ": {}"
0x180048ebf  lea     rax, [rbp+var_20]
0x180048ec3  mov     r8d, ebx
0x180048ec6  mov     [rsp+60h+var_40], rax
0x180048ecb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180048ed0  test    edi, edi
0x180048ed2  jns     short loc_180048EE4
0x180048ed4  mov     r9d, edi
0x180048ed7  mov     edx, 29Dh
0x180048edc  jmp     loc_180048DF2
0x180048ee1  mov     edi, r14d
0x180048ee4  lea     rcx, [rbp+var_30]
0x180048ee8  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180048eed  mov     eax, edi
0x180048eef  mov     rcx, [rbp+var_10]
0x180048ef3  xor     rcx, rsp; StackCookie
0x180048ef6  call    __security_check_cookie
0x180048efb  lea     r11, [rsp+60h+var_s0]
0x180048f00  mov     rbx, [r11+20h]
0x180048f04  mov     rsi, [r11+30h]
0x180048f08  mov     rsp, r11
0x180048f0b  pop     r14
0x180048f0d  pop     rdi
0x180048f0e  pop     rbp
0x180048f0f  retn
```
