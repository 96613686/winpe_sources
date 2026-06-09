# RecursiveCopyFileCallback(wchar_t const *,_WIN32_FIND_DATAW *,void *)

- ea: `0x180048f20`
- end: `0x180049196`
- name: `?RecursiveCopyFileCallback@@YAJPEB_WPEAU_WIN32_FIND_DATAW@@PEAX@Z`
- size: `630`
- prototype: `__int64 __fastcall(const wchar_t *Str, struct _WIN32_FIND_DATAW *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x18001e51c`
- `0x180022d80`
- `0x180024120`
- `0x1800243c0`
- `0x1800293a0`
- `0x18002a208`
- `0x180041a74`
- `0x180041c30`
- `0x180041de8`
- `0x180048f20`
- `0x18004c9e0`
- `0x18004d3a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800490d9`
- `KERNEL32!GetLastError` at `0x1800490d9`
- `KERNEL32!PrivCopyFileExW` at `0x1800490c5`
- `KERNEL32!PrivCopyFileExW` at `0x1800490c5`

## string_xrefs

- `0x180049120`: `Failed copying file {}`

## pseudocode

```c
__int64 __fastcall RecursiveCopyFileCallback(const wchar_t *Str, struct _WIN32_FIND_DATAW *a2, unsigned int *a3)
{
  unsigned int v5; // edi
  int v6; // edx
  __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // edx
  int v10; // eax
  const wchar_t *v11; // rcx
  size_t v12; // r8
  wchar_t *v13; // rax
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
  if ( !Str )
  {
    v5 = -2147024809;
    v22 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file specified");
      v20 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v6,
        3,
        (unsigned int)": {}",
        (__int64)&v20);
    }
    v7 = 2147942487LL;
    v8 = 682;
    goto LABEL_12;
  }
  if ( !a3 )
  {
    v5 = -2147024809;
    v22 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No context specified");
      v20 = &v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)&v20);
    }
    v7 = 2147942487LL;
    v8 = 683;
    goto LABEL_12;
  }
  v10 = SczAllocFromSz(&v19, *((_QWORD *)a3 + 1));
  v5 = v10;
  if ( v10 < 0 )
  {
    v8 = 685;
LABEL_11:
    v7 = (unsigned int)v10;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile2.cpp",
      (const char *)v7,
      v18);
    goto LABEL_30;
  }
  v11 = (const wchar_t *)*((_QWORD *)a3 + 1);
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  if ( !wcsnicmp(v11, Str, v12) )
    goto LABEL_29;
  v10 = SczAllocConcatSz(&v19, &Str[*a3]);
  v5 = v10;
  if ( v10 < 0 )
  {
    v8 = 693;
    goto LABEL_11;
  }
  if ( *((_QWORD *)a3 + 2) )
  {
    v13 = wcsrchr(Str, 0x2Eu);
    if ( v13 )
    {
      if ( !wcsicmp(v13, *((const wchar_t **)a3 + 2)) )
        goto LABEL_29;
    }
  }
  v14 = v19;
  v18 = 0;
  if ( (unsigned int)PrivCopyFileExW(Str, v19, 0, 0) )
    goto LABEL_29;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 == -2147024713 )
  {
LABEL_29:
    v5 = 0;
    goto LABEL_30;
  }
  v22 = v5;
  if ( LogAdapter::g_Logger )
  {
    v20 = v14;
    LogAdapter::Logger::LogNumObjects<wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed copying file {}",
      (__int64)&v20);
    v21 = &v22;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v16,
      3,
      (unsigned int)": {}",
      (__int64)&v21);
  }
  if ( (v5 & 0x80000000) != 0 )
  {
    v7 = v5;
    v8 = 720;
    goto LABEL_12;
  }
LABEL_30:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v19);
  return v5;
}

```

## disassembly

```asm
0x180048f20  mov     [rsp-18h+arg_8], rbx
0x180048f25  mov     [rsp-18h+arg_18], rsi
0x180048f2a  push    rbp
0x180048f2b  push    rdi
0x180048f2c  push    r14
0x180048f2e  mov     rbp, rsp
0x180048f31  sub     rsp, 60h
0x180048f35  mov     rax, cs:__security_cookie
0x180048f3c  xor     rax, rsp
0x180048f3f  mov     [rbp+var_10], rax
0x180048f43  xor     r14d, r14d
0x180048f46  mov     rbx, r8
0x180048f49  mov     [rbp+var_30], r14
0x180048f4d  mov     rsi, rcx
0x180048f50  test    rcx, rcx
0x180048f53  jnz     short loc_180048FAE
0x180048f55  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180048f5c  mov     edi, 80070057h
0x180048f61  mov     [rbp+var_18], edi
0x180048f64  test    rcx, rcx
0x180048f67  jz      short loc_180048FA4
0x180048f69  lea     ebx, [rsi+3]
0x180048f6c  xor     edx, edx
0x180048f6e  mov     r8d, ebx
0x180048f71  lea     r9, aNoFileSpecifie; "No file specified"
0x180048f78  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180048f7d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180048f84  lea     rax, [rbp+var_18]
0x180048f88  mov     [rbp+var_28], rax
0x180048f8c  lea     r9, asc_1800AFB70; ": {}"
0x180048f93  lea     rax, [rbp+var_28]
0x180048f97  mov     r8d, ebx
0x180048f9a  mov     [rsp+60h+var_40], rax
0x180048f9f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180048fa4  mov     r9d, edi
0x180048fa7  mov     edx, 2AAh
0x180048fac  jmp     short loc_180049029
0x180048fae  test    rbx, rbx
0x180048fb1  jnz     short loc_18004900E
0x180048fb3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180048fba  mov     edi, 80070057h
0x180048fbf  mov     [rbp+var_18], edi
0x180048fc2  test    rcx, rcx
0x180048fc5  jz      short loc_180049004
0x180048fc7  mov     ebx, 3
0x180048fcc  lea     r9, aNoContextSpeci; "No context specified"
0x180048fd3  mov     r8d, ebx
0x180048fd6  xor     edx, edx
0x180048fd8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180048fdd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180048fe4  lea     rax, [rbp+var_18]
0x180048fe8  mov     [rbp+var_28], rax
0x180048fec  lea     r9, asc_1800AFB70; ": {}"
0x180048ff3  lea     rax, [rbp+var_28]
0x180048ff7  mov     r8d, ebx
0x180048ffa  mov     [rsp+60h+var_40], rax
0x180048fff  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180049004  mov     r9d, edi
0x180049007  mov     edx, 2ABh
0x18004900c  jmp     short loc_180049029
0x18004900e  mov     rdx, [r8+8]
0x180049012  lea     rcx, [rbp+var_30]
0x180049016  call    SczAllocFromSz
0x18004901b  mov     edi, eax
0x18004901d  test    eax, eax
0x18004901f  jns     short loc_18004903E
0x180049021  mov     edx, 2ADh; void *
0x180049026  mov     r9d, eax; char *
0x180049029  mov     rcx, [rbp+18h]; this
0x18004902d  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x180049034  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049039  jmp     loc_180049169
0x18004903e  mov     rcx, [rbx+8]; String1
0x180049042  or      r8, 0FFFFFFFFFFFFFFFFh
0x180049046  inc     r8; MaxCount
0x180049049  cmp     [rcx+r8*2], r14w
0x18004904e  jnz     short loc_180049046
0x180049050  mov     rdx, rsi; String2
0x180049053  call    _wcsnicmp
0x180049058  test    eax, eax
0x18004905a  jz      loc_180049166
0x180049060  mov     eax, [rbx]
0x180049062  lea     rcx, [rbp+var_30]
0x180049066  lea     rdx, [rsi+rax*2]
0x18004906a  call    SczAllocConcatSz
0x18004906f  mov     edi, eax
0x180049071  test    eax, eax
0x180049073  jns     short loc_18004907C
0x180049075  mov     edx, 2B5h
0x18004907a  jmp     short loc_180049026
0x18004907c  cmp     [rbx+10h], r14
0x180049080  jz      short loc_1800490A8
0x180049082  mov     edx, 2Eh ; '.'; Ch
0x180049087  mov     rcx, rsi; Str
0x18004908a  call    wcsrchr
0x18004908f  test    rax, rax
0x180049092  jz      short loc_1800490A8
0x180049094  mov     rdx, [rbx+10h]; String2
0x180049098  mov     rcx, rax; String1
0x18004909b  call    _wcsicmp
0x1800490a0  test    eax, eax
0x1800490a2  jz      loc_180049166
0x1800490a8  mov     rbx, [rbp+var_30]
0x1800490ac  xor     r9d, r9d
0x1800490af  mov     rdx, rbx
0x1800490b2  mov     [rsp+60h+var_38], 970h
0x1800490ba  xor     r8d, r8d
0x1800490bd  mov     [rsp+60h+var_40], r14
0x1800490c2  mov     rcx, rsi
0x1800490c5  call    cs:__imp_PrivCopyFileExW
0x1800490cc  nop     dword ptr [rax+rax+00h]
0x1800490d1  test    eax, eax
0x1800490d3  jnz     loc_180049166
0x1800490d9  call    cs:__imp_GetLastError
0x1800490e0  nop     dword ptr [rax+rax+00h]
0x1800490e5  mov     edi, eax
0x1800490e7  test    eax, eax
0x1800490e9  jle     short loc_1800490F4
0x1800490eb  movzx   edi, ax
0x1800490ee  or      edi, 80070000h
0x1800490f4  cmp     edi, 800700B7h
0x1800490fa  jz      short loc_180049166
0x1800490fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180049103  mov     [rbp+var_18], edi
0x180049106  test    rcx, rcx
0x180049109  jz      short loc_180049155
0x18004910b  mov     [rbp+var_28], rbx
0x18004910f  lea     rax, [rbp+var_28]
0x180049113  mov     ebx, 3
0x180049118  mov     [rsp+60h+var_40], rax
0x18004911d  mov     r8d, ebx
0x180049120  lea     r9, aFailedCopyingF; "Failed copying file {}"
0x180049127  xor     edx, edx
0x180049129  call    ??$LogNumObjects@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x18004912e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180049135  lea     rax, [rbp+var_18]
0x180049139  mov     [rbp+var_20], rax
0x18004913d  lea     r9, asc_1800AFB70; ": {}"
0x180049144  lea     rax, [rbp+var_20]
0x180049148  mov     r8d, ebx
0x18004914b  mov     [rsp+60h+var_40], rax
0x180049150  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180049155  test    edi, edi
0x180049157  jns     short loc_180049169
0x180049159  mov     r9d, edi
0x18004915c  mov     edx, 2D0h
0x180049161  jmp     loc_180049029
0x180049166  mov     edi, r14d
0x180049169  lea     rcx, [rbp+var_30]
0x18004916d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180049172  mov     eax, edi
0x180049174  mov     rcx, [rbp+var_10]
0x180049178  xor     rcx, rsp; StackCookie
0x18004917b  call    __security_check_cookie
0x180049180  lea     r11, [rsp+60h+var_s0]
0x180049185  mov     rbx, [r11+28h]
0x180049189  mov     rsi, [r11+38h]
0x18004918d  mov     rsp, r11
0x180049190  pop     r14
0x180049192  pop     rdi
0x180049193  pop     rbp
0x180049194  retn
```
