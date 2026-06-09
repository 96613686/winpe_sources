# _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14000cfc4`
- end: `0x14000d5b0`
- name: `?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1516`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14000cc0c`

## callees

- `0x14000113c`
- `0x1400011dc`
- `0x14000126c`
- `0x14000134c`
- `0x1400023d0`
- `0x1400023f4`
- `0x140008d3c`
- `0x14000cfc4`
- `0x14000d5b8`
- `0x14000dc44`
- `0x14000ddf0`
- `0x14000de94`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000d2ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000d2ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d4b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d4b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d581`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000d1ba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000d1ba`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000d03b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000d26b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000d03b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000d26b`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathOnUnmountedVolume(void *a1, __int64 a2)
{
  char *FileW; // rbx
  DWORD FinalPathNameByHandleW; // eax
  int v5; // r8d
  int v6; // r9d
  unsigned __int64 v7; // r14
  __int64 v8; // r8
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  signed int LastError; // edi
  char *v14; // rdx
  const WCHAR *v15; // rcx
  signed int v16; // eax
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  __int16 *v20; // rdx
  DWORD v21; // eax
  __int64 v22; // rdx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  void *v28; // [rsp+40h] [rbp-C0h] BYREF
  void *v29; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v31; // [rsp+58h] [rbp-A8h]
  _WORD v32[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH lpString1; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v34; // [rsp+78h] [rbp-88h]
  _WORD v35[8]; // [rsp+80h] [rbp-80h] BYREF
  char v36[32]; // [rsp+90h] [rbp-70h] BYREF
  void **v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  WCHAR szFilePath[264]; // [rsp+C0h] [rbp-40h] BYREF

  lpFileName = v32;
  v32[0] = 0;
  v31 = v32;
  v35[0] = 0;
  lpString1 = v35;
  v34 = v35;
  FileW = 0;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(a1, szFilePath, 0x104u, 2u);
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
    {
LABEL_69:
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( (unsigned int)dword_14001A000 <= 2 || (qword_14001A010 & 8) == 0 || (qword_14001A018 & 8) != qword_14001A018 )
        goto LABEL_77;
      v14 = (char *)&word_14001617E;
LABEL_75:
      LODWORD(v28) = LastError;
      goto LABEL_76;
    }
LABEL_68:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_69;
  }
  if ( FinalPathNameByHandleW >= 0x104 )
  {
    LOWORD(LastError) = 111;
    goto LABEL_68;
  }
  if ( (unsigned int)dword_14001A000 > 4 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
  {
    v28 = szFilePath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      qword_14001A018,
      (unsigned int)&dword_14001613C,
      v5,
      v6,
      (__int64)&v28);
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( szFilePath[v8] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpString1,
                           szFilePath) )
  {
    LastError = -2147024882;
    if ( (unsigned int)dword_14001A000 > 2 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
    {
      LODWORD(v28) = -2147024882;
      v14 = (char *)&unk_140016100;
LABEL_76:
      v38 = 4;
      v37 = &v28;
      tlgWriteTransfer_EventWriteTransfer(&dword_14001A000, v14, 0, 0, 3, v36);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  LastError = UtilRegGetString(v10, v9, v11, v12, (__int64)&lpFileName, dwFlagsAndAttributes);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_14001A000 <= 2 || (qword_14001A010 & 8) == 0 || (qword_14001A018 & 8) != qword_14001A018 )
      goto LABEL_77;
    v14 = byte_1400160BD;
    goto LABEL_75;
  }
  v15 = lpFileName;
  if ( lpFileName == v31 || *(v31 - 1) != 92 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(&lpFileName) )
    {
      LastError = -2147024882;
      goto LABEL_77;
    }
    v15 = lpFileName;
  }
  FileW = (char *)CreateFileW(v15, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    v16 = GetLastError();
    LastError = v16;
    if ( v16 > 0 )
      LastError = (unsigned __int16)v16 | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( (unsigned int)dword_14001A000 <= 2 )
      goto LABEL_77;
    v19 = qword_14001A018;
    if ( (qword_14001A010 & 8) == 0 || (qword_14001A018 & 8) != qword_14001A018 )
      goto LABEL_77;
    v20 = &word_14001606E;
    goto LABEL_33;
  }
  v21 = GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 2u);
  if ( !v21 )
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
    {
LABEL_60:
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( (unsigned int)dword_14001A000 <= 2 )
        goto LABEL_77;
      v19 = qword_14001A018;
      if ( (qword_14001A010 & 8) == 0 || (qword_14001A018 & 8) != qword_14001A018 )
        goto LABEL_77;
      v20 = (__int16 *)&byte_14001601F;
LABEL_33:
      v29 = (void *)lpFileName;
      LODWORD(v28) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v19,
        (_DWORD)v20,
        v17,
        v18,
        (__int64)&v29,
        (__int64)&v28);
      goto LABEL_77;
    }
LABEL_59:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_60;
  }
  if ( v21 >= 0x104 )
  {
    LOWORD(LastError) = 111;
    goto LABEL_59;
  }
  do
    ++v7;
  while ( szFilePath[v7] );
  if ( v34 - lpString1 >= v7 && CompareStringOrdinal(lpString1, v7, szFilePath, v7, 1) == 2 )
  {
    if ( (unsigned int)dword_14001A000 > 4 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
    {
      v29 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_14001A018,
        (unsigned int)byte_140015FD9,
        v17,
        v18,
        (__int64)&v29);
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(
                            &lpString1,
                            v22,
                            v7) )
    {
      if ( (unsigned int)dword_14001A000 > 4 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
      {
        v29 = (void *)lpString1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v23,
          (unsigned int)&word_140015F56,
          v24,
          v25,
          (__int64)&v29);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpString1);
      LastError = 0;
    }
    else
    {
      LastError = -2147024882;
      if ( (unsigned int)dword_14001A000 > 2 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
      {
        LODWORD(v28) = -2147024882;
        v14 = byte_140015F9B;
        goto LABEL_76;
      }
    }
  }
  else
  {
    LastError = -2147024735;
    if ( (unsigned int)dword_14001A000 > 2 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
    {
      v29 = szFilePath;
      v28 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        qword_14001A018,
        (unsigned int)word_140015F02,
        v17,
        v18,
        (__int64)&v28,
        (__int64)&v29);
    }
  }
LABEL_77:
  if ( lpString1 != v35 )
    operator delete((void *)lpString1, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v32 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14000cfc4  mov     [rsp-8+arg_10], rbx
0x14000cfc9  push    rbp
0x14000cfca  push    rdi
0x14000cfcb  push    r12
0x14000cfcd  push    r13
0x14000cfcf  push    r14
0x14000cfd1  lea     rbp, [rsp-1E0h]
0x14000cfd9  sub     rsp, 2E0h
0x14000cfe0  mov     rax, cs:__security_cookie
0x14000cfe7  xor     rax, rsp
0x14000cfea  mov     [rbp+200h+var_30], rax
0x14000cff1  xor     r13d, r13d
0x14000cff4  lea     rax, [rsp+300h+var_2A0]
0x14000cff9  mov     [rsp+300h+lpFileName], rax
0x14000cffe  mov     r12, rdx
0x14000d001  lea     rax, [rsp+300h+var_2A0]
0x14000d006  mov     [rsp+300h+var_2A0], r13w
0x14000d00c  mov     [rsp+300h+var_2A8], rax
0x14000d011  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x14000d015  lea     rax, [rbp+200h+var_280]
0x14000d019  mov     [rbp+200h+var_280], r13w
0x14000d01e  mov     [rsp+300h+lpString1], rax
0x14000d023  lea     r9d, [r13+2]; dwFlags
0x14000d027  lea     rax, [rbp+200h+var_280]
0x14000d02b  mov     edi, 104h
0x14000d030  mov     r8d, edi; cchFilePath
0x14000d033  mov     [rsp+300h+var_288], rax
0x14000d038  mov     ebx, r13d
0x14000d03b  call    cs:__imp_GetFinalPathNameByHandleW
0x14000d041  test    eax, eax
0x14000d043  jz      loc_14000D4B9
0x14000d049  cmp     eax, edi
0x14000d04b  jnb     loc_14000D4B2
0x14000d051  mov     eax, cs:dword_14001A000
0x14000d057  cmp     eax, 4
0x14000d05a  jbe     short loc_14000D098
0x14000d05c  mov     rcx, cs:qword_14001A018
0x14000d063  mov     rax, cs:qword_14001A010
0x14000d06a  test    al, 8
0x14000d06c  jz      short loc_14000D098
0x14000d06e  mov     rax, rcx
0x14000d071  and     eax, 8
0x14000d074  cmp     rax, rcx
0x14000d077  jnz     short loc_14000D098
0x14000d079  lea     rax, [rbp+200h+szFilePath]
0x14000d07d  mov     [rsp+300h+var_2C0], rax
0x14000d082  lea     rdx, dword_14001613C
0x14000d089  lea     rax, [rsp+300h+var_2C0]
0x14000d08e  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000d093  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14000d098  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000d09c  lea     rax, [rbp+200h+szFilePath]
0x14000d0a0  mov     r8, r14
0x14000d0a3  inc     r8
0x14000d0a6  cmp     [rax+r8*2], r13w
0x14000d0ab  jnz     short loc_14000D0A3
0x14000d0ad  lea     rdx, [rbp+200h+szFilePath]
0x14000d0b1  lea     rcx, [rsp+300h+lpString1]
0x14000d0b6  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14000d0bb  test    al, al
0x14000d0bd  jnz     short loc_14000D10C
0x14000d0bf  mov     eax, cs:dword_14001A000
0x14000d0c5  mov     edi, 8007000Eh
0x14000d0ca  cmp     eax, 2
0x14000d0cd  jbe     loc_14000D53F
0x14000d0d3  mov     rcx, cs:qword_14001A018
0x14000d0da  mov     rax, cs:qword_14001A010
0x14000d0e1  test    al, 8
0x14000d0e3  jz      loc_14000D53F
0x14000d0e9  mov     rax, rcx
0x14000d0ec  and     eax, 8
0x14000d0ef  cmp     rax, rcx
0x14000d0f2  jnz     loc_14000D53F
0x14000d0f8  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x14000d100  lea     rdx, unk_140016100
0x14000d107  jmp     loc_14000D50B
0x14000d10c  lea     rax, [rsp+300h+lpFileName]
0x14000d111  mov     qword ptr [rsp+300h+dwCreationDisposition], rax; __int64
0x14000d116  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x14000d11b  mov     edi, eax
0x14000d11d  test    eax, eax
0x14000d11f  jns     short loc_14000D162
0x14000d121  mov     ecx, cs:dword_14001A000
0x14000d127  cmp     ecx, 2
0x14000d12a  jbe     loc_14000D53F
0x14000d130  mov     rax, cs:qword_14001A018
0x14000d137  mov     rcx, cs:qword_14001A010
0x14000d13e  test    cl, 8
0x14000d141  jz      loc_14000D53F
0x14000d147  mov     rcx, rax
0x14000d14a  and     ecx, 8
0x14000d14d  cmp     rcx, rax
0x14000d150  jnz     loc_14000D53F
0x14000d156  lea     rdx, byte_1400160BD
0x14000d15d  jmp     loc_14000D507
0x14000d162  mov     rcx, [rsp+300h+lpFileName]
0x14000d167  mov     rax, [rsp+300h+var_2A8]
0x14000d16c  cmp     rcx, rax
0x14000d16f  jz      short loc_14000D17C
0x14000d171  mov     edx, 5Ch ; '\'
0x14000d176  cmp     dx, [rax-2]
0x14000d17a  jz      short loc_14000D199
0x14000d17c  lea     rcx, [rsp+300h+lpFileName]
0x14000d181  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14000d186  test    al, al
0x14000d188  jnz     short loc_14000D194
0x14000d18a  mov     edi, 8007000Eh
0x14000d18f  jmp     loc_14000D53F
0x14000d194  mov     rcx, [rsp+300h+lpFileName]; lpFileName
0x14000d199  xor     r9d, r9d; lpSecurityAttributes
0x14000d19c  mov     [rsp+300h+hTemplateFile], r13; hTemplateFile
0x14000d1a1  mov     [rsp+300h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x14000d1a9  mov     edx, 80h; dwDesiredAccess
0x14000d1ae  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x14000d1b6  lea     r8d, [r9+1]; dwShareMode
0x14000d1ba  call    cs:__imp_CreateFileW
0x14000d1c0  mov     rbx, rax
0x14000d1c3  inc     rax
0x14000d1c6  cmp     rax, 1
0x14000d1ca  ja      loc_14000D256
0x14000d1d0  call    cs:__imp_GetLastError
0x14000d1d6  mov     edi, eax
0x14000d1d8  test    eax, eax
0x14000d1da  jle     short loc_14000D1E5
0x14000d1dc  movzx   edi, ax
0x14000d1df  or      edi, 80070000h
0x14000d1e5  test    edi, edi
0x14000d1e7  mov     eax, 80004005h
0x14000d1ec  cmovns  edi, eax
0x14000d1ef  mov     eax, cs:dword_14001A000
0x14000d1f5  cmp     eax, 2
0x14000d1f8  jbe     loc_14000D53F
0x14000d1fe  mov     rcx, cs:qword_14001A018
0x14000d205  mov     rax, cs:qword_14001A010
0x14000d20c  test    al, 8
0x14000d20e  jz      loc_14000D53F
0x14000d214  mov     rax, rcx
0x14000d217  and     eax, 8
0x14000d21a  cmp     rax, rcx
0x14000d21d  jnz     loc_14000D53F
0x14000d223  lea     rdx, word_14001606E
0x14000d22a  mov     rax, [rsp+300h+lpFileName]
0x14000d22f  mov     [rsp+300h+var_2B8], rax
0x14000d234  lea     rax, [rsp+300h+var_2C0]
0x14000d239  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x14000d23e  lea     rax, [rsp+300h+var_2B8]
0x14000d243  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000d248  mov     dword ptr [rsp+300h+var_2C0], edi
0x14000d24c  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x14000d251  jmp     loc_14000D53F
0x14000d256  mov     edi, 104h
0x14000d25b  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x14000d25f  mov     r8d, edi; cchFilePath
0x14000d262  mov     r9d, 2; dwFlags
0x14000d268  mov     rcx, rbx; hFile
0x14000d26b  call    cs:__imp_GetFinalPathNameByHandleW
0x14000d271  test    eax, eax
0x14000d273  jz      loc_14000D453
0x14000d279  cmp     eax, edi
0x14000d27b  jnb     loc_14000D44C
0x14000d281  lea     rax, [rbp+200h+szFilePath]
0x14000d285  inc     r14
0x14000d288  cmp     [rax+r14*2], r13w
0x14000d28d  jnz     short loc_14000D285
0x14000d28f  mov     rax, [rsp+300h+var_288]
0x14000d294  mov     rcx, [rsp+300h+lpString1]; lpString1
0x14000d299  sub     rax, rcx
0x14000d29c  sar     rax, 1
0x14000d29f  cmp     rax, r14
0x14000d2a2  jb      loc_14000D3DB
0x14000d2a8  mov     r9d, r14d; cchCount2
0x14000d2ab  mov     [rsp+300h+dwCreationDisposition], 1; bIgnoreCase
0x14000d2b3  lea     r8, [rbp+200h+szFilePath]; lpString2
0x14000d2b7  mov     edx, r14d; cchCount1
0x14000d2ba  call    cs:__imp_CompareStringOrdinal
0x14000d2c0  cmp     eax, 2
0x14000d2c3  jnz     loc_14000D3DB
0x14000d2c9  mov     eax, cs:dword_14001A000
0x14000d2cf  cmp     eax, 4
0x14000d2d2  jbe     short loc_14000D311
0x14000d2d4  mov     rcx, cs:qword_14001A018
0x14000d2db  mov     rax, cs:qword_14001A010
0x14000d2e2  test    al, 8
0x14000d2e4  jz      short loc_14000D311
0x14000d2e6  mov     rax, rcx
0x14000d2e9  and     eax, 8
0x14000d2ec  cmp     rax, rcx
0x14000d2ef  jnz     short loc_14000D311
0x14000d2f1  mov     rax, [rsp+300h+lpString1]
0x14000d2f6  lea     rdx, byte_140015FD9
0x14000d2fd  mov     [rsp+300h+var_2B8], rax
0x14000d302  lea     rax, [rsp+300h+var_2B8]
0x14000d307  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000d30c  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14000d311  mov     rax, [rsp+300h+var_2A8]
0x14000d316  lea     rcx, [rsp+300h+lpString1]
0x14000d31b  mov     r9, [rsp+300h+lpFileName]
0x14000d320  mov     r8, r14
0x14000d323  sub     rax, r9
0x14000d326  sar     rax, 1
0x14000d329  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000d32e  call    ?replace@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K0PEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x14000d333  test    al, al
0x14000d335  mov     eax, cs:dword_14001A000
0x14000d33b  jnz     short loc_14000D384
0x14000d33d  mov     edi, 8007000Eh
0x14000d342  cmp     eax, 2
0x14000d345  jbe     loc_14000D53F
0x14000d34b  mov     rcx, cs:qword_14001A018
0x14000d352  mov     rax, cs:qword_14001A010
0x14000d359  test    al, 8
0x14000d35b  jz      loc_14000D53F
0x14000d361  mov     rax, rcx
0x14000d364  and     eax, 8
0x14000d367  cmp     rax, rcx
0x14000d36a  jnz     loc_14000D53F
0x14000d370  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x14000d378  lea     rdx, byte_140015F9B
0x14000d37f  jmp     loc_14000D50B
0x14000d384  cmp     eax, 4
0x14000d387  jbe     short loc_14000D3C6
0x14000d389  mov     rdx, cs:qword_14001A018
0x14000d390  mov     rax, cs:qword_14001A010
0x14000d397  test    al, 8
0x14000d399  jz      short loc_14000D3C6
0x14000d39b  mov     rax, rdx
0x14000d39e  and     eax, 8
0x14000d3a1  cmp     rax, rdx
0x14000d3a4  jnz     short loc_14000D3C6
0x14000d3a6  mov     rax, [rsp+300h+lpString1]
0x14000d3ab  lea     rdx, word_140015F56
0x14000d3b2  mov     [rsp+300h+var_2B8], rax
0x14000d3b7  lea     rax, [rsp+300h+var_2B8]
0x14000d3bc  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000d3c1  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x14000d3c6  lea     rdx, [rsp+300h+lpString1]
0x14000d3cb  mov     rcx, r12
0x14000d3ce  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14000d3d3  mov     edi, r13d
0x14000d3d6  jmp     loc_14000D53F
0x14000d3db  mov     eax, cs:dword_14001A000
0x14000d3e1  mov     edi, 800700A1h
0x14000d3e6  cmp     eax, 2
0x14000d3e9  jbe     loc_14000D53F
0x14000d3ef  mov     rcx, cs:qword_14001A018
0x14000d3f6  mov     rax, cs:qword_14001A010
0x14000d3fd  test    al, 8
0x14000d3ff  jz      loc_14000D53F
0x14000d405  mov     rax, rcx
0x14000d408  and     eax, 8
0x14000d40b  cmp     rax, rcx
0x14000d40e  jnz     loc_14000D53F
0x14000d414  lea     rax, [rbp+200h+szFilePath]
0x14000d418  mov     [rsp+300h+var_2B8], rax
0x14000d41d  lea     rdx, word_140015F02
0x14000d424  mov     rax, [rsp+300h+lpString1]
0x14000d429  mov     [rsp+300h+var_2C0], rax
0x14000d42e  lea     rax, [rsp+300h+var_2B8]
0x14000d433  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x14000d438  lea     rax, [rsp+300h+var_2C0]
0x14000d43d  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x14000d442  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x14000d447  jmp     loc_14000D53F
0x14000d44c  mov     edi, 6Fh ; 'o'
0x14000d451  jmp     short loc_14000D45F
0x14000d453  call    cs:__imp_GetLastError
0x14000d459  mov     edi, eax
0x14000d45b  test    eax, eax
0x14000d45d  jle     short loc_14000D468
0x14000d45f  movzx   edi, di
0x14000d462  or      edi, 80070000h
0x14000d468  test    edi, edi
0x14000d46a  mov     eax, 80004005h
0x14000d46f  cmovns  edi, eax
0x14000d472  mov     eax, cs:dword_14001A000
0x14000d478  cmp     eax, 2
0x14000d47b  jbe     loc_14000D53F
0x14000d481  mov     rcx, cs:qword_14001A018
0x14000d488  mov     rax, cs:qword_14001A010
0x14000d48f  test    al, 8
0x14000d491  jz      loc_14000D53F
0x14000d497  mov     rax, rcx
0x14000d49a  and     eax, 8
0x14000d49d  cmp     rax, rcx
0x14000d4a0  jnz     loc_14000D53F
0x14000d4a6  lea     rdx, byte_14001601F
0x14000d4ad  jmp     loc_14000D22A
0x14000d4b2  mov     edi, 6Fh ; 'o'
0x14000d4b7  jmp     short loc_14000D4C5
0x14000d4b9  call    cs:__imp_GetLastError
0x14000d4bf  mov     edi, eax
0x14000d4c1  test    eax, eax
0x14000d4c3  jle     short loc_14000D4CE
0x14000d4c5  movzx   edi, di
0x14000d4c8  or      edi, 80070000h
0x14000d4ce  test    edi, edi
0x14000d4d0  mov     eax, 80004005h
0x14000d4d5  cmovns  edi, eax
0x14000d4d8  mov     eax, cs:dword_14001A000
0x14000d4de  cmp     eax, 2
  ... truncated ...
```
