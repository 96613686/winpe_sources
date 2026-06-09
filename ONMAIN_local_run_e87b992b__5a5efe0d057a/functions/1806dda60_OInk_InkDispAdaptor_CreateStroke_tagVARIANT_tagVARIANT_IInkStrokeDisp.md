# OInk::InkDispAdaptor::CreateStroke(tagVARIANT,tagVARIANT,IInkStrokeDisp * *)

- ea: `0x1806dda60`
- end: `0x1806de2b7`
- name: `?CreateStroke@InkDispAdaptor@OInk@@UEAAJUtagVARIANT@@0PEAPEAUIInkStrokeDisp@@@Z`
- size: `2135`
- prototype: `__int64 __fastcall(OInk::InkDispAdaptor *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *__struct_ptr, struct IInkStrokeDisp **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callees

- `0x18002e4fc`
- `0x18002fe90`
- `0x180094630`
- `0x1802e50d0`
- `0x1802e5160`
- `0x1802e5190`
- `0x18039788c`
- `0x180398900`
- `0x1806dda60`
- `0x1806de2b8`
- `0x180efe414`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1806ddcd9`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1806ddcd9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806ddd44`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1806ddd44`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1806ddd02`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1806ddd02`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806ddae3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806ddca8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806ddae3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1806ddca8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806ddb5d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806ddcc7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806ddd18`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806ddd5e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806ddd96`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806de19e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806ddb5d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806ddcc7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806ddd18`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806ddd5e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806ddd96`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1806de19e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1806ddcb7`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1806de003`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1806ddcb7`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1806de003`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1806ddb2a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1806ddb2a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1806ddb6c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1806ddd2a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1806de282`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1806ddb6c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1806ddd2a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1806de282`

## pseudocode

```c
HRESULT __fastcall OInk::InkDispAdaptor::CreateStroke(
        unsigned __int64 this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        struct IInkStrokeDisp **a4)
{
  HRESULT result; // eax
  SAFEARRAY *parray; // rbx
  unsigned int v7; // r8d
  __int64 v8; // r13
  __int64 v9; // rax
  __int64 v10; // r14
  Mso::Memory *v11; // rax
  Mso::Memory *v12; // rsi
  __int64 v13; // rdx
  HRESULT UBound; // ebx
  int v15; // eax
  int v16; // r15d
  int v17; // r12d
  unsigned int v18; // ecx
  Mso::Memory *v19; // r9
  __int64 v20; // rax
  __int64 v21; // xmm0_8
  __int64 v22; // rax
  SAFEARRAY *v23; // rbx
  void *v24; // rdx
  HRESULT LBound; // edi
  LONG v26; // r14d
  bool v27; // r15
  bool v28; // r12
  __int64 v29; // r8
  int v30; // ebx
  __int64 v31; // rdi
  __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rdx
  float v35; // xmm0_4
  float v36; // xmm1_4
  __int64 v37; // rax
  __m128 v38; // xmm1
  __m128i v39; // xmm2
  int v40; // eax
  float v41; // xmm1_4
  float v42; // xmm2_4
  float v43; // xmm0_4
  float v44; // xmm1_4
  float v45; // xmm2_4
  int v46; // ebx
  __int64 v47; // rdi
  int v48; // eax
  int v49; // r14d
  __m128i si128; // xmm0
  _QWORD *v51; // rax
  __int64 v52; // rcx
  struct IInkStrokeDisp *v53; // rax
  int v54; // [rsp+30h] [rbp-D0h]
  int v55; // [rsp+34h] [rbp-CCh]
  int v56; // [rsp+38h] [rbp-C8h]
  SAFEARRAY *psa[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v58; // [rsp+50h] [rbp-B0h]
  int v59; // [rsp+54h] [rbp-ACh]
  LONG plUbound; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v61; // [rsp+60h] [rbp-A0h] BYREF
  LONG plLbound; // [rsp+68h] [rbp-98h] BYREF
  LONG v63; // [rsp+6Ch] [rbp-94h]
  void *ppvData; // [rsp+70h] [rbp-90h] BYREF
  __int64 v65; // [rsp+78h] [rbp-88h] BYREF
  struct IInkStrokeDisp *v66; // [rsp+80h] [rbp-80h] BYREF
  __int64 v67; // [rsp+88h] [rbp-78h]
  __m128i v68; // [rsp+90h] [rbp-70h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-60h]
  struct IInkStrokeDisp *v70; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v71; // [rsp+B0h] [rbp-50h] BYREF
  __m128i v72; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v73; // [rsp+C8h] [rbp-38h]
  float v74[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v75; // [rsp+D8h] [rbp-28h]
  __m128i v76; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v77; // [rsp+F0h] [rbp-10h]
  __m128i v78; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v79; // [rsp+108h] [rbp+8h]
  Mso::Memory *v80; // [rsp+110h] [rbp+10h]
  __int64 v81; // [rsp+118h] [rbp+18h]

  if ( !a4 )
    return -2147024809;
  *a4 = 0;
  if ( !*(_QWORD *)(this + 16) )
    return -2147467259;
  if ( a2->vt != 8195 || a3->vt != 8209 )
    return -2147024809;
  ppvData = 0;
  parray = a3->parray;
  result = SafeArrayAccessData(parray, &ppvData);
  if ( result < 0 )
    return result;
  ppvData = (char *)ppvData + 8;
  v8 = *(int *)ppvData;
  ppvData = (char *)ppvData + 4;
  v9 = 32LL * (unsigned int)v8;
  v10 = -1;
  v67 = -1;
  if ( !is_mul_ok((unsigned int)v8, 0x20u) )
    v9 = -1;
  v11 = (Mso::Memory *)Mso::Memory::AllocateEx((Mso::Memory *)v9, 0, v7);
  v12 = v11;
  v80 = v11;
  if ( !v11 )
    return -2144862207;
  memcpy_0(v11, ppvData, (unsigned int)(32 * v8));
  UBound = SafeArrayUnaccessData(parray);
  if ( UBound < 0 )
    goto LABEL_12;
  v15 = -1;
  v54 = -1;
  v16 = -1;
  v58 = -1;
  v56 = -1;
  v17 = -1;
  v55 = -1;
  v18 = 0;
  if ( (_DWORD)v8 )
  {
    v19 = v12;
    while ( 1 )
    {
      v20 = *(_QWORD *)v19;
      v21 = *((_QWORD *)v19 + 1);
      v13 = *(_QWORD *)v19 - 0x4BA052C0598A6A8FLL;
      if ( *(_QWORD *)v19 == 0x4BA052C0598A6A8FLL )
        v13 = v21 - 0x61A5117435AFAF93LL;
      if ( !v13 )
        break;
      v13 = v20 - 0x449804E0B53F9F75LL;
      if ( v20 == 0x449804E0B53F9F75LL )
        v13 = v21 - 0x11905ABB0DC3EEA7LL;
      if ( v13 )
      {
        v13 = v20 - 0x4E18F9F47307502DLL;
        if ( v20 == 0x4E18F9F47307502DLL )
          v13 = v21 - 0xC61A3B1E12CF2B3LL;
        if ( v13 )
        {
          v13 = v20 - 0x410B8828029123B4LL;
          if ( v20 == 0x410B8828029123B4LL )
            v13 = v21 + 0x231A6A9AAC5FAF4ELL;
          if ( v13 )
          {
            v22 = v20 - 0x4906F6BA82DEC5C7LL;
            if ( !v22 )
              v22 = v21 - 0x6C45FC8DD6664F89LL;
            if ( !v22 )
              v17 = v18;
          }
          else
          {
            v56 = v18;
          }
        }
        else
        {
          v16 = v18;
        }
        goto LABEL_35;
      }
      v15 = v18;
      v54 = v18;
LABEL_36:
      ++v18;
      v19 = (Mso::Memory *)((char *)v19 + 32);
      if ( v18 >= (unsigned int)v8 )
      {
        v58 = v16;
        v55 = v17;
        v67 = v10;
        goto LABEL_38;
      }
    }
    v10 = v18;
LABEL_35:
    v15 = v54;
    goto LABEL_36;
  }
LABEL_38:
  if ( (int)v10 < 0 || v15 < 0 )
  {
    Mso::Memory::Free(v12, (void *)v13);
    return -2147024809;
  }
  v23 = a2->parray;
  psa[0] = v23;
  psa[1] = 0;
  if ( v23 && SafeArrayAccessData(v23, (void **)&psa[1]) < 0 )
  {
    MsoShipAssertTagProc(4024273);
    SafeArrayUnaccessData(v23);
    *(_OWORD *)psa = 0;
  }
  if ( SafeArrayGetDim(v23) != 1 )
    goto LABEL_55;
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(v23, 1u, &plLbound);
  if ( LBound >= 0 )
  {
    UBound = SafeArrayGetUBound(v23, 1u, &plUbound);
    if ( UBound < 0 )
    {
LABEL_51:
      if ( psa[0] )
        SafeArrayUnaccessData(psa[0]);
LABEL_119:
      *(_OWORD *)psa = 0;
LABEL_12:
      Mso::Memory::Free(v12, (void *)v13);
      return UBound;
    }
    v26 = plLbound;
    v63 = plLbound;
    if ( plLbound > plUbound || (v13 = (plUbound - plLbound + 1) % (unsigned int)v8, (_DWORD)v13) )
    {
LABEL_55:
      if ( psa[0] )
        SafeArrayUnaccessData(psa[0]);
      UBound = -2147024809;
      goto LABEL_119;
    }
    v27 = v16 >= 0;
    v28 = v56 >= 0 && v17 >= 0;
    v68 = 0;
    v29 = 0;
    v69 = 0;
    v78 = 0;
    v79 = 0;
    v72 = 0;
    v73 = 0;
    v76 = 0;
    v77 = 0;
    if ( v27 )
      v30 = 2 * v28 + 3;
    else
      v30 = 2;
    v59 = v30;
    if ( plLbound >= plUbound )
    {
LABEL_107:
      (*(void (__fastcall **)(_QWORD, struct IInkStrokeDisp **, __m128i *, __m128i *, __m128i *))(**(_QWORD **)(this + 16)
                                                                                                + 192LL))(
        *(_QWORD *)(this + 16),
        &v70,
        &v68,
        &v78,
        &v72);
      if ( !v70 )
      {
        if ( v76.m128i_i64[0] )
          std::_Deallocate<16>(v76.m128i_i64[0], (v77 - v76.m128i_i64[0]) & 0xFFFFFFFFFFFFFFFCuLL);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v76 = si128;
        v77 = 19937;
        if ( v72.m128i_i64[0] )
        {
          std::_Deallocate<16>(v72.m128i_i64[0], (v73 - v72.m128i_i64[0]) & 0xFFFFFFFFFFFFFFF8uLL);
          si128 = _mm_load_si128((const __m128i *)&_xmm);
        }
        v72 = si128;
        v73 = 19937;
        if ( v78.m128i_i64[0] )
        {
          std::_Deallocate<16>(v78.m128i_i64[0], (v79 - v78.m128i_i64[0]) & 0xFFFFFFFFFFFFFFFCuLL);
          si128 = _mm_load_si128((const __m128i *)&_xmm);
        }
        v78 = si128;
        v79 = 19937;
        if ( v68.m128i_i64[0] )
        {
          std::_Deallocate<16>(v68.m128i_i64[0], (v69 - v68.m128i_i64[0]) & 0xFFFFFFFFFFFFFFF8uLL);
          si128 = _mm_load_si128((const __m128i *)&_xmm);
        }
        v68 = si128;
        v69 = 19937;
        if ( psa[0] )
          SafeArrayUnaccessData(psa[0]);
        UBound = -2147467259;
        goto LABEL_119;
      }
      ((void (__fastcall *)(struct IInkStrokeDisp *, Mso::Memory *, _QWORD, __m128i *))v70->lpVtbl->get_DrawingAttributes)(
        v70,
        v12,
        (unsigned int)v8,
        &v76);
      v71 = this & -(__int64)(this != 8);
      v66 = v70;
      v51 = (_QWORD *)Mso::Make<OInk::InkStrokeDispAdaptor,IInkStrokeDisp,IInkDisp * &,OInk::IInkStroke2 * &>(
                        &v65,
                        &v71,
                        &v66);
      MsoCF::CIPtr<Jot::IXPSDocument,Jot::IXPSDocument>::CIPtr<Jot::IXPSDocument,Jot::IXPSDocument>(&v66, *v51);
      v52 = v65;
      if ( v65 )
      {
        v65 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      v53 = v66;
      *a4 = v66;
      UBound = v53 == 0 ? 0x8007000E : 0;
      if ( v70 )
        ((void (__fastcall *)(struct IInkStrokeDisp *))v70->lpVtbl->Release)(v70);
      std::vector<enum OfficeSpace::Data::FSBaseGallery::ItemSizes>::~vector<enum OfficeSpace::Data::FSBaseGallery::ItemSizes>(&v76);
      std::vector<OInk::CTiltF>::~vector<OInk::CTiltF>(&v72);
      std::vector<enum OfficeSpace::Data::FSBaseGallery::ItemSizes>::~vector<enum OfficeSpace::Data::FSBaseGallery::ItemSizes>(&v78);
      std::vector<OInk::CTiltF>::~vector<OInk::CTiltF>(&v68);
      goto LABEL_51;
    }
    v81 = 4 * v8;
    v31 = 4 * (plLbound + (__int64)v56);
    v65 = v31;
    v32 = (int)v67 - (__int64)v54;
    v66 = (struct IInkStrokeDisp *)v32;
    v33 = v54 - (__int64)v56;
    v71 = v33;
    v75 = v55 - (__int64)v56;
    while ( 1 )
    {
      v34 = v31 + 4 * v33;
      v35 = (float)*(int *)((char *)&psa[1]->cDims + 4 * v32 + v34);
      v74[0] = v35;
      v36 = (float)*(int *)((char *)&psa[1]->cDims + v34);
      v74[1] = v36;
      v37 = v68.m128i_i64[1];
      if ( v68.m128i_i64[1] == v29 )
      {
        std::vector<OInk::CPointF>::_Emplace_reallocate<OInk::CPointF const &>(&v68, v68.m128i_i64[1], v74);
      }
      else
      {
        *(float *)v68.m128i_i64[1] = v35;
        *(float *)(v37 + 4) = v36;
        v68.m128i_i64[1] += 8;
      }
      if ( v27 )
        std::vector<long>::_Emplace_one_at_back<long const &>(&v78, (char *)psa[1] + 4 * v26 + 4 * v58);
      if ( v28 )
      {
        v61 = 0;
        v38 = *((__m128 *)v12 + 2 * v56 + 1);
        v39 = *((__m128i *)v12 + 2 * v55 + 1);
        v40 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v38, 8));
        if ( v40 == 3 )
        {
          if ( _mm_cvtsi128_si32(_mm_srli_si128(v39, 8)) == 3 )
          {
            v41 = _mm_shuffle_ps(v38, v38, 255).m128_f32[0];
            if ( v41 == 0.0 )
              v42 = *(float *)&FLOAT_1_0;
            else
              v42 = v41;
            if ( v41 == 0.0 )
              v41 = *(float *)&FLOAT_1_0;
            *(float *)&v61 = (float)((float)((float)*(int *)((char *)&psa[1]->cDims + v31) / v42) - 180.0) * 0.017453292;
            v43 = (float)((float)*(int *)((char *)&psa[1]->cDims + 4 * v75 + v31) / v41) * 0.017453292;
LABEL_89:
            *((float *)&v61 + 1) = v43;
            std::vector<OInk::CTiltF>::_Emplace_one_at_back<OInk::CTiltF const &>(&v72, &v61);
            goto LABEL_91;
          }
        }
        else if ( v40 == 4 && _mm_cvtsi128_si32(_mm_srli_si128(v39, 8)) == 4 )
        {
          v44 = _mm_shuffle_ps(v38, v38, 255).m128_f32[0];
          if ( v44 == 0.0 )
            v45 = *(float *)&FLOAT_1_0;
          else
            v45 = v44;
          if ( v44 == 0.0 )
            v44 = *(float *)&FLOAT_1_0;
          *(float *)&v61 = (float)((float)*(int *)((char *)&psa[1]->cDims + v31) / v45) - 3.1415927;
          v43 = (float)*(int *)((char *)&psa[1]->cDims + 4 * v75 + v31) / v44;
          goto LABEL_89;
        }
        MsoShipAssertTagProc(24477794);
        v28 = 0;
      }
LABEL_91:
      if ( (int)v8 > v30 )
      {
        v46 = 0;
        if ( (int)v8 > 0 )
        {
          v47 = 4LL * v26;
          v48 = v67;
          v49 = v58;
          do
          {
            if ( v46 != v48 && v46 != v54 && (!v27 || v46 != v49) && (!v28 || v46 != v56 && v46 != v55) )
            {
              std::vector<long>::_Emplace_one_at_back<long const &>(&v76, (char *)psa[1] + v47);
              v48 = v67;
            }
            ++v46;
            v47 += 4;
          }
          while ( v46 < (int)v8 );
          v12 = v80;
          v26 = v63;
          v31 = v65;
        }
        v30 = v59;
      }
      v26 += v8;
      v63 = v26;
      v31 += v81;
      v65 = v31;
      if ( v26 >= plUbound )
        goto LABEL_107;
      v29 = v69;
      v33 = v71;
      v32 = (__int64)v66;
    }
  }
  if ( psa[0] )
    SafeArrayUnaccessData(psa[0]);
  *(_OWORD *)psa = 0;
  Mso::Memory::Free(v12, v24);
  return LBound;
}

```

## disassembly

```asm
0x1806dda60  mov     rax, rsp
0x1806dda63  mov     [rax+10h], rbx
0x1806dda67  mov     [rax+20h], r9
0x1806dda6b  mov     [rax+8], rcx
0x1806dda6f  push    rbp
0x1806dda70  push    rsi
0x1806dda71  push    rdi
0x1806dda72  push    r12
0x1806dda74  push    r13
0x1806dda76  push    r14
0x1806dda78  push    r15
0x1806dda7a  lea     rbp, [rsp-50h]
0x1806dda7f  sub     rsp, 150h
0x1806dda86  movaps  xmmword ptr [rax-48h], xmm6
0x1806dda8a  movaps  xmmword ptr [rax-58h], xmm7
0x1806dda8e  movaps  xmmword ptr [rax-68h], xmm8
0x1806dda93  mov     rdi, rdx
0x1806dda96  xor     r15d, r15d
0x1806dda99  test    r9, r9
0x1806dda9c  jz      loc_1806DE288
0x1806ddaa2  mov     [r9], r15
0x1806ddaa5  cmp     [rcx+10h], r15
0x1806ddaa9  jnz     short loc_1806DDAB5
0x1806ddaab  mov     eax, 80004005h
0x1806ddab0  jmp     loc_1806DE28D
0x1806ddab5  mov     eax, 2003h
0x1806ddaba  cmp     [rdx], ax
0x1806ddabd  jnz     loc_1806DE288
0x1806ddac3  mov     eax, 2011h
0x1806ddac8  cmp     [r8], ax
0x1806ddacc  jnz     loc_1806DE288
0x1806ddad2  mov     [rsp+180h+ppvData], r15
0x1806ddad7  mov     rbx, [r8+8]
0x1806ddadb  lea     rdx, [rsp+180h+ppvData]; ppvData
0x1806ddae0  mov     rcx, rbx; psa
0x1806ddae3  call    cs:__imp_SafeArrayAccessData
0x1806ddae9  test    eax, eax
0x1806ddaeb  js      loc_1806DE28D
0x1806ddaf1  mov     rax, [rsp+180h+ppvData]
0x1806ddaf6  add     rax, 8
0x1806ddafa  mov     [rsp+180h+ppvData], rax
0x1806ddaff  movsxd  r13, dword ptr [rax]
0x1806ddb02  add     rax, 4
0x1806ddb06  mov     [rsp+180h+ppvData], rax
0x1806ddb0b  mov     ecx, r13d
0x1806ddb0e  mov     eax, 20h ; ' '
0x1806ddb13  mul     rcx
0x1806ddb16  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1806ddb1d  mov     [rbp+80h+var_F8], r14
0x1806ddb21  cmovb   rax, r14
0x1806ddb25  xor     edx, edx
0x1806ddb27  mov     rcx, rax
0x1806ddb2a  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1806ddb30  mov     rsi, rax
0x1806ddb33  mov     [rbp+80h+var_70], rax
0x1806ddb37  test    rax, rax
0x1806ddb3a  jnz     short loc_1806DDB46
0x1806ddb3c  mov     eax, 80280001h
0x1806ddb41  jmp     loc_1806DE28D
0x1806ddb46  mov     r8d, r13d
0x1806ddb49  shl     r8d, 5; Size
0x1806ddb4d  mov     rdx, [rsp+180h+ppvData]; Src
0x1806ddb52  mov     rcx, rsi; void *
0x1806ddb55  call    memcpy_0
0x1806ddb5a  mov     rcx, rbx; psa
0x1806ddb5d  call    cs:__imp_SafeArrayUnaccessData
0x1806ddb63  mov     ebx, eax
0x1806ddb65  test    eax, eax
0x1806ddb67  jns     short loc_1806DDB79
0x1806ddb69  mov     rcx, rsi
0x1806ddb6c  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1806ddb72  mov     eax, ebx
0x1806ddb74  jmp     loc_1806DE28D
0x1806ddb79  mov     eax, r14d
0x1806ddb7c  mov     [rsp+180h+var_150], eax
0x1806ddb80  mov     r15d, r14d
0x1806ddb83  mov     [rsp+180h+var_130], r14d
0x1806ddb88  mov     [rsp+180h+var_148], r14d
0x1806ddb8d  mov     r12d, r14d
0x1806ddb90  mov     [rsp+180h+var_14C], r14d
0x1806ddb95  xor     ecx, ecx
0x1806ddb97  test    r13d, r13d
0x1806ddb9a  jz      loc_1806DDC78
0x1806ddba0  mov     r9, rsi
0x1806ddba3  mov     rax, [r9]
0x1806ddba6  mov     rdx, rax
0x1806ddba9  movq    xmm0, qword ptr [r9+8]
0x1806ddbaf  sub     rdx, cs:qword_18129BB70
0x1806ddbb6  jnz     short loc_1806DDBC4
0x1806ddbb8  movq    rdx, xmm0
0x1806ddbbd  sub     rdx, cs:qword_18129BB78
0x1806ddbc4  test    rdx, rdx
0x1806ddbc7  jnz     short loc_1806DDBD1
0x1806ddbc9  mov     r14d, ecx
0x1806ddbcc  jmp     loc_1806DDC57
0x1806ddbd1  mov     rdx, rax
0x1806ddbd4  sub     rdx, cs:qword_18129BB80
0x1806ddbdb  jnz     short loc_1806DDBE9
0x1806ddbdd  movq    rdx, xmm0
0x1806ddbe2  sub     rdx, cs:qword_18129BB88
0x1806ddbe9  test    rdx, rdx
0x1806ddbec  jnz     short loc_1806DDBF6
0x1806ddbee  mov     eax, ecx
0x1806ddbf0  mov     [rsp+180h+var_150], ecx
0x1806ddbf4  jmp     short loc_1806DDC5B
0x1806ddbf6  mov     rdx, rax
0x1806ddbf9  sub     rdx, cs:qword_18129BB50
0x1806ddc00  jnz     short loc_1806DDC0E
0x1806ddc02  movq    rdx, xmm0
0x1806ddc07  sub     rdx, cs:qword_18129BB58
0x1806ddc0e  test    rdx, rdx
0x1806ddc11  jnz     short loc_1806DDC18
0x1806ddc13  mov     r15d, ecx
0x1806ddc16  jmp     short loc_1806DDC57
0x1806ddc18  mov     rdx, rax
0x1806ddc1b  sub     rdx, cs:qword_18129BB60
0x1806ddc22  jnz     short loc_1806DDC30
0x1806ddc24  movq    rdx, xmm0
0x1806ddc29  sub     rdx, cs:qword_18129BB68
0x1806ddc30  test    rdx, rdx
0x1806ddc33  jnz     short loc_1806DDC3B
0x1806ddc35  mov     [rsp+180h+var_148], ecx
0x1806ddc39  jmp     short loc_1806DDC57
0x1806ddc3b  sub     rax, cs:qword_18129BB40
0x1806ddc42  jnz     short loc_1806DDC50
0x1806ddc44  movq    rax, xmm0
0x1806ddc49  sub     rax, cs:qword_18129BB48
0x1806ddc50  test    rax, rax
0x1806ddc53  cmovz   r12d, ecx
0x1806ddc57  mov     eax, [rsp+180h+var_150]
0x1806ddc5b  inc     ecx
0x1806ddc5d  add     r9, 20h ; ' '
0x1806ddc61  cmp     ecx, r13d
0x1806ddc64  jb      loc_1806DDBA3
0x1806ddc6a  mov     [rsp+180h+var_130], r15d
0x1806ddc6f  mov     [rsp+180h+var_14C], r12d
0x1806ddc74  mov     [rbp+80h+var_F8], r14
0x1806ddc78  test    r14d, r14d
0x1806ddc7b  js      loc_1806DE27F
0x1806ddc81  test    eax, eax
0x1806ddc83  js      loc_1806DE27F
0x1806ddc89  mov     rbx, [rdi+8]
0x1806ddc8d  mov     [rsp+180h+psa], rbx
0x1806ddc92  mov     [rsp+180h+psa+8], 0
0x1806ddc9b  test    rbx, rbx
0x1806ddc9e  jz      short loc_1806DDCD6
0x1806ddca0  lea     rdx, [rsp+180h+psa+8]; ppvData
0x1806ddca5  mov     rcx, rbx; psa
0x1806ddca8  call    cs:__imp_SafeArrayAccessData
0x1806ddcae  test    eax, eax
0x1806ddcb0  jns     short loc_1806DDCD6
0x1806ddcb2  mov     ecx, 3D67D1h
0x1806ddcb7  call    cs:__imp_MsoShipAssertTagProc
0x1806ddcbd  mov     rcx, [rsp+180h+psa]; psa
0x1806ddcc2  test    rcx, rcx
0x1806ddcc5  jz      short loc_1806DDCCD
0x1806ddcc7  call    cs:__imp_SafeArrayUnaccessData
0x1806ddccd  xorps   xmm0, xmm0
0x1806ddcd0  movdqu  xmmword ptr [rsp+180h+psa], xmm0
0x1806ddcd6  mov     rcx, rbx; psa
0x1806ddcd9  call    cs:__imp_SafeArrayGetDim
0x1806ddcdf  cmp     eax, 1
0x1806ddce2  jnz     loc_1806DDD8C
0x1806ddce8  mov     [rsp+180h+plLbound], 0
0x1806ddcf0  mov     [rsp+180h+plUbound], 0
0x1806ddcf8  lea     r8, [rsp+180h+plLbound]; plLbound
0x1806ddcfd  mov     edx, eax; nDim
0x1806ddcff  mov     rcx, rbx; psa
0x1806ddd02  call    cs:__imp_SafeArrayGetLBound
0x1806ddd08  mov     edi, eax
0x1806ddd0a  test    eax, eax
0x1806ddd0c  jns     short loc_1806DDD37
0x1806ddd0e  mov     rcx, [rsp+180h+psa]; psa
0x1806ddd13  test    rcx, rcx
0x1806ddd16  jz      short loc_1806DDD1E
0x1806ddd18  call    cs:__imp_SafeArrayUnaccessData
0x1806ddd1e  xorps   xmm0, xmm0
0x1806ddd21  movdqu  xmmword ptr [rsp+180h+psa], xmm0
0x1806ddd27  mov     rcx, rsi
0x1806ddd2a  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1806ddd30  mov     eax, edi
0x1806ddd32  jmp     loc_1806DE28D
0x1806ddd37  lea     r8, [rsp+180h+plUbound]; plUbound
0x1806ddd3c  mov     edx, 1; nDim
0x1806ddd41  mov     rcx, rbx; psa
0x1806ddd44  call    cs:__imp_SafeArrayGetUBound
0x1806ddd4a  mov     ebx, eax
0x1806ddd4c  test    eax, eax
0x1806ddd4e  jns     short loc_1806DDD69
0x1806ddd50  mov     rcx, [rsp+180h+psa]; psa
0x1806ddd55  test    rcx, rcx
0x1806ddd58  jz      loc_1806DE1A9
0x1806ddd5e  call    cs:__imp_SafeArrayUnaccessData
0x1806ddd64  jmp     loc_1806DE1A9
0x1806ddd69  movsxd  r14, [rsp+180h+plLbound]
0x1806ddd6e  mov     [rsp+180h+var_114], r14d
0x1806ddd73  mov     ecx, [rsp+180h+plUbound]
0x1806ddd77  cmp     r14d, ecx
0x1806ddd7a  jg      short loc_1806DDD8C
0x1806ddd7c  mov     eax, ecx
0x1806ddd7e  sub     eax, r14d
0x1806ddd81  inc     eax
0x1806ddd83  xor     edx, edx
0x1806ddd85  div     r13d
0x1806ddd88  test    edx, edx
0x1806ddd8a  jz      short loc_1806DDDA6
0x1806ddd8c  mov     rcx, [rsp+180h+psa]; psa
0x1806ddd91  test    rcx, rcx
0x1806ddd94  jz      short loc_1806DDD9C
0x1806ddd96  call    cs:__imp_SafeArrayUnaccessData
0x1806ddd9c  mov     ebx, 80070057h
0x1806ddda1  jmp     loc_1806DE1A9
0x1806ddda6  shr     r15d, 1Fh
0x1806dddaa  xor     r15b, 1
0x1806dddae  movsxd  rdx, [rsp+180h+var_148]
0x1806dddb3  test    edx, edx
0x1806dddb5  js      short loc_1806DDDC1
0x1806dddb7  test    r12d, r12d
0x1806dddba  js      short loc_1806DDDC1
0x1806dddbc  mov     r12b, 1
0x1806dddbf  jmp     short loc_1806DDDC4
0x1806dddc1  xor     r12b, r12b
0x1806dddc4  xorps   xmm0, xmm0
0x1806dddc7  movdqu  [rbp+80h+var_F0], xmm0
0x1806dddcc  xor     r8d, r8d
0x1806dddcf  mov     [rbp+80h+var_E0], r8
0x1806dddd3  movdqu  [rbp+80h+var_88], xmm0
0x1806dddd8  mov     [rbp+80h+var_78], r8
0x1806ddddc  xorps   xmm1, xmm1
0x1806ddddf  movdqu  [rbp+80h+var_C8], xmm1
0x1806ddde4  mov     [rbp+80h+var_B8], r8
0x1806ddde8  movdqu  [rbp+80h+var_A0], xmm0
0x1806ddded  mov     [rbp+80h+var_90], r8
0x1806dddf1  test    r15b, r15b
0x1806dddf4  jz      short loc_1806DDE03
0x1806dddf6  movzx   eax, r12b
0x1806dddfa  lea     ebx, ds:3[rax*2]
0x1806dde01  jmp     short loc_1806DDE08
0x1806dde03  mov     ebx, 2
0x1806dde08  mov     [rsp+180h+var_12C], ebx
0x1806dde0c  cmp     r14d, ecx
0x1806dde0f  jge     loc_1806DE0AA
0x1806dde15  mov     rax, r13
0x1806dde18  movsxd  r10, [rsp+180h+var_14C]
0x1806dde1d  shl     rax, 2
0x1806dde21  mov     [rbp+80h+var_68], rax
0x1806dde25  lea     rdi, [r14+rdx]
0x1806dde29  shl     rdi, 2
0x1806dde2d  mov     [rsp+180h+var_108], rdi
0x1806dde32  movsxd  rcx, [rsp+180h+var_150]
0x1806dde37  movsxd  r9, dword ptr [rbp+80h+var_F8]
0x1806dde3b  sub     r9, rcx
0x1806dde3e  mov     [rbp+80h+var_100], r9
0x1806dde42  sub     rcx, rdx
0x1806dde45  mov     [rbp+80h+var_D0], rcx
0x1806dde49  sub     r10, rdx
0x1806dde4c  mov     [rbp+80h+var_A8], r10
0x1806dde50  xorps   xmm7, xmm7
0x1806dde53  movss   xmm6, cs:__real@3f800000
0x1806dde5b  movss   xmm8, cs:__real@3c8efa35
0x1806dde64  lea     rdx, [rdi+rcx*4]
0x1806dde68  mov     rcx, [rsp+180h+psa+8]
0x1806dde6d  lea     rax, [rdx+rcx]
0x1806dde71  movd    xmm0, dword ptr [rax+r9*4]
0x1806dde77  cvtdq2ps xmm0, xmm0
0x1806dde7a  movss   [rbp+80h+var_B0], xmm0
0x1806dde7f  movd    xmm1, dword ptr [rcx+rdx]
0x1806dde84  cvtdq2ps xmm1, xmm1
0x1806dde87  movss   [rbp+80h+var_AC], xmm1
0x1806dde8c  mov     rax, qword ptr [rbp+80h+var_F0+8]
0x1806dde90  cmp     rax, r8
0x1806dde93  jz      short loc_1806DDEA5
0x1806dde95  movss   dword ptr [rax], xmm0
0x1806dde99  movss   dword ptr [rax+4], xmm1
0x1806dde9e  add     qword ptr [rbp+80h+var_F0+8], 8
0x1806ddea3  jmp     short loc_1806DDEB6
0x1806ddea5  lea     r8, [rbp+80h+var_B0]
0x1806ddea9  mov     rdx, qword ptr [rbp+80h+var_F0+8]
0x1806ddead  lea     rcx, [rbp+80h+var_F0]
0x1806ddeb1  call    ??$_Emplace_reallocate@AEBVCPointF@OInk@@@?$vector@VCPointF@OInk@@V?$allocator@VCPointF@OInk@@@std@@@std@@AEAAPEAVCPointF@OInk@@QEAV23@AEBV23@@Z; std::vector<OInk::CPointF>::_Emplace_reallocate<OInk::CPointF const &>(OInk::CPointF * const,OInk::CPointF const &)
0x1806ddeb6  test    r15b, r15b
0x1806ddeb9  jz      short loc_1806DDED7
0x1806ddebb  mov     eax, [rsp+180h+var_130]
0x1806ddebf  add     eax, r14d
0x1806ddec2  movsxd  rcx, eax
0x1806ddec5  mov     rax, [rsp+180h+psa+8]
0x1806ddeca  lea     rdx, [rax+rcx*4]
0x1806ddece  lea     rcx, [rbp+80h+var_88]
0x1806dded2  call    ??$_Emplace_one_at_back@AEBJ@?$vector@JV?$allocator@J@std@@@std@@AEAAAEAJAEBJ@Z; std::vector<long>::_Emplace_one_at_back<long const &>(long const &)
0x1806dded7  test    r12b, r12b
0x1806ddeda  jz      loc_1806DE00C
0x1806ddee0  mov     [rsp+180h+var_120], 0
0x1806ddee9  movsxd  rax, [rsp+180h+var_148]
0x1806ddeee  shl     rax, 5
0x1806ddef2  movups  xmm1, xmmword ptr [rax+rsi+10h]
0x1806ddef7  movsxd  rax, [rsp+180h+var_14C]
0x1806ddefc  shl     rax, 5
0x1806ddf00  movups  xmm2, xmmword ptr [rax+rsi+10h]
0x1806ddf05  movdqa  xmm0, xmm1
0x1806ddf09  psrldq  xmm0, 8
  ... truncated ...
```
