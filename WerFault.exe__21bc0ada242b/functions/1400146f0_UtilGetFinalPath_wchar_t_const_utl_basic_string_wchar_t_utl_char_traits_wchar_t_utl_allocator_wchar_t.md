# UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x1400146f0`
- end: `0x140014a8e`
- name: `?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `926`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x140014a94`

## callees

- `0x14000113c`
- `0x1400011dc`
- `0x14000126c`
- `0x14000134c`
- `0x140002470`
- `0x14000ff08`
- `0x140014104`
- `0x1400146f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400149ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400149ef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400149ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400149ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014a5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014a5e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140014799`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140014799`

## pseudocode

```c
__int64 __fastcall UtilGetFinalPath(LPCWSTR lpFileName, const WCHAR **a2, __int64 a3, __int64 a4)
{
  char *FileW; // rbx
  signed int LastError; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  WCHAR v10; // r14
  int FinalPathByHandle; // edx
  const WCHAR *v12; // rax
  const WCHAR *v13; // rcx
  const WCHAR *v14; // rax
  __int64 v15; // r14
  int v16; // eax
  unsigned int v17; // edi
  const WCHAR *v19; // [rsp+40h] [rbp-19h] BYREF
  const WCHAR *v20; // [rsp+48h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+50h] [rbp-9h] BYREF
  const WCHAR **v22; // [rsp+70h] [rbp+17h]
  __int64 v23; // [rsp+78h] [rbp+1Fh]

  if ( !lpFileName )
  {
    FileW = 0;
LABEL_45:
    v17 = 0;
    goto LABEL_46;
  }
  if ( (unsigned int)dword_14007A000 > 4 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
  {
    v19 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      qword_14007A018,
      (__int64)&word_14006F0D6,
      a3,
      a4,
      &v19);
  }
  FileW = (char *)CreateFileW(lpFileName, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v8 = (unsigned int)LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (int)v8 >= 0 )
      v8 = 2147500037LL;
    if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
    {
      LODWORD(v19) = v8;
      v20 = lpFileName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v8,
        (__int64)word_14006F09A,
        a3,
        a4,
        &v20,
        (__int64)&v19);
    }
    goto LABEL_45;
  }
  v9 = -1;
  do
    ++v9;
  while ( lpFileName[v9] );
  v10 = lpFileName[v9 - 1];
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(FileW, (__int64)a2);
  if ( FinalPathByHandle < 0 )
  {
    if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
    {
      LODWORD(v19) = FinalPathByHandle;
      v22 = &v19;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14007A000, (unsigned __int8 *)byte_14006F06F, 0, 0, 3u, &v21);
    }
    goto LABEL_45;
  }
  if ( v10 == 92 )
  {
    v12 = a2[1];
    if ( (*a2 == v12 || *(v12 - 1) != 92)
      && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             a2,
                             92) )
    {
      v13 = *a2;
      a2[1] = *a2;
      *v13 = 0;
      goto LABEL_45;
    }
  }
  v14 = *a2;
  if ( *a2 && *v14 == 92 && v14[1] == 92 && v14[2] == 63 && v14[3] == 92 )
  {
    if ( (unsigned int)dword_14007A000 > 5 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
    {
      v20 = *a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_14007A018,
        (__int64)byte_14006F031,
        a3,
        a4,
        &v20);
    }
    v15 = 4;
  }
  else
  {
    v15 = 0;
  }
  if ( (unsigned int)dword_14007A000 > 5 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
  {
    v20 = *a2;
    v19 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      qword_14007A018,
      (__int64)&dword_14006EFEC,
      a3,
      a4,
      &v19,
      &v20);
  }
  if ( !(unsigned int)_o__wcsnicmp(lpFileName, *a2, a2[1] - *a2) )
    goto LABEL_45;
  v16 = _o__wcsnicmp(lpFileName, &(*a2)[v15], a2[1] - *a2 - v15);
  v17 = 1;
  if ( !v16 )
    goto LABEL_45;
LABEL_46:
  if ( (unsigned int)dword_14007A000 > 4 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
  {
    v20 = *a2;
    LODWORD(v19) = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      qword_14007A018,
      (__int64)word_14006EFB2,
      a3,
      a4,
      &v20,
      (__int64)&v19);
  }
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return v17;
}

```

## disassembly

```asm
0x1400146f0  mov     [rsp-8+arg_10], rbx
0x1400146f5  mov     [rsp-8+arg_18], rsi
0x1400146fa  push    rbp
0x1400146fb  push    rdi
0x1400146fc  push    r13
0x1400146fe  push    r14
0x140014700  push    r15
0x140014702  lea     rbp, [rsp-37h]
0x140014707  sub     rsp, 90h
0x14001470e  mov     rax, cs:__security_cookie
0x140014715  xor     rax, rsp
0x140014718  mov     [rbp+57h+var_30], rax
0x14001471c  xor     r15d, r15d
0x14001471f  mov     rsi, rdx
0x140014722  mov     rdi, rcx
0x140014725  test    rcx, rcx
0x140014728  jnz     short loc_140014732
0x14001472a  mov     ebx, r15d
0x14001472d  jmp     loc_1400149FE
0x140014732  mov     eax, cs:dword_14007A000
0x140014738  cmp     eax, 4
0x14001473b  jbe     short loc_140014773
0x14001473d  mov     rcx, cs:qword_14007A018
0x140014744  mov     rax, cs:qword_14007A010
0x14001474b  test    al, 8
0x14001474d  jz      short loc_140014773
0x14001474f  mov     rax, rcx
0x140014752  and     eax, 8
0x140014755  cmp     rax, rcx
0x140014758  jnz     short loc_140014773
0x14001475a  lea     rax, [rbp+57h+var_70]
0x14001475e  mov     [rbp+57h+var_70], rdi
0x140014762  lea     rdx, word_14006F0D6
0x140014769  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x14001476e  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x140014773  mov     r13d, 3
0x140014779  mov     [rsp+0B0h+hTemplateFile], r15; hTemplateFile
0x14001477e  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x140014786  xor     r9d, r9d; lpSecurityAttributes
0x140014789  mov     rcx, rdi; lpFileName
0x14001478c  mov     [rsp+0B0h+dwCreationDisposition], r13d; dwCreationDisposition
0x140014791  lea     edx, [r13+7Dh]; dwDesiredAccess
0x140014795  lea     r8d, [r13-2]; dwShareMode
0x140014799  call    cs:__imp_CreateFileW
0x14001479f  mov     rbx, rax
0x1400147a2  inc     rax
0x1400147a5  cmp     rax, 1
0x1400147a9  ja      short loc_140014828
0x1400147ab  call    cs:__imp_GetLastError
0x1400147b1  mov     ecx, eax
0x1400147b3  test    eax, eax
0x1400147b5  jle     short loc_1400147C0
0x1400147b7  movzx   ecx, ax
0x1400147ba  or      ecx, 80070000h
0x1400147c0  test    ecx, ecx
0x1400147c2  mov     eax, 80004005h
0x1400147c7  cmovns  ecx, eax
0x1400147ca  mov     eax, cs:dword_14007A000
0x1400147d0  cmp     eax, 2
0x1400147d3  jbe     loc_1400149FE
0x1400147d9  mov     rdx, cs:qword_14007A018
0x1400147e0  mov     rax, cs:qword_14007A010
0x1400147e7  test    al, 8
0x1400147e9  jz      loc_1400149FE
0x1400147ef  mov     rax, rdx
0x1400147f2  and     eax, 8
0x1400147f5  cmp     rax, rdx
0x1400147f8  jnz     loc_1400149FE
0x1400147fe  lea     rax, [rbp+57h+var_70]
0x140014802  mov     dword ptr [rbp+57h+var_70], ecx
0x140014805  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x14001480a  lea     rdx, word_14006F09A
0x140014811  lea     rax, [rbp+57h+var_68]
0x140014815  mov     [rbp+57h+var_68], rdi
0x140014819  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x14001481e  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x140014823  jmp     loc_1400149FE
0x140014828  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001482c  inc     rax
0x14001482f  cmp     [rdi+rax*2], r15w
0x140014834  jnz     short loc_14001482C
0x140014836  movzx   r14d, word ptr [rdi+rax*2-2]
0x14001483c  mov     rdx, rsi
0x14001483f  mov     rcx, rbx; hFile
0x140014842  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140014847  mov     edx, eax
0x140014849  test    eax, eax
0x14001484b  jns     short loc_1400148C0
0x14001484d  mov     eax, cs:dword_14007A000
0x140014853  cmp     eax, 2
0x140014856  jbe     loc_1400149FE
0x14001485c  mov     rcx, cs:qword_14007A018
0x140014863  mov     rax, cs:qword_14007A010
0x14001486a  test    al, 8
0x14001486c  jz      loc_1400149FE
0x140014872  mov     rax, rcx
0x140014875  and     eax, 8
0x140014878  cmp     rax, rcx
0x14001487b  jnz     loc_1400149FE
0x140014881  lea     rax, [rbp+57h+var_70]
0x140014885  mov     dword ptr [rbp+57h+var_70], edx
0x140014888  mov     [rbp+57h+var_40], rax
0x14001488c  lea     rdx, byte_14006F06F
0x140014893  lea     rax, [rbp+57h+var_60]
0x140014897  mov     [rbp+57h+var_38], 4
0x14001489f  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x1400148a4  lea     rcx, dword_14007A000
0x1400148ab  xor     r9d, r9d
0x1400148ae  mov     [rsp+0B0h+dwCreationDisposition], r13d
0x1400148b3  xor     r8d, r8d
0x1400148b6  call    _tlgWriteTransfer_EventWriteTransfer
0x1400148bb  jmp     loc_1400149FE
0x1400148c0  mov     r13d, 5Ch ; '\'
0x1400148c6  cmp     r14w, r13w
0x1400148ca  jnz     short loc_1400148FB
0x1400148cc  mov     rax, [rsi+8]
0x1400148d0  cmp     [rsi], rax
0x1400148d3  jz      short loc_1400148DC
0x1400148d5  cmp     r13w, [rax-2]
0x1400148da  jz      short loc_1400148FB
0x1400148dc  mov     edx, r13d
0x1400148df  mov     rcx, rsi
0x1400148e2  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1400148e7  test    al, al
0x1400148e9  jnz     short loc_1400148FB
0x1400148eb  mov     rcx, [rsi]
0x1400148ee  mov     [rsi+8], rcx
0x1400148f2  mov     [rcx], r15w
0x1400148f6  jmp     loc_1400149FE
0x1400148fb  mov     rax, [rsi]
0x1400148fe  test    rax, rax
0x140014901  jz      short loc_14001496A
0x140014903  cmp     [rax], r13w
0x140014907  jnz     short loc_14001496A
0x140014909  cmp     [rax+2], r13w
0x14001490e  jnz     short loc_14001496A
0x140014910  cmp     word ptr [rax+4], 3Fh ; '?'
0x140014915  jnz     short loc_14001496A
0x140014917  cmp     [rax+6], r13w
0x14001491c  jnz     short loc_14001496A
0x14001491e  mov     eax, cs:dword_14007A000
0x140014924  cmp     eax, 5
0x140014927  jbe     short loc_140014962
0x140014929  mov     rcx, cs:qword_14007A018
0x140014930  mov     rax, cs:qword_14007A010
0x140014937  test    al, 8
0x140014939  jz      short loc_140014962
0x14001493b  mov     rax, rcx
0x14001493e  and     eax, 8
0x140014941  cmp     rax, rcx
0x140014944  jnz     short loc_140014962
0x140014946  mov     rax, [rsi]
0x140014949  lea     rdx, byte_14006F031
0x140014950  mov     [rbp+57h+var_68], rax
0x140014954  lea     rax, [rbp+57h+var_68]
0x140014958  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x14001495d  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x140014962  mov     r14d, 4
0x140014968  jmp     short loc_14001496D
0x14001496a  mov     r14, r15
0x14001496d  mov     eax, cs:dword_14007A000
0x140014973  cmp     eax, 5
0x140014976  jbe     short loc_1400149BE
0x140014978  mov     rcx, cs:qword_14007A018
0x14001497f  mov     rax, cs:qword_14007A010
0x140014986  test    al, 8
0x140014988  jz      short loc_1400149BE
0x14001498a  mov     rax, rcx
0x14001498d  and     eax, 8
0x140014990  cmp     rax, rcx
0x140014993  jnz     short loc_1400149BE
0x140014995  mov     rax, [rsi]
0x140014998  lea     rdx, dword_14006EFEC
0x14001499f  mov     [rbp+57h+var_68], rax
0x1400149a3  lea     rax, [rbp+57h+var_68]
0x1400149a7  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x1400149ac  lea     rax, [rbp+57h+var_70]
0x1400149b0  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1400149b5  mov     [rbp+57h+var_70], rdi
0x1400149b9  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x1400149be  mov     r8, [rsi+8]
0x1400149c2  mov     rcx, rdi
0x1400149c5  sub     r8, [rsi]
0x1400149c8  mov     rdx, [rsi]
0x1400149cb  sar     r8, 1
0x1400149ce  call    cs:__imp__o__wcsnicmp
0x1400149d4  test    eax, eax
0x1400149d6  jz      short loc_1400149FE
0x1400149d8  mov     rax, [rsi]
0x1400149db  mov     rcx, rdi
0x1400149de  mov     r8, [rsi+8]
0x1400149e2  sub     r8, rax
0x1400149e5  sar     r8, 1
0x1400149e8  sub     r8, r14
0x1400149eb  lea     rdx, [rax+r14*2]
0x1400149ef  call    cs:__imp__o__wcsnicmp
0x1400149f5  mov     edi, 1
0x1400149fa  test    eax, eax
0x1400149fc  jnz     short loc_140014A01
0x1400149fe  mov     edi, r15d
0x140014a01  mov     eax, cs:dword_14007A000
0x140014a07  cmp     eax, 4
0x140014a0a  jbe     short loc_140014A51
0x140014a0c  mov     rcx, cs:qword_14007A018
0x140014a13  mov     rax, cs:qword_14007A010
0x140014a1a  test    al, 8
0x140014a1c  jz      short loc_140014A51
0x140014a1e  mov     rax, rcx
0x140014a21  and     eax, 8
0x140014a24  cmp     rax, rcx
0x140014a27  jnz     short loc_140014A51
0x140014a29  mov     rax, [rsi]
0x140014a2c  lea     rdx, word_14006EFB2
0x140014a33  mov     [rbp+57h+var_68], rax
0x140014a37  lea     rax, [rbp+57h+var_70]
0x140014a3b  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x140014a40  lea     rax, [rbp+57h+var_68]
0x140014a44  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x140014a49  mov     dword ptr [rbp+57h+var_70], edi
0x140014a4c  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x140014a51  lea     rcx, [rbx+1]
0x140014a55  cmp     rcx, 1
0x140014a59  jbe     short loc_140014A64
0x140014a5b  mov     rcx, rbx; hObject
0x140014a5e  call    cs:__imp_CloseHandle
0x140014a64  mov     eax, edi
0x140014a66  mov     rcx, [rbp+57h+var_30]
0x140014a6a  xor     rcx, rsp; StackCookie
0x140014a6d  call    __security_check_cookie
0x140014a72  lea     r11, [rsp+0B0h+var_20]
0x140014a7a  mov     rbx, [r11+40h]
0x140014a7e  mov     rsi, [r11+48h]
0x140014a82  mov     rsp, r11
0x140014a85  pop     r15
0x140014a87  pop     r14
0x140014a89  pop     r13
0x140014a8b  pop     rdi
0x140014a8c  pop     rbp
0x140014a8d  retn
```
