# ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)

- ea: `0x1400143ac`
- end: `0x140014cb6`
- name: `?UpdateActiveFilter@ColorFilterHelper@ColorFiltering@@SAXXZ`
- size: `2314`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140010244`

## callees

- `0x140009024`
- `0x140012cbc`
- `0x14001317c`
- `0x140013254`
- `0x1400133cc`
- `0x1400143ac`
- `0x140014de8`
- `0x140014f18`
- `0x140015048`
- `0x140015178`
- `0x140015ac2`
- `0x140015b00`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14001446d`
- `ADVAPI32!RegQueryValueExW` at `0x1400144f4`
- `ADVAPI32!RegQueryValueExW` at `0x140014555`
- `ADVAPI32!RegQueryValueExW` at `0x1400145d9`
- `ADVAPI32!RegQueryValueExW` at `0x14001463a`
- `ADVAPI32!RegQueryValueExW` at `0x1400146be`
- `ADVAPI32!RegQueryValueExW` at `0x14001446d`
- `ADVAPI32!RegQueryValueExW` at `0x1400144f4`
- `ADVAPI32!RegQueryValueExW` at `0x140014555`
- `ADVAPI32!RegQueryValueExW` at `0x1400145d9`
- `ADVAPI32!RegQueryValueExW` at `0x14001463a`
- `ADVAPI32!RegQueryValueExW` at `0x1400146be`
- `ADVAPI32!RegOpenKeyExW` at `0x140014429`
- `ADVAPI32!RegOpenKeyExW` at `0x1400144b3`
- `ADVAPI32!RegOpenKeyExW` at `0x140014598`
- `ADVAPI32!RegOpenKeyExW` at `0x14001467d`
- `ADVAPI32!RegOpenKeyExW` at `0x140014429`
- `ADVAPI32!RegOpenKeyExW` at `0x1400144b3`
- `ADVAPI32!RegOpenKeyExW` at `0x140014598`
- `ADVAPI32!RegOpenKeyExW` at `0x14001467d`
- `ADVAPI32!RegCloseKey` at `0x140014519`
- `ADVAPI32!RegCloseKey` at `0x1400145fe`
- `ADVAPI32!RegCloseKey` at `0x1400146e3`
- `ADVAPI32!RegCloseKey` at `0x140014725`
- `ADVAPI32!RegCloseKey` at `0x140014519`
- `ADVAPI32!RegCloseKey` at `0x1400145fe`
- `ADVAPI32!RegCloseKey` at `0x1400146e3`
- `ADVAPI32!RegCloseKey` at `0x140014725`
- `USER32!SetDesktopColorTransform` at `0x140014c7b`
- `USER32!SetDesktopColorTransform` at `0x140014c7b`
- `mscms!__imp_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z` at `0x140014c6d`
- `mscms!__imp_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z` at `0x140014c6d`

## string_xrefs

- `0x140014418`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)
{
  int v0; // ebx
  char v1; // r12
  char v2; // r15
  HKEY v3; // rsi
  char v4; // r14
  HKEY v5; // rdi
  HKEY v6; // rdi
  HKEY v7; // rdi
  unsigned int v8; // edi
  wil::details *v9; // rcx
  float v10; // eax
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  float v13; // xmm0_4
  const struct _MAGN_COLOR_TRANSFORM *v14; // rcx
  float v15; // xmm1_4
  __int64 *v16; // r9
  __int64 *v17; // r8
  __int64 *v18; // rax
  float v19; // xmm1_4
  unsigned int v20; // r8d
  __int64 *lpcbData; // [rsp+28h] [rbp-D8h]
  __int64 *v22; // [rsp+30h] [rbp-D0h]
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  __int16 v25; // [rsp+68h] [rbp-98h]
  BYTE v26[4]; // [rsp+6Ch] [rbp-94h] BYREF
  BYTE v27[4]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[4]; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  __m256i v31; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-50h]
  __m128i si128; // [rsp+C0h] [rbp-40h]
  __int128 v34; // [rsp+D0h] [rbp-30h]
  __int128 v35; // [rsp+E0h] [rbp-20h]
  int v36; // [rsp+F0h] [rbp-10h]
  float v37[5][5]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v38; // [rsp+170h] [rbp+70h] BYREF
  __int128 v39; // [rsp+180h] [rbp+80h]
  __int128 v40; // [rsp+190h] [rbp+90h]
  __int128 v41; // [rsp+1A0h] [rbp+A0h]
  __int128 v42; // [rsp+1B0h] [rbp+B0h]
  __int128 v43; // [rsp+1C0h] [rbp+C0h]
  int v44; // [rsp+1D0h] [rbp+D0h]
  __int128 v45; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v46; // [rsp+1F0h] [rbp+F0h]
  __int128 v47; // [rsp+200h] [rbp+100h]
  __int128 v48; // [rsp+210h] [rbp+110h]
  __int128 v49; // [rsp+220h] [rbp+120h]
  __int128 v50; // [rsp+230h] [rbp+130h]
  int v51; // [rsp+240h] [rbp+140h]

  v0 = 70;
  *(_DWORD *)Data = -1;
  *(_DWORD *)v26 = 70;
  *(_DWORD *)v27 = 100;
  if ( !ColorFiltering::ColorFilterHelper::IsActive() )
    goto LABEL_42;
  hKey = 0;
  v1 = 1;
  v2 = 1;
  if ( RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
         0,
         1u,
         &hKey) )
  {
    v3 = 0;
LABEL_33:
    *(_DWORD *)Data = 0;
    goto LABEL_34;
  }
  v3 = hKey;
  Type = 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"FilterType", 0, &Type, Data, &cbData) || Type != 4 )
  {
    phkResult = 0;
    v4 = 1;
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\ColorFiltering", 0, 1u, &phkResult) )
    {
      v5 = phkResult;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(phkResult, L"FilterType", 0, &Type, Data, &cbData) && Type == 4 )
      {
        v4 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(*(unsigned int *)Data);
      }
      if ( v5 )
        RegCloseKey(v5);
    }
  }
  else
  {
    v4 = 0;
  }
  Type = 0;
  cbData = 4;
  if ( RegQueryValueExW(v3, L"Intensity", 0, &Type, v27, &cbData) || Type != 4 )
  {
    phkResult = 0;
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\ColorFiltering", 0, 1u, &phkResult) )
    {
      v6 = phkResult;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(phkResult, L"Intensity", 0, &Type, v27, &cbData) && Type == 4 )
      {
        v1 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(*(unsigned int *)v27);
      }
      if ( v6 )
        RegCloseKey(v6);
    }
  }
  else
  {
    v1 = 0;
  }
  Type = 0;
  cbData = 4;
  if ( RegQueryValueExW(v3, L"Gain", 0, &Type, v26, &cbData) || Type != 4 )
  {
    phkResult = 0;
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\ColorFiltering", 0, 1u, &phkResult) )
    {
      v7 = phkResult;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(phkResult, L"Gain", 0, &Type, v26, &cbData) && Type == 4 )
      {
        v2 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(*(unsigned int *)v26);
      }
      if ( v7 )
        RegCloseKey(v7);
    }
  }
  else
  {
    v2 = 0;
  }
  if ( v4 )
    goto LABEL_33;
LABEL_34:
  if ( v1 )
  {
    v8 = 100;
    *(_DWORD *)v27 = 100;
  }
  else
  {
    v8 = *(_DWORD *)v27;
  }
  if ( v2 )
    *(_DWORD *)v26 = 70;
  else
    v0 = *(_DWORD *)v26;
  if ( v3 )
  {
    RegCloseKey(v3);
LABEL_42:
    v0 = *(_DWORD *)v26;
    v8 = *(_DWORD *)v27;
  }
  memset_0(v37, 0, sizeof(v37));
  switch ( *(_DWORD *)Data )
  {
    case 0:
      v10 = 1.0;
      *(_OWORD *)&v37[0][0] = ColorFiltering::Filters::Greyscale;
      *(_OWORD *)&v37[0][4] = xmmword_14001AFB0;
      *(_OWORD *)&v37[1][3] = xmmword_14001AFC0;
      v11 = xmmword_14001AFE0;
      *(_OWORD *)&v37[2][2] = xmmword_14001AFD0;
      v12 = xmmword_14001AFF0;
      goto LABEL_70;
    case 1:
      v10 = 1.0;
      *(_OWORD *)&v37[0][0] = ColorFiltering::Filters::InvertFilter;
      *(_OWORD *)&v37[0][4] = xmmword_14001A3D0;
      *(_OWORD *)&v37[1][3] = xmmword_14001A3E0;
      v11 = xmmword_14001A400;
      *(_OWORD *)&v37[2][2] = xmmword_14001A3F0;
      v12 = xmmword_14001A410;
      goto LABEL_70;
    case 2:
      v10 = 1.0;
      *(_OWORD *)&v37[0][0] = ColorFiltering::Filters::GreyscaleInvert;
      *(_OWORD *)&v37[0][4] = xmmword_14001A210;
      *(_OWORD *)&v37[1][3] = xmmword_14001A220;
      v11 = xmmword_14001A240;
      *(_OWORD *)&v37[2][2] = xmmword_14001A230;
      v12 = xmmword_14001A250;
      goto LABEL_70;
    case 3:
      v19 = 0.0;
      if ( v0 )
      {
        if ( (unsigned int)v0 <= 0x64 )
          v19 = (float)v0 / 100.0;
        else
          v19 = FLOAT_1_0;
      }
      *(float *)&v31.m256i_i32[1] = v19;
      v16 = qword_14001A7B0;
      *((float *)&v32 + 3) = v19;
      v17 = qword_14001A510;
      v31.m256i_i32[0] = 1065353216;
      memset(&v31.m256i_u64[1], 0, 24);
      v22 = qword_14001A6D0;
      lpcbData = qword_14001A9E0;
      v18 = qword_14001AC10;
      DWORD2(v32) = 0;
      goto LABEL_65;
    case 4:
      v15 = 0.0;
      if ( v0 )
      {
        if ( (unsigned int)v0 <= 0x64 )
          v15 = (float)v0 / 100.0;
        else
          v15 = FLOAT_1_0;
      }
      *(float *)&v31.m256i_i32[5] = v15;
      v16 = qword_14001A4A0;
      *((_QWORD *)&v32 + 1) = LODWORD(v15);
      v17 = qword_14001A660;
      memset(&v31, 0, 20);
      v22 = qword_14001A820;
      lpcbData = qword_14001A350;
      v18 = qword_14001A890;
      v31.m256i_i64[3] = 1065353216;
LABEL_65:
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v34 = 0;
      v36 = 0;
      v35 = 0;
      *(_QWORD *)&v32 = 0;
      ColorFiltering::Filters::_GetAppearance(&v45, v8, v17, v16, v18, lpcbData);
      v14 = (const struct _MAGN_COLOR_TRANSFORM *)&v38;
      v44 = v51;
      v38 = v45;
      v39 = v46;
      v40 = v47;
      v41 = v48;
      v42 = v49;
      v43 = v50;
LABEL_66:
      ColorFiltering::ColorFilterHelper::GenerateAdaptationFilter(
        v14,
        (const struct _MAGN_COLOR_TRANSFORM *)&v31,
        (struct _MAGN_COLOR_TRANSFORM *)v37);
      goto LABEL_71;
    case 5:
      v13 = 0.0;
      if ( v0 )
      {
        if ( (unsigned int)v0 <= 0x64 )
          v13 = (float)v0 / 100.0;
        else
          v13 = FLOAT_1_0;
      }
      *(float *)&v31.m256i_i32[2] = v13;
      *(float *)&v31.m256i_i32[7] = v13;
      v31.m256i_i64[0] = 1065353216;
      *(__int64 *)((char *)&v31.m256i_i64[1] + 4) = 0;
      *(__int64 *)((char *)&v31.m256i_i64[2] + 4) = 0x3F80000000000000LL;
      v32 = 0;
      v22 = qword_14001ACF0;
      si128 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      ColorFiltering::Filters::_GetAppearance(
        &v38,
        v8,
        qword_14001A430,
        qword_14001A120,
        qword_14001AE40,
        qword_14001A5F0);
      v14 = (const struct _MAGN_COLOR_TRANSFORM *)&v45;
      v51 = v44;
      v45 = v38;
      v46 = v39;
      v47 = v40;
      v48 = v41;
      v49 = v42;
      v50 = v43;
      goto LABEL_66;
  }
  v10 = *(float *)&dword_1400209C0;
  *(_OWORD *)&v37[0][0] = ColorFiltering::Filters::PassthroughFilter;
  *(_OWORD *)&v37[0][4] = xmmword_140020970;
  *(_OWORD *)&v37[1][3] = xmmword_140020980;
  v11 = xmmword_1400209A0;
  *(_OWORD *)&v37[2][2] = xmmword_140020990;
  v12 = xmmword_1400209B0;
LABEL_70:
  v37[4][4] = v10;
  *(_OWORD *)&v37[4][0] = v12;
  *(_OWORD *)&v37[3][1] = v11;
LABEL_71:
  v20 = *(_DWORD *)Feature_AllowProcessingColorFiltersOnHardware__descriptor;
  if ( (*(_DWORD *)Feature_AllowProcessingColorFiltersOnHardware__descriptor & 4) == 0 )
  {
    phkResult = (HKEY)*wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::GetCachedFeatureEnabledState(
                         v9,
                         &phkResult);
    v20 = (unsigned int)phkResult;
  }
  cbData = 0;
  v25 = 3;
  wil::details::ReportUsageToService(
    (__int64)&qword_1400213A0,
    0x260E88Au,
    (v20 >> 10) & 1,
    (v20 >> 11) & 1,
    (__int64)&cbData,
    1u,
    (int)v22);
  if ( (int)InternalSetAccessibilityColorMatrix((float (*)[5][5])v37) < 0 )
    SetDesktopColorTransform((float *)v37);
  AccessibilitySettingsTelemetry::ColorFilterWithOptions<unsigned long &,unsigned long &,unsigned long &>(
    Data,
    (int *)v27,
    (WINBOOL *)v26);
}

```

## disassembly

```asm
0x1400143ac  push    rbp
0x1400143ae  push    rbx
0x1400143af  push    rsi
0x1400143b0  push    rdi
0x1400143b1  push    r12
0x1400143b3  push    r14
0x1400143b5  push    r15
0x1400143b7  lea     rbp, [rsp-160h]
0x1400143bf  sub     rsp, 260h
0x1400143c6  mov     rax, cs:__security_cookie
0x1400143cd  xor     rax, rsp
0x1400143d0  mov     [rbp+190h+var_40], rax
0x1400143d7  mov     ebx, 46h ; 'F'
0x1400143dc  mov     dword ptr [rsp+290h+Data], 0FFFFFFFFh
0x1400143e4  mov     dword ptr [rsp+290h+var_224], ebx
0x1400143e8  mov     dword ptr [rsp+290h+var_220], 64h ; 'd'
0x1400143f0  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x1400143f5  test    al, al
0x1400143f7  jz      loc_14001472B
0x1400143fd  lea     rax, [rbp+190h+hKey]
0x140014401  mov     [rbp+190h+hKey], 0
0x140014409  mov     r12b, 1
0x14001440c  mov     [rsp+290h+phkResult], rax; phkResult
0x140014411  lea     r9d, [rbx-45h]; samDesired
0x140014415  xor     r8d, r8d; ulOptions
0x140014418  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001441f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140014426  mov     r15b, r12b
0x140014429  call    cs:__imp_RegOpenKeyExW
0x14001442f  test    eax, eax
0x140014431  jnz     loc_1400146F0
0x140014437  mov     rsi, [rbp+190h+hKey]
0x14001443b  lea     r9, [rsp+290h+Type]; lpType
0x140014440  mov     [rsp+290h+Type], eax
0x140014444  lea     rdx, aFiltertype_0; "FilterType"
0x14001444b  lea     rax, [rsp+290h+cbData]
0x140014450  mov     [rsp+290h+cbData], 4
0x140014458  mov     [rsp+290h+lpcbData], rax; lpcbData
0x14001445d  xor     r8d, r8d; lpReserved
0x140014460  lea     rax, [rsp+290h+Data]
0x140014465  mov     rcx, rsi; hKey
0x140014468  mov     [rsp+290h+phkResult], rax; lpData
0x14001446d  call    cs:__imp_RegQueryValueExW
0x140014473  test    eax, eax
0x140014475  jnz     short loc_140014486
0x140014477  cmp     [rsp+290h+Type], 4
0x14001447c  jnz     short loc_140014486
0x14001447e  xor     r14b, r14b
0x140014481  jmp     loc_14001451F
0x140014486  lea     rax, [rsp+290h+var_218]
0x14001448b  mov     [rsp+290h+var_218], 0
0x140014494  mov     r9d, 1; samDesired
0x14001449a  mov     [rsp+290h+phkResult], rax; phkResult
0x14001449f  xor     r8d, r8d; ulOptions
0x1400144a2  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ColorFiltering"
0x1400144a9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400144b0  mov     r14b, r12b
0x1400144b3  call    cs:__imp_RegOpenKeyExW
0x1400144b9  test    eax, eax
0x1400144bb  jnz     short loc_14001451F
0x1400144bd  mov     rdi, [rsp+290h+var_218]
0x1400144c2  lea     r9, [rsp+290h+Type]; lpType
0x1400144c7  mov     [rsp+290h+Type], eax
0x1400144cb  lea     rdx, aFiltertype_0; "FilterType"
0x1400144d2  lea     rax, [rsp+290h+cbData]
0x1400144d7  mov     [rsp+290h+cbData], 4
0x1400144df  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1400144e4  xor     r8d, r8d; lpReserved
0x1400144e7  lea     rax, [rsp+290h+Data]
0x1400144ec  mov     rcx, rdi; hKey
0x1400144ef  mov     [rsp+290h+phkResult], rax; lpData
0x1400144f4  call    cs:__imp_RegQueryValueExW
0x1400144fa  test    eax, eax
0x1400144fc  jnz     short loc_140014511
0x1400144fe  cmp     [rsp+290h+Type], 4
0x140014503  jnz     short loc_140014511
0x140014505  mov     ecx, dword ptr [rsp+290h+Data]; unsigned int
0x140014509  xor     r14b, r14b
0x14001450c  call    ?UpdateTransferSettingsFilterType@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(ulong)
0x140014511  test    rdi, rdi
0x140014514  jz      short loc_14001451F
0x140014516  mov     rcx, rdi; hKey
0x140014519  call    cs:__imp_RegCloseKey
0x14001451f  lea     rax, [rsp+290h+cbData]
0x140014524  mov     [rsp+290h+Type], 0
0x14001452c  mov     [rsp+290h+lpcbData], rax; lpcbData
0x140014531  lea     r9, [rsp+290h+Type]; lpType
0x140014536  lea     rax, [rsp+290h+var_220]
0x14001453b  mov     [rsp+290h+cbData], 4
0x140014543  xor     r8d, r8d; lpReserved
0x140014546  mov     [rsp+290h+phkResult], rax; lpData
0x14001454b  lea     rdx, aIntensity_0; "Intensity"
0x140014552  mov     rcx, rsi; hKey
0x140014555  call    cs:__imp_RegQueryValueExW
0x14001455b  test    eax, eax
0x14001455d  jnz     short loc_14001456E
0x14001455f  cmp     [rsp+290h+Type], 4
0x140014564  jnz     short loc_14001456E
0x140014566  xor     r12b, r12b
0x140014569  jmp     loc_140014604
0x14001456e  lea     rax, [rsp+290h+var_218]
0x140014573  mov     [rsp+290h+var_218], 0
0x14001457c  mov     r9d, 1; samDesired
0x140014582  mov     [rsp+290h+phkResult], rax; phkResult
0x140014587  xor     r8d, r8d; ulOptions
0x14001458a  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ColorFiltering"
0x140014591  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140014598  call    cs:__imp_RegOpenKeyExW
0x14001459e  test    eax, eax
0x1400145a0  jnz     short loc_140014604
0x1400145a2  mov     rdi, [rsp+290h+var_218]
0x1400145a7  lea     r9, [rsp+290h+Type]; lpType
0x1400145ac  mov     [rsp+290h+Type], eax
0x1400145b0  lea     rdx, aIntensity_0; "Intensity"
0x1400145b7  lea     rax, [rsp+290h+cbData]
0x1400145bc  mov     [rsp+290h+cbData], 4
0x1400145c4  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1400145c9  xor     r8d, r8d; lpReserved
0x1400145cc  lea     rax, [rsp+290h+var_220]
0x1400145d1  mov     rcx, rdi; hKey
0x1400145d4  mov     [rsp+290h+phkResult], rax; lpData
0x1400145d9  call    cs:__imp_RegQueryValueExW
0x1400145df  test    eax, eax
0x1400145e1  jnz     short loc_1400145F6
0x1400145e3  cmp     [rsp+290h+Type], 4
0x1400145e8  jnz     short loc_1400145F6
0x1400145ea  mov     ecx, dword ptr [rsp+290h+var_220]; unsigned int
0x1400145ee  xor     r12b, r12b
0x1400145f1  call    ?UpdateTransferSettingsIntensity@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(ulong)
0x1400145f6  test    rdi, rdi
0x1400145f9  jz      short loc_140014604
0x1400145fb  mov     rcx, rdi; hKey
0x1400145fe  call    cs:__imp_RegCloseKey
0x140014604  lea     rax, [rsp+290h+cbData]
0x140014609  mov     [rsp+290h+Type], 0
0x140014611  mov     [rsp+290h+lpcbData], rax; lpcbData
0x140014616  lea     r9, [rsp+290h+Type]; lpType
0x14001461b  lea     rax, [rsp+290h+var_224]
0x140014620  mov     [rsp+290h+cbData], 4
0x140014628  xor     r8d, r8d; lpReserved
0x14001462b  mov     [rsp+290h+phkResult], rax; lpData
0x140014630  lea     rdx, aGain_0; "Gain"
0x140014637  mov     rcx, rsi; hKey
0x14001463a  call    cs:__imp_RegQueryValueExW
0x140014640  test    eax, eax
0x140014642  jnz     short loc_140014653
0x140014644  cmp     [rsp+290h+Type], 4
0x140014649  jnz     short loc_140014653
0x14001464b  xor     r15b, r15b
0x14001464e  jmp     loc_1400146E9
0x140014653  lea     rax, [rsp+290h+var_218]
0x140014658  mov     [rsp+290h+var_218], 0
0x140014661  mov     r9d, 1; samDesired
0x140014667  mov     [rsp+290h+phkResult], rax; phkResult
0x14001466c  xor     r8d, r8d; ulOptions
0x14001466f  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ColorFiltering"
0x140014676  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001467d  call    cs:__imp_RegOpenKeyExW
0x140014683  test    eax, eax
0x140014685  jnz     short loc_1400146E9
0x140014687  mov     rdi, [rsp+290h+var_218]
0x14001468c  lea     r9, [rsp+290h+Type]; lpType
0x140014691  mov     [rsp+290h+Type], eax
0x140014695  lea     rdx, aGain_0; "Gain"
0x14001469c  lea     rax, [rsp+290h+cbData]
0x1400146a1  mov     [rsp+290h+cbData], 4
0x1400146a9  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1400146ae  xor     r8d, r8d; lpReserved
0x1400146b1  lea     rax, [rsp+290h+var_224]
0x1400146b6  mov     rcx, rdi; hKey
0x1400146b9  mov     [rsp+290h+phkResult], rax; lpData
0x1400146be  call    cs:__imp_RegQueryValueExW
0x1400146c4  test    eax, eax
0x1400146c6  jnz     short loc_1400146DB
0x1400146c8  cmp     [rsp+290h+Type], 4
0x1400146cd  jnz     short loc_1400146DB
0x1400146cf  mov     ecx, dword ptr [rsp+290h+var_224]; unsigned int
0x1400146d3  xor     r15b, r15b
0x1400146d6  call    ?UpdateTransferSettingsGain@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(ulong)
0x1400146db  test    rdi, rdi
0x1400146de  jz      short loc_1400146E9
0x1400146e0  mov     rcx, rdi; hKey
0x1400146e3  call    cs:__imp_RegCloseKey
0x1400146e9  test    r14b, r14b
0x1400146ec  jnz     short loc_1400146F2
0x1400146ee  jmp     short loc_1400146FA
0x1400146f0  xor     esi, esi
0x1400146f2  mov     dword ptr [rsp+290h+Data], 0
0x1400146fa  test    r12b, r12b
0x1400146fd  jz      short loc_14001470A
0x1400146ff  mov     edi, 64h ; 'd'
0x140014704  mov     dword ptr [rsp+290h+var_220], edi
0x140014708  jmp     short loc_14001470E
0x14001470a  mov     edi, dword ptr [rsp+290h+var_220]
0x14001470e  test    r15b, r15b
0x140014711  jz      short loc_140014719
0x140014713  mov     dword ptr [rsp+290h+var_224], ebx
0x140014717  jmp     short loc_14001471D
0x140014719  mov     ebx, dword ptr [rsp+290h+var_224]
0x14001471d  test    rsi, rsi
0x140014720  jz      short loc_140014733
0x140014722  mov     rcx, rsi; hKey
0x140014725  call    cs:__imp_RegCloseKey
0x14001472b  mov     ebx, dword ptr [rsp+290h+var_224]
0x14001472f  mov     edi, dword ptr [rsp+290h+var_220]
0x140014733  xor     edx, edx; Val
0x140014735  lea     rcx, [rbp+190h+var_190]; void *
0x140014739  lea     r8d, [rdx+64h]; Size
0x14001473d  call    memset_0
0x140014742  mov     eax, dword ptr [rsp+290h+Data]
0x140014746  test    eax, eax
0x140014748  jz      loc_140014BB6
0x14001474e  cmp     eax, 1
0x140014751  jz      loc_140014B74
0x140014757  cmp     eax, 2
0x14001475a  jz      loc_140014B2F
0x140014760  cmp     eax, 3
0x140014763  jz      loc_1400149C8
0x140014769  cmp     eax, 4
0x14001476c  jz      loc_14001490B
0x140014772  cmp     eax, 5
0x140014775  jz      short loc_1400147BC
0x140014777  movaps  xmm0, cs:?PassthroughFilter@Filters@ColorFiltering@@3U_MAGN_COLOR_TRANSFORM@@A; _MAGN_COLOR_TRANSFORM ColorFiltering::Filters::PassthroughFilter
0x14001477e  movaps  xmm1, cs:xmmword_140020970
0x140014785  mov     eax, cs:dword_1400209C0
0x14001478b  movaps  [rbp+190h+var_190], xmm0
0x14001478f  movaps  xmm0, cs:xmmword_140020980
0x140014796  movaps  [rbp+190h+var_180], xmm1
0x14001479a  movaps  xmm1, cs:xmmword_140020990
0x1400147a1  movaps  [rbp+190h+var_170], xmm0
0x1400147a5  movaps  xmm0, cs:xmmword_1400209A0
0x1400147ac  movaps  [rbp+190h+var_160], xmm1
0x1400147b0  movaps  xmm1, cs:xmmword_1400209B0
0x1400147b7  jmp     loc_140014BF6
0x1400147bc  xorps   xmm0, xmm0
0x1400147bf  test    ebx, ebx
0x1400147c1  jz      short loc_1400147E4
0x1400147c3  cmp     ebx, 64h ; 'd'
0x1400147c6  jbe     short loc_1400147D2
0x1400147c8  movss   xmm0, cs:__real@3f800000
0x1400147d0  jmp     short loc_1400147E4
0x1400147d2  xorps   xmm0, xmm0
0x1400147d5  mov     eax, ebx
0x1400147d7  cvtsi2ss xmm0, rax
0x1400147dc  divss   xmm0, cs:__real@42c80000
0x1400147e4  xorps   xmm1, xmm1
0x1400147e7  movss   dword ptr [rbp+190h+var_200+8], xmm0
0x1400147ec  lea     rax, qword_14001AA50
0x1400147f3  movss   dword ptr [rbp+190h+var_1E8+4], xmm0
0x1400147f8  mov     [rsp+290h+var_238], rax
0x1400147fd  lea     r9, qword_14001A120
0x140014804  xorps   xmm0, xmm0
0x140014807  mov     qword ptr [rbp+190h+var_200], 3F800000h
0x14001480f  lea     rax, qword_14001A580
0x140014816  mov     qword ptr [rbp+190h+var_200+0Ch], 0
0x14001481e  mov     [rsp+290h+var_240], rax
0x140014823  lea     r8, qword_14001A430
0x14001482a  lea     rax, qword_14001AB30
0x140014831  mov     [rbp+190h+var_1EC], 0
0x140014838  mov     [rsp+290h+var_248], rax
0x14001483d  lea     rcx, [rbp+190h+var_120]
0x140014841  lea     rax, qword_14001A2E0
0x140014848  mov     dword ptr [rbp+190h+var_1E8], 3F800000h
0x14001484f  mov     [rsp+290h+var_250], rax
0x140014854  mov     edx, edi
0x140014856  lea     rax, qword_14001A900
0x14001485d  movaps  [rbp+190h+var_1E0], xmm0
0x140014861  mov     [rsp+290h+var_258], rax
0x140014866  lea     rax, qword_14001ACF0
0x14001486d  mov     [rsp+290h+var_260], rax
0x140014872  lea     rax, qword_14001A5F0
0x140014879  mov     [rsp+290h+lpcbData], rax
0x14001487e  lea     rax, qword_14001AE40
0x140014885  mov     [rsp+290h+phkResult], rax
0x14001488a  movaps  [rbp+190h+var_1D0], xmm1
0x14001488e  movaps  [rbp+190h+var_1C0], xmm0
0x140014892  movaps  [rbp+190h+var_1B0], xmm1
0x140014896  mov     [rbp+190h+var_1A0], 0
0x14001489d  call    ?_GetAppearance@Filters@ColorFiltering@@YA?AU_MAGN_COLOR_TRANSFORM@@KAEBU3@000000000@Z; ColorFiltering::Filters::_GetAppearance(ulong,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &)
0x1400148a2  movups  xmm0, [rbp+190h+var_120]
0x1400148a6  mov     eax, [rbp+190h+var_C0]
0x1400148ac  lea     rcx, [rbp+190h+var_B0]
0x1400148b3  movups  xmm1, [rbp+190h+var_110]
0x1400148ba  mov     [rbp+190h+var_50], eax
0x1400148c0  movaps  [rbp+190h+var_B0], xmm0
0x1400148c7  movups  xmm0, [rbp+190h+var_100]
0x1400148ce  movaps  [rbp+190h+var_A0], xmm1
0x1400148d5  movups  xmm1, [rbp+190h+var_F0]
0x1400148dc  movaps  [rbp+190h+var_90], xmm0
0x1400148e3  movups  xmm0, [rbp+190h+var_E0]
0x1400148ea  movaps  [rbp+190h+var_80], xmm1
0x1400148f1  movups  xmm1, [rbp+190h+var_D0]
0x1400148f8  movaps  [rbp+190h+var_70], xmm0
0x1400148ff  movaps  [rbp+190h+var_60], xmm1
0x140014906  jmp     loc_140014B1D
0x14001490b  xorps   xmm1, xmm1
0x14001490e  test    ebx, ebx
0x140014910  jz      short loc_140014933
0x140014912  cmp     ebx, 64h ; 'd'
0x140014915  jbe     short loc_140014921
  ... truncated ...
```
