# _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14001096c`
- end: `0x140010faa`
- name: `?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1598`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140010594`

## callees

- `0x140001150`
- `0x1400011f4`
- `0x140001288`
- `0x140001368`
- `0x140002490`
- `0x140002748`
- `0x14000ca20`
- `0x14000e9d4`
- `0x14001096c`
- `0x140012a9c`
- `0x140014b9c`
- `0x140014c4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ea6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010f74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010f74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140010c9b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140010c9b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1400109e3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140010c46`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1400109e3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140010c46`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140010b89`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140010b89`

## string_xrefs

- `0x140010ad0`: `StorePath`

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
  signed int LastError; // edi
  char *v10; // rdx
  const WCHAR *v11; // rcx
  signed int v12; // eax
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  char *v16; // rdx
  DWORD v17; // eax
  __int64 v18; // rdx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD hTemplateFile; // [rsp+30h] [rbp-D0h]
  void *v25; // [rsp+40h] [rbp-C0h] BYREF
  void *v26; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v28; // [rsp+58h] [rbp-A8h]
  _WORD v29[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWCH lpString1; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v31; // [rsp+78h] [rbp-88h]
  _WORD v32[8]; // [rsp+80h] [rbp-80h] BYREF
  char v33[32]; // [rsp+90h] [rbp-70h] BYREF
  void **v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  WCHAR szFilePath[264]; // [rsp+C0h] [rbp-40h] BYREF

  lpFileName = v29;
  v29[0] = 0;
  v28 = v29;
  v32[0] = 0;
  lpString1 = v32;
  v31 = v32;
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
      if ( (unsigned int)dword_14007E000 <= 2 || (qword_14007E010 & 8) == 0 || (qword_14007E018 & 8) != qword_14007E018 )
        goto LABEL_77;
      v10 = &byte_140072DFF;
LABEL_75:
      LODWORD(v25) = LastError;
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
  if ( (unsigned int)dword_14007E000 > 4 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
  {
    v25 = szFilePath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      qword_14007E018,
      (unsigned int)byte_140072DBD,
      v5,
      v6,
      (__int64)&v25);
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
    if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
    {
      LODWORD(v25) = -2147024882;
      v10 = byte_140072D81;
LABEL_76:
      v35 = 4;
      v34 = &v25;
      LODWORD(dwCreationDisposition) = 3;
      tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, v10, 0, 0, dwCreationDisposition, v33);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  LastError = UtilRegGetString(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\Windows Error Reporting",
                L"StorePath",
                (__int64)&lpFileName,
                0,
                hTemplateFile);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_14007E000 <= 2 || (qword_14007E010 & 8) == 0 || (qword_14007E018 & 8) != qword_14007E018 )
      goto LABEL_77;
    v10 = (char *)&word_140072D3E;
    goto LABEL_75;
  }
  v11 = lpFileName;
  if ( lpFileName == v28 || *(v28 - 1) != 92 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             &lpFileName,
                             92) )
    {
      LastError = -2147024882;
      goto LABEL_77;
    }
    v11 = lpFileName;
  }
  FileW = (char *)CreateFileW(v11, 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    v12 = GetLastError();
    LastError = v12;
    if ( v12 > 0 )
      LastError = (unsigned __int16)v12 | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    if ( (unsigned int)dword_14007E000 <= 2 )
      goto LABEL_77;
    v15 = qword_14007E018;
    if ( (qword_14007E010 & 8) == 0 || (qword_14007E018 & 8) != qword_14007E018 )
      goto LABEL_77;
    v16 = &byte_140072CEF;
    goto LABEL_33;
  }
  v17 = GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 2u);
  if ( !v17 )
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
    {
LABEL_60:
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( (unsigned int)dword_14007E000 <= 2 )
        goto LABEL_77;
      v15 = qword_14007E018;
      if ( (qword_14007E010 & 8) == 0 || (qword_14007E018 & 8) != qword_14007E018 )
        goto LABEL_77;
      v16 = (char *)&unk_140072CA0;
LABEL_33:
      v26 = (void *)lpFileName;
      LODWORD(v25) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v15,
        (_DWORD)v16,
        v13,
        v14,
        (__int64)&v26,
        (__int64)&v25);
      goto LABEL_77;
    }
LABEL_59:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_60;
  }
  if ( v17 >= 0x104 )
  {
    LOWORD(LastError) = 111;
    goto LABEL_59;
  }
  do
    ++v7;
  while ( szFilePath[v7] );
  if ( v31 - lpString1 >= v7 && CompareStringOrdinal(lpString1, v7, szFilePath, v7, 1) == 2 )
  {
    if ( (unsigned int)dword_14007E000 > 4 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
    {
      v26 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        qword_14007E018,
        (unsigned int)word_140072C5A,
        v13,
        v14,
        (__int64)&v26);
    }
    dwCreationDisposition = v28 - lpFileName;
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(
                            &lpString1,
                            v18,
                            v7) )
    {
      if ( (unsigned int)dword_14007E000 > 4 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
      {
        v26 = (void *)lpString1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v19,
          (unsigned int)&byte_140072BD7,
          v20,
          v21,
          (__int64)&v26);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpString1);
      LastError = 0;
    }
    else
    {
      LastError = -2147024882;
      if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
      {
        LODWORD(v25) = -2147024882;
        v10 = (char *)&dword_140072C1C;
        goto LABEL_76;
      }
    }
  }
  else
  {
    LastError = -2147024735;
    if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
    {
      v26 = szFilePath;
      v25 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        qword_14007E018,
        (unsigned int)byte_140072B83,
        v13,
        v14,
        (__int64)&v25,
        (__int64)&v26);
    }
  }
LABEL_77:
  if ( lpString1 != v32 )
    operator delete((void *)lpString1, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName != v29 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14001096c  mov     [rsp-8+arg_10], rbx
0x140010971  push    rbp
0x140010972  push    rdi
0x140010973  push    r12
0x140010975  push    r13
0x140010977  push    r14
0x140010979  lea     rbp, [rsp-1E0h]
0x140010981  sub     rsp, 2E0h
0x140010988  mov     rax, cs:__security_cookie
0x14001098f  xor     rax, rsp
0x140010992  mov     [rbp+200h+var_30], rax
0x140010999  xor     r13d, r13d
0x14001099c  lea     rax, [rsp+300h+var_2A0]
0x1400109a1  mov     [rsp+300h+lpFileName], rax
0x1400109a6  mov     r12, rdx
0x1400109a9  lea     rax, [rsp+300h+var_2A0]
0x1400109ae  mov     [rsp+300h+var_2A0], r13w
0x1400109b4  mov     [rsp+300h+var_2A8], rax
0x1400109b9  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x1400109bd  lea     rax, [rbp+200h+var_280]
0x1400109c1  mov     [rbp+200h+var_280], r13w
0x1400109c6  mov     [rsp+300h+lpString1], rax
0x1400109cb  lea     r9d, [r13+2]; dwFlags
0x1400109cf  lea     rax, [rbp+200h+var_280]
0x1400109d3  mov     edi, 104h
0x1400109d8  mov     r8d, edi; cchFilePath
0x1400109db  mov     [rsp+300h+var_288], rax
0x1400109e0  mov     ebx, r13d
0x1400109e3  call    cs:__imp_GetFinalPathNameByHandleW
0x1400109ea  nop     dword ptr [rax+rax+00h]
0x1400109ef  test    eax, eax
0x1400109f1  jz      loc_140010EA6
0x1400109f7  cmp     eax, edi
0x1400109f9  jnb     loc_140010E9F
0x1400109ff  mov     eax, cs:dword_14007E000
0x140010a05  cmp     eax, 4
0x140010a08  jbe     short loc_140010A46
0x140010a0a  mov     rcx, cs:qword_14007E018
0x140010a11  mov     rax, cs:qword_14007E010
0x140010a18  test    al, 8
0x140010a1a  jz      short loc_140010A46
0x140010a1c  mov     rax, rcx
0x140010a1f  and     eax, 8
0x140010a22  cmp     rax, rcx
0x140010a25  jnz     short loc_140010A46
0x140010a27  lea     rax, [rbp+200h+szFilePath]
0x140010a2b  mov     [rsp+300h+var_2C0], rax
0x140010a30  lea     rdx, byte_140072DBD
0x140010a37  lea     rax, [rsp+300h+var_2C0]
0x140010a3c  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x140010a41  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x140010a46  or      r14, 0FFFFFFFFFFFFFFFFh
0x140010a4a  lea     rax, [rbp+200h+szFilePath]
0x140010a4e  mov     r8, r14
0x140010a51  inc     r8
0x140010a54  cmp     [rax+r8*2], r13w
0x140010a59  jnz     short loc_140010A51
0x140010a5b  lea     rdx, [rbp+200h+szFilePath]
0x140010a5f  lea     rcx, [rsp+300h+lpString1]
0x140010a64  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140010a69  test    al, al
0x140010a6b  jnz     short loc_140010ABA
0x140010a6d  mov     eax, cs:dword_14007E000
0x140010a73  mov     edi, 8007000Eh
0x140010a78  cmp     eax, 2
0x140010a7b  jbe     loc_140010F32
0x140010a81  mov     rcx, cs:qword_14007E018
0x140010a88  mov     rax, cs:qword_14007E010
0x140010a8f  test    al, 8
0x140010a91  jz      loc_140010F32
0x140010a97  mov     rax, rcx
0x140010a9a  and     eax, 8
0x140010a9d  cmp     rax, rcx
0x140010aa0  jnz     loc_140010F32
0x140010aa6  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x140010aae  lea     rdx, byte_140072D81
0x140010ab5  jmp     loc_140010EFE
0x140010aba  lea     rax, [rsp+300h+lpFileName]
0x140010abf  mov     byte ptr [rsp+300h+dwFlagsAndAttributes], r13b; char
0x140010ac4  lea     r9, pwzValue
0x140010acb  mov     qword ptr [rsp+300h+dwCreationDisposition], rax; __int64
0x140010ad0  lea     r8, aStorepath; "StorePath"
0x140010ad7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010ade  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\Windows E"...
0x140010ae5  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140010aea  mov     edi, eax
0x140010aec  test    eax, eax
0x140010aee  jns     short loc_140010B31
0x140010af0  mov     ecx, cs:dword_14007E000
0x140010af6  cmp     ecx, 2
0x140010af9  jbe     loc_140010F32
0x140010aff  mov     rax, cs:qword_14007E018
0x140010b06  mov     rcx, cs:qword_14007E010
0x140010b0d  test    cl, 8
0x140010b10  jz      loc_140010F32
0x140010b16  mov     rcx, rax
0x140010b19  and     ecx, 8
0x140010b1c  cmp     rcx, rax
0x140010b1f  jnz     loc_140010F32
0x140010b25  lea     rdx, word_140072D3E
0x140010b2c  jmp     loc_140010EFA
0x140010b31  mov     rcx, [rsp+300h+lpFileName]
0x140010b36  mov     edx, 5Ch ; '\'
0x140010b3b  mov     rax, [rsp+300h+var_2A8]
0x140010b40  cmp     rcx, rax
0x140010b43  jz      short loc_140010B4B
0x140010b45  cmp     dx, [rax-2]
0x140010b49  jz      short loc_140010B68
0x140010b4b  lea     rcx, [rsp+300h+lpFileName]
0x140010b50  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140010b55  test    al, al
0x140010b57  jnz     short loc_140010B63
0x140010b59  mov     edi, 8007000Eh
0x140010b5e  jmp     loc_140010F32
0x140010b63  mov     rcx, [rsp+300h+lpFileName]; lpFileName
0x140010b68  xor     r9d, r9d; lpSecurityAttributes
0x140010b6b  mov     qword ptr [rsp+300h+hTemplateFile], r13; hTemplateFile
0x140010b70  mov     [rsp+300h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x140010b78  mov     edx, 80h; dwDesiredAccess
0x140010b7d  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x140010b85  lea     r8d, [r9+1]; dwShareMode
0x140010b89  call    cs:__imp_CreateFileW
0x140010b90  nop     dword ptr [rax+rax+00h]
0x140010b95  mov     rbx, rax
0x140010b98  inc     rax
0x140010b9b  cmp     rax, 1
0x140010b9f  ja      loc_140010C31
0x140010ba5  call    cs:__imp_GetLastError
0x140010bac  nop     dword ptr [rax+rax+00h]
0x140010bb1  mov     edi, eax
0x140010bb3  test    eax, eax
0x140010bb5  jle     short loc_140010BC0
0x140010bb7  movzx   edi, ax
0x140010bba  or      edi, 80070000h
0x140010bc0  test    edi, edi
0x140010bc2  mov     eax, 80004005h
0x140010bc7  cmovns  edi, eax
0x140010bca  mov     eax, cs:dword_14007E000
0x140010bd0  cmp     eax, 2
0x140010bd3  jbe     loc_140010F32
0x140010bd9  mov     rcx, cs:qword_14007E018
0x140010be0  mov     rax, cs:qword_14007E010
0x140010be7  test    al, 8
0x140010be9  jz      loc_140010F32
0x140010bef  mov     rax, rcx
0x140010bf2  and     eax, 8
0x140010bf5  cmp     rax, rcx
0x140010bf8  jnz     loc_140010F32
0x140010bfe  lea     rdx, byte_140072CEF
0x140010c05  mov     rax, [rsp+300h+lpFileName]
0x140010c0a  mov     [rsp+300h+var_2B8], rax
0x140010c0f  lea     rax, [rsp+300h+var_2C0]
0x140010c14  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x140010c19  lea     rax, [rsp+300h+var_2B8]
0x140010c1e  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x140010c23  mov     dword ptr [rsp+300h+var_2C0], edi
0x140010c27  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x140010c2c  jmp     loc_140010F32
0x140010c31  mov     edi, 104h
0x140010c36  lea     rdx, [rbp+200h+szFilePath]; lpszFilePath
0x140010c3a  mov     r8d, edi; cchFilePath
0x140010c3d  mov     r9d, 2; dwFlags
0x140010c43  mov     rcx, rbx; hFile
0x140010c46  call    cs:__imp_GetFinalPathNameByHandleW
0x140010c4d  nop     dword ptr [rax+rax+00h]
0x140010c52  test    eax, eax
0x140010c54  jz      loc_140010E3A
0x140010c5a  cmp     eax, edi
0x140010c5c  jnb     loc_140010E33
0x140010c62  lea     rax, [rbp+200h+szFilePath]
0x140010c66  inc     r14
0x140010c69  cmp     [rax+r14*2], r13w
0x140010c6e  jnz     short loc_140010C66
0x140010c70  mov     rax, [rsp+300h+var_288]
0x140010c75  mov     rcx, [rsp+300h+lpString1]; lpString1
0x140010c7a  sub     rax, rcx
0x140010c7d  sar     rax, 1
0x140010c80  cmp     rax, r14
0x140010c83  jb      loc_140010DC2
0x140010c89  mov     r9d, r14d; cchCount2
0x140010c8c  mov     [rsp+300h+dwCreationDisposition], 1; bIgnoreCase
0x140010c94  lea     r8, [rbp+200h+szFilePath]; lpString2
0x140010c98  mov     edx, r14d; cchCount1
0x140010c9b  call    cs:__imp_CompareStringOrdinal
0x140010ca2  nop     dword ptr [rax+rax+00h]
0x140010ca7  cmp     eax, 2
0x140010caa  jnz     loc_140010DC2
0x140010cb0  mov     eax, cs:dword_14007E000
0x140010cb6  cmp     eax, 4
0x140010cb9  jbe     short loc_140010CF8
0x140010cbb  mov     rcx, cs:qword_14007E018
0x140010cc2  mov     rax, cs:qword_14007E010
0x140010cc9  test    al, 8
0x140010ccb  jz      short loc_140010CF8
0x140010ccd  mov     rax, rcx
0x140010cd0  and     eax, 8
0x140010cd3  cmp     rax, rcx
0x140010cd6  jnz     short loc_140010CF8
0x140010cd8  mov     rax, [rsp+300h+lpString1]
0x140010cdd  lea     rdx, word_140072C5A
0x140010ce4  mov     [rsp+300h+var_2B8], rax
0x140010ce9  lea     rax, [rsp+300h+var_2B8]
0x140010cee  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x140010cf3  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x140010cf8  mov     rax, [rsp+300h+var_2A8]
0x140010cfd  lea     rcx, [rsp+300h+lpString1]
0x140010d02  mov     r9, [rsp+300h+lpFileName]
0x140010d07  mov     r8, r14
0x140010d0a  sub     rax, r9
0x140010d0d  sar     rax, 1
0x140010d10  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x140010d15  call    ?replace@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K0PEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x140010d1a  test    al, al
0x140010d1c  mov     eax, cs:dword_14007E000
0x140010d22  jnz     short loc_140010D6B
0x140010d24  mov     edi, 8007000Eh
0x140010d29  cmp     eax, 2
0x140010d2c  jbe     loc_140010F32
0x140010d32  mov     rcx, cs:qword_14007E018
0x140010d39  mov     rax, cs:qword_14007E010
0x140010d40  test    al, 8
0x140010d42  jz      loc_140010F32
0x140010d48  mov     rax, rcx
0x140010d4b  and     eax, 8
0x140010d4e  cmp     rax, rcx
0x140010d51  jnz     loc_140010F32
0x140010d57  mov     dword ptr [rsp+300h+var_2C0], 8007000Eh
0x140010d5f  lea     rdx, dword_140072C1C
0x140010d66  jmp     loc_140010EFE
0x140010d6b  cmp     eax, 4
0x140010d6e  jbe     short loc_140010DAD
0x140010d70  mov     rdx, cs:qword_14007E018
0x140010d77  mov     rax, cs:qword_14007E010
0x140010d7e  test    al, 8
0x140010d80  jz      short loc_140010DAD
0x140010d82  mov     rax, rdx
0x140010d85  and     eax, 8
0x140010d88  cmp     rax, rdx
0x140010d8b  jnz     short loc_140010DAD
0x140010d8d  mov     rax, [rsp+300h+lpString1]
0x140010d92  lea     rdx, byte_140072BD7
0x140010d99  mov     [rsp+300h+var_2B8], rax
0x140010d9e  lea     rax, [rsp+300h+var_2B8]
0x140010da3  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x140010da8  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x140010dad  lea     rdx, [rsp+300h+lpString1]
0x140010db2  mov     rcx, r12
0x140010db5  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x140010dba  mov     edi, r13d
0x140010dbd  jmp     loc_140010F32
0x140010dc2  mov     eax, cs:dword_14007E000
0x140010dc8  mov     edi, 800700A1h
0x140010dcd  cmp     eax, 2
0x140010dd0  jbe     loc_140010F32
0x140010dd6  mov     rcx, cs:qword_14007E018
0x140010ddd  mov     rax, cs:qword_14007E010
0x140010de4  test    al, 8
0x140010de6  jz      loc_140010F32
0x140010dec  mov     rax, rcx
0x140010def  and     eax, 8
0x140010df2  cmp     rax, rcx
0x140010df5  jnz     loc_140010F32
0x140010dfb  lea     rax, [rbp+200h+szFilePath]
0x140010dff  mov     [rsp+300h+var_2B8], rax
0x140010e04  lea     rdx, byte_140072B83
0x140010e0b  mov     rax, [rsp+300h+lpString1]
0x140010e10  mov     [rsp+300h+var_2C0], rax
0x140010e15  lea     rax, [rsp+300h+var_2B8]
0x140010e1a  mov     qword ptr [rsp+300h+dwFlagsAndAttributes], rax
0x140010e1f  lea     rax, [rsp+300h+var_2C0]
0x140010e24  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x140010e29  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x140010e2e  jmp     loc_140010F32
0x140010e33  mov     edi, 6Fh ; 'o'
0x140010e38  jmp     short loc_140010E4C
0x140010e3a  call    cs:__imp_GetLastError
0x140010e41  nop     dword ptr [rax+rax+00h]
0x140010e46  mov     edi, eax
0x140010e48  test    eax, eax
0x140010e4a  jle     short loc_140010E55
0x140010e4c  movzx   edi, di
0x140010e4f  or      edi, 80070000h
0x140010e55  test    edi, edi
0x140010e57  mov     eax, 80004005h
0x140010e5c  cmovns  edi, eax
0x140010e5f  mov     eax, cs:dword_14007E000
0x140010e65  cmp     eax, 2
0x140010e68  jbe     loc_140010F32
0x140010e6e  mov     rcx, cs:qword_14007E018
0x140010e75  mov     rax, cs:qword_14007E010
0x140010e7c  test    al, 8
0x140010e7e  jz      loc_140010F32
0x140010e84  mov     rax, rcx
0x140010e87  and     eax, 8
0x140010e8a  cmp     rax, rcx
0x140010e8d  jnz     loc_140010F32
0x140010e93  lea     rdx, unk_140072CA0
0x140010e9a  jmp     loc_140010C05
0x140010e9f  mov     edi, 6Fh ; 'o'
0x140010ea4  jmp     short loc_140010EB8
  ... truncated ...
```
