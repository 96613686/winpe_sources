# Mso::SVG::Stats::Log(void)

- ea: `0x18010d784`
- end: `0x18010e401`
- name: `?Log@Stats@SVG@Mso@@QEBAXXZ`
- size: `3197`
- prototype: `void __fastcall(Mso::SVG::Stats *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004c38`

## callees

- `0x180009180`
- `0x1800091d0`
- `0x18010d784`
- `0x18013d700`

## import_xrefs

- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18010dd5d`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18010dd5d`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18010deaa`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18010deaa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010deec`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010df3a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010df81`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010dfce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e01b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e068`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e0b5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e102`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e14f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e19c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e1e5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e244`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010deec`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010df3a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010df81`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010dfce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e01b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e068`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e0b5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e102`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e14f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e19c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e1e5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e244`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18010e23d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18010e23d`

## string_xrefs

- `0x18010d875`: `Unsupported_TextPath_Elements_Total_Count`
- `0x18010dbf9`: `SVG_Filter_Composite_Total_Count`
- `0x18010dc23`: `SVG_Filter_ComponentTransfer_Total_Count`

## pseudocode

```c
void __fastcall Mso::SVG::Stats::Log(Mso::SVG::Stats *this)
{
  __m128i si128; // xmm1
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  _OWORD v23[2]; // [rsp+5D0h] [rbp+4C8h] BYREF
  void **v24; // [rsp+5F0h] [rbp+4E8h]
  const char *v25; // [rsp+5F8h] [rbp+4F0h]
  int v26; // [rsp+600h] [rbp+4F8h]
  __int16 v27; // [rsp+604h] [rbp+4FCh]
  _OWORD v28[2]; // [rsp+608h] [rbp+500h] BYREF

  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v24 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
  v27 = 4;
  v25 = "SVG_Entity_Count";
  v26 = *((_DWORD *)this + 4);
  v28[0] = 0;
  LOWORD(v28[0]) = 0;
  v23[0] = 0;
  LOWORD(v23[0]) = 0;
  v28[1] = si128;
  v23[1] = si128;
  if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(19174148, 1890, 50) )
    Mso::Logging::MsoSendStructuredTraceTag(19174148, 1890, 50);
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v3 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v3 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v3);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v4 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v4 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v4);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v5 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v5 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v5);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v6 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v6 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v6);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v7 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v7 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v7);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v8 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v8 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v8);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v9 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v9 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v9);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v10 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v10 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v10);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v11 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v11 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v11);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v12 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v12 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v12);
  }
  if ( si128.m128i_i64[1] <= 7uLL )
    goto LABEL_47;
  v13 = 0;
  if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
  {
    v13 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
    if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
LABEL_50:
      _invoke_watson(0, 0, 0, 0, 0);
  }
  free(v13);
LABEL_47:
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v14 = 0;
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v14 = (void *)MEMORY[0xFFFFFFFFFFFFFFF8];
      if ( (unsigned __int64)(-MEMORY[0xFFFFFFFFFFFFFFF8] - 8LL) > 0x1F )
        goto LABEL_50;
    }
    free(v14);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    std::wstring::_Deallocate_for_capacity(v2, 0);
    std::wstring::_Deallocate_for_capacity(v15, 0);
    std::wstring::_Deallocate_for_capacity(v16, 0);
    std::wstring::_Deallocate_for_capacity(v17, 0);
    std::wstring::_Deallocate_for_capacity(v18, 0);
    std::wstring::_Deallocate_for_capacity(v19, 0);
    std::wstring::_Deallocate_for_capacity(v20, 0);
    std::wstring::_Deallocate_for_capacity(v21, 0);
    std::wstring::_Deallocate_for_capacity(v22, 0);
  }
  std::wstring::~wstring(v23);
  std::wstring::~wstring(v28);
}

```

## disassembly

```asm
0x18010d784  mov     rax, rsp
0x18010d787  mov     [rax+8], rbx
0x18010d78b  mov     [rax+10h], rsi
0x18010d78f  mov     [rax+18h], rdi
0x18010d793  mov     [rax+20h], r15
0x18010d797  push    rbp
0x18010d798  lea     rbp, [rax-548h]
0x18010d79f  sub     rsp, 640h
0x18010d7a6  movaps  xmmword ptr [rax-18h], xmm6
0x18010d7aa  mov     rax, cs:__security_cookie
0x18010d7b1  xor     rax, rsp
0x18010d7b4  mov     [rbp+540h+var_20], rax
0x18010d7bb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18010d7c3  lea     r8, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18010d7ca  xor     r15d, r15d
0x18010d7cd  mov     [rbp+540h+var_58], r8
0x18010d7d4  xorps   xmm0, xmm0
0x18010d7d7  mov     [rbp+540h+var_90], r8
0x18010d7de  mov     r9d, 4
0x18010d7e4  movdqa  [rbp+540h+var_A0], xmm1
0x18010d7ec  lea     rax, aSvgEntityCount; "SVG_Entity_Count"
0x18010d7f3  mov     [rbp+540h+var_44], r9w
0x18010d7fb  mov     [rbp+540h+var_50], rax
0x18010d802  lea     rdx, aLarge; "Large"
0x18010d809  mov     eax, [rcx+10h]
0x18010d80c  mov     [rbp+540h+var_48], eax
0x18010d812  lea     rax, aUniqueColorCou; "Unique_Color_Count"
0x18010d819  mov     [rbp+540h+var_88], rax
0x18010d820  mov     eax, [rcx+20h]
0x18010d823  cmp     eax, 14h
0x18010d826  movups  [rbp+540h+var_40], xmm0
0x18010d82d  cmova   eax, r15d
0x18010d831  mov     word ptr [rbp+540h+var_40], r15w
0x18010d839  mov     [rbp+540h+var_80], eax
0x18010d83f  lea     rax, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x18010d846  mov     [rbp+540h+var_D0], rax
0x18010d84d  lea     rax, aColorCountBuck; "Color_Count_Bucket"
0x18010d854  mov     [rbp+540h+var_C8], rax
0x18010d85b  lea     rax, aSmall; "Small"
0x18010d862  cmova   rax, rdx
0x18010d866  mov     [rbp+540h+var_7C], r9w
0x18010d86e  mov     [rbp+540h+var_C0], rax
0x18010d875  lea     rax, aUnsupportedTex; "Unsupported_TextPath_Elements_Total_Cou"...
0x18010d87c  mov     [rbp+540h+var_100], rax
0x18010d883  mov     eax, [rcx+0Ch]
0x18010d886  mov     [rbp+540h+var_F8], eax
0x18010d88c  lea     rax, aUnsupportedFon; "Unsupported_Font_Elements_Total_Count"
0x18010d893  mov     [rbp+540h+var_138], rax
0x18010d89a  mov     eax, [rcx+8]
0x18010d89d  mov     [rbp+540h+var_130], eax
0x18010d8a3  lea     rax, aSvgFilterTurbu; "SVG_Filter_Turbulence_Total_Count"
0x18010d8aa  mov     [rbp+540h+var_170], rax
0x18010d8b1  mov     eax, [rcx+64h]
0x18010d8b4  mov     [rbp+540h+var_168], eax
0x18010d8ba  lea     rax, aSvgFilterTileT; "SVG_Filter_Tile_Total_Count"
0x18010d8c1  mov     [rbp+540h+var_1A8], rax
0x18010d8c8  mov     eax, [rcx+60h]
0x18010d8cb  mov     [rbp+540h+var_1A0], eax
0x18010d8d1  lea     rax, aSvgFilterSpecu; "SVG_Filter_SpecularLighting_Total_Count"
0x18010d8d8  mov     [rbp+540h+var_1E0], rax
0x18010d8df  mov     eax, [rcx+5Ch]
0x18010d8e2  movups  [rbp+540h+var_78], xmm0
0x18010d8e9  mov     [rbp+540h+var_1D8], eax
0x18010d8ef  movups  [rbp+540h+var_B0], xmm0
0x18010d8f6  mov     word ptr [rbp+540h+var_78], r15w
0x18010d8fe  movups  [rbp+540h+var_F0], xmm0
0x18010d905  mov     [rbp+540h+var_B8], r9w
0x18010d90d  movups  [rbp+540h+var_128], xmm0
0x18010d914  mov     word ptr [rbp+540h+var_B0], r15w
0x18010d91c  movups  [rbp+540h+var_160], xmm0
0x18010d923  mov     [rbp+540h+var_108], r8
0x18010d92a  movups  [rbp+540h+var_198], xmm0
0x18010d931  mov     [rbp+540h+var_F4], r9w
0x18010d939  movdqu  [rbp+540h+var_30], xmm1
0x18010d941  mov     word ptr [rbp+540h+var_F0], r15w
0x18010d949  movdqu  [rbp+540h+var_68], xmm1
0x18010d951  mov     [rbp+540h+var_140], r8
0x18010d958  movdqu  [rbp+540h+var_E0], xmm1
0x18010d960  mov     [rbp+540h+var_12C], r9w
0x18010d968  movdqu  [rbp+540h+var_118], xmm1
0x18010d970  mov     word ptr [rbp+540h+var_128], r15w
0x18010d978  mov     [rbp+540h+var_178], r8
0x18010d97f  mov     [rbp+540h+var_164], r9w
0x18010d987  movdqu  [rbp+540h+var_150], xmm1
0x18010d98f  mov     word ptr [rbp+540h+var_160], r15w
0x18010d997  mov     [rbp+540h+var_1B0], r8
0x18010d99e  mov     [rbp+540h+var_19C], r9w
0x18010d9a6  movdqu  [rbp+540h+var_188], xmm1
0x18010d9ae  mov     word ptr [rbp+540h+var_198], r15w
0x18010d9b6  mov     [rbp+540h+var_1E8], r8
0x18010d9bd  mov     [rbp+540h+var_1D4], r9w
0x18010d9c5  movups  [rbp+540h+var_1D0], xmm0
0x18010d9cc  movdqu  [rbp+540h+var_1C0], xmm1
0x18010d9d4  lea     rax, aSvgFilterOffse; "SVG_Filter_Offset_Total_Count"
0x18010d9db  mov     word ptr [rbp+540h+var_1D0], r15w
0x18010d9e3  mov     [rbp+540h+var_218], rax
0x18010d9ea  mov     eax, [rcx+58h]
0x18010d9ed  mov     [rbp+540h+var_210], eax
0x18010d9f3  lea     rax, aSvgFilterMorph; "SVG_Filter_Morphology_Total_Count"
0x18010d9fa  mov     [rbp+540h+var_250], rax
0x18010da01  mov     eax, [rcx+54h]
0x18010da04  mov     [rbp+540h+var_248], eax
0x18010da0a  lea     rax, aSvgFilterMerge; "SVG_Filter_Merge_Total_Count"
0x18010da11  mov     [rbp+540h+var_288], rax
0x18010da18  mov     eax, [rcx+50h]
0x18010da1b  mov     [rbp+540h+var_280], eax
0x18010da21  lea     rax, aSvgFilterImage; "SVG_Filter_Image_Total_Count"
0x18010da28  mov     [rbp+540h+var_2C0], rax
0x18010da2f  mov     eax, [rcx+4Ch]
0x18010da32  mov     [rbp+540h+var_2B8], eax
0x18010da38  lea     rax, aSvgFilterGauss; "SVG_Filter_GaussianBlur_Total_Count"
0x18010da3f  mov     [rbp+540h+var_2F8], rax
0x18010da46  mov     eax, [rcx+48h]
0x18010da49  mov     [rbp+540h+var_2F0], eax
0x18010da4f  lea     rax, aSvgFilterFlood; "SVG_Filter_Flood_Total_Count"
0x18010da56  mov     [rbp+540h+var_330], rax
0x18010da5d  mov     eax, [rcx+44h]
0x18010da60  mov     [rbp+540h+var_328], eax
0x18010da66  lea     rax, aSvgFilterDispl; "SVG_Filter_DisplacementMap_Total_Count"
0x18010da6d  mov     [rbp+540h+var_368], rax
0x18010da74  mov     eax, [rcx+40h]
0x18010da77  mov     [rbp+540h+var_360], eax
0x18010da7d  lea     rax, aSvgFilterDiffu; "SVG_Filter_DiffuseLighting_Total_Count"
0x18010da84  mov     [rbp+540h+var_3A0], rax
0x18010da8b  mov     eax, [rcx+3Ch]
0x18010da8e  mov     [rbp+540h+var_398], eax
0x18010da94  lea     rax, aSvgFilterConvo; "SVG_Filter_ConvolveMatrix_Total_Count"
0x18010da9b  mov     [rbp+540h+var_3D8], rax
0x18010daa2  mov     eax, [rcx+38h]
0x18010daa5  movups  [rbp+540h+var_208], xmm0
0x18010daac  mov     [rbp+540h+var_3D0], eax
0x18010dab2  movups  [rbp+540h+var_240], xmm0
0x18010dab9  mov     [rbp+540h+var_220], r8
0x18010dac0  movups  [rbp+540h+var_278], xmm0
0x18010dac7  mov     [rbp+540h+var_20C], r9w
0x18010dacf  movups  xmmword ptr [rbp+540h+Block], xmm0
0x18010dad6  mov     word ptr [rbp+540h+var_208], r15w
0x18010dade  movups  [rbp+540h+var_2E8], xmm0
0x18010dae5  mov     [rbp+540h+var_258], r8
0x18010daec  movups  [rbp+540h+var_320], xmm0
0x18010daf3  mov     [rbp+540h+var_244], r9w
0x18010dafb  movups  [rbp+540h+var_358], xmm0
0x18010db02  mov     word ptr [rbp+540h+var_240], r15w
0x18010db0a  movups  [rbp+540h+var_390], xmm0
0x18010db11  mov     [rbp+540h+var_290], r8
0x18010db18  movdqu  [rbp+540h+var_1F8], xmm1
0x18010db20  mov     [rbp+540h+var_27C], r9w
0x18010db28  movdqu  [rbp+540h+var_230], xmm1
0x18010db30  mov     word ptr [rbp+540h+var_278], r15w
0x18010db38  movdqu  [rbp+540h+var_268], xmm1
0x18010db40  mov     [rbp+540h+var_2C8], r8
0x18010db47  mov     [rbp+540h+var_2B4], r9w
0x18010db4f  movdqu  [rbp+540h+var_2A0], xmm1
0x18010db57  mov     word ptr [rbp+540h+Block], r15w
0x18010db5f  mov     [rbp+540h+var_300], r8
0x18010db66  mov     [rbp+540h+var_2EC], r9w
0x18010db6e  movdqu  [rbp+540h+var_2D8], xmm1
0x18010db76  mov     word ptr [rbp+540h+var_2E8], r15w
0x18010db7e  mov     [rbp+540h+var_338], r8
0x18010db85  mov     [rbp+540h+var_324], r9w
0x18010db8d  movdqu  [rbp+540h+var_310], xmm1
0x18010db95  mov     word ptr [rbp+540h+var_320], r15w
0x18010db9d  mov     [rbp+540h+var_370], r8
0x18010dba4  mov     [rbp+540h+var_35C], r9w
0x18010dbac  movdqu  [rbp+540h+var_348], xmm1
0x18010dbb4  mov     word ptr [rbp+540h+var_358], r15w
0x18010dbbc  mov     [rbp+540h+var_3A8], r8
0x18010dbc3  mov     [rbp+540h+var_394], r9w
0x18010dbcb  movdqu  [rbp+540h+var_380], xmm1
0x18010dbd3  mov     word ptr [rbp+540h+var_390], r15w
0x18010dbdb  mov     [rbp+540h+var_3E0], r8
0x18010dbe2  mov     [rbp+540h+var_3CC], r9w
0x18010dbea  movups  [rbp+540h+var_3C8], xmm0
0x18010dbf1  movdqu  [rbp+540h+var_3B8], xmm1
0x18010dbf9  lea     rax, aSvgFilterCompo_0; "SVG_Filter_Composite_Total_Count"
0x18010dc00  mov     [rbp+540h+var_418], r8
0x18010dc07  mov     [rbp+540h+var_410], rax
0x18010dc0e  lea     ebx, [r9-2]
0x18010dc12  mov     eax, [rcx+34h]
0x18010dc15  lea     edi, [rbx+30h]
0x18010dc18  mov     [rbp+540h+var_408], eax
0x18010dc1e  mov     esi, 762h
0x18010dc23  lea     rax, aSvgFilterCompo; "SVG_Filter_ComponentTransfer_Total_Coun"...
0x18010dc2a  mov     [rbp+540h+var_404], r9w
0x18010dc32  mov     [rbp+540h+var_448], rax
0x18010dc39  mov     edx, esi
0x18010dc3b  mov     eax, [rcx+30h]
0x18010dc3e  mov     [rbp+540h+var_440], eax
0x18010dc44  lea     rax, aSvgFilterColor; "SVG_Filter_ColorMatrix_Total_Count"
0x18010dc4b  mov     [rbp+540h+var_480], rax
0x18010dc52  mov     eax, [rcx+2Ch]
0x18010dc55  mov     [rbp+540h+var_478], eax
0x18010dc5b  lea     rax, aSvgFilterBlend; "SVG_Filter_Blend_Total_Count"
0x18010dc62  mov     [rbp+540h+var_4B8], rax
0x18010dc69  mov     eax, [rcx+28h]
0x18010dc6c  mov     [rbp+540h+var_4B0], eax
0x18010dc72  lea     rax, aSvgElementsTot; "SVG_Elements_Total_Count"
0x18010dc79  mov     [rbp+540h+var_4F0], rax
0x18010dc7d  mov     eax, [rcx+4]
0x18010dc80  mov     [rbp+540h+var_4E8], eax
0x18010dc83  lea     rax, aSvgFileCount; "SVG_File_Count"
0x18010dc8a  mov     [rbp+540h+var_528], rax
0x18010dc8e  mov     eax, [rcx]
0x18010dc90  mov     ecx, 1249304h
0x18010dc95  mov     [rbp+540h+var_450], r8
0x18010dc9c  mov     [rbp+540h+var_43C], r9w
0x18010dca4  mov     [rbp+540h+var_488], r8
0x18010dcab  mov     [rbp+540h+var_474], r9w
0x18010dcb3  mov     [rbp+540h+var_4C0], r8
0x18010dcba  mov     [rbp+540h+var_4AC], r9w
0x18010dcc2  mov     [rbp+540h+var_4F8], r8
0x18010dcc6  mov     [rbp+540h+var_4E4], r9w
0x18010dccb  mov     [rbp+540h+var_530], r8
0x18010dccf  mov     r8d, edi
0x18010dcd2  mov     [rbp+540h+var_51C], r9w
0x18010dcd7  mov     r9d, ebx
0x18010dcda  movups  [rbp+540h+var_400], xmm0
0x18010dce1  mov     word ptr [rbp+540h+var_3C8], r15w
0x18010dce9  movups  [rbp+540h+var_438], xmm0
0x18010dcf0  mov     word ptr [rbp+540h+var_400], r15w
0x18010dcf8  movups  [rbp+540h+var_470], xmm0
0x18010dcff  mov     word ptr [rbp+540h+var_438], r15w
0x18010dd07  movups  [rbp+540h+var_4A8], xmm0
0x18010dd0e  mov     word ptr [rbp+540h+var_470], r15w
0x18010dd16  movups  [rbp+540h+var_4E0], xmm0
0x18010dd1a  mov     word ptr [rbp+540h+var_4A8], r15w
0x18010dd22  movups  [rbp+540h+var_518], xmm0
0x18010dd26  mov     word ptr [rbp+540h+var_4E0], r15w
0x18010dd2b  movdqu  [rbp+540h+var_3F0], xmm1
0x18010dd33  mov     [rbp+540h+var_520], eax
0x18010dd36  movdqu  [rbp+540h+var_428], xmm1
0x18010dd3e  mov     word ptr [rbp+540h+var_518], r15w
0x18010dd43  movdqu  [rbp+540h+var_460], xmm1
0x18010dd4b  movdqu  [rbp+540h+var_498], xmm1
0x18010dd53  movdqu  [rbp+540h+var_4D0], xmm1
0x18010dd58  movdqu  [rbp+540h+var_508], xmm1
0x18010dd5d  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18010dd63  test    al, al
0x18010dd65  jz      loc_18010DEB0
0x18010dd6b  lea     rax, [rbp+540h+var_530]
0x18010dd6f  mov     r9d, ebx
0x18010dd72  mov     [rsp+640h+var_5F0], rax
0x18010dd77  mov     r8d, edi
0x18010dd7a  lea     rax, [rbp+540h+var_4F8]
0x18010dd7e  mov     edx, esi
0x18010dd80  mov     [rsp+640h+var_5E8], rax
0x18010dd85  mov     ecx, 1249304h
0x18010dd8a  lea     rax, [rbp+540h+var_4C0]
0x18010dd91  mov     [rsp+640h+var_5E0], rax
0x18010dd96  lea     rax, [rbp+540h+var_488]
0x18010dd9d  mov     [rsp+640h+var_5D8], rax
0x18010dda2  lea     rax, [rbp+540h+var_450]
0x18010dda9  mov     [rsp+640h+var_5D0], rax
0x18010ddae  lea     rax, [rbp+540h+var_418]
0x18010ddb5  mov     [rsp+640h+var_5C8], rax
0x18010ddba  lea     rax, [rbp+540h+var_3E0]
0x18010ddc1  mov     [rbp+540h+var_5C0], rax
0x18010ddc5  lea     rax, [rbp+540h+var_3A8]
0x18010ddcc  mov     [rbp+540h+var_5B8], rax
0x18010ddd0  lea     rax, [rbp+540h+var_370]
0x18010ddd7  mov     [rbp+540h+var_5B0], rax
0x18010dddb  lea     rax, [rbp+540h+var_338]
0x18010dde2  mov     [rbp+540h+var_5A8], rax
0x18010dde6  lea     rax, [rbp+540h+var_300]
0x18010dded  mov     [rbp+540h+var_5A0], rax
0x18010ddf1  lea     rax, [rbp+540h+var_2C8]
0x18010ddf8  mov     [rbp+540h+var_598], rax
0x18010ddfc  lea     rax, [rbp+540h+var_290]
0x18010de03  mov     [rbp+540h+var_590], rax
0x18010de07  lea     rax, [rbp+540h+var_258]
0x18010de0e  mov     [rbp+540h+var_588], rax
0x18010de12  lea     rax, [rbp+540h+var_220]
0x18010de19  mov     [rbp+540h+var_580], rax
0x18010de1d  lea     rax, [rbp+540h+var_1E8]
0x18010de24  mov     [rbp+540h+var_578], rax
0x18010de28  lea     rax, [rbp+540h+var_1B0]
0x18010de2f  mov     [rbp+540h+var_570], rax
0x18010de33  lea     rax, [rbp+540h+var_178]
0x18010de3a  mov     [rbp+540h+var_568], rax
0x18010de3e  lea     rax, [rbp+540h+var_140]
0x18010de45  mov     [rbp+540h+var_560], rax
0x18010de49  lea     rax, [rbp+540h+var_108]
0x18010de50  mov     [rbp+540h+var_558], rax
0x18010de54  lea     rax, [rbp+540h+var_D0]
0x18010de5b  mov     [rbp+540h+var_550], rax
0x18010de5f  lea     rax, [rbp+540h+var_90]
0x18010de66  mov     [rbp+540h+var_548], rax
0x18010de6a  lea     rax, [rbp+540h+var_58]
0x18010de71  mov     [rbp+540h+var_540], rax
0x18010de75  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18010de7c  mov     [rsp+640h+var_610], rax
0x18010de81  lea     rax, [rsp+640h+var_5F0]
0x18010de86  mov     [rsp+640h+var_608], rax
0x18010de8b  lea     rax, [rbp+540h+var_538]
0x18010de8f  mov     [rsp+640h+var_600], rax
0x18010de94  lea     rax, [rsp+640h+var_610]
0x18010de99  mov     [rsp+640h+var_618], rax
0x18010de9e  lea     rax, aSvgStatistics; "SVG Statistics"
0x18010dea5  mov     [rsp+640h+Reserved], rax
0x18010deaa  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,char const *,Mso::Logging::IStructuredTrace const &)
  ... truncated ...
```
