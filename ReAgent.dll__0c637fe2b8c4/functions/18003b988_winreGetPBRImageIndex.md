# winreGetPBRImageIndex

- ea: `0x18003b988`
- end: `0x18003be9f`
- name: `winreGetPBRImageIndex`
- size: `1303`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18003af14`
- `0x18003bfbc`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18001c56c`
- `0x18003b988`
- `0x18003f35c`
- `0x18003fc50`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003bc07`
- `KERNEL32!GetLastError` at `0x18003bc07`
- `KERNEL32!FindFirstFileW` at `0x18003bbf8`
- `KERNEL32!FindFirstFileW` at `0x18003bbf8`
- `KERNEL32!FindNextFileW` at `0x18003bdcb`
- `KERNEL32!FindNextFileW` at `0x18003bdcb`
- `KERNEL32!FindClose` at `0x18003be4d`
- `KERNEL32!FindClose` at `0x18003be4d`

## string_xrefs

- `0x18003be17`: `failed to append path`
- `0x18003bae3`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003bb8f`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003be00`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003bba6`: `failed to create wildcard path`
- `0x18003ba8e`: `resetconfig.xml`
- `0x18003bafa`: `failed to append path resetconfig.xml`
- `0x18003bb62`: `ResetConfig.xml does not have the PBR image tag, checking other xmls`
- `0x18003bb73`: `%s\*.xml`
- `0x18003bbe0`: `Scanning path %s`
- `0x18003bc6b`: `Ignorning directory %s`
- `0x18003be34`: ` %lu valid xmls found, exactly one xml has to be valid`

## pseudocode

```c
__int64 __fastcall winreGetPBRImageIndex(unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v4; // r15d
  int v5; // eax
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // r8
  int v10; // ebx
  HANDLE FirstFileW; // rdi
  DWORD LastError; // eax
  unsigned int v13; // r13d
  unsigned int v14; // esi
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  const unsigned __int16 *v17; // r8
  WCHAR *cFileName; // rax
  unsigned __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v21[3]; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v23; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v24[606]; // [rsp+2A2h] [rbp+1A2h] BYREF
  WCHAR FileName; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v26[606]; // [rsp+502h] [rbp+402h] BYREF

  v4 = 0;
  FileName = 0;
  memset_0(v26, 0, 0x25Au);
  v23 = 0;
  memset_0(v24, 0, 0x25Au);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v21[0] = 0;
  v21[1] = 0;
  if ( !a1 || !a2 )
  {
    v6 = 87;
    UnattendLogW(1, L"invalid parameter");
    goto LABEL_60;
  }
  *a2 = 0;
  v20 = 0;
  v5 = StringCchLengthW(a1, 0x7FFFFFFFu, &v20);
  LOWORD(v6) = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 14;
LABEL_14:
      WPP_SF_d(v7[2], v8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v5);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  if ( !v20 || (v9 = L"%s\\%s", a1[v20 - 1] == 92) )
    v9 = L"%s%s";
  v5 = StringCchPrintfW(&v23, 0x12Eu, v9, a1, L"resetconfig.xml");
  LOWORD(v6) = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 15;
      goto LABEL_14;
    }
LABEL_15:
    v6 = (unsigned __int16)v6;
    if ( (_WORD)v6 )
    {
      UnattendLogW(
        2,
        L"winreGetPBRImageIndex %s (0x%x) in file %S line %d",
        L"failed to append path resetconfig.xml",
        (unsigned __int16)v6,
        "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
        3195);
      goto LABEL_60;
    }
    goto LABEL_18;
  }
  v6 = 0;
LABEL_18:
  if ( (unsigned int)ResetConfigXMLParser::Init((ResetConfigXMLParser *)v21, &v23)
    && !ResetConfigXMLParser::ParseConfigFile((ResetConfigXMLParser *)v21)
    && HIDWORD(v21[0]) )
  {
    *a2 = HIDWORD(v21[0]);
    UnattendLogW(0, L"File %s found with index = %lu", &v23);
    goto LABEL_60;
  }
  UnattendLogW(0, L"ResetConfig.xml does not have the PBR image tag, checking other xmls");
  v10 = StringCchPrintfW(&FileName, 0x12Eu, L"%s\\*.xml", a1);
  if ( v10 < 0 )
  {
    UnattendLogW(
      2,
      L"winreGetPBRImageIndex %s (0x%x) in file %S line %d",
      L"failed to create wildcard path",
      (unsigned int)v10,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      3207);
    UnattendLogW(1, L" hr = 0x%x", (unsigned int)v10);
    v6 = -1;
    goto LABEL_60;
  }
  UnattendLogW(0, L"Scanning path %s", &FileName);
  FirstFileW = FindFirstFileW(&FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 2 )
      UnattendLogW(0, L"%s not found", &FileName);
    else
      UnattendLogW(1, L"FindFirstFileW(%s) failed, last error 0x%x", &FileName, LastError);
    goto LABEL_60;
  }
  v13 = 0;
  v14 = 0;
  do
  {
    UnattendLogW(0, L"Checking %s", FindFileData.cFileName);
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      UnattendLogW(0, L"Ignorning directory %s", FindFileData.cFileName);
      goto LABEL_51;
    }
    v20 = 0;
    v6 = StringCchLengthW(a1, 0x7FFFFFFFu, &v20);
    if ( v6 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v16 = 14;
LABEL_44:
        WPP_SF_d(v15[2], v16, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v6);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
    if ( !v20 || (v17 = L"%s\\%s", a1[v20 - 1] == 92) )
      v17 = L"%s%s";
    cFileName = &FindFileData.cFileName[1];
    if ( FindFileData.cFileName[0] != 92 )
      cFileName = FindFileData.cFileName;
    v6 = StringCchPrintfW(&v23, 0x12Eu, v17, a1, cFileName);
    if ( v6 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v16 = 15;
        goto LABEL_44;
      }
LABEL_45:
      v6 = (unsigned __int16)v6;
      if ( (_WORD)v6 )
      {
        UnattendLogW(
          2,
          L"winreGetPBRImageIndex %s (0x%x) in file %S line %d",
          L"failed to append path",
          (unsigned __int16)v6,
          "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
          3235);
        goto LABEL_57;
      }
    }
    UnattendLogW(0, L"Processing file %s", &v23);
    if ( !(unsigned int)ResetConfigXMLParser::Init((ResetConfigXMLParser *)v21, &v23) )
    {
      if ( ResetConfigXMLParser::ParseConfigFile((ResetConfigXMLParser *)v21) || !HIDWORD(v21[0]) )
      {
        UnattendLogW(0, L" File %s does not contain PBR image index information", &v23);
      }
      else
      {
        ++v14;
        v4 = HIDWORD(v21[0]);
        UnattendLogW(0, L"File %s found with index = %lu ", &v23);
      }
    }
LABEL_51:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      break;
    ++v13;
  }
  while ( v13 < 0x64 );
  if ( v14 == 1 )
  {
    UnattendLogW(0, L"Setting PBR index to %lu", v4);
    v6 = 0;
    *a2 = v4;
  }
  else
  {
    UnattendLogW(0, L" %lu valid xmls found, exactly one xml has to be valid", v14);
    v6 = 2;
  }
LABEL_57:
  if ( FirstFileW )
    FindClose(FirstFileW);
LABEL_60:
  ResetConfigXMLParser::~ResetConfigXMLParser((ResetConfigXMLParser *)v21);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003b988  mov     [rsp-8+arg_10], rbx
0x18003b98d  push    rbp
0x18003b98e  push    rsi
0x18003b98f  push    rdi
0x18003b990  push    r12
0x18003b992  push    r13
0x18003b994  push    r14
0x18003b996  push    r15
0x18003b998  lea     rbp, [rsp-670h]
0x18003b9a0  sub     rsp, 770h
0x18003b9a7  mov     rax, cs:__security_cookie
0x18003b9ae  xor     rax, rsp
0x18003b9b1  mov     [rbp+6A0h+var_40], rax
0x18003b9b8  mov     r12, rdx
0x18003b9bb  mov     r14, rcx
0x18003b9be  mov     ebx, 25Ah
0x18003b9c3  lea     rcx, [rbp+6A0h+var_29E]; void *
0x18003b9ca  xor     r15d, r15d
0x18003b9cd  mov     r8d, ebx; Size
0x18003b9d0  xor     edx, edx; Val
0x18003b9d2  mov     [rbp+6A0h+FileName], r15w
0x18003b9da  call    memset_0
0x18003b9df  mov     r8d, ebx; Size
0x18003b9e2  mov     [rbp+6A0h+var_500], r15w
0x18003b9ea  xor     edx, edx; Val
0x18003b9ec  lea     rcx, [rbp+6A0h+var_4FE]; void *
0x18003b9f3  call    memset_0
0x18003b9f8  xor     edx, edx; Val
0x18003b9fa  lea     r8d, [rbx-0Ah]; Size
0x18003b9fe  lea     rcx, [rsp+7A0h+FindFileData]; void *
0x18003ba03  call    memset_0
0x18003ba08  mov     [rsp+7A0h+var_768], r15
0x18003ba0d  mov     [rsp+7A0h+var_760], r15
0x18003ba12  test    r14, r14
0x18003ba15  jz      loc_18003BE55
0x18003ba1b  test    r12, r12
0x18003ba1e  jz      loc_18003BE55
0x18003ba24  lea     r8, [rsp+7A0h+var_770]; unsigned __int64 *
0x18003ba29  mov     [r12], r15d
0x18003ba2d  mov     edx, 7FFFFFFFh; unsigned __int64
0x18003ba32  mov     [rsp+7A0h+var_770], r15
0x18003ba37  mov     rcx, r14; unsigned __int16 *
0x18003ba3a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003ba3f  lea     rdi, WPP_GLOBAL_Control
0x18003ba46  mov     ebx, eax
0x18003ba48  lea     esi, [r15+2]
0x18003ba4c  mov     r13d, 12Eh
0x18003ba52  test    eax, eax
0x18003ba54  jns     short loc_18003BA6D
0x18003ba56  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba5d  cmp     rcx, rdi
0x18003ba60  jz      short loc_18003BADC
0x18003ba62  test    [rcx+1Ch], sil
0x18003ba66  jz      short loc_18003BADC
0x18003ba68  lea     edx, [rsi+0Ch]
0x18003ba6b  jmp     short loc_18003BAC9
0x18003ba6d  mov     rax, [rsp+7A0h+var_770]
0x18003ba72  test    rax, rax
0x18003ba75  jz      short loc_18003BA87
0x18003ba77  cmp     word ptr [r14+rax*2-2], 5Ch ; '\'
0x18003ba7e  lea     r8, aSS_1; "%s\\%s"
0x18003ba85  jnz     short loc_18003BA8E
0x18003ba87  lea     r8, aSS_2; "%s%s"
0x18003ba8e  lea     rax, aResetconfigXml_0; "resetconfig.xml"
0x18003ba95  mov     r9, r14
0x18003ba98  mov     rdx, r13; unsigned __int64
0x18003ba9b  mov     [rsp+7A0h+var_780], rax
0x18003baa0  lea     rcx, [rbp+6A0h+var_500]; unsigned __int16 *
0x18003baa7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003baac  mov     ebx, eax
0x18003baae  test    eax, eax
0x18003bab0  jns     short loc_18003BB14
0x18003bab2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bab9  cmp     rcx, rdi
0x18003babc  jz      short loc_18003BADC
0x18003babe  test    [rcx+1Ch], sil
0x18003bac2  jz      short loc_18003BADC
0x18003bac4  mov     edx, 0Fh
0x18003bac9  mov     rcx, [rcx+10h]
0x18003bacd  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18003bad4  mov     r9d, eax
0x18003bad7  call    WPP_SF_d
0x18003badc  movzx   ebx, bx
0x18003badf  test    ebx, ebx
0x18003bae1  jz      short loc_18003BB17
0x18003bae3  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003baea  mov     [rsp+7A0h+var_778], 0C7Bh
0x18003baf2  mov     r9d, ebx
0x18003baf5  mov     [rsp+7A0h+var_780], rax
0x18003bafa  lea     r8, aFailedToAppend_10; "failed to append path resetconfig.xml"
0x18003bb01  mov     ecx, esi
0x18003bb03  lea     rdx, aWinregetpbrima; "winreGetPBRImageIndex %s (0x%x) in file"...
0x18003bb0a  call    UnattendLogW
0x18003bb0f  jmp     loc_18003BE69
0x18003bb14  mov     ebx, r15d
0x18003bb17  lea     rdx, [rbp+6A0h+var_500]; unsigned __int16 *
0x18003bb1e  lea     rcx, [rsp+7A0h+var_768]; this
0x18003bb23  call    ?Init@ResetConfigXMLParser@@QEAAKPEAG@Z; ResetConfigXMLParser::Init(ushort *)
0x18003bb28  test    eax, eax
0x18003bb2a  jz      short loc_18003BB62
0x18003bb2c  lea     rcx, [rsp+7A0h+var_768]; this
0x18003bb31  call    ?ParseConfigFile@ResetConfigXMLParser@@QEAAKXZ; ResetConfigXMLParser::ParseConfigFile(void)
0x18003bb36  test    eax, eax
0x18003bb38  jnz     short loc_18003BB62
0x18003bb3a  mov     r9d, dword ptr [rsp+7A0h+var_768+4]
0x18003bb3f  test    r9d, r9d
0x18003bb42  jz      short loc_18003BB62
0x18003bb44  lea     r8, [rbp+6A0h+var_500]
0x18003bb4b  mov     [r12], r9d
0x18003bb4f  lea     rdx, aFileSFoundWith_0; "File %s found with index = %lu"
0x18003bb56  xor     ecx, ecx
0x18003bb58  call    UnattendLogW
0x18003bb5d  jmp     loc_18003BE69
0x18003bb62  lea     rdx, aResetconfigXml_1; "ResetConfig.xml does not have the PBR i"...
0x18003bb69  xor     ecx, ecx
0x18003bb6b  call    UnattendLogW
0x18003bb70  mov     r9, r14
0x18003bb73  lea     r8, aSXml; "%s\\*.xml"
0x18003bb7a  mov     rdx, r13; unsigned __int64
0x18003bb7d  lea     rcx, [rbp+6A0h+FileName]; unsigned __int16 *
0x18003bb84  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bb89  mov     ebx, eax
0x18003bb8b  test    eax, eax
0x18003bb8d  jns     short loc_18003BBD7
0x18003bb8f  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003bb96  mov     [rsp+7A0h+var_778], 0C87h
0x18003bb9e  mov     r9d, ebx
0x18003bba1  mov     [rsp+7A0h+var_780], rax
0x18003bba6  lea     r8, aFailedToCreate_29; "failed to create wildcard path"
0x18003bbad  mov     ecx, esi
0x18003bbaf  lea     rdx, aWinregetpbrima; "winreGetPBRImageIndex %s (0x%x) in file"...
0x18003bbb6  call    UnattendLogW
0x18003bbbb  mov     r8d, ebx
0x18003bbbe  lea     rdx, aHr0xX; " hr = 0x%x"
0x18003bbc5  mov     ecx, 1
0x18003bbca  call    UnattendLogW
0x18003bbcf  or      ebx, 0FFFFFFFFh
0x18003bbd2  jmp     loc_18003BE69
0x18003bbd7  lea     r8, [rbp+6A0h+FileName]
0x18003bbde  xor     ecx, ecx
0x18003bbe0  lea     rdx, aScanningPathS; "Scanning path %s"
0x18003bbe7  call    UnattendLogW
0x18003bbec  lea     rdx, [rsp+7A0h+FindFileData]; lpFindFileData
0x18003bbf1  lea     rcx, [rbp+6A0h+FileName]; lpFileName
0x18003bbf8  call    cs:__imp_FindFirstFileW
0x18003bbfe  mov     rdi, rax
0x18003bc01  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003bc05  jnz     short loc_18003BC46
0x18003bc07  call    cs:__imp_GetLastError
0x18003bc0d  lea     r8, [rbp+6A0h+FileName]
0x18003bc14  mov     ebx, eax
0x18003bc16  cmp     eax, esi
0x18003bc18  jnz     short loc_18003BC2D
0x18003bc1a  lea     rdx, aSNotFound; "%s not found"
0x18003bc21  xor     ecx, ecx
0x18003bc23  call    UnattendLogW
0x18003bc28  jmp     loc_18003BE69
0x18003bc2d  mov     r9d, eax
0x18003bc30  lea     rdx, aFindfirstfilew_1; "FindFirstFileW(%s) failed, last error 0"...
0x18003bc37  mov     ecx, 1
0x18003bc3c  call    UnattendLogW
0x18003bc41  jmp     loc_18003BE69
0x18003bc46  mov     r13d, r15d
0x18003bc49  mov     esi, r15d
0x18003bc4c  lea     r8, [rsp+7A0h+FindFileData.cFileName]
0x18003bc51  xor     ecx, ecx
0x18003bc53  lea     rdx, aCheckingS; "Checking %s"
0x18003bc5a  call    UnattendLogW
0x18003bc5f  test    byte ptr [rsp+7A0h+FindFileData.dwFileAttributes], 10h
0x18003bc64  jz      short loc_18003BC77
0x18003bc66  lea     r8, [rsp+7A0h+FindFileData.cFileName]
0x18003bc6b  lea     rdx, aIgnorningDirec; "Ignorning directory %s"
0x18003bc72  jmp     loc_18003BDBC
0x18003bc77  lea     r8, [rsp+7A0h+var_770]; unsigned __int64 *
0x18003bc7c  mov     [rsp+7A0h+var_770], 0
0x18003bc85  mov     edx, 7FFFFFFFh; unsigned __int64
0x18003bc8a  mov     rcx, r14; unsigned __int16 *
0x18003bc8d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003bc92  mov     ebx, eax
0x18003bc94  test    eax, eax
0x18003bc96  jns     short loc_18003BCC0
0x18003bc98  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bc9f  lea     rax, WPP_GLOBAL_Control
0x18003bca6  cmp     rcx, rax
0x18003bca9  jz      loc_18003BD45
0x18003bcaf  test    byte ptr [rcx+1Ch], 2
0x18003bcb3  jz      loc_18003BD45
0x18003bcb9  mov     edx, 0Eh
0x18003bcbe  jmp     short loc_18003BD32
0x18003bcc0  mov     rax, [rsp+7A0h+var_770]
0x18003bcc5  test    rax, rax
0x18003bcc8  jz      short loc_18003BCDA
0x18003bcca  cmp     word ptr [r14+rax*2-2], 5Ch ; '\'
0x18003bcd1  lea     r8, aSS_1; "%s\\%s"
0x18003bcd8  jnz     short loc_18003BCE1
0x18003bcda  lea     r8, aSS_2; "%s%s"
0x18003bce1  cmp     [rsp+7A0h+FindFileData.cFileName], 5Ch ; '\'
0x18003bce7  lea     rcx, [rsp+7A0h+FindFileData.cFileName]
0x18003bcec  lea     rax, [rsp+7A0h+FindFileData.cFileName+2]
0x18003bcf1  mov     r9, r14
0x18003bcf4  cmovnz  rax, rcx
0x18003bcf8  mov     edx, 12Eh; unsigned __int64
0x18003bcfd  lea     rcx, [rbp+6A0h+var_500]; unsigned __int16 *
0x18003bd04  mov     [rsp+7A0h+var_780], rax
0x18003bd09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bd0e  mov     ebx, eax
0x18003bd10  test    eax, eax
0x18003bd12  jns     short loc_18003BD50
0x18003bd14  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bd1b  lea     rax, WPP_GLOBAL_Control
0x18003bd22  cmp     rcx, rax
0x18003bd25  jz      short loc_18003BD45
0x18003bd27  test    byte ptr [rcx+1Ch], 2
0x18003bd2b  jz      short loc_18003BD45
0x18003bd2d  mov     edx, 0Fh
0x18003bd32  mov     rcx, [rcx+10h]
0x18003bd36  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18003bd3d  mov     r9d, ebx
0x18003bd40  call    WPP_SF_d
0x18003bd45  movzx   ebx, bx
0x18003bd48  test    ebx, ebx
0x18003bd4a  jnz     loc_18003BE00
0x18003bd50  lea     r8, [rbp+6A0h+var_500]
0x18003bd57  xor     ecx, ecx
0x18003bd59  lea     rdx, aProcessingFile; "Processing file %s"
0x18003bd60  call    UnattendLogW
0x18003bd65  lea     rdx, [rbp+6A0h+var_500]; unsigned __int16 *
0x18003bd6c  lea     rcx, [rsp+7A0h+var_768]; this
0x18003bd71  call    ?Init@ResetConfigXMLParser@@QEAAKPEAG@Z; ResetConfigXMLParser::Init(ushort *)
0x18003bd76  test    eax, eax
0x18003bd78  jnz     short loc_18003BDC3
0x18003bd7a  lea     rcx, [rsp+7A0h+var_768]; this
0x18003bd7f  call    ?ParseConfigFile@ResetConfigXMLParser@@QEAAKXZ; ResetConfigXMLParser::ParseConfigFile(void)
0x18003bd84  test    eax, eax
0x18003bd86  jnz     short loc_18003BDAE
0x18003bd88  mov     r9d, dword ptr [rsp+7A0h+var_768+4]
0x18003bd8d  test    r9d, r9d
0x18003bd90  jz      short loc_18003BDAE
0x18003bd92  inc     esi
0x18003bd94  lea     r8, [rbp+6A0h+var_500]
0x18003bd9b  lea     rdx, aFileSFoundWith; "File %s found with index = %lu "
0x18003bda2  xor     ecx, ecx
0x18003bda4  mov     r15d, r9d
0x18003bda7  call    UnattendLogW
0x18003bdac  jmp     short loc_18003BDC3
0x18003bdae  lea     r8, [rbp+6A0h+var_500]
0x18003bdb5  lea     rdx, aFileSDoesNotCo; " File %s does not contain PBR image ind"...
0x18003bdbc  xor     ecx, ecx
0x18003bdbe  call    UnattendLogW
0x18003bdc3  lea     rdx, [rsp+7A0h+FindFileData]; lpFindFileData
0x18003bdc8  mov     rcx, rdi; hFindFile
0x18003bdcb  call    cs:__imp_FindNextFileW
0x18003bdd1  test    eax, eax
0x18003bdd3  jz      short loc_18003BDE2
0x18003bdd5  inc     r13d
0x18003bdd8  cmp     r13d, 64h ; 'd'
0x18003bddc  jb      loc_18003BC4C
0x18003bde2  xor     ecx, ecx
0x18003bde4  cmp     esi, 1
0x18003bde7  jnz     short loc_18003BE31
0x18003bde9  mov     r8d, r15d
0x18003bdec  lea     rdx, aSettingPbrInde; "Setting PBR index to %lu"
0x18003bdf3  call    UnattendLogW
0x18003bdf8  xor     ebx, ebx
0x18003bdfa  mov     [r12], r15d
0x18003bdfe  jmp     short loc_18003BE45
0x18003be00  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003be07  mov     [rsp+7A0h+var_778], 0CA3h
0x18003be0f  mov     r9d, ebx
0x18003be12  mov     [rsp+7A0h+var_780], rax
0x18003be17  lea     r8, aFailedToAppend_7; "failed to append path"
0x18003be1e  mov     ecx, 2
0x18003be23  lea     rdx, aWinregetpbrima; "winreGetPBRImageIndex %s (0x%x) in file"...
0x18003be2a  call    UnattendLogW
0x18003be2f  jmp     short loc_18003BE45
0x18003be31  mov     r8d, esi
0x18003be34  lea     rdx, aLuValidXmlsFou; " %lu valid xmls found, exactly one xml "...
0x18003be3b  call    UnattendLogW
0x18003be40  mov     ebx, 2
0x18003be45  test    rdi, rdi
0x18003be48  jz      short loc_18003BE69
0x18003be4a  mov     rcx, rdi; hFindFile
0x18003be4d  call    cs:__imp_FindClose
0x18003be53  jmp     short loc_18003BE69
0x18003be55  mov     ebx, 57h ; 'W'
0x18003be5a  lea     rdx, aInvalidParamet_5; "invalid parameter"
0x18003be61  lea     ecx, [rbx-56h]
0x18003be64  call    UnattendLogW
0x18003be69  lea     rcx, [rsp+7A0h+var_768]; this
0x18003be6e  call    ??1ResetConfigXMLParser@@QEAA@XZ; ResetConfigXMLParser::~ResetConfigXMLParser(void)
0x18003be73  mov     eax, ebx
0x18003be75  mov     rcx, [rbp+6A0h+var_40]
0x18003be7c  xor     rcx, rsp; StackCookie
0x18003be7f  call    __security_check_cookie
0x18003be84  mov     rbx, [rsp+7A0h+arg_10]
0x18003be8c  add     rsp, 770h
0x18003be93  pop     r15
0x18003be95  pop     r14
0x18003be97  pop     r13
0x18003be99  pop     r12
  ... truncated ...
```
