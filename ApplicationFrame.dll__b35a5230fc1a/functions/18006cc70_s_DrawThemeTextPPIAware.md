# s_DrawThemeTextPPIAware

- ea: `0x18006cc70`
- end: `0x18006d199`
- name: `s_DrawThemeTextPPIAware`
- size: `1321`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006d26c`

## callees

- `0x180030aec`
- `0x180041ec0`
- `0x180043c30`
- `0x1800446fc`
- `0x1800532a8`
- `0x18006c3f4`
- `0x18006c464`
- `0x18006c7d0`
- `0x18006cc70`
- `0x18006e3e8`
- `0x18006e51c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d13f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d13f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006d15c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006d15c`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeFont` at `0x18006ce2c`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeFont` at `0x18006ce2c`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18006cdc5`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18006cdc5`
- `GDI32!CreateFontIndirectW` at `0x18006ced4`
- `GDI32!CreateFontIndirectW` at `0x18006ced4`
- `GDI32!CreateDIBSection` at `0x18006cd41`
- `GDI32!CreateDIBSection` at `0x18006cd41`
- `GDI32!SelectObject` at `0x18006cd6d`
- `GDI32!SelectObject` at `0x18006cf47`
- `GDI32!SelectObject` at `0x18006d0e6`
- `GDI32!SelectObject` at `0x18006d10b`
- `GDI32!SelectObject` at `0x18006cd6d`
- `GDI32!SelectObject` at `0x18006cf47`
- `GDI32!SelectObject` at `0x18006d0e6`
- `GDI32!SelectObject` at `0x18006d10b`
- `GDI32!GdiAlphaBlend` at `0x18006d0cd`
- `GDI32!GdiAlphaBlend` at `0x18006d0cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall s_DrawThemeTextPPIAware(void *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __m128i *a6)
{
  HDC v7; // rcx
  int Error; // ebx
  __int32 v9; // edi
  __int32 v10; // ebx
  HBITMAP v11; // rax
  HDC v12; // r12
  HGDIOBJ v13; // r13
  __m128i v14; // xmm0
  int v15; // ebx
  int v16; // edi
  HTHEME v17; // rbx
  bool v18; // sf
  int v19; // eax
  __int16 *v20; // r12
  void *v21; // r9
  __int64 v22; // r13
  unsigned int v23; // r10d
  unsigned int v24; // esi
  __int16 v25; // ax
  __int16 *v26; // rcx
  int LastError; // eax
  _BYTE v29[8]; // [rsp+78h] [rbp-88h] BYREF
  HDC hdc; // [rsp+80h] [rbp-80h]
  HTHEME hTheme; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  void **v33; // [rsp+98h] [rbp-68h] BYREF
  HBITMAP v34; // [rsp+A0h] [rbp-60h]
  void *ppvBits; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-50h]
  HGDIOBJ h; // [rsp+B8h] [rbp-48h]
  HDC v38; // [rsp+C0h] [rbp-40h]
  HDC v39; // [rsp+C8h] [rbp-38h]
  HGDIOBJ v40; // [rsp+D0h] [rbp-30h]
  HFONT v41; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v42; // [rsp+E0h] [rbp-20h]
  int v43; // [rsp+F0h] [rbp-10h]
  int v44[19]; // [rsp+F4h] [rbp-Ch] BYREF
  int v45; // [rsp+140h] [rbp+40h]
  int v46; // [rsp+144h] [rbp+44h]
  int v47; // [rsp+148h] [rbp+48h]
  int v48; // [rsp+14Ch] [rbp+4Ch]
  BITMAPINFO pbmi; // [rsp+150h] [rbp+50h] BYREF
  LOGFONTW pFont; // [rsp+180h] [rbp+80h] BYREF
  int pvParam; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v52[220]; // [rsp+1E4h] [rbp+E4h] BYREF
  __int128 v53; // [rsp+2C0h] [rbp+1C0h]
  __int128 v54; // [rsp+2D0h] [rbp+1D0h]
  __int128 v55; // [rsp+2E0h] [rbp+1E0h]
  __int128 v56; // [rsp+2F0h] [rbp+1F0h]
  _OWORD v57[14]; // [rsp+300h] [rbp+200h]

  v36 = a4;
  v32 = a3;
  hTheme = a1;
  Microsoft::WRL::Wrappers::CompatibleDC::CompatibleDC((Microsoft::WRL::Wrappers::CompatibleDC *)v29, *(HDC *)(a4 + 32));
  v7 = hdc;
  if ( !hdc )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_39;
    v7 = hdc;
  }
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  pbmi.bmiHeader.biSize = 44;
  v9 = a6->m128i_i32[0];
  pbmi.bmiHeader.biWidth = a6->m128i_i32[2] - a6->m128i_i32[0];
  v10 = a6->m128i_i32[1];
  pbmi.bmiHeader.biHeight = v10 - a6->m128i_i32[3];
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  ppvBits = 0;
  v11 = CreateDIBSection(v7, &pbmi, 0, &ppvBits, 0, 0);
  v33 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::`vftable';
  v34 = v11;
  if ( !v11 )
  {
    Error = -2147024882;
    goto LABEL_34;
  }
  v12 = hdc;
  v39 = hdc;
  v13 = SelectObject(hdc, v11);
  v40 = v13;
  v14 = *a6;
  v15 = -v10;
  v16 = -v9;
  v45 = v16 + _mm_cvtsi128_si32(*a6);
  v47 = v16 + v14.m128i_i32[2];
  v48 = v15 + v14.m128i_i32[3];
  v46 = v15 + v14.m128i_i32[1];
  memset_0(v52, 0, 0x1F4u);
  pvParam = 504;
  if ( SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v43 = 72;
    memset_0(v44, 0, 0x44u);
    memset_0(&pFont, 0, sizeof(pFont));
    v17 = hTheme;
    v18 = GetThemeFont(hTheme, hdc, 27, 0, 210, &pFont) < 0;
    v19 = v44[0];
    if ( v18 )
    {
      *(_OWORD *)&pFont.lfHeight = v53;
      *(_OWORD *)&pFont.lfWeight = v54;
      *(_OWORD *)&pFont.lfFaceName[2] = v55;
      *(_OWORD *)&pFont.lfFaceName[10] = v56;
      *(_OWORD *)&pFont.lfFaceName[18] = v57[0];
      *(_OWORD *)&pFont.lfFaceName[24] = *(_OWORD *)((char *)v57 + 12);
    }
    else
    {
      v19 = v44[0] | 0x40;
      v44[0] |= 0x40u;
      if ( (int)v53 <= 0 )
      {
        if ( (int)v53 >= pFont.lfHeight )
          goto LABEL_14;
      }
      else if ( (int)v53 <= pFont.lfHeight )
      {
        goto LABEL_14;
      }
      pFont.lfHeight = v53;
    }
LABEL_14:
    if ( (*(_BYTE *)(a4 + 16) & 0x20) != 0 )
    {
      pFont.lfWeight = 700;
      v44[0] = v19 | 0x40;
    }
    v41 = CreateFontIndirectW(&pFont);
    if ( !v41 )
    {
      Error = -2147467259;
      goto LABEL_31;
    }
    v20 = *(__int16 **)a5;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a5);
    v22 = *(_QWORD *)(a5 + 8);
    v24 = v23;
    v25 = *v20;
    if ( *v20 )
    {
      v26 = v20;
      do
      {
        if ( v25 == 9 )
          break;
        ++v26;
        ++v24;
        v25 = *v26;
      }
      while ( *v26 );
    }
    v38 = hdc;
    h = SelectObject(hdc, v21);
    if ( v24 )
    {
      Error = DPIToPPIHelpers::DrawThemeTextExPPI(v32, *(unsigned int *)(a5 + 60), a5 + 64, v17, hdc);
      if ( Error < 0 )
      {
LABEL_29:
        SelectObject(v38, h);
        v12 = v39;
        v13 = v40;
LABEL_31:
        CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(&v41);
        goto LABEL_32;
      }
      v17 = hTheme;
    }
    if ( v24 >= (unsigned __int64)(v22 - 1)
      || (v42 = 0,
          Error = DPIToPPIHelpers::GetThemeTextExtentPPI(v32, *(unsigned int *)(a5 + 60), a5 + 64, v17, hdc),
          Error >= 0)
      && (v45 = v47 + v42 - DWORD2(v42),
          Error = DPIToPPIHelpers::DrawThemeTextExPPI(v32, *(unsigned int *)(a5 + 60), a5 + 64, hTheme, hdc),
          Error >= 0) )
    {
      Error = 0;
      if ( !GdiAlphaBlend(
              *(HDC *)(v36 + 32),
              a6->m128i_i32[0],
              a6->m128i_i32[1],
              a6->m128i_i32[2] - a6->m128i_i32[0],
              a6->m128i_i32[3] - a6->m128i_i32[1],
              hdc,
              0,
              0,
              a6->m128i_i32[2] - a6->m128i_i32[0],
              a6->m128i_i32[3] - a6->m128i_i32[1],
              (BLENDFUNCTION)33488896) )
        Error = ResultFromKnownLastError();
    }
    goto LABEL_29;
  }
LABEL_32:
  SelectObject(v12, v13);
  v11 = v34;
LABEL_34:
  v33 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::`vftable';
  if ( v11
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::InternalClose(&v33) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
LABEL_39:
  Microsoft::WRL::Wrappers::CompatibleDC::~CompatibleDC((Microsoft::WRL::Wrappers::CompatibleDC *)v29);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18006cc70  mov     [rsp-8+arg_8], rbx
0x18006cc75  push    rbp
0x18006cc76  push    rsi
0x18006cc77  push    rdi
0x18006cc78  push    r12
0x18006cc7a  push    r13
0x18006cc7c  push    r14
0x18006cc7e  push    r15
0x18006cc80  lea     rbp, [rsp-2F0h]
0x18006cc88  sub     rsp, 3F0h
0x18006cc8f  mov     rax, cs:__security_cookie
0x18006cc96  xor     rax, rsp
0x18006cc99  mov     [rbp+320h+var_40], rax
0x18006cca0  mov     rsi, r9
0x18006cca3  mov     [rbp+320h+var_370], r9
0x18006cca7  mov     [rbp+320h+var_390], r8
0x18006ccab  mov     dword ptr [rsp+420h+var_3B0.BlendOp], edx
0x18006ccaf  mov     [rbp+320h+hTheme], rcx
0x18006ccb3  mov     r14, [rbp+320h+arg_20]
0x18006ccba  mov     r15, [rbp+320h+arg_28]
0x18006ccc1  mov     rdx, [r9+20h]; HDC
0x18006ccc5  lea     rcx, [rsp+420h+var_3A8]; this
0x18006ccca  call    ??0CompatibleDC@Wrappers@WRL@Microsoft@@QEAA@PEAUHDC__@@@Z; Microsoft::WRL::Wrappers::CompatibleDC::CompatibleDC(HDC__ *)
0x18006cccf  mov     rcx, [rbp+320h+hdc]
0x18006ccd3  xor     r12d, r12d
0x18006ccd6  test    rcx, rcx
0x18006ccd9  jnz     short loc_18006CCEE
0x18006ccdb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006cce0  mov     ebx, eax
0x18006cce2  test    eax, eax
0x18006cce4  js      loc_18006D163
0x18006ccea  mov     rcx, [rbp+320h+hdc]; hdc
0x18006ccee  xorps   xmm0, xmm0
0x18006ccf1  movdqu  xmmword ptr [rbp+320h+pbmi.bmiHeader.biSizeImage], xmm0
0x18006ccf6  mov     qword ptr [rbp+320h+pbmi.bmiHeader.biClrImportant], r12
0x18006ccfa  mov     [rbp+320h+pbmi.bmiHeader.biSize], 2Ch ; ','
0x18006cd01  mov     edi, [r15]
0x18006cd04  mov     eax, [r15+8]
0x18006cd08  sub     eax, edi
0x18006cd0a  mov     [rbp+320h+pbmi.bmiHeader.biWidth], eax
0x18006cd0d  mov     ebx, [r15+4]
0x18006cd11  mov     eax, ebx
0x18006cd13  sub     eax, [r15+0Ch]
0x18006cd17  mov     [rbp+320h+pbmi.bmiHeader.biHeight], eax
0x18006cd1a  mov     r13d, 1
0x18006cd20  mov     qword ptr [rbp+320h+pbmi.bmiHeader.biPlanes], 200001h
0x18006cd28  mov     [rbp+320h+ppvBits], r12
0x18006cd2c  mov     [rsp+420h+offset], r12d; offset
0x18006cd31  mov     [rsp+420h+hSection], r12; hSection
0x18006cd36  lea     r9, [rbp+320h+ppvBits]; ppvBits
0x18006cd3a  xor     r8d, r8d; usage
0x18006cd3d  lea     rdx, [rbp+320h+pbmi]; pbmi
0x18006cd41  call    cs:__imp_CreateDIBSection
0x18006cd47  lea     rcx, ??_7?$HandleT@UHBITMAPTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::`vftable'
0x18006cd4e  mov     [rbp+320h+var_388], rcx
0x18006cd52  mov     [rbp+320h+var_380], rax
0x18006cd56  test    rax, rax
0x18006cd59  jz      loc_18006D124
0x18006cd5f  mov     r12, [rbp+320h+hdc]
0x18006cd63  mov     [rbp+320h+var_358], r12
0x18006cd67  mov     rdx, rax; h
0x18006cd6a  mov     rcx, r12; hdc
0x18006cd6d  call    cs:__imp_SelectObject
0x18006cd73  mov     r13, rax
0x18006cd76  mov     [rbp+320h+var_350], rax
0x18006cd7a  movaps  xmm0, xmmword ptr [r15]
0x18006cd7e  movups  [rbp+320h+var_2E0], xmm0
0x18006cd82  neg     ebx
0x18006cd84  neg     edi
0x18006cd86  movd    eax, xmm0
0x18006cd8a  add     eax, edi
0x18006cd8c  mov     dword ptr [rbp+320h+var_2E0], eax
0x18006cd8f  add     dword ptr [rbp+320h+var_2E0+8], edi
0x18006cd92  add     dword ptr [rbp+320h+var_2E0+0Ch], ebx
0x18006cd95  add     dword ptr [rbp+320h+var_2E0+4], ebx
0x18006cd98  xor     edx, edx; Val
0x18006cd9a  mov     r8d, 1F4h; Size
0x18006cda0  lea     rcx, [rbp+320h+var_23C]; void *
0x18006cda7  call    memset_0
0x18006cdac  mov     edx, 1F8h; uiParam
0x18006cdb1  mov     [rbp+320h+pvParam], edx
0x18006cdb7  xor     r9d, r9d; fWinIni
0x18006cdba  lea     r8, [rbp+320h+pvParam]; pvParam
0x18006cdc1  lea     ecx, [r9+29h]; uiAction
0x18006cdc5  call    cs:__imp_SystemParametersInfoW
0x18006cdcb  test    eax, eax
0x18006cdcd  jnz     short loc_18006CDDE
0x18006cdcf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006cdd4  mov     ebx, eax
0x18006cdd6  test    eax, eax
0x18006cdd8  js      loc_18006D105
0x18006cdde  mov     [rbp+320h+var_330], 48h ; 'H'
0x18006cde5  xor     edx, edx; Val
0x18006cde7  lea     r8d, [rdx+44h]; Size
0x18006cdeb  lea     rcx, [rbp+320h+var_32C]; void *
0x18006cdef  call    memset_0
0x18006cdf4  xor     edx, edx; Val
0x18006cdf6  lea     r8d, [rdx+5Ch]; Size
0x18006cdfa  lea     rcx, [rbp+320h+pFont]; void *
0x18006ce01  call    memset_0
0x18006ce06  lea     rax, [rbp+320h+pFont]
0x18006ce0d  mov     qword ptr [rsp+420h+offset], rax; pFont
0x18006ce12  mov     dword ptr [rsp+420h+hSection], 0D2h; iPropId
0x18006ce1a  xor     r9d, r9d; iStateId
0x18006ce1d  lea     r8d, [r9+1Bh]; iPartId
0x18006ce21  mov     rdx, [rbp+320h+hdc]; hdc
0x18006ce25  mov     rbx, [rbp+320h+hTheme]
0x18006ce29  mov     rcx, rbx; hTheme
0x18006ce2c  call    cs:__imp_GetThemeFont
0x18006ce32  test    eax, eax
0x18006ce34  mov     eax, [rbp+320h+var_32C]
0x18006ce37  js      short loc_18006CE63
0x18006ce39  or      eax, 40h
0x18006ce3c  mov     [rbp+320h+var_32C], eax
0x18006ce3f  mov     ecx, dword ptr [rbp+320h+var_160]
0x18006ce45  test    ecx, ecx
0x18006ce47  jle     short loc_18006CE53
0x18006ce49  cmp     ecx, [rbp+320h+pFont.lfHeight]
0x18006ce4f  jle     short loc_18006CEB7
0x18006ce51  jmp     short loc_18006CE5B
0x18006ce53  cmp     ecx, [rbp+320h+pFont.lfHeight]
0x18006ce59  jge     short loc_18006CEB7
0x18006ce5b  mov     [rbp+320h+pFont.lfHeight], ecx
0x18006ce61  jmp     short loc_18006CEB7
0x18006ce63  movaps  xmm0, [rbp+320h+var_160]
0x18006ce6a  movaps  xmmword ptr [rbp+320h+pFont.lfHeight], xmm0
0x18006ce71  movaps  xmm1, [rbp+320h+var_150]
0x18006ce78  movaps  xmmword ptr [rbp+320h+pFont.lfWeight], xmm1
0x18006ce7f  movaps  xmm0, [rbp+320h+var_140]
0x18006ce86  movaps  xmmword ptr [rbp+320h+pFont.lfFaceName+4], xmm0
0x18006ce8d  movaps  xmm1, [rbp+320h+var_130]
0x18006ce94  movaps  xmmword ptr [rbp+320h+pFont.lfFaceName+14h], xmm1
0x18006ce9b  movaps  xmm0, [rbp+320h+var_120]
0x18006cea2  movaps  xmmword ptr [rbp+320h+pFont.lfFaceName+24h], xmm0
0x18006cea9  movups  xmm1, [rbp+320h+var_120+0Ch]
0x18006ceb0  movups  xmmword ptr [rbp+320h+pFont.lfFaceName+30h], xmm1
0x18006ceb7  test    byte ptr [rsi+10h], 20h
0x18006cebb  jz      short loc_18006CECD
0x18006cebd  mov     [rbp+320h+pFont.lfWeight], 2BCh
0x18006cec7  or      eax, 40h
0x18006ceca  mov     [rbp+320h+var_32C], eax
0x18006cecd  lea     rcx, [rbp+320h+pFont]; lplf
0x18006ced4  call    cs:__imp_CreateFontIndirectW
0x18006ceda  mov     r9, rax
0x18006cedd  mov     [rbp+320h+var_348], rax
0x18006cee1  xor     r10d, r10d
0x18006cee4  test    rax, rax
0x18006cee7  jz      loc_18006D0F6
0x18006ceed  lea     edi, [r10+24h]
0x18006cef1  cmp     [r14+48h], r10d
0x18006cef5  jnz     short loc_18006CF06
0x18006cef7  test    dword ptr [rsi+10h], 100h
0x18006cefe  mov     eax, 100024h
0x18006cf03  cmovnz  edi, eax
0x18006cf06  mov     r12, [r14]
0x18006cf09  mov     rcx, r14
0x18006cf0c  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18006cf11  mov     r13, [r14+8]
0x18006cf15  mov     esi, r10d
0x18006cf18  movzx   eax, word ptr [r12]
0x18006cf1d  test    ax, ax
0x18006cf20  jz      short loc_18006CF39
0x18006cf22  mov     rcx, r12
0x18006cf25  cmp     ax, 9
0x18006cf29  jz      short loc_18006CF39
0x18006cf2b  add     rcx, 2
0x18006cf2f  inc     esi
0x18006cf31  movzx   eax, word ptr [rcx]
0x18006cf34  test    ax, ax
0x18006cf37  jnz     short loc_18006CF25
0x18006cf39  mov     rax, [rbp+320h+hdc]
0x18006cf3d  mov     [rbp+320h+var_360], rax
0x18006cf41  mov     rdx, r9; h
0x18006cf44  mov     rcx, rax; hdc
0x18006cf47  call    cs:__imp_SelectObject
0x18006cf4d  mov     [rbp+320h+h], rax
0x18006cf51  test    esi, esi
0x18006cf53  jz      short loc_18006CFA7
0x18006cf55  lea     r8, [r14+40h]
0x18006cf59  lea     rax, [rbp+320h+var_330]
0x18006cf5d  mov     [rsp+420h+var_3C8], rax
0x18006cf62  lea     rax, [rbp+320h+var_2E0]
0x18006cf66  mov     qword ptr [rsp+420h+ftn.BlendOp], rax
0x18006cf6b  mov     [rsp+420h+hSrc], edi
0x18006cf6f  mov     [rsp+420h+wSrc], esi
0x18006cf73  mov     qword ptr [rsp+420h+yoriginSrc], r12
0x18006cf78  mov     eax, dword ptr [rsp+420h+var_3B0.BlendOp]
0x18006cf7c  mov     [rsp+420h+xoriginSrc], eax
0x18006cf80  mov     rax, [rbp+320h+hdc]
0x18006cf84  mov     [rsp+420h+hSection], rax
0x18006cf89  mov     r9, rbx
0x18006cf8c  mov     edx, [r14+3Ch]
0x18006cf90  mov     rcx, [rbp+320h+var_390]
0x18006cf94  call    ?DrawThemeTextExPPI@DPIToPPIHelpers@@YAJPEAUHWND__@@W4ScaleType@1@PEAIPEAXPEAUHDC__@@HHPEBGHKPEAUtagRECT@@PEAU_DTTOPTS@@@Z; DPIToPPIHelpers::DrawThemeTextExPPI(HWND__ *,DPIToPPIHelpers::ScaleType,uint *,void *,HDC__ *,int,int,ushort const *,int,ulong,tagRECT *,_DTTOPTS *)
0x18006cf99  mov     ebx, eax
0x18006cf9b  test    eax, eax
0x18006cf9d  js      loc_18006D0DE
0x18006cfa3  mov     rbx, [rbp+320h+hTheme]
0x18006cfa7  mov     ecx, esi
0x18006cfa9  lea     rax, [r13-1]
0x18006cfad  cmp     rcx, rax
0x18006cfb0  jnb     loc_18006D07B
0x18006cfb6  xorps   xmm0, xmm0
0x18006cfb9  movdqu  [rbp+320h+var_340], xmm0
0x18006cfbe  sub     r13d, esi
0x18006cfc1  dec     r13d
0x18006cfc4  inc     rcx
0x18006cfc7  lea     rsi, [r12+rcx*2]
0x18006cfcb  lea     rax, [rbp+320h+var_340]
0x18006cfcf  mov     [rsp+420h+var_3C0], rax
0x18006cfd4  lea     rax, [rbp+320h+var_2E0]
0x18006cfd8  mov     [rsp+420h+var_3C8], rax
0x18006cfdd  lea     rax, [rbp+320h+var_330]
0x18006cfe1  mov     qword ptr [rsp+420h+ftn.BlendOp], rax
0x18006cfe6  mov     [rsp+420h+hSrc], edi
0x18006cfea  mov     [rsp+420h+wSrc], r13d
0x18006cfef  mov     qword ptr [rsp+420h+yoriginSrc], rsi
0x18006cff4  mov     eax, dword ptr [rsp+420h+var_3B0.BlendOp]
0x18006cff8  mov     [rsp+420h+xoriginSrc], eax
0x18006cffc  mov     rax, [rbp+320h+hdc]
0x18006d000  mov     [rsp+420h+hSection], rax
0x18006d005  mov     r9, rbx
0x18006d008  lea     r8, [r14+40h]
0x18006d00c  mov     edx, [r14+3Ch]
0x18006d010  mov     rcx, [rbp+320h+var_390]
0x18006d014  call    ?GetThemeTextExtentPPI@DPIToPPIHelpers@@YAJPEAUHWND__@@W4ScaleType@1@PEAIPEAXPEAUHDC__@@HHPEBGHKPEAU_DTTOPTS@@PEAUtagRECT@@7@Z; DPIToPPIHelpers::GetThemeTextExtentPPI(HWND__ *,DPIToPPIHelpers::ScaleType,uint *,void *,HDC__ *,int,int,ushort const *,int,ulong,_DTTOPTS *,tagRECT *,tagRECT *)
0x18006d019  mov     ebx, eax
0x18006d01b  test    eax, eax
0x18006d01d  js      loc_18006D0DE
0x18006d023  mov     eax, dword ptr [rbp+320h+var_340]
0x18006d026  sub     eax, dword ptr [rbp+320h+var_340+8]
0x18006d029  add     eax, dword ptr [rbp+320h+var_2E0+8]
0x18006d02c  mov     dword ptr [rbp+320h+var_2E0], eax
0x18006d02f  lea     rax, [rbp+320h+var_330]
0x18006d033  mov     [rsp+420h+var_3C8], rax
0x18006d038  lea     rax, [rbp+320h+var_2E0]
0x18006d03c  mov     qword ptr [rsp+420h+ftn.BlendOp], rax
0x18006d041  mov     [rsp+420h+hSrc], edi
0x18006d045  mov     [rsp+420h+wSrc], r13d
0x18006d04a  mov     qword ptr [rsp+420h+yoriginSrc], rsi
0x18006d04f  mov     eax, dword ptr [rsp+420h+var_3B0.BlendOp]
0x18006d053  mov     [rsp+420h+xoriginSrc], eax
0x18006d057  mov     rax, [rbp+320h+hdc]
0x18006d05b  mov     [rsp+420h+hSection], rax
0x18006d060  mov     r9, [rbp+320h+hTheme]
0x18006d064  lea     r8, [r14+40h]
0x18006d068  mov     edx, [r14+3Ch]
0x18006d06c  mov     rcx, [rbp+320h+var_390]
0x18006d070  call    ?DrawThemeTextExPPI@DPIToPPIHelpers@@YAJPEAUHWND__@@W4ScaleType@1@PEAIPEAXPEAUHDC__@@HHPEBGHKPEAUtagRECT@@PEAU_DTTOPTS@@@Z; DPIToPPIHelpers::DrawThemeTextExPPI(HWND__ *,DPIToPPIHelpers::ScaleType,uint *,void *,HDC__ *,int,int,ushort const *,int,ulong,tagRECT *,_DTTOPTS *)
0x18006d075  mov     ebx, eax
0x18006d077  test    eax, eax
0x18006d079  js      short loc_18006D0DE
0x18006d07b  xor     ebx, ebx
0x18006d07d  mov     dword ptr [rsp+420h+var_3B0.BlendOp], ebx
0x18006d081  mov     word ptr [rsp+420h+var_3B0.SourceConstantAlpha], 1FFh
0x18006d088  mov     r8d, [r15+4]; yoriginDest
0x18006d08c  mov     r10d, [r15+0Ch]
0x18006d090  sub     r10d, r8d
0x18006d093  mov     r9d, [r15+8]
0x18006d097  sub     r9d, [r15]; wDest
0x18006d09a  mov     eax, dword ptr [rsp+420h+var_3B0.BlendOp]
0x18006d09e  mov     dword ptr [rsp+420h+ftn.BlendOp], eax; ftn
0x18006d0a2  mov     [rsp+420h+hSrc], r10d; hSrc
0x18006d0a7  mov     [rsp+420h+wSrc], r9d; wSrc
0x18006d0ac  mov     [rsp+420h+yoriginSrc], ebx; yoriginSrc
0x18006d0b0  mov     [rsp+420h+xoriginSrc], ebx; xoriginSrc
0x18006d0b4  mov     rax, [rbp+320h+hdc]
0x18006d0b8  mov     qword ptr [rsp+420h+offset], rax; hdcSrc
0x18006d0bd  mov     dword ptr [rsp+420h+hSection], r10d; hDest
0x18006d0c2  mov     edx, [r15]; xoriginDest
0x18006d0c5  mov     rcx, [rbp+320h+var_370]
0x18006d0c9  mov     rcx, [rcx+20h]; hdcDest
0x18006d0cd  call    cs:__imp_GdiAlphaBlend
0x18006d0d3  test    eax, eax
0x18006d0d5  jnz     short loc_18006D0DE
0x18006d0d7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006d0dc  mov     ebx, eax
0x18006d0de  mov     rdx, [rbp+320h+h]; h
0x18006d0e2  mov     rcx, [rbp+320h+var_360]; hdc
0x18006d0e6  call    cs:__imp_SelectObject
0x18006d0ec  mov     r12, [rbp+320h+var_358]
0x18006d0f0  mov     r13, [rbp+320h+var_350]
0x18006d0f4  jmp     short loc_18006D0FB
0x18006d0f6  mov     ebx, 80004005h
0x18006d0fb  lea     rcx, [rbp+320h+var_348]
0x18006d0ff  call    ??1?$CAutoHandle@PEAUHBITMAP__@@@@QEAA@XZ; CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(void)
0x18006d104  nop
0x18006d105  mov     rdx, r13; h
0x18006d108  mov     rcx, r12; hdc
0x18006d10b  call    cs:__imp_SelectObject
0x18006d111  mov     rax, [rbp+320h+var_380]
0x18006d115  mov     r13d, 1
0x18006d11b  lea     rcx, ??_7?$HandleT@UHBITMAPTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::`vftable'
0x18006d122  jmp     short loc_18006D129
0x18006d124  mov     ebx, 8007000Eh
0x18006d129  mov     [rbp+320h+var_388], rcx
0x18006d12d  test    rax, rax
0x18006d130  jz      short loc_18006D163
0x18006d132  lea     rcx, [rbp+320h+var_388]
0x18006d136  call    ?InternalClose@?$HandleT@UHBITMAPTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::InternalClose(void)
  ... truncated ...
```
