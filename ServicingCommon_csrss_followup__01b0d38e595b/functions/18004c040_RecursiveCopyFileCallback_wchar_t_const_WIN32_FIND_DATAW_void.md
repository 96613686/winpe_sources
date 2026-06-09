# RecursiveCopyFileCallback(wchar_t const *,_WIN32_FIND_DATAW *,void *)

- ea: `0x18004c040`
- end: `0x18004c2b6`
- name: `?RecursiveCopyFileCallback@@YAJPEB_WPEAU_WIN32_FIND_DATAW@@PEAX@Z`
- size: `630`
- prototype: `__int64 __fastcall(const wchar_t *Str, struct _WIN32_FIND_DATAW *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x180020440`
- `0x180026c90`
- `0x180028030`
- `0x1800282d0`
- `0x18002d2b0`
- `0x18002e118`
- `0x180046650`
- `0x1800468fc`
- `0x180046ca4`
- `0x18004c040`
- `0x18004fb00`
- `0x1800504d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004c1f9`
- `KERNEL32!GetLastError` at `0x18004c1f9`
- `KERNEL32!PrivCopyFileExW` at `0x18004c1e5`
- `KERNEL32!PrivCopyFileExW` at `0x18004c1e5`

## string_xrefs

- `0x18004c240`: `Failed copying file {}`

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
0x18004c040  mov     [rsp-18h+arg_8], rbx
0x18004c045  mov     [rsp-18h+arg_18], rsi
0x18004c04a  push    rbp
0x18004c04b  push    rdi
0x18004c04c  push    r14
0x18004c04e  mov     rbp, rsp
0x18004c051  sub     rsp, 60h
0x18004c055  mov     rax, cs:__security_cookie
0x18004c05c  xor     rax, rsp
0x18004c05f  mov     [rbp+var_10], rax
0x18004c063  xor     r14d, r14d
0x18004c066  mov     rbx, r8
0x18004c069  mov     [rbp+var_30], r14
0x18004c06d  mov     rsi, rcx
0x18004c070  test    rcx, rcx
0x18004c073  jnz     short loc_18004C0CE
0x18004c075  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c07c  mov     edi, 80070057h
0x18004c081  mov     [rbp+var_18], edi
0x18004c084  test    rcx, rcx
0x18004c087  jz      short loc_18004C0C4
0x18004c089  lea     ebx, [rsi+3]
0x18004c08c  xor     edx, edx
0x18004c08e  mov     r8d, ebx
0x18004c091  lea     r9, aNoFileSpecifie; "No file specified"
0x18004c098  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004c09d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c0a4  lea     rax, [rbp+var_18]
0x18004c0a8  mov     [rbp+var_28], rax
0x18004c0ac  lea     r9, asc_1800AFAD8; ": {}"
0x18004c0b3  lea     rax, [rbp+var_28]
0x18004c0b7  mov     r8d, ebx
0x18004c0ba  mov     [rsp+60h+var_40], rax
0x18004c0bf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004c0c4  mov     r9d, edi
0x18004c0c7  mov     edx, 2AAh
0x18004c0cc  jmp     short loc_18004C149
0x18004c0ce  test    rbx, rbx
0x18004c0d1  jnz     short loc_18004C12E
0x18004c0d3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c0da  mov     edi, 80070057h
0x18004c0df  mov     [rbp+var_18], edi
0x18004c0e2  test    rcx, rcx
0x18004c0e5  jz      short loc_18004C124
0x18004c0e7  mov     ebx, 3
0x18004c0ec  lea     r9, aNoContextSpeci; "No context specified"
0x18004c0f3  mov     r8d, ebx
0x18004c0f6  xor     edx, edx
0x18004c0f8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004c0fd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c104  lea     rax, [rbp+var_18]
0x18004c108  mov     [rbp+var_28], rax
0x18004c10c  lea     r9, asc_1800AFAD8; ": {}"
0x18004c113  lea     rax, [rbp+var_28]
0x18004c117  mov     r8d, ebx
0x18004c11a  mov     [rsp+60h+var_40], rax
0x18004c11f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004c124  mov     r9d, edi
0x18004c127  mov     edx, 2ABh
0x18004c12c  jmp     short loc_18004C149
0x18004c12e  mov     rdx, [r8+8]
0x18004c132  lea     rcx, [rbp+var_30]
0x18004c136  call    SczAllocFromSz
0x18004c13b  mov     edi, eax
0x18004c13d  test    eax, eax
0x18004c13f  jns     short loc_18004C15E
0x18004c141  mov     edx, 2ADh; void *
0x18004c146  mov     r9d, eax; char *
0x18004c149  mov     rcx, [rbp+18h]; this
0x18004c14d  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsfile2.cpp"
0x18004c154  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c159  jmp     loc_18004C289
0x18004c15e  mov     rcx, [rbx+8]; String1
0x18004c162  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004c166  inc     r8; MaxCount
0x18004c169  cmp     [rcx+r8*2], r14w
0x18004c16e  jnz     short loc_18004C166
0x18004c170  mov     rdx, rsi; String2
0x18004c173  call    _wcsnicmp
0x18004c178  test    eax, eax
0x18004c17a  jz      loc_18004C286
0x18004c180  mov     eax, [rbx]
0x18004c182  lea     rcx, [rbp+var_30]
0x18004c186  lea     rdx, [rsi+rax*2]
0x18004c18a  call    SczAllocConcatSz
0x18004c18f  mov     edi, eax
0x18004c191  test    eax, eax
0x18004c193  jns     short loc_18004C19C
0x18004c195  mov     edx, 2B5h
0x18004c19a  jmp     short loc_18004C146
0x18004c19c  cmp     [rbx+10h], r14
0x18004c1a0  jz      short loc_18004C1C8
0x18004c1a2  mov     edx, 2Eh ; '.'; Ch
0x18004c1a7  mov     rcx, rsi; Str
0x18004c1aa  call    wcsrchr
0x18004c1af  test    rax, rax
0x18004c1b2  jz      short loc_18004C1C8
0x18004c1b4  mov     rdx, [rbx+10h]; String2
0x18004c1b8  mov     rcx, rax; String1
0x18004c1bb  call    _wcsicmp
0x18004c1c0  test    eax, eax
0x18004c1c2  jz      loc_18004C286
0x18004c1c8  mov     rbx, [rbp+var_30]
0x18004c1cc  xor     r9d, r9d
0x18004c1cf  mov     rdx, rbx
0x18004c1d2  mov     [rsp+60h+var_38], 970h
0x18004c1da  xor     r8d, r8d
0x18004c1dd  mov     [rsp+60h+var_40], r14
0x18004c1e2  mov     rcx, rsi
0x18004c1e5  call    cs:__imp_PrivCopyFileExW
0x18004c1ec  nop     dword ptr [rax+rax+00h]
0x18004c1f1  test    eax, eax
0x18004c1f3  jnz     loc_18004C286
0x18004c1f9  call    cs:__imp_GetLastError
0x18004c200  nop     dword ptr [rax+rax+00h]
0x18004c205  mov     edi, eax
0x18004c207  test    eax, eax
0x18004c209  jle     short loc_18004C214
0x18004c20b  movzx   edi, ax
0x18004c20e  or      edi, 80070000h
0x18004c214  cmp     edi, 800700B7h
0x18004c21a  jz      short loc_18004C286
0x18004c21c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c223  mov     [rbp+var_18], edi
0x18004c226  test    rcx, rcx
0x18004c229  jz      short loc_18004C275
0x18004c22b  mov     [rbp+var_28], rbx
0x18004c22f  lea     rax, [rbp+var_28]
0x18004c233  mov     ebx, 3
0x18004c238  mov     [rsp+60h+var_40], rax
0x18004c23d  mov     r8d, ebx
0x18004c240  lea     r9, aFailedCopyingF; "Failed copying file {}"
0x18004c247  xor     edx, edx
0x18004c249  call    ??$LogNumObjects@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x18004c24e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004c255  lea     rax, [rbp+var_18]
0x18004c259  mov     [rbp+var_20], rax
0x18004c25d  lea     r9, asc_1800AFAD8; ": {}"
0x18004c264  lea     rax, [rbp+var_20]
0x18004c268  mov     r8d, ebx
0x18004c26b  mov     [rsp+60h+var_40], rax
0x18004c270  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004c275  test    edi, edi
0x18004c277  jns     short loc_18004C289
0x18004c279  mov     r9d, edi
0x18004c27c  mov     edx, 2D0h
0x18004c281  jmp     loc_18004C149
0x18004c286  mov     edi, r14d
0x18004c289  lea     rcx, [rbp+var_30]
0x18004c28d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004c292  mov     eax, edi
0x18004c294  mov     rcx, [rbp+var_10]
0x18004c298  xor     rcx, rsp; StackCookie
0x18004c29b  call    __security_check_cookie
0x18004c2a0  lea     r11, [rsp+60h+var_s0]
0x18004c2a5  mov     rbx, [r11+28h]
0x18004c2a9  mov     rsi, [r11+38h]
0x18004c2ad  mov     rsp, r11
0x18004c2b0  pop     r14
0x18004c2b2  pop     rdi
0x18004c2b3  pop     rbp
0x18004c2b4  retn
```
