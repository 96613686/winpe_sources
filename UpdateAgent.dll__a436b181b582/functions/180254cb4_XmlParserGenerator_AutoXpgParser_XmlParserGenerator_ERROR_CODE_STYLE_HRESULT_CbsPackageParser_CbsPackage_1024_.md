# XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CbsPackageParser::CbsPackage,1024>::ParseFromFile(XmlParserGenerator::ParseDocumentFlags,wchar_t const * const,XmlParserGenerator::IParseErrorCallback *,Windows::Rtl::StopWatch *)

- ea: `0x180254cb4`
- end: `0x180255170`
- name: `?ParseFromFile@?$AutoXpgParser@UERROR_CODE_STYLE_HRESULT@XmlParserGenerator@@UCbsPackage@CbsPackageParser@@$0EAA@@XmlParserGenerator@@QEAAJW4ParseDocumentFlags@2@QEB_WPEAUIParseErrorCallback@2@PEAVStopWatch@Rtl@Windows@@@Z`
- size: `1212`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180253a04`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x1800061e0`
- `0x1800692fc`
- `0x1801efdc0`
- `0x180254b70`
- `0x180254cb4`

## import_xrefs

- `ntdll!NtClose` at `0x180254e28`
- `ntdll!NtClose` at `0x180254e5c`
- `ntdll!NtClose` at `0x180254ec6`
- `ntdll!NtClose` at `0x180254fa5`
- `ntdll!NtClose` at `0x180255104`
- `ntdll!NtClose` at `0x180254e28`
- `ntdll!NtClose` at `0x180254e5c`
- `ntdll!NtClose` at `0x180254ec6`
- `ntdll!NtClose` at `0x180254fa5`
- `ntdll!NtClose` at `0x180255104`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180254dd3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180254dd3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180254d18`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180254d18`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180254d54`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180254d54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180254ee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180254f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180254fc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180254fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180255040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180255057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180255094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180255143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180254ee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180254f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180254fc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180254fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180255040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180255057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180255094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180255143`

## string_xrefs

- `0x180254f1a`: `EnsureBOOL(::ReadFile(hFile, pData + cbOffset, cbToRead, &cbRead, nullptr))`
- `0x180254e98`: `cbRead == cbToRead`
- `0x180254e7a`: `OneCore\Internal\Base\inc\autoxmlparsergenerator.h`
- `0x180254efc`: `OneCore\Internal\Base\inc\autoxmlparsergenerator.h`
- `0x180254f62`: `OneCore\Internal\Base\inc\autoxmlparsergenerator.h`
- `0x180254ff1`: `OneCore\Internal\Base\inc\autoxmlparsergenerator.h`
- `0x18025506d`: `OneCore\Internal\Base\inc\autoxmlparsergenerator.h`
- `0x1802550ad`: `OneCore\Internal\Base\inc\autoxmlparsergenerator.h`
- `0x180254e85`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParser::CbsPackage,1024>::ParseFromFile`
- `0x180254f07`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParser::CbsPackage,1024>::ParseFromFile`
- `0x180254f6d`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParser::CbsPackage,1024>::ParseFromFile`
- `0x180254ffc`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParser::CbsPackage,1024>::ParseFromFile`
- `0x180255078`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParser::CbsPackage,1024>::ParseFromFile`
- `0x1802550b8`: `XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParser::CbsPackage,1024>::ParseFromFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CbsPackageParser::CbsPackage,1024>::ParseFromFile(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3)
{
  char *FileW; // rdi
  unsigned __int64 v5; // rbx
  char *v6; // rsi
  __int64 v7; // r12
  const char *v8; // r15
  DWORD v9; // r14d
  __int64 v10; // rdx
  const struct std::nothrow_t *v11; // rdx
  signed int LastError; // ebx
  void *v13; // rcx
  const struct std::nothrow_t *v15; // rdx
  const char *v16; // rax
  const char *v17; // [rsp+48h] [rbp-41h] BYREF
  const char *v18; // [rsp+50h] [rbp-39h]
  __int64 v19; // [rsp+58h] [rbp-31h]
  const char *v20; // [rsp+60h] [rbp-29h]
  char *v21; // [rsp+68h] [rbp-21h]
  __int64 v22; // [rsp+70h] [rbp-19h]
  char *v23; // [rsp+78h] [rbp-11h]
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp-9h] BYREF
  __int128 FileInformation; // [rsp+88h] [rbp-1h] BYREF
  __int64 v26; // [rsp+98h] [rbp+Fh]

  v22 = -2;
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
    v17 = "OneCore\\Internal\\Base\\inc\\autoxmlparsergenerator.h";
    v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParser:"
          ":CbsPackage,1024>::ParseFromFile";
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
    v17 = "OneCore\\Internal\\Base\\inc\\autoxmlparsergenerator.h";
    v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParser:"
          ":CbsPackage,1024>::ParseFromFile";
    v19 = 160;
    v16 = "EnsureBOOL(::GetFileInformationByHandleEx( hFile, FileStandardInfo, &Info, sizeof(Info)))";
    goto LABEL_37;
  }
  v5 = *((_QWORD *)&FileInformation + 1);
  if ( FileInformation < 0 )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_36:
      v17 = "OneCore\\Internal\\Base\\inc\\autoxmlparsergenerator.h";
      v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParse"
            "r::CbsPackage,1024>::ParseFromFile";
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
    v17 = "OneCore\\Internal\\Base\\inc\\autoxmlparsergenerator.h";
    v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParser:"
          ":CbsPackage,1024>::ParseFromFile";
    v19 = 166;
    v20 = "ullDataSize != 0";
    RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942413LL);
    if ( NtClose(FileW) < 0 )
      __fastfail(7u);
    return 2147942413LL;
  }
  v6 = (char *)operator new[](*((unsigned __int64 *)&FileInformation + 1));
  v21 = v6;
  v7 = 0;
  v8 = (const char *)v5;
  while ( 1 )
  {
    v9 = v5;
    if ( v5 >= 0xFFFFFFFF )
      v9 = -1;
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, &v6[v7], v9, &NumberOfBytesRead, 0) )
    {
      if ( !GetLastError() )
      {
        LastError = 14077;
LABEL_25:
        v17 = "OneCore\\Internal\\Base\\inc\\autoxmlparsergenerator.h";
        v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackagePar"
              "ser::CbsPackage,1024>::ParseFromFile";
        v19 = 180;
        v20 = "EnsureBOOL(::ReadFile(hFile, pData + cbOffset, cbToRead, &cbRead, nullptr))";
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
LABEL_13:
        operator delete(v6, v11);
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
      JUMPOUT(0x18025516FLL);
    }
    if ( NumberOfBytesRead != v9 )
    {
      v17 = "OneCore\\Internal\\Base\\inc\\autoxmlparsergenerator.h";
      v18 = "XmlParserGenerator::AutoXpgParser<struct XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,struct CbsPackageParse"
            "r::CbsPackage,1024>::ParseFromFile";
      v19 = 181;
      v20 = "cbRead == cbToRead";
      RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147549183LL);
      operator delete(v6, v15);
      if ( NtClose(FileW) < 0 )
        __fastfail(7u);
      return 2147549183LL;
    }
    v5 -= v9;
    if ( !v5 )
      break;
    v7 += v9;
  }
  v17 = v8;
  v18 = v8;
  v19 = (__int64)v6;
  LastError = XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CbsPackageParser::CbsPackage,1024>::ParseFromBlob(
                a1,
                v10,
                &v17);
  if ( LastError < 0 )
    goto LABEL_13;
  v13 = *(void **)(a1 + 56);
  *(_QWORD *)(a1 + 56) = v6;
  if ( v13 )
    operator delete(v13, v11);
  if ( NtClose(FileW) < 0 )
    __fastfail(7u);
  return 0;
}

```

## disassembly

```asm
0x180254cb4  mov     rax, rsp
0x180254cb7  push    rbp
0x180254cb8  push    rsi
0x180254cb9  push    rdi
0x180254cba  push    r12
0x180254cbc  push    r13
0x180254cbe  push    r14
0x180254cc0  push    r15
0x180254cc2  lea     rbp, [rax-57h]
0x180254cc6  sub     rsp, 0A0h
0x180254ccd  mov     [rbp+4Fh+var_68], 0FFFFFFFFFFFFFFFEh
0x180254cd5  mov     [rax+10h], rbx
0x180254cd9  mov     rax, cs:__security_cookie
0x180254ce0  xor     rax, rsp
0x180254ce3  mov     [rbp+4Fh+var_38], rax
0x180254ce7  mov     rax, r8
0x180254cea  mov     r13, rcx
0x180254ced  mov     qword ptr [rsp+30h], 0; hTemplateFile
0x180254cf6  mov     [rsp+0D0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180254cfe  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180254d06  xor     r9d, r9d; lpSecurityAttributes
0x180254d09  lea     esi, [r9+7]
0x180254d0d  mov     r8d, esi; dwShareMode
0x180254d10  mov     edx, 80000000h; dwDesiredAccess
0x180254d15  mov     rcx, rax; lpFileName
0x180254d18  call    cs:__imp_CreateFileW
0x180254d1f  nop     dword ptr [rax+rax+00h]
0x180254d24  mov     rdi, rax
0x180254d27  mov     [rbp+4Fh+var_60], rax
0x180254d2b  lea     rcx, [rax-1]
0x180254d2f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180254d33  ja      loc_180255094
0x180254d39  xorps   xmm0, xmm0
0x180254d3c  xor     eax, eax
0x180254d3e  movups  [rbp+4Fh+FileInformation], xmm0
0x180254d42  mov     [rbp+4Fh+var_40], rax
0x180254d46  lea     r9d, [rsi+11h]; dwBufferSize
0x180254d4a  lea     r8, [rbp+4Fh+FileInformation]; lpFileInformation
0x180254d4e  lea     edx, [rsi-6]; FileInformationClass
0x180254d51  mov     rcx, rdi; hFile
0x180254d54  call    cs:__imp_GetFileInformationByHandleEx
0x180254d5b  nop     dword ptr [rax+rax+00h]
0x180254d60  test    eax, eax
0x180254d62  jz      loc_180255040
0x180254d68  mov     rbx, qword ptr [rbp+4Fh+FileInformation+8]
0x180254d6c  test    rbx, rbx
0x180254d6f  js      loc_180254FC4
0x180254d75  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180254d79  jz      loc_180254FC4
0x180254d7f  test    rbx, rbx
0x180254d82  jz      loc_180254F62
0x180254d88  mov     [rbp+4Fh+var_70], 0
0x180254d90  mov     rcx, rbx; unsigned __int64
0x180254d93  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180254d98  mov     rsi, rax
0x180254d9b  mov     [rbp+4Fh+var_70], rax
0x180254d9f  xor     r12d, r12d
0x180254da2  mov     r15, rbx
0x180254da5  mov     eax, 0FFFFFFFFh
0x180254daa  cmp     rbx, rax
0x180254dad  mov     r14d, ebx
0x180254db0  jb      short loc_180254DB5
0x180254db2  mov     r14d, eax
0x180254db5  mov     [rbp+4Fh+NumberOfBytesRead], 0
0x180254dbc  lea     rdx, [rsi+r12]; lpBuffer
0x180254dc0  mov     qword ptr [rsp+0D0h+dwCreationDisposition], 0; lpOverlapped
0x180254dc9  lea     r9, [rbp+4Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x180254dcd  mov     r8d, r14d; nNumberOfBytesToRead
0x180254dd0  mov     rcx, rdi; hFile
0x180254dd3  call    cs:__imp_ReadFile
0x180254dda  nop     dword ptr [rax+rax+00h]
0x180254ddf  test    eax, eax
0x180254de1  jz      loc_180254EE7
0x180254de7  cmp     [rbp+4Fh+NumberOfBytesRead], r14d
0x180254deb  jnz     loc_180254E7A
0x180254df1  mov     eax, r14d
0x180254df4  sub     rbx, rax
0x180254df7  jz      short loc_180254DFE
0x180254df9  add     r12, rax
0x180254dfc  jmp     short loc_180254DA5
0x180254dfe  mov     [rbp+4Fh+var_90], r15
0x180254e02  mov     [rbp+4Fh+var_88], r15
0x180254e06  mov     [rbp+4Fh+var_80], rsi
0x180254e0a  lea     r8, [rbp+4Fh+var_90]
0x180254e0e  mov     rcx, r13
0x180254e11  call    ?ParseFromBlob@?$AutoXpgParser@UERROR_CODE_STYLE_HRESULT@XmlParserGenerator@@UCbsPackage@CbsPackageParser@@$0EAA@@XmlParserGenerator@@QEAAJW4ParseDocumentFlags@2@AEBU_LBLOB@@PEAUIParseErrorCallback@2@PEAVStopWatch@Rtl@Windows@@@Z; XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CbsPackageParser::CbsPackage,1024>::ParseFromBlob(XmlParserGenerator::ParseDocumentFlags,_LBLOB const &,XmlParserGenerator::IParseErrorCallback *,Windows::Rtl::StopWatch *)
0x180254e16  mov     ebx, eax
0x180254e18  test    eax, eax
0x180254e1a  jns     short loc_180254E46
0x180254e1c  mov     rcx, rsi; void *
0x180254e1f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180254e24  nop
0x180254e25  mov     rcx, rdi; Handle
0x180254e28  call    cs:__imp_NtClose
0x180254e2f  nop     dword ptr [rax+rax+00h]
0x180254e34  test    eax, eax
0x180254e36  jns     loc_180255119
0x180254e3c  mov     ecx, 7
0x180254e41  jmp     loc_180255117
0x180254e46  mov     rcx, [r13+38h]; void *
0x180254e4a  mov     [r13+38h], rsi
0x180254e4e  test    rcx, rcx
0x180254e51  jz      short loc_180254E59
0x180254e53  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180254e58  nop
0x180254e59  mov     rcx, rdi; Handle
0x180254e5c  call    cs:__imp_NtClose
0x180254e63  nop     dword ptr [rax+rax+00h]
0x180254e68  test    eax, eax
0x180254e6a  jns     short loc_180254E73
0x180254e6c  mov     ecx, 7
0x180254e71  int     29h; Win8: RtlFailFast(ecx)
0x180254e73  xor     eax, eax
0x180254e75  jmp     loc_18025511B
0x180254e7a  lea     rax, aOnecoreInterna_0; "OneCore\\Internal\\Base\\inc\\autoxmlpa"...
0x180254e81  mov     [rbp+4Fh+var_90], rax
0x180254e85  lea     rax, aXmlparsergener_2; "XmlParserGenerator::AutoXpgParser<struc"...
0x180254e8c  mov     [rbp+4Fh+var_88], rax
0x180254e90  mov     [rbp+4Fh+var_80], 0B5h
0x180254e98  lea     rax, aCbreadCbtoread; "cbRead == cbToRead"
0x180254e9f  mov     [rbp+4Fh+var_78], rax
0x180254ea3  mov     r8d, 8000FFFFh
0x180254ea9  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180254eb0  lea     rcx, [rbp+4Fh+var_90]
0x180254eb4  call    RtlReportErrorOrigination
0x180254eb9  nop
0x180254eba  mov     rcx, rsi; void *
0x180254ebd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180254ec2  nop
0x180254ec3  mov     rcx, rdi; Handle
0x180254ec6  call    cs:__imp_NtClose
0x180254ecd  nop     dword ptr [rax+rax+00h]
0x180254ed2  test    eax, eax
0x180254ed4  jns     short loc_180254EDD
0x180254ed6  mov     ecx, 7
0x180254edb  int     29h; Win8: RtlFailFast(ecx)
0x180254edd  mov     eax, 8000FFFFh
0x180254ee2  jmp     loc_18025511B
0x180254ee7  call    cs:__imp_GetLastError
0x180254eee  nop     dword ptr [rax+rax+00h]
0x180254ef3  test    eax, eax
0x180254ef5  jnz     short loc_180254F4A
0x180254ef7  mov     ebx, 36FDh
0x180254efc  lea     rax, aOnecoreInterna_0; "OneCore\\Internal\\Base\\inc\\autoxmlpa"...
0x180254f03  mov     [rbp+4Fh+var_90], rax
0x180254f07  lea     rax, aXmlparsergener_2; "XmlParserGenerator::AutoXpgParser<struc"...
0x180254f0e  mov     [rbp+4Fh+var_88], rax
0x180254f12  mov     [rbp+4Fh+var_80], 0B4h
0x180254f1a  lea     rax, aEnsureboolRead; "EnsureBOOL(::ReadFile(hFile, pData + cb"...
0x180254f21  mov     [rbp+4Fh+var_78], rax
0x180254f25  test    ebx, ebx
0x180254f27  jle     short loc_180254F32
0x180254f29  movzx   ebx, bx
0x180254f2c  or      ebx, 80070000h
0x180254f32  mov     r8d, ebx
0x180254f35  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180254f3c  lea     rcx, [rbp+4Fh+var_90]
0x180254f40  call    RtlReportErrorOrigination
0x180254f45  jmp     loc_180254E1C
0x180254f4a  call    cs:__imp_GetLastError
0x180254f51  nop     dword ptr [rax+rax+00h]
0x180254f56  mov     ebx, eax
0x180254f58  test    eax, eax
0x180254f5a  jz      loc_180255165
0x180254f60  jmp     short loc_180254EFC
0x180254f62  lea     rax, aOnecoreInterna_0; "OneCore\\Internal\\Base\\inc\\autoxmlpa"...
0x180254f69  mov     [rbp+4Fh+var_90], rax
0x180254f6d  lea     rax, aXmlparsergener_2; "XmlParserGenerator::AutoXpgParser<struc"...
0x180254f74  mov     [rbp+4Fh+var_88], rax
0x180254f78  mov     [rbp+4Fh+var_80], 0A6h
0x180254f80  lea     rax, aUlldatasize0; "ullDataSize != 0"
0x180254f87  mov     [rbp+4Fh+var_78], rax
0x180254f8b  mov     r8d, 8007000Dh
0x180254f91  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180254f98  lea     rcx, [rbp+4Fh+var_90]
0x180254f9c  call    RtlReportErrorOrigination
0x180254fa1  nop
0x180254fa2  mov     rcx, rdi; Handle
0x180254fa5  call    cs:__imp_NtClose
0x180254fac  nop     dword ptr [rax+rax+00h]
0x180254fb1  test    eax, eax
0x180254fb3  jns     short loc_180254FBA
0x180254fb5  mov     rcx, rsi
0x180254fb8  int     29h; Win8: RtlFailFast(ecx)
0x180254fba  mov     eax, 8007000Dh
0x180254fbf  jmp     loc_18025511B
0x180254fc4  call    cs:__imp_GetLastError
0x180254fcb  nop     dword ptr [rax+rax+00h]
0x180254fd0  test    eax, eax
0x180254fd2  jnz     short loc_180254FDB
0x180254fd4  mov     ebx, 36FDh
0x180254fd9  jmp     short loc_180254FF1
0x180254fdb  call    cs:__imp_GetLastError
0x180254fe2  nop     dword ptr [rax+rax+00h]
0x180254fe7  mov     ebx, eax
0x180254fe9  test    eax, eax
0x180254feb  jz      loc_18025515A
0x180254ff1  lea     rax, aOnecoreInterna_0; "OneCore\\Internal\\Base\\inc\\autoxmlpa"...
0x180254ff8  mov     [rbp+4Fh+var_90], rax
0x180254ffc  lea     rax, aXmlparsergener_2; "XmlParserGenerator::AutoXpgParser<struc"...
0x180255003  mov     [rbp+4Fh+var_88], rax
0x180255007  mov     [rbp+4Fh+var_80], 0A4h
0x18025500f  lea     rax, aUlldatasize0xf; "ullDataSize != 0xffffffffffffffffui64"
0x180255016  test    ebx, ebx
0x180255018  mov     [rbp+4Fh+var_78], rax
0x18025501c  jle     short loc_180255027
0x18025501e  movzx   ebx, bx
0x180255021  or      ebx, 80070000h
0x180255027  mov     r8d, ebx
0x18025502a  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180255031  lea     rcx, [rbp+4Fh+var_90]
0x180255035  call    RtlReportErrorOrigination
0x18025503a  nop
0x18025503b  jmp     loc_180255101
0x180255040  call    cs:__imp_GetLastError
0x180255047  nop     dword ptr [rax+rax+00h]
0x18025504c  test    eax, eax
0x18025504e  jnz     short loc_180255057
0x180255050  mov     ebx, 36FDh
0x180255055  jmp     short loc_18025506D
0x180255057  call    cs:__imp_GetLastError
0x18025505e  nop     dword ptr [rax+rax+00h]
0x180255063  mov     ebx, eax
0x180255065  test    eax, eax
0x180255067  jz      loc_18025515A
0x18025506d  lea     rax, aOnecoreInterna_0; "OneCore\\Internal\\Base\\inc\\autoxmlpa"...
0x180255074  mov     [rbp+4Fh+var_90], rax
0x180255078  lea     rax, aXmlparsergener_2; "XmlParserGenerator::AutoXpgParser<struc"...
0x18025507f  mov     [rbp+4Fh+var_88], rax
0x180255083  mov     [rbp+4Fh+var_80], 0A0h
0x18025508b  lea     rax, aEnsureboolGetf; "EnsureBOOL(::GetFileInformationByHandle"...
0x180255092  jmp     short loc_180255016
0x180255094  call    cs:__imp_GetLastError
0x18025509b  nop     dword ptr [rax+rax+00h]
0x1802550a0  test    eax, eax
0x1802550a2  jnz     loc_180255143
0x1802550a8  mov     ebx, 36FDh
0x1802550ad  lea     rax, aOnecoreInterna_0; "OneCore\\Internal\\Base\\inc\\autoxmlpa"...
0x1802550b4  mov     [rbp+4Fh+var_90], rax
0x1802550b8  lea     rax, aXmlparsergener_2; "XmlParserGenerator::AutoXpgParser<struc"...
0x1802550bf  mov     [rbp+4Fh+var_88], rax
0x1802550c3  mov     [rbp+4Fh+var_80], 98h
0x1802550cb  lea     rax, aHfileIsvalid; "hFile.IsValid()"
0x1802550d2  mov     [rbp+4Fh+var_78], rax
0x1802550d6  test    ebx, ebx
0x1802550d8  jle     short loc_1802550E3
0x1802550da  movzx   ebx, bx
0x1802550dd  or      ebx, 80070000h
0x1802550e3  mov     r8d, ebx
0x1802550e6  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1802550ed  lea     rcx, [rbp+4Fh+var_90]
0x1802550f1  call    RtlReportErrorOrigination
0x1802550f6  nop
0x1802550f7  lea     rcx, [rdi-1]
0x1802550fb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1802550ff  ja      short loc_180255119
0x180255101  mov     rcx, rdi; Handle
0x180255104  call    cs:__imp_NtClose
0x18025510b  nop     dword ptr [rax+rax+00h]
0x180255110  test    eax, eax
0x180255112  jns     short loc_180255119
0x180255114  mov     rcx, rsi
0x180255117  int     29h; Win8: RtlFailFast(ecx)
0x180255119  mov     eax, ebx
0x18025511b  mov     rcx, [rbp+4Fh+var_38]
0x18025511f  xor     rcx, rsp; StackCookie
0x180255122  call    __security_check_cookie
0x180255127  mov     rbx, [rsp+0D0h+arg_8]
0x18025512f  add     rsp, 0A0h
0x180255136  pop     r15
0x180255138  pop     r14
0x18025513a  pop     r13
0x18025513c  pop     r12
0x18025513e  pop     rdi
0x18025513f  pop     rsi
0x180255140  pop     rbp
0x180255141  retn
0x180255143  call    cs:__imp_GetLastError
0x18025514a  nop     dword ptr [rax+rax+00h]
0x18025514f  nop
0x180255150  mov     ebx, eax
0x180255152  test    eax, eax
0x180255154  jnz     loc_1802550AD
0x18025515a  mov     ecx, 0C00000E5h; int
0x18025515f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x180255164  nop
0x180255165  mov     ecx, 0C00000E5h; int
0x18025516a  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
