# Gfx::DrawShapeBuilderToHDC(Gfx::IShapeBuilder const &,HDC__ *,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const *,Math::TAffine3x3<double> const &,bool)

- ea: `0x1800ce890`
- end: `0x1800cf1f7`
- name: `?DrawShapeBuilderToHDC@Gfx@@YA_NAEBUIShapeBuilder@1@PEAUHDC__@@PEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@AEBU?$TAffine3x3@N@5@_N@Z`
- size: `2407`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180020af0`
- `0x180023120`
- `0x180024e70`
- `0x18003e1e0`
- `0x180051d08`
- `0x180057e70`
- `0x18006ee24`
- `0x18006eed0`
- `0x180074758`
- `0x18007fc30`
- `0x1800ce820`
- `0x1800ce890`
- `0x1800cf3f0`
- `0x1800cf950`
- `0x1800d0530`
- `0x1800d0a70`
- `0x1800dfdc0`
- `0x18014733c`
- `0x18014c980`
- `0x18017f1b4`
- `0x1801838bc`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800cf148`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800cf148`
- `GDI32!DeleteDC` at `0x1800cf04c`
- `GDI32!DeleteDC` at `0x1800cf169`
- `GDI32!DeleteDC` at `0x1800cf04c`
- `GDI32!DeleteDC` at `0x1800cf169`
- `GDI32!SelectObject` at `0x1800cf043`
- `GDI32!SelectObject` at `0x1800cf160`
- `GDI32!SelectObject` at `0x1800cf043`
- `GDI32!SelectObject` at `0x1800cf160`
- `GDI32!GetObjectType` at `0x1800ceae7`
- `GDI32!GetObjectType` at `0x1800ceae7`
- `GDI32!DeleteObject` at `0x1800cf056`
- `GDI32!DeleteObject` at `0x1800cf056`
- `MSIMG32!AlphaBlend` at `0x1800cf023`
- `MSIMG32!AlphaBlend` at `0x1800cf023`

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
        sub_18017F1B4(v65, v51, &hdc);
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
0x1800ce890  mov     [rsp+arg_18], r9
0x1800ce895  push    rbx
0x1800ce896  push    rsi
0x1800ce897  push    rdi
0x1800ce898  push    r12
0x1800ce89a  push    r13
0x1800ce89c  push    r14
0x1800ce89e  push    r15
0x1800ce8a0  sub     rsp, 160h
0x1800ce8a7  mov     rsi, r9
0x1800ce8aa  mov     r13, r8
0x1800ce8ad  mov     r14, rdx
0x1800ce8b0  mov     r12, rcx
0x1800ce8b3  call    ?GetViewScaleForShape@ViewScale@Gfx@@SAAEBV12@AEBUIShapeBuilder@2@@Z; Gfx::ViewScale::GetViewScaleForShape(Gfx::IShapeBuilder const &)
0x1800ce8b8  mov     rbx, rax
0x1800ce8bb  mov     r8, [r12]
0x1800ce8bf  mov     rax, [r8+110h]
0x1800ce8c6  mov     edi, 1
0x1800ce8cb  mov     byte ptr [rsp+198h+hDest], dil
0x1800ce8d0  xor     r9d, r9d
0x1800ce8d3  xor     r8d, r8d
0x1800ce8d6  lea     rdx, [rsp+198h+var_68]
0x1800ce8de  mov     rcx, r12
0x1800ce8e1  call    cs:__guard_dispatch_icall_fptr
0x1800ce8e7  movups  xmm0, xmmword ptr [rax]
0x1800ce8ea  movups  [rsp+198h+var_E0], xmm0
0x1800ce8f2  movups  xmm1, xmmword ptr [rax+10h]
0x1800ce8f6  movups  [rsp+198h+var_D0], xmm1
0x1800ce8fe  movss   xmm3, dword ptr [rbx+2Ch]
0x1800ce903  cvtps2pd xmm3, xmm3
0x1800ce906  movss   xmm1, dword ptr [rbx+10h]
0x1800ce90b  cvtps2pd xmm1, xmm1
0x1800ce90e  movaps  xmm2, xmm1
0x1800ce911  mulsd   xmm2, qword ptr [rbx+20h]
0x1800ce916  movups  xmm4, xmmword ptr [rsi+20h]
0x1800ce91a  mulsd   xmm1, qword ptr [rbx+18h]
0x1800ce91f  movss   xmm0, dword ptr [rbx+28h]
0x1800ce924  cvtps2pd xmm0, xmm0
0x1800ce927  mulsd   xmm1, xmm0
0x1800ce92b  unpcklpd xmm1, xmm1
0x1800ce92f  movups  xmm0, xmmword ptr [rsi]
0x1800ce932  mulpd   xmm1, xmm0
0x1800ce936  movups  xmmword ptr [rsp+198h+hdc], xmm1
0x1800ce93b  mulsd   xmm2, xmm3
0x1800ce93f  movaps  xmm1, xmm2
0x1800ce942  unpcklpd xmm1, xmm1
0x1800ce946  movups  xmm0, xmmword ptr [rsi+10h]
0x1800ce94a  mulpd   xmm1, xmm0
0x1800ce94e  movups  [rsp+198h+var_128], xmm1
0x1800ce953  movups  [rsp+198h+var_118], xmm4
0x1800ce95b  lea     r8, [rsp+198h+hdc]
0x1800ce960  lea     rdx, [rsp+198h+var_E0]
0x1800ce968  lea     rcx, [rsp+198h+var_68]
0x1800ce970  call    ??$GetTransformedBounds@V?$TUnits@NUDevicePixels@Math@@@Math@@NV12@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU10@AEBU?$TAffine3x3@N@0@@Z; Math::GetTransformedBounds<Math::TUnits<double,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TAffine3x3<double> const &)
0x1800ce975  movups  xmm0, xmmword ptr [rax]
0x1800ce978  movups  [rsp+198h+var_E0], xmm0
0x1800ce980  movups  xmm1, xmmword ptr [rax+10h]
0x1800ce984  movups  [rsp+198h+var_D0], xmm1
0x1800ce98c  lea     rdx, [rsp+198h+var_E0]
0x1800ce994  lea     rcx, [rsp+198h+hdc]
0x1800ce999  call    ??$snap_outward_cast@V?$TUnits@HUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &)
0x1800ce99e  mov     r11d, dword ptr [rsp+198h+hdc]
0x1800ce9a3  mov     ebx, dword ptr [rsp+198h+hdc+8]
0x1800ce9a7  mov     edx, dword ptr [rsp+198h+hdc+4]
0x1800ce9ab  mov     r8d, dword ptr [rsp+198h+hdc+0Ch]
0x1800ce9b0  cmp     r11d, ebx
0x1800ce9b3  jge     short loc_1800CE9DA
0x1800ce9b5  cmp     edx, r8d
0x1800ce9b8  jge     short loc_1800CE9DA
0x1800ce9ba  sub     r11d, 2
0x1800ce9be  mov     dword ptr [rsp+198h+hdc], r11d
0x1800ce9c3  sub     edx, 2
0x1800ce9c6  mov     dword ptr [rsp+198h+hdc+4], edx
0x1800ce9ca  add     ebx, 2
0x1800ce9cd  mov     dword ptr [rsp+198h+hdc+8], ebx
0x1800ce9d1  add     r8d, 2
0x1800ce9d5  mov     dword ptr [rsp+198h+hdc+0Ch], r8d
0x1800ce9da  lea     r9, [rsp+198h+hdc]
0x1800ce9df  test    r13, r13
0x1800ce9e2  cmovnz  r9, r13
0x1800ce9e6  movups  xmm0, xmmword ptr [r9]
0x1800ce9ea  movups  [rsp+198h+var_E0], xmm0
0x1800ce9f2  movq    rax, xmm0
0x1800ce9f7  mov     rcx, [r9+8]
0x1800ce9fb  cmp     eax, ecx
0x1800ce9fd  jge     loc_1800CED57
0x1800cea03  shr     rcx, 20h
0x1800cea07  shr     rax, 20h
0x1800cea0b  cmp     eax, ecx
0x1800cea0d  jge     loc_1800CED57
0x1800cea13  movups  xmm1, xmm0
0x1800cea16  movaps  xmmword ptr [rsp+198h+hdc], xmm0
0x1800cea1b  cmp     r11d, ebx
0x1800cea1e  jg      loc_1800CED7B
0x1800cea24  cmp     edx, r8d
0x1800cea27  jg      loc_1800CED7B
0x1800cea2d  mov     r9d, dword ptr [rsp+198h+hdc+0Ch]
0x1800cea32  mov     eax, dword ptr [rsp+198h+hdc+8]
0x1800cea36  mov     r10d, dword ptr [rsp+198h+hdc+4]
0x1800cea3b  mov     ecx, dword ptr [rsp+198h+hdc]
0x1800cea3f  cmp     ecx, eax
0x1800cea41  jg      short loc_1800CEA79
0x1800cea43  cmp     r10d, r9d
0x1800cea46  jg      short loc_1800CEA79
0x1800cea48  cmp     r11d, ecx
0x1800cea4b  cmovg   ecx, r11d
0x1800cea4f  mov     dword ptr [rsp+198h+hdc], ecx
0x1800cea53  cmp     ebx, eax
0x1800cea55  cmovl   eax, ebx
0x1800cea58  mov     dword ptr [rsp+198h+hdc+8], eax
0x1800cea5c  cmp     edx, r10d
0x1800cea5f  cmovg   r10d, edx
0x1800cea63  mov     dword ptr [rsp+198h+hdc+4], r10d
0x1800cea68  cmp     r8d, r9d
0x1800cea6b  cmovl   r9d, r8d
0x1800cea6f  mov     dword ptr [rsp+198h+hdc+0Ch], r9d
0x1800cea74  movaps  xmm1, xmmword ptr [rsp+198h+hdc]
0x1800cea79  movdqa  xmmword ptr [rsp+198h+yoriginDest], xmm1
0x1800cea82  cmp     ecx, eax
0x1800cea84  jge     loc_1800CED5F
0x1800cea8a  movdqa  xmm0, xmm1
0x1800cea8e  psrldq  xmm0, 8
0x1800cea93  movq    rcx, xmm0
0x1800cea98  shr     rcx, 20h
0x1800cea9c  movq    rax, xmm1
0x1800ceaa1  shr     rax, 20h
0x1800ceaa5  cmp     eax, ecx
0x1800ceaa7  jge     loc_1800CED5F
0x1800ceaad  mov     rdx, rsi
0x1800ceab0  lea     rcx, [rsp+198h+hdc]
0x1800ceab5  call    ??$Inverse@N@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@@Z; Math::Inverse<double>(Math::TAffine3x3<double> const &)
0x1800ceaba  mov     r8, rax
0x1800ceabd  lea     rdx, [rsp+198h+var_E0]
0x1800ceac5  lea     rcx, [rsp+198h+var_68]
0x1800ceacd  call    ??$GetTransformedBounds@V?$TUnits@HUDevicePixels@Math@@@Math@@NV?$TUnits@NUDevicePixels@Math@@@2@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TAffine3x3@N@0@@Z; Math::GetTransformedBounds<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,Math::TAffine3x3<double> const &)
0x1800cead2  lea     rdx, [rsp+198h+var_68]
0x1800ceada  lea     rcx, [rsp+198h+hdc]
0x1800ceadf  call    ??$snap_outward_cast@V?$TUnits@HUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &)
0x1800ceae4  mov     rcx, r14; h
0x1800ceae7  call    cs:__imp_GetObjectType
0x1800ceaed  lea     ecx, [rax-3]
0x1800ceaf0  test    ecx, 0FFFFFFF6h
0x1800ceaf6  jnz     short loc_1800CEB02
0x1800ceaf8  cmp     eax, 0Bh
0x1800ceafb  jz      short loc_1800CEB02
0x1800ceafd  mov     bl, dil
0x1800ceb00  jmp     short loc_1800CEB04
0x1800ceb02  xor     bl, bl
0x1800ceb04  mov     [rsp+198h+arg_10], 0
0x1800ceb10  mov     [rsp+198h+var_B8], 0
0x1800ceb1b  movups  xmm0, xmmword ptr [rsp+198h+hdc]
0x1800ceb20  movdqu  [rsp+198h+var_B4], xmm0
0x1800ceb29  mov     [rsp+198h+var_A0], 0
0x1800ceb35  xorps   xmm1, xmm1
0x1800ceb38  movdqa  [rsp+198h+var_98], xmm1
0x1800ceb41  mov     [rsp+198h+var_88], 3
0x1800ceb4c  xorps   xmm0, xmm0
0x1800ceb4f  movups  [rsp+198h+var_80], xmm0
0x1800ceb57  mov     [rsp+198h+var_70], edi
0x1800ceb5e  mov     [rsp+198h+var_6B], dil
0x1800ceb66  mov     r15b, byte ptr [rsp+198h+arg_20]
0x1800ceb6e  mov     [rsp+198h+var_6C], r15b
0x1800ceb76  mov     rax, [r12]
0x1800ceb7a  lea     r8, [rsp+198h+var_B8]
0x1800ceb82  lea     rdx, [rsp+198h+arg_10]
0x1800ceb8a  mov     rcx, r12
0x1800ceb8d  mov     rax, [rax+1A8h]
0x1800ceb94  call    cs:__guard_dispatch_icall_fptr
0x1800ceb9a  mov     rcx, [rsp+198h+arg_10]
0x1800ceba2  cmp     eax, edi
0x1800ceba4  jnz     short loc_1800CEBCE
0x1800ceba6  test    rcx, rcx
0x1800ceba9  jz      short loc_1800CEBB8
0x1800cebab  mov     rax, [rcx]
0x1800cebae  mov     rax, [rax+8]
0x1800cebb2  call    cs:__guard_dispatch_icall_fptr
0x1800cebb8  mov     al, dil
0x1800cebbb  add     rsp, 160h
0x1800cebc2  pop     r15
0x1800cebc4  pop     r14
0x1800cebc6  pop     r13
0x1800cebc8  pop     r12
0x1800cebca  pop     rdi
0x1800cebcb  pop     rsi
0x1800cebcc  pop     rbx
0x1800cebcd  retn
0x1800cebce  test    rcx, rcx
0x1800cebd1  jz      short loc_1800CEBA6
0x1800cebd3  test    eax, eax
0x1800cebd5  jnz     loc_1800CF0F7
0x1800cebdb  test    bl, bl
0x1800cebdd  jnz     loc_1800CF10B
0x1800cebe3  xor     bl, bl
0x1800cebe5  mov     r11, qword ptr [rsp+198h+yoriginDest]
0x1800cebed  mov     r9, qword ptr [rsp+198h+yoriginDest+8]
0x1800cebf5  mov     r10d, [rsp+198h+yoriginDest+4]
0x1800cebfd  mov     edx, [rsp+198h+yoriginDest+0Ch]
0x1800cec04  cmp     r11d, r9d
0x1800cec07  jg      loc_1800CF0C6
0x1800cec0d  cmp     r10d, edx
0x1800cec10  jg      loc_1800CF0C6
0x1800cec16  mov     eax, edx
0x1800cec18  sub     eax, r10d
0x1800cec1b  mov     r8d, r9d
0x1800cec1e  sub     r8d, r11d
0x1800cec21  mov     dword ptr [rsp+198h+arg_0], r8d
0x1800cec29  mov     dword ptr [rsp+198h+arg_0+4], eax
0x1800cec30  mov     rdi, [rsp+198h+arg_0]
0x1800cec38  mov     [rsp+198h+arg_0], rdi
0x1800cec40  mov     eax, 800h
0x1800cec45  mov     esi, dword ptr [rsp+198h+arg_0+4]
0x1800cec4c  cmp     edi, eax
0x1800cec4e  jbe     loc_1800CED6C
0x1800cec54  mov     al, 1
0x1800cec56  test    bl, bl
0x1800cec58  jnz     loc_1800CEDA0
0x1800cec5e  test    rcx, rcx
0x1800cec61  jz      short loc_1800CEC70
0x1800cec63  mov     rax, [rcx]
0x1800cec66  mov     rax, [rax+8]
0x1800cec6a  call    cs:__guard_dispatch_icall_fptr
0x1800cec70  mov     rsi, [rsp+198h+arg_18]
0x1800cec78  movdqa  xmm0, cs:__xmm@00000000000000000000000100000001
0x1800cec80  movdqu  xmmword ptr [rsp+198h+hdc], xmm0
0x1800cec86  mov     [rsp+198h+arg_0], r14
0x1800cec8e  lea     r8, [rsp+198h+hdc]
0x1800cec93  lea     rdx, [rsp+198h+arg_0]
0x1800cec9b  lea     rcx, [rsp+198h+arg_18]
0x1800ceca3  call    ??$Make@VDC@GEL@@V12@AEAPEAUHDC__@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Mso@@YA?AV?$TCntPtr@VDC@GEL@@@0@AEAPEAUHDC__@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z; Mso::Make<GEL::DC,GEL::DC,HDC__ * &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &>(HDC__ * &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1800ceca8  mov     rbx, [rax]
0x1800cecab  mov     qword ptr [rax], 0
0x1800cecb2  mov     rcx, [rsp+198h+arg_18]
0x1800cecba  test    rcx, rcx
0x1800cecbd  jnz     loc_1800CF1D9
0x1800cecc3  mov     [rsp+198h+arg_0], rbx
0x1800ceccb  mov     rdx, rbx
0x1800cecce  lea     rcx, [rsp+198h+arg_18]
0x1800cecd6  call    ?Create@IScene@GEL@@SA?AV?$TCntPtr@UIScene@GEL@@@Mso@@AEAUIDevice@2@@Z; GEL::IScene::Create(GEL::IDevice &)
0x1800cecdb  mov     rdi, [rax]
0x1800cecde  xor     r14d, r14d
0x1800cece1  mov     [rax], r14
0x1800cece4  mov     rcx, [rsp+198h+arg_18]
0x1800cecec  test    rcx, rcx
0x1800cecef  jz      short loc_1800CED06
0x1800cecf1  mov     [rsp+198h+arg_18], r14
0x1800cecf9  mov     rax, [rcx]
0x1800cecfc  mov     rax, [rax+8]
0x1800ced00  call    cs:__guard_dispatch_icall_fptr
0x1800ced06  mov     [rsp+198h+hdcSrc], r14
0x1800ced0b  mov     byte ptr [rsp+198h+hDest], r15b
0x1800ced10  mov     r9, rsi
0x1800ced13  mov     r8, r13
0x1800ced16  mov     rdx, rdi
0x1800ced19  mov     rcx, r12
0x1800ced1c  call    ?DrawShapeBuilderToGELScene@Gfx@@YA_NAEBUIShapeBuilder@1@AEAUIScene@GEL@@PEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@AEBU?$TAffine3x3@N@6@_NPEBURenderOptions@1@@Z; Gfx::DrawShapeBuilderToGELScene(Gfx::IShapeBuilder const &,GEL::IScene &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const *,Math::TAffine3x3<double> const &,bool,Gfx::RenderOptions const *)
0x1800ced21  mov     sil, al
0x1800ced24  test    rdi, rdi
0x1800ced27  jz      short loc_1800CED3A
0x1800ced29  mov     rdx, [rdi]
0x1800ced2c  mov     rcx, rdi
0x1800ced2f  mov     rax, [rdx+8]
0x1800ced33  call    cs:__guard_dispatch_icall_fptr
0x1800ced39  nop
0x1800ced3a  test    rbx, rbx
0x1800ced3d  jz      short loc_1800CED4F
0x1800ced3f  mov     rax, [rbx]
0x1800ced42  mov     rcx, rbx
0x1800ced45  mov     rax, [rax+8]
0x1800ced49  call    cs:__guard_dispatch_icall_fptr
0x1800ced4f  mov     al, sil
0x1800ced52  jmp     loc_1800CEBBB
0x1800ced57  mov     al, dil
0x1800ced5a  jmp     loc_1800CEBBB
0x1800ced5f  mov     r15b, byte ptr [rsp+198h+arg_20]
0x1800ced67  jmp     loc_1800CEC78
0x1800ced6c  cmp     esi, eax
0x1800ced6e  ja      loc_1800CEC54
0x1800ced74  xor     al, al
0x1800ced76  jmp     loc_1800CEC56
0x1800ced7b  mov     r10d, edi
0x1800ced7e  mov     dword ptr [rsp+198h+hdc+4], edi
0x1800ced82  mov     ecx, edi
0x1800ced84  mov     dword ptr [rsp+198h+hdc], ecx
0x1800ced88  xor     r9d, r9d
0x1800ced8b  mov     dword ptr [rsp+198h+hdc+0Ch], r9d
0x1800ced90  xor     eax, eax
0x1800ced92  mov     dword ptr [rsp+198h+hdc+8], eax
0x1800ced96  movaps  xmm1, xmmword ptr [rsp+198h+hdc]
0x1800ced9b  jmp     loc_1800CEA3F
0x1800ceda0  test    al, al
0x1800ceda2  jnz     loc_1800CEC5E
0x1800ceda8  movss   xmm1, cs:__real@42c00000
0x1800cedb0  mov     dword ptr [rsp+198h+var_E0], 42C00000h
0x1800cedbb  cmp     r11d, r9d
0x1800cedbe  jg      loc_1800CF0D7
0x1800cedc4  cmp     r10d, edx
0x1800cedc7  jg      loc_1800CF0D7
0x1800cedcd  sub     edx, r10d; unsigned int
0x1800cedd0  sub     r9d, r11d
0x1800cedd3  mov     dword ptr [rsp+198h+arg_0], r9d
  ... truncated ...
```
