# Gfx::DrawShapeBuilderToHDC(Gfx::IShapeBuilder const &,HDC__ *,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const *,Math::TAffine3x3<double> const &,bool)

- ea: `0x1800d0510`
- end: `0x1800d0e77`
- name: `?DrawShapeBuilderToHDC@Gfx@@YA_NAEBUIShapeBuilder@1@PEAUHDC__@@PEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@AEBU?$TAffine3x3@N@5@_N@Z`
- size: `2407`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800205a0`
- `0x180022f40`
- `0x180024818`
- `0x180036d2c`
- `0x180050434`
- `0x1800573f0`
- `0x1800617a0`
- `0x18006ddcc`
- `0x1800ceb9c`
- `0x1800cec34`
- `0x1800cf8d8`
- `0x1800d0510`
- `0x1800d1070`
- `0x1800d13a0`
- `0x1800d1670`
- `0x1800d1790`
- `0x1800d7b90`
- `0x1800d9b60`
- `0x1800da250`
- `0x18014d760`
- `0x18017f4dc`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800d0dc8`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800d0dc8`
- `GDI32!DeleteDC` at `0x1800d0ccc`
- `GDI32!DeleteDC` at `0x1800d0de9`
- `GDI32!DeleteDC` at `0x1800d0ccc`
- `GDI32!DeleteDC` at `0x1800d0de9`
- `GDI32!SelectObject` at `0x1800d0cc3`
- `GDI32!SelectObject` at `0x1800d0de0`
- `GDI32!SelectObject` at `0x1800d0cc3`
- `GDI32!SelectObject` at `0x1800d0de0`
- `GDI32!GetObjectType` at `0x1800d0767`
- `GDI32!GetObjectType` at `0x1800d0767`
- `GDI32!DeleteObject` at `0x1800d0cd6`
- `GDI32!DeleteObject` at `0x1800d0cd6`
- `MSIMG32!AlphaBlend` at `0x1800d0ca3`
- `MSIMG32!AlphaBlend` at `0x1800d0ca3`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char Gfx::DrawShapeBuilderToHDC(const struct Gfx::IShapeBuilder *a1, HDC a2, __m256i *a3, ...)
{
  __int64 v3; // rsi
  const struct Gfx::ViewScale *ViewScaleForShape; // rbx
  __int64 (__fastcall *v8)(const struct Gfx::IShapeBuilder *, _BYTE *, _QWORD, _QWORD, int); // rax
  __m128i *v9; // rax
  double v10; // xmm3_8
  __m128d v11; // xmm1
  __m128d v12; // xmm2
  double v13; // xmm2_8
  __int128 v14; // xmm4
  __m128i *v15; // rax
  __int32 v16; // r11d
  __int32 v17; // ebx
  __int32 v18; // edx
  __int32 v19; // r8d
  __m256i *p_hdc; // r9
  __m128i v21; // xmm0
  __int64 v22; // rcx
  __m128i v23; // xmm1
  __int32 v24; // r9d
  __int32 v25; // eax
  __int32 v26; // r10d
  __int32 v27; // ecx
  __int64 v28; // rax
  DWORD ObjectType; // eax
  bool v30; // bl
  char v31; // r15
  int v32; // eax
  __int64 v33; // r8
  __int64 v34; // rcx
  char result; // al
  bool v36; // bl
  unsigned int v37; // edx
  int v38; // edi
  int hSrc; // esi
  bool v40; // al
  unsigned __int64 *v41; // rax
  unsigned __int64 v42; // rbx
  __int64 *v43; // rax
  __int64 v44; // rdi
  __int64 v45; // rcx
  char v46; // si
  __int64 v47; // rax
  __int64 v48; // rcx
  unsigned int OptimalRenderingPolicyForTarget; // ebx
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rax
  Gfx **v53; // rax
  unsigned int v54; // r8d
  HBITMAP HBITMAPFromImage; // rbx
  int v56; // ecx
  int v57; // r9d
  HDC v58; // rdi
  char v59; // al
  __int64 v60; // [rsp+0h] [rbp-198h] BYREF
  int hDest[2]; // [rsp+20h] [rbp-178h]
  int wSrc; // [rsp+40h] [rbp-158h]
  __m256i hdc; // [rsp+60h] [rbp-138h] BYREF
  __int128 v64; // [rsp+80h] [rbp-118h]
  __int64 v65; // [rsp+90h] [rbp-108h] BYREF
  int yoriginDest[4]; // [rsp+A0h] [rbp-F8h] BYREF
  __int64 v67; // [rsp+B0h] [rbp-E8h] BYREF
  __m128i v68; // [rsp+B8h] [rbp-E0h] BYREF
  __m128i v69; // [rsp+C8h] [rbp-D0h]
  int v70; // [rsp+E0h] [rbp-B8h] BYREF
  __int128 v71; // [rsp+E4h] [rbp-B4h]
  __int64 v72; // [rsp+F8h] [rbp-A0h]
  __int128 v73; // [rsp+100h] [rbp-98h]
  int v74; // [rsp+110h] [rbp-88h]
  __int128 v75; // [rsp+118h] [rbp-80h]
  int v76; // [rsp+128h] [rbp-70h]
  char v77; // [rsp+12Ch] [rbp-6Ch]
  char v78; // [rsp+12Dh] [rbp-6Bh]
  _BYTE v79[104]; // [rsp+130h] [rbp-68h] BYREF
  unsigned __int64 ftn; // [rsp+1A0h] [rbp+8h] BYREF
  __int64 v81; // [rsp+1B0h] [rbp+18h] BYREF
  __int64 v82; // [rsp+1B8h] [rbp+20h] BYREF
  va_list va; // [rsp+1B8h] [rbp+20h]
  __int64 v84; // [rsp+1C0h] [rbp+28h]
  va_list va1; // [rsp+1C8h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v82 = va_arg(va1, _QWORD);
  v84 = va_arg(va1, _QWORD);
  v3 = v82;
  ViewScaleForShape = Gfx::ViewScale::GetViewScaleForShape(a1);
  v8 = *(__int64 (__fastcall **)(const struct Gfx::IShapeBuilder *, _BYTE *, _QWORD, _QWORD, int))(*(_QWORD *)a1 + 272LL);
  LOBYTE(hDest[0]) = 1;
  v9 = (__m128i *)v8(a1, v79, 0, 0, hDest[0]);
  v68 = *v9;
  v69 = v9[1];
  v10 = *((float *)ViewScaleForShape + 11);
  v11 = _mm_cvtps_pd((__m128)*((unsigned int *)ViewScaleForShape + 4));
  v12.m128d_f64[1] = v11.m128d_f64[1];
  v13 = v11.m128d_f64[0] * *((double *)ViewScaleForShape + 4);
  v14 = *(_OWORD *)(v3 + 32);
  v11.m128d_f64[0] = v11.m128d_f64[0] * *((double *)ViewScaleForShape + 3) * *((float *)ViewScaleForShape + 10);
  *(__m128d *)hdc.m256i_i8 = _mm_mul_pd(_mm_unpacklo_pd(v11, v11), *(__m128d *)v3);
  v12.m128d_f64[0] = v13 * v10;
  *(__m128d *)&hdc.m256i_u64[2] = _mm_mul_pd(_mm_unpacklo_pd(v12, v12), *(__m128d *)(v3 + 16));
  v64 = v14;
  v15 = (__m128i *)Math::GetTransformedBounds<Math::TUnits<double,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(
                     v79,
                     &v68,
                     &hdc);
  v68 = *v15;
  v69 = v15[1];
  Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(&hdc, &v68);
  v16 = hdc.m256i_i32[0];
  v17 = hdc.m256i_i32[2];
  v18 = hdc.m256i_i32[1];
  v19 = hdc.m256i_i32[3];
  if ( hdc.m256i_i32[0] < hdc.m256i_i32[2] && hdc.m256i_i32[1] < hdc.m256i_i32[3] )
  {
    v16 = hdc.m256i_i32[0] - 2;
    hdc.m256i_i32[0] -= 2;
    v18 = hdc.m256i_i32[1] - 2;
    hdc.m256i_i32[1] -= 2;
    v17 = hdc.m256i_i32[2] + 2;
    hdc.m256i_i32[2] += 2;
    v19 = hdc.m256i_i32[3] + 2;
    hdc.m256i_i32[3] += 2;
  }
  p_hdc = &hdc;
  if ( a3 )
    p_hdc = a3;
  try
  {
    v21 = *(__m128i *)p_hdc->m256i_i8;
    v68 = v21;
    v22 = p_hdc->m256i_i64[1];
    if ( v21.m128i_i32[0] >= (int)v22 || v21.m128i_i32[1] >= SHIDWORD(v22) )
      return 1;
    v23 = v21;
    *(__m128i *)hdc.m256i_i8 = v21;
    if ( v16 > v17 || v18 > v19 )
    {
      v26 = 1;
      v27 = 1;
      *(_OWORD *)hdc.m256i_i8 = 0x100000001uLL;
      v24 = 0;
      v25 = 0;
      v23 = (__m128i)0x100000001uLL;
    }
    else
    {
      v24 = hdc.m256i_i32[3];
      v25 = hdc.m256i_i32[2];
      v26 = hdc.m256i_i32[1];
      v27 = hdc.m256i_i32[0];
    }
    if ( v27 <= v25 && v26 <= v24 )
    {
      if ( v16 > v27 )
        v27 = v16;
      hdc.m256i_i32[0] = v27;
      if ( v17 < v25 )
        v25 = v17;
      hdc.m256i_i32[2] = v25;
      if ( v18 > v26 )
        v26 = v18;
      hdc.m256i_i32[1] = v26;
      if ( v19 < v24 )
        v24 = v19;
      hdc.m256i_i32[3] = v24;
      v23 = *(__m128i *)hdc.m256i_i8;
    }
    *(__m128i *)yoriginDest = v23;
    if ( v27 >= v25 || v23.m128i_i32[1] >= _mm_srli_si128(v23, 8).m128i_i32[1] )
    {
      v31 = v84;
LABEL_45:
      *(__m128i *)hdc.m256i_i8 = _mm_load_si128((const __m128i *)&_xmm);
      ftn = (unsigned __int64)a2;
      v41 = (unsigned __int64 *)Mso::Make<GEL::DC,GEL::DC,HDC__ * &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &>(
                                  (__int64 *)va,
                                  &ftn,
                                  &hdc);
      v42 = *v41;
      *v41 = 0;
      if ( v82 )
      {
        v82 = 0;
        Mso::RefCountedObject<GEL::IDC,>::Release();
      }
      ftn = v42;
      v43 = (__int64 *)GEL::IScene::Create((__int64 *)va, v42);
      v44 = *v43;
      *v43 = 0;
      v45 = v82;
      if ( v82 )
      {
        v82 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 8LL))(v45);
      }
      v46 = Gfx::DrawShapeBuilderToGELScene((_DWORD)a1, v44, (_DWORD)a3, v3, v31, 0);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
      if ( v42 )
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v42 + 8LL))(v42);
      return v46;
    }
    Math::Inverse<double>(&hdc, v3);
    Math::GetTransformedBounds<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(
      v79,
      &v68,
      v28);
    Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(&hdc, v79);
    ObjectType = GetObjectType(a2);
    v30 = ((ObjectType - 3) & 0xFFFFFFF6) == 0 && ObjectType != 11;
    v81 = 0;
    v70 = 0;
    v71 = *(_OWORD *)hdc.m256i_i8;
    v72 = 0;
    v73 = 0;
    v74 = 3;
    v75 = 0;
    v76 = 1;
    v78 = 1;
    v31 = v84;
    v77 = v84;
    v32 = (*(__int64 (__fastcall **)(const struct Gfx::IShapeBuilder *, __int64 *, int *))(*(_QWORD *)a1 + 424LL))(
            a1,
            &v81,
            &v70);
    v34 = v81;
    if ( v32 != 1 && v81 )
    {
      if ( v32 )
      {
        (*(void (**)(void))(*(_QWORD *)v81 + 8LL))();
        return 0;
      }
      v36 = 0;
      if ( v30 )
      {
        LOBYTE(v33) = 1;
        v59 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v81 + 72LL))(v81, 0, v33);
        v34 = v81;
        if ( v59 )
          v36 = 1;
      }
      v37 = yoriginDest[3];
      if ( yoriginDest[0] > yoriginDest[2] || yoriginDest[1] > yoriginDest[3] )
      {
        ftn = 0;
      }
      else
      {
        LODWORD(ftn) = yoriginDest[2] - yoriginDest[0];
        HIDWORD(ftn) = yoriginDest[3] - yoriginDest[1];
      }
      v38 = ftn;
      hSrc = HIDWORD(ftn);
      v40 = (unsigned int)ftn > 0x800 || HIDWORD(ftn) > 0x800;
      if ( v36 && !v40 )
      {
        v68.m128i_i32[0] = 1119879168;
        if ( yoriginDest[0] > yoriginDest[2] || yoriginDest[1] > yoriginDest[3] )
        {
          ftn = 0;
        }
        else
        {
          v37 = yoriginDest[3] - yoriginDest[1];
          LODWORD(ftn) = yoriginDest[2] - yoriginDest[0];
          HIDWORD(ftn) = yoriginDest[3] - yoriginDest[1];
        }
        v47 = ftn;
        ftn = __PAIR64__(LODWORD(FLOAT_96_0), v68.m128i_u32[0]);
        hdc.m256i_i64[0] = v47;
        *(_QWORD *)hDest = Gfx::GetBestFactoryForBitmapTarget((Gfx *)8, v37);
        Gfx::IBitmapTarget::Create((unsigned int)&v68, (unsigned int)&hdc, (unsigned int)&ftn, 1, *(__int64 *)hDest, 8);
        v48 = v68.m128i_i64[0];
        v68.m128i_i64[0] = 0;
        v65 = v48;
        OptimalRenderingPolicyForTarget = Gfx::GetOptimalRenderingPolicyForTarget();
        v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 24LL))(v65);
        LODWORD(ftn) = *(_DWORD *)v50;
        *(double *)hdc.m256i_i64 = (float)(914400.0 / *(float *)&ftn);
        *(_OWORD *)&hdc.m256i_u64[1] = 0;
        *(double *)&hdc.m256i_i64[3] = (float)(914400.0 / *(float *)(v50 + 4));
        v64 = 0;
        GEL::ITopLevelEffect::Create(&v67, v81, &hdc, OptimalRenderingPolicyForTarget);
        hdc.m256i_i64[0] = (__int64)&v67;
        hdc.m256i_i64[1] = (__int64)&v65;
        hdc.m256i_i64[2] = (__int64)yoriginDest;
        sub_1800CEC34(v65, v51, &hdc);
        v68.m128i_i64[0] = 0;
        v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 464LL))(v65);
        v53 = (Gfx **)GEL::IImage::Create(&ftn, v52);
        HBITMAPFromImage = Gfx::CreateHBITMAPFromImage(*v53, 0, v54);
        v68.m128i_i64[0] = (__int64)HBITMAPFromImage;
        if ( ftn )
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)ftn + 8LL))(ftn);
        if ( HBITMAPFromImage )
        {
          *(_OWORD *)hdc.m256i_i8 = 0;
          Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)&hdc, a2, HBITMAPFromImage);
          LODWORD(ftn) = 33488896;
          if ( yoriginDest[0] > yoriginDest[2] || yoriginDest[1] > yoriginDest[3] )
            v56 = 0;
          else
            v56 = yoriginDest[3] - yoriginDest[1];
          if ( yoriginDest[0] > yoriginDest[2] || yoriginDest[1] > yoriginDest[3] )
            v57 = 0;
          else
            v57 = yoriginDest[2] - yoriginDest[0];
          wSrc = v38;
          v58 = (HDC)hdc.m256i_i64[0];
          if ( AlphaBlend(
                 a2,
                 yoriginDest[0],
                 yoriginDest[1],
                 v57,
                 v56,
                 (HDC)hdc.m256i_i64[0],
                 0,
                 0,
                 wSrc,
                 hSrc,
                 (BLENDFUNCTION)ftn) )
          {
            if ( v58 )
            {
              if ( hdc.m256i_i64[1] )
                SelectObject(v58, (HGDIOBJ)hdc.m256i_i64[1]);
              DeleteDC(v58);
            }
            DeleteObject(HBITMAPFromImage);
            if ( v67 )
            {
              if ( *(__int64 (**)(void))(*(_QWORD *)(v67 + 8) + 8LL) == Mso::RefCountedObject<GEL::ITopLevelEffect,>::Release )
                Mso::RefCountedObject<GEL::ITopLevelEffect,>::Release();
              else
                (*(void (__fastcall **)(__int64))(*(_QWORD *)(v67 + 8) + 8LL))(v67 + 8);
            }
            if ( v65 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 8LL))(v65);
            if ( v81 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 8LL))(v81);
            return 1;
          }
          MsoShipAssertTagProc(2942093);
          if ( v58 )
          {
            if ( hdc.m256i_i64[1] )
              SelectObject(v58, (HGDIOBJ)hdc.m256i_i64[1]);
            DeleteDC(v58);
          }
        }
        Ofc::CHBitmap::Reset((Ofc::CHBitmap *)&v68);
        if ( v67 )
        {
          if ( *(__int64 (**)(void))(*(_QWORD *)(v67 + 8) + 8LL) == Mso::RefCountedObject<GEL::ITopLevelEffect,>::Release )
            Mso::RefCountedObject<GEL::ITopLevelEffect,>::Release();
          else
            (*(void (__fastcall **)(__int64))(*(_QWORD *)(v67 + 8) + 8LL))(v67 + 8);
        }
        if ( v65 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 8LL))(v65);
        v34 = v81;
      }
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
      LODWORD(v3) = v82;
      goto LABEL_45;
    }
    if ( v81 )
      (*(void (**)(void))(*(_QWORD *)v81 + 8LL))();
    result = 1;
  }
  catch ( ... )
  {
    Ofc::ConvertExceptionHelper(0, (bool)&v60);
  }
  return result;
}

```

## disassembly

```asm
0x1800d0510  mov     [rsp+arg_18], r9
0x1800d0515  push    rbx
0x1800d0516  push    rsi
0x1800d0517  push    rdi
0x1800d0518  push    r12
0x1800d051a  push    r13
0x1800d051c  push    r14
0x1800d051e  push    r15
0x1800d0520  sub     rsp, 160h
0x1800d0527  mov     rsi, r9
0x1800d052a  mov     r13, r8
0x1800d052d  mov     r14, rdx
0x1800d0530  mov     r12, rcx
0x1800d0533  call    ?GetViewScaleForShape@ViewScale@Gfx@@SAAEBV12@AEBUIShapeBuilder@2@@Z; Gfx::ViewScale::GetViewScaleForShape(Gfx::IShapeBuilder const &)
0x1800d0538  mov     rbx, rax
0x1800d053b  mov     r8, [r12]
0x1800d053f  mov     rax, [r8+110h]
0x1800d0546  mov     edi, 1
0x1800d054b  mov     byte ptr [rsp+198h+hDest], dil
0x1800d0550  xor     r9d, r9d
0x1800d0553  xor     r8d, r8d
0x1800d0556  lea     rdx, [rsp+198h+var_68]
0x1800d055e  mov     rcx, r12
0x1800d0561  call    cs:__guard_dispatch_icall_fptr
0x1800d0567  movups  xmm0, xmmword ptr [rax]
0x1800d056a  movups  [rsp+198h+var_E0], xmm0
0x1800d0572  movups  xmm1, xmmword ptr [rax+10h]
0x1800d0576  movups  [rsp+198h+var_D0], xmm1
0x1800d057e  movss   xmm3, dword ptr [rbx+2Ch]
0x1800d0583  cvtps2pd xmm3, xmm3
0x1800d0586  movss   xmm1, dword ptr [rbx+10h]
0x1800d058b  cvtps2pd xmm1, xmm1
0x1800d058e  movaps  xmm2, xmm1
0x1800d0591  mulsd   xmm2, qword ptr [rbx+20h]
0x1800d0596  movups  xmm4, xmmword ptr [rsi+20h]
0x1800d059a  mulsd   xmm1, qword ptr [rbx+18h]
0x1800d059f  movss   xmm0, dword ptr [rbx+28h]
0x1800d05a4  cvtps2pd xmm0, xmm0
0x1800d05a7  mulsd   xmm1, xmm0
0x1800d05ab  unpcklpd xmm1, xmm1
0x1800d05af  movups  xmm0, xmmword ptr [rsi]
0x1800d05b2  mulpd   xmm1, xmm0
0x1800d05b6  movups  xmmword ptr [rsp+198h+hdc], xmm1
0x1800d05bb  mulsd   xmm2, xmm3
0x1800d05bf  movaps  xmm1, xmm2
0x1800d05c2  unpcklpd xmm1, xmm1
0x1800d05c6  movups  xmm0, xmmword ptr [rsi+10h]
0x1800d05ca  mulpd   xmm1, xmm0
0x1800d05ce  movups  [rsp+198h+var_128], xmm1
0x1800d05d3  movups  [rsp+198h+var_118], xmm4
0x1800d05db  lea     r8, [rsp+198h+hdc]
0x1800d05e0  lea     rdx, [rsp+198h+var_E0]
0x1800d05e8  lea     rcx, [rsp+198h+var_68]
0x1800d05f0  call    ??$GetTransformedBounds@V?$TUnits@NUDevicePixels@Math@@@Math@@NV12@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU10@AEBU?$TAffine3x3@N@0@@Z; Math::GetTransformedBounds<Math::TUnits<double,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TAffine3x3<double> const &)
0x1800d05f5  movups  xmm0, xmmword ptr [rax]
0x1800d05f8  movups  [rsp+198h+var_E0], xmm0
0x1800d0600  movups  xmm1, xmmword ptr [rax+10h]
0x1800d0604  movups  [rsp+198h+var_D0], xmm1
0x1800d060c  lea     rdx, [rsp+198h+var_E0]
0x1800d0614  lea     rcx, [rsp+198h+hdc]
0x1800d0619  call    ??$snap_outward_cast@V?$TUnits@HUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &)
0x1800d061e  mov     r11d, dword ptr [rsp+198h+hdc]
0x1800d0623  mov     ebx, dword ptr [rsp+198h+hdc+8]
0x1800d0627  mov     edx, dword ptr [rsp+198h+hdc+4]
0x1800d062b  mov     r8d, dword ptr [rsp+198h+hdc+0Ch]
0x1800d0630  cmp     r11d, ebx
0x1800d0633  jge     short loc_1800D065A
0x1800d0635  cmp     edx, r8d
0x1800d0638  jge     short loc_1800D065A
0x1800d063a  sub     r11d, 2
0x1800d063e  mov     dword ptr [rsp+198h+hdc], r11d
0x1800d0643  sub     edx, 2
0x1800d0646  mov     dword ptr [rsp+198h+hdc+4], edx
0x1800d064a  add     ebx, 2
0x1800d064d  mov     dword ptr [rsp+198h+hdc+8], ebx
0x1800d0651  add     r8d, 2
0x1800d0655  mov     dword ptr [rsp+198h+hdc+0Ch], r8d
0x1800d065a  lea     r9, [rsp+198h+hdc]
0x1800d065f  test    r13, r13
0x1800d0662  cmovnz  r9, r13
0x1800d0666  movups  xmm0, xmmword ptr [r9]
0x1800d066a  movups  [rsp+198h+var_E0], xmm0
0x1800d0672  movq    rax, xmm0
0x1800d0677  mov     rcx, [r9+8]
0x1800d067b  cmp     eax, ecx
0x1800d067d  jge     loc_1800D09D7
0x1800d0683  shr     rcx, 20h
0x1800d0687  shr     rax, 20h
0x1800d068b  cmp     eax, ecx
0x1800d068d  jge     loc_1800D09D7
0x1800d0693  movups  xmm1, xmm0
0x1800d0696  movaps  xmmword ptr [rsp+198h+hdc], xmm0
0x1800d069b  cmp     r11d, ebx
0x1800d069e  jg      loc_1800D09FB
0x1800d06a4  cmp     edx, r8d
0x1800d06a7  jg      loc_1800D09FB
0x1800d06ad  mov     r9d, dword ptr [rsp+198h+hdc+0Ch]
0x1800d06b2  mov     eax, dword ptr [rsp+198h+hdc+8]
0x1800d06b6  mov     r10d, dword ptr [rsp+198h+hdc+4]
0x1800d06bb  mov     ecx, dword ptr [rsp+198h+hdc]
0x1800d06bf  cmp     ecx, eax
0x1800d06c1  jg      short loc_1800D06F9
0x1800d06c3  cmp     r10d, r9d
0x1800d06c6  jg      short loc_1800D06F9
0x1800d06c8  cmp     r11d, ecx
0x1800d06cb  cmovg   ecx, r11d
0x1800d06cf  mov     dword ptr [rsp+198h+hdc], ecx
0x1800d06d3  cmp     ebx, eax
0x1800d06d5  cmovl   eax, ebx
0x1800d06d8  mov     dword ptr [rsp+198h+hdc+8], eax
0x1800d06dc  cmp     edx, r10d
0x1800d06df  cmovg   r10d, edx
0x1800d06e3  mov     dword ptr [rsp+198h+hdc+4], r10d
0x1800d06e8  cmp     r8d, r9d
0x1800d06eb  cmovl   r9d, r8d
0x1800d06ef  mov     dword ptr [rsp+198h+hdc+0Ch], r9d
0x1800d06f4  movaps  xmm1, xmmword ptr [rsp+198h+hdc]
0x1800d06f9  movdqa  xmmword ptr [rsp+198h+yoriginDest], xmm1
0x1800d0702  cmp     ecx, eax
0x1800d0704  jge     loc_1800D09EE
0x1800d070a  movdqa  xmm0, xmm1
0x1800d070e  psrldq  xmm0, 8
0x1800d0713  movq    rcx, xmm0
0x1800d0718  shr     rcx, 20h
0x1800d071c  movq    rax, xmm1
0x1800d0721  shr     rax, 20h
0x1800d0725  cmp     eax, ecx
0x1800d0727  jge     loc_1800D09EE
0x1800d072d  mov     rdx, rsi
0x1800d0730  lea     rcx, [rsp+198h+hdc]
0x1800d0735  call    ??$Inverse@N@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@@Z; Math::Inverse<double>(Math::TAffine3x3<double> const &)
0x1800d073a  mov     r8, rax
0x1800d073d  lea     rdx, [rsp+198h+var_E0]
0x1800d0745  lea     rcx, [rsp+198h+var_68]
0x1800d074d  call    ??$GetTransformedBounds@V?$TUnits@HUDevicePixels@Math@@@Math@@NV?$TUnits@NUDevicePixels@Math@@@2@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TAffine3x3@N@0@@Z; Math::GetTransformedBounds<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,Math::TAffine3x3<double> const &)
0x1800d0752  lea     rdx, [rsp+198h+var_68]
0x1800d075a  lea     rcx, [rsp+198h+hdc]
0x1800d075f  call    ??$snap_outward_cast@V?$TUnits@HUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &)
0x1800d0764  mov     rcx, r14; h
0x1800d0767  call    cs:__imp_GetObjectType
0x1800d076d  lea     ecx, [rax-3]
0x1800d0770  test    ecx, 0FFFFFFF6h
0x1800d0776  jnz     short loc_1800D0782
0x1800d0778  cmp     eax, 0Bh
0x1800d077b  jz      short loc_1800D0782
0x1800d077d  mov     bl, dil
0x1800d0780  jmp     short loc_1800D0784
0x1800d0782  xor     bl, bl
0x1800d0784  mov     [rsp+198h+arg_10], 0
0x1800d0790  mov     [rsp+198h+var_B8], 0
0x1800d079b  movups  xmm0, xmmword ptr [rsp+198h+hdc]
0x1800d07a0  movdqu  [rsp+198h+var_B4], xmm0
0x1800d07a9  mov     [rsp+198h+var_A0], 0
0x1800d07b5  xorps   xmm1, xmm1
0x1800d07b8  movdqa  [rsp+198h+var_98], xmm1
0x1800d07c1  mov     [rsp+198h+var_88], 3
0x1800d07cc  xorps   xmm0, xmm0
0x1800d07cf  movups  [rsp+198h+var_80], xmm0
0x1800d07d7  mov     [rsp+198h+var_70], edi
0x1800d07de  mov     [rsp+198h+var_6B], dil
0x1800d07e6  mov     r15b, byte ptr [rsp+198h+arg_20]
0x1800d07ee  mov     [rsp+198h+var_6C], r15b
0x1800d07f6  mov     rax, [r12]
0x1800d07fa  lea     r8, [rsp+198h+var_B8]
0x1800d0802  lea     rdx, [rsp+198h+arg_10]
0x1800d080a  mov     rcx, r12
0x1800d080d  mov     rax, [rax+1A8h]
0x1800d0814  call    cs:__guard_dispatch_icall_fptr
0x1800d081a  mov     rcx, [rsp+198h+arg_10]
0x1800d0822  cmp     eax, edi
0x1800d0824  jnz     short loc_1800D084E
0x1800d0826  test    rcx, rcx
0x1800d0829  jz      short loc_1800D0838
0x1800d082b  mov     rax, [rcx]
0x1800d082e  mov     rax, [rax+8]
0x1800d0832  call    cs:__guard_dispatch_icall_fptr
0x1800d0838  mov     al, dil
0x1800d083b  add     rsp, 160h
0x1800d0842  pop     r15
0x1800d0844  pop     r14
0x1800d0846  pop     r13
0x1800d0848  pop     r12
0x1800d084a  pop     rdi
0x1800d084b  pop     rsi
0x1800d084c  pop     rbx
0x1800d084d  retn
0x1800d084e  test    rcx, rcx
0x1800d0851  jz      short loc_1800D0826
0x1800d0853  test    eax, eax
0x1800d0855  jnz     loc_1800D0D77
0x1800d085b  test    bl, bl
0x1800d085d  jnz     loc_1800D0D8B
0x1800d0863  xor     bl, bl
0x1800d0865  mov     r11, qword ptr [rsp+198h+yoriginDest]
0x1800d086d  mov     r9, qword ptr [rsp+198h+yoriginDest+8]
0x1800d0875  mov     r10d, [rsp+198h+yoriginDest+4]
0x1800d087d  mov     edx, [rsp+198h+yoriginDest+0Ch]
0x1800d0884  cmp     r11d, r9d
0x1800d0887  jg      loc_1800D0D46
0x1800d088d  cmp     r10d, edx
0x1800d0890  jg      loc_1800D0D46
0x1800d0896  mov     eax, edx
0x1800d0898  sub     eax, r10d
0x1800d089b  mov     r8d, r9d
0x1800d089e  sub     r8d, r11d
0x1800d08a1  mov     dword ptr [rsp+198h+arg_0], r8d
0x1800d08a9  mov     dword ptr [rsp+198h+arg_0+4], eax
0x1800d08b0  mov     rdi, [rsp+198h+arg_0]
0x1800d08b8  mov     [rsp+198h+arg_0], rdi
0x1800d08c0  mov     eax, 800h
0x1800d08c5  mov     esi, dword ptr [rsp+198h+arg_0+4]
0x1800d08cc  cmp     edi, eax
0x1800d08ce  jbe     loc_1800D09DF
0x1800d08d4  mov     al, 1
0x1800d08d6  test    bl, bl
0x1800d08d8  jnz     loc_1800D0A20
0x1800d08de  test    rcx, rcx
0x1800d08e1  jz      short loc_1800D08F0
0x1800d08e3  mov     rax, [rcx]
0x1800d08e6  mov     rax, [rax+8]
0x1800d08ea  call    cs:__guard_dispatch_icall_fptr
0x1800d08f0  mov     rsi, [rsp+198h+arg_18]
0x1800d08f8  movdqa  xmm0, cs:__xmm@00000000000000000000000100000001
0x1800d0900  movdqu  xmmword ptr [rsp+198h+hdc], xmm0
0x1800d0906  mov     [rsp+198h+arg_0], r14
0x1800d090e  lea     r8, [rsp+198h+hdc]
0x1800d0913  lea     rdx, [rsp+198h+arg_0]
0x1800d091b  lea     rcx, [rsp+198h+arg_18]
0x1800d0923  call    ??$Make@VDC@GEL@@V12@AEAPEAUHDC__@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Mso@@YA?AV?$TCntPtr@VDC@GEL@@@0@AEAPEAUHDC__@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z; Mso::Make<GEL::DC,GEL::DC,HDC__ * &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &>(HDC__ * &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1800d0928  mov     rbx, [rax]
0x1800d092b  mov     qword ptr [rax], 0
0x1800d0932  mov     rcx, [rsp+198h+arg_18]
0x1800d093a  test    rcx, rcx
0x1800d093d  jnz     loc_1800D0E59
0x1800d0943  mov     [rsp+198h+arg_0], rbx
0x1800d094b  mov     rdx, rbx
0x1800d094e  lea     rcx, [rsp+198h+arg_18]
0x1800d0956  call    ?Create@IScene@GEL@@SA?AV?$TCntPtr@UIScene@GEL@@@Mso@@AEAUIDevice@2@@Z; GEL::IScene::Create(GEL::IDevice &)
0x1800d095b  mov     rdi, [rax]
0x1800d095e  xor     r14d, r14d
0x1800d0961  mov     [rax], r14
0x1800d0964  mov     rcx, [rsp+198h+arg_18]
0x1800d096c  test    rcx, rcx
0x1800d096f  jz      short loc_1800D0986
0x1800d0971  mov     [rsp+198h+arg_18], r14
0x1800d0979  mov     rax, [rcx]
0x1800d097c  mov     rax, [rax+8]
0x1800d0980  call    cs:__guard_dispatch_icall_fptr
0x1800d0986  mov     [rsp+198h+hdcSrc], r14
0x1800d098b  mov     byte ptr [rsp+198h+hDest], r15b
0x1800d0990  mov     r9, rsi
0x1800d0993  mov     r8, r13
0x1800d0996  mov     rdx, rdi
0x1800d0999  mov     rcx, r12
0x1800d099c  call    ?DrawShapeBuilderToGELScene@Gfx@@YA_NAEBUIShapeBuilder@1@AEAUIScene@GEL@@PEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@AEBU?$TAffine3x3@N@6@_NPEBURenderOptions@1@@Z; Gfx::DrawShapeBuilderToGELScene(Gfx::IShapeBuilder const &,GEL::IScene &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const *,Math::TAffine3x3<double> const &,bool,Gfx::RenderOptions const *)
0x1800d09a1  mov     sil, al
0x1800d09a4  test    rdi, rdi
0x1800d09a7  jz      short loc_1800D09BA
0x1800d09a9  mov     rdx, [rdi]
0x1800d09ac  mov     rcx, rdi
0x1800d09af  mov     rax, [rdx+8]
0x1800d09b3  call    cs:__guard_dispatch_icall_fptr
0x1800d09b9  nop
0x1800d09ba  test    rbx, rbx
0x1800d09bd  jz      short loc_1800D09CF
0x1800d09bf  mov     rax, [rbx]
0x1800d09c2  mov     rcx, rbx
0x1800d09c5  mov     rax, [rax+8]
0x1800d09c9  call    cs:__guard_dispatch_icall_fptr
0x1800d09cf  mov     al, sil
0x1800d09d2  jmp     loc_1800D083B
0x1800d09d7  mov     al, dil
0x1800d09da  jmp     loc_1800D083B
0x1800d09df  cmp     esi, eax
0x1800d09e1  ja      loc_1800D08D4
0x1800d09e7  xor     al, al
0x1800d09e9  jmp     loc_1800D08D6
0x1800d09ee  mov     r15b, byte ptr [rsp+198h+arg_20]
0x1800d09f6  jmp     loc_1800D08F8
0x1800d09fb  mov     r10d, edi
0x1800d09fe  mov     dword ptr [rsp+198h+hdc+4], edi
0x1800d0a02  mov     ecx, edi
0x1800d0a04  mov     dword ptr [rsp+198h+hdc], ecx
0x1800d0a08  xor     r9d, r9d
0x1800d0a0b  mov     dword ptr [rsp+198h+hdc+0Ch], r9d
0x1800d0a10  xor     eax, eax
0x1800d0a12  mov     dword ptr [rsp+198h+hdc+8], eax
0x1800d0a16  movaps  xmm1, xmmword ptr [rsp+198h+hdc]
0x1800d0a1b  jmp     loc_1800D06BF
0x1800d0a20  test    al, al
0x1800d0a22  jnz     loc_1800D08DE
0x1800d0a28  movss   xmm1, cs:__real@42c00000
0x1800d0a30  mov     dword ptr [rsp+198h+var_E0], 42C00000h
0x1800d0a3b  cmp     r11d, r9d
0x1800d0a3e  jg      loc_1800D0D57
0x1800d0a44  cmp     r10d, edx
0x1800d0a47  jg      loc_1800D0D57
0x1800d0a4d  sub     edx, r10d; unsigned int
0x1800d0a50  sub     r9d, r11d
0x1800d0a53  mov     dword ptr [rsp+198h+arg_0], r9d
  ... truncated ...
```
