# SystemSettings::DataModel::CHighContrastTheme::ApplyNameOverrideToTheme(SystemSettings::DataModel::CHighContrastTheme *)

- ea: `0x180062168`
- end: `0x18006233d`
- name: `?ApplyNameOverrideToTheme@CHighContrastTheme@DataModel@SystemSettings@@CAXPEAV123@@Z`
- size: `469`
- prototype: `void __fastcall(struct SystemSettings::DataModel::CHighContrastTheme *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062bdc`

## callees

- `0x18000c840`
- `0x18004d124`
- `0x180062168`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180062228`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006225a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006228f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800622c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800622f3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180062228`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006225a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006228f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800622c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800622f3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800621a6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800621c1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800621df`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800621fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800621a6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800621c1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800621df`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800621fd`

## string_xrefs

- `0x1800621ba`: `%SystemRoot%\resources\ease of access themes\hcblack.theme`
- `0x18006219c`: `%SystemRoot%\resources\ease of access themes\hcwhite.theme`
- `0x1800621d8`: `%SystemRoot%\resources\ease of access themes\hc1.theme`
- `0x1800621f6`: `%SystemRoot%\resources\ease of access themes\hc2.theme`
- `0x180062239`: `SystemSettings_Accessibility_HighContrast_NotHighContrastTheme`
- `0x18006226b`: `SystemSettings_Accessibility_HighContrast_AquaticContrastTheme`
- `0x180062304`: `SystemSettings_Accessibility_HighContrast_NightSkyContrastTheme`
- `0x1800622a0`: `SystemSettings_Accessibility_HighContrast_DesertContrastTheme`
- `0x1800622d2`: `SystemSettings_Accessibility_HighContrast_DuskContrastTheme`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CHighContrastTheme::ApplyNameOverrideToTheme(
        struct SystemSettings::DataModel::CHighContrastTheme *a1)
{
  unsigned __int16 **v2; // r8
  wchar_t *v3; // rcx
  WCHAR String2[264]; // [rsp+30h] [rbp-858h] BYREF
  WCHAR v5[264]; // [rsp+240h] [rbp-648h] BYREF
  WCHAR v6[264]; // [rsp+450h] [rbp-438h] BYREF
  WCHAR v7[264]; // [rsp+660h] [rbp-228h] BYREF

  SHExpandEnvironmentStringsW(L"%SystemRoot%\\resources\\ease of access themes\\hcwhite.theme", v5, 260);
  SHExpandEnvironmentStringsW(L"%SystemRoot%\\resources\\ease of access themes\\hcblack.theme", String2, 260);
  SHExpandEnvironmentStringsW(L"%SystemRoot%\\resources\\ease of access themes\\hc1.theme", v6, 260);
  SHExpandEnvironmentStringsW(L"%SystemRoot%\\resources\\ease of access themes\\hc2.theme", v7, 260);
  if ( CompareStringOrdinal(*((LPCWCH *)a1 + 32), -1, L"D2085E9E-6DF2-485F-9C52-B3D9804EBEF6", -1, 1) == 2 )
  {
    v3 = L"SystemSettings_Accessibility_HighContrast_NotHighContrastTheme";
  }
  else if ( CompareStringOrdinal(*((LPCWCH *)a1 + 32), -1, String2, -1, 1) == 2 )
  {
    v3 = L"SystemSettings_Accessibility_HighContrast_AquaticContrastTheme";
  }
  else if ( CompareStringOrdinal(*((LPCWCH *)a1 + 32), -1, v5, -1, 1) == 2 )
  {
    v3 = L"SystemSettings_Accessibility_HighContrast_DesertContrastTheme";
  }
  else if ( CompareStringOrdinal(*((LPCWCH *)a1 + 32), -1, v6, -1, 1) == 2 )
  {
    v3 = L"SystemSettings_Accessibility_HighContrast_DuskContrastTheme";
  }
  else
  {
    if ( CompareStringOrdinal(*((LPCWCH *)a1 + 32), -1, v7, -1, 1) != 2 )
      return;
    v3 = L"SystemSettings_Accessibility_HighContrast_NightSkyContrastTheme";
  }
  SystemSettings::DataModel::GetResourceStringById(
    (SystemSettings::DataModel *)v3,
    (const unsigned __int16 *)a1 + 132,
    v2);
}

```

## disassembly

```asm
0x180062168  mov     [rsp+arg_8], rbx
0x18006216d  mov     [rsp+arg_10], rsi
0x180062172  push    rdi
0x180062173  sub     rsp, 880h
0x18006217a  mov     rax, cs:__security_cookie
0x180062181  xor     rax, rsp
0x180062184  mov     [rsp+888h+var_18], rax
0x18006218c  mov     rbx, rcx
0x18006218f  lea     rdx, [rsp+888h+var_648]
0x180062197  mov     edi, 104h
0x18006219c  lea     rcx, aSystemrootReso; "%SystemRoot%\\resources\\ease of access"...
0x1800621a3  mov     r8d, edi
0x1800621a6  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800621ad  nop     dword ptr [rax+rax+00h]
0x1800621b2  mov     r8d, edi
0x1800621b5  lea     rdx, [rsp+888h+String2]
0x1800621ba  lea     rcx, aSystemrootReso_0; "%SystemRoot%\\resources\\ease of access"...
0x1800621c1  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800621c8  nop     dword ptr [rax+rax+00h]
0x1800621cd  mov     r8d, edi
0x1800621d0  lea     rdx, [rsp+888h+var_438]
0x1800621d8  lea     rcx, Src; "%SystemRoot%\\resources\\ease of access"...
0x1800621df  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800621e6  nop     dword ptr [rax+rax+00h]
0x1800621eb  mov     r8d, edi
0x1800621ee  lea     rdx, [rsp+888h+var_228]
0x1800621f6  lea     rcx, aSystemrootReso_1; "%SystemRoot%\\resources\\ease of access"...
0x1800621fd  call    cs:__imp_SHExpandEnvironmentStringsW
0x180062204  nop     dword ptr [rax+rax+00h]
0x180062209  mov     rcx, [rbx+100h]; lpString1
0x180062210  lea     r8, aD2085e9e6df248; "D2085E9E-6DF2-485F-9C52-B3D9804EBEF6"
0x180062217  or      edi, 0FFFFFFFFh
0x18006221a  mov     esi, 1
0x18006221f  mov     r9d, edi; cchCount2
0x180062222  mov     [rsp+888h+bIgnoreCase], esi; bIgnoreCase
0x180062226  mov     edx, edi; cchCount1
0x180062228  call    cs:__imp_CompareStringOrdinal
0x18006222f  nop     dword ptr [rax+rax+00h]
0x180062234  cmp     eax, 2
0x180062237  jnz     short loc_180062245
0x180062239  lea     rcx, aSystemsettings_1258; "SystemSettings_Accessibility_HighContra"...
0x180062240  jmp     loc_18006230B
0x180062245  mov     rcx, [rbx+100h]; lpString1
0x18006224c  lea     r8, [rsp+888h+String2]; lpString2
0x180062251  mov     r9d, edi; cchCount2
0x180062254  mov     [rsp+888h+bIgnoreCase], esi; bIgnoreCase
0x180062258  mov     edx, edi; cchCount1
0x18006225a  call    cs:__imp_CompareStringOrdinal
0x180062261  nop     dword ptr [rax+rax+00h]
0x180062266  cmp     eax, 2
0x180062269  jnz     short loc_180062277
0x18006226b  lea     rcx, aSystemsettings_1209; "SystemSettings_Accessibility_HighContra"...
0x180062272  jmp     loc_18006230B
0x180062277  mov     rcx, [rbx+100h]; lpString1
0x18006227e  lea     r8, [rsp+888h+var_648]; lpString2
0x180062286  mov     r9d, edi; cchCount2
0x180062289  mov     [rsp+888h+bIgnoreCase], esi; bIgnoreCase
0x18006228d  mov     edx, edi; cchCount1
0x18006228f  call    cs:__imp_CompareStringOrdinal
0x180062296  nop     dword ptr [rax+rax+00h]
0x18006229b  cmp     eax, 2
0x18006229e  jnz     short loc_1800622A9
0x1800622a0  lea     rcx, aSystemsettings_1224; "SystemSettings_Accessibility_HighContra"...
0x1800622a7  jmp     short loc_18006230B
0x1800622a9  mov     rcx, [rbx+100h]; lpString1
0x1800622b0  lea     r8, [rsp+888h+var_438]; lpString2
0x1800622b8  mov     r9d, edi; cchCount2
0x1800622bb  mov     [rsp+888h+bIgnoreCase], esi; bIgnoreCase
0x1800622bf  mov     edx, edi; cchCount1
0x1800622c1  call    cs:__imp_CompareStringOrdinal
0x1800622c8  nop     dword ptr [rax+rax+00h]
0x1800622cd  cmp     eax, 2
0x1800622d0  jnz     short loc_1800622DB
0x1800622d2  lea     rcx, aSystemsettings_1043; "SystemSettings_Accessibility_HighContra"...
0x1800622d9  jmp     short loc_18006230B
0x1800622db  mov     rcx, [rbx+100h]; lpString1
0x1800622e2  lea     r8, [rsp+888h+var_228]; lpString2
0x1800622ea  mov     r9d, edi; cchCount2
0x1800622ed  mov     [rsp+888h+bIgnoreCase], esi; bIgnoreCase
0x1800622f1  mov     edx, edi; cchCount1
0x1800622f3  call    cs:__imp_CompareStringOrdinal
0x1800622fa  nop     dword ptr [rax+rax+00h]
0x1800622ff  cmp     eax, 2
0x180062302  jnz     short loc_180062317
0x180062304  lea     rcx, aSystemsettings_1303; "SystemSettings_Accessibility_HighContra"...
0x18006230b  lea     rdx, [rbx+108h]; unsigned __int16 *
0x180062312  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x180062317  mov     rcx, [rsp+888h+var_18]
0x18006231f  xor     rcx, rsp; StackCookie
0x180062322  call    __security_check_cookie
0x180062327  lea     r11, [rsp+888h+var_8]
0x18006232f  mov     rbx, [r11+18h]
0x180062333  mov     rsi, [r11+20h]
0x180062337  mov     rsp, r11
0x18006233a  pop     rdi
0x18006233b  retn
```
