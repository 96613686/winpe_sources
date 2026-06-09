# UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x1400151b8`
- end: `0x140015579`
- name: `?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `961`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x140015580`

## callees

- `0x140001150`
- `0x1400011f4`
- `0x140001288`
- `0x140001368`
- `0x140002490`
- `0x140010594`
- `0x140014b9c`
- `0x1400151b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400154a6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400154cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400154a6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400154cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001527d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001527d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015542`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015542`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140015261`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140015261`

## pseudocode

```c
__int64 __fastcall UtilGetFinalPath(LPCWSTR lpFileName, LPCWSTR *a2, int a3, int a4)
{
  char *FileW; // rbx
  signed int LastError; // eax
  signed int v8; // ecx
  __int64 v9; // rax
  WCHAR v10; // r14
  int FinalPathByHandle; // edx
  const WCHAR *v12; // rax
  _WORD *v13; // rcx
  _WORD *v14; // rax
  __int64 v15; // r14
  int v16; // eax
  unsigned int v17; // edi
  LPCWSTR v19; // [rsp+40h] [rbp-19h] BYREF
  LPCWSTR v20; // [rsp+48h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+50h] [rbp-9h] BYREF
  LPCWSTR *v22; // [rsp+70h] [rbp+17h]
  __int64 v23; // [rsp+78h] [rbp+1Fh]

  if ( !lpFileName )
  {
    FileW = 0;
LABEL_45:
    v17 = 0;
    goto LABEL_46;
  }
  if ( (unsigned int)dword_14007E000 > 4 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
  {
    v19 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      qword_14007E018,
      (unsigned int)&word_14007306E,
      a3,
      a4,
      (__int64)&v19);
  }
  FileW = (char *)CreateFileW(lpFileName, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
    {
      LODWORD(v19) = v8;
      v20 = lpFileName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)word_140073032,
        a3,
        a4,
        (__int64)&v20,
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
    if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
    {
      LODWORD(v19) = FinalPathByHandle;
      v22 = &v19;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14007E000, (unsigned __int8 *)byte_140073007, 0, 0, 3u, &v21);
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
    if ( (unsigned int)dword_14007E000 > 5 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
    {
      v20 = *a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_14007E018,
        (unsigned int)byte_140072FC9,
        a3,
        a4,
        (__int64)&v20);
    }
    v15 = 4;
  }
  else
  {
    v15 = 0;
  }
  if ( (unsigned int)dword_14007E000 > 5 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
  {
    v20 = *a2;
    v19 = lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      qword_14007E018,
      (unsigned int)&dword_140072F84,
      a3,
      a4,
      (__int64)&v19,
      (__int64)&v20);
  }
  if ( !(unsigned int)_o__wcsnicmp(lpFileName, *a2, a2[1] - *a2) )
    goto LABEL_45;
  v16 = _o__wcsnicmp(lpFileName, &(*a2)[v15], a2[1] - *a2 - v15);
  v17 = 1;
  if ( !v16 )
    goto LABEL_45;
LABEL_46:
  if ( (unsigned int)dword_14007E000 > 4 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
  {
    v20 = *a2;
    LODWORD(v19) = v17;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      qword_14007E018,
      (unsigned int)word_140072F4A,
      a3,
      a4,
      (__int64)&v20,
      (__int64)&v19);
  }
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return v17;
}

```

## disassembly

```asm
0x1400151b8  mov     [rsp-8+arg_10], rbx
0x1400151bd  mov     [rsp-8+arg_18], rsi
0x1400151c2  push    rbp
0x1400151c3  push    rdi
0x1400151c4  push    r13
0x1400151c6  push    r14
0x1400151c8  push    r15
0x1400151ca  lea     rbp, [rsp-37h]
0x1400151cf  sub     rsp, 90h
0x1400151d6  mov     rax, cs:__security_cookie
0x1400151dd  xor     rax, rsp
0x1400151e0  mov     [rbp+57h+var_30], rax
0x1400151e4  xor     r15d, r15d
0x1400151e7  mov     rsi, rdx
0x1400151ea  mov     rdi, rcx
0x1400151ed  test    rcx, rcx
0x1400151f0  jnz     short loc_1400151FA
0x1400151f2  mov     ebx, r15d
0x1400151f5  jmp     loc_1400154E2
0x1400151fa  mov     eax, cs:dword_14007E000
0x140015200  cmp     eax, 4
0x140015203  jbe     short loc_14001523B
0x140015205  mov     rcx, cs:qword_14007E018
0x14001520c  mov     rax, cs:qword_14007E010
0x140015213  test    al, 8
0x140015215  jz      short loc_14001523B
0x140015217  mov     rax, rcx
0x14001521a  and     eax, 8
0x14001521d  cmp     rax, rcx
0x140015220  jnz     short loc_14001523B
0x140015222  lea     rax, [rbp+57h+var_70]
0x140015226  mov     [rbp+57h+var_70], rdi
0x14001522a  lea     rdx, word_14007306E
0x140015231  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x140015236  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14001523b  mov     r13d, 3
0x140015241  mov     [rsp+0B0h+hTemplateFile], r15; hTemplateFile
0x140015246  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x14001524e  xor     r9d, r9d; lpSecurityAttributes
0x140015251  mov     rcx, rdi; lpFileName
0x140015254  mov     [rsp+0B0h+dwCreationDisposition], r13d; dwCreationDisposition
0x140015259  lea     edx, [r13+7Dh]; dwDesiredAccess
0x14001525d  lea     r8d, [r13-2]; dwShareMode
0x140015261  call    cs:__imp_CreateFileW
0x140015268  nop     dword ptr [rax+rax+00h]
0x14001526d  mov     rbx, rax
0x140015270  inc     rax
0x140015273  cmp     rax, 1
0x140015277  ja      loc_140015300
0x14001527d  call    cs:__imp_GetLastError
0x140015284  nop     dword ptr [rax+rax+00h]
0x140015289  mov     ecx, eax
0x14001528b  test    eax, eax
0x14001528d  jle     short loc_140015298
0x14001528f  movzx   ecx, ax
0x140015292  or      ecx, 80070000h
0x140015298  test    ecx, ecx
0x14001529a  mov     eax, 80004005h
0x14001529f  cmovns  ecx, eax
0x1400152a2  mov     eax, cs:dword_14007E000
0x1400152a8  cmp     eax, 2
0x1400152ab  jbe     loc_1400154E2
0x1400152b1  mov     rdx, cs:qword_14007E018
0x1400152b8  mov     rax, cs:qword_14007E010
0x1400152bf  test    al, 8
0x1400152c1  jz      loc_1400154E2
0x1400152c7  mov     rax, rdx
0x1400152ca  and     eax, 8
0x1400152cd  cmp     rax, rdx
0x1400152d0  jnz     loc_1400154E2
0x1400152d6  lea     rax, [rbp+57h+var_70]
0x1400152da  mov     dword ptr [rbp+57h+var_70], ecx
0x1400152dd  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x1400152e2  lea     rdx, word_140073032
0x1400152e9  lea     rax, [rbp+57h+var_68]
0x1400152ed  mov     [rbp+57h+var_68], rdi
0x1400152f1  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1400152f6  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1400152fb  jmp     loc_1400154E2
0x140015300  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015304  inc     rax
0x140015307  cmp     [rdi+rax*2], r15w
0x14001530c  jnz     short loc_140015304
0x14001530e  movzx   r14d, word ptr [rdi+rax*2-2]
0x140015314  mov     rdx, rsi
0x140015317  mov     rcx, rbx; hFile
0x14001531a  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14001531f  mov     edx, eax
0x140015321  test    eax, eax
0x140015323  jns     short loc_140015398
0x140015325  mov     eax, cs:dword_14007E000
0x14001532b  cmp     eax, 2
0x14001532e  jbe     loc_1400154E2
0x140015334  mov     rcx, cs:qword_14007E018
0x14001533b  mov     rax, cs:qword_14007E010
0x140015342  test    al, 8
0x140015344  jz      loc_1400154E2
0x14001534a  mov     rax, rcx
0x14001534d  and     eax, 8
0x140015350  cmp     rax, rcx
0x140015353  jnz     loc_1400154E2
0x140015359  lea     rax, [rbp+57h+var_70]
0x14001535d  mov     dword ptr [rbp+57h+var_70], edx
0x140015360  mov     [rbp+57h+var_40], rax
0x140015364  lea     rdx, byte_140073007
0x14001536b  lea     rax, [rbp+57h+var_60]
0x14001536f  mov     [rbp+57h+var_38], 4
0x140015377  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x14001537c  lea     rcx, dword_14007E000
0x140015383  xor     r9d, r9d
0x140015386  mov     [rsp+0B0h+dwCreationDisposition], r13d
0x14001538b  xor     r8d, r8d
0x14001538e  call    _tlgWriteTransfer_EventWriteTransfer
0x140015393  jmp     loc_1400154E2
0x140015398  mov     r13d, 5Ch ; '\'
0x14001539e  cmp     r14w, r13w
0x1400153a2  jnz     short loc_1400153D3
0x1400153a4  mov     rax, [rsi+8]
0x1400153a8  cmp     [rsi], rax
0x1400153ab  jz      short loc_1400153B4
0x1400153ad  cmp     r13w, [rax-2]
0x1400153b2  jz      short loc_1400153D3
0x1400153b4  mov     edx, r13d
0x1400153b7  mov     rcx, rsi
0x1400153ba  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1400153bf  test    al, al
0x1400153c1  jnz     short loc_1400153D3
0x1400153c3  mov     rcx, [rsi]
0x1400153c6  mov     [rsi+8], rcx
0x1400153ca  mov     [rcx], r15w
0x1400153ce  jmp     loc_1400154E2
0x1400153d3  mov     rax, [rsi]
0x1400153d6  test    rax, rax
0x1400153d9  jz      short loc_140015442
0x1400153db  cmp     [rax], r13w
0x1400153df  jnz     short loc_140015442
0x1400153e1  cmp     [rax+2], r13w
0x1400153e6  jnz     short loc_140015442
0x1400153e8  cmp     word ptr [rax+4], 3Fh ; '?'
0x1400153ed  jnz     short loc_140015442
0x1400153ef  cmp     [rax+6], r13w
0x1400153f4  jnz     short loc_140015442
0x1400153f6  mov     eax, cs:dword_14007E000
0x1400153fc  cmp     eax, 5
0x1400153ff  jbe     short loc_14001543A
0x140015401  mov     rcx, cs:qword_14007E018
0x140015408  mov     rax, cs:qword_14007E010
0x14001540f  test    al, 8
0x140015411  jz      short loc_14001543A
0x140015413  mov     rax, rcx
0x140015416  and     eax, 8
0x140015419  cmp     rax, rcx
0x14001541c  jnz     short loc_14001543A
0x14001541e  mov     rax, [rsi]
0x140015421  lea     rdx, byte_140072FC9
0x140015428  mov     [rbp+57h+var_68], rax
0x14001542c  lea     rax, [rbp+57h+var_68]
0x140015430  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x140015435  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14001543a  mov     r14d, 4
0x140015440  jmp     short loc_140015445
0x140015442  mov     r14, r15
0x140015445  mov     eax, cs:dword_14007E000
0x14001544b  cmp     eax, 5
0x14001544e  jbe     short loc_140015496
0x140015450  mov     rcx, cs:qword_14007E018
0x140015457  mov     rax, cs:qword_14007E010
0x14001545e  test    al, 8
0x140015460  jz      short loc_140015496
0x140015462  mov     rax, rcx
0x140015465  and     eax, 8
0x140015468  cmp     rax, rcx
0x14001546b  jnz     short loc_140015496
0x14001546d  mov     rax, [rsi]
0x140015470  lea     rdx, dword_140072F84
0x140015477  mov     [rbp+57h+var_68], rax
0x14001547b  lea     rax, [rbp+57h+var_68]
0x14001547f  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x140015484  lea     rax, [rbp+57h+var_70]
0x140015488  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x14001548d  mov     [rbp+57h+var_70], rdi
0x140015491  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x140015496  mov     r8, [rsi+8]
0x14001549a  mov     rcx, rdi
0x14001549d  sub     r8, [rsi]
0x1400154a0  mov     rdx, [rsi]
0x1400154a3  sar     r8, 1
0x1400154a6  call    cs:__imp__o__wcsnicmp
0x1400154ad  nop     dword ptr [rax+rax+00h]
0x1400154b2  test    eax, eax
0x1400154b4  jz      short loc_1400154E2
0x1400154b6  mov     rax, [rsi]
0x1400154b9  mov     rcx, rdi
0x1400154bc  mov     r8, [rsi+8]
0x1400154c0  sub     r8, rax
0x1400154c3  sar     r8, 1
0x1400154c6  sub     r8, r14
0x1400154c9  lea     rdx, [rax+r14*2]
0x1400154cd  call    cs:__imp__o__wcsnicmp
0x1400154d4  nop     dword ptr [rax+rax+00h]
0x1400154d9  mov     edi, 1
0x1400154de  test    eax, eax
0x1400154e0  jnz     short loc_1400154E5
0x1400154e2  mov     edi, r15d
0x1400154e5  mov     eax, cs:dword_14007E000
0x1400154eb  cmp     eax, 4
0x1400154ee  jbe     short loc_140015535
0x1400154f0  mov     rcx, cs:qword_14007E018
0x1400154f7  mov     rax, cs:qword_14007E010
0x1400154fe  test    al, 8
0x140015500  jz      short loc_140015535
0x140015502  mov     rax, rcx
0x140015505  and     eax, 8
0x140015508  cmp     rax, rcx
0x14001550b  jnz     short loc_140015535
0x14001550d  mov     rax, [rsi]
0x140015510  lea     rdx, word_140072F4A
0x140015517  mov     [rbp+57h+var_68], rax
0x14001551b  lea     rax, [rbp+57h+var_70]
0x14001551f  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x140015524  lea     rax, [rbp+57h+var_68]
0x140015528  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x14001552d  mov     dword ptr [rbp+57h+var_70], edi
0x140015530  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x140015535  lea     rcx, [rbx+1]
0x140015539  cmp     rcx, 1
0x14001553d  jbe     short loc_14001554E
0x14001553f  mov     rcx, rbx; hObject
0x140015542  call    cs:__imp_CloseHandle
0x140015549  nop     dword ptr [rax+rax+00h]
0x14001554e  mov     eax, edi
0x140015550  mov     rcx, [rbp+57h+var_30]
0x140015554  xor     rcx, rsp; StackCookie
0x140015557  call    __security_check_cookie
0x14001555c  lea     r11, [rsp+0B0h+var_20]
0x140015564  mov     rbx, [r11+40h]
0x140015568  mov     rsi, [r11+48h]
0x14001556c  mov     rsp, r11
0x14001556f  pop     r15
0x140015571  pop     r14
0x140015573  pop     r13
0x140015575  pop     rdi
0x140015576  pop     rbp
0x140015577  retn
```
