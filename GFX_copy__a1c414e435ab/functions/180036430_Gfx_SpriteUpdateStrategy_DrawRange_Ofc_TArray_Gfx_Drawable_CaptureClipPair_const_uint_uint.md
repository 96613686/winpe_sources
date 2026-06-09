# Gfx::SpriteUpdateStrategy::DrawRange(Ofc::TArray<Gfx::Drawable::CaptureClipPair> const &,uint,uint)

- ea: `0x180036430`
- end: `0x180036950`
- name: `?DrawRange@SpriteUpdateStrategy@Gfx@@QEAA_NAEBV?$TArray@UCaptureClipPair@Drawable@Gfx@@@Ofc@@II@Z`
- size: `1312`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004edb8`

## callees

- `0x180036430`
- `0x180036950`
- `0x180036a88`
- `0x1800408d0`
- `0x180040cf0`
- `0x180044698`
- `0x18004a7f0`
- `0x18004f188`
- `0x1800502bc`
- `0x1800510b4`
- `0x18005159c`
- `0x1800573f0`
- `0x180069030`
- `0x180069194`
- `0x1800691bc`
- `0x1800dbec0`

## import_xrefs

- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x1800367aa`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x1800367aa`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x18003683d`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x18003683d`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x18003684c`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x18003684c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Gfx::SpriteUpdateStrategy::DrawRange(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  int v4; // r15d
  unsigned int v5; // r14d
  __int64 v6; // r13
  __int64 v7; // rdi
  _QWORD *v8; // r12
  _QWORD *v9; // rbx
  __int64 v10; // rsi
  __int64 v11; // rbx
  __int64 v12; // rax
  _OWORD *v13; // rdx
  _OWORD *v14; // rax
  __int64 v15; // rbx
  int TargetClipBounds; // eax
  _QWORD *v17; // rax
  __int64 v18; // rax
  double v19; // xmm2_8
  double v20; // xmm0_8
  double v21; // xmm4_8
  double v22; // xmm1_8
  double v23; // xmm3_8
  double v24; // xmm0_8
  __int64 v25; // rax
  char v26; // al
  __int64 v27; // rcx
  __int64 v28; // xmm1_8
  __int64 v29; // xmm0_8
  __int64 v30; // rax
  const struct ARC::IFactory *v31; // rax
  double v33; // [rsp+40h] [rbp-398h] BYREF
  double v34; // [rsp+48h] [rbp-390h]
  _DWORD v35[4]; // [rsp+50h] [rbp-388h] BYREF
  __int128 v36; // [rsp+60h] [rbp-378h] BYREF
  __int128 v37; // [rsp+70h] [rbp-368h] BYREF
  __m128i si128; // [rsp+80h] [rbp-358h]
  __m128i v39; // [rsp+90h] [rbp-348h]
  _QWORD *v40; // [rsp+A0h] [rbp-338h]
  _QWORD *v41; // [rsp+A8h] [rbp-330h]
  _OWORD v42[3]; // [rsp+B0h] [rbp-328h] BYREF
  const ARC::Exception *v43; // [rsp+E0h] [rbp-2F8h] BYREF
  _OWORD v44[5]; // [rsp+F0h] [rbp-2E8h] BYREF
  _BYTE v45[136]; // [rsp+140h] [rbp-298h] BYREF
  __int64 v46; // [rsp+1C8h] [rbp-210h]
  char v47[176]; // [rsp+1D8h] [rbp-200h] BYREF
  char v48[336]; // [rsp+288h] [rbp-150h] BYREF

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v7 = a1;
  v8 = (_QWORD *)a1;
  v41 = (_QWORD *)a1;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 488LL))(*(_QWORD *)(a1 + 16));
  v9 = v8 + 4;
  v40 = v8 + 4;
  v36 = *((_OWORD *)v8 + 2);
  v37 = v36;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v39 = si128;
  if ( !(unsigned __int8)Math::TRect<Math::TUnits<int,Math::DevicePixels>>::HasZeroArea(v8 + 4) )
  {
    if ( !(unsigned __int8)Gfx::TargetSupportsMethod(*(_QWORD *)(*v8 + 8LL), 4096) )
    {
      v10 = v8[6];
      v11 = *v8;
      v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*v8 + 8LL) + 248LL))(*(_QWORD *)(*v8 + 8LL));
      v13 = *(_OWORD **)(v11 + 56);
      if ( v12 )
      {
        v14 = (_OWORD *)Math::operator*<double,double,double>(v42, v13, v12 + 96);
      }
      else
      {
        v42[0] = *v13;
        v42[1] = v13[1];
        v42[2] = v13[2];
        v14 = v42;
      }
      v44[0] = *v14;
      v44[1] = v14[1];
      v44[2] = v14[2];
      v15 = *(_QWORD *)(v7 + 8);
      TargetClipBounds = Gfx::SpriteUpdateStrategy::GetTargetClipBounds(v7, v35);
      Gfx::Bounds::ClipToTarget((unsigned int)&v36, TargetClipBounds, v15, (unsigned int)v44, v10);
      v9 = v40;
    }
    if ( (int)v36 < SDWORD2(v36) && SDWORD1(v36) < SHIDWORD(v36) )
    {
      if ( v5 == v4 )
      {
        v17 = (_QWORD *)Ofc::TArray<Gfx::Drawable::CaptureClipPair>::operator[](v6, v5);
        v18 = (*(__int64 (__fastcall **)(_QWORD, double *, __int64))(*(_QWORD *)*v17 + 32LL))(
                *v17,
                &v33,
                *(_QWORD *)v7 + 8LL);
        v19 = *(double *)v18;
        v20 = DOUBLE_1_0;
        if ( *(double *)v18 < 0.0 )
        {
          v19 = DOUBLE_1_0;
          *(double *)si128.m128i_i64 = DOUBLE_1_0;
          v21 = DOUBLE_1_0;
        }
        else
        {
          si128.m128i_i64[0] = *(_QWORD *)v18;
          v21 = v19;
        }
        v22 = *(double *)(v18 + 8);
        if ( v22 < 0.0 )
        {
          v22 = DOUBLE_1_0;
          *(double *)&si128.m128i_i64[1] = DOUBLE_1_0;
        }
        else
        {
          si128.m128i_i64[1] = *(_QWORD *)(v18 + 8);
          v20 = v22;
        }
        v23 = *(double *)&v39.m128i_i64[1];
        if ( v20 <= *(double *)&v39.m128i_i64[1] )
          v23 = v22;
        v24 = *(double *)v39.m128i_i64;
        if ( v21 <= *(double *)v39.m128i_i64 )
          v24 = v19;
        v33 = v24;
        v34 = v23;
        v25 = Math::operator*<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(
                v42,
                &v37,
                &v33);
        Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(
          &v33,
          v25,
          &Gfx::c_halfSamplePx);
        Math::TRect<int>::IsDegenerate(&v33);
        if ( v26 )
        {
          v33 = 0.0;
        }
        else
        {
          LODWORD(v33) = LODWORD(v34) - LODWORD(v33);
          HIDWORD(v33) = HIDWORD(v34) - HIDWORD(v33);
        }
        if ( HIDWORD(v33) < 0x32 || LODWORD(v33) < 0x32 )
          si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      v27 = *(_QWORD *)(v7 + 8);
      if ( v27 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27) )
      {
        LODWORD(v33) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 8) + 24LL))(*(_QWORD *)(v7 + 8));
        HIDWORD(v33) = LODWORD(v33);
        Gfx::Bounds::ImposeSizeLimit(&v36, &v33);
      }
      v28 = v39.m128i_i64[1];
      if ( *(double *)&si128.m128i_i64[1] <= *(double *)&v39.m128i_i64[1] )
        v28 = si128.m128i_i64[1];
      v29 = v39.m128i_i64[0];
      if ( *(double *)si128.m128i_i64 <= *(double *)v39.m128i_i64 )
        v29 = si128.m128i_i64[0];
      v33 = *(double *)&v29;
      v34 = *(double *)&v28;
      v30 = Math::operator*<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(
              v42,
              &v37,
              &v33);
      Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(
        v35,
        v30,
        &Gfx::c_halfSamplePx);
      if ( v35[0] < v35[2] && v35[1] < v35[3] )
      {
        (*(void (__fastcall **)(_QWORD, _DWORD *))(**(_QWORD **)(v7 + 16) + 472LL))(*(_QWORD *)(v7 + 16), v35);
        v31 = (const struct ARC::IFactory *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 16) + 96LL))(*(_QWORD *)(v7 + 16));
        ARC::ExceptionScope::ExceptionScope((ARC::ExceptionScope *)v44, v31);
        while ( 2 )
        {
          try
          {
            Gfx::SpriteUpdateStrategy::SpriteDrawContext::SpriteDrawContext(
              (Gfx::SpriteUpdateStrategy::SpriteDrawContext *)v45,
              (struct Gfx::DrawContext *)(*v8 + 8LL),
              *(struct Gfx::ISpriteTarget **)(v7 + 16),
              (struct Gfx::Bounds *)&v36);
            (**(void (__fastcall ***)(_QWORD, _BYTE *, _QWORD, __int64, unsigned int, int))*v8)(
              *v8,
              v45,
              *(unsigned int *)(v7 + 56),
              v6,
              v5,
              v4);
            Gfx::SpriteUpdateStrategy::SpriteDrawContext::Commit((Gfx::SpriteUpdateStrategy::SpriteDrawContext *)v45);
            Gfx::ITarget::Clip::~Clip((Gfx::ITarget::Clip *)v48);
            Gfx::ITarget::Frame::~Frame((Gfx::ITarget::Frame *)v47);
            if ( v46 )
              *(_DWORD *)(v46 + 104) = 2;
            ARC::ExceptionScope::RethrowCachedException((ARC::ExceptionScope *)v44);
          }
          catch ( const ARC::Exception *v43 )
          {
            ARC::ExceptionScope::Rethrow((ARC::ExceptionScope *)v44, v43);
            v7 = a1;
            v4 = a4;
            v5 = a3;
            v6 = a2;
            v8 = v41;
            v9 = v40;
            continue;
          }
          break;
        }
        ARC::ExceptionScope::~ExceptionScope((ARC::ExceptionScope *)v44);
      }
    }
  }
  (*(void (__fastcall **)(_QWORD, _QWORD *, __int128 *))(**(_QWORD **)(v7 + 16) + 480LL))(
    *(_QWORD *)(v7 + 16),
    v9,
    &v37);
  *(_OWORD *)*(_QWORD *)(v7 + 24) = *(_OWORD *)(*(_QWORD *)(*v8 + 56LL) + 56LL);
  return (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 16) + 496LL))(*(_QWORD *)(v7 + 16)) >= 3;
}

```

## disassembly

```asm
0x180036430  mov     rax, rsp
0x180036433  mov     [rax+20h], r9d
0x180036437  mov     [rax+18h], r8d
0x18003643b  mov     [rax+10h], rdx
0x18003643f  mov     [rax+8], rcx
0x180036443  push    rbx
0x180036444  push    rsi
0x180036445  push    rdi
0x180036446  push    r12
0x180036448  push    r13
0x18003644a  push    r14
0x18003644c  push    r15
0x18003644e  sub     rsp, 3A0h
0x180036455  mov     r15d, r9d
0x180036458  mov     r14d, r8d
0x18003645b  mov     r13, rdx
0x18003645e  mov     rdi, rcx
0x180036461  mov     r12, rcx
0x180036464  mov     [rsp+3D8h+var_330], rcx
0x18003646c  mov     rcx, [rcx+10h]
0x180036470  mov     rax, [rcx]
0x180036473  mov     rax, [rax+1E8h]
0x18003647a  call    cs:__guard_dispatch_icall_fptr
0x180036480  lea     rbx, [r12+20h]
0x180036485  mov     [rsp+3D8h+var_338], rbx
0x18003648d  movups  xmm0, xmmword ptr [rbx]
0x180036490  movdqu  [rsp+3D8h+var_378], xmm0
0x180036496  movdqu  [rsp+3D8h+var_368], xmm0
0x18003649c  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x1800364a4  movaps  [rsp+3D8h+var_358], xmm0
0x1800364ac  movaps  [rsp+3D8h+var_348], xmm0
0x1800364b4  mov     rcx, rbx
0x1800364b7  call    ?HasZeroArea@?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@QEBA_NXZ; Math::TRect<Math::TUnits<int,Math::DevicePixels>>::HasZeroArea(void)
0x1800364bc  test    al, al
0x1800364be  jnz     loc_180036852
0x1800364c4  mov     rcx, [r12]
0x1800364c8  mov     edx, 1000h
0x1800364cd  mov     rcx, [rcx+8]
0x1800364d1  call    ?TargetSupportsMethod@Gfx@@YA_NAEBUITarget@1@W4RenderingMethod@1@@Z; Gfx::TargetSupportsMethod(Gfx::ITarget const &,Gfx::RenderingMethod)
0x1800364d6  test    al, al
0x1800364d8  jnz     loc_180036572
0x1800364de  mov     rsi, [r12+30h]
0x1800364e3  mov     rbx, [r12]
0x1800364e7  mov     rcx, [rbx+8]
0x1800364eb  mov     rax, [rcx]
0x1800364ee  mov     rax, [rax+0F8h]
0x1800364f5  call    cs:__guard_dispatch_icall_fptr
0x1800364fb  mov     rdx, [rbx+38h]
0x1800364ff  test    rax, rax
0x180036502  jz      loc_1800368C5
0x180036508  lea     r8, [rax+60h]
0x18003650c  lea     rcx, [rsp+3D8h+var_328]
0x180036514  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x180036519  movups  xmm0, xmmword ptr [rax]
0x18003651c  movups  [rsp+3D8h+var_2E8], xmm0
0x180036524  movups  xmm1, xmmword ptr [rax+10h]
0x180036528  movups  [rsp+3D8h+var_2D8], xmm1
0x180036530  movups  xmm0, xmmword ptr [rax+20h]
0x180036534  movups  [rsp+3D8h+var_2C8], xmm0
0x18003653c  mov     rbx, [rdi+8]
0x180036540  lea     rdx, [rsp+3D8h+var_388]
0x180036545  mov     rcx, rdi
0x180036548  call    ?GetTargetClipBounds@SpriteUpdateStrategy@Gfx@@AEBA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@XZ; Gfx::SpriteUpdateStrategy::GetTargetClipBounds(void)
0x18003654d  mov     [rsp+3D8h+var_3B8], rsi
0x180036552  lea     r9, [rsp+3D8h+var_2E8]
0x18003655a  mov     r8, rbx
0x18003655d  mov     rdx, rax
0x180036560  lea     rcx, [rsp+3D8h+var_378]
0x180036565  call    ?ClipToTarget@Bounds@Gfx@@QEAAXAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@PEBUICachingPolicy@2@AEBU?$TAffine3x3@N@4@PEBU64@@Z; Gfx::Bounds::ClipToTarget(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,Gfx::ICachingPolicy const *,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)
0x18003656a  mov     rbx, [rsp+3D8h+var_338]
0x180036572  mov     eax, dword ptr [rsp+3D8h+var_378+8]
0x180036576  cmp     dword ptr [rsp+3D8h+var_378], eax
0x18003657a  jge     loc_180036852
0x180036580  mov     eax, dword ptr [rsp+3D8h+var_378+0Ch]
0x180036584  cmp     dword ptr [rsp+3D8h+var_378+4], eax
0x180036588  jge     loc_180036852
0x18003658e  cmp     r14d, r15d
0x180036591  jnz     loc_1800366A9
0x180036597  mov     edx, r14d
0x18003659a  mov     rcx, r13
0x18003659d  call    ??A?$TArray@UCaptureClipPair@Drawable@Gfx@@@Ofc@@QEBAAEBUCaptureClipPair@Drawable@Gfx@@K@Z; Ofc::TArray<Gfx::Drawable::CaptureClipPair>::operator[](ulong)
0x1800365a2  mov     rcx, [rax]
0x1800365a5  mov     rax, [rcx]
0x1800365a8  mov     r8, [rdi]
0x1800365ab  add     r8, 8
0x1800365af  lea     rdx, [rsp+3D8h+var_398]
0x1800365b4  mov     rax, [rax+20h]
0x1800365b8  call    cs:__guard_dispatch_icall_fptr
0x1800365be  movsd   xmm2, qword ptr [rax]
0x1800365c2  xorps   xmm3, xmm3
0x1800365c5  movsd   xmm0, cs:__real@3ff0000000000000
0x1800365cd  comisd  xmm2, xmm3
0x1800365d1  jb      loc_1800368F5
0x1800365d7  movsd   qword ptr [rsp+3D8h+var_358], xmm2
0x1800365e0  movaps  xmm4, xmm2
0x1800365e3  movsd   xmm1, qword ptr [rax+8]
0x1800365e8  comisd  xmm1, xmm3
0x1800365ec  jb      loc_180036909
0x1800365f2  movsd   qword ptr [rsp+3D8h+var_358+8], xmm1
0x1800365fb  movaps  xmm0, xmm1
0x1800365fe  movsd   xmm3, qword ptr [rsp+3D8h+var_348+8]
0x180036607  comisd  xmm0, xmm3
0x18003660b  ja      short loc_180036610
0x18003660d  movaps  xmm3, xmm1
0x180036610  movsd   xmm0, qword ptr [rsp+3D8h+var_348]
0x180036619  comisd  xmm4, xmm0
0x18003661d  ja      short loc_180036622
0x18003661f  movaps  xmm0, xmm2
0x180036622  movsd   [rsp+3D8h+var_398], xmm0
0x180036628  movsd   [rsp+3D8h+var_390], xmm3
0x18003662e  lea     r8, [rsp+3D8h+var_398]
0x180036633  lea     rdx, [rsp+3D8h+var_368]
0x180036638  lea     rcx, [rsp+3D8h+var_328]
0x180036640  call    ??$?DV?$TUnits@HUDevicePixels@Math@@@Math@@NV?$TUnits@NUDevicePixels@Math@@@1@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TScaling2@N@0@@Z; Math::operator*<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,Math::TScaling2<double> const &)
0x180036645  mov     rdx, rax
0x180036648  lea     r8, ?c_halfSamplePx@Gfx@@3V?$TUnits@NUDevicePixels@Math@@@Math@@B; Math::TUnits<double,Math::DevicePixels> const Gfx::c_halfSamplePx
0x18003664f  lea     rcx, [rsp+3D8h+var_398]
0x180036654  call    ??$snap_outward_cast@V?$TUnits@HUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBV?$TUnits@NUDevicePixels@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TUnits<double,Math::DevicePixels> const &)
0x180036659  lea     rcx, [rsp+3D8h+var_398]
0x18003665e  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x180036663  test    al, al
0x180036665  jnz     loc_1800368B7
0x18003666b  mov     eax, dword ptr [rsp+3D8h+var_390+4]
0x18003666f  sub     eax, dword ptr [rsp+3D8h+var_398+4]
0x180036673  mov     ecx, dword ptr [rsp+3D8h+var_390]
0x180036677  sub     ecx, dword ptr [rsp+3D8h+var_398]
0x18003667b  mov     dword ptr [rsp+3D8h+var_398], ecx
0x18003667f  mov     dword ptr [rsp+3D8h+var_398+4], eax
0x180036683  mov     rax, [rsp+3D8h+var_398]
0x180036688  mov     [rsp+3D8h+var_398], rax
0x18003668d  cmp     dword ptr [rsp+3D8h+var_398+4], 32h ; '2'
0x180036692  jb      short loc_180036699
0x180036694  cmp     eax, 32h ; '2'
0x180036697  jnb     short loc_1800366A9
0x180036699  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x1800366a1  movaps  [rsp+3D8h+var_358], xmm0
0x1800366a9  mov     rcx, [rdi+8]
0x1800366ad  test    rcx, rcx
0x1800366b0  jz      short loc_1800366EB
0x1800366b2  mov     rax, [rcx]
0x1800366b5  mov     rax, [rax+18h]
0x1800366b9  call    cs:__guard_dispatch_icall_fptr
0x1800366bf  test    eax, eax
0x1800366c1  jz      short loc_1800366EB
0x1800366c3  mov     rcx, [rdi+8]
0x1800366c7  mov     rax, [rcx]
0x1800366ca  mov     rax, [rax+18h]
0x1800366ce  call    cs:__guard_dispatch_icall_fptr
0x1800366d4  mov     dword ptr [rsp+3D8h+var_398], eax
0x1800366d8  mov     dword ptr [rsp+3D8h+var_398+4], eax
0x1800366dc  lea     rdx, [rsp+3D8h+var_398]
0x1800366e1  lea     rcx, [rsp+3D8h+var_378]
0x1800366e6  call    ?ImposeSizeLimit@Bounds@Gfx@@QEAAXAEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; Gfx::Bounds::ImposeSizeLimit(Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1800366eb  movsd   xmm0, qword ptr [rsp+3D8h+var_358+8]
0x1800366f4  movsd   xmm1, qword ptr [rsp+3D8h+var_348+8]
0x1800366fd  comisd  xmm0, xmm1
0x180036701  ja      short loc_180036706
0x180036703  movaps  xmm1, xmm0
0x180036706  movsd   xmm2, qword ptr [rsp+3D8h+var_358]
0x18003670f  movsd   xmm0, qword ptr [rsp+3D8h+var_348]
0x180036718  comisd  xmm2, xmm0
0x18003671c  jbe     loc_1800368AF
0x180036722  movsd   [rsp+3D8h+var_398], xmm0
0x180036728  movsd   [rsp+3D8h+var_390], xmm1
0x18003672e  lea     r8, [rsp+3D8h+var_398]
0x180036733  lea     rdx, [rsp+3D8h+var_368]
0x180036738  lea     rcx, [rsp+3D8h+var_328]
0x180036740  call    ??$?DV?$TUnits@HUDevicePixels@Math@@@Math@@NV?$TUnits@NUDevicePixels@Math@@@1@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TScaling2@N@0@@Z; Math::operator*<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,Math::TScaling2<double> const &)
0x180036745  mov     rdx, rax
0x180036748  lea     r8, ?c_halfSamplePx@Gfx@@3V?$TUnits@NUDevicePixels@Math@@@Math@@B; Math::TUnits<double,Math::DevicePixels> const Gfx::c_halfSamplePx
0x18003674f  lea     rcx, [rsp+3D8h+var_388]
0x180036754  call    ??$snap_outward_cast@V?$TUnits@HUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBV?$TUnits@NUDevicePixels@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TUnits<double,Math::DevicePixels> const &)
0x180036759  mov     eax, [rsp+3D8h+var_380]
0x18003675d  cmp     [rsp+3D8h+var_388], eax
0x180036761  jge     loc_180036852
0x180036767  mov     eax, [rsp+3D8h+var_37C]
0x18003676b  cmp     [rsp+3D8h+var_384], eax
0x18003676f  jge     loc_180036852
0x180036775  mov     rcx, [rdi+10h]
0x180036779  mov     rax, [rcx]
0x18003677c  lea     rdx, [rsp+3D8h+var_388]
0x180036781  mov     rax, [rax+1D8h]
0x180036788  call    cs:__guard_dispatch_icall_fptr
0x18003678e  mov     rcx, [rdi+10h]
0x180036792  mov     rax, [rcx]
0x180036795  mov     rax, [rax+60h]
0x180036799  call    cs:__guard_dispatch_icall_fptr
0x18003679f  mov     rdx, rax
0x1800367a2  lea     rcx, [rsp+3D8h+var_2E8]
0x1800367aa  call    cs:__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z; ARC::ExceptionScope::ExceptionScope(ARC::IFactory const *)
0x1800367b0  nop
0x1800367b1  mov     rdx, [r12]
0x1800367b5  add     rdx, 8; struct Gfx::DrawContext *
0x1800367b9  lea     r9, [rsp+3D8h+var_378]; struct Gfx::Bounds *
0x1800367be  mov     r8, [rdi+10h]; struct Gfx::ISpriteTarget *
0x1800367c2  lea     rcx, [rsp+3D8h+var_298]; this
0x1800367ca  call    ??0SpriteDrawContext@SpriteUpdateStrategy@Gfx@@QEAA@AEAVDrawContext@2@AEAUISpriteTarget@2@AEAVBounds@2@@Z; Gfx::SpriteUpdateStrategy::SpriteDrawContext::SpriteDrawContext(Gfx::DrawContext &,Gfx::ISpriteTarget &,Gfx::Bounds &)
0x1800367cf  nop
0x1800367d0  mov     rcx, [r12]
0x1800367d4  mov     rax, [rcx]
0x1800367d7  mov     [rsp+3D8h+var_3B0], r15d
0x1800367dc  mov     dword ptr [rsp+3D8h+var_3B8], r14d
0x1800367e1  mov     r9, r13
0x1800367e4  mov     r8d, [rdi+38h]
0x1800367e8  lea     rdx, [rsp+3D8h+var_298]
0x1800367f0  mov     rax, [rax]
0x1800367f3  call    cs:__guard_dispatch_icall_fptr
0x1800367f9  lea     rcx, [rsp+3D8h+var_298]; this
0x180036801  call    ?Commit@SpriteDrawContext@SpriteUpdateStrategy@Gfx@@QEAAXXZ; Gfx::SpriteUpdateStrategy::SpriteDrawContext::Commit(void)
0x180036806  nop
0x180036807  lea     rcx, [rsp+3D8h+var_150]; this
0x18003680f  call    ??1Clip@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Clip::~Clip(void)
0x180036814  lea     rcx, [rsp+3D8h+var_200]; this
0x18003681c  call    ??1Frame@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Frame::~Frame(void)
0x180036821  mov     rax, [rsp+3D8h+var_210]
0x180036829  test    rax, rax
0x18003682c  jz      short loc_180036835
0x18003682e  mov     dword ptr [rax+68h], 2
0x180036835  lea     rcx, [rsp+3D8h+var_2E8]
0x18003683d  call    cs:__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ; ARC::ExceptionScope::RethrowCachedException(void)
0x180036843  nop
0x180036844  lea     rcx, [rsp+3D8h+var_2E8]
0x18003684c  call    cs:__imp_??1ExceptionScope@ARC@@QEAA@XZ; ARC::ExceptionScope::~ExceptionScope(void)
0x180036852  mov     rcx, [rdi+10h]
0x180036856  mov     rax, [rcx]
0x180036859  lea     r8, [rsp+3D8h+var_368]
0x18003685e  mov     rdx, rbx
0x180036861  mov     rax, [rax+1E0h]
0x180036868  call    cs:__guard_dispatch_icall_fptr
0x18003686e  mov     rax, [r12]
0x180036872  mov     rcx, [rax+38h]
0x180036876  mov     rax, [rdi+18h]
0x18003687a  movups  xmm0, xmmword ptr [rcx+38h]
0x18003687e  movdqu  xmmword ptr [rax], xmm0
0x180036882  mov     rcx, [rdi+10h]
0x180036886  mov     rax, [rcx]
0x180036889  mov     rax, [rax+1F0h]
0x180036890  call    cs:__guard_dispatch_icall_fptr
0x180036896  cmp     eax, 3
0x180036899  setnb   al
0x18003689c  add     rsp, 3A0h
0x1800368a3  pop     r15
0x1800368a5  pop     r14
0x1800368a7  pop     r13
0x1800368a9  pop     r12
0x1800368ab  pop     rdi
0x1800368ac  pop     rsi
0x1800368ad  pop     rbx
0x1800368ae  retn
0x1800368af  movaps  xmm0, xmm2
0x1800368b2  jmp     loc_180036722
0x1800368b7  mov     [rsp+3D8h+var_398], 0
0x1800368c0  jmp     loc_180036683
0x1800368c5  movups  xmm0, xmmword ptr [rdx]
0x1800368c8  movups  [rsp+3D8h+var_328], xmm0
0x1800368d0  movups  xmm1, xmmword ptr [rdx+10h]
0x1800368d4  movups  [rsp+3D8h+var_318], xmm1
0x1800368dc  movups  xmm0, xmmword ptr [rdx+20h]
0x1800368e0  movups  [rsp+3D8h+var_308], xmm0
0x1800368e8  lea     rax, [rsp+3D8h+var_328]
0x1800368f0  jmp     loc_180036519
0x1800368f5  movaps  xmm2, xmm0
0x1800368f8  movsd   qword ptr [rsp+3D8h+var_358], xmm0
0x180036901  movaps  xmm4, xmm0
0x180036904  jmp     loc_1800365E3
0x180036909  movaps  xmm1, xmm0
0x18003690c  movsd   qword ptr [rsp+3D8h+var_358+8], xmm0
0x180036915  jmp     loc_1800365FE
0x18003691a  mov     rdi, [rsp+3D8h+arg_0]
0x180036922  mov     r15d, [rsp+3D8h+arg_18]
0x18003692a  mov     r14d, [rsp+3D8h+arg_10]
0x180036932  mov     r13, [rsp+3D8h+arg_8]
0x18003693a  mov     r12, [rsp+3D8h+var_330]
0x180036942  mov     rbx, [rsp+3D8h+var_338]
0x18003694a  jmp     loc_1800367B1
```
