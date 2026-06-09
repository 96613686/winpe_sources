# CTitleBar::_GetDefaultColors(CTitleBar::TitleBarColorSet *,bool *)

- ea: `0x18000caf0`
- end: `0x18000d65f`
- name: `?_GetDefaultColors@CTitleBar@@AEAAXPEAUTitleBarColorSet@1@PEA_N@Z`
- size: `2927`
- prototype: `void __fastcall(CTitleBar *__hidden this, struct CTitleBar::TitleBarColorSet *, bool *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016320`
- `0x180021be8`
- `0x18002c164`

## callees

- `0x180007b30`
- `0x180008d90`
- `0x180008e70`
- `0x18000caf0`
- `0x18000d668`
- `0x18000d6a8`
- `0x18002d11c`
- `0x18004c498`
- `0x180072010`

## import_xrefs

- `UxTheme!__imp_GetUserColorPreference` at `0x18000cbcc`
- `UxTheme!__imp_GetUserColorPreference` at `0x18000cbcc`
- `UxTheme!__imp_GetColorFromPreference` at `0x18000cbe4`
- `UxTheme!__imp_GetColorFromPreference` at `0x18000cbe4`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d42f`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d443`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d458`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d46d`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d482`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d497`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d4ac`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d4c1`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d4d6`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d4eb`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d500`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d515`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d42f`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d443`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d458`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d46d`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d482`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d497`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d4ac`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d4c1`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d4d6`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d4eb`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d500`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000d515`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000cb38`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000cb38`

## pseudocode

```c
void __fastcall CTitleBar::_GetDefaultColors(CTitleBar *this, struct CTitleBar::TitleBarColorSet *a2, bool *a3)
{
  bool v5; // bl
  int v6; // ebx
  int Color; // ecx
  __int64 v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // r10d
  bool v11; // zf
  int v12; // r15d
  unsigned int v13; // ebx
  int v14; // r14d
  int v15; // r10d
  unsigned int v16; // esi
  unsigned int v17; // eax
  unsigned int v18; // edx
  __m128i v19; // xmm0
  int v20; // eax
  float v21; // xmm0_4
  unsigned int v22; // r15d
  float v23; // xmm0_4
  float v24; // xmm1_4
  unsigned int v25; // r8d
  int v26; // edx
  int v27; // r10d
  unsigned int v28; // edi
  unsigned int v29; // ebx
  float v30; // xmm3_4
  float v31; // xmm4_4
  float v32; // xmm5_4
  float v33; // xmm6_4
  unsigned int v34; // r9d
  float v35; // xmm2_4
  int v36; // eax
  unsigned int v37; // r8d
  float v38; // xmm4_4
  float v39; // xmm5_4
  float v40; // xmm1_4
  int v41; // eax
  unsigned int v42; // edx
  __int64 v43; // rcx
  bool v44; // bl
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  int v52; // eax
  int v53; // eax
  __int128 v54; // xmm1
  __int64 v55; // xmm0_8
  int v56; // eax
  __int64 v57; // [rsp+30h] [rbp-51h]
  __int64 v58; // [rsp+38h] [rbp-49h]
  int v59; // [rsp+38h] [rbp-49h]
  int v60; // [rsp+58h] [rbp-29h] BYREF
  _BYTE pvParam[12]; // [rsp+60h] [rbp-21h] BYREF
  int v62; // [rsp+6Ch] [rbp-15h]
  bool v64; // [rsp+100h] [rbp+7Fh]

  *(_DWORD *)pvParam = 16;
  *(_QWORD *)&pvParam[4] = 0;
  v5 = 0;
  v62 = 0;
  v64 = 0;
  if ( SystemParametersInfoW(0x42u, 0x10u, pvParam, 0) && (pvParam[4] & 1) != 0 )
  {
    *(_DWORD *)a2 = GetSysColor(2) | 0xFF000000;
    *((_DWORD *)a2 + 1) = GetSysColor(3) | 0xFF000000;
    *((_DWORD *)a2 + 2) = GetSysColor(9) | 0xFF000000;
    *((_DWORD *)a2 + 3) = GetSysColor(19) | 0xFF000000;
    *((_DWORD *)a2 + 4) = GetSysColor(5) | 0xFF000000;
    *((_DWORD *)a2 + 5) = GetSysColor(5) | 0xFF000000;
    *((_DWORD *)a2 + 6) = GetSysColor(18) | 0xFF000000;
    *((_DWORD *)a2 + 7) = GetSysColor(18) | 0xFF000000;
    *((_DWORD *)a2 + 8) = GetSysColor(13) | 0xFF000000;
    *((_DWORD *)a2 + 10) = GetSysColor(14) | 0xFF000000;
    *((_DWORD *)a2 + 11) = GetSysColor(13) | 0xFF000000;
    *((_DWORD *)a2 + 13) = GetSysColor(14) | 0xFF000000;
    v54 = *((_OWORD *)a2 + 2);
    *(_OWORD *)((char *)a2 + 56) = *((_OWORD *)a2 + 1);
    v55 = *((_QWORD *)a2 + 6);
    *(_OWORD *)((char *)a2 + 72) = v54;
    *((_QWORD *)a2 + 11) = v55;
    goto LABEL_26;
  }
  v6 = -789517;
  if ( *((_BYTE *)this + 573) || !*((_BYTE *)this + 575) )
  {
    if ( CTitleBar::_IsTitleBarColorized(this) )
    {
      Color = CImmersiveColor::GetColor(4);
    }
    else
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_VTCC>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_VTCC>::GetImpl'::`2'::impl);
      v45 = CImmersiveColor::GetColor(210);
      Color = -789517;
      if ( v45 != -1 )
        Color = -14671840;
    }
  }
  else
  {
    Color = *((_DWORD *)this + 207);
  }
  *(_QWORD *)pvParam = 0;
  *(_DWORD *)a2 = Color | 0xFF000000;
  GetUserColorPreference(pvParam, 0);
  GetColorFromPreference(pvParam, 210, 0, 1);
  if ( (*(_DWORD *)Feature_VTCC__descriptor & 4) == 0 )
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_VTCC>::GetCachedFeatureEnabledState(v8, &v60);
  *(_WORD *)&pvParam[4] = 3;
  *(_DWORD *)pvParam = 0;
  v60 = 3;
  v9 = wil_details_MapReportingKind(3, 1);
  if ( (unsigned int)wil::details::ReportUsageToServiceDirect(
                       (__int64)&qword_180091E28,
                       0x1E36E4Bu,
                       (v10 >> 10) & 1,
                       (v10 >> 11) & 1,
                       v9,
                       v57,
                       v58,
                       3u)
    && g_wil_details_pfnFeatureLoggingHook )
  {
    LOBYTE(v59) = 0;
    g_wil_details_pfnFeatureLoggingHook(31682123, pvParam, 0, 1, &v60, 0, v59, 1);
  }
  if ( *((_BYTE *)this + 573) )
  {
    *(_QWORD *)pvParam = (char *)this + 575;
    goto LABEL_55;
  }
  v11 = *((_BYTE *)this + 575) == 0;
  *(_QWORD *)pvParam = (char *)this + 575;
  if ( v11 )
  {
    *(_QWORD *)pvParam = (char *)this + 575;
LABEL_55:
    if ( CTitleBar::_IsTitleBarColorized(this) )
    {
      v6 = CImmersiveColor::GetColor(4);
    }
    else
    {
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_VTCC>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_VTCC>::GetImpl'::`2'::impl);
      v48 = CImmersiveColor::GetColor(210);
      *(_QWORD *)pvParam = (char *)this + 575;
      if ( v48 != -1 )
        v6 = -14671840;
    }
    goto LABEL_12;
  }
  v6 = *((_DWORD *)this + 207);
LABEL_12:
  v12 = *(_DWORD *)a2;
  v13 = v6 | 0xFF000000;
  v14 = -16777216;
  v15 = BYTE1(v13);
  v60 = v13;
  *((_DWORD *)a2 + 1) = v13;
  *((_DWORD *)a2 + 5) = v13;
  v16 = BYTE2(v12) + 5 * BYTE1(v12) + 2 * (unsigned __int8)v12;
  if ( v16 <= 0x400 )
    v14 = -1;
  *((_DWORD *)a2 + 2) = v14;
  *((_DWORD *)a2 + 6) = v14;
  v17 = 92;
  v18 = v15 + BYTE2(v13) + 4 * v15 + 2 * (unsigned __int8)v13;
  if ( v18 <= 0x400 )
    v17 = 96;
  v19 = _mm_cvtsi32_si128(v17);
  v20 = 0;
  LODWORD(v21) = _mm_cvtepi32_ps(v19).m128_u32[0];
  if ( v18 <= 0x400 )
    v20 = 255;
  v22 = v12 | 0xFF000000;
  *((_DWORD *)a2 + 4) = v22;
  v23 = v21 / 255.0;
  v24 = (float)v20 * v23;
  v25 = ((int)(float)((float)((float)BYTE2(v13) * (float)(1.0 - v23)) + v24) | 0xFFFFFF00) << 16;
  v26 = (unsigned __int8)(int)(float)((float)((float)(unsigned __int8)v13 * (float)(1.0 - v23)) + v24);
  *((_DWORD *)a2 + 3) = v25 | v26 | ((unsigned __int8)(int)(float)((float)((float)v15 * (float)(1.0 - v23)) + v24) << 8);
  *((_DWORD *)a2 + 10) = v14;
  v27 = v25 | v26 | ((unsigned __int8)(int)(float)((float)((float)BYTE1(v13) * (float)(1.0 - v23)) + v24) << 8);
  *((_DWORD *)a2 + 7) = v27;
  v28 = 167772160;
  v29 = 100663296;
  if ( v16 <= 0x400 )
    v28 = 0xFFFFFFF;
  v30 = (float)HIBYTE(v28) / 255.0;
  v31 = (float)BYTE2(v22);
  v32 = (float)BYTE1(v22);
  v33 = (float)(unsigned __int8)v22;
  v34 = (unsigned __int8)(int)(float)((float)((float)(unsigned __int8)v28 * v30) + (float)((float)(1.0 - v30) * v33))
      | (((int)(float)((float)((float)BYTE2(v28) * v30) + (float)((float)(1.0 - v30) * v31)) | 0xFFFFFF00) << 16)
      | ((unsigned __int8)(int)(float)((float)((float)BYTE1(v28) * v30) + (float)((float)(1.0 - v30) * v32)) << 8);
  *((_DWORD *)a2 + 8) = v34;
  if ( v16 <= 0x400 )
    v29 = 201326591;
  v35 = (float)HIBYTE(v29) / 255.0;
  *((_DWORD *)a2 + 14) = v22;
  *((_DWORD *)a2 + 16) = v14;
  *((_DWORD *)a2 + 17) = v27;
  *((_DWORD *)a2 + 18) = v34;
  *((_DWORD *)a2 + 20) = v14;
  v36 = 0;
  v37 = (unsigned __int8)(int)(float)((float)((float)(unsigned __int8)v29 * v35) + (float)((float)(1.0 - v35) * v33))
      | (((int)(float)((float)((float)BYTE2(v29) * v35) + (float)((float)(1.0 - v35) * v31)) | 0xFFFFFF00) << 16)
      | ((unsigned __int8)(int)(float)((float)((float)BYTE1(v29) * v35) + (float)((float)(1.0 - v35) * v32)) << 8);
  v38 = v31 * 0.3937;
  v39 = v32 * 0.3937;
  if ( v16 <= 0x400 )
    v36 = 255;
  *((_DWORD *)a2 + 11) = v37;
  *((_DWORD *)a2 + 21) = v37;
  v40 = (float)v36 * 0.6063;
  v41 = v60;
  v42 = (unsigned __int8)(int)(float)((float)(v33 * 0.3937) + v40)
      | ((unsigned __int8)(int)(float)(v39 + v40) << 8)
      | (((int)(float)(v38 + v40) | 0xFFFFFF00) << 16);
  *((_DWORD *)a2 + 13) = v42;
  *((_DWORD *)a2 + 23) = v42;
  *((_DWORD *)a2 + 15) = v41;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_MicaBackdropInApplicationFrameHostTitlebar>::GetImpl'::`2'::impl);
  *((_DWORD *)a2 + 9) = v28;
  *((_DWORD *)a2 + 19) = v28;
  *((_DWORD *)a2 + 12) = v29;
  *((_DWORD *)a2 + 22) = v29;
  v43 = *((_QWORD *)this + 53);
  if ( !v43 || **(_BYTE **)pvParam )
  {
    v5 = 0;
  }
  else
  {
    v60 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v43 + 40LL))(v43, 0, &v60) >= 0 )
    {
      v44 = v60 != *(_DWORD *)a2;
      v64 = v44;
      *(_DWORD *)a2 = v60;
    }
    else
    {
      v44 = 0;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           2,
           &v60) >= 0 )
    {
      if ( v44 || v60 != *((_DWORD *)a2 + 2) )
        v44 = 1;
      v64 = v44;
      *((_DWORD *)a2 + 2) = v60;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           1,
           &v60) >= 0 )
    {
      if ( v44 || v60 != *((_DWORD *)a2 + 1) )
        v44 = 1;
      v64 = v44;
      *((_DWORD *)a2 + 1) = v60;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           3,
           &v60) >= 0 )
    {
      if ( v44 || v60 != *((_DWORD *)a2 + 3) )
        v44 = 1;
      v64 = v44;
      *((_DWORD *)a2 + 3) = v60;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           4,
           &v60) >= 0 )
    {
      v52 = v60;
      v44 = v44 || v60 != *((_DWORD *)a2 + 4);
      v64 = v44;
      *((_DWORD *)a2 + 4) = v60;
      *((_DWORD *)a2 + 14) = v52;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           6,
           &v60) >= 0 )
    {
      v53 = v60;
      v44 = v44 || v60 != *((_DWORD *)a2 + 6);
      v64 = v44;
      *((_DWORD *)a2 + 6) = v60;
      *((_DWORD *)a2 + 16) = v53;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           8,
           &v60) >= 0 )
    {
      v56 = v60;
      if ( v44 || v60 != *((_DWORD *)a2 + 8) )
        v44 = 1;
      v64 = v44;
      *((_DWORD *)a2 + 8) = v60;
      *((_DWORD *)a2 + 18) = v56;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           9,
           &v60) >= 0 )
    {
      v50 = v60;
      v44 = v44 || v60 != *((_DWORD *)a2 + 10);
      v64 = v44;
      *((_DWORD *)a2 + 10) = v60;
      *((_DWORD *)a2 + 20) = v50;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           10,
           &v60) >= 0 )
    {
      v51 = v60;
      v44 = v44 || v60 != *((_DWORD *)a2 + 11);
      v64 = v44;
      *((_DWORD *)a2 + 11) = v60;
      *((_DWORD *)a2 + 21) = v51;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           11,
           &v60) >= 0 )
    {
      v46 = v60;
      v44 = v44 || v60 != *((_DWORD *)a2 + 13);
      v64 = v44;
      *((_DWORD *)a2 + 13) = v60;
      *((_DWORD *)a2 + 23) = v46;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           5,
           &v60) >= 0 )
    {
      v47 = v60;
      v44 = v44 || v60 != *((_DWORD *)a2 + 5);
      v64 = v44;
      *((_DWORD *)a2 + 5) = v60;
      *((_DWORD *)a2 + 15) = v47;
    }
    if ( (*(int (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 53) + 40LL))(
           *((_QWORD *)this + 53),
           7,
           &v60) >= 0 )
    {
      v49 = v60;
      v5 = v44 || v60 != *((_DWORD *)a2 + 7);
      *((_DWORD *)a2 + 7) = v60;
      *((_DWORD *)a2 + 17) = v49;
    }
    else
    {
      v5 = v64;
    }
  }
LABEL_26:
  if ( a3 )
    *a3 = v5;
}

```

## disassembly

```asm
0x18000caf0  mov     rax, rsp
0x18000caf3  mov     [rax+18h], r8
0x18000caf7  push    rbp
0x18000caf8  push    rbx
0x18000caf9  lea     rbp, [rax-5Fh]
0x18000cafd  sub     rsp, 0C8h
0x18000cb04  mov     [rax-20h], r12
0x18000cb08  lea     r8, [rbp+57h+pvParam]; pvParam
0x18000cb0c  mov     [rax-28h], r13
0x18000cb10  mov     r12, rdx
0x18000cb13  xor     eax, eax
0x18000cb15  mov     dword ptr [rbp+57h+pvParam], 10h
0x18000cb1c  mov     r13, rcx
0x18000cb1f  mov     qword ptr [rbp+57h+pvParam+4], rax
0x18000cb23  xor     bl, bl
0x18000cb25  mov     [rbp+57h+var_6C], eax
0x18000cb28  mov     ecx, 42h ; 'B'; uiAction
0x18000cb2d  mov     [rbp+57h+arg_18], bl
0x18000cb30  xor     r9d, r9d; fWinIni
0x18000cb33  mov     edx, 10h; uiParam
0x18000cb38  call    cs:__imp_SystemParametersInfoW
0x18000cb3e  test    eax, eax
0x18000cb40  jz      short loc_18000CB4C
0x18000cb42  test    [rbp+57h+pvParam+4], 1
0x18000cb46  jnz     loc_18000D42A
0x18000cb4c  cmp     byte ptr [r13+23Dh], 0
0x18000cb54  mov     ebx, 0FFF3F3F3h
0x18000cb59  mov     [rsp+0D0h+arg_0], rsi
0x18000cb61  mov     esi, 0FF202020h
0x18000cb66  mov     [rsp+0C0h], rdi
0x18000cb6e  mov     edi, 0FFFFFFFFh
0x18000cb73  mov     [rsp+0D0h+var_28], r14
0x18000cb7b  mov     [rsp+0D0h+var_30], r15
0x18000cb83  movaps  [rsp+0D0h+var_48+8], xmm6
0x18000cb8b  movaps  [rsp+0D0h+var_58+8], xmm7
0x18000cb93  movaps  [rsp+0D0h+var_68+8], xmm8
0x18000cb99  jnz     loc_18000D245
0x18000cb9f  cmp     byte ptr [r13+23Fh], 0
0x18000cba7  jz      loc_18000D245
0x18000cbad  mov     ecx, [r13+33Ch]
0x18000cbb4  or      ecx, 0FF000000h
0x18000cbba  mov     qword ptr [rbp+57h+pvParam], 0
0x18000cbc2  mov     [r12], ecx
0x18000cbc6  xor     edx, edx
0x18000cbc8  lea     rcx, [rbp+57h+pvParam]
0x18000cbcc  call    cs:__imp_GetUserColorPreference
0x18000cbd2  mov     r9d, 1
0x18000cbd8  lea     rcx, [rbp+57h+pvParam]
0x18000cbdc  xor     r8d, r8d
0x18000cbdf  mov     edx, 0D2h
0x18000cbe4  call    cs:__imp_GetColorFromPreference
0x18000cbea  mov     rax, cs:Feature_VTCC__descriptor
0x18000cbf1  mov     r10d, [rax]
0x18000cbf4  test    r10b, 4
0x18000cbf8  jz      loc_18000D550
0x18000cbfe  xor     eax, eax
0x18000cc00  mov     word ptr [rbp+57h+pvParam+4], 3
0x18000cc06  mov     edx, 1
0x18000cc0b  mov     dword ptr [rbp+57h+pvParam], eax
0x18000cc0e  mov     ecx, 3
0x18000cc13  mov     [rbp+57h+var_80], 3
0x18000cc1a  call    wil_details_MapReportingKind
0x18000cc1f  mov     r9d, r10d
0x18000cc22  mov     byte ptr [rsp+38h], 3
0x18000cc27  shr     r10d, 0Ah
0x18000cc2b  lea     rcx, qword_180091E28
0x18000cc32  and     r10d, 1
0x18000cc36  shr     r9d, 0Bh
0x18000cc3a  mov     r8d, r10d
0x18000cc3d  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000cc41  and     r9d, 1
0x18000cc45  mov     edx, 1E36E4Bh
0x18000cc4a  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000cc4f  test    eax, eax
0x18000cc51  jnz     loc_18000D38F
0x18000cc57  cmp     byte ptr [r13+23Dh], 0
0x18000cc5f  jnz     loc_18000D2B5
0x18000cc65  lea     rdi, [r13+23Fh]
0x18000cc6c  cmp     byte ptr [rdi], 0
0x18000cc6f  mov     qword ptr [rbp+57h+pvParam], rdi
0x18000cc73  jz      loc_18000D366
0x18000cc79  mov     ebx, [r13+33Ch]
0x18000cc80  mov     edi, 0FFFFFFFFh
0x18000cc85  mov     r15d, [r12]
0x18000cc89  or      ebx, 0FF000000h
0x18000cc8f  movss   xmm7, cs:__real@437f0000
0x18000cc97  mov     r14d, 0FF000000h
0x18000cc9d  movss   xmm8, cs:__real@3f800000
0x18000cca6  movzx   eax, r15w
0x18000ccaa  movaps  xmm2, xmm8
0x18000ccae  shr     eax, 8
0x18000ccb1  movzx   r11d, bx
0x18000ccb5  mov     r10d, r11d
0x18000ccb8  movzx   r9d, bl
0x18000ccbc  shr     r10d, 8
0x18000ccc0  lea     ecx, [rax+rax*4]
0x18000ccc3  mov     [rbp+57h+var_80], ebx
0x18000ccc6  mov     eax, r15d
0x18000ccc9  mov     [r12+4], ebx
0x18000ccce  shr     eax, 10h
0x18000ccd1  movzx   eax, al
0x18000ccd4  add     ecx, eax
0x18000ccd6  mov     [r12+14h], ebx
0x18000ccdb  movzx   eax, r15b
0x18000ccdf  lea     esi, [rcx+rax*2]
0x18000cce2  mov     eax, ebx
0x18000cce4  shr     eax, 10h
0x18000cce7  movzx   r8d, al
0x18000cceb  cmp     esi, 400h
0x18000ccf1  cmovbe  r14d, edi
0x18000ccf5  mov     [r12+8], r14d
0x18000ccfa  lea     eax, [r10+r8]
0x18000ccfe  mov     [r12+18h], r14d
0x18000cd03  lea     ecx, [rax+r10*4]
0x18000cd07  mov     eax, 5Ch ; '\'
0x18000cd0c  lea     edx, [rcx+r9*2]
0x18000cd10  mov     ecx, 60h ; '`'
0x18000cd15  cmp     edx, 400h
0x18000cd1b  cmovbe  eax, ecx
0x18000cd1e  mov     ecx, 0FFh
0x18000cd23  movd    xmm0, eax
0x18000cd27  xor     eax, eax
0x18000cd29  cvtdq2ps xmm0, xmm0
0x18000cd2c  cmp     edx, 400h
0x18000cd32  cmovbe  eax, ecx
0x18000cd35  or      r15d, 0FF000000h
0x18000cd3c  mov     [r12+10h], r15d
0x18000cd41  divss   xmm0, xmm7
0x18000cd45  movd    xmm1, eax
0x18000cd49  subss   xmm2, xmm0
0x18000cd4d  cvtdq2ps xmm1, xmm1
0x18000cd50  mulss   xmm1, xmm0
0x18000cd54  movd    xmm0, r8d
0x18000cd59  cvtdq2ps xmm0, xmm0
0x18000cd5c  mulss   xmm0, xmm2
0x18000cd60  addss   xmm0, xmm1
0x18000cd64  cvttss2si eax, xmm0
0x18000cd68  movd    xmm0, r9d
0x18000cd6d  cvtdq2ps xmm0, xmm0
0x18000cd70  movzx   r8d, al
0x18000cd74  or      r8d, 0FFFFFF00h
0x18000cd7b  shl     r8d, 10h
0x18000cd7f  mulss   xmm0, xmm2
0x18000cd83  addss   xmm0, xmm1
0x18000cd87  cvttss2si eax, xmm0
0x18000cd8b  movd    xmm0, r10d
0x18000cd90  cvtdq2ps xmm0, xmm0
0x18000cd93  movzx   edx, al
0x18000cd96  mulss   xmm0, xmm2
0x18000cd9a  addss   xmm0, xmm1
0x18000cd9e  cvttss2si eax, xmm0
0x18000cda2  movzx   ecx, al
0x18000cda5  shl     ecx, 8
0x18000cda8  or      ecx, edx
0x18000cdaa  or      ecx, r8d
0x18000cdad  shr     r11w, 8
0x18000cdb2  movzx   eax, r11w
0x18000cdb6  mov     [r12+0Ch], ecx
0x18000cdbb  movd    xmm0, eax
0x18000cdbf  cvtdq2ps xmm0, xmm0
0x18000cdc2  mulss   xmm0, xmm2
0x18000cdc6  addss   xmm0, xmm1
0x18000cdca  cvttss2si eax, xmm0
0x18000cdce  movzx   r10d, al
0x18000cdd2  shl     r10d, 8
0x18000cdd6  movaps  xmm2, xmm8
0x18000cdda  or      r10d, edx
0x18000cddd  mov     [r12+28h], r14d
0x18000cde2  or      r10d, r8d
0x18000cde5  mov     eax, 0FFFFFFFh
0x18000cdea  cmp     esi, 400h
0x18000cdf0  mov     [r12+1Ch], r10d
0x18000cdf5  mov     edi, 0A000000h
0x18000cdfa  mov     ebx, 6000000h
0x18000cdff  cmovbe  edi, eax
0x18000ce02  mov     eax, edi
0x18000ce04  shr     eax, 18h
0x18000ce07  movd    xmm3, eax
0x18000ce0b  movzx   eax, r15b
0x18000ce0f  cvtdq2ps xmm3, xmm3
0x18000ce12  movd    xmm6, eax
0x18000ce16  mov     eax, r15d
0x18000ce19  shr     eax, 10h
0x18000ce1c  movzx   eax, al
0x18000ce1f  divss   xmm3, xmm7
0x18000ce23  movd    xmm4, eax
0x18000ce27  movzx   eax, r15w
0x18000ce2b  shr     ax, 8
0x18000ce2f  subss   xmm2, xmm3
0x18000ce33  movzx   eax, ax
0x18000ce36  cvtdq2ps xmm4, xmm4
0x18000ce39  movd    xmm5, eax
0x18000ce3d  movaps  xmm0, xmm2
0x18000ce40  movzx   eax, di
0x18000ce43  shr     ax, 8
0x18000ce47  movzx   eax, ax
0x18000ce4a  cvtdq2ps xmm5, xmm5
0x18000ce4d  movd    xmm1, eax
0x18000ce51  cvtdq2ps xmm1, xmm1
0x18000ce54  mulss   xmm0, xmm5
0x18000ce58  mulss   xmm1, xmm3
0x18000ce5c  cvtdq2ps xmm6, xmm6
0x18000ce5f  addss   xmm1, xmm0
0x18000ce63  movaps  xmm0, xmm2
0x18000ce66  mulss   xmm0, xmm4
0x18000ce6a  mulss   xmm2, xmm6
0x18000ce6e  cvttss2si eax, xmm1
0x18000ce72  movzx   r9d, al
0x18000ce76  mov     eax, edi
0x18000ce78  shr     eax, 10h
0x18000ce7b  movzx   eax, al
0x18000ce7e  shl     r9d, 8
0x18000ce82  movd    xmm1, eax
0x18000ce86  cvtdq2ps xmm1, xmm1
0x18000ce89  mulss   xmm1, xmm3
0x18000ce8d  addss   xmm1, xmm0
0x18000ce91  cvttss2si eax, xmm1
0x18000ce95  movzx   ecx, al
0x18000ce98  or      ecx, 0FFFFFF00h
0x18000ce9e  movzx   eax, dil
0x18000cea2  shl     ecx, 10h
0x18000cea5  or      r9d, ecx
0x18000cea8  movd    xmm0, eax
0x18000ceac  cvtdq2ps xmm0, xmm0
0x18000ceaf  mulss   xmm0, xmm3
0x18000ceb3  addss   xmm0, xmm2
0x18000ceb7  cvttss2si eax, xmm0
0x18000cebb  movzx   ecx, al
0x18000cebe  mov     eax, 0BFFFFFFh
0x18000cec3  or      r9d, ecx
0x18000cec6  cmp     esi, 400h
0x18000cecc  mov     [r12+20h], r9d
0x18000ced1  cmovbe  ebx, eax
0x18000ced4  mov     eax, ebx
0x18000ced6  shr     eax, 18h
0x18000ced9  movd    xmm2, eax
0x18000cedd  movzx   eax, bx
0x18000cee0  cvtdq2ps xmm2, xmm2
0x18000cee3  shr     ax, 8
0x18000cee7  movzx   eax, ax
0x18000ceea  divss   xmm2, xmm7
0x18000ceee  movd    xmm1, eax
0x18000cef2  cvtdq2ps xmm1, xmm1
0x18000cef5  subss   xmm8, xmm2
0x18000cefa  mulss   xmm1, xmm2
0x18000cefe  movaps  xmm0, xmm8
0x18000cf02  mov     [r12+38h], r15d
0x18000cf07  mulss   xmm0, xmm5
0x18000cf0b  mov     [r12+40h], r14d
0x18000cf10  mov     [r12+44h], r10d
0x18000cf15  mov     [r12+48h], r9d
0x18000cf1a  addss   xmm1, xmm0
0x18000cf1e  mov     [r12+50h], r14d
0x18000cf23  movaps  xmm0, xmm8
0x18000cf27  mulss   xmm8, xmm6
0x18000cf2c  mulss   xmm0, xmm4
0x18000cf30  cvttss2si eax, xmm1
0x18000cf34  movzx   r8d, al
0x18000cf38  mov     eax, ebx
0x18000cf3a  shr     eax, 10h
0x18000cf3d  movzx   eax, al
0x18000cf40  shl     r8d, 8
0x18000cf44  movd    xmm1, eax
0x18000cf48  cvtdq2ps xmm1, xmm1
0x18000cf4b  mulss   xmm1, xmm2
0x18000cf4f  addss   xmm1, xmm0
0x18000cf53  cvttss2si eax, xmm1
0x18000cf57  movzx   ecx, al
0x18000cf5a  or      ecx, 0FFFFFF00h
0x18000cf60  movzx   eax, bl
0x18000cf63  shl     ecx, 10h
0x18000cf66  or      r8d, ecx
0x18000cf69  movd    xmm0, eax
0x18000cf6d  cvtdq2ps xmm0, xmm0
0x18000cf70  mulss   xmm0, xmm2
0x18000cf74  addss   xmm0, xmm8
0x18000cf79  cvttss2si eax, xmm0
0x18000cf7d  movss   xmm0, cs:__real@3ec9930c
0x18000cf85  movzx   ecx, al
0x18000cf88  xor     eax, eax
0x18000cf8a  or      r8d, ecx
0x18000cf8d  mulss   xmm4, xmm0
0x18000cf91  cmp     esi, 400h
0x18000cf97  mov     ecx, 0FFh
0x18000cf9c  mulss   xmm5, xmm0
0x18000cfa0  cmovbe  eax, ecx
0x18000cfa3  mov     [r12+2Ch], r8d
0x18000cfa8  mulss   xmm6, xmm0
0x18000cfac  mov     [r12+54h], r8d
0x18000cfb1  movd    xmm1, eax
0x18000cfb5  cvtdq2ps xmm1, xmm1
0x18000cfb8  mulss   xmm1, cs:__real@3f1b367a
0x18000cfc0  addss   xmm4, xmm1
0x18000cfc4  addss   xmm5, xmm1
0x18000cfc8  addss   xmm6, xmm1
0x18000cfcc  cvttss2si eax, xmm4
0x18000cfd0  movzx   edx, al
0x18000cfd3  or      edx, 0FFFFFF00h
0x18000cfd9  cvttss2si eax, xmm5
0x18000cfdd  shl     edx, 10h
  ... truncated ...
```
