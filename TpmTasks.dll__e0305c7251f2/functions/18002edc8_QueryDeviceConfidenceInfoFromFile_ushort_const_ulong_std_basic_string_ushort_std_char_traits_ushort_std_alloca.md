# QueryDeviceConfidenceInfoFromFile(ushort const *,ulong &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong &)

- ea: `0x18002edc8`
- end: `0x18002f227`
- name: `?QueryDeviceConfidenceInfoFromFile@@YAJPEBGAEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2221@Z`
- size: `1119`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int *, __int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f230`
- `0x18002f340`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000bcc4`
- `0x18000d524`
- `0x18000eb54`
- `0x180023634`
- `0x18002386c`
- `0x1800275d0`
- `0x18002b4c0`
- `0x18002c62c`
- `0x18002c770`
- `0x18002c8b4`
- `0x18002e658`
- `0x18002edc8`
- `0x18002f400`
- `0x18002f498`
- `0x180030394`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ee89`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ee89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eea2`
- `WINTRUST!WTGetSignatureInfo` at `0x18002ef39`
- `WINTRUST!WTGetSignatureInfo` at `0x18002ef39`

## string_xrefs

- `0x18002eebd`: `CreateFileW for %ls failed with %x`
- `0x18002efc5`: `Failed to extract Metadata json from cab: %x`
- `0x18002f091`: `Skipping Parsing BucketConfidence file version %d, returning cached ConfidenceLevel %s`
- `0x18002f0f9`: `Known OEM %s checking only its OEM JSON files.`
- `0x18002f138`: `Failed to extract OEM json files from cab: %x`
- `0x18002f14a`: `Generic OEM %s checking only Generic JSON files.`
- `0x18002f189`: `Failed to extract Generic json: %x`
- `0x18002f1bd`: `No matching OEM entries found in any JSON files, setting to default.`

## pseudocode

```c
__int64 __fastcall QueryDeviceConfidenceInfoFromFile(
        LPCWSTR lpFileName,
        unsigned int *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7)
{
  _WORD *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  _WORD *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  _WORD *v16; // rax
  __int64 v17; // r8
  _WORD *v18; // rax
  HANDLE hTemplateFile; // r8
  unsigned int v20; // r15d
  HANDLE FileW; // rbx
  signed int LastError; // eax
  signed int MetadataJsonFromCab; // ebx
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  const unsigned __int8 *v27; // rax
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // r8
  unsigned __int64 appended; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rdx
  HANDLE v36; // [rsp+48h] [rbp-1F0h] BYREF
  __int64 v37[4]; // [rsp+50h] [rbp-1E8h] BYREF
  _DWORD v38[10]; // [rsp+70h] [rbp-1C8h] BYREF
  _BYTE *v39; // [rsp+98h] [rbp-1A0h]
  int v40; // [rsp+A0h] [rbp-198h]
  _BYTE v41[32]; // [rsp+D0h] [rbp-168h] BYREF
  _BYTE v42[256]; // [rsp+F0h] [rbp-148h] BYREF

  v37[0] = a5;
  *(_QWORD *)(a3 + 16) = 0;
  v10 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  *v10 = v11;
  *(_QWORD *)(v12 + 16) = v11;
  v13 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  *v13 = v14;
  *(_QWORD *)(v15 + 16) = v14;
  v16 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  *v16 = v17;
  *(_QWORD *)(a6 + 16) = v17;
  v18 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6);
  *v18 = (_WORD)hTemplateFile;
  *a7 = (_DWORD)hTemplateFile;
  v20 = (_DWORD)hTemplateFile + 1;
  FileW = CreateFileW(lpFileName, 0x80000000, (int)hTemplateFile + 1, 0, 3u, 0x80u, hTemplateFile);
  v36 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    memset_0(v38, 0, 0x58u);
    v38[0] = 88;
    memset_0(v42, 0, sizeof(v42));
    v39 = v42;
    v40 = 128;
    v24 = WTGetSignatureInfo(lpFileName, FileW, 6147, v38, 0, 0);
    MetadataJsonFromCab = v24;
    if ( v24 < 0 )
    {
      SBServicingLogMessage((wchar_t *)L"WTGetSignatureInfo failed with %x", (unsigned int)v24);
      goto LABEL_26;
    }
    if ( v38[1] - 5 > v20 )
    {
      SBServicingLogMessage((wchar_t *)L"Invalid signature for %ls\n", lpFileName);
      MetadataJsonFromCab = -2147024883;
      goto LABEL_26;
    }
    SBServicingLogMessage((wchar_t *)L"Verified signature publisher: %s", v39);
    std::wstring::wstring(v41, lpFileName);
    MetadataJsonFromCab = ExtractMetadataJsonFromCab(v41);
    std::wstring::_Tidy_deallocate(v41);
    if ( MetadataJsonFromCab < 0 )
    {
      SBServicingLogMessage(
        (wchar_t *)L"Failed to extract Metadata json from cab: %x",
        (unsigned int)MetadataJsonFromCab);
      goto LABEL_26;
    }
    std::wstring::operator=(a3, qword_1800A3798);
    *a2 = g_MetadataInfo;
    std::wstring::operator=(a4, qword_1800A37B8);
    std::wstring::operator=(v37[0], qword_1800A37D8);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800A37D8);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800A37B8);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800A37F8);
    v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800A3798);
    SBServicingLogMessage(
      (wchar_t *)L"Version: %d Timestamp: %s oemName: %s BucketId: %ls BucketAttribValues: %ls",
      g_MetadataInfo,
      v25);
    if ( (unsigned int)ShouldSkipParsingConfidenceFile(*a2, a4) )
    {
      LoadSavedConfidenceLevel(a6, a7);
      v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6);
      SBServicingLogMessage(
        (wchar_t *)L"Skipping Parsing BucketConfidence file version %d, returning cached ConfidenceLevel %s",
        *a2,
        v26);
      goto LABEL_26;
    }
    v27 = (const unsigned __int8 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800A37F8);
    appended = std::_Fnv1a_append_bytes(v28, v27, v29);
    v32 = *(_QWORD *)(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                        v31,
                        v37,
                        qword_1800A37F8,
                        appended)
                    + 8);
    if ( !v32 || v32 == qword_1800A4318 )
      LOBYTE(v20) = 0;
    v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800A37F8);
    if ( (_BYTE)v20 )
    {
      SBServicingLogMessage((wchar_t *)L"Known OEM %s checking only its OEM JSON files.", v33);
      std::wstring::wstring(v41, lpFileName);
      MetadataJsonFromCab = ExtractOEMJsonFromCab(v41);
      std::wstring::_Tidy_deallocate(v41);
      if ( MetadataJsonFromCab < 0 )
      {
        SBServicingLogMessage(
          (wchar_t *)L"Failed to extract OEM json files from cab: %x",
          (unsigned int)MetadataJsonFromCab);
        goto LABEL_26;
      }
    }
    else
    {
      SBServicingLogMessage((wchar_t *)L"Generic OEM %s checking only Generic JSON files.", v33);
      std::wstring::wstring(v41, lpFileName);
      MetadataJsonFromCab = ExtractGenericJsonFromCab(v41);
      std::wstring::_Tidy_deallocate(v41);
      if ( MetadataJsonFromCab < 0 )
      {
        SBServicingLogMessage((wchar_t *)L"Failed to extract Generic json: %x", (unsigned int)MetadataJsonFromCab);
        goto LABEL_26;
      }
    }
    if ( qword_1800A3848 )
    {
      std::wstring::operator=(a6, qword_1800A3838);
      *a7 = dword_1800A3858;
    }
    else
    {
      SBServicingLogMessage((wchar_t *)L"No matching OEM entries found in any JSON files, setting to default.");
      std::wstring::_Assign<unsigned short>(a6, L"No Data Observed - Action Required");
      *a7 = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    MetadataJsonFromCab = LastError;
    if ( LastError > 0 )
      MetadataJsonFromCab = (unsigned __int16)LastError | 0x80070000;
    SBServicingLogMessage(
      (wchar_t *)L"CreateFileW for %ls failed with %x",
      lpFileName,
      (unsigned int)MetadataJsonFromCab);
  }
  if ( MetadataJsonFromCab >= 0 )
    SaveLastParsedDataVersionIfDifferent(*a2);
LABEL_26:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
  return (unsigned int)MetadataJsonFromCab;
}

```

## disassembly

```asm
0x18002edc8  push    rbx
0x18002edca  push    rsi
0x18002edcb  push    rdi
0x18002edcc  push    r12
0x18002edce  push    r13
0x18002edd0  push    r14
0x18002edd2  push    r15
0x18002edd4  sub     rsp, 200h
0x18002eddb  mov     rax, cs:__security_cookie
0x18002ede2  xor     rax, rsp
0x18002ede5  mov     [rsp+238h+var_48], rax
0x18002eded  mov     r13, r9
0x18002edf0  mov     rax, r8
0x18002edf3  mov     [rsp+238h+var_1F8], rax
0x18002edf8  mov     r14, rdx
0x18002edfb  mov     rdi, rcx
0x18002edfe  mov     rsi, [rsp+238h+arg_28]
0x18002ee06  mov     rdx, [rsp+238h+arg_20]
0x18002ee0e  mov     [rsp+238h+var_1E8], rdx
0x18002ee13  mov     r12, [rsp+238h+arg_30]
0x18002ee1b  xor     r8d, r8d
0x18002ee1e  mov     [rax+10h], r8
0x18002ee22  mov     rcx, rax
0x18002ee25  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ee2a  mov     [rax], r8w
0x18002ee2e  mov     [r9+10h], r8
0x18002ee32  mov     rcx, r9
0x18002ee35  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ee3a  mov     [rax], r8w
0x18002ee3e  mov     [rdx+10h], r8
0x18002ee42  mov     rcx, rdx
0x18002ee45  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ee4a  mov     [rax], r8w
0x18002ee4e  mov     [rsi+10h], r8
0x18002ee52  mov     rcx, rsi
0x18002ee55  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ee5a  mov     [rax], r8w
0x18002ee5e  mov     [r12], r8d
0x18002ee62  mov     [rsp+238h+hTemplateFile], r8; hTemplateFile
0x18002ee67  mov     [rsp+238h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002ee6f  mov     [rsp+238h+dwCreationDisposition], 3; dwCreationDisposition
0x18002ee77  xor     r9d, r9d; lpSecurityAttributes
0x18002ee7a  lea     r15d, [r8+1]
0x18002ee7e  mov     r8d, r15d; dwShareMode
0x18002ee81  mov     edx, 80000000h; dwDesiredAccess
0x18002ee86  mov     rcx, rdi; lpFileName
0x18002ee89  call    cs:__imp_CreateFileW
0x18002ee8f  mov     rbx, rax
0x18002ee92  mov     [rsp+238h+var_1F0], rax
0x18002ee97  inc     rax
0x18002ee9a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002eea0  jnz     short loc_18002EECE
0x18002eea2  call    cs:__imp_GetLastError
0x18002eea8  mov     ebx, eax
0x18002eeaa  test    eax, eax
0x18002eeac  jle     short loc_18002EEB7
0x18002eeae  movzx   ebx, ax
0x18002eeb1  or      ebx, 80070000h
0x18002eeb7  mov     r8d, ebx
0x18002eeba  mov     rdx, rdi
0x18002eebd  lea     rcx, aCreatefilewFor; "CreateFileW for %ls failed with %x"
0x18002eec4  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002eec9  jmp     loc_18002F1E6
0x18002eece  xor     edx, edx; Val
0x18002eed0  lea     r8d, [rdx+58h]; Size
0x18002eed4  lea     rcx, [rsp+238h+var_1C8]; void *
0x18002eed9  call    memset_0
0x18002eede  mov     [rsp+238h+var_1C8], 58h ; 'X'
0x18002eee6  xor     edx, edx; Val
0x18002eee8  mov     r8d, 100h; Size
0x18002eeee  lea     rcx, [rsp+238h+var_148]; void *
0x18002eef6  call    memset_0
0x18002eefb  lea     rax, [rsp+238h+var_148]
0x18002ef03  mov     [rsp+238h+var_1A0], rax
0x18002ef0b  mov     [rsp+238h+var_198], 80h
0x18002ef16  mov     qword ptr [rsp+238h+dwFlagsAndAttributes], 0
0x18002ef1f  mov     qword ptr [rsp+238h+dwCreationDisposition], 0
0x18002ef28  lea     r9, [rsp+238h+var_1C8]
0x18002ef2d  mov     r8d, 1803h
0x18002ef33  mov     rdx, rbx
0x18002ef36  mov     rcx, rdi
0x18002ef39  call    cs:__imp_WTGetSignatureInfo
0x18002ef3f  mov     ebx, eax
0x18002ef41  test    eax, eax
0x18002ef43  jns     short loc_18002EF59
0x18002ef45  mov     edx, eax
0x18002ef47  lea     rcx, aWtgetsignature; "WTGetSignatureInfo failed with %x"
0x18002ef4e  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002ef53  nop
0x18002ef54  jmp     loc_18002F1F8
0x18002ef59  mov     eax, [rsp+238h+var_1C4]
0x18002ef5d  add     eax, 0FFFFFFFBh
0x18002ef60  cmp     eax, r15d
0x18002ef63  jbe     short loc_18002EF7E
0x18002ef65  mov     rdx, rdi
0x18002ef68  lea     rcx, aInvalidSignatu; "Invalid signature for %ls\n"
0x18002ef6f  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002ef74  mov     ebx, 8007000Dh
0x18002ef79  jmp     loc_18002F1F8
0x18002ef7e  mov     rdx, [rsp+238h+var_1A0]
0x18002ef86  lea     rcx, aVerifiedSignat; "Verified signature publisher: %s"
0x18002ef8d  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002ef92  mov     rdx, rdi
0x18002ef95  lea     rcx, [rsp+238h+var_168]
0x18002ef9d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002efa2  nop
0x18002efa3  lea     rcx, [rsp+238h+var_168]
0x18002efab  call    ?ExtractMetadataJsonFromCab@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractMetadataJsonFromCab(std::wstring const &)
0x18002efb0  mov     ebx, eax
0x18002efb2  lea     rcx, [rsp+238h+var_168]
0x18002efba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002efbf  test    ebx, ebx
0x18002efc1  jns     short loc_18002EFD7
0x18002efc3  mov     edx, ebx
0x18002efc5  lea     rcx, aFailedToExtrac_1; "Failed to extract Metadata json from ca"...
0x18002efcc  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002efd1  nop
0x18002efd2  jmp     loc_18002F1F8
0x18002efd7  lea     rdx, qword_1800A3798
0x18002efde  mov     rcx, [rsp+238h+var_1F8]
0x18002efe3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002efe8  mov     eax, cs:?g_MetadataInfo@@3UMetadataInfo@@A; MetadataInfo g_MetadataInfo
0x18002efee  mov     [r14], eax
0x18002eff1  lea     rdx, qword_1800A37B8
0x18002eff8  mov     rcx, r13
0x18002effb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002f000  lea     rdx, qword_1800A37D8
0x18002f007  mov     rcx, [rsp+238h+var_1E8]
0x18002f00c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002f011  lea     rcx, qword_1800A37D8
0x18002f018  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f01d  mov     r11, rax
0x18002f020  lea     rcx, qword_1800A37B8
0x18002f027  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f02c  mov     r10, rax
0x18002f02f  lea     rcx, qword_1800A37F8
0x18002f036  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f03b  mov     r9, rax
0x18002f03e  lea     rcx, qword_1800A3798
0x18002f045  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f04a  mov     r8, rax
0x18002f04d  mov     qword ptr [rsp+238h+dwFlagsAndAttributes], r11
0x18002f052  mov     qword ptr [rsp+238h+dwCreationDisposition], r10
0x18002f057  mov     edx, cs:?g_MetadataInfo@@3UMetadataInfo@@A; MetadataInfo g_MetadataInfo
0x18002f05d  lea     rcx, aVersionDTimest; "Version: %d Timestamp: %s oemName: %s B"...
0x18002f064  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f069  mov     rdx, r13
0x18002f06c  mov     ecx, [r14]
0x18002f06f  call    ?ShouldSkipParsingConfidenceFile@@YAHKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ShouldSkipParsingConfidenceFile(ulong,std::wstring const &)
0x18002f074  test    eax, eax
0x18002f076  jz      short loc_18002F0A3
0x18002f078  mov     rdx, r12
0x18002f07b  mov     rcx, rsi
0x18002f07e  call    ?LoadSavedConfidenceLevel@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z; LoadSavedConfidenceLevel(std::wstring &,ulong &)
0x18002f083  mov     rcx, rsi
0x18002f086  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f08b  mov     r8, rax
0x18002f08e  mov     edx, [r14]
0x18002f091  lea     rcx, aSkippingParsin; "Skipping Parsing BucketConfidence file "...
0x18002f098  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f09d  nop
0x18002f09e  jmp     loc_18002F1F8
0x18002f0a3  mov     r8, cs:qword_1800A3808
0x18002f0aa  add     r8, r8
0x18002f0ad  lea     rbx, qword_1800A37F8
0x18002f0b4  mov     rcx, rbx
0x18002f0b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f0bc  mov     rdx, rax; unsigned __int8 *
0x18002f0bf  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18002f0c4  mov     r9, rax
0x18002f0c7  mov     r8, rbx
0x18002f0ca  lea     rdx, [rsp+238h+var_1E8]
0x18002f0cf  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18002f0d4  mov     rcx, [rax+8]
0x18002f0d8  test    rcx, rcx
0x18002f0db  jz      short loc_18002F0E6
0x18002f0dd  cmp     rcx, cs:qword_1800A4318
0x18002f0e4  jnz     short loc_18002F0E9
0x18002f0e6  xor     r15b, r15b
0x18002f0e9  mov     rcx, rbx
0x18002f0ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f0f1  mov     rdx, rax
0x18002f0f4  test    r15b, r15b
0x18002f0f7  jz      short loc_18002F14A
0x18002f0f9  lea     rcx, aKnownOemSCheck; "Known OEM %s checking only its OEM JSON"...
0x18002f100  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f105  mov     rdx, rdi
0x18002f108  lea     rcx, [rsp+238h+var_168]
0x18002f110  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f115  nop
0x18002f116  lea     rcx, [rsp+238h+var_168]
0x18002f11e  call    ?ExtractOEMJsonFromCab@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractOEMJsonFromCab(std::wstring const &)
0x18002f123  mov     ebx, eax
0x18002f125  lea     rcx, [rsp+238h+var_168]
0x18002f12d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f132  test    ebx, ebx
0x18002f134  jns     short loc_18002F198
0x18002f136  mov     edx, ebx
0x18002f138  lea     rcx, aFailedToExtrac_0; "Failed to extract OEM json files from c"...
0x18002f13f  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f144  nop
0x18002f145  jmp     loc_18002F1F8
0x18002f14a  lea     rcx, aGenericOemSChe; "Generic OEM %s checking only Generic JS"...
0x18002f151  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f156  mov     rdx, rdi
0x18002f159  lea     rcx, [rsp+238h+var_168]
0x18002f161  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f166  nop
0x18002f167  lea     rcx, [rsp+238h+var_168]
0x18002f16f  call    ?ExtractGenericJsonFromCab@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractGenericJsonFromCab(std::wstring const &)
0x18002f174  mov     ebx, eax
0x18002f176  lea     rcx, [rsp+238h+var_168]
0x18002f17e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f183  test    ebx, ebx
0x18002f185  jns     short loc_18002F198
0x18002f187  mov     edx, ebx
0x18002f189  lea     rcx, aFailedToExtrac; "Failed to extract Generic json: %x"
0x18002f190  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f195  nop
0x18002f196  jmp     short loc_18002F1F8
0x18002f198  cmp     cs:qword_1800A3848, 0
0x18002f1a0  jz      short loc_18002F1BD
0x18002f1a2  lea     rdx, qword_1800A3838
0x18002f1a9  mov     rcx, rsi
0x18002f1ac  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002f1b1  mov     eax, cs:dword_1800A3858
0x18002f1b7  mov     [r12], eax
0x18002f1bb  jmp     short loc_18002F1E6
0x18002f1bd  lea     rcx, aNoMatchingOemE; "No matching OEM entries found in any JS"...
0x18002f1c4  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f1c9  mov     r8d, 22h ; '"'
0x18002f1cf  lea     rdx, aNoDataObserved_0; "No Data Observed - Action Required"
0x18002f1d6  mov     rcx, rsi
0x18002f1d9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002f1de  mov     dword ptr [r12], 0
0x18002f1e6  test    ebx, ebx
0x18002f1e8  js      short loc_18002F1F8
0x18002f1ea  mov     ecx, [r14]; unsigned int
0x18002f1ed  call    ?SaveLastParsedDataVersionIfDifferent@@YAXK@Z; SaveLastParsedDataVersionIfDifferent(ulong)
0x18002f1f2  jmp     short loc_18002F1F8
0x18002f1f4  mov     ebx, dword ptr [rsp+238h+var_1F8]
0x18002f1f8  lea     rcx, [rsp+238h+var_1F0]
0x18002f1fd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f202  mov     eax, ebx
0x18002f204  mov     rcx, [rsp+238h+var_48]
0x18002f20c  xor     rcx, rsp; StackCookie
0x18002f20f  call    __security_check_cookie
0x18002f214  add     rsp, 200h
0x18002f21b  pop     r15
0x18002f21d  pop     r14
0x18002f21f  pop     r13
0x18002f221  pop     r12
0x18002f223  pop     rdi
0x18002f224  pop     rsi
0x18002f225  pop     rbx
0x18002f226  retn
```
