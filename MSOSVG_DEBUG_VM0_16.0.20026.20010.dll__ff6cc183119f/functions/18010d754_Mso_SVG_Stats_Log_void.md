# Mso::SVG::Stats::Log(void)

- ea: `0x18010d754`
- end: `0x18010e3d1`
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
- `0x18010d754`
- `0x18013d650`

## import_xrefs

- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18010dd2d`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x18010dd2d`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18010de7a`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z` at `0x18010de7a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010debc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010df0a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010df51`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010df9e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010dfeb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e038`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e085`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e0d2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e11f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e16c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e1b5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e214`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010debc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010df0a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010df51`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010df9e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010dfeb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e038`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e085`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e0d2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e11f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e16c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e1b5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010e214`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18010e20d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18010e20d`

## string_xrefs

- `0x18010d845`: `Unsupported_TextPath_Elements_Total_Count`
- `0x18010dbc9`: `SVG_Filter_Composite_Total_Count`
- `0x18010dbf3`: `SVG_Filter_ComponentTransfer_Total_Count`

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
0x18010d754  mov     rax, rsp
0x18010d757  mov     [rax+8], rbx
0x18010d75b  mov     [rax+10h], rsi
0x18010d75f  mov     [rax+18h], rdi
0x18010d763  mov     [rax+20h], r15
0x18010d767  push    rbp
0x18010d768  lea     rbp, [rax-548h]
0x18010d76f  sub     rsp, 640h
0x18010d776  movaps  xmmword ptr [rax-18h], xmm6
0x18010d77a  mov     rax, cs:__security_cookie
0x18010d781  xor     rax, rsp
0x18010d784  mov     [rbp+540h+var_20], rax
0x18010d78b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18010d793  lea     r8, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18010d79a  xor     r15d, r15d
0x18010d79d  mov     [rbp+540h+var_58], r8
0x18010d7a4  xorps   xmm0, xmm0
0x18010d7a7  mov     [rbp+540h+var_90], r8
0x18010d7ae  mov     r9d, 4
0x18010d7b4  movdqa  [rbp+540h+var_A0], xmm1
0x18010d7bc  lea     rax, aSvgEntityCount; "SVG_Entity_Count"
0x18010d7c3  mov     [rbp+540h+var_44], r9w
0x18010d7cb  mov     [rbp+540h+var_50], rax
0x18010d7d2  lea     rdx, aLarge; "Large"
0x18010d7d9  mov     eax, [rcx+10h]
0x18010d7dc  mov     [rbp+540h+var_48], eax
0x18010d7e2  lea     rax, aUniqueColorCou; "Unique_Color_Count"
0x18010d7e9  mov     [rbp+540h+var_88], rax
0x18010d7f0  mov     eax, [rcx+20h]
0x18010d7f3  cmp     eax, 14h
0x18010d7f6  movups  [rbp+540h+var_40], xmm0
0x18010d7fd  cmova   eax, r15d
0x18010d801  mov     word ptr [rbp+540h+var_40], r15w
0x18010d809  mov     [rbp+540h+var_80], eax
0x18010d80f  lea     rax, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x18010d816  mov     [rbp+540h+var_D0], rax
0x18010d81d  lea     rax, aColorCountBuck; "Color_Count_Bucket"
0x18010d824  mov     [rbp+540h+var_C8], rax
0x18010d82b  lea     rax, aSmall; "Small"
0x18010d832  cmova   rax, rdx
0x18010d836  mov     [rbp+540h+var_7C], r9w
0x18010d83e  mov     [rbp+540h+var_C0], rax
0x18010d845  lea     rax, aUnsupportedTex; "Unsupported_TextPath_Elements_Total_Cou"...
0x18010d84c  mov     [rbp+540h+var_100], rax
0x18010d853  mov     eax, [rcx+0Ch]
0x18010d856  mov     [rbp+540h+var_F8], eax
0x18010d85c  lea     rax, aUnsupportedFon; "Unsupported_Font_Elements_Total_Count"
0x18010d863  mov     [rbp+540h+var_138], rax
0x18010d86a  mov     eax, [rcx+8]
0x18010d86d  mov     [rbp+540h+var_130], eax
0x18010d873  lea     rax, aSvgFilterTurbu; "SVG_Filter_Turbulence_Total_Count"
0x18010d87a  mov     [rbp+540h+var_170], rax
0x18010d881  mov     eax, [rcx+64h]
0x18010d884  mov     [rbp+540h+var_168], eax
0x18010d88a  lea     rax, aSvgFilterTileT; "SVG_Filter_Tile_Total_Count"
0x18010d891  mov     [rbp+540h+var_1A8], rax
0x18010d898  mov     eax, [rcx+60h]
0x18010d89b  mov     [rbp+540h+var_1A0], eax
0x18010d8a1  lea     rax, aSvgFilterSpecu; "SVG_Filter_SpecularLighting_Total_Count"
0x18010d8a8  mov     [rbp+540h+var_1E0], rax
0x18010d8af  mov     eax, [rcx+5Ch]
0x18010d8b2  movups  [rbp+540h+var_78], xmm0
0x18010d8b9  mov     [rbp+540h+var_1D8], eax
0x18010d8bf  movups  [rbp+540h+var_B0], xmm0
0x18010d8c6  mov     word ptr [rbp+540h+var_78], r15w
0x18010d8ce  movups  [rbp+540h+var_F0], xmm0
0x18010d8d5  mov     [rbp+540h+var_B8], r9w
0x18010d8dd  movups  [rbp+540h+var_128], xmm0
0x18010d8e4  mov     word ptr [rbp+540h+var_B0], r15w
0x18010d8ec  movups  [rbp+540h+var_160], xmm0
0x18010d8f3  mov     [rbp+540h+var_108], r8
0x18010d8fa  movups  [rbp+540h+var_198], xmm0
0x18010d901  mov     [rbp+540h+var_F4], r9w
0x18010d909  movdqu  [rbp+540h+var_30], xmm1
0x18010d911  mov     word ptr [rbp+540h+var_F0], r15w
0x18010d919  movdqu  [rbp+540h+var_68], xmm1
0x18010d921  mov     [rbp+540h+var_140], r8
0x18010d928  movdqu  [rbp+540h+var_E0], xmm1
0x18010d930  mov     [rbp+540h+var_12C], r9w
0x18010d938  movdqu  [rbp+540h+var_118], xmm1
0x18010d940  mov     word ptr [rbp+540h+var_128], r15w
0x18010d948  mov     [rbp+540h+var_178], r8
0x18010d94f  mov     [rbp+540h+var_164], r9w
0x18010d957  movdqu  [rbp+540h+var_150], xmm1
0x18010d95f  mov     word ptr [rbp+540h+var_160], r15w
0x18010d967  mov     [rbp+540h+var_1B0], r8
0x18010d96e  mov     [rbp+540h+var_19C], r9w
0x18010d976  movdqu  [rbp+540h+var_188], xmm1
0x18010d97e  mov     word ptr [rbp+540h+var_198], r15w
0x18010d986  mov     [rbp+540h+var_1E8], r8
0x18010d98d  mov     [rbp+540h+var_1D4], r9w
0x18010d995  movups  [rbp+540h+var_1D0], xmm0
0x18010d99c  movdqu  [rbp+540h+var_1C0], xmm1
0x18010d9a4  lea     rax, aSvgFilterOffse; "SVG_Filter_Offset_Total_Count"
0x18010d9ab  mov     word ptr [rbp+540h+var_1D0], r15w
0x18010d9b3  mov     [rbp+540h+var_218], rax
0x18010d9ba  mov     eax, [rcx+58h]
0x18010d9bd  mov     [rbp+540h+var_210], eax
0x18010d9c3  lea     rax, aSvgFilterMorph; "SVG_Filter_Morphology_Total_Count"
0x18010d9ca  mov     [rbp+540h+var_250], rax
0x18010d9d1  mov     eax, [rcx+54h]
0x18010d9d4  mov     [rbp+540h+var_248], eax
0x18010d9da  lea     rax, aSvgFilterMerge; "SVG_Filter_Merge_Total_Count"
0x18010d9e1  mov     [rbp+540h+var_288], rax
0x18010d9e8  mov     eax, [rcx+50h]
0x18010d9eb  mov     [rbp+540h+var_280], eax
0x18010d9f1  lea     rax, aSvgFilterImage; "SVG_Filter_Image_Total_Count"
0x18010d9f8  mov     [rbp+540h+var_2C0], rax
0x18010d9ff  mov     eax, [rcx+4Ch]
0x18010da02  mov     [rbp+540h+var_2B8], eax
0x18010da08  lea     rax, aSvgFilterGauss; "SVG_Filter_GaussianBlur_Total_Count"
0x18010da0f  mov     [rbp+540h+var_2F8], rax
0x18010da16  mov     eax, [rcx+48h]
0x18010da19  mov     [rbp+540h+var_2F0], eax
0x18010da1f  lea     rax, aSvgFilterFlood; "SVG_Filter_Flood_Total_Count"
0x18010da26  mov     [rbp+540h+var_330], rax
0x18010da2d  mov     eax, [rcx+44h]
0x18010da30  mov     [rbp+540h+var_328], eax
0x18010da36  lea     rax, aSvgFilterDispl; "SVG_Filter_DisplacementMap_Total_Count"
0x18010da3d  mov     [rbp+540h+var_368], rax
0x18010da44  mov     eax, [rcx+40h]
0x18010da47  mov     [rbp+540h+var_360], eax
0x18010da4d  lea     rax, aSvgFilterDiffu; "SVG_Filter_DiffuseLighting_Total_Count"
0x18010da54  mov     [rbp+540h+var_3A0], rax
0x18010da5b  mov     eax, [rcx+3Ch]
0x18010da5e  mov     [rbp+540h+var_398], eax
0x18010da64  lea     rax, aSvgFilterConvo; "SVG_Filter_ConvolveMatrix_Total_Count"
0x18010da6b  mov     [rbp+540h+var_3D8], rax
0x18010da72  mov     eax, [rcx+38h]
0x18010da75  movups  [rbp+540h+var_208], xmm0
0x18010da7c  mov     [rbp+540h+var_3D0], eax
0x18010da82  movups  [rbp+540h+var_240], xmm0
0x18010da89  mov     [rbp+540h+var_220], r8
0x18010da90  movups  [rbp+540h+var_278], xmm0
0x18010da97  mov     [rbp+540h+var_20C], r9w
0x18010da9f  movups  xmmword ptr [rbp+540h+Block], xmm0
0x18010daa6  mov     word ptr [rbp+540h+var_208], r15w
0x18010daae  movups  [rbp+540h+var_2E8], xmm0
0x18010dab5  mov     [rbp+540h+var_258], r8
0x18010dabc  movups  [rbp+540h+var_320], xmm0
0x18010dac3  mov     [rbp+540h+var_244], r9w
0x18010dacb  movups  [rbp+540h+var_358], xmm0
0x18010dad2  mov     word ptr [rbp+540h+var_240], r15w
0x18010dada  movups  [rbp+540h+var_390], xmm0
0x18010dae1  mov     [rbp+540h+var_290], r8
0x18010dae8  movdqu  [rbp+540h+var_1F8], xmm1
0x18010daf0  mov     [rbp+540h+var_27C], r9w
0x18010daf8  movdqu  [rbp+540h+var_230], xmm1
0x18010db00  mov     word ptr [rbp+540h+var_278], r15w
0x18010db08  movdqu  [rbp+540h+var_268], xmm1
0x18010db10  mov     [rbp+540h+var_2C8], r8
0x18010db17  mov     [rbp+540h+var_2B4], r9w
0x18010db1f  movdqu  [rbp+540h+var_2A0], xmm1
0x18010db27  mov     word ptr [rbp+540h+Block], r15w
0x18010db2f  mov     [rbp+540h+var_300], r8
0x18010db36  mov     [rbp+540h+var_2EC], r9w
0x18010db3e  movdqu  [rbp+540h+var_2D8], xmm1
0x18010db46  mov     word ptr [rbp+540h+var_2E8], r15w
0x18010db4e  mov     [rbp+540h+var_338], r8
0x18010db55  mov     [rbp+540h+var_324], r9w
0x18010db5d  movdqu  [rbp+540h+var_310], xmm1
0x18010db65  mov     word ptr [rbp+540h+var_320], r15w
0x18010db6d  mov     [rbp+540h+var_370], r8
0x18010db74  mov     [rbp+540h+var_35C], r9w
0x18010db7c  movdqu  [rbp+540h+var_348], xmm1
0x18010db84  mov     word ptr [rbp+540h+var_358], r15w
0x18010db8c  mov     [rbp+540h+var_3A8], r8
0x18010db93  mov     [rbp+540h+var_394], r9w
0x18010db9b  movdqu  [rbp+540h+var_380], xmm1
0x18010dba3  mov     word ptr [rbp+540h+var_390], r15w
0x18010dbab  mov     [rbp+540h+var_3E0], r8
0x18010dbb2  mov     [rbp+540h+var_3CC], r9w
0x18010dbba  movups  [rbp+540h+var_3C8], xmm0
0x18010dbc1  movdqu  [rbp+540h+var_3B8], xmm1
0x18010dbc9  lea     rax, aSvgFilterCompo_0; "SVG_Filter_Composite_Total_Count"
0x18010dbd0  mov     [rbp+540h+var_418], r8
0x18010dbd7  mov     [rbp+540h+var_410], rax
0x18010dbde  lea     ebx, [r9-2]
0x18010dbe2  mov     eax, [rcx+34h]
0x18010dbe5  lea     edi, [rbx+30h]
0x18010dbe8  mov     [rbp+540h+var_408], eax
0x18010dbee  mov     esi, 762h
0x18010dbf3  lea     rax, aSvgFilterCompo; "SVG_Filter_ComponentTransfer_Total_Coun"...
0x18010dbfa  mov     [rbp+540h+var_404], r9w
0x18010dc02  mov     [rbp+540h+var_448], rax
0x18010dc09  mov     edx, esi
0x18010dc0b  mov     eax, [rcx+30h]
0x18010dc0e  mov     [rbp+540h+var_440], eax
0x18010dc14  lea     rax, aSvgFilterColor; "SVG_Filter_ColorMatrix_Total_Count"
0x18010dc1b  mov     [rbp+540h+var_480], rax
0x18010dc22  mov     eax, [rcx+2Ch]
0x18010dc25  mov     [rbp+540h+var_478], eax
0x18010dc2b  lea     rax, aSvgFilterBlend; "SVG_Filter_Blend_Total_Count"
0x18010dc32  mov     [rbp+540h+var_4B8], rax
0x18010dc39  mov     eax, [rcx+28h]
0x18010dc3c  mov     [rbp+540h+var_4B0], eax
0x18010dc42  lea     rax, aSvgElementsTot; "SVG_Elements_Total_Count"
0x18010dc49  mov     [rbp+540h+var_4F0], rax
0x18010dc4d  mov     eax, [rcx+4]
0x18010dc50  mov     [rbp+540h+var_4E8], eax
0x18010dc53  lea     rax, aSvgFileCount; "SVG_File_Count"
0x18010dc5a  mov     [rbp+540h+var_528], rax
0x18010dc5e  mov     eax, [rcx]
0x18010dc60  mov     ecx, 1249304h
0x18010dc65  mov     [rbp+540h+var_450], r8
0x18010dc6c  mov     [rbp+540h+var_43C], r9w
0x18010dc74  mov     [rbp+540h+var_488], r8
0x18010dc7b  mov     [rbp+540h+var_474], r9w
0x18010dc83  mov     [rbp+540h+var_4C0], r8
0x18010dc8a  mov     [rbp+540h+var_4AC], r9w
0x18010dc92  mov     [rbp+540h+var_4F8], r8
0x18010dc96  mov     [rbp+540h+var_4E4], r9w
0x18010dc9b  mov     [rbp+540h+var_530], r8
0x18010dc9f  mov     r8d, edi
0x18010dca2  mov     [rbp+540h+var_51C], r9w
0x18010dca7  mov     r9d, ebx
0x18010dcaa  movups  [rbp+540h+var_400], xmm0
0x18010dcb1  mov     word ptr [rbp+540h+var_3C8], r15w
0x18010dcb9  movups  [rbp+540h+var_438], xmm0
0x18010dcc0  mov     word ptr [rbp+540h+var_400], r15w
0x18010dcc8  movups  [rbp+540h+var_470], xmm0
0x18010dccf  mov     word ptr [rbp+540h+var_438], r15w
0x18010dcd7  movups  [rbp+540h+var_4A8], xmm0
0x18010dcde  mov     word ptr [rbp+540h+var_470], r15w
0x18010dce6  movups  [rbp+540h+var_4E0], xmm0
0x18010dcea  mov     word ptr [rbp+540h+var_4A8], r15w
0x18010dcf2  movups  [rbp+540h+var_518], xmm0
0x18010dcf6  mov     word ptr [rbp+540h+var_4E0], r15w
0x18010dcfb  movdqu  [rbp+540h+var_3F0], xmm1
0x18010dd03  mov     [rbp+540h+var_520], eax
0x18010dd06  movdqu  [rbp+540h+var_428], xmm1
0x18010dd0e  mov     word ptr [rbp+540h+var_518], r15w
0x18010dd13  movdqu  [rbp+540h+var_460], xmm1
0x18010dd1b  movdqu  [rbp+540h+var_498], xmm1
0x18010dd23  movdqu  [rbp+540h+var_4D0], xmm1
0x18010dd28  movdqu  [rbp+540h+var_508], xmm1
0x18010dd2d  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z; Mso::Logging::MsoShouldTrace(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories)
0x18010dd33  test    al, al
0x18010dd35  jz      loc_18010DE80
0x18010dd3b  lea     rax, [rbp+540h+var_530]
0x18010dd3f  mov     r9d, ebx
0x18010dd42  mov     [rsp+640h+var_5F0], rax
0x18010dd47  mov     r8d, edi
0x18010dd4a  lea     rax, [rbp+540h+var_4F8]
0x18010dd4e  mov     edx, esi
0x18010dd50  mov     [rsp+640h+var_5E8], rax
0x18010dd55  mov     ecx, 1249304h
0x18010dd5a  lea     rax, [rbp+540h+var_4C0]
0x18010dd61  mov     [rsp+640h+var_5E0], rax
0x18010dd66  lea     rax, [rbp+540h+var_488]
0x18010dd6d  mov     [rsp+640h+var_5D8], rax
0x18010dd72  lea     rax, [rbp+540h+var_450]
0x18010dd79  mov     [rsp+640h+var_5D0], rax
0x18010dd7e  lea     rax, [rbp+540h+var_418]
0x18010dd85  mov     [rsp+640h+var_5C8], rax
0x18010dd8a  lea     rax, [rbp+540h+var_3E0]
0x18010dd91  mov     [rbp+540h+var_5C0], rax
0x18010dd95  lea     rax, [rbp+540h+var_3A8]
0x18010dd9c  mov     [rbp+540h+var_5B8], rax
0x18010dda0  lea     rax, [rbp+540h+var_370]
0x18010dda7  mov     [rbp+540h+var_5B0], rax
0x18010ddab  lea     rax, [rbp+540h+var_338]
0x18010ddb2  mov     [rbp+540h+var_5A8], rax
0x18010ddb6  lea     rax, [rbp+540h+var_300]
0x18010ddbd  mov     [rbp+540h+var_5A0], rax
0x18010ddc1  lea     rax, [rbp+540h+var_2C8]
0x18010ddc8  mov     [rbp+540h+var_598], rax
0x18010ddcc  lea     rax, [rbp+540h+var_290]
0x18010ddd3  mov     [rbp+540h+var_590], rax
0x18010ddd7  lea     rax, [rbp+540h+var_258]
0x18010ddde  mov     [rbp+540h+var_588], rax
0x18010dde2  lea     rax, [rbp+540h+var_220]
0x18010dde9  mov     [rbp+540h+var_580], rax
0x18010dded  lea     rax, [rbp+540h+var_1E8]
0x18010ddf4  mov     [rbp+540h+var_578], rax
0x18010ddf8  lea     rax, [rbp+540h+var_1B0]
0x18010ddff  mov     [rbp+540h+var_570], rax
0x18010de03  lea     rax, [rbp+540h+var_178]
0x18010de0a  mov     [rbp+540h+var_568], rax
0x18010de0e  lea     rax, [rbp+540h+var_140]
0x18010de15  mov     [rbp+540h+var_560], rax
0x18010de19  lea     rax, [rbp+540h+var_108]
0x18010de20  mov     [rbp+540h+var_558], rax
0x18010de24  lea     rax, [rbp+540h+var_D0]
0x18010de2b  mov     [rbp+540h+var_550], rax
0x18010de2f  lea     rax, [rbp+540h+var_90]
0x18010de36  mov     [rbp+540h+var_548], rax
0x18010de3a  lea     rax, [rbp+540h+var_58]
0x18010de41  mov     [rbp+540h+var_540], rax
0x18010de45  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x18010de4c  mov     [rsp+640h+var_610], rax
0x18010de51  lea     rax, [rsp+640h+var_5F0]
0x18010de56  mov     [rsp+640h+var_608], rax
0x18010de5b  lea     rax, [rbp+540h+var_538]
0x18010de5f  mov     [rsp+640h+var_600], rax
0x18010de64  lea     rax, [rsp+640h+var_610]
0x18010de69  mov     [rsp+640h+var_618], rax
0x18010de6e  lea     rax, aSvgStatistics; "SVG Statistics"
0x18010de75  mov     [rsp+640h+Reserved], rax
0x18010de7a  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEBDAEBUIStructuredTrace@12@@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,char const *,Mso::Logging::IStructuredTrace const &)
  ... truncated ...
```
