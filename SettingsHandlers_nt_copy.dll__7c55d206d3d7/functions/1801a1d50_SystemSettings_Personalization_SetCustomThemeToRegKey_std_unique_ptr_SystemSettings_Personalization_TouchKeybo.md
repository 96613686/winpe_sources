# SystemSettings::Personalization::SetCustomThemeToRegKey(std::unique_ptr<SystemSettings::Personalization::TouchKeyboardCustomThemeItemModel,std::default_delete<SystemSettings::Personalization::TouchKeyboardCustomThemeItemModel>> const &)

- ea: `0x1801a1d50`
- end: `0x1801a23b1`
- name: `?SetCustomThemeToRegKey@Personalization@SystemSettings@@YAJAEBV?$unique_ptr@VTouchKeyboardCustomThemeItemModel@Personalization@SystemSettings@@U?$default_delete@VTouchKeyboardCustomThemeItemModel@Personalization@SystemSettings@@@std@@@std@@@Z`
- size: `1633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18018d350`

## callees

- `0x180019a20`
- `0x18001ecfc`
- `0x18004e918`
- `0x18004e954`
- `0x1801a1af8`
- `0x1801a1b48`
- `0x1801a1d50`
- `0x1801a2554`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a2073`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a2090`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a20a9`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a21ff`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a221c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a2235`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a2073`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a2090`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a20a9`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a21ff`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a221c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801a2235`

## string_xrefs

- `0x1801a21b9`: `ChineseSimplifiedImeBackgroundImagePath`
- `0x1801a220b`: `ChineseSimplifiedImeBackgroundImagePath`
- `0x1801a2228`: `ChineseSimplifiedImeBackgroundImagePath`
- `0x1801a202d`: `KeyboardBackgroundImagePath`
- `0x1801a207f`: `KeyboardBackgroundImagePath`
- `0x1801a209c`: `KeyboardBackgroundImagePath`
- `0x1801a1da3`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a1dea`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a1e34`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a1e7e`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a1ec8`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a1f12`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a1f5c`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a1fa6`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a2000`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a2053`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a20e6`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a2133`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a2189`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a21df`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a2274`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a22b9`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a2343`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`
- `0x1801a2382`: `shell\systemsettingsthreshold\handlers\internal\personalize\lib\touchkeyboardpersonalizationdataaccesshelper.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::Personalization::SetCustomThemeToRegKey(SystemSettings::Personalization *a1)
{
  __int64 v2; // r9
  int v3; // eax
  unsigned int v4; // r14d
  __int64 result; // rax
  int v6; // eax
  unsigned int v7; // r14d
  int v8; // eax
  unsigned int v9; // r14d
  int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  unsigned int v13; // r14d
  int v14; // eax
  unsigned int v15; // r14d
  int v16; // eax
  unsigned int v17; // r14d
  int v18; // eax
  unsigned int v19; // r14d
  int v20; // eax
  unsigned int v21; // r14d
  const unsigned __int16 *v22; // r9
  int v23; // eax
  unsigned int v24; // r14d
  int v25; // eax
  unsigned int v26; // r14d
  int v27; // eax
  unsigned int v28; // r14d
  int v29; // eax
  unsigned int v30; // r14d
  const unsigned __int16 *v31; // r9
  int v32; // eax
  unsigned int v33; // r14d
  __int64 v34; // r9
  int v35; // eax
  unsigned int v36; // esi
  int v37; // eax
  unsigned int v38; // esi
  SystemSettings::Personalization *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  unsigned int v42; // ebx
  const char *v43; // r9
  int v44; // eax
  unsigned int v45; // ebx
  int v46[22]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = *(_QWORD *)a1;
  if ( *(_BYTE *)(*(_QWORD *)a1 + 152LL) )
  {
    v3 = SHRegSetString(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
           L"KeyLabelColor",
           *(const unsigned __int16 **)(v2 + 24));
    v4 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B2,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v3,
        v46[0]);
      return v4;
    }
  }
  else if ( *(_BYTE *)(v2 + 153) )
  {
    v6 = SHRegSetString(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
           L"KeyLabelColor",
           *(const unsigned __int16 **)(v2 + 32));
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B6,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v6,
        v46[0]);
      return v7;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 153LL) )
  {
    v8 = SHRegSetString(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
           L"SuggestionTextColor",
           *(const unsigned __int16 **)(*(_QWORD *)a1 + 32LL));
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BB,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v8,
        v46[0]);
      return v9;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 154LL) )
  {
    v10 = SHRegSetString(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"KeyColor",
            *(const unsigned __int16 **)(*(_QWORD *)a1 + 40LL));
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v10,
        v46[0]);
      return v11;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 157LL) )
  {
    v12 = SHRegSetString(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"KeyboardBackgroundSolidColor",
            *(const unsigned __int16 **)(*(_QWORD *)a1 + 64LL));
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C5,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v12,
        v46[0]);
      return v13;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 155LL) )
  {
    v14 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"KeyTransparency",
            *(_DWORD *)(*(_QWORD *)a1 + 48LL));
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CA,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v14,
        v46[0]);
      return v15;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 156LL) )
  {
    v16 = SHRegSetString(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"KeyboardBackgroundType",
            *(const unsigned __int16 **)(*(_QWORD *)a1 + 56LL));
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CF,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v16,
        v46[0]);
      return v17;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 158LL) )
  {
    v18 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"KeyboardBackgroundImageOpacity",
            *(_DWORD *)(*(_QWORD *)a1 + 104LL));
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v18,
        v46[0]);
      return v19;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 159LL) )
  {
    v20 = SHRegSetString(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"KeyboardBackgroundImageStretchType",
            *((const unsigned __int16 **)&SystemSettings::Personalization::c_customThemeBackgroundStretchTypeNames
            + 3 * *(int *)(*(_QWORD *)a1 + 108LL)
            + 2));
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DA,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v20,
        v46[0]);
      return v21;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 160LL) )
  {
    v22 = *(const unsigned __int16 **)(*(_QWORD *)a1 + 112LL);
    if ( v22 )
    {
      v23 = SHRegSetString(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
              L"KeyboardBackgroundImagePath",
              v22);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E1,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalizati"
                        "ondataaccesshelper.cpp",
          (const char *)(unsigned int)v23,
          v46[0]);
        return v24;
      }
    }
    else
    {
      RegDeleteKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\TabletTip\\1.7\\SelectedThemeLight",
        L"KeyboardBackgroundImagePath");
      RegDeleteKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\TabletTip\\1.7\\SelectedThemeDark",
        L"KeyboardBackgroundImagePath");
      RegDeleteKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
        L"KeyboardBackgroundImagePath");
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 208LL) )
  {
    v25 = SHRegSetString(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"AccentColor",
            *(const unsigned __int16 **)(*(_QWORD *)a1 + 96LL));
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1ED,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v25,
        v46[0]);
      return v26;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 211LL) )
  {
    v27 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"ChineseSimplifiedImeBackgroundImageOpacity",
            *(_DWORD *)(*(_QWORD *)a1 + 184LL));
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F2,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v27,
        v46[0]);
      return v28;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 212LL) )
  {
    v29 = SHRegSetString(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"ChineseSimplifiedImeBackgroundImageStretchType",
            *((const unsigned __int16 **)&SystemSettings::Personalization::c_customThemeBackgroundStretchTypeNames
            + 3 * *(int *)(*(_QWORD *)a1 + 188LL)
            + 2));
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F8,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v29,
        v46[0]);
      return v30;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 213LL) )
  {
    v31 = *(const unsigned __int16 **)(*(_QWORD *)a1 + 192LL);
    if ( v31 )
    {
      v32 = SHRegSetString(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
              L"ChineseSimplifiedImeBackgroundImagePath",
              v31);
      v33 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1FF,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalizati"
                        "ondataaccesshelper.cpp",
          (const char *)(unsigned int)v32,
          v46[0]);
        return v33;
      }
    }
    else
    {
      RegDeleteKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\TabletTip\\1.7\\SelectedThemeLight",
        L"ChineseSimplifiedImeBackgroundImagePath");
      RegDeleteKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\TabletTip\\1.7\\SelectedThemeDark",
        L"ChineseSimplifiedImeBackgroundImagePath");
      RegDeleteKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
        L"ChineseSimplifiedImeBackgroundImagePath");
    }
  }
  v34 = *(_QWORD *)a1;
  if ( *(_BYTE *)(*(_QWORD *)a1 + 214LL) )
  {
    v35 = SHRegSetString(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"ChineseSimplifiedImeTextColor",
            *(const unsigned __int16 **)(v34 + 200));
    v36 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20B,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v35,
        v46[0]);
      return v36;
    }
  }
  else if ( *(_BYTE *)(v34 + 153) )
  {
    v37 = SHRegSetString(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\TabletTip\\1.7\\UserCustomTheme",
            L"ChineseSimplifiedImeTextColor",
            *(const unsigned __int16 **)(v34 + 32));
    v38 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20F,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v37,
        v46[0]);
      return v38;
    }
  }
  if ( *(_BYTE *)(*(_QWORD *)a1 + 145LL) )
  {
    SystemSettings::Personalization::ResetTouchKeyboardLightAndDarkThemeRegKeys(a1);
    SystemSettings::Personalization::SetLightAndDarkRegKeyFromCustomTheme(v39);
  }
  try
  {
    if ( *(_BYTE *)(*(_QWORD *)a1 + 210LL) )
    {
      v40 = std::wstring::wstring(v46, *(_QWORD *)(*(_QWORD *)a1 + 176LL));
      SystemSettings::Personalization::SetCurrentSelectingCHSIMETextSizeType(v40);
    }
    if ( *(_BYTE *)(*(_QWORD *)a1 + 209LL)
      && (v41 = SHRegSetString(
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\TabletTip\\1.7",
                  L"ChineseSimplifiedImeHeightType",
                  *(const unsigned __int16 **)(*(_QWORD *)a1 + 168LL)),
          v42 = v41,
          v41 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21F,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalization"
                      "dataaccesshelper.cpp",
        (const char *)(unsigned int)v41,
        v46[0]);
      result = v42;
    }
    else
    {
      v44 = SHRegSetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\TabletTip\\1.7", L"ThemeDataVersion", 2u);
      v45 = v44;
      if ( v44 >= 0 )
      {
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x223,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyboardpersonalizati"
                        "ondataaccesshelper.cpp",
          (const char *)(unsigned int)v44,
          v46[0]);
        result = v45;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x227,
                           (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\touchkeyb"
                                         "oardpersonalizationdataaccesshelper.cpp",
                           v43);
  }
  return result;
}

```

## disassembly

```asm
0x1801a1d50  push    rbx
0x1801a1d52  push    rsi
0x1801a1d53  push    rdi
0x1801a1d54  push    r12
0x1801a1d56  push    r14
0x1801a1d58  push    r15
0x1801a1d5a  sub     rsp, 48h
0x1801a1d5e  mov     rbx, rcx
0x1801a1d61  mov     r9, [rcx]
0x1801a1d64  xor     r12d, r12d
0x1801a1d67  lea     rsi, aSoftwareMicros_45; "Software\\Microsoft\\TabletTip\\1.7\\Us"...
0x1801a1d6e  mov     rdi, 0FFFFFFFF80000001h
0x1801a1d75  cmp     [r9+98h], r12b
0x1801a1d7c  jz      short loc_1801A1DBC
0x1801a1d7e  mov     r9, [r9+18h]; unsigned __int16 *
0x1801a1d82  lea     r8, aKeylabelcolor; "KeyLabelColor"
0x1801a1d89  mov     rdx, rsi; unsigned __int16 *
0x1801a1d8c  mov     rcx, rdi; HKEY
0x1801a1d8f  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a1d94  mov     r14d, eax
0x1801a1d97  test    eax, eax
0x1801a1d99  jns     short loc_1801A1E03
0x1801a1d9b  mov     rcx, [rsp+78h]; this
0x1801a1da0  mov     r9d, eax; char *
0x1801a1da3  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a1daa  mov     edx, 1B2h; void *
0x1801a1daf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a1db4  mov     eax, r14d
0x1801a1db7  jmp     loc_1801A23A2
0x1801a1dbc  cmp     [r9+99h], r12b
0x1801a1dc3  jz      short loc_1801A1E03
0x1801a1dc5  mov     r9, [r9+20h]; unsigned __int16 *
0x1801a1dc9  lea     r8, aKeylabelcolor; "KeyLabelColor"
0x1801a1dd0  mov     rdx, rsi; unsigned __int16 *
0x1801a1dd3  mov     rcx, rdi; HKEY
0x1801a1dd6  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a1ddb  mov     r14d, eax
0x1801a1dde  test    eax, eax
0x1801a1de0  jns     short loc_1801A1E03
0x1801a1de2  mov     rcx, [rsp+78h]; this
0x1801a1de7  mov     r9d, eax; char *
0x1801a1dea  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a1df1  mov     edx, 1B6h; void *
0x1801a1df6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a1dfb  mov     eax, r14d
0x1801a1dfe  jmp     loc_1801A23A2
0x1801a1e03  mov     r9, [rbx]
0x1801a1e06  cmp     [r9+99h], r12b
0x1801a1e0d  jz      short loc_1801A1E4D
0x1801a1e0f  mov     r9, [r9+20h]; unsigned __int16 *
0x1801a1e13  lea     r8, aSuggestiontext; "SuggestionTextColor"
0x1801a1e1a  mov     rdx, rsi; unsigned __int16 *
0x1801a1e1d  mov     rcx, rdi; HKEY
0x1801a1e20  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a1e25  mov     r14d, eax
0x1801a1e28  test    eax, eax
0x1801a1e2a  jns     short loc_1801A1E4D
0x1801a1e2c  mov     rcx, [rsp+78h]; this
0x1801a1e31  mov     r9d, eax; char *
0x1801a1e34  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a1e3b  mov     edx, 1BBh; void *
0x1801a1e40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a1e45  mov     eax, r14d
0x1801a1e48  jmp     loc_1801A23A2
0x1801a1e4d  mov     r9, [rbx]
0x1801a1e50  cmp     [r9+9Ah], r12b
0x1801a1e57  jz      short loc_1801A1E97
0x1801a1e59  mov     r9, [r9+28h]; unsigned __int16 *
0x1801a1e5d  lea     r8, aKeycolor; "KeyColor"
0x1801a1e64  mov     rdx, rsi; unsigned __int16 *
0x1801a1e67  mov     rcx, rdi; HKEY
0x1801a1e6a  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a1e6f  mov     r14d, eax
0x1801a1e72  test    eax, eax
0x1801a1e74  jns     short loc_1801A1E97
0x1801a1e76  mov     rcx, [rsp+78h]; this
0x1801a1e7b  mov     r9d, eax; char *
0x1801a1e7e  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a1e85  mov     edx, 1C0h; void *
0x1801a1e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a1e8f  mov     eax, r14d
0x1801a1e92  jmp     loc_1801A23A2
0x1801a1e97  mov     r9, [rbx]
0x1801a1e9a  cmp     [r9+9Dh], r12b
0x1801a1ea1  jz      short loc_1801A1EE1
0x1801a1ea3  mov     r9, [r9+40h]; unsigned __int16 *
0x1801a1ea7  lea     r8, aKeyboardbackgr_5; "KeyboardBackgroundSolidColor"
0x1801a1eae  mov     rdx, rsi; unsigned __int16 *
0x1801a1eb1  mov     rcx, rdi; HKEY
0x1801a1eb4  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a1eb9  mov     r14d, eax
0x1801a1ebc  test    eax, eax
0x1801a1ebe  jns     short loc_1801A1EE1
0x1801a1ec0  mov     rcx, [rsp+78h]; this
0x1801a1ec5  mov     r9d, eax; char *
0x1801a1ec8  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a1ecf  mov     edx, 1C5h; void *
0x1801a1ed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a1ed9  mov     eax, r14d
0x1801a1edc  jmp     loc_1801A23A2
0x1801a1ee1  mov     r9, [rbx]
0x1801a1ee4  cmp     [r9+9Bh], r12b
0x1801a1eeb  jz      short loc_1801A1F2B
0x1801a1eed  mov     r9d, [r9+30h]; unsigned int
0x1801a1ef1  lea     r8, aKeytransparenc; "KeyTransparency"
0x1801a1ef8  mov     rdx, rsi; unsigned __int16 *
0x1801a1efb  mov     rcx, rdi; HKEY
0x1801a1efe  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801a1f03  mov     r14d, eax
0x1801a1f06  test    eax, eax
0x1801a1f08  jns     short loc_1801A1F2B
0x1801a1f0a  mov     rcx, [rsp+78h]; this
0x1801a1f0f  mov     r9d, eax; char *
0x1801a1f12  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a1f19  mov     edx, 1CAh; void *
0x1801a1f1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a1f23  mov     eax, r14d
0x1801a1f26  jmp     loc_1801A23A2
0x1801a1f2b  mov     r9, [rbx]
0x1801a1f2e  cmp     [r9+9Ch], r12b
0x1801a1f35  jz      short loc_1801A1F75
0x1801a1f37  mov     r9, [r9+38h]; unsigned __int16 *
0x1801a1f3b  lea     r8, aKeyboardbackgr_0; "KeyboardBackgroundType"
0x1801a1f42  mov     rdx, rsi; unsigned __int16 *
0x1801a1f45  mov     rcx, rdi; HKEY
0x1801a1f48  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a1f4d  mov     r14d, eax
0x1801a1f50  test    eax, eax
0x1801a1f52  jns     short loc_1801A1F75
0x1801a1f54  mov     rcx, [rsp+78h]; this
0x1801a1f59  mov     r9d, eax; char *
0x1801a1f5c  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a1f63  mov     edx, 1CFh; void *
0x1801a1f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a1f6d  mov     eax, r14d
0x1801a1f70  jmp     loc_1801A23A2
0x1801a1f75  mov     r9, [rbx]
0x1801a1f78  cmp     [r9+9Eh], r12b
0x1801a1f7f  jz      short loc_1801A1FBF
0x1801a1f81  mov     r9d, [r9+68h]; unsigned int
0x1801a1f85  lea     r8, aKeyboardbackgr_2; "KeyboardBackgroundImageOpacity"
0x1801a1f8c  mov     rdx, rsi; unsigned __int16 *
0x1801a1f8f  mov     rcx, rdi; HKEY
0x1801a1f92  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801a1f97  mov     r14d, eax
0x1801a1f9a  test    eax, eax
0x1801a1f9c  jns     short loc_1801A1FBF
0x1801a1f9e  mov     rcx, [rsp+78h]; this
0x1801a1fa3  mov     r9d, eax; char *
0x1801a1fa6  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a1fad  mov     edx, 1D4h; void *
0x1801a1fb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a1fb7  mov     eax, r14d
0x1801a1fba  jmp     loc_1801A23A2
0x1801a1fbf  mov     rax, [rbx]
0x1801a1fc2  lea     r15, ?c_customThemeBackgroundStretchTypeNames@Personalization@SystemSettings@@3QBUBackgroundImageStretchTypeFullInfo@12@B; SystemSettings::Personalization::BackgroundImageStretchTypeFullInfo const near * const SystemSettings::Personalization::c_customThemeBackgroundStretchTypeNames
0x1801a1fc9  cmp     [rax+9Fh], r12b
0x1801a1fd0  jz      short loc_1801A2019
0x1801a1fd2  movsxd  rax, dword ptr [rax+6Ch]
0x1801a1fd6  lea     r9, [rax+rax*2]
0x1801a1fda  mov     r9, [r15+r9*8+10h]; unsigned __int16 *
0x1801a1fdf  lea     r8, aKeyboardbackgr_3; "KeyboardBackgroundImageStretchType"
0x1801a1fe6  mov     rdx, rsi; unsigned __int16 *
0x1801a1fe9  mov     rcx, rdi; HKEY
0x1801a1fec  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a1ff1  mov     r14d, eax
0x1801a1ff4  test    eax, eax
0x1801a1ff6  jns     short loc_1801A2019
0x1801a1ff8  mov     rcx, [rsp+78h]; this
0x1801a1ffd  mov     r9d, eax; char *
0x1801a2000  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a2007  mov     edx, 1DAh; void *
0x1801a200c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a2011  mov     eax, r14d
0x1801a2014  jmp     loc_1801A23A2
0x1801a2019  mov     rax, [rbx]
0x1801a201c  cmp     [rax+0A0h], r12b
0x1801a2023  jz      loc_1801A20B5
0x1801a2029  mov     r9, [rax+70h]; unsigned __int16 *
0x1801a202d  lea     r8, aKeyboardbackgr_4; "KeyboardBackgroundImagePath"
0x1801a2034  mov     rcx, rdi; HKEY
0x1801a2037  test    r9, r9
0x1801a203a  jz      short loc_1801A206C
0x1801a203c  mov     rdx, rsi; unsigned __int16 *
0x1801a203f  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a2044  mov     r14d, eax
0x1801a2047  test    eax, eax
0x1801a2049  jns     short loc_1801A20B5
0x1801a204b  mov     rcx, [rsp+78h]; this
0x1801a2050  mov     r9d, eax; char *
0x1801a2053  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a205a  mov     edx, 1E1h; void *
0x1801a205f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a2064  mov     eax, r14d
0x1801a2067  jmp     loc_1801A23A2
0x1801a206c  lea     rdx, aSoftwareMicros_77; "Software\\Microsoft\\TabletTip\\1.7\\Se"...
0x1801a2073  call    cs:__imp_RegDeleteKeyValueW
0x1801a207a  nop     dword ptr [rax+rax+00h]
0x1801a207f  lea     r8, aKeyboardbackgr_4; "KeyboardBackgroundImagePath"
0x1801a2086  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\TabletTip\\1.7\\Se"...
0x1801a208d  mov     rcx, rdi; hKey
0x1801a2090  call    cs:__imp_RegDeleteKeyValueW
0x1801a2097  nop     dword ptr [rax+rax+00h]
0x1801a209c  lea     r8, aKeyboardbackgr_4; "KeyboardBackgroundImagePath"
0x1801a20a3  mov     rdx, rsi; lpSubKey
0x1801a20a6  mov     rcx, rdi; hKey
0x1801a20a9  call    cs:__imp_RegDeleteKeyValueW
0x1801a20b0  nop     dword ptr [rax+rax+00h]
0x1801a20b5  mov     r9, [rbx]
0x1801a20b8  cmp     [r9+0D0h], r12b
0x1801a20bf  jz      short loc_1801A20FF
0x1801a20c1  mov     r9, [r9+60h]; unsigned __int16 *
0x1801a20c5  lea     r8, sourceString; "AccentColor"
0x1801a20cc  mov     rdx, rsi; unsigned __int16 *
0x1801a20cf  mov     rcx, rdi; HKEY
0x1801a20d2  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a20d7  mov     r14d, eax
0x1801a20da  test    eax, eax
0x1801a20dc  jns     short loc_1801A20FF
0x1801a20de  mov     rcx, [rsp+78h]; this
0x1801a20e3  mov     r9d, eax; char *
0x1801a20e6  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a20ed  mov     edx, 1EDh; void *
0x1801a20f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a20f7  mov     eax, r14d
0x1801a20fa  jmp     loc_1801A23A2
0x1801a20ff  mov     r9, [rbx]
0x1801a2102  cmp     [r9+0D3h], r12b
0x1801a2109  jz      short loc_1801A214C
0x1801a210b  mov     r9d, [r9+0B8h]; unsigned int
0x1801a2112  lea     r8, aChinesesimplif; "ChineseSimplifiedImeBackgroundImageOpac"...
0x1801a2119  mov     rdx, rsi; unsigned __int16 *
0x1801a211c  mov     rcx, rdi; HKEY
0x1801a211f  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801a2124  mov     r14d, eax
0x1801a2127  test    eax, eax
0x1801a2129  jns     short loc_1801A214C
0x1801a212b  mov     rcx, [rsp+78h]; this
0x1801a2130  mov     r9d, eax; char *
0x1801a2133  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a213a  mov     edx, 1F2h; void *
0x1801a213f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a2144  mov     eax, r14d
0x1801a2147  jmp     loc_1801A23A2
0x1801a214c  mov     rax, [rbx]
0x1801a214f  cmp     [rax+0D4h], r12b
0x1801a2156  jz      short loc_1801A21A2
0x1801a2158  movsxd  rax, dword ptr [rax+0BCh]
0x1801a215f  lea     r9, [rax+rax*2]
0x1801a2163  mov     r9, [r15+r9*8+10h]; unsigned __int16 *
0x1801a2168  lea     r8, aChinesesimplif_1; "ChineseSimplifiedImeBackgroundImageStre"...
0x1801a216f  mov     rdx, rsi; unsigned __int16 *
0x1801a2172  mov     rcx, rdi; HKEY
0x1801a2175  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a217a  mov     r14d, eax
0x1801a217d  test    eax, eax
0x1801a217f  jns     short loc_1801A21A2
0x1801a2181  mov     rcx, [rsp+78h]; this
0x1801a2186  mov     r9d, eax; char *
0x1801a2189  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a2190  mov     edx, 1F8h; void *
0x1801a2195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a219a  mov     eax, r14d
0x1801a219d  jmp     loc_1801A23A2
0x1801a21a2  mov     rax, [rbx]
0x1801a21a5  cmp     [rax+0D5h], r12b
0x1801a21ac  jz      loc_1801A2241
0x1801a21b2  mov     r9, [rax+0C0h]; unsigned __int16 *
0x1801a21b9  lea     r8, aChinesesimplif_3; "ChineseSimplifiedImeBackgroundImagePath"
0x1801a21c0  mov     rcx, rdi; HKEY
0x1801a21c3  test    r9, r9
0x1801a21c6  jz      short loc_1801A21F8
0x1801a21c8  mov     rdx, rsi; unsigned __int16 *
0x1801a21cb  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801a21d0  mov     r14d, eax
0x1801a21d3  test    eax, eax
0x1801a21d5  jns     short loc_1801A2241
0x1801a21d7  mov     rcx, [rsp+78h]; this
0x1801a21dc  mov     r9d, eax; char *
0x1801a21df  lea     r8, aShellSystemset_54; "shell\\systemsettingsthreshold\\handler"...
0x1801a21e6  mov     edx, 1FFh; void *
0x1801a21eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a21f0  mov     eax, r14d
0x1801a21f3  jmp     loc_1801A23A2
0x1801a21f8  lea     rdx, aSoftwareMicros_77; "Software\\Microsoft\\TabletTip\\1.7\\Se"...
0x1801a21ff  call    cs:__imp_RegDeleteKeyValueW
0x1801a2206  nop     dword ptr [rax+rax+00h]
0x1801a220b  lea     r8, aChinesesimplif_3; "ChineseSimplifiedImeBackgroundImagePath"
0x1801a2212  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\TabletTip\\1.7\\Se"...
0x1801a2219  mov     rcx, rdi; hKey
0x1801a221c  call    cs:__imp_RegDeleteKeyValueW
0x1801a2223  nop     dword ptr [rax+rax+00h]
0x1801a2228  lea     r8, aChinesesimplif_3; "ChineseSimplifiedImeBackgroundImagePath"
0x1801a222f  mov     rdx, rsi; lpSubKey
0x1801a2232  mov     rcx, rdi; hKey
0x1801a2235  call    cs:__imp_RegDeleteKeyValueW
0x1801a223c  nop     dword ptr [rax+rax+00h]
0x1801a2241  mov     r9, [rbx]
0x1801a2244  cmp     [r9+0D6h], r12b
0x1801a224b  jz      short loc_1801A228C
  ... truncated ...
```
