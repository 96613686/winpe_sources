# Windows::UI::Input::Inking::InkPresenterStencilBase::_OnManipulationUpdated(Windows::UI::Input::IGestureRecognizer *,Windows::UI::Input::IManipulationUpdatedEventArgs *)

- ea: `0x1800c1a20`
- end: `0x1800c223a`
- name: `?_OnManipulationUpdated@InkPresenterStencilBase@Inking@Input@UI@Windows@@MEAAJPEAUIGestureRecognizer@345@PEAUIManipulationUpdatedEventArgs@345@@Z`
- size: `2074`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::InkPresenterStencilBase *__hidden this, struct IGestureRecognizer *, struct Windows::UI::Input::IManipulationUpdatedEventArgs *)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001b9c`
- `0x180002c28`
- `0x180004a48`
- `0x180004c14`
- `0x180004d1c`
- `0x1800062a0`
- `0x180006e10`
- `0x180049f2c`
- `0x180062ea4`
- `0x180062f68`
- `0x1800b43d8`
- `0x1800bf3c4`
- `0x1800bf430`
- `0x1800c03cc`
- `0x1800c0458`
- `0x1800c1a20`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c21ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c21ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c1a7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c1a7b`
- `d2d1!__imp_D2D1MakeRotateMatrix` at `0x1800c2054`
- `d2d1!__imp_D2D1MakeRotateMatrix` at `0x1800c20e2`
- `d2d1!__imp_D2D1MakeRotateMatrix` at `0x1800c2054`
- `d2d1!__imp_D2D1MakeRotateMatrix` at `0x1800c20e2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c1cd3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c1cd3`

## string_xrefs

- `0x1800c21b5`: `InkPresenterStencilBase::_OnManipulationUpdated[Exit]`
- `0x1800c1b98`: `InkPresenterStencilBase::_OnManipulationUpdated`
- `0x1800c1f28`: `InkPresenterStencilBase::_OnManipulationUpdated`
- `0x1800c1cbe`: `Cannot decompose m_manipulationTransform`
- `0x1800c1ad6`: `InkPresenterStencilBase::_OnManipulationUpdated[Enter]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Input::Inking::InkPresenterStencilBase::_OnManipulationUpdated(
        Windows::UI::Input::Inking::InkPresenterStencilBase *this,
        struct IGestureRecognizer *a2,
        struct Windows::UI::Input::IManipulationUpdatedEventArgs *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  __int64 v6; // r8
  FLOAT v7; // r14d
  int v8; // esi
  int v9; // ecx
  int v10; // r9d
  int v11; // ecx
  double v12; // r8
  int v13; // r9d
  __m128i *v14; // r14
  __int64 v15; // rdx
  double v16; // xmm0_8
  float v17; // xmm7_4
  _QWORD *v18; // rax
  __m128i v19; // xmm10
  __int64 v20; // xmm11_8
  char v21; // al
  float v22; // xmm4_4
  __int64 v23; // rdx
  float v24; // xmm1_4
  float v25; // xmm8_4
  float v26; // xmm0_4
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  double v32; // xmm0_8
  int v33; // esi
  double DegreesStart; // xmm0_8
  float v35; // xmm4_4
  __m128 v36; // xmm2
  __m128 v37; // xmm1
  __int16 *v38; // rdx
  FLOAT v40; // [rsp+78h] [rbp-90h] BYREF
  FLOAT v41; // [rsp+7Ch] [rbp-8Ch] BYREF
  FLOAT v42; // [rsp+80h] [rbp-88h] BYREF
  double v43; // [rsp+88h] [rbp-80h] BYREF
  D2D1_POINT_2F v44; // [rsp+90h] [rbp-78h] BYREF
  int v45; // [rsp+98h] [rbp-70h] BYREF
  FLOAT y; // [rsp+9Ch] [rbp-6Ch] BYREF
  float x; // [rsp+A0h] [rbp-68h] BYREF
  double v48[2]; // [rsp+A8h] [rbp-60h] BYREF
  FLOAT angle[4]; // [rsp+B8h] [rbp-50h] BYREF
  int v50; // [rsp+C8h] [rbp-40h]
  __m128i si128; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v52; // [rsp+E0h] [rbp-28h]
  __int128 v53; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v54; // [rsp+F8h] [rbp-10h]
  __m128i v55; // [rsp+100h] [rbp-8h] BYREF
  __int64 v56; // [rsp+110h] [rbp+8h]
  D2D1_MATRIX_3X2_F matrix; // [rsp+118h] [rbp+10h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  *(_QWORD *)&v48[1] = v5;
  LODWORD(v7) = *((unsigned __int8 *)this + 171);
  v8 = 0;
  if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 4104, v6) )
  {
    v42 = *((float *)this + 79);
    LODWORD(v41) = *((unsigned __int8 *)this + 320);
    v40 = v7;
    v45 = *((unsigned __int8 *)this + 266);
    v44 = (D2D1_POINT_2F)L"InkPresenterStencilBase::_OnManipulationUpdated[Enter]";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v9,
      (unsigned int)byte_18013F0F1,
      v6,
      v10,
      (__int64)&v44,
      (__int64)&v45,
      (__int64)&v40,
      (__int64)&v41,
      (__int64)&v42);
  }
  if ( !*((_BYTE *)this + 266) )
  {
    v53 = *(_OWORD *)((char *)this + 172);
    v54 = *(_QWORD *)((char *)this + 188);
    *(_OWORD *)angle = 0;
    v50 = 0;
    v44 = 0;
    (*(void (__fastcall **)(struct Windows::UI::Input::IManipulationUpdatedEventArgs *, FLOAT *))(*(_QWORD *)a3 + 64LL))(
      a3,
      angle);
    v43 = 0.0;
    (*(void (__fastcall **)(struct Windows::UI::Input::IManipulationUpdatedEventArgs *, double *))(*(_QWORD *)a3 + 56LL))(
      a3,
      &v43);
    v44 = *(D2D1_POINT_2F *)&v43;
    if ( (unsigned int)dword_18015B128 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 4104, L"InkPresenterStencilBase::_OnManipulationUpdated") )
    {
      v45 = v50;
      v42 = angle[3];
      v41 = angle[2];
      v40 = angle[1];
      *(FLOAT *)v48 = angle[0];
      y = v44.y;
      x = v44.x;
      v43 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)word_18013F1B2,
        LODWORD(v12),
        v13,
        (__int64)&v43,
        (__int64)&x,
        (__int64)&y,
        (__int64)v48,
        (__int64)&v40,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v45);
    }
    if ( LOBYTE(v7) )
    {
      v8 = (*(__int64 (__fastcall **)(Windows::UI::Input::Inking::InkPresenterStencilBase *, __int128 *, FLOAT *, D2D1_POINT_2F *))(*(_QWORD *)this + 328LL))(
             this,
             &v53,
             angle,
             &v44);
      if ( v8 < 0
        || ((v40 = 0.0,
             v14 = (__m128i *)((char *)this + 268),
             !Matrix3x2Helper::Decompose(
                (Windows::UI::Input::Inking::InkPresenterStencilBase *)((char *)this + 268),
                &v40,
                (float *)&v43,
                (struct Windows::Foundation::Point *)&si128))
          ? (v8 = -2147418113,
             v18 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                               (HSTRING *)&matrix,
                               L"Cannot decompose m_manipulationTransform"),
             RoOriginateError(2147549183LL, *v18),
             v17 = v40)
          : (v16 = ((double (*)(void))InkPresenterRulerGeometryHelper::_MakeDegreesStartFrom<float>)(),
             v17 = *(float *)&v16),
            v8 < 0) )
      {
LABEL_40:
        if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 4104, v6) )
        {
          v38 = &word_18013EFBE;
LABEL_46:
          si128.m128i_i64[0] = (__int64)L"InkPresenterStencilBase::_OnManipulationUpdated[Exit]";
          LODWORD(v43) = v8;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18015B128,
            (_DWORD)v38,
            0,
            0,
            (__int64)&si128,
            (__int64)&v43);
          goto LABEL_47;
        }
        goto LABEL_47;
      }
      v19 = *v14;
      v55 = *v14;
      v20 = *(_QWORD *)((char *)this + 284);
      v56 = v20;
      v43 = *(double *)&this;
      LOBYTE(v15) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RulerAngleSnap>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_RulerAngleSnap>::GetImpl'::`2'::impl,
        v15);
      v21 = lambda_c9b099c44735688f64a874efad8688a9_::operator()(&v43);
      *((_BYTE *)this + 264) = v21;
      if ( v21 )
      {
        v22 = *((float *)this + 64);
      }
      else
      {
        v24 = (float)(int)floor((float)(v17 / 45.0) + 0.5) * 45.0;
        *((float *)this + 64) = v24;
        v25 = FLOAT_5_0;
        if ( v17 == v24 )
        {
          v26 = 0.0;
        }
        else if ( v24 <= v17 )
        {
          v26 = FLOAT_N5_0;
        }
        else
        {
          v26 = FLOAT_5_0;
        }
        *((float *)this + 65) = v26;
        if ( *((_DWORD *)this + 79) < 3u )
        {
          si128 = 0;
          (*(void (__fastcall **)(struct Windows::UI::Input::IManipulationUpdatedEventArgs *, __m128i *))(*(_QWORD *)a3 + 80LL))(
            a3,
            &si128);
          if ( COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(float *)&si128.m128i_i32[2]) & _xmm) >= 0.02500000037252903 )
          {
            v25 = FLOAT_1_0;
          }
          else
          {
            LOBYTE(v23) = 1;
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_RulerSubPixel>::ReportUsage(
              `wil::Feature<__WilFeatureTraits_Feature_RulerSubPixel>::GetImpl'::`2'::impl,
              v23);
            v25 = FLOAT_0_1;
          }
        }
        v41 = v25;
        v42 = 0.0;
        v48[0] = 0.0;
        lambda_f53b86f9f8fc552dc8d8413cc679f7f2_::operator()(&v41, v23, &v42, v48);
        v40 = 0.0;
        v43 = 0.0;
        lambda_f53b86f9f8fc552dc8d8413cc679f7f2_::operator()(&v41, v27, &v40, &v43);
        v31 = LODWORD(v42);
        v32 = v43;
        v33 = LODWORD(v40);
        if ( v43 < 0.8999999761581421 )
        {
          if ( v43 > 0.1000000238418579 )
          {
            v30 = (unsigned int)(LODWORD(v40) - LODWORD(v42));
            v29 = (unsigned int)((unsigned __int64)(3054198967LL * (int)v30) >> 32) >> 31;
            v28 = (unsigned int)(360 * ((int)v30 / 360));
            if ( (_DWORD)v30 == (_DWORD)v28
              || (v29 = (unsigned int)(v30 + 1), v28 = (unsigned int)((int)v29 / 360), (_DWORD)v29 == 360 * (_DWORD)v28) )
            {
              v33 = LODWORD(v42);
            }
          }
        }
        else
        {
          v33 = LODWORD(v40) + 1;
        }
        if ( (unsigned int)dword_18015B128 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 4104, v30) )
        {
          x = v32;
          y = *(float *)&v33;
          *(float *)v48 = v48[0];
          v45 = v31;
          v42 = 0.89999998;
          v41 = v25;
          v40 = v17;
          LODWORD(v43) = *((_DWORD *)this + 60);
          si128.m128i_i64[0] = (__int64)L"InkPresenterStencilBase::_OnManipulationUpdated";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v29,
            (unsigned int)&byte_18013EDF7,
            v30,
            v31,
            (__int64)&si128,
            (__int64)&v43,
            (__int64)&v40,
            (__int64)&v41,
            (__int64)&v42,
            (__int64)&v45,
            (__int64)v48,
            (__int64)&y,
            (__int64)&x);
        }
        DegreesStart = InkPresenterRulerGeometryHelper::_MakeDegreesStartFrom<float>(v29, v28, v30, v31);
        v22 = *(float *)&DegreesStart;
      }
      v35 = v22 - v17;
      if ( COERCE_DOUBLE(COERCE_UNSIGNED_INT64(v35) & _xmm) >= 0.05000000074505806 )
      {
        v36 = (__m128)HIDWORD(v53);
        v36.m128_f32[0] = (float)((float)(*((float *)&v53 + 3) * v44.y) + (float)(*((float *)&v53 + 1) * v44.x))
                        + *((float *)&v54 + 1);
        v37 = v36;
        v37.m128_f32[0] = (float)((float)(v36.m128_f32[0] * *((float *)this + 75))
                                + (float)((float)((float)((float)(*((float *)&v53 + 2) * v44.y)
                                                        + (float)(*(float *)&v53 * v44.x))
                                                + *(float *)&v54)
                                        * *((float *)this + 73)))
                        + *((float *)this + 77);
        v36.m128_f32[0] = (float)((float)(v36.m128_f32[0] * *((float *)this + 76))
                                + (float)((float)((float)((float)(*((float *)&v53 + 2) * v44.y)
                                                        + (float)(*(float *)&v53 * v44.x))
                                                + *(float *)&v54)
                                        * *((float *)this + 74)))
                        + *((float *)this + 78);
        D2D1MakeRotateMatrix(v35, (D2D1_POINT_2F)*(_OWORD *)&_mm_unpacklo_ps(v37, v36), &matrix);
        D2D1::Matrix3x2F::SetProduct(
          (D2D1::Matrix3x2F *)&si128,
          (const struct D2D1::Matrix3x2F *)&matrix,
          (const struct D2D1::Matrix3x2F *)&v55);
        v19 = si128;
        v20 = v52;
      }
      *(__m128i *)((char *)this + 196) = v19;
      *(_QWORD *)((char *)this + 212) = v20;
    }
    else
    {
      *(FLOAT *)si128.m128i_i32 = angle[2];
      *(__int64 *)((char *)si128.m128i_i64 + 4) = 0;
      *(FLOAT *)&si128.m128i_i32[3] = angle[2];
      *(float *)&v52 = v44.x - (float)(angle[2] * v44.x);
      *((float *)&v52 + 1) = v44.y - (float)(angle[2] * v44.y);
      v44 = (D2D1_POINT_2F)_mm_unpacklo_ps((__m128)LODWORD(v44.x), (__m128)LODWORD(v44.y)).m128_u64[0];
      D2D1MakeRotateMatrix(angle[3], v44, &matrix);
      D2D1::Matrix3x2F::SetProduct(
        (D2D1::Matrix3x2F *)&v55,
        (const struct D2D1::Matrix3x2F *)&si128,
        (const struct D2D1::Matrix3x2F *)&matrix);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v52 = *(_QWORD *)angle;
      D2D1::Matrix3x2F::SetProduct(
        (D2D1::Matrix3x2F *)&matrix,
        (const struct D2D1::Matrix3x2F *)&v55,
        (const struct D2D1::Matrix3x2F *)&si128);
      D2D1::Matrix3x2F::SetProduct(
        (D2D1::Matrix3x2F *)&v55,
        (const struct D2D1::Matrix3x2F *)&matrix,
        (const struct D2D1::Matrix3x2F *)&v53);
      *(__m128i *)((char *)this + 196) = v55;
      *(_QWORD *)((char *)this + 212) = v56;
    }
    v8 = (*(__int64 (__fastcall **)(Windows::UI::Input::Inking::InkPresenterStencilBase *, _QWORD))(*(_QWORD *)this
                                                                                                  + 160LL))(
           this,
           0);
    if ( v8 < 0 )
      goto LABEL_40;
  }
  if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 4104, v6) )
  {
    v38 = word_18013ED92;
    goto LABEL_46;
  }
LABEL_47:
  if ( v5 )
    LeaveCriticalSection(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c1a20  mov     rax, rsp
0x1800c1a23  mov     [rax+10h], rbx
0x1800c1a27  mov     [rax+20h], rsi
0x1800c1a2b  push    rbp
0x1800c1a2c  push    rdi
0x1800c1a2d  push    r13
0x1800c1a2f  push    r14
0x1800c1a31  push    r15
0x1800c1a33  lea     rbp, [rax-0C8h]
0x1800c1a3a  sub     rsp, 1A0h
0x1800c1a41  movaps  xmmword ptr [rax-38h], xmm6
0x1800c1a45  movaps  xmmword ptr [rax-48h], xmm7
0x1800c1a49  movaps  xmmword ptr [rax-58h], xmm8
0x1800c1a4e  movaps  xmmword ptr [rax-68h], xmm9
0x1800c1a53  movaps  xmmword ptr [rax-78h], xmm10
0x1800c1a58  movaps  xmmword ptr [rax-88h], xmm11
0x1800c1a60  mov     rax, cs:__security_cookie
0x1800c1a67  xor     rax, rsp
0x1800c1a6a  mov     [rbp+0C0h+var_90], rax
0x1800c1a6e  mov     r15, r8
0x1800c1a71  mov     rdi, rcx
0x1800c1a74  lea     rbx, [rcx+68h]
0x1800c1a78  mov     rcx, rbx; lpCriticalSection
0x1800c1a7b  call    cs:__imp_EnterCriticalSection
0x1800c1a81  mov     [rbp+0C0h+var_118], rbx
0x1800c1a85  movzx   r14d, byte ptr [rdi+0ABh]
0x1800c1a8d  xor     esi, esi
0x1800c1a8f  mov     eax, cs:dword_18015B128
0x1800c1a95  lea     r13, dword_18015B128
0x1800c1a9c  cmp     eax, 4
0x1800c1a9f  jbe     short loc_1800C1B1D
0x1800c1aa1  mov     edx, 1008h
0x1800c1aa6  mov     rcx, r13
0x1800c1aa9  call    _tlgKeywordOn
0x1800c1aae  test    al, al
0x1800c1ab0  jz      short loc_1800C1B1D
0x1800c1ab2  mov     eax, [rdi+13Ch]
0x1800c1ab8  mov     [rsp+1C0h+var_148], eax
0x1800c1abc  movzx   eax, byte ptr [rdi+140h]
0x1800c1ac3  mov     [rsp+1C0h+var_14C], eax
0x1800c1ac7  mov     [rsp+1C0h+var_150], r14d
0x1800c1acc  movzx   eax, byte ptr [rdi+10Ah]
0x1800c1ad3  mov     [rbp+0C0h+var_130], eax
0x1800c1ad6  lea     rax, aInkpresenterst_66; "InkPresenterStencilBase::_OnManipulatio"...
0x1800c1add  mov     [rbp+0C0h+var_138], rax
0x1800c1ae1  lea     rax, [rsp+1C0h+var_148]
0x1800c1ae6  mov     [rsp+1C0h+var_180], rax
0x1800c1aeb  lea     rax, [rsp+1C0h+var_14C]
0x1800c1af0  mov     [rsp+1C0h+var_188], rax
0x1800c1af5  lea     rax, [rsp+1C0h+var_150]
0x1800c1afa  mov     [rsp+1C0h+var_190], rax
0x1800c1aff  lea     rax, [rbp+0C0h+var_130]
0x1800c1b03  mov     [rsp+1C0h+var_198], rax
0x1800c1b08  lea     rax, [rbp+0C0h+var_138]
0x1800c1b0c  mov     [rsp+1C0h+var_1A0], rax
0x1800c1b11  lea     rdx, byte_18013F0F1
0x1800c1b18  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c1b1d  cmp     [rdi+10Ah], sil
0x1800c1b24  jnz     loc_1800C2192
0x1800c1b2a  movups  xmm0, xmmword ptr [rdi+0ACh]
0x1800c1b31  movups  [rbp+0C0h+var_E0], xmm0
0x1800c1b35  movsd   xmm1, qword ptr [rdi+0BCh]
0x1800c1b3d  movsd   [rbp+0C0h+var_D0], xmm1
0x1800c1b42  xorps   xmm0, xmm0
0x1800c1b45  xor     eax, eax
0x1800c1b47  movups  xmmword ptr [rbp+0C0h+angle], xmm0
0x1800c1b4b  mov     [rbp+0C0h+var_100], eax
0x1800c1b4e  mov     [rbp+0C0h+var_138], rax
0x1800c1b52  mov     rax, [r15]
0x1800c1b55  lea     rdx, [rbp+0C0h+angle]
0x1800c1b59  mov     rcx, r15
0x1800c1b5c  mov     rax, [rax+40h]
0x1800c1b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1b65  xor     eax, eax
0x1800c1b67  mov     qword ptr [rbp+0C0h+var_140], rax
0x1800c1b6b  mov     rax, [r15]
0x1800c1b6e  lea     rdx, [rbp+0C0h+var_140]
0x1800c1b72  mov     rcx, r15
0x1800c1b75  mov     rax, [rax+38h]
0x1800c1b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1b7e  movss   xmm0, [rbp+0C0h+var_140]
0x1800c1b83  movss   dword ptr [rbp+0C0h+var_138], xmm0
0x1800c1b88  movss   xmm1, [rbp+0C0h+var_140+4]
0x1800c1b8d  movss   dword ptr [rbp+0C0h+var_138+4], xmm1
0x1800c1b92  mov     eax, cs:dword_18015B128
0x1800c1b98  lea     r8, aInkpresenterst_20; "InkPresenterStencilBase::_OnManipulatio"...
0x1800c1b9f  cmp     eax, 5
0x1800c1ba2  jbe     loc_1800C1C45
0x1800c1ba8  mov     edx, 1008h
0x1800c1bad  mov     rcx, r13
0x1800c1bb0  call    _tlgKeywordOn
0x1800c1bb5  test    al, al
0x1800c1bb7  jz      loc_1800C1C45
0x1800c1bbd  mov     eax, [rbp+0C0h+var_100]
0x1800c1bc0  mov     [rbp+0C0h+var_130], eax
0x1800c1bc3  mov     eax, [rbp+0C0h+angle+0Ch]
0x1800c1bc6  mov     [rsp+1C0h+var_148], eax
0x1800c1bca  mov     eax, [rbp+0C0h+angle+8]
0x1800c1bcd  mov     [rsp+1C0h+var_14C], eax
0x1800c1bd1  mov     eax, [rbp+0C0h+angle+4]
0x1800c1bd4  mov     [rsp+1C0h+var_150], eax
0x1800c1bd8  mov     eax, [rbp+0C0h+angle]
0x1800c1bdb  mov     dword ptr [rbp+0C0h+var_120], eax
0x1800c1bde  mov     eax, dword ptr [rbp+0C0h+var_138+4]
0x1800c1be1  mov     [rbp+0C0h+var_12C], eax
0x1800c1be4  mov     eax, dword ptr [rbp+0C0h+var_138]
0x1800c1be7  mov     [rbp+0C0h+var_128], eax
0x1800c1bea  mov     qword ptr [rbp+0C0h+var_140], r8
0x1800c1bee  lea     rax, [rbp+0C0h+var_130]
0x1800c1bf2  mov     [rsp+1C0h+var_168], rax
0x1800c1bf7  lea     rax, [rsp+1C0h+var_148]
0x1800c1bfc  mov     [rsp+1C0h+var_170], rax
0x1800c1c01  lea     rax, [rsp+1C0h+var_14C]
0x1800c1c06  mov     [rsp+1C0h+var_178], rax
0x1800c1c0b  lea     rax, [rsp+1C0h+var_150]
0x1800c1c10  mov     [rsp+1C0h+var_180], rax
0x1800c1c15  lea     rax, [rbp+0C0h+var_120]
0x1800c1c19  mov     [rsp+1C0h+var_188], rax
0x1800c1c1e  lea     rax, [rbp+0C0h+var_12C]
0x1800c1c22  mov     [rsp+1C0h+var_190], rax
0x1800c1c27  lea     rax, [rbp+0C0h+var_128]
0x1800c1c2b  mov     [rsp+1C0h+var_198], rax
0x1800c1c30  lea     rax, [rbp+0C0h+var_140]
0x1800c1c34  mov     [rsp+1C0h+var_1A0], rax
0x1800c1c39  lea     rdx, word_18013F1B2
0x1800c1c40  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c1c45  test    r14b, r14b
0x1800c1c48  jz      loc_1800C208C
0x1800c1c4e  mov     rax, [rdi]
0x1800c1c51  lea     r9, [rbp+0C0h+var_138]
0x1800c1c55  lea     r8, [rbp+0C0h+angle]
0x1800c1c59  lea     rdx, [rbp+0C0h+var_E0]
0x1800c1c5d  mov     rcx, rdi
0x1800c1c60  mov     rax, [rax+148h]
0x1800c1c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1c6c  mov     esi, eax
0x1800c1c6e  test    eax, eax
0x1800c1c70  js      loc_1800C216D
0x1800c1c76  mov     [rsp+1C0h+var_150], 0
0x1800c1c7e  lea     r14, [rdi+10Ch]
0x1800c1c85  lea     r9, [rbp+0C0h+var_F8]; struct Windows::Foundation::Point *
0x1800c1c89  lea     r8, [rbp+0C0h+var_140]; float *
0x1800c1c8d  lea     rdx, [rsp+1C0h+var_150]; float *
0x1800c1c92  mov     rcx, r14; struct D2D1::Matrix3x2F *
0x1800c1c95  call    ?Decompose@Matrix3x2Helper@@SA_NAEBVMatrix3x2F@D2D1@@PEAM1PEAUPoint@Foundation@Windows@@@Z; Matrix3x2Helper::Decompose(D2D1::Matrix3x2F const &,float *,float *,Windows::Foundation::Point *)
0x1800c1c9a  test    al, al
0x1800c1c9c  jz      short loc_1800C1CB9
0x1800c1c9e  movss   xmm0, [rsp+1C0h+var_150]
0x1800c1ca4  mulss   xmm0, cs:__real@42652ee0
0x1800c1cac  xorps   xmm1, xmm1
0x1800c1caf  call    ??$_MakeDegreesStartFrom@M@InkPresenterRulerGeometryHelper@@CAMMM@Z; InkPresenterRulerGeometryHelper::_MakeDegreesStartFrom<float>(float,float)
0x1800c1cb4  movaps  xmm7, xmm0
0x1800c1cb7  jmp     short loc_1800C1CDF
0x1800c1cb9  mov     esi, 8000FFFFh
0x1800c1cbe  lea     rdx, aCannotDecompos; "Cannot decompose m_manipulationTransfor"...
0x1800c1cc5  lea     rcx, [rbp+0C0h+matrix]; string
0x1800c1cc9  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x1800c1cce  mov     rdx, [rax]
0x1800c1cd1  mov     ecx, esi
0x1800c1cd3  call    cs:__imp_RoOriginateError
0x1800c1cd9  movss   xmm7, [rsp+1C0h+var_150]
0x1800c1cdf  test    esi, esi
0x1800c1ce1  js      loc_1800C216D
0x1800c1ce7  movups  xmm10, xmmword ptr [r14]
0x1800c1ceb  movups  [rbp+0C0h+var_C8], xmm10
0x1800c1cf0  movsd   xmm11, qword ptr [r14+10h]
0x1800c1cf6  movsd   [rbp+0C0h+var_B8], xmm11
0x1800c1cfc  mov     qword ptr [rbp+0C0h+var_140], rdi
0x1800c1d00  mov     dl, 1
0x1800c1d02  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RulerAngleSnap@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RulerAngleSnap@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RulerAngleSnap> `wil::Feature<__WilFeatureTraits_Feature_RulerAngleSnap>::GetImpl(void)'::`2'::impl
0x1800c1d09  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RulerAngleSnap@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RulerAngleSnap>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800c1d0e  movaps  xmm1, xmm7
0x1800c1d11  lea     rcx, [rbp+0C0h+var_140]
0x1800c1d15  call    _lambda_c9b099c44735688f64a874efad8688a9___operator__
0x1800c1d1a  mov     [rdi+108h], al
0x1800c1d20  test    al, al
0x1800c1d22  jz      short loc_1800C1D31
0x1800c1d24  movss   xmm4, dword ptr [rdi+100h]
0x1800c1d2c  jmp     loc_1800C1FAD
0x1800c1d31  movaps  xmm0, xmm7
0x1800c1d34  divss   xmm0, cs:__real@42340000
0x1800c1d3c  cvtss2sd xmm0, xmm0
0x1800c1d40  addsd   xmm0, cs:__real@3fe0000000000000; X
0x1800c1d48  call    floor
0x1800c1d4d  cvttsd2si eax, xmm0
0x1800c1d51  movd    xmm1, eax
0x1800c1d55  cvtdq2ps xmm1, xmm1
0x1800c1d58  mulss   xmm1, cs:__real@42340000
0x1800c1d60  movss   dword ptr [rdi+100h], xmm1
0x1800c1d68  movss   xmm8, cs:__real@40a00000
0x1800c1d71  ucomiss xmm7, xmm1
0x1800c1d74  jp      short loc_1800C1D7D
0x1800c1d76  jnz     short loc_1800C1D7D
0x1800c1d78  xorps   xmm0, xmm0
0x1800c1d7b  jmp     short loc_1800C1D90
0x1800c1d7d  comiss  xmm1, xmm7
0x1800c1d80  jbe     short loc_1800C1D88
0x1800c1d82  movaps  xmm0, xmm8
0x1800c1d86  jmp     short loc_1800C1D90
0x1800c1d88  movss   xmm0, cs:__real@c0a00000
0x1800c1d90  movss   dword ptr [rdi+104h], xmm0
0x1800c1d98  cmp     dword ptr [rdi+13Ch], 3
0x1800c1d9f  jnb     short loc_1800C1DFA
0x1800c1da1  xorps   xmm0, xmm0
0x1800c1da4  movups  [rbp+0C0h+var_F8], xmm0
0x1800c1da8  mov     rax, [r15]
0x1800c1dab  lea     rdx, [rbp+0C0h+var_F8]
0x1800c1daf  mov     rcx, r15
0x1800c1db2  mov     rax, [rax+50h]
0x1800c1db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1dbb  movss   xmm1, dword ptr [rbp+0C0h+var_F8+8]
0x1800c1dc0  cvtps2pd xmm1, xmm1
0x1800c1dc3  andps   xmm1, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1800c1dca  movsd   xmm0, cs:__real@3f999999a0000000
0x1800c1dd2  comisd  xmm0, xmm1
0x1800c1dd6  jbe     short loc_1800C1DF1
0x1800c1dd8  mov     dl, 1
0x1800c1dda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RulerSubPixel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RulerSubPixel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RulerSubPixel> `wil::Feature<__WilFeatureTraits_Feature_RulerSubPixel>::GetImpl(void)'::`2'::impl
0x1800c1de1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RulerSubPixel@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RulerSubPixel>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800c1de6  movss   xmm8, cs:__real@3dcccccd
0x1800c1def  jmp     short loc_1800C1DFA
0x1800c1df1  movss   xmm8, cs:__real@3f800000
0x1800c1dfa  movss   [rsp+1C0h+var_14C], xmm8
0x1800c1e01  mov     [rsp+1C0h+var_148], 0
0x1800c1e09  xorps   xmm6, xmm6
0x1800c1e0c  movsd   [rbp+0C0h+var_120], xmm6
0x1800c1e11  movss   xmm1, dword ptr [rdi+0F0h]
0x1800c1e19  cvtps2pd xmm1, xmm1
0x1800c1e1c  lea     r9, [rbp+0C0h+var_120]
0x1800c1e20  lea     r8, [rsp+1C0h+var_148]
0x1800c1e25  lea     rcx, [rsp+1C0h+var_14C]
0x1800c1e2a  call    _lambda_f53b86f9f8fc552dc8d8413cc679f7f2___operator__
0x1800c1e2f  mov     [rsp+1C0h+var_150], 0
0x1800c1e37  movsd   qword ptr [rbp+0C0h+var_140], xmm6
0x1800c1e3c  xorps   xmm1, xmm1
0x1800c1e3f  cvtss2sd xmm1, xmm7
0x1800c1e43  lea     r9, [rbp+0C0h+var_140]
0x1800c1e47  lea     r8, [rsp+1C0h+var_150]
0x1800c1e4c  lea     rcx, [rsp+1C0h+var_14C]
0x1800c1e51  call    _lambda_f53b86f9f8fc552dc8d8413cc679f7f2___operator__
0x1800c1e56  mov     r9d, [rsp+1C0h+var_148]
0x1800c1e5b  movsd   xmm0, qword ptr [rbp+0C0h+var_140]
0x1800c1e60  mov     esi, [rsp+1C0h+var_150]
0x1800c1e64  comisd  xmm0, cs:__real@3fecccccc0000000
0x1800c1e6c  jb      short loc_1800C1E72
0x1800c1e6e  inc     esi
0x1800c1e70  jmp     short loc_1800C1EC8
0x1800c1e72  comisd  xmm0, cs:__real@3fb9999a00000000
0x1800c1e7a  jbe     short loc_1800C1EC8
0x1800c1e7c  mov     r8d, esi
0x1800c1e7f  sub     r8d, r9d
0x1800c1e82  mov     r10d, 0B60B60B7h
0x1800c1e88  mov     eax, r10d
0x1800c1e8b  imul    r8d
0x1800c1e8e  add     edx, r8d
0x1800c1e91  sar     edx, 8
0x1800c1e94  mov     ecx, edx
0x1800c1e96  shr     ecx, 1Fh
0x1800c1e99  add     edx, ecx
0x1800c1e9b  imul    edx, 168h
0x1800c1ea1  cmp     r8d, edx
0x1800c1ea4  jz      short loc_1800C1EC5
0x1800c1ea6  lea     ecx, [r8+1]
0x1800c1eaa  mov     eax, r10d
0x1800c1ead  imul    ecx
0x1800c1eaf  add     edx, ecx
0x1800c1eb1  sar     edx, 8
0x1800c1eb4  mov     eax, edx
0x1800c1eb6  shr     eax, 1Fh
0x1800c1eb9  add     edx, eax
0x1800c1ebb  imul    eax, edx, 168h
0x1800c1ec1  cmp     ecx, eax
0x1800c1ec3  jnz     short loc_1800C1EC8
0x1800c1ec5  mov     esi, r9d
0x1800c1ec8  mov     eax, cs:dword_18015B128
0x1800c1ece  cmp     eax, 5
0x1800c1ed1  jbe     loc_1800C1F93
0x1800c1ed7  mov     edx, 1008h
0x1800c1edc  mov     rcx, r13
0x1800c1edf  call    _tlgKeywordOn
0x1800c1ee4  test    al, al
0x1800c1ee6  jz      loc_1800C1F93
0x1800c1eec  cvtpd2ps xmm0, xmm0
0x1800c1ef0  movss   [rbp+0C0h+var_128], xmm0
0x1800c1ef5  mov     [rbp+0C0h+var_12C], esi
0x1800c1ef8  movsd   xmm1, [rbp+0C0h+var_120]
0x1800c1efd  cvtpd2ps xmm1, xmm1
0x1800c1f01  movss   dword ptr [rbp+0C0h+var_120], xmm1
0x1800c1f06  mov     [rbp+0C0h+var_130], r9d
0x1800c1f0a  mov     [rsp+1C0h+var_148], 3F666666h
0x1800c1f12  movss   [rsp+1C0h+var_14C], xmm8
0x1800c1f19  movss   [rsp+1C0h+var_150], xmm7
0x1800c1f1f  mov     eax, [rdi+0F0h]
0x1800c1f25  mov     [rbp+0C0h+var_140], eax
0x1800c1f28  lea     rax, aInkpresenterst_20; "InkPresenterStencilBase::_OnManipulatio"...
0x1800c1f2f  mov     qword ptr [rbp+0C0h+var_F8], rax
0x1800c1f33  lea     rax, [rbp+0C0h+var_128]
0x1800c1f37  mov     [rsp+1C0h+var_160], rax
0x1800c1f3c  lea     rax, [rbp+0C0h+var_12C]
0x1800c1f40  mov     [rsp+1C0h+var_168], rax
  ... truncated ...
```
