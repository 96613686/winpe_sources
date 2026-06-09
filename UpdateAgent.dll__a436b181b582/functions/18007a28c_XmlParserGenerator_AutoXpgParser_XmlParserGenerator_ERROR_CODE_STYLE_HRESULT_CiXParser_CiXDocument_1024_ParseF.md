# XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CiXParser::CiXDocument,1024>::ParseFromFile(XmlParserGenerator::ParseDocumentFlags,wchar_t const * const,XmlParserGenerator::IParseErrorCallback *,Windows::Rtl::StopWatch *)

- ea: `0x18007a28c`
- end: `0x18007a755`
- name: `?ParseFromFile@?$AutoXpgParser@UERROR_CODE_STYLE_HRESULT@XmlParserGenerator@@UCiXDocument@CiXParser@@$0EAA@@XmlParserGenerator@@QEAAJW4ParseDocumentFlags@2@QEB_WPEAUIParseErrorCallback@2@PEAVStopWatch@Rtl@Windows@@@Z`
- size: `1225`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800613b4`
- `0x1800918a8`
- `0x1800f6d7c`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x1800061e0`
- `0x1800692fc`
- `0x18007a13c`
- `0x18007a28c`
- `0x1801efdc0`

## import_xrefs

- `ntdll!NtClose` at `0x18007a40d`
- `ntdll!NtClose` at `0x18007a441`
- `ntdll!NtClose` at `0x18007a4ab`
- `ntdll!NtClose` at `0x18007a58a`
- `ntdll!NtClose` at `0x18007a6e9`
- `ntdll!NtClose` at `0x18007a40d`
- `ntdll!NtClose` at `0x18007a441`
- `ntdll!NtClose` at `0x18007a4ab`
- `ntdll!NtClose` at `0x18007a58a`
- `ntdll!NtClose` at `0x18007a6e9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007a3af`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007a3af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007a2f4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007a2f4`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18007a330`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18007a330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a4cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a5a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a4cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a5a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a728`

## string_xrefs

- `0x18007a45f`: `onecore\internal\base\inc\autoxmlparsergenerator.h`
- `0x18007a4e1`: `onecore\internal\base\inc\autoxmlparsergenerator.h`
- `0x18007a547`: `onecore\internal\base\inc\autoxmlparsergenerator.h`
- `0x18007a5d6`: `onecore\internal\base\inc\autoxmlparsergenerator.h`
- `0x18007a652`: `onecore\internal\base\inc\autoxmlparsergenerator.h`
- `0x18007a692`: `onecore\internal\base\inc\autoxmlparsergenerator.h`
- `0x18007a46a`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x18007a4ec`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x18007a552`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x18007a5e1`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x18007a65d`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x18007a69d`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x18007a4ff`: `EnsureBOOL(::ReadFile(hFile, pData + cbOffset, cbToRead, &cbRead, nullptr))`
- `0x18007a47d`: `cbRead == cbToRead`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CiXParser::CiXDocument,1024>::ParseFromFile(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4)
{
  char *FileW; // rdi
  unsigned __int64 v6; // rbx
  char *v7; // rsi
  __int64 v8; // r12
  const char *v9; // r15
  DWORD v10; // r14d
  const struct std::nothrow_t *v11; // rdx
  signed int LastError; // ebx
  void *v13; // rcx
  const struct std::nothrow_t *v15; // rdx
  const char *v16; // rax
  const char *v17; // [rsp+48h] [rbp-51h] BYREF
  const char *v18; // [rsp+50h] [rbp-49h]
  __int64 v19; // [rsp+58h] [rbp-41h]
  const char *v20; // [rsp+60h] [rbp-39h]
  char *v21; // [rsp+68h] [rbp-31h]
  __int64 v22; // [rsp+70h] [rbp-29h]
  __int64 v23; // [rsp+78h] [rbp-21h]
  char *v24; // [rsp+80h] [rbp-19h]
  DWORD NumberOfBytesRead; // [rsp+88h] [rbp-11h] BYREF
  __int128 FileInformation; // [rsp+90h] [rbp-9h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+7h]

  v23 = -2;
  v22 = a4;
  FileW = (char *)CreateFileW(a3, 0x80000000, 7u, 0, 3u, 0x8000000u, 0);
  v24 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_53;
    }
    else
    {
      LastError = 14077;
    }
    v17 = "onecore\\internal\\base\\inc\\autoxmlparsergenerator.h";
    v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDoc"
          "ument,1024>::ParseFromFile";
    v19 = 152;
    v20 = "hFile.IsValid()";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return (unsigned int)LastError;
    goto LABEL_49;
  }
  FileInformation = 0;
  v27 = 0;
  if ( !GetFileInformationByHandleEx(FileW, FileStandardInfo, &FileInformation, 0x18u) )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_53;
    }
    else
    {
      LastError = 14077;
    }
    v17 = "onecore\\internal\\base\\inc\\autoxmlparsergenerator.h";
    v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDoc"
          "ument,1024>::ParseFromFile";
    v19 = 160;
    v16 = "EnsureBOOL(::GetFileInformationByHandleEx( hFile, FileStandardInfo, &Info, sizeof(Info)))";
    goto LABEL_37;
  }
  v6 = *((_QWORD *)&FileInformation + 1);
  if ( FileInformation < 0 )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_36:
      v17 = "onecore\\internal\\base\\inc\\autoxmlparsergenerator.h";
      v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXD"
            "ocument,1024>::ParseFromFile";
      v19 = 164;
      v16 = "ullDataSize != 0xffffffffffffffffui64";
LABEL_37:
      v20 = v16;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
LABEL_49:
      if ( NtClose(FileW) < 0 )
        goto LABEL_50;
      return (unsigned int)LastError;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_36;
LABEL_53:
    INTERNAL_ERROR_ACTION(-1073741595);
    goto LABEL_54;
  }
  if ( !*((_QWORD *)&FileInformation + 1) )
  {
    v17 = "onecore\\internal\\base\\inc\\autoxmlparsergenerator.h";
    v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDoc"
          "ument,1024>::ParseFromFile";
    v19 = 166;
    v20 = "ullDataSize != 0";
    RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942413LL);
    if ( NtClose(FileW) < 0 )
      __fastfail(7u);
    return 2147942413LL;
  }
  v7 = (char *)operator new[](*((unsigned __int64 *)&FileInformation + 1));
  v21 = v7;
  v8 = 0;
  v9 = (const char *)v6;
  while ( 1 )
  {
    v10 = v6;
    if ( v6 >= 0xFFFFFFFF )
      v10 = -1;
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, &v7[v8], v10, &NumberOfBytesRead, 0) )
    {
      if ( !GetLastError() )
      {
        LastError = 14077;
LABEL_25:
        v17 = "onecore\\internal\\base\\inc\\autoxmlparsergenerator.h";
        v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::Ci"
              "XDocument,1024>::ParseFromFile";
        v19 = 180;
        v20 = "EnsureBOOL(::ReadFile(hFile, pData + cbOffset, cbToRead, &cbRead, nullptr))";
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
LABEL_13:
        operator delete(v7, v11);
        if ( NtClose(FileW) < 0 )
LABEL_50:
          __fastfail(7u);
        return (unsigned int)LastError;
      }
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_25;
LABEL_54:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18007A754LL);
    }
    if ( NumberOfBytesRead != v10 )
    {
      v17 = "onecore\\internal\\base\\inc\\autoxmlparsergenerator.h";
      v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXD"
            "ocument,1024>::ParseFromFile";
      v19 = 181;
      v20 = "cbRead == cbToRead";
      RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147549183LL);
      operator delete(v7, v15);
      if ( NtClose(FileW) < 0 )
        __fastfail(7u);
      return 2147549183LL;
    }
    v6 -= v10;
    if ( !v6 )
      break;
    v8 += v10;
  }
  v17 = v9;
  v18 = v9;
  v19 = (__int64)v7;
  LastError = XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CiXParser::CiXDocument,1024>::ParseFromBlob(
                a1,
                2,
                &v17,
                v22);
  if ( LastError < 0 )
    goto LABEL_13;
  v13 = *(void **)(a1 + 56);
  *(_QWORD *)(a1 + 56) = v7;
  if ( v13 )
    operator delete(v13, v11);
  if ( NtClose(FileW) < 0 )
    __fastfail(7u);
  return 0;
}

```

## disassembly

```asm
0x18007a28c  mov     rax, rsp
0x18007a28f  push    rbp
0x18007a290  push    rsi
0x18007a291  push    rdi
0x18007a292  push    r12
0x18007a294  push    r13
0x18007a296  push    r14
0x18007a298  push    r15
0x18007a29a  lea     rbp, [rax-57h]
0x18007a29e  sub     rsp, 0B0h
0x18007a2a5  mov     [rbp+4Fh+var_70], 0FFFFFFFFFFFFFFFEh
0x18007a2ad  mov     [rax+10h], rbx
0x18007a2b1  mov     rax, cs:__security_cookie
0x18007a2b8  xor     rax, rsp
0x18007a2bb  mov     [rbp+4Fh+var_40], rax
0x18007a2bf  mov     [rbp+4Fh+var_78], r9
0x18007a2c3  mov     rax, r8
0x18007a2c6  mov     r13, rcx
0x18007a2c9  mov     qword ptr [rsp+30h], 0; hTemplateFile
0x18007a2d2  mov     [rsp+0E0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18007a2da  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18007a2e2  xor     r9d, r9d; lpSecurityAttributes
0x18007a2e5  lea     esi, [r9+7]
0x18007a2e9  mov     r8d, esi; dwShareMode
0x18007a2ec  mov     edx, 80000000h; dwDesiredAccess
0x18007a2f1  mov     rcx, rax; lpFileName
0x18007a2f4  call    cs:__imp_CreateFileW
0x18007a2fb  nop     dword ptr [rax+rax+00h]
0x18007a300  mov     rdi, rax
0x18007a303  mov     [rbp+4Fh+var_68], rax
0x18007a307  lea     rcx, [rax-1]
0x18007a30b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18007a30f  ja      loc_18007A679
0x18007a315  xorps   xmm0, xmm0
0x18007a318  xor     eax, eax
0x18007a31a  movups  [rbp+4Fh+FileInformation], xmm0
0x18007a31e  mov     [rbp+4Fh+var_48], rax
0x18007a322  lea     r9d, [rsi+11h]; dwBufferSize
0x18007a326  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x18007a32a  lea     edx, [rsi-6]; FileInformationClass
0x18007a32d  mov     rcx, rdi; hFile
0x18007a330  call    cs:__imp_GetFileInformationByHandleEx
0x18007a337  nop     dword ptr [rax+rax+00h]
0x18007a33c  test    eax, eax
0x18007a33e  jz      loc_18007A625
0x18007a344  mov     rbx, qword ptr [rbp+4Fh+FileInformation+8]
0x18007a348  test    rbx, rbx
0x18007a34b  js      loc_18007A5A9
0x18007a351  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007a355  jz      loc_18007A5A9
0x18007a35b  test    rbx, rbx
0x18007a35e  jz      loc_18007A547
0x18007a364  mov     [rbp+4Fh+var_80], 0
0x18007a36c  mov     rcx, rbx; unsigned __int64
0x18007a36f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007a374  mov     rsi, rax
0x18007a377  mov     [rbp+4Fh+var_80], rax
0x18007a37b  xor     r12d, r12d
0x18007a37e  mov     r15, rbx
0x18007a381  mov     eax, 0FFFFFFFFh
0x18007a386  cmp     rbx, rax
0x18007a389  mov     r14d, ebx
0x18007a38c  jb      short loc_18007A391
0x18007a38e  mov     r14d, eax
0x18007a391  mov     [rbp+4Fh+NumberOfBytesRead], 0
0x18007a398  lea     rdx, [rsi+r12]; lpBuffer
0x18007a39c  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x18007a3a5  lea     r9, [rbp+4Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x18007a3a9  mov     r8d, r14d; nNumberOfBytesToRead
0x18007a3ac  mov     rcx, rdi; hFile
0x18007a3af  call    cs:__imp_ReadFile
0x18007a3b6  nop     dword ptr [rax+rax+00h]
0x18007a3bb  test    eax, eax
0x18007a3bd  jz      loc_18007A4CC
0x18007a3c3  cmp     [rbp+4Fh+NumberOfBytesRead], r14d
0x18007a3c7  jnz     loc_18007A45F
0x18007a3cd  mov     eax, r14d
0x18007a3d0  sub     rbx, rax
0x18007a3d3  jz      short loc_18007A3DA
0x18007a3d5  add     r12, rax
0x18007a3d8  jmp     short loc_18007A381
0x18007a3da  mov     [rbp+4Fh+var_A0], r15
0x18007a3de  mov     [rbp+4Fh+var_98], r15
0x18007a3e2  mov     [rbp+4Fh+var_90], rsi
0x18007a3e6  mov     r9, [rbp+4Fh+var_78]
0x18007a3ea  lea     r8, [rbp+4Fh+var_A0]
0x18007a3ee  mov     edx, 2
0x18007a3f3  mov     rcx, r13
0x18007a3f6  call    ?ParseFromBlob@?$AutoXpgParser@UERROR_CODE_STYLE_HRESULT@XmlParserGenerator@@UCiXDocument@CiXParser@@$0EAA@@XmlParserGenerator@@QEAAJW4ParseDocumentFlags@2@AEBU_LBLOB@@PEAUIParseErrorCallback@2@PEAVStopWatch@Rtl@Windows@@@Z; XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CiXParser::CiXDocument,1024>::ParseFromBlob(XmlParserGenerator::ParseDocumentFlags,_LBLOB const &,XmlParserGenerator::IParseErrorCallback *,Windows::Rtl::StopWatch *)
0x18007a3fb  mov     ebx, eax
0x18007a3fd  test    eax, eax
0x18007a3ff  jns     short loc_18007A42B
0x18007a401  mov     rcx, rsi; void *
0x18007a404  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007a409  nop
0x18007a40a  mov     rcx, rdi; Handle
0x18007a40d  call    cs:__imp_NtClose
0x18007a414  nop     dword ptr [rax+rax+00h]
0x18007a419  test    eax, eax
0x18007a41b  jns     loc_18007A6FE
0x18007a421  mov     ecx, 7
0x18007a426  jmp     loc_18007A6FC
0x18007a42b  mov     rcx, [r13+38h]; void *
0x18007a42f  mov     [r13+38h], rsi
0x18007a433  test    rcx, rcx
0x18007a436  jz      short loc_18007A43E
0x18007a438  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007a43d  nop
0x18007a43e  mov     rcx, rdi; Handle
0x18007a441  call    cs:__imp_NtClose
0x18007a448  nop     dword ptr [rax+rax+00h]
0x18007a44d  test    eax, eax
0x18007a44f  jns     short loc_18007A458
0x18007a451  mov     ecx, 7
0x18007a456  int     29h; Win8: RtlFailFast(ecx)
0x18007a458  xor     eax, eax
0x18007a45a  jmp     loc_18007A700
0x18007a45f  lea     rax, aOnecoreInterna_12; "onecore\\internal\\base\\inc\\autoxmlpa"...
0x18007a466  mov     [rbp+4Fh+var_A0], rax
0x18007a46a  lea     rax, aXmlparsergener_4; "XmlParserGenerator::AutoXpgParser<struc"...
0x18007a471  mov     [rbp+4Fh+var_98], rax
0x18007a475  mov     [rbp+4Fh+var_90], 0B5h
0x18007a47d  lea     rax, aCbreadCbtoread; "cbRead == cbToRead"
0x18007a484  mov     [rbp+4Fh+var_88], rax
0x18007a488  mov     r8d, 8000FFFFh
0x18007a48e  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18007a495  lea     rcx, [rbp+4Fh+var_A0]
0x18007a499  call    RtlReportErrorOrigination
0x18007a49e  nop
0x18007a49f  mov     rcx, rsi; void *
0x18007a4a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007a4a7  nop
0x18007a4a8  mov     rcx, rdi; Handle
0x18007a4ab  call    cs:__imp_NtClose
0x18007a4b2  nop     dword ptr [rax+rax+00h]
0x18007a4b7  test    eax, eax
0x18007a4b9  jns     short loc_18007A4C2
0x18007a4bb  mov     ecx, 7
0x18007a4c0  int     29h; Win8: RtlFailFast(ecx)
0x18007a4c2  mov     eax, 8000FFFFh
0x18007a4c7  jmp     loc_18007A700
0x18007a4cc  call    cs:__imp_GetLastError
0x18007a4d3  nop     dword ptr [rax+rax+00h]
0x18007a4d8  test    eax, eax
0x18007a4da  jnz     short loc_18007A52F
0x18007a4dc  mov     ebx, 36FDh
0x18007a4e1  lea     rax, aOnecoreInterna_12; "onecore\\internal\\base\\inc\\autoxmlpa"...
0x18007a4e8  mov     [rbp+4Fh+var_A0], rax
0x18007a4ec  lea     rax, aXmlparsergener_4; "XmlParserGenerator::AutoXpgParser<struc"...
0x18007a4f3  mov     [rbp+4Fh+var_98], rax
0x18007a4f7  mov     [rbp+4Fh+var_90], 0B4h
0x18007a4ff  lea     rax, aEnsureboolRead; "EnsureBOOL(::ReadFile(hFile, pData + cb"...
0x18007a506  mov     [rbp+4Fh+var_88], rax
0x18007a50a  test    ebx, ebx
0x18007a50c  jle     short loc_18007A517
0x18007a50e  movzx   ebx, bx
0x18007a511  or      ebx, 80070000h
0x18007a517  mov     r8d, ebx
0x18007a51a  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18007a521  lea     rcx, [rbp+4Fh+var_A0]
0x18007a525  call    RtlReportErrorOrigination
0x18007a52a  jmp     loc_18007A401
0x18007a52f  call    cs:__imp_GetLastError
0x18007a536  nop     dword ptr [rax+rax+00h]
0x18007a53b  mov     ebx, eax
0x18007a53d  test    eax, eax
0x18007a53f  jz      loc_18007A74A
0x18007a545  jmp     short loc_18007A4E1
0x18007a547  lea     rax, aOnecoreInterna_12; "onecore\\internal\\base\\inc\\autoxmlpa"...
0x18007a54e  mov     [rbp+4Fh+var_A0], rax
0x18007a552  lea     rax, aXmlparsergener_4; "XmlParserGenerator::AutoXpgParser<struc"...
0x18007a559  mov     [rbp+4Fh+var_98], rax
0x18007a55d  mov     [rbp+4Fh+var_90], 0A6h
0x18007a565  lea     rax, aUlldatasize0; "ullDataSize != 0"
0x18007a56c  mov     [rbp+4Fh+var_88], rax
0x18007a570  mov     r8d, 8007000Dh
0x18007a576  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18007a57d  lea     rcx, [rbp+4Fh+var_A0]
0x18007a581  call    RtlReportErrorOrigination
0x18007a586  nop
0x18007a587  mov     rcx, rdi; Handle
0x18007a58a  call    cs:__imp_NtClose
0x18007a591  nop     dword ptr [rax+rax+00h]
0x18007a596  test    eax, eax
0x18007a598  jns     short loc_18007A59F
0x18007a59a  mov     rcx, rsi
0x18007a59d  int     29h; Win8: RtlFailFast(ecx)
0x18007a59f  mov     eax, 8007000Dh
0x18007a5a4  jmp     loc_18007A700
0x18007a5a9  call    cs:__imp_GetLastError
0x18007a5b0  nop     dword ptr [rax+rax+00h]
0x18007a5b5  test    eax, eax
0x18007a5b7  jnz     short loc_18007A5C0
0x18007a5b9  mov     ebx, 36FDh
0x18007a5be  jmp     short loc_18007A5D6
0x18007a5c0  call    cs:__imp_GetLastError
0x18007a5c7  nop     dword ptr [rax+rax+00h]
0x18007a5cc  mov     ebx, eax
0x18007a5ce  test    eax, eax
0x18007a5d0  jz      loc_18007A73F
0x18007a5d6  lea     rax, aOnecoreInterna_12; "onecore\\internal\\base\\inc\\autoxmlpa"...
0x18007a5dd  mov     [rbp+4Fh+var_A0], rax
0x18007a5e1  lea     rax, aXmlparsergener_4; "XmlParserGenerator::AutoXpgParser<struc"...
0x18007a5e8  mov     [rbp+4Fh+var_98], rax
0x18007a5ec  mov     [rbp+4Fh+var_90], 0A4h
0x18007a5f4  lea     rax, aUlldatasize0xf; "ullDataSize != 0xffffffffffffffffui64"
0x18007a5fb  test    ebx, ebx
0x18007a5fd  mov     [rbp+4Fh+var_88], rax
0x18007a601  jle     short loc_18007A60C
0x18007a603  movzx   ebx, bx
0x18007a606  or      ebx, 80070000h
0x18007a60c  mov     r8d, ebx
0x18007a60f  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18007a616  lea     rcx, [rbp+4Fh+var_A0]
0x18007a61a  call    RtlReportErrorOrigination
0x18007a61f  nop
0x18007a620  jmp     loc_18007A6E6
0x18007a625  call    cs:__imp_GetLastError
0x18007a62c  nop     dword ptr [rax+rax+00h]
0x18007a631  test    eax, eax
0x18007a633  jnz     short loc_18007A63C
0x18007a635  mov     ebx, 36FDh
0x18007a63a  jmp     short loc_18007A652
0x18007a63c  call    cs:__imp_GetLastError
0x18007a643  nop     dword ptr [rax+rax+00h]
0x18007a648  mov     ebx, eax
0x18007a64a  test    eax, eax
0x18007a64c  jz      loc_18007A73F
0x18007a652  lea     rax, aOnecoreInterna_12; "onecore\\internal\\base\\inc\\autoxmlpa"...
0x18007a659  mov     [rbp+4Fh+var_A0], rax
0x18007a65d  lea     rax, aXmlparsergener_4; "XmlParserGenerator::AutoXpgParser<struc"...
0x18007a664  mov     [rbp+4Fh+var_98], rax
0x18007a668  mov     [rbp+4Fh+var_90], 0A0h
0x18007a670  lea     rax, aEnsureboolGetf; "EnsureBOOL(::GetFileInformationByHandle"...
0x18007a677  jmp     short loc_18007A5FB
0x18007a679  call    cs:__imp_GetLastError
0x18007a680  nop     dword ptr [rax+rax+00h]
0x18007a685  test    eax, eax
0x18007a687  jnz     loc_18007A728
0x18007a68d  mov     ebx, 36FDh
0x18007a692  lea     rax, aOnecoreInterna_12; "onecore\\internal\\base\\inc\\autoxmlpa"...
0x18007a699  mov     [rbp+4Fh+var_A0], rax
0x18007a69d  lea     rax, aXmlparsergener_4; "XmlParserGenerator::AutoXpgParser<struc"...
0x18007a6a4  mov     [rbp+4Fh+var_98], rax
0x18007a6a8  mov     [rbp+4Fh+var_90], 98h
0x18007a6b0  lea     rax, aHfileIsvalid; "hFile.IsValid()"
0x18007a6b7  mov     [rbp+4Fh+var_88], rax
0x18007a6bb  test    ebx, ebx
0x18007a6bd  jle     short loc_18007A6C8
0x18007a6bf  movzx   ebx, bx
0x18007a6c2  or      ebx, 80070000h
0x18007a6c8  mov     r8d, ebx
0x18007a6cb  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18007a6d2  lea     rcx, [rbp+4Fh+var_A0]
0x18007a6d6  call    RtlReportErrorOrigination
0x18007a6db  nop
0x18007a6dc  lea     rcx, [rdi-1]
0x18007a6e0  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18007a6e4  ja      short loc_18007A6FE
0x18007a6e6  mov     rcx, rdi; Handle
0x18007a6e9  call    cs:__imp_NtClose
0x18007a6f0  nop     dword ptr [rax+rax+00h]
0x18007a6f5  test    eax, eax
0x18007a6f7  jns     short loc_18007A6FE
0x18007a6f9  mov     rcx, rsi
0x18007a6fc  int     29h; Win8: RtlFailFast(ecx)
0x18007a6fe  mov     eax, ebx
0x18007a700  mov     rcx, [rbp+4Fh+var_40]
0x18007a704  xor     rcx, rsp; StackCookie
0x18007a707  call    __security_check_cookie
0x18007a70c  mov     rbx, [rsp+0E0h+arg_8]
0x18007a714  add     rsp, 0B0h
0x18007a71b  pop     r15
0x18007a71d  pop     r14
0x18007a71f  pop     r13
0x18007a721  pop     r12
0x18007a723  pop     rdi
0x18007a724  pop     rsi
0x18007a725  pop     rbp
0x18007a726  retn
0x18007a728  call    cs:__imp_GetLastError
0x18007a72f  nop     dword ptr [rax+rax+00h]
0x18007a734  nop
0x18007a735  mov     ebx, eax
0x18007a737  test    eax, eax
0x18007a739  jnz     loc_18007A692
0x18007a73f  mov     ecx, 0C00000E5h; int
0x18007a744  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x18007a749  nop
0x18007a74a  mov     ecx, 0C00000E5h; int
0x18007a74f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
