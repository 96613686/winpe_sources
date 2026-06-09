# SystemSettings::Personalization::ColorSetting_ColorMode::SetValue(HSTRING__ *)

- ea: `0x180131fd0`
- end: `0x18013226a`
- name: `?SetValue@ColorSetting_ColorMode@Personalization@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `666`
- prototype: `int(SystemSettings::Personalization::ColorSetting_ColorMode *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000d1c4`
- `0x180019a20`
- `0x180021398`
- `0x18004d1ac`
- `0x18012bbb0`
- `0x180131fd0`
- `0x180133850`
- `0x180199320`
- `0x18019cbd8`
- `0x18019da90`
- `0x18019de60`
- `0x18019e294`
- `0x18019e2e8`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18013205f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18013210b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18013205f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18013210b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180132001`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180132096`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180132166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801321ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013222f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180132248`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180132001`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180132096`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180132166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801321ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013222f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180132248`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180131ff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013203e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801320ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180131ff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013203e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801320ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::Personalization::ColorSetting_ColorMode::SetValue(
        SystemSettings::Personalization::ColorSetting_ColorMode *this,
        HSTRING a2)
{
  const WCHAR *StringRawBuffer; // r14
  HSTRING *v4; // r8
  int ResourceStringById; // eax
  unsigned int v6; // edi
  __int64 v7; // rdx
  HSTRING v8; // rbx
  const WCHAR *v9; // rax
  HSTRING *v10; // r8
  const WCHAR *v11; // rax
  __int64 (__fastcall *v12)(SystemSettings::Personalization::ColorSetting_ColorMode *, HSTRING *); // rdi
  int v13; // eax
  const unsigned __int16 *v14; // r8
  SystemSettings::Personalization::ColorSingleton *v15; // rcx
  _QWORD *v16; // rax
  const unsigned __int16 *v17; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-30h]
  HSTRING v20[4]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  _QWORD *v22; // [rsp+80h] [rbp+30h] BYREF
  HSTRING string; // [rsp+88h] [rbp+38h] BYREF

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  WindowsDeleteString(0);
  string = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                         (SystemSettings::DataModel *)L"SystemSettings_Personalize_ColorMode_Light",
                         &string,
                         v4);
  v6 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    v7 = 428;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
      (const char *)(unsigned int)ResourceStringById,
      bIgnoreCase);
    v8 = string;
    goto LABEL_19;
  }
  v8 = string;
  v9 = WindowsGetStringRawBuffer(string, 0);
  if ( CompareStringOrdinal(v9, -1, StringRawBuffer, -1, 1) == 2 )
  {
    SystemSettings::Personalization::ColorSingleton::set_AppsUseLightMode(1u);
    SystemSettings::Personalization::ColorSingleton::set_SystemUsesLightMode(1u);
    SystemSettings::Personalization::ColorSingleton::set_ShouldShowColorModes(0, 1u);
    LODWORD(v22) = 0;
  }
  else
  {
    WindowsDeleteString(v8);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Personalize_ColorMode_Dark",
                           &string,
                           v10);
    v6 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      v7 = 438;
      goto LABEL_7;
    }
    v8 = string;
    v11 = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(v11, -1, StringRawBuffer, -1, 1) == 2 )
    {
      SystemSettings::Personalization::ColorSingleton::set_AppsUseLightMode(0);
      SystemSettings::Personalization::ColorSingleton::set_SystemUsesLightMode(0);
      SystemSettings::Personalization::ColorSingleton::set_ShouldShowColorModes(0, 1u);
      LODWORD(v22) = 1;
    }
    else
    {
      SystemSettings::Personalization::ColorSingleton::set_ShouldShowColorModes(1u, 1u);
      LODWORD(v22) = 2;
    }
  }
  PersonalizeSettingsTelemetry::ColorModeChanged<enum PersonalizationTelemetryTypes::ColorModeTypes>(&v22);
  v20[0] = 0;
  v12 = *(__int64 (__fastcall **)(SystemSettings::Personalization::ColorSetting_ColorMode *, HSTRING *))(*(_QWORD *)this + 48LL);
  WindowsDeleteString(0);
  v20[0] = 0;
  v13 = v12(this, v20);
  v6 = v13;
  if ( v13 >= 0 )
  {
    if ( SystemSettings::DataModel::IsHstringEqual((SystemSettings::DataModel *)v20[0], (HSTRING)&stru_1802DFE90, v14) )
    {
      SystemSettings::Personalization::ColorSingleton::MarkSettingsUpdated(v15);
      v16 = operator new(0x60u);
      v22 = v16;
      v16[11] = &SystemSettings::Personalization::g_ColorSingleton;
      *v16 = SystemSettings::Personalization::ColorSingleton::TrySaveToThemeIfNeededAsync__ResumeCoro_1;
      *((_DWORD *)v16 + 2) = 65538;
      *((_BYTE *)v16 + 80) = 0;
      SystemSettings::Personalization::ColorSingleton::TrySaveToThemeIfNeededAsync__ResumeCoro_1(v16);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUserPersonalizationTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUserPersonalizationTelemetry>::GetImpl'::`2'::impl) )
      SystemSettings::Personalization::LogChangeofPersonalizationSettings(
        (SystemSettings::Personalization *)L"ColorMode",
        v17);
    WindowsDeleteString(v20[0]);
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
    WindowsDeleteString(v20[0]);
  }
  v20[0] = 0;
LABEL_19:
  WindowsDeleteString(v8);
  return v6;
}

```

## disassembly

```asm
0x180131fd0  mov     [rsp-18h+arg_0], rbx
0x180131fd5  mov     [rsp-18h+arg_8], rsi
0x180131fda  push    rbp
0x180131fdb  push    rdi
0x180131fdc  push    r14
0x180131fde  mov     rbp, rsp
0x180131fe1  sub     rsp, 50h
0x180131fe5  mov     rax, rdx
0x180131fe8  mov     rsi, rcx
0x180131feb  xor     edx, edx; length
0x180131fed  mov     rcx, rax; string
0x180131ff0  call    cs:__imp_WindowsGetStringRawBuffer
0x180131ff7  nop     dword ptr [rax+rax+00h]
0x180131ffc  mov     r14, rax
0x180131fff  xor     ecx, ecx; string
0x180132001  call    cs:__imp_WindowsDeleteString
0x180132008  nop     dword ptr [rax+rax+00h]
0x18013200d  mov     [rbp+string], 0
0x180132015  lea     rdx, [rbp+string]; HSTRING *
0x180132019  lea     rcx, aSystemsettings_68; "SystemSettings_Personalize_ColorMode_Li"...
0x180132020  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180132025  mov     edi, eax
0x180132027  test    eax, eax
0x180132029  jns     short loc_180132035
0x18013202b  mov     edx, 1ACh
0x180132030  jmp     loc_1801320C5
0x180132035  xor     edx, edx; length
0x180132037  mov     rbx, [rbp+string]
0x18013203b  mov     rcx, rbx; string
0x18013203e  call    cs:__imp_WindowsGetStringRawBuffer
0x180132045  nop     dword ptr [rax+rax+00h]
0x18013204a  mov     [rsp+50h+bIgnoreCase], 1; int
0x180132052  or      r9d, 0FFFFFFFFh; cchCount2
0x180132056  mov     r8, r14; lpString2
0x180132059  or      edx, r9d; cchCount1
0x18013205c  mov     rcx, rax; lpString1
0x18013205f  call    cs:__imp_CompareStringOrdinal
0x180132066  nop     dword ptr [rax+rax+00h]
0x18013206b  cmp     eax, 2
0x18013206e  jnz     short loc_180132093
0x180132070  mov     cl, 1; unsigned __int8
0x180132072  call    ?set_AppsUseLightMode@ColorSingleton@Personalization@SystemSettings@@SAJE@Z; SystemSettings::Personalization::ColorSingleton::set_AppsUseLightMode(uchar)
0x180132077  mov     cl, 1; unsigned __int8
0x180132079  call    ?set_SystemUsesLightMode@ColorSingleton@Personalization@SystemSettings@@SAJE@Z; SystemSettings::Personalization::ColorSingleton::set_SystemUsesLightMode(uchar)
0x18013207e  mov     dl, 1; unsigned __int8
0x180132080  xor     ecx, ecx; unsigned __int8
0x180132082  call    ?set_ShouldShowColorModes@ColorSingleton@Personalization@SystemSettings@@SAXEE@Z; SystemSettings::Personalization::ColorSingleton::set_ShouldShowColorModes(uchar,uchar)
0x180132087  mov     dword ptr [rbp+arg_10], 0
0x18013208e  jmp     loc_18013214C
0x180132093  mov     rcx, rbx; string
0x180132096  call    cs:__imp_WindowsDeleteString
0x18013209d  nop     dword ptr [rax+rax+00h]
0x1801320a2  mov     [rbp+string], 0
0x1801320aa  lea     rdx, [rbp+string]; HSTRING *
0x1801320ae  lea     rcx, aSystemsettings_111; "SystemSettings_Personalize_ColorMode_Da"...
0x1801320b5  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801320ba  mov     edi, eax
0x1801320bc  test    eax, eax
0x1801320be  jns     short loc_1801320E1
0x1801320c0  mov     edx, 1B6h; void *
0x1801320c5  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x1801320cc  mov     r9d, eax; char *
0x1801320cf  mov     rcx, [rbp+18h]; this
0x1801320d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801320d8  mov     rbx, [rbp+string]
0x1801320dc  jmp     loc_180132245
0x1801320e1  xor     edx, edx; length
0x1801320e3  mov     rbx, [rbp+string]
0x1801320e7  mov     rcx, rbx; string
0x1801320ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1801320f1  nop     dword ptr [rax+rax+00h]
0x1801320f6  mov     [rsp+50h+bIgnoreCase], 1; int
0x1801320fe  or      r9d, 0FFFFFFFFh; cchCount2
0x180132102  mov     r8, r14; lpString2
0x180132105  or      edx, r9d; cchCount1
0x180132108  mov     rcx, rax; lpString1
0x18013210b  call    cs:__imp_CompareStringOrdinal
0x180132112  nop     dword ptr [rax+rax+00h]
0x180132117  cmp     eax, 2
0x18013211a  jnz     short loc_18013213C
0x18013211c  xor     ecx, ecx; unsigned __int8
0x18013211e  call    ?set_AppsUseLightMode@ColorSingleton@Personalization@SystemSettings@@SAJE@Z; SystemSettings::Personalization::ColorSingleton::set_AppsUseLightMode(uchar)
0x180132123  xor     ecx, ecx; unsigned __int8
0x180132125  call    ?set_SystemUsesLightMode@ColorSingleton@Personalization@SystemSettings@@SAJE@Z; SystemSettings::Personalization::ColorSingleton::set_SystemUsesLightMode(uchar)
0x18013212a  mov     dl, 1; unsigned __int8
0x18013212c  xor     ecx, ecx; unsigned __int8
0x18013212e  call    ?set_ShouldShowColorModes@ColorSingleton@Personalization@SystemSettings@@SAXEE@Z; SystemSettings::Personalization::ColorSingleton::set_ShouldShowColorModes(uchar,uchar)
0x180132133  mov     dword ptr [rbp+arg_10], 1
0x18013213a  jmp     short loc_18013214C
0x18013213c  mov     dl, 1; unsigned __int8
0x18013213e  mov     cl, dl; unsigned __int8
0x180132140  call    ?set_ShouldShowColorModes@ColorSingleton@Personalization@SystemSettings@@SAXEE@Z; SystemSettings::Personalization::ColorSingleton::set_ShouldShowColorModes(uchar,uchar)
0x180132145  mov     dword ptr [rbp+arg_10], 2
0x18013214c  lea     rcx, [rbp+arg_10]
0x180132150  call    ??$ColorModeChanged@W4ColorModeTypes@PersonalizationTelemetryTypes@@@PersonalizeSettingsTelemetry@@SAX$$QEAW4ColorModeTypes@PersonalizationTelemetryTypes@@@Z; PersonalizeSettingsTelemetry::ColorModeChanged<PersonalizationTelemetryTypes::ColorModeTypes>(PersonalizationTelemetryTypes::ColorModeTypes &&)
0x180132155  mov     [rbp+var_20], 0
0x18013215d  mov     rax, [rsi]
0x180132160  mov     rdi, [rax+30h]
0x180132164  xor     ecx, ecx; string
0x180132166  call    cs:__imp_WindowsDeleteString
0x18013216d  nop     dword ptr [rax+rax+00h]
0x180132172  mov     [rbp+var_20], 0
0x18013217a  lea     rdx, [rbp+var_20]
0x18013217e  mov     rcx, rsi
0x180132181  mov     rax, rdi
0x180132184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132189  mov     edi, eax
0x18013218b  test    eax, eax
0x18013218d  jns     short loc_1801321BD
0x18013218f  mov     rcx, [rbp+18h]; this
0x180132193  mov     r9d, eax; char *
0x180132196  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x18013219d  mov     edx, 1C7h; void *
0x1801321a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801321a7  nop
0x1801321a8  mov     rcx, [rbp+var_20]; string
0x1801321ac  call    cs:__imp_WindowsDeleteString
0x1801321b3  nop     dword ptr [rax+rax+00h]
0x1801321b8  jmp     loc_18013223D
0x1801321bd  lea     rdx, stru_1802DFE90; HSTRING
0x1801321c4  mov     rcx, [rbp+var_20]; this
0x1801321c8  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801321cd  test    al, al
0x1801321cf  jz      short loc_18013220E
0x1801321d1  call    ?MarkSettingsUpdated@ColorSingleton@Personalization@SystemSettings@@QEAAXXZ; SystemSettings::Personalization::ColorSingleton::MarkSettingsUpdated(void)
0x1801321d6  mov     ecx, 60h ; '`'; Size
0x1801321db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801321e0  mov     [rbp+arg_10], rax
0x1801321e4  lea     rcx, ?g_ColorSingleton@Personalization@SystemSettings@@3VColorSingleton@12@A; SystemSettings::Personalization::ColorSingleton SystemSettings::Personalization::g_ColorSingleton
0x1801321eb  mov     [rax+58h], rcx
0x1801321ef  lea     rcx, SystemSettings__Personalization__ColorSingleton__TrySaveToThemeIfNeededAsync$_ResumeCoro$1
0x1801321f6  mov     [rax], rcx
0x1801321f9  mov     dword ptr [rax+8], 10002h
0x180132200  xor     ecx, ecx
0x180132202  mov     [rax+50h], cl
0x180132205  mov     rcx, rax
0x180132208  call    SystemSettings__Personalization__ColorSingleton__TrySaveToThemeIfNeededAsync$_ResumeCoro$1
0x18013220d  nop
0x18013220e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightUserPersonalizationTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUserPersonalizationTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUserPersonalizationTelemetry> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUserPersonalizationTelemetry>::GetImpl(void)'::`2'::impl
0x180132215  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUserPersonalizationTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUserPersonalizationTelemetry>::__private_IsEnabled(void)
0x18013221a  test    al, al
0x18013221c  jz      short loc_18013222B
0x18013221e  lea     rcx, aColormode; "ColorMode"
0x180132225  call    ?LogChangeofPersonalizationSettings@Personalization@SystemSettings@@YAXPEBG@Z; SystemSettings::Personalization::LogChangeofPersonalizationSettings(ushort const *)
0x18013222a  nop
0x18013222b  mov     rcx, [rbp+var_20]; string
0x18013222f  call    cs:__imp_WindowsDeleteString
0x180132236  nop     dword ptr [rax+rax+00h]
0x18013223b  xor     edi, edi
0x18013223d  mov     [rbp+var_20], 0
0x180132245  mov     rcx, rbx; string
0x180132248  call    cs:__imp_WindowsDeleteString
0x18013224f  nop     dword ptr [rax+rax+00h]
0x180132254  mov     eax, edi
0x180132256  mov     rbx, [rsp+50h+arg_0]
0x18013225b  mov     rsi, [rsp+50h+arg_8]
0x180132260  add     rsp, 50h
0x180132264  pop     r14
0x180132266  pop     rdi
0x180132267  pop     rbp
0x180132268  retn
```
