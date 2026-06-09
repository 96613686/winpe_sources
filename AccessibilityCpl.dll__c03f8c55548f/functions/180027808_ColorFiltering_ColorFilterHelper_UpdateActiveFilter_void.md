# ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)

- ea: `0x180027808`
- end: `0x180027ee7`
- name: `?UpdateActiveFilter@ColorFilterHelper@ColorFiltering@@SAXXZ`
- size: `1759`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800241b0`

## callees

- `0x1800055c0`
- `0x180014828`
- `0x180014b34`
- `0x1800261ec`
- `0x1800265d4`
- `0x180026810`
- `0x1800272dc`
- `0x180027808`
- `0x180028014`
- `0x180028138`
- `0x18002825c`
- `0x180028380`
- `0x1800283b0`
- `0x18002d1ee`
- `0x18002d220`

## import_xrefs

- `USER32!SetDesktopColorTransform` at `0x180027eae`
- `USER32!SetDesktopColorTransform` at `0x180027eae`
- `mscms!__imp_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z` at `0x180027ea0`
- `mscms!__imp_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z` at `0x180027ea0`

## string_xrefs

- `0x180027879`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void ColorFiltering::ColorFilterHelper::UpdateActiveFilter(void)
{
  char v0; // si
  char v1; // bl
  char v2; // di
  __int64 v3; // rdx
  float v4; // eax
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  const struct _MAGN_COLOR_TRANSFORM *v7; // rcx
  __int64 *v8; // r9
  __int64 *v9; // r8
  __int128 v10; // xmm1
  __int64 *v11; // rax
  __int64 *v12; // [rsp+28h] [rbp-D8h]
  __int64 *v13; // [rsp+30h] [rbp-D0h]
  __int64 *v14; // [rsp+38h] [rbp-C8h]
  __int64 *v15; // [rsp+40h] [rbp-C0h]
  __int64 *v16; // [rsp+48h] [rbp-B8h]
  __int64 *v17; // [rsp+50h] [rbp-B0h]
  __int64 *v18; // [rsp+58h] [rbp-A8h]
  ColorFiltering::Filters *v19; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h]
  __int64 v23; // [rsp+80h] [rbp-80h]
  _QWORD v24[3]; // [rsp+88h] [rbp-78h] BYREF
  __m256i v25; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v26; // [rsp+C0h] [rbp-40h]
  __m128i si128; // [rsp+D0h] [rbp-30h]
  __int128 v28; // [rsp+E0h] [rbp-20h]
  __int128 v29; // [rsp+F0h] [rbp-10h]
  int v30; // [rsp+100h] [rbp+0h]
  float v31[5][5]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v32; // [rsp+180h] [rbp+80h] BYREF
  __int128 v33; // [rsp+190h] [rbp+90h]
  __int128 v34; // [rsp+1A0h] [rbp+A0h]
  __int128 v35; // [rsp+1B0h] [rbp+B0h]
  __int128 v36; // [rsp+1C0h] [rbp+C0h]
  __int128 v37; // [rsp+1D0h] [rbp+D0h]
  int v38; // [rsp+1E0h] [rbp+E0h]
  __int128 v39; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v40; // [rsp+200h] [rbp+100h]
  __int128 v41; // [rsp+210h] [rbp+110h]
  __int128 v42; // [rsp+220h] [rbp+120h]
  __int128 v43; // [rsp+230h] [rbp+130h]
  __int128 v44; // [rsp+240h] [rbp+140h]
  int v45; // [rsp+250h] [rbp+150h]

  v20 = -1;
  v19 = (ColorFiltering::Filters *)0x6400000046LL;
  if ( ColorFiltering::ColorFilterHelper::IsActive() )
  {
    memset(v24, 0, sizeof(v24));
    v0 = 1;
    v1 = 1;
    if ( (unsigned int)ATL::CRegKey::Open(
                         (ATL::CRegKey *)v24,
                         HKEY_CURRENT_USER,
                         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
                         1u) )
      goto LABEL_22;
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"FilterType", &v20) )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      v2 = 1;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&v21,
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\ColorFiltering",
                            1u)
        && !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v21, L"FilterType", &v20) )
      {
        v2 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(v20);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&v21);
    }
    else
    {
      v2 = 0;
    }
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"Intensity", (unsigned int *)&v19 + 1) )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&v21,
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\ColorFiltering",
                            1u)
        && !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v21, L"Intensity", (unsigned int *)&v19 + 1) )
      {
        v0 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(SHIDWORD(v19));
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&v21);
    }
    else
    {
      v0 = 0;
    }
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v24, L"Gain", (unsigned int *)&v19) )
    {
      v21 = 0;
      v22 = 0;
      v23 = 0;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&v21,
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\ColorFiltering",
                            1u)
        && !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v21, L"Gain", (unsigned int *)&v19) )
      {
        v1 = 0;
        ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain((int)v19);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&v21);
    }
    else
    {
      v1 = 0;
    }
    if ( v2 )
LABEL_22:
      v20 = 0;
    if ( v0 )
      HIDWORD(v19) = 100;
    if ( v1 )
      LODWORD(v19) = 70;
    ATL::CRegKey::Close((ATL::CRegKey *)v24);
  }
  memset_0(v31, 0, sizeof(v31));
  switch ( v20 )
  {
    case 0u:
      v4 = 1.0;
      *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::Greyscale;
      *(_OWORD *)&v31[0][4] = xmmword_180035C20;
      *(_OWORD *)&v31[1][3] = xmmword_180035C30;
      v5 = xmmword_180035C50;
      *(_OWORD *)&v31[2][2] = xmmword_180035C40;
      v6 = xmmword_180035C60;
      goto LABEL_43;
    case 1u:
      v4 = 1.0;
      *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::InvertFilter;
      *(_OWORD *)&v31[0][4] = xmmword_1800351A0;
      *(_OWORD *)&v31[1][3] = xmmword_1800351B0;
      v5 = xmmword_1800351D0;
      *(_OWORD *)&v31[2][2] = xmmword_1800351C0;
      v6 = xmmword_1800351E0;
      goto LABEL_43;
    case 2u:
      v4 = 1.0;
      *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::GreyscaleInvert;
      *(_OWORD *)&v31[0][4] = xmmword_180034FE0;
      *(_OWORD *)&v31[1][3] = xmmword_180034FF0;
      v5 = xmmword_180035010;
      *(_OWORD *)&v31[2][2] = xmmword_180035000;
      v6 = xmmword_180035020;
      goto LABEL_43;
    case 3u:
      v25.m256i_i32[1] = ColorFiltering::Filters::_ConvertToPercent((ColorFiltering::Filters *)(unsigned int)v19, v3);
      v18 = qword_180034E80;
      v8 = qword_1800353C0;
      HIDWORD(v26) = v25.m256i_i32[1];
      v17 = qword_180035B30;
      v9 = qword_180035120;
      v25.m256i_i32[0] = 1065353216;
      v16 = qword_180035BA0;
      v10 = 0;
      memset(&v25.m256i_u64[1], 0, 24);
      v15 = qword_180035970;
      v14 = qword_180035740;
      v13 = qword_1800352E0;
      v12 = qword_180035660;
      v11 = qword_1800359E0;
      DWORD2(v26) = 0;
      goto LABEL_38;
    case 4u:
      v25.m256i_i32[5] = ColorFiltering::Filters::_ConvertToPercent((ColorFiltering::Filters *)(unsigned int)v19, v3);
      v18 = qword_180035510;
      v8 = qword_180035270;
      *((_QWORD *)&v26 + 1) = v25.m256i_u32[5];
      v17 = qword_180035890;
      v9 = qword_180035430;
      v16 = qword_1800357B0;
      v10 = 0;
      memset(&v25, 0, 20);
      v15 = qword_1800356D0;
      v14 = qword_180034DF0;
      v13 = qword_1800355F0;
      v12 = qword_180034F60;
      v11 = qword_1800354A0;
      v25.m256i_i64[3] = 1065353216;
LABEL_38:
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v28 = 0;
      v30 = 0;
      v29 = v10;
      *(_QWORD *)&v26 = 0;
      ColorFiltering::Filters::_GetAppearance(&v39, HIDWORD(v19), v9, v8, v11, v12, v13, v14, v15, v16, v17, v18);
      v7 = (const struct _MAGN_COLOR_TRANSFORM *)&v32;
      v38 = v45;
      v32 = v39;
      v33 = v40;
      v34 = v41;
      v35 = v42;
      v36 = v43;
      v37 = v44;
      goto LABEL_39;
    case 5u:
      v25.m256i_i32[2] = ColorFiltering::Filters::_ConvertToPercent((ColorFiltering::Filters *)(unsigned int)v19, v3);
      v25.m256i_i32[7] = v25.m256i_i32[2];
      v25.m256i_i64[0] = 1065353216;
      *(__int64 *)((char *)&v25.m256i_i64[1] + 4) = 0;
      *(__int64 *)((char *)&v25.m256i_i64[2] + 4) = 0x3F80000000000000LL;
      v26 = 0;
      si128 = 0;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      ColorFiltering::Filters::_GetAppearance(
        &v32,
        HIDWORD(v19),
        qword_180035040,
        qword_180034EF0,
        qword_180035A50,
        qword_180035200,
        qword_180035AC0,
        qword_180035580,
        qword_1800350B0,
        qword_180035900,
        qword_180035350,
        qword_180035820);
      v7 = (const struct _MAGN_COLOR_TRANSFORM *)&v39;
      v45 = v38;
      v39 = v32;
      v40 = v33;
      v41 = v34;
      v42 = v35;
      v43 = v36;
      v44 = v37;
LABEL_39:
      ColorFiltering::ColorFilterHelper::GenerateAdaptationFilter(
        v7,
        (const struct _MAGN_COLOR_TRANSFORM *)&v25,
        (struct _MAGN_COLOR_TRANSFORM *)v31);
      goto LABEL_44;
  }
  v4 = *(float *)&dword_1800409A0;
  *(_OWORD *)&v31[0][0] = ColorFiltering::Filters::PassthroughFilter;
  *(_OWORD *)&v31[0][4] = xmmword_180040950;
  *(_OWORD *)&v31[1][3] = xmmword_180040960;
  v5 = xmmword_180040980;
  *(_OWORD *)&v31[2][2] = xmmword_180040970;
  v6 = xmmword_180040990;
LABEL_43:
  v31[4][4] = v4;
  *(_OWORD *)&v31[4][0] = v6;
  *(_OWORD *)&v31[3][1] = v5;
LABEL_44:
  LOBYTE(v3) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::GetImpl'::`2'::impl,
    v3);
  if ( (int)InternalSetAccessibilityColorMatrix((float (*)[5][5])v31) < 0 )
    SetDesktopColorTransform((float *)v31);
  AccessibilitySettingsTelemetry::ColorFilterWithOptions<unsigned long &,unsigned long &,unsigned long &>(
    &v20,
    (char *)&v19 + 4,
    &v19);
}

```

## disassembly

```asm
0x180027808  push    rbp
0x18002780a  push    rbx
0x18002780b  push    rsi
0x18002780c  push    rdi
0x18002780d  push    r12
0x18002780f  push    r14
0x180027811  lea     rbp, [rsp-178h]
0x180027819  sub     rsp, 278h
0x180027820  mov     rax, cs:__security_cookie
0x180027827  xor     rax, rsp
0x18002782a  mov     [rbp+1A0h+var_40], rax
0x180027831  mov     [rsp+2A0h+var_238], 0FFFFFFFFh
0x180027839  mov     dword ptr [rsp+2A0h+var_240+4], 64h ; 'd'
0x180027841  mov     dword ptr [rsp+2A0h+var_240], 46h ; 'F'
0x180027849  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x18002784e  xor     r14d, r14d
0x180027851  test    al, al
0x180027853  jz      loc_180027A2E
0x180027859  mov     r12, 0FFFFFFFF80000001h
0x180027860  mov     [rbp+1A0h+var_218], r14
0x180027864  mov     sil, 1
0x180027867  mov     [rbp+1A0h+var_210], r14
0x18002786b  mov     rdx, r12; hKey
0x18002786e  mov     [rbp+1A0h+var_208], r14
0x180027872  lea     r9d, [r14+1]; unsigned int
0x180027876  mov     bl, sil
0x180027879  lea     r8, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x180027880  lea     rcx, [rbp+1A0h+var_218]; this
0x180027884  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180027889  test    eax, eax
0x18002788b  jnz     loc_180027A07
0x180027891  lea     r8, [rsp+2A0h+var_238]; unsigned int *
0x180027896  lea     rdx, aFiltertype_0; "FilterType"
0x18002789d  lea     rcx, [rbp+1A0h+var_218]; this
0x1800278a1  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800278a6  test    eax, eax
0x1800278a8  jnz     short loc_1800278AF
0x1800278aa  mov     dil, r14b
0x1800278ad  jmp     short loc_18002790E
0x1800278af  mov     r9d, 1; unsigned int
0x1800278b5  mov     [rsp+2A0h+var_230], r14
0x1800278ba  lea     r8, aSoftwareMicros_12; "Software\\Microsoft\\ColorFiltering"
0x1800278c1  mov     [rsp+2A0h+var_228], r14
0x1800278c6  mov     rdx, r12; hKey
0x1800278c9  mov     [rbp+1A0h+var_220], r14
0x1800278cd  lea     rcx, [rsp+2A0h+var_230]; this
0x1800278d2  mov     dil, bl
0x1800278d5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800278da  test    eax, eax
0x1800278dc  jnz     short loc_180027904
0x1800278de  lea     r8, [rsp+2A0h+var_238]; unsigned int *
0x1800278e3  lea     rdx, aFiltertype_0; "FilterType"
0x1800278ea  lea     rcx, [rsp+2A0h+var_230]; this
0x1800278ef  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800278f4  test    eax, eax
0x1800278f6  jnz     short loc_180027904
0x1800278f8  mov     ecx, [rsp+2A0h+var_238]; unsigned int
0x1800278fc  mov     dil, r14b
0x1800278ff  call    ?UpdateTransferSettingsFilterType@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(ulong)
0x180027904  lea     rcx, [rsp+2A0h+var_230]; this
0x180027909  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002790e  lea     r8, [rsp+2A0h+var_240+4]; unsigned int *
0x180027913  lea     rdx, aIntensity_0; "Intensity"
0x18002791a  lea     rcx, [rbp+1A0h+var_218]; this
0x18002791e  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180027923  test    eax, eax
0x180027925  jnz     short loc_18002792C
0x180027927  mov     sil, r14b
0x18002792a  jmp     short loc_180027988
0x18002792c  mov     r9d, 1; unsigned int
0x180027932  mov     [rsp+2A0h+var_230], r14
0x180027937  lea     r8, aSoftwareMicros_12; "Software\\Microsoft\\ColorFiltering"
0x18002793e  mov     [rsp+2A0h+var_228], r14
0x180027943  mov     rdx, r12; hKey
0x180027946  mov     [rbp+1A0h+var_220], r14
0x18002794a  lea     rcx, [rsp+2A0h+var_230]; this
0x18002794f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180027954  test    eax, eax
0x180027956  jnz     short loc_18002797E
0x180027958  lea     r8, [rsp+2A0h+var_240+4]; unsigned int *
0x18002795d  lea     rdx, aIntensity_0; "Intensity"
0x180027964  lea     rcx, [rsp+2A0h+var_230]; this
0x180027969  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18002796e  test    eax, eax
0x180027970  jnz     short loc_18002797E
0x180027972  mov     ecx, dword ptr [rsp+2A0h+var_240+4]; unsigned int
0x180027976  mov     sil, r14b
0x180027979  call    ?UpdateTransferSettingsIntensity@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(ulong)
0x18002797e  lea     rcx, [rsp+2A0h+var_230]; this
0x180027983  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180027988  lea     r8, [rsp+2A0h+var_240]; unsigned int *
0x18002798d  lea     rdx, aGain_0; "Gain"
0x180027994  lea     rcx, [rbp+1A0h+var_218]; this
0x180027998  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18002799d  test    eax, eax
0x18002799f  jnz     short loc_1800279A6
0x1800279a1  mov     bl, r14b
0x1800279a4  jmp     short loc_180027A02
0x1800279a6  mov     r9d, 1; unsigned int
0x1800279ac  mov     [rsp+2A0h+var_230], r14
0x1800279b1  lea     r8, aSoftwareMicros_12; "Software\\Microsoft\\ColorFiltering"
0x1800279b8  mov     [rsp+2A0h+var_228], r14
0x1800279bd  mov     rdx, r12; hKey
0x1800279c0  mov     [rbp+1A0h+var_220], r14
0x1800279c4  lea     rcx, [rsp+2A0h+var_230]; this
0x1800279c9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800279ce  test    eax, eax
0x1800279d0  jnz     short loc_1800279F8
0x1800279d2  lea     r8, [rsp+2A0h+var_240]; unsigned int *
0x1800279d7  lea     rdx, aGain_0; "Gain"
0x1800279de  lea     rcx, [rsp+2A0h+var_230]; this
0x1800279e3  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800279e8  test    eax, eax
0x1800279ea  jnz     short loc_1800279F8
0x1800279ec  mov     ecx, dword ptr [rsp+2A0h+var_240]; unsigned int
0x1800279f0  mov     bl, r14b
0x1800279f3  call    ?UpdateTransferSettingsGain@ColorFilterHelper@ColorFiltering@@SAXK@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(ulong)
0x1800279f8  lea     rcx, [rsp+2A0h+var_230]; this
0x1800279fd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180027a02  test    dil, dil
0x180027a05  jz      short loc_180027A0C
0x180027a07  mov     [rsp+2A0h+var_238], r14d
0x180027a0c  test    sil, sil
0x180027a0f  jz      short loc_180027A19
0x180027a11  mov     dword ptr [rsp+2A0h+var_240+4], 64h ; 'd'
0x180027a19  test    bl, bl
0x180027a1b  jz      short loc_180027A25
0x180027a1d  mov     dword ptr [rsp+2A0h+var_240], 46h ; 'F'
0x180027a25  lea     rcx, [rbp+1A0h+var_218]; this
0x180027a29  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180027a2e  xor     edx, edx; Val
0x180027a30  lea     rcx, [rbp+1A0h+var_190]; void *
0x180027a34  lea     r8d, [rdx+64h]; Size
0x180027a38  call    memset_0
0x180027a3d  mov     eax, [rsp+2A0h+var_238]
0x180027a41  test    eax, eax
0x180027a43  jz      loc_180027E43
0x180027a49  cmp     eax, 1
0x180027a4c  jz      loc_180027E01
0x180027a52  cmp     eax, 2
0x180027a55  jz      loc_180027DBC
0x180027a5b  cmp     eax, 3
0x180027a5e  jz      loc_180027C7D
0x180027a64  cmp     eax, 4
0x180027a67  jz      loc_180027BE5
0x180027a6d  cmp     eax, 5
0x180027a70  jz      short loc_180027AB7
0x180027a72  movaps  xmm0, cs:?PassthroughFilter@Filters@ColorFiltering@@3U_MAGN_COLOR_TRANSFORM@@A; _MAGN_COLOR_TRANSFORM ColorFiltering::Filters::PassthroughFilter
0x180027a79  movaps  xmm1, cs:xmmword_180040950
0x180027a80  mov     eax, cs:dword_1800409A0
0x180027a86  movaps  [rbp+1A0h+var_190], xmm0
0x180027a8a  movaps  xmm0, cs:xmmword_180040960
0x180027a91  movaps  [rbp+1A0h+var_180], xmm1
0x180027a95  movaps  xmm1, cs:xmmword_180040970
0x180027a9c  movaps  [rbp+1A0h+var_170], xmm0
0x180027aa0  movaps  xmm0, cs:xmmword_180040980
0x180027aa7  movaps  [rbp+1A0h+var_160], xmm1
0x180027aab  movaps  xmm1, cs:xmmword_180040990
0x180027ab2  jmp     loc_180027E83
0x180027ab7  mov     ecx, dword ptr [rsp+2A0h+var_240]; this
0x180027abb  call    ?_ConvertToPercent@Filters@ColorFiltering@@YAMK@Z; ColorFiltering::Filters::_ConvertToPercent(ulong)
0x180027ac0  mov     edx, dword ptr [rsp+2A0h+var_240+4]
0x180027ac4  lea     rax, qword_180035820
0x180027acb  mov     [rsp+2A0h+var_248], rax
0x180027ad0  lea     r9, qword_180034EF0
0x180027ad7  xorps   xmm1, xmm1
0x180027ada  movss   dword ptr [rbp+1A0h+var_200+8], xmm0
0x180027adf  lea     rax, qword_180035350
0x180027ae6  movss   dword ptr [rbp+1A0h+var_1E8+4], xmm0
0x180027aeb  mov     [rsp+2A0h+var_250], rax
0x180027af0  lea     r8, qword_180035040
0x180027af7  xorps   xmm0, xmm0
0x180027afa  mov     qword ptr [rbp+1A0h+var_200], 3F800000h
0x180027b02  lea     rax, qword_180035900
0x180027b09  mov     qword ptr [rbp+1A0h+var_200+0Ch], r14
0x180027b0d  mov     [rsp+2A0h+var_258], rax
0x180027b12  lea     rcx, [rbp+1A0h+var_120]
0x180027b19  lea     rax, qword_1800350B0
0x180027b20  mov     [rbp+1A0h+var_1EC], r14d
0x180027b24  mov     [rsp+2A0h+var_260], rax
0x180027b29  lea     rax, qword_180035580
0x180027b30  mov     [rsp+2A0h+var_268], rax
0x180027b35  lea     rax, qword_180035AC0
0x180027b3c  mov     [rsp+2A0h+var_270], rax
0x180027b41  lea     rax, qword_180035200
0x180027b48  mov     [rsp+2A0h+var_278], rax
0x180027b4d  lea     rax, qword_180035A50
0x180027b54  mov     [rsp+2A0h+var_280], rax
0x180027b59  mov     dword ptr [rbp+1A0h+var_1E8], 3F800000h
0x180027b60  movaps  [rbp+1A0h+var_1E0], xmm0
0x180027b64  movaps  [rbp+1A0h+var_1D0], xmm1
0x180027b68  movaps  [rbp+1A0h+var_1C0], xmm0
0x180027b6c  movaps  [rbp+1A0h+var_1B0], xmm1
0x180027b70  mov     [rbp+1A0h+var_1A0], r14d
0x180027b74  call    ?_GetAppearance@Filters@ColorFiltering@@YA?AU_MAGN_COLOR_TRANSFORM@@KAEBU3@000000000@Z; ColorFiltering::Filters::_GetAppearance(ulong,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &)
0x180027b79  movups  xmm0, [rbp+1A0h+var_120]
0x180027b80  mov     eax, [rbp+1A0h+var_C0]
0x180027b86  lea     rcx, [rbp+1A0h+var_B0]
0x180027b8d  movups  xmm1, [rbp+1A0h+var_110]
0x180027b94  mov     [rbp+1A0h+var_50], eax
0x180027b9a  movaps  [rbp+1A0h+var_B0], xmm0
0x180027ba1  movups  xmm0, [rbp+1A0h+var_100]
0x180027ba8  movaps  [rbp+1A0h+var_A0], xmm1
0x180027baf  movups  xmm1, [rbp+1A0h+var_F0]
0x180027bb6  movaps  [rbp+1A0h+var_90], xmm0
0x180027bbd  movups  xmm0, [rbp+1A0h+var_E0]
0x180027bc4  movaps  [rbp+1A0h+var_80], xmm1
0x180027bcb  movups  xmm1, [rbp+1A0h+var_D0]
0x180027bd2  movaps  [rbp+1A0h+var_70], xmm0
0x180027bd9  movaps  [rbp+1A0h+var_60], xmm1
0x180027be0  jmp     loc_180027DAA
0x180027be5  mov     ecx, dword ptr [rsp+2A0h+var_240]; this
0x180027be9  call    ?_ConvertToPercent@Filters@ColorFiltering@@YAMK@Z; ColorFiltering::Filters::_ConvertToPercent(ulong)
0x180027bee  lea     rax, qword_180035510
0x180027bf5  movss   [rbp+1A0h+var_1EC], xmm0
0x180027bfa  mov     [rsp+2A0h+var_248], rax
0x180027bff  lea     r9, qword_180035270
0x180027c06  lea     rax, qword_180035890
0x180027c0d  movss   dword ptr [rbp+1A0h+var_1E0+8], xmm0
0x180027c12  mov     [rsp+2A0h+var_250], rax
0x180027c17  lea     r8, qword_180035430
0x180027c1e  lea     rax, qword_1800357B0
0x180027c25  mov     [rbp-50h], r14d
0x180027c29  mov     [rsp+2A0h+var_258], rax
0x180027c2e  xorps   xmm1, xmm1
0x180027c31  lea     rax, qword_1800356D0
0x180027c38  movaps  [rbp+1A0h+var_200], xmm1
0x180027c3c  mov     [rsp+2A0h+var_260], rax
0x180027c41  lea     rax, qword_180034DF0
0x180027c48  mov     [rsp+2A0h+var_268], rax
0x180027c4d  lea     rax, qword_1800355F0
0x180027c54  mov     [rsp+2A0h+var_270], rax
0x180027c59  lea     rax, qword_180034F60
0x180027c60  mov     [rsp+2A0h+var_278], rax
0x180027c65  lea     rax, qword_1800354A0
0x180027c6c  mov     [rbp+1A0h+var_1E8], 3F800000h
0x180027c74  mov     dword ptr [rbp+1A0h+var_1E0+0Ch], r14d
0x180027c78  jmp     loc_180027D0F
0x180027c7d  mov     ecx, dword ptr [rsp+2A0h+var_240]; this
0x180027c81  call    ?_ConvertToPercent@Filters@ColorFiltering@@YAMK@Z; ColorFiltering::Filters::_ConvertToPercent(ulong)
0x180027c86  lea     rax, qword_180034E80
0x180027c8d  movss   dword ptr [rbp+1A0h+var_200+4], xmm0
0x180027c92  mov     [rsp+2A0h+var_248], rax
0x180027c97  lea     r9, qword_1800353C0
0x180027c9e  lea     rax, qword_180035B30
0x180027ca5  movss   dword ptr [rbp+1A0h+var_1E0+0Ch], xmm0
0x180027caa  mov     [rsp+2A0h+var_250], rax
0x180027caf  lea     r8, qword_180035120
0x180027cb6  lea     rax, qword_180035BA0
0x180027cbd  mov     dword ptr [rbp+1A0h+var_200], 3F800000h
0x180027cc4  mov     [rsp+2A0h+var_258], rax
0x180027cc9  xorps   xmm1, xmm1
0x180027ccc  lea     rax, qword_180035970
0x180027cd3  mov     qword ptr [rbp+1A0h+var_200+8], r14
0x180027cd7  mov     [rsp+2A0h+var_260], rax
0x180027cdc  lea     rax, qword_180035740
0x180027ce3  mov     [rsp+2A0h+var_268], rax
0x180027ce8  lea     rax, qword_1800352E0
0x180027cef  mov     [rsp+2A0h+var_270], rax
0x180027cf4  lea     rax, qword_180035660
0x180027cfb  mov     [rsp+2A0h+var_278], rax
0x180027d00  lea     rax, qword_1800359E0
0x180027d07  movaps  xmmword ptr [rbp-50h], xmm1
0x180027d0b  mov     dword ptr [rbp+1A0h+var_1E0+8], r14d
0x180027d0f  movdqa  xmm0, cs:__xmm@0000000000000000000000003f800000
0x180027d17  lea     rcx, [rbp+1A0h+var_B0]
0x180027d1e  mov     edx, dword ptr [rsp+2A0h+var_240+4]
0x180027d22  movaps  [rbp+1A0h+var_1D0], xmm0
0x180027d26  xorps   xmm0, xmm0
0x180027d29  movaps  [rbp+1A0h+var_1C0], xmm0
0x180027d2d  mov     [rsp+2A0h+var_280], rax
0x180027d32  mov     [rbp+1A0h+var_1A0], r14d
0x180027d36  movaps  [rbp+1A0h+var_1B0], xmm1
0x180027d3a  mov     qword ptr [rbp+1A0h+var_1E0], r14
0x180027d3e  call    ?_GetAppearance@Filters@ColorFiltering@@YA?AU_MAGN_COLOR_TRANSFORM@@KAEBU3@000000000@Z; ColorFiltering::Filters::_GetAppearance(ulong,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &)
0x180027d43  movups  xmm0, [rbp+1A0h+var_B0]
0x180027d4a  mov     eax, [rbp+1A0h+var_50]
0x180027d50  lea     rcx, [rbp+1A0h+var_120]; struct _MAGN_COLOR_TRANSFORM *
0x180027d57  movups  xmm1, [rbp+1A0h+var_A0]
0x180027d5e  mov     [rbp+1A0h+var_C0], eax
0x180027d64  movaps  [rbp+1A0h+var_120], xmm0
0x180027d6b  movups  xmm0, [rbp+1A0h+var_90]
0x180027d72  movaps  [rbp+1A0h+var_110], xmm1
0x180027d79  movups  xmm1, [rbp+1A0h+var_80]
0x180027d80  movaps  [rbp+1A0h+var_100], xmm0
0x180027d87  movups  xmm0, [rbp+1A0h+var_70]
0x180027d8e  movaps  [rbp+1A0h+var_F0], xmm1
0x180027d95  movups  xmm1, [rbp+1A0h+var_60]
0x180027d9c  movaps  [rbp+1A0h+var_E0], xmm0
0x180027da3  movaps  [rbp+1A0h+var_D0], xmm1
0x180027daa  lea     rdx, [rbp+1A0h+var_200]; struct _MAGN_COLOR_TRANSFORM *
0x180027dae  lea     r8, [rbp+1A0h+var_190]; struct _MAGN_COLOR_TRANSFORM *
0x180027db2  call    ?GenerateAdaptationFilter@ColorFilterHelper@ColorFiltering@@CAXAEBU_MAGN_COLOR_TRANSFORM@@0AEAU3@@Z; ColorFiltering::ColorFilterHelper::GenerateAdaptationFilter(_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM const &,_MAGN_COLOR_TRANSFORM &)
0x180027db7  jmp     loc_180027E8E
0x180027dbc  movaps  xmm0, cs:?GreyscaleInvert@Filters@ColorFiltering@@3U_MAGN_COLOR_TRANSFORM@@A; _MAGN_COLOR_TRANSFORM ColorFiltering::Filters::GreyscaleInvert
0x180027dc3  movaps  xmm1, cs:xmmword_180034FE0
0x180027dca  mov     eax, cs:dword_180035030
0x180027dd0  movaps  [rbp+1A0h+var_190], xmm0
0x180027dd4  movaps  xmm0, cs:xmmword_180034FF0
0x180027ddb  movaps  [rbp+1A0h+var_180], xmm1
  ... truncated ...
```
