# XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CiXParser::CiXDocument,1024>::ParseFromFile(XmlParserGenerator::ParseDocumentFlags,wchar_t const * const,XmlParserGenerator::IParseErrorCallback *,Windows::Rtl::StopWatch *)

- ea: `0x1800a8ef8`
- end: `0x1800a93bc`
- name: `?ParseFromFile@?$AutoXpgParser@UERROR_CODE_STYLE_HRESULT@XmlParserGenerator@@UCiXDocument@CiXParser@@$0EAA@@XmlParserGenerator@@QEAAJW4ParseDocumentFlags@2@QEB_WPEAUIParseErrorCallback@2@PEAVStopWatch@Rtl@Windows@@@Z`
- size: `1220`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800a02fc`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000636c`
- `0x18000aedc`
- `0x1800497c0`
- `0x1800a8db8`
- `0x1800a8ef8`

## import_xrefs

- `ntdll!NtClose` at `0x1800a9074`
- `ntdll!NtClose` at `0x1800a90a8`
- `ntdll!NtClose` at `0x1800a9112`
- `ntdll!NtClose` at `0x1800a91f1`
- `ntdll!NtClose` at `0x1800a9350`
- `ntdll!NtClose` at `0x1800a9074`
- `ntdll!NtClose` at `0x1800a90a8`
- `ntdll!NtClose` at `0x1800a9112`
- `ntdll!NtClose` at `0x1800a91f1`
- `ntdll!NtClose` at `0x1800a9350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a928c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a92a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a92e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a938f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a928c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a92a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a92e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a938f`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800a8f9c`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800a8f9c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a901b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a901b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a8f60`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a8f60`

## string_xrefs

- `0x1800a90d1`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x1800a9153`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x1800a91b9`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x1800a9248`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x1800a92c4`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x1800a9304`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDocument,1024>::ParseFromFile`
- `0x1800a90c6`: `OneCore\internal\Base\inc\autoxmlparsergenerator.h`
- `0x1800a9148`: `OneCore\internal\Base\inc\autoxmlparsergenerator.h`
- `0x1800a91ae`: `OneCore\internal\Base\inc\autoxmlparsergenerator.h`
- `0x1800a923d`: `OneCore\internal\Base\inc\autoxmlparsergenerator.h`
- `0x1800a92b9`: `OneCore\internal\Base\inc\autoxmlparsergenerator.h`
- `0x1800a92f9`: `OneCore\internal\Base\inc\autoxmlparsergenerator.h`
- `0x1800a90e4`: `cbRead == cbToRead`
- `0x1800a9166`: `EnsureBOOL(::ReadFile(hFile, pData + cbOffset, cbToRead, &cbRead, nullptr))`

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
  __int64 v11; // rdx
  signed int LastError; // ebx
  void *v13; // rcx
  const char *v15; // rax
  const char *v16; // [rsp+48h] [rbp-51h] BYREF
  const char *v17; // [rsp+50h] [rbp-49h]
  __int64 v18; // [rsp+58h] [rbp-41h]
  const char *v19; // [rsp+60h] [rbp-39h]
  char *v20; // [rsp+68h] [rbp-31h]
  __int64 v21; // [rsp+70h] [rbp-29h]
  __int64 v22; // [rsp+78h] [rbp-21h]
  char *v23; // [rsp+80h] [rbp-19h]
  DWORD NumberOfBytesRead; // [rsp+88h] [rbp-11h] BYREF
  __int128 FileInformation; // [rsp+90h] [rbp-9h] BYREF
  __int64 v26; // [rsp+A0h] [rbp+7h]

  v22 = -2;
  v21 = a4;
  FileW = (char *)CreateFileW(a3, 0x80000000, 7u, 0, 3u, 0x8000000u, 0);
  v23 = FileW;
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
    v16 = "OneCore\\internal\\Base\\inc\\autoxmlparsergenerator.h";
    v17 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDoc"
          "ument,1024>::ParseFromFile";
    v18 = 152;
    v19 = "hFile.IsValid()";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(&v16, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return (unsigned int)LastError;
    goto LABEL_49;
  }
  FileInformation = 0;
  v26 = 0;
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
    v16 = "OneCore\\internal\\Base\\inc\\autoxmlparsergenerator.h";
    v17 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDoc"
          "ument,1024>::ParseFromFile";
    v18 = 160;
    v15 = "EnsureBOOL(::GetFileInformationByHandleEx( hFile, FileStandardInfo, &Info, sizeof(Info)))";
    goto LABEL_37;
  }
  v6 = *((_QWORD *)&FileInformation + 1);
  if ( FileInformation < 0 )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_36:
      v16 = "OneCore\\internal\\Base\\inc\\autoxmlparsergenerator.h";
      v17 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXD"
            "ocument,1024>::ParseFromFile";
      v18 = 164;
      v15 = "ullDataSize != 0xffffffffffffffffui64";
LABEL_37:
      v19 = v15;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(&v16, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
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
    v16 = "OneCore\\internal\\Base\\inc\\autoxmlparsergenerator.h";
    v17 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXDoc"
          "ument,1024>::ParseFromFile";
    v18 = 166;
    v19 = "ullDataSize != 0";
    RtlReportErrorOrigination(&v16, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942413LL);
    if ( NtClose(FileW) < 0 )
      __fastfail(7u);
    return 2147942413LL;
  }
  v7 = (char *)operator new[](*((unsigned __int64 *)&FileInformation + 1));
  v20 = v7;
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
        v16 = "OneCore\\internal\\Base\\inc\\autoxmlparsergenerator.h";
        v17 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::Ci"
              "XDocument,1024>::ParseFromFile";
        v18 = 180;
        v19 = "EnsureBOOL(::ReadFile(hFile, pData + cbOffset, cbToRead, &cbRead, nullptr))";
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        RtlReportErrorOrigination(&v16, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
LABEL_13:
        operator delete(v7);
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
      JUMPOUT(0x1800A93BBLL);
    }
    if ( NumberOfBytesRead != v10 )
    {
      v16 = "OneCore\\internal\\Base\\inc\\autoxmlparsergenerator.h";
      v17 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CiXParser::CiXD"
            "ocument,1024>::ParseFromFile";
      v18 = 181;
      v19 = "cbRead == cbToRead";
      RtlReportErrorOrigination(&v16, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147549183LL);
      operator delete(v7);
      if ( NtClose(FileW) < 0 )
        __fastfail(7u);
      return 2147549183LL;
    }
    v6 -= v10;
    if ( !v6 )
      break;
    v8 += v10;
  }
  v16 = v9;
  v17 = v9;
  v18 = (__int64)v7;
  LastError = XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CiXParser::CiXDocument,1024>::ParseFromBlob(
                a1,
                v11,
                &v16,
                v21);
  if ( LastError < 0 )
    goto LABEL_13;
  v13 = *(void **)(a1 + 56);
  *(_QWORD *)(a1 + 56) = v7;
  if ( v13 )
    operator delete(v13);
  if ( NtClose(FileW) < 0 )
    __fastfail(7u);
  return 0;
}

```

## disassembly

```asm
0x1800a8ef8  mov     rax, rsp
0x1800a8efb  push    rbp
0x1800a8efc  push    rsi
0x1800a8efd  push    rdi
0x1800a8efe  push    r12
0x1800a8f00  push    r13
0x1800a8f02  push    r14
0x1800a8f04  push    r15
0x1800a8f06  lea     rbp, [rax-57h]
0x1800a8f0a  sub     rsp, 0B0h
0x1800a8f11  mov     [rbp+4Fh+var_70], 0FFFFFFFFFFFFFFFEh
0x1800a8f19  mov     [rax+10h], rbx
0x1800a8f1d  mov     rax, cs:__security_cookie
0x1800a8f24  xor     rax, rsp
0x1800a8f27  mov     [rbp+4Fh+var_40], rax
0x1800a8f2b  mov     [rbp+4Fh+var_78], r9
0x1800a8f2f  mov     rax, r8
0x1800a8f32  mov     r13, rcx
0x1800a8f35  mov     qword ptr [rsp+30h], 0; hTemplateFile
0x1800a8f3e  mov     [rsp+0E0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800a8f46  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a8f4e  xor     r9d, r9d; lpSecurityAttributes
0x1800a8f51  lea     esi, [r9+7]
0x1800a8f55  mov     r8d, esi; dwShareMode
0x1800a8f58  mov     edx, 80000000h; dwDesiredAccess
0x1800a8f5d  mov     rcx, rax; lpFileName
0x1800a8f60  call    cs:__imp_CreateFileW
0x1800a8f67  nop     dword ptr [rax+rax+00h]
0x1800a8f6c  mov     rdi, rax
0x1800a8f6f  mov     [rbp+4Fh+var_68], rax
0x1800a8f73  lea     rcx, [rax-1]
0x1800a8f77  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800a8f7b  ja      loc_1800A92E0
0x1800a8f81  xorps   xmm0, xmm0
0x1800a8f84  xor     eax, eax
0x1800a8f86  movups  [rbp+4Fh+FileInformation], xmm0
0x1800a8f8a  mov     [rbp+4Fh+var_48], rax
0x1800a8f8e  lea     r9d, [rsi+11h]; dwBufferSize
0x1800a8f92  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x1800a8f96  lea     edx, [rsi-6]; FileInformationClass
0x1800a8f99  mov     rcx, rdi; hFile
0x1800a8f9c  call    cs:__imp_GetFileInformationByHandleEx
0x1800a8fa3  nop     dword ptr [rax+rax+00h]
0x1800a8fa8  test    eax, eax
0x1800a8faa  jz      loc_1800A928C
0x1800a8fb0  mov     rbx, qword ptr [rbp+4Fh+FileInformation+8]
0x1800a8fb4  test    rbx, rbx
0x1800a8fb7  js      loc_1800A9210
0x1800a8fbd  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a8fc1  jz      loc_1800A9210
0x1800a8fc7  test    rbx, rbx
0x1800a8fca  jz      loc_1800A91AE
0x1800a8fd0  mov     [rbp+4Fh+var_80], 0
0x1800a8fd8  mov     rcx, rbx; unsigned __int64
0x1800a8fdb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a8fe0  mov     rsi, rax
0x1800a8fe3  mov     [rbp+4Fh+var_80], rax
0x1800a8fe7  xor     r12d, r12d
0x1800a8fea  mov     r15, rbx
0x1800a8fed  mov     eax, 0FFFFFFFFh
0x1800a8ff2  cmp     rbx, rax
0x1800a8ff5  mov     r14d, ebx
0x1800a8ff8  jb      short loc_1800A8FFD
0x1800a8ffa  mov     r14d, eax
0x1800a8ffd  mov     [rbp+4Fh+NumberOfBytesRead], 0
0x1800a9004  lea     rdx, [rsi+r12]; lpBuffer
0x1800a9008  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x1800a9011  lea     r9, [rbp+4Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a9015  mov     r8d, r14d; nNumberOfBytesToRead
0x1800a9018  mov     rcx, rdi; hFile
0x1800a901b  call    cs:__imp_ReadFile
0x1800a9022  nop     dword ptr [rax+rax+00h]
0x1800a9027  test    eax, eax
0x1800a9029  jz      loc_1800A9133
0x1800a902f  cmp     [rbp+4Fh+NumberOfBytesRead], r14d
0x1800a9033  jnz     loc_1800A90C6
0x1800a9039  mov     eax, r14d
0x1800a903c  sub     rbx, rax
0x1800a903f  jz      short loc_1800A9046
0x1800a9041  add     r12, rax
0x1800a9044  jmp     short loc_1800A8FED
0x1800a9046  mov     [rbp+4Fh+var_A0], r15
0x1800a904a  mov     [rbp+4Fh+var_98], r15
0x1800a904e  mov     [rbp+4Fh+var_90], rsi
0x1800a9052  mov     r9, [rbp+4Fh+var_78]
0x1800a9056  lea     r8, [rbp+4Fh+var_A0]
0x1800a905a  mov     rcx, r13
0x1800a905d  call    ?ParseFromBlob@?$AutoXpgParser@UERROR_CODE_STYLE_HRESULT@XmlParserGenerator@@UCiXDocument@CiXParser@@$0EAA@@XmlParserGenerator@@QEAAJW4ParseDocumentFlags@2@AEBU_LBLOB@@PEAUIParseErrorCallback@2@PEAVStopWatch@Rtl@Windows@@@Z; XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CiXParser::CiXDocument,1024>::ParseFromBlob(XmlParserGenerator::ParseDocumentFlags,_LBLOB const &,XmlParserGenerator::IParseErrorCallback *,Windows::Rtl::StopWatch *)
0x1800a9062  mov     ebx, eax
0x1800a9064  test    eax, eax
0x1800a9066  jns     short loc_1800A9092
0x1800a9068  mov     rcx, rsi; Block
0x1800a906b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a9070  nop
0x1800a9071  mov     rcx, rdi; Handle
0x1800a9074  call    cs:__imp_NtClose
0x1800a907b  nop     dword ptr [rax+rax+00h]
0x1800a9080  test    eax, eax
0x1800a9082  jns     loc_1800A9365
0x1800a9088  mov     ecx, 7
0x1800a908d  jmp     loc_1800A9363
0x1800a9092  mov     rcx, [r13+38h]; Block
0x1800a9096  mov     [r13+38h], rsi
0x1800a909a  test    rcx, rcx
0x1800a909d  jz      short loc_1800A90A5
0x1800a909f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a90a4  nop
0x1800a90a5  mov     rcx, rdi; Handle
0x1800a90a8  call    cs:__imp_NtClose
0x1800a90af  nop     dword ptr [rax+rax+00h]
0x1800a90b4  test    eax, eax
0x1800a90b6  jns     short loc_1800A90BF
0x1800a90b8  mov     ecx, 7
0x1800a90bd  int     29h; Win8: RtlFailFast(ecx)
0x1800a90bf  xor     eax, eax
0x1800a90c1  jmp     loc_1800A9367
0x1800a90c6  lea     rax, aOnecoreInterna; "OneCore\\internal\\Base\\inc\\autoxmlpa"...
0x1800a90cd  mov     [rbp+4Fh+var_A0], rax
0x1800a90d1  lea     rax, aXmlparsergener_1; "XmlParserGenerator::AutoXpgParser<struc"...
0x1800a90d8  mov     [rbp+4Fh+var_98], rax
0x1800a90dc  mov     [rbp+4Fh+var_90], 0B5h
0x1800a90e4  lea     rax, aCbreadCbtoread; "cbRead == cbToRead"
0x1800a90eb  mov     [rbp+4Fh+var_88], rax
0x1800a90ef  mov     r8d, 8000FFFFh
0x1800a90f5  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800a90fc  lea     rcx, [rbp+4Fh+var_A0]
0x1800a9100  call    RtlReportErrorOrigination
0x1800a9105  nop
0x1800a9106  mov     rcx, rsi; Block
0x1800a9109  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a910e  nop
0x1800a910f  mov     rcx, rdi; Handle
0x1800a9112  call    cs:__imp_NtClose
0x1800a9119  nop     dword ptr [rax+rax+00h]
0x1800a911e  test    eax, eax
0x1800a9120  jns     short loc_1800A9129
0x1800a9122  mov     ecx, 7
0x1800a9127  int     29h; Win8: RtlFailFast(ecx)
0x1800a9129  mov     eax, 8000FFFFh
0x1800a912e  jmp     loc_1800A9367
0x1800a9133  call    cs:__imp_GetLastError
0x1800a913a  nop     dword ptr [rax+rax+00h]
0x1800a913f  test    eax, eax
0x1800a9141  jnz     short loc_1800A9196
0x1800a9143  mov     ebx, 36FDh
0x1800a9148  lea     rax, aOnecoreInterna; "OneCore\\internal\\Base\\inc\\autoxmlpa"...
0x1800a914f  mov     [rbp+4Fh+var_A0], rax
0x1800a9153  lea     rax, aXmlparsergener_1; "XmlParserGenerator::AutoXpgParser<struc"...
0x1800a915a  mov     [rbp+4Fh+var_98], rax
0x1800a915e  mov     [rbp+4Fh+var_90], 0B4h
0x1800a9166  lea     rax, aEnsureboolRead; "EnsureBOOL(::ReadFile(hFile, pData + cb"...
0x1800a916d  mov     [rbp+4Fh+var_88], rax
0x1800a9171  test    ebx, ebx
0x1800a9173  jle     short loc_1800A917E
0x1800a9175  movzx   ebx, bx
0x1800a9178  or      ebx, 80070000h
0x1800a917e  mov     r8d, ebx
0x1800a9181  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800a9188  lea     rcx, [rbp+4Fh+var_A0]
0x1800a918c  call    RtlReportErrorOrigination
0x1800a9191  jmp     loc_1800A9068
0x1800a9196  call    cs:__imp_GetLastError
0x1800a919d  nop     dword ptr [rax+rax+00h]
0x1800a91a2  mov     ebx, eax
0x1800a91a4  test    eax, eax
0x1800a91a6  jz      loc_1800A93B1
0x1800a91ac  jmp     short loc_1800A9148
0x1800a91ae  lea     rax, aOnecoreInterna; "OneCore\\internal\\Base\\inc\\autoxmlpa"...
0x1800a91b5  mov     [rbp+4Fh+var_A0], rax
0x1800a91b9  lea     rax, aXmlparsergener_1; "XmlParserGenerator::AutoXpgParser<struc"...
0x1800a91c0  mov     [rbp+4Fh+var_98], rax
0x1800a91c4  mov     [rbp+4Fh+var_90], 0A6h
0x1800a91cc  lea     rax, aUlldatasize0; "ullDataSize != 0"
0x1800a91d3  mov     [rbp+4Fh+var_88], rax
0x1800a91d7  mov     r8d, 8007000Dh
0x1800a91dd  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800a91e4  lea     rcx, [rbp+4Fh+var_A0]
0x1800a91e8  call    RtlReportErrorOrigination
0x1800a91ed  nop
0x1800a91ee  mov     rcx, rdi; Handle
0x1800a91f1  call    cs:__imp_NtClose
0x1800a91f8  nop     dword ptr [rax+rax+00h]
0x1800a91fd  test    eax, eax
0x1800a91ff  jns     short loc_1800A9206
0x1800a9201  mov     rcx, rsi
0x1800a9204  int     29h; Win8: RtlFailFast(ecx)
0x1800a9206  mov     eax, 8007000Dh
0x1800a920b  jmp     loc_1800A9367
0x1800a9210  call    cs:__imp_GetLastError
0x1800a9217  nop     dword ptr [rax+rax+00h]
0x1800a921c  test    eax, eax
0x1800a921e  jnz     short loc_1800A9227
0x1800a9220  mov     ebx, 36FDh
0x1800a9225  jmp     short loc_1800A923D
0x1800a9227  call    cs:__imp_GetLastError
0x1800a922e  nop     dword ptr [rax+rax+00h]
0x1800a9233  mov     ebx, eax
0x1800a9235  test    eax, eax
0x1800a9237  jz      loc_1800A93A6
0x1800a923d  lea     rax, aOnecoreInterna; "OneCore\\internal\\Base\\inc\\autoxmlpa"...
0x1800a9244  mov     [rbp+4Fh+var_A0], rax
0x1800a9248  lea     rax, aXmlparsergener_1; "XmlParserGenerator::AutoXpgParser<struc"...
0x1800a924f  mov     [rbp+4Fh+var_98], rax
0x1800a9253  mov     [rbp+4Fh+var_90], 0A4h
0x1800a925b  lea     rax, aUlldatasize0xf; "ullDataSize != 0xffffffffffffffffui64"
0x1800a9262  test    ebx, ebx
0x1800a9264  mov     [rbp+4Fh+var_88], rax
0x1800a9268  jle     short loc_1800A9273
0x1800a926a  movzx   ebx, bx
0x1800a926d  or      ebx, 80070000h
0x1800a9273  mov     r8d, ebx
0x1800a9276  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800a927d  lea     rcx, [rbp+4Fh+var_A0]
0x1800a9281  call    RtlReportErrorOrigination
0x1800a9286  nop
0x1800a9287  jmp     loc_1800A934D
0x1800a928c  call    cs:__imp_GetLastError
0x1800a9293  nop     dword ptr [rax+rax+00h]
0x1800a9298  test    eax, eax
0x1800a929a  jnz     short loc_1800A92A3
0x1800a929c  mov     ebx, 36FDh
0x1800a92a1  jmp     short loc_1800A92B9
0x1800a92a3  call    cs:__imp_GetLastError
0x1800a92aa  nop     dword ptr [rax+rax+00h]
0x1800a92af  mov     ebx, eax
0x1800a92b1  test    eax, eax
0x1800a92b3  jz      loc_1800A93A6
0x1800a92b9  lea     rax, aOnecoreInterna; "OneCore\\internal\\Base\\inc\\autoxmlpa"...
0x1800a92c0  mov     [rbp+4Fh+var_A0], rax
0x1800a92c4  lea     rax, aXmlparsergener_1; "XmlParserGenerator::AutoXpgParser<struc"...
0x1800a92cb  mov     [rbp+4Fh+var_98], rax
0x1800a92cf  mov     [rbp+4Fh+var_90], 0A0h
0x1800a92d7  lea     rax, aEnsureboolGetf; "EnsureBOOL(::GetFileInformationByHandle"...
0x1800a92de  jmp     short loc_1800A9262
0x1800a92e0  call    cs:__imp_GetLastError
0x1800a92e7  nop     dword ptr [rax+rax+00h]
0x1800a92ec  test    eax, eax
0x1800a92ee  jnz     loc_1800A938F
0x1800a92f4  mov     ebx, 36FDh
0x1800a92f9  lea     rax, aOnecoreInterna; "OneCore\\internal\\Base\\inc\\autoxmlpa"...
0x1800a9300  mov     [rbp+4Fh+var_A0], rax
0x1800a9304  lea     rax, aXmlparsergener_1; "XmlParserGenerator::AutoXpgParser<struc"...
0x1800a930b  mov     [rbp+4Fh+var_98], rax
0x1800a930f  mov     [rbp+4Fh+var_90], 98h
0x1800a9317  lea     rax, aHfileIsvalid; "hFile.IsValid()"
0x1800a931e  mov     [rbp+4Fh+var_88], rax
0x1800a9322  test    ebx, ebx
0x1800a9324  jle     short loc_1800A932F
0x1800a9326  movzx   ebx, bx
0x1800a9329  or      ebx, 80070000h
0x1800a932f  mov     r8d, ebx
0x1800a9332  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800a9339  lea     rcx, [rbp+4Fh+var_A0]
0x1800a933d  call    RtlReportErrorOrigination
0x1800a9342  nop
0x1800a9343  lea     rcx, [rdi-1]
0x1800a9347  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800a934b  ja      short loc_1800A9365
0x1800a934d  mov     rcx, rdi; Handle
0x1800a9350  call    cs:__imp_NtClose
0x1800a9357  nop     dword ptr [rax+rax+00h]
0x1800a935c  test    eax, eax
0x1800a935e  jns     short loc_1800A9365
0x1800a9360  mov     rcx, rsi
0x1800a9363  int     29h; Win8: RtlFailFast(ecx)
0x1800a9365  mov     eax, ebx
0x1800a9367  mov     rcx, [rbp+4Fh+var_40]
0x1800a936b  xor     rcx, rsp; StackCookie
0x1800a936e  call    __security_check_cookie
0x1800a9373  mov     rbx, [rsp+0E0h+arg_8]
0x1800a937b  add     rsp, 0B0h
0x1800a9382  pop     r15
0x1800a9384  pop     r14
0x1800a9386  pop     r13
0x1800a9388  pop     r12
0x1800a938a  pop     rdi
0x1800a938b  pop     rsi
0x1800a938c  pop     rbp
0x1800a938d  retn
0x1800a938f  call    cs:__imp_GetLastError
0x1800a9396  nop     dword ptr [rax+rax+00h]
0x1800a939b  nop
0x1800a939c  mov     ebx, eax
0x1800a939e  test    eax, eax
0x1800a93a0  jnz     loc_1800A92F9
0x1800a93a6  mov     ecx, 0C00000E5h; int
0x1800a93ab  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x1800a93b0  nop
0x1800a93b1  mov     ecx, 0C00000E5h; int
0x1800a93b6  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
