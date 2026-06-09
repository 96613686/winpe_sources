# _anonymous_namespace_::ListCompatibleDrivers

- ea: `0x18003ded0`
- end: `0x18003e4fd`
- name: `_anonymous_namespace_::ListCompatibleDrivers`
- size: `1581`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180042d7c`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x18001ecfc`
- `0x1800234f8`
- `0x1800236e0`
- `0x18002373c`
- `0x180023de0`
- `0x180024410`
- `0x180024ad4`
- `0x180024b2c`
- `0x180024c04`
- `0x180024c68`
- `0x180028e44`
- `0x180028f9c`
- `0x180029448`
- `0x18002970c`
- `0x18002b9a8`
- `0x18002be2c`
- `0x18002db24`
- `0x18002f220`
- `0x18003704c`
- `0x18003dae0`
- `0x18003ded0`
- `0x18003eaec`
- `0x180045a68`
- `0x180045d34`
- `0x180046bfc`
- `0x18004d1ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e0a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e10e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e0a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e10e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e0e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e0e2`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x18003df47`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x18003df47`
- `SETUPAPI!SetupDiGetDriverInfoDetailW` at `0x18003e344`
- `SETUPAPI!SetupDiGetDriverInfoDetailW` at `0x18003e344`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18003dff7`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18003dff7`

## string_xrefs

- `0x18003e0c0`: `SystemSettings_Accessibility_Braille_Driver_NarratorPreDescription`
- `0x18003df96`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x18003e3a0`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`
- `0x18003e4bb`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\braille.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void *__fastcall anonymous_namespace_::ListCompatibleDrivers(void *a1, HDEVINFO *a2, __int64 a3, __int64 a4)
{
  int v7; // r12d
  struct _SP_DEVINFO_DATA *v8; // r8
  signed int LastError; // eax
  unsigned __int64 v10; // r9
  DWORD i; // r14d
  __int64 VersionText; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  HSTRING *v15; // r8
  int ResourceStringById; // eax
  PCWSTR StringRawBuffer; // rax
  _QWORD *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rax
  _BYTE *j; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  signed int v27; // eax
  unsigned __int64 v28; // r9
  _BYTE *v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rax
  __int64 v33; // r10
  __int64 v34; // rdx
  int v35; // eax
  int v36; // edx
  int v37; // r8d
  int v38; // r9d
  __int64 v39; // r10
  bool v40; // bl
  int DriverInfoData; // [rsp+20h] [rbp-E0h]
  int DriverInfoDataa; // [rsp+20h] [rbp-E0h]
  int DriverInfoDatab; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v46[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h]
  void *v48; // [rsp+80h] [rbp-80h]
  _BYTE v49[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v50[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v51[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v52[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v53[24]; // [rsp+B8h] [rbp-48h] BYREF
  struct _SP_DRVINFO_DATA_V2_W v54; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE Src[32]; // [rsp+6F0h] [rbp+5F0h] BYREF
  _BYTE v56[32]; // [rsp+710h] [rbp+610h] BYREF
  bool v57; // [rsp+730h] [rbp+630h]
  int v58; // [rsp+731h] [rbp+631h]
  __int16 v59; // [rsp+735h] [rbp+635h]
  char v60; // [rsp+737h] [rbp+637h]
  _BYTE v61[32]; // [rsp+738h] [rbp+638h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+758h] [rbp+658h] BYREF
  _BYTE v63[32]; // [rsp+778h] [rbp+678h] BYREF
  _BYTE v64[32]; // [rsp+798h] [rbp+698h] BYREF
  _BYTE v65[16]; // [rsp+7B8h] [rbp+6B8h] BYREF
  __int64 v66; // [rsp+7C8h] [rbp+6C8h]
  _BYTE v67[32]; // [rsp+7D8h] [rbp+6D8h] BYREF
  _BYTE v68[32]; // [rsp+7F8h] [rbp+6F8h] BYREF
  _BYTE v69[32]; // [rsp+818h] [rbp+718h] BYREF
  _BYTE v70[40]; // [rsp+838h] [rbp+738h] BYREF
  _SP_DRVINFO_DETAIL_DATA_W DriverInfoDetailData; // [rsp+860h] [rbp+760h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+ED8h] [rbp+DD8h]

  v48 = a1;
  std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>(a1);
  v7 = 1;
  DeviceInfoData = *v8;
  if ( !SetupDiBuildDriverInfoList(*a2, &DeviceInfoData, 2u) )
  {
    LastError = GetLastError();
    v10 = (unsigned int)LastError;
    if ( (LastError & 0xE0000000) == 0xE0000000 )
    {
      v10 = (unsigned __int16)LastError | 0x800F0000;
    }
    else if ( LastError > 0 )
    {
      v10 = (unsigned __int16)LastError | 0x80070000;
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
      (const char *)v10,
      DriverInfoData);
  }
  std::unordered_map<std::wstring,unsigned __int64>::unordered_map<std::wstring,unsigned __int64>(v46);
  for ( i = 0; i < 0x3E8; ++i )
  {
    v54.cbSize = 1568;
    memset_0(&v54.DriverType, 0, 0x61Cu);
    if ( !SetupDiEnumDriverInfoW(*a2, &DeviceInfoData, 2u, i, &v54) )
      break;
    std::wstring::wstring(Src, v54.Description);
    VersionText = anonymous_namespace_::GetVersionText(v61, v54.DriverVersion);
    v13 = std::operator+<unsigned short>(v63, L" (", VersionText);
    v14 = std::operator+<unsigned short>(v64, v13, L")");
    std::wstring::append(Src, v14);
    std::wstring::_Tidy_deallocate(v64);
    std::wstring::_Tidy_deallocate(v63);
    std::wstring::_Tidy_deallocate(v61);
    if ( (unsigned __int8)anonymous_namespace_::IsDriverSupportedByNarrator(Src) )
    {
      WindowsDeleteString(0);
      string = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Accessibility_Braille_Driver_NarratorPreDescription",
                             &string,
                             v15);
      if ( ResourceStringById < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x158,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
          (const char *)(unsigned int)ResourceStringById,
          DriverInfoDataa);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      std::_WChar_traits<wchar_t>::length(StringRawBuffer);
      std::wstring::_Insert<unsigned short>(Src);
      WindowsDeleteString(string);
    }
    v18 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::find(
                      v46,
                      v49,
                      Src);
    if ( *v18 == v47 )
    {
      *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Try_emplace<std::wstring const &,>(
                               v46,
                               v51,
                               Src)
                + 48LL) = 1;
    }
    else
    {
      v19 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Try_emplace<std::wstring const &,>(
                         v46,
                         v52,
                         Src);
      std::_Integral_to_string<unsigned short,unsigned __int64>(v63, ++*(_QWORD *)(v19 + 48));
      v7 |= 2u;
      v20 = std::operator+<unsigned short>(v68, Src, L" (");
      v21 = std::operator+<unsigned short>(v67, v20, v63);
      std::operator+<unsigned short>(v61, v21, L")");
      std::wstring::_Tidy_deallocate(v67);
      std::wstring::_Tidy_deallocate(v68);
      for ( j = v63; ; j = v64 )
      {
        std::wstring::_Tidy_deallocate(j);
        v23 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::find(
                          v46,
                          v50,
                          v61);
        if ( *v23 == v47 )
          break;
        std::_Integral_to_string<unsigned short,unsigned __int64>(v64, ++*(_QWORD *)(v19 + 48));
        v7 |= 8u;
        v24 = std::operator+<unsigned short>(v56, Src, L" (");
        v25 = std::operator+<unsigned short>(v70, v24, v64);
        v26 = std::operator+<unsigned short>(v69, v25, L")");
        std::wstring::operator=(v61, v26);
        std::wstring::_Tidy_deallocate(v69);
        std::wstring::_Tidy_deallocate(v70);
        std::wstring::_Tidy_deallocate(v56);
      }
      *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Try_emplace<std::wstring const &,>(
                               v46,
                               v53,
                               v61)
                + 48LL) = 1;
      std::wstring::operator=(Src, v61);
      std::wstring::_Tidy_deallocate(v61);
    }
    DriverInfoDetailData.cbSize = 1584;
    memset_0(&DriverInfoDetailData.InfDate, 0, 0x62Cu);
    if ( SetupDiGetDriverInfoDetailW(*a2, &DeviceInfoData, &v54, &DriverInfoDetailData, 0x630u, 0)
      || (v27 = GetLastError(), v28 = (unsigned int)v27, v27 == 122) )
    {
      std::wstring::wstring(v65, DriverInfoDetailData.InfFileName);
      v32 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a4, v66, v30, v31);
      v35 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v65, v34, v34 - v33, v32);
      v40 = std::_Traits_find<std::char_traits<unsigned short>>(v35, v36, v37, v38, v39) != -1;
      std::wstring::wstring(v56, Src);
      v57 = v40;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      std::vector__anonymous_namespace_::DriverInfo_std::allocator__anonymous_namespace_::DriverInfo___::push_back(
        a1,
        v56);
      std::wstring::_Tidy_deallocate(v56);
      v29 = v65;
    }
    else
    {
      if ( (v27 & 0xE0000000) == 0xE0000000 )
      {
        v28 = (unsigned __int16)v27 | 0x800F0000;
      }
      else if ( v27 > 0 )
      {
        v28 = (unsigned __int16)v27 | 0x80070000;
      }
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\braille.cpp",
        (const char *)v28,
        DriverInfoDatab);
      std::wstring::wstring(v56, Src);
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      std::vector__anonymous_namespace_::DriverInfo_std::allocator__anonymous_namespace_::DriverInfo___::push_back(
        a1,
        v56);
      v29 = v56;
    }
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(Src);
  }
  std::_Hash<std::_Umap_traits<std::wstring,unsigned int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned int,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>(v46);
  return a1;
}

```

## disassembly

```asm
0x18003ded0  push    rbp
0x18003ded2  push    rbx
0x18003ded3  push    rsi
0x18003ded4  push    r12
0x18003ded6  push    r13
0x18003ded8  push    r14
0x18003deda  push    r15
0x18003dedc  lea     rbp, [rsp-0DA0h]
0x18003dee4  sub     rsp, 0EA0h
0x18003deeb  mov     rax, cs:__security_cookie
0x18003def2  xor     rax, rsp
0x18003def5  mov     [rbp+0DD0h+var_40], rax
0x18003defc  mov     r13, r9
0x18003deff  mov     r15, rdx
0x18003df02  mov     rsi, rcx
0x18003df05  mov     [rbp+0DD0h+var_E50], rcx
0x18003df09  mov     [rsp+0ED0h+var_EA0], 0
0x18003df11  call    ??0?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>(void)
0x18003df16  mov     r12d, 1
0x18003df1c  mov     [rsp+0ED0h+var_EA0], r12d
0x18003df21  movups  xmm0, xmmword ptr [r8]
0x18003df25  movups  xmmword ptr [rbp+0DD0h+DeviceInfoData.cbSize], xmm0
0x18003df2c  movups  xmm1, xmmword ptr [r8+10h]
0x18003df31  movups  xmmword ptr [rbp+0DD0h+DeviceInfoData.ClassGuid.Data4+4], xmm1
0x18003df38  lea     r8d, [r12+1]; DriverType
0x18003df3d  lea     rdx, [rbp+0DD0h+DeviceInfoData]; DeviceInfoData
0x18003df44  mov     rcx, [r15]; DeviceInfoSet
0x18003df47  call    cs:__imp_SetupDiBuildDriverInfoList
0x18003df4e  nop     dword ptr [rax+rax+00h]
0x18003df53  test    eax, eax
0x18003df55  jnz     short loc_18003DFA8
0x18003df57  call    cs:__imp_GetLastError
0x18003df5e  nop     dword ptr [rax+rax+00h]
0x18003df63  mov     r9d, eax
0x18003df66  and     eax, 0E0000000h
0x18003df6b  cmp     eax, 0E0000000h
0x18003df70  jnz     short loc_18003DF7F
0x18003df72  movzx   r9d, r9w
0x18003df76  or      r9d, 800F0000h
0x18003df7d  jmp     short loc_18003DF8F
0x18003df7f  test    r9d, r9d
0x18003df82  jle     short loc_18003DF8F
0x18003df84  movzx   r9d, r9w
0x18003df88  or      r9d, 80070000h; char *
0x18003df8f  mov     rcx, [rbp+0DD8h]; this
0x18003df96  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x18003df9d  mov     edx, 143h; void *
0x18003dfa2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003dfa8  lea     rcx, [rsp+0ED0h+var_E90]
0x18003dfad  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,unsigned __int64>::unordered_map<std::wstring,unsigned __int64>(void)
0x18003dfb2  nop
0x18003dfb3  xor     r14d, r14d
0x18003dfb6  cmp     r14d, 3E8h
0x18003dfbd  jnb     loc_18003E4CD
0x18003dfc3  mov     [rbp+0DD0h+var_E00.cbSize], 620h
0x18003dfca  xor     edx, edx; Val
0x18003dfcc  mov     r8d, 61Ch; Size
0x18003dfd2  lea     rcx, [rbp+0DD0h+var_E00.DriverType]; void *
0x18003dfd6  call    memset_0
0x18003dfdb  lea     rax, [rbp+0DD0h+var_E00]
0x18003dfdf  mov     [rsp+0ED0h+DriverInfoData], rax; int
0x18003dfe4  mov     r9d, r14d; MemberIndex
0x18003dfe7  mov     r8d, 2; DriverType
0x18003dfed  lea     rdx, [rbp+0DD0h+DeviceInfoData]; DeviceInfoData
0x18003dff4  mov     rcx, [r15]; DeviceInfoSet
0x18003dff7  call    cs:__imp_SetupDiEnumDriverInfoW
0x18003dffe  nop     dword ptr [rax+rax+00h]
0x18003e003  test    eax, eax
0x18003e005  jz      loc_18003E4CD
0x18003e00b  lea     rdx, [rbp+0DD0h+var_E00.Description]
0x18003e00f  lea     rcx, [rbp+0DD0h+Src]
0x18003e016  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003e01b  nop
0x18003e01c  mov     rdx, [rbp+0DD0h+var_E00.DriverVersion]
0x18003e023  lea     rcx, [rbp+0DD0h+var_798]
0x18003e02a  call    _anonymous_namespace___GetVersionText
0x18003e02f  nop
0x18003e030  mov     r8, rax
0x18003e033  lea     rdx, asc_1802E8310; " ("
0x18003e03a  lea     rcx, [rbp+0DD0h+var_758]
0x18003e041  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18003e046  nop
0x18003e047  lea     r8, asc_1802E8300; ")"
0x18003e04e  mov     rdx, rax
0x18003e051  lea     rcx, [rbp+0DD0h+var_738]
0x18003e058  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003e05d  nop
0x18003e05e  mov     rdx, rax
0x18003e061  lea     rcx, [rbp+0DD0h+Src]
0x18003e068  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003e06d  nop
0x18003e06e  lea     rcx, [rbp+0DD0h+var_738]
0x18003e075  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e07a  nop
0x18003e07b  lea     rcx, [rbp+0DD0h+var_758]
0x18003e082  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e087  nop
0x18003e088  lea     rcx, [rbp+0DD0h+var_798]
0x18003e08f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e094  lea     rcx, [rbp+0DD0h+Src]
0x18003e09b  call    _anonymous_namespace___IsDriverSupportedByNarrator
0x18003e0a0  test    al, al
0x18003e0a2  jz      short loc_18003E11A
0x18003e0a4  xor     ecx, ecx; string
0x18003e0a6  call    cs:__imp_WindowsDeleteString
0x18003e0ad  nop     dword ptr [rax+rax+00h]
0x18003e0b2  mov     [rsp+0ED0h+string], 0
0x18003e0bb  lea     rdx, [rsp+0ED0h+string]; HSTRING *
0x18003e0c0  lea     rcx, aSystemsettings_445; "SystemSettings_Accessibility_Braille_Dr"...
0x18003e0c7  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18003e0cc  mov     rcx, [rbp+0DD8h]; this
0x18003e0d3  test    eax, eax
0x18003e0d5  js      loc_18003E4B8
0x18003e0db  xor     edx, edx; length
0x18003e0dd  mov     rcx, [rsp+0ED0h+string]; string
0x18003e0e2  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e0e9  nop     dword ptr [rax+rax+00h]
0x18003e0ee  mov     rcx, rax
0x18003e0f1  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18003e0f6  mov     r9, rax
0x18003e0f9  mov     r8, rcx
0x18003e0fc  lea     rcx, [rbp+0DD0h+Src]; Src
0x18003e103  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18003e108  nop
0x18003e109  mov     rcx, [rsp+0ED0h+string]; string
0x18003e10e  call    cs:__imp_WindowsDeleteString
0x18003e115  nop     dword ptr [rax+rax+00h]
0x18003e11a  lea     r8, [rbp+0DD0h+Src]
0x18003e121  lea     rdx, [rbp+0DD0h+var_E48]
0x18003e125  lea     rcx, [rsp+0ED0h+var_E90]
0x18003e12a  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::find(std::wstring const &)
0x18003e12f  mov     rcx, [rsp+0ED0h+var_E88]
0x18003e134  lea     r8, [rbp+0DD0h+Src]
0x18003e13b  cmp     [rax], rcx
0x18003e13e  lea     rcx, [rsp+0ED0h+var_E90]
0x18003e143  jnz     short loc_18003E15E
0x18003e145  lea     rdx, [rbp+0DD0h+var_E38]
0x18003e149  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18003e14e  mov     rcx, [rax]
0x18003e151  mov     qword ptr [rcx+30h], 1
0x18003e159  jmp     loc_18003E300
0x18003e15e  lea     rdx, [rbp+0DD0h+var_E28]
0x18003e162  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18003e167  mov     rbx, [rax]
0x18003e16a  inc     qword ptr [rbx+30h]
0x18003e16e  mov     rdx, [rbx+30h]
0x18003e172  lea     rcx, [rbp+0DD0h+var_758]
0x18003e179  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x18003e17e  or      r12d, 2
0x18003e182  mov     [rsp+0ED0h+var_EA0], r12d
0x18003e187  lea     r8, asc_1802E8310; " ("
0x18003e18e  lea     rdx, [rbp+0DD0h+Src]
0x18003e195  lea     rcx, [rbp+0DD0h+var_6D8]
0x18003e19c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003e1a1  nop
0x18003e1a2  lea     r8, [rbp+0DD0h+var_758]
0x18003e1a9  mov     rdx, rax
0x18003e1ac  lea     rcx, [rbp+0DD0h+var_6F8]
0x18003e1b3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18003e1b8  nop
0x18003e1b9  lea     r8, asc_1802E8300; ")"
0x18003e1c0  mov     rdx, rax
0x18003e1c3  lea     rcx, [rbp+0DD0h+var_798]
0x18003e1ca  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003e1cf  nop
0x18003e1d0  lea     rcx, [rbp+0DD0h+var_6F8]
0x18003e1d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e1dc  nop
0x18003e1dd  lea     rcx, [rbp+0DD0h+var_6D8]
0x18003e1e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e1e9  nop
0x18003e1ea  lea     rcx, [rbp+0DD0h+var_758]
0x18003e1f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e1f6  lea     r8, [rbp+0DD0h+var_798]
0x18003e1fd  lea     rdx, [rbp+0DD0h+var_E40]
0x18003e201  lea     rcx, [rsp+0ED0h+var_E90]
0x18003e206  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::find(std::wstring const &)
0x18003e20b  mov     rcx, [rsp+0ED0h+var_E88]
0x18003e210  cmp     [rax], rcx
0x18003e213  jz      loc_18003E2C0
0x18003e219  inc     qword ptr [rbx+30h]
0x18003e21d  mov     rdx, [rbx+30h]
0x18003e221  lea     rcx, [rbp+0DD0h+var_738]
0x18003e228  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x18003e22d  or      r12d, 8
0x18003e231  mov     [rsp+0ED0h+var_EA0], r12d
0x18003e236  lea     r8, asc_1802E8310; " ("
0x18003e23d  lea     rdx, [rbp+0DD0h+Src]
0x18003e244  lea     rcx, [rbp+0DD0h+var_7C0]
0x18003e24b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18003e250  nop
0x18003e251  lea     r8, [rbp+0DD0h+var_738]
0x18003e258  mov     rdx, rax
0x18003e25b  lea     rcx, [rbp+0DD0h+var_698]
0x18003e262  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18003e267  nop
0x18003e268  lea     r8, asc_1802E8300; ")"
0x18003e26f  mov     rdx, rax
0x18003e272  lea     rcx, [rbp+0DD0h+var_6B8]
0x18003e279  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003e27e  mov     rdx, rax
0x18003e281  lea     rcx, [rbp+0DD0h+var_798]
0x18003e288  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003e28d  lea     rcx, [rbp+0DD0h+var_6B8]
0x18003e294  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e299  nop
0x18003e29a  lea     rcx, [rbp+0DD0h+var_698]
0x18003e2a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e2a6  nop
0x18003e2a7  lea     rcx, [rbp+0DD0h+var_7C0]
0x18003e2ae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e2b3  nop
0x18003e2b4  lea     rcx, [rbp+0DD0h+var_738]
0x18003e2bb  jmp     loc_18003E1F1
0x18003e2c0  lea     r8, [rbp+0DD0h+var_798]
0x18003e2c7  lea     rdx, [rbp+0DD0h+var_E18]
0x18003e2cb  lea     rcx, [rsp+0ED0h+var_E90]
0x18003e2d0  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18003e2d5  mov     rcx, [rax]
0x18003e2d8  mov     qword ptr [rcx+30h], 1
0x18003e2e0  lea     rdx, [rbp+0DD0h+var_798]
0x18003e2e7  lea     rcx, [rbp+0DD0h+Src]
0x18003e2ee  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003e2f3  nop
0x18003e2f4  lea     rcx, [rbp+0DD0h+var_798]
0x18003e2fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e300  mov     [rbp+0DD0h+DriverInfoDetailData.cbSize], 630h
0x18003e30a  xor     edx, edx; Val
0x18003e30c  mov     r8d, 62Ch; Size
0x18003e312  lea     rcx, [rbp+0DD0h+DriverInfoDetailData.InfDate]; void *
0x18003e319  call    memset_0
0x18003e31e  mov     [rsp+0ED0h+RequiredSize], 0; RequiredSize
0x18003e327  mov     dword ptr [rsp+0ED0h+DriverInfoData], 630h; int
0x18003e32f  lea     r9, [rbp+0DD0h+DriverInfoDetailData]; DriverInfoDetailData
0x18003e336  lea     r8, [rbp+0DD0h+var_E00]; DriverInfoData
0x18003e33a  lea     rdx, [rbp+0DD0h+DeviceInfoData]; DeviceInfoData
0x18003e341  mov     rcx, [r15]; DeviceInfoSet
0x18003e344  call    cs:__imp_SetupDiGetDriverInfoDetailW
0x18003e34b  nop     dword ptr [rax+rax+00h]
0x18003e350  test    eax, eax
0x18003e352  jnz     loc_18003E3FC
0x18003e358  call    cs:__imp_GetLastError
0x18003e35f  nop     dword ptr [rax+rax+00h]
0x18003e364  mov     r9d, eax
0x18003e367  cmp     eax, 7Ah ; 'z'
0x18003e36a  jz      loc_18003E3FC
0x18003e370  and     eax, 0E0000000h
0x18003e375  cmp     eax, 0E0000000h
0x18003e37a  jnz     short loc_18003E389
0x18003e37c  movzx   r9d, r9w
0x18003e380  or      r9d, 800F0000h
0x18003e387  jmp     short loc_18003E399
0x18003e389  test    r9d, r9d
0x18003e38c  jle     short loc_18003E399
0x18003e38e  movzx   r9d, r9w
0x18003e392  or      r9d, 80070000h; char *
0x18003e399  mov     rcx, [rbp+0DD8h]; this
0x18003e3a0  lea     r8, aShellSystemset_56; "shell\\systemsettingsthreshold\\handler"...
0x18003e3a7  mov     edx, 184h; void *
0x18003e3ac  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003e3b1  lea     rdx, [rbp+0DD0h+Src]
0x18003e3b8  lea     rcx, [rbp+0DD0h+var_7C0]
0x18003e3bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003e3c4  mov     [rbp+0DD0h+var_7A0], 0
0x18003e3cb  xor     eax, eax
0x18003e3cd  mov     [rbp+0DD0h+var_79F], eax
0x18003e3d3  mov     [rbp+0DD0h+var_79B], ax
0x18003e3da  mov     [rbp+0DD0h+var_799], al
0x18003e3e0  lea     rdx, [rbp+0DD0h+var_7C0]
0x18003e3e7  mov     rcx, rsi
0x18003e3ea  call    std__vector__anonymous_namespace___DriverInfo_std__allocator__anonymous_namespace___DriverInfo_____push_back
0x18003e3ef  nop
0x18003e3f0  lea     rcx, [rbp+0DD0h+var_7C0]
0x18003e3f7  jmp     loc_18003E49E
0x18003e3fc  lea     rdx, [rbp+0DD0h+DriverInfoDetailData.InfFileName]
0x18003e403  lea     rcx, [rbp+0DD0h+var_718]
0x18003e40a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003e40f  nop
0x18003e410  mov     r10, [r13+10h]
0x18003e414  mov     rdx, [rbp+0DD0h+var_708]
0x18003e41b  mov     rcx, r13
0x18003e41e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003e423  mov     r9, rax
0x18003e426  mov     r8, rdx
0x18003e429  sub     r8, r10
0x18003e42c  lea     rcx, [rbp+0DD0h+var_718]
0x18003e433  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003e438  mov     rcx, rax
0x18003e43b  mov     [rsp+0ED0h+DriverInfoData], r10
0x18003e440  call    ??$_Traits_find@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18003e445  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e449  setnz   bl
0x18003e44c  lea     rdx, [rbp+0DD0h+Src]
0x18003e453  lea     rcx, [rbp+0DD0h+var_7C0]
0x18003e45a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003e45f  mov     [rbp+0DD0h+var_7A0], bl
0x18003e465  xor     eax, eax
0x18003e467  mov     [rbp+0DD0h+var_79F], eax
0x18003e46d  mov     [rbp+0DD0h+var_79B], ax
0x18003e474  mov     [rbp+0DD0h+var_799], al
  ... truncated ...
```
