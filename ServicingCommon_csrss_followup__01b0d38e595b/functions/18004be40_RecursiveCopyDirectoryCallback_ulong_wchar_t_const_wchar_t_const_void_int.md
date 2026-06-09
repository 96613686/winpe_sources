# RecursiveCopyDirectoryCallback(ulong,wchar_t const *,wchar_t const *,void *,int)

- ea: `0x18004be40`
- end: `0x18004c031`
- name: `?RecursiveCopyDirectoryCallback@@YAJKPEB_W0PEAXH@Z`
- size: `497`
- prototype: `__int64 __fastcall(unsigned int, const wchar_t *, const wchar_t *, void *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180020440`
- `0x180026c90`
- `0x1800282d0`
- `0x18002d2b0`
- `0x180046650`
- `0x1800468fc`
- `0x180046ca4`
- `0x18004be40`
- `0x18004fb00`
- `0x1800504d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004bf74`
- `KERNEL32!GetLastError` at `0x18004bf74`
- `KERNEL32!PrivCopyFileExW` at `0x18004bf60`
- `KERNEL32!PrivCopyFileExW` at `0x18004bf60`

## string_xrefs

- `0x18004beba`: `No full directory path specified`
- `0x18004bfbb`: `Failed creating directory {}`

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
0x18004be40  mov     [rsp-18h+arg_0], rbx
0x18004be45  mov     [rsp-18h+arg_10], rsi
0x18004be4a  push    rbp
0x18004be4b  push    rdi
0x18004be4c  push    r14
0x18004be4e  mov     rbp, rsp
0x18004be51  sub     rsp, 60h
0x18004be55  mov     rax, cs:__security_cookie
0x18004be5c  xor     rax, rsp
0x18004be5f  mov     [rbp+var_10], rax
0x18004be63  xor     r14d, r14d
0x18004be66  mov     rbx, r9
0x18004be69  mov     rsi, rdx
0x18004be6c  mov     [rbp+var_30], r14
0x18004be70  cmp     [rbp+arg_20], r14d
0x18004be74  jz      loc_18004C001
0x18004be7a  mov     rcx, [r9+8]; String1
0x18004be7e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004be82  inc     r8; MaxCount
0x18004be85  cmp     [rcx+r8*2], r14w
0x18004be8a  jnz     short loc_18004BE82
0x18004be8c  call    _wcsnicmp
0x18004be91  test    eax, eax
0x18004be93  jz      loc_18004C001
0x18004be99  test    rsi, rsi
0x18004be9c  jnz     short loc_18004BEF7
0x18004be9e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004bea5  mov     edi, 80070057h
0x18004beaa  mov     [rbp+var_18], edi
0x18004bead  test    rcx, rcx
0x18004beb0  jz      short loc_18004BEED
0x18004beb2  lea     ebx, [rsi+3]
0x18004beb5  xor     edx, edx
0x18004beb7  mov     r8d, ebx
0x18004beba  lea     r9, aNoFullDirector; "No full directory path specified"
0x18004bec1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004bec6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004becd  lea     rax, [rbp+var_18]
0x18004bed1  mov     [rbp+var_28], rax
0x18004bed5  lea     r9, asc_1800AFAD8; ": {}"
0x18004bedc  lea     rax, [rbp+var_28]
0x18004bee0  mov     r8d, ebx
0x18004bee3  mov     [rsp+60h+var_40], rax
0x18004bee8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004beed  mov     r9d, edi
0x18004bef0  mov     edx, 285h
0x18004bef5  jmp     short loc_18004BF12
0x18004bef7  mov     rdx, [rbx+8]
0x18004befb  lea     rcx, [rbp+var_30]
0x18004beff  call    SczAllocFromSz
0x18004bf04  mov     edi, eax
0x18004bf06  test    eax, eax
0x18004bf08  jns     short loc_18004BF27
0x18004bf0a  mov     edx, 288h; void *
0x18004bf0f  mov     r9d, eax; char *
0x18004bf12  mov     rcx, [rbp+18h]; this
0x18004bf16  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x18004bf1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bf22  jmp     loc_18004C004
0x18004bf27  mov     eax, [rbx]
0x18004bf29  lea     rcx, [rbp+var_30]
0x18004bf2d  lea     rdx, [rsi+rax*2]
0x18004bf31  call    SczAllocConcatSz
0x18004bf36  mov     edi, eax
0x18004bf38  test    eax, eax
0x18004bf3a  jns     short loc_18004BF43
0x18004bf3c  mov     edx, 289h
0x18004bf41  jmp     short loc_18004BF0F
0x18004bf43  mov     rbx, [rbp+var_30]
0x18004bf47  xor     r9d, r9d
0x18004bf4a  mov     rdx, rbx
0x18004bf4d  mov     [rsp+60h+var_38], 9F0h
0x18004bf55  xor     r8d, r8d
0x18004bf58  mov     [rsp+60h+var_40], r14
0x18004bf5d  mov     rcx, rsi
0x18004bf60  call    cs:__imp_PrivCopyFileExW
0x18004bf67  nop     dword ptr [rax+rax+00h]
0x18004bf6c  test    eax, eax
0x18004bf6e  jnz     loc_18004C001
0x18004bf74  call    cs:__imp_GetLastError
0x18004bf7b  nop     dword ptr [rax+rax+00h]
0x18004bf80  mov     edi, eax
0x18004bf82  test    eax, eax
0x18004bf84  jle     short loc_18004BF8F
0x18004bf86  movzx   edi, ax
0x18004bf89  or      edi, 80070000h
0x18004bf8f  cmp     edi, 800700B7h
0x18004bf95  jz      short loc_18004C001
0x18004bf97  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004bf9e  mov     [rbp+var_18], edi
0x18004bfa1  test    rcx, rcx
0x18004bfa4  jz      short loc_18004BFF0
0x18004bfa6  mov     [rbp+var_28], rbx
0x18004bfaa  lea     rax, [rbp+var_28]
0x18004bfae  mov     ebx, 3
0x18004bfb3  mov     [rsp+60h+var_40], rax
0x18004bfb8  mov     r8d, ebx
0x18004bfbb  lea     r9, aFailedCreating_0; "Failed creating directory {}"
0x18004bfc2  xor     edx, edx
0x18004bfc4  call    ??$LogNumObjects@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x18004bfc9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004bfd0  lea     rax, [rbp+var_18]
0x18004bfd4  mov     [rbp+var_20], rax
0x18004bfd8  lea     r9, asc_1800AFAD8; ": {}"
0x18004bfdf  lea     rax, [rbp+var_20]
0x18004bfe3  mov     r8d, ebx
0x18004bfe6  mov     [rsp+60h+var_40], rax
0x18004bfeb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004bff0  test    edi, edi
0x18004bff2  jns     short loc_18004C004
0x18004bff4  mov     r9d, edi
0x18004bff7  mov     edx, 29Dh
0x18004bffc  jmp     loc_18004BF12
0x18004c001  mov     edi, r14d
0x18004c004  lea     rcx, [rbp+var_30]
0x18004c008  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004c00d  mov     eax, edi
0x18004c00f  mov     rcx, [rbp+var_10]
0x18004c013  xor     rcx, rsp; StackCookie
0x18004c016  call    __security_check_cookie
0x18004c01b  lea     r11, [rsp+60h+var_s0]
0x18004c020  mov     rbx, [r11+20h]
0x18004c024  mov     rsi, [r11+30h]
0x18004c028  mov     rsp, r11
0x18004c02b  pop     r14
0x18004c02d  pop     rdi
0x18004c02e  pop     rbp
0x18004c02f  retn
```
