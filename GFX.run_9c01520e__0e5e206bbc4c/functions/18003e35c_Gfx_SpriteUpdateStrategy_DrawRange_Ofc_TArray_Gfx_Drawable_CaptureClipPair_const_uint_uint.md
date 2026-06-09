# Gfx::SpriteUpdateStrategy::DrawRange(Ofc::TArray<Gfx::Drawable::CaptureClipPair> const &,uint,uint)

- ea: `0x18003e35c`
- end: `0x18003e880`
- name: `?DrawRange@SpriteUpdateStrategy@Gfx@@QEAA_NAEBV?$TArray@UCaptureClipPair@Drawable@Gfx@@@Ofc@@II@Z`
- size: `1316`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004e220`

## callees

- `0x180029f54`
- `0x18003df18`
- `0x18003e35c`
- `0x18003e880`
- `0x1800428f0`
- `0x180046500`
- `0x180047790`
- `0x18004b198`
- `0x18004e1f4`
- `0x180051ac0`
- `0x180052528`
- `0x180057e70`
- `0x180070350`
- `0x1800725e4`
- `0x18009a854`
- `0x18009a890`

## import_xrefs

- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x18003e6a0`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x18003e6a0`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x18003e733`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x18003e733`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x18003e742`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x18003e742`

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
0x18003e35c  mov     rax, rsp
0x18003e35f  mov     [rax+20h], r9d
0x18003e363  mov     [rax+18h], r8d
0x18003e367  mov     [rax+10h], rdx
0x18003e36b  mov     [rax+8], rcx
0x18003e36f  push    rbx
0x18003e370  push    rsi
0x18003e371  push    rdi
0x18003e372  push    r12
0x18003e374  push    r13
0x18003e376  push    r14
0x18003e378  push    r15
0x18003e37a  sub     rsp, 3A0h
0x18003e381  mov     r15d, r9d
0x18003e384  mov     r14d, r8d
0x18003e387  mov     r13, rdx
0x18003e38a  mov     rdi, rcx
0x18003e38d  mov     r12, rcx
0x18003e390  mov     [rsp+3D8h+var_330], rcx
0x18003e398  mov     rcx, [rcx+10h]
0x18003e39c  mov     rax, [rcx]
0x18003e39f  mov     rax, [rax+1E8h]
0x18003e3a6  call    cs:__guard_dispatch_icall_fptr
0x18003e3ac  lea     rbx, [r12+20h]
0x18003e3b1  mov     [rsp+3D8h+var_338], rbx
0x18003e3b9  movups  xmm0, xmmword ptr [rbx]
0x18003e3bc  movdqu  [rsp+3D8h+var_378], xmm0
0x18003e3c2  movdqu  [rsp+3D8h+var_368], xmm0
0x18003e3c8  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x18003e3d0  movaps  [rsp+3D8h+var_358], xmm0
0x18003e3d8  movaps  [rsp+3D8h+var_348], xmm0
0x18003e3e0  mov     rcx, rbx
0x18003e3e3  call    ?HasZeroArea@?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@QEBA_NXZ; Math::TRect<Math::TUnits<int,Math::DevicePixels>>::HasZeroArea(void)
0x18003e3e8  test    al, al
0x18003e3ea  jnz     loc_18003E748
0x18003e3f0  mov     rcx, [r12]
0x18003e3f4  mov     edx, 1000h
0x18003e3f9  mov     rcx, [rcx+8]
0x18003e3fd  call    ?TargetSupportsMethod@Gfx@@YA_NAEBUITarget@1@W4RenderingMethod@1@@Z; Gfx::TargetSupportsMethod(Gfx::ITarget const &,Gfx::RenderingMethod)
0x18003e402  test    al, al
0x18003e404  jnz     loc_18003E49E
0x18003e40a  mov     rsi, [r12+30h]
0x18003e40f  mov     rbx, [r12]
0x18003e413  mov     rcx, [rbx+8]
0x18003e417  mov     rax, [rcx]
0x18003e41a  mov     rax, [rax+0F8h]
0x18003e421  call    cs:__guard_dispatch_icall_fptr
0x18003e427  mov     rdx, [rbx+38h]
0x18003e42b  test    rax, rax
0x18003e42e  jz      loc_18003E7F5
0x18003e434  lea     r8, [rax+60h]
0x18003e438  lea     rcx, [rsp+3D8h+var_328]
0x18003e440  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x18003e445  movups  xmm0, xmmword ptr [rax]
0x18003e448  movups  [rsp+3D8h+var_2E8], xmm0
0x18003e450  movups  xmm1, xmmword ptr [rax+10h]
0x18003e454  movups  [rsp+3D8h+var_2D8], xmm1
0x18003e45c  movups  xmm0, xmmword ptr [rax+20h]
0x18003e460  movups  [rsp+3D8h+var_2C8], xmm0
0x18003e468  mov     rbx, [rdi+8]
0x18003e46c  lea     rdx, [rsp+3D8h+var_388]
0x18003e471  mov     rcx, rdi
0x18003e474  call    ?GetTargetClipBounds@SpriteUpdateStrategy@Gfx@@AEBA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@XZ; Gfx::SpriteUpdateStrategy::GetTargetClipBounds(void)
0x18003e479  mov     [rsp+3D8h+var_3B8], rsi
0x18003e47e  lea     r9, [rsp+3D8h+var_2E8]
0x18003e486  mov     r8, rbx
0x18003e489  mov     rdx, rax
0x18003e48c  lea     rcx, [rsp+3D8h+var_378]
0x18003e491  call    ?ClipToTarget@Bounds@Gfx@@QEAAXAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@PEBUICachingPolicy@2@AEBU?$TAffine3x3@N@4@PEBU64@@Z; Gfx::Bounds::ClipToTarget(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,Gfx::ICachingPolicy const *,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)
0x18003e496  mov     rbx, [rsp+3D8h+var_338]
0x18003e49e  mov     eax, dword ptr [rsp+3D8h+var_378+8]
0x18003e4a2  cmp     dword ptr [rsp+3D8h+var_378], eax
0x18003e4a6  jge     loc_18003E748
0x18003e4ac  mov     eax, dword ptr [rsp+3D8h+var_378+0Ch]
0x18003e4b0  cmp     dword ptr [rsp+3D8h+var_378+4], eax
0x18003e4b4  jge     loc_18003E748
0x18003e4ba  cmp     r14d, r15d
0x18003e4bd  jnz     loc_18003E5D5
0x18003e4c3  mov     edx, r14d
0x18003e4c6  mov     rcx, r13
0x18003e4c9  call    ??A?$TArray@UCaptureClipPair@Drawable@Gfx@@@Ofc@@QEBAAEBUCaptureClipPair@Drawable@Gfx@@K@Z; Ofc::TArray<Gfx::Drawable::CaptureClipPair>::operator[](ulong)
0x18003e4ce  mov     rcx, [rax]
0x18003e4d1  mov     rax, [rcx]
0x18003e4d4  mov     r8, [rdi]
0x18003e4d7  add     r8, 8
0x18003e4db  lea     rdx, [rsp+3D8h+var_398]
0x18003e4e0  mov     rax, [rax+20h]
0x18003e4e4  call    cs:__guard_dispatch_icall_fptr
0x18003e4ea  movsd   xmm2, qword ptr [rax]
0x18003e4ee  xorps   xmm3, xmm3
0x18003e4f1  movsd   xmm0, cs:__real@3ff0000000000000
0x18003e4f9  comisd  xmm2, xmm3
0x18003e4fd  jb      loc_18003E825
0x18003e503  movsd   qword ptr [rsp+3D8h+var_358], xmm2
0x18003e50c  movaps  xmm4, xmm2
0x18003e50f  movsd   xmm1, qword ptr [rax+8]
0x18003e514  comisd  xmm1, xmm3
0x18003e518  jb      loc_18003E839
0x18003e51e  movsd   qword ptr [rsp+3D8h+var_358+8], xmm1
0x18003e527  movaps  xmm0, xmm1
0x18003e52a  movsd   xmm3, qword ptr [rsp+3D8h+var_348+8]
0x18003e533  comisd  xmm0, xmm3
0x18003e537  ja      short loc_18003E53C
0x18003e539  movaps  xmm3, xmm1
0x18003e53c  movsd   xmm0, qword ptr [rsp+3D8h+var_348]
0x18003e545  comisd  xmm4, xmm0
0x18003e549  ja      short loc_18003E54E
0x18003e54b  movaps  xmm0, xmm2
0x18003e54e  movsd   [rsp+3D8h+var_398], xmm0
0x18003e554  movsd   [rsp+3D8h+var_390], xmm3
0x18003e55a  lea     r8, [rsp+3D8h+var_398]
0x18003e55f  lea     rdx, [rsp+3D8h+var_368]
0x18003e564  lea     rcx, [rsp+3D8h+var_328]
0x18003e56c  call    ??$?DV?$TUnits@HUDevicePixels@Math@@@Math@@NV?$TUnits@NUDevicePixels@Math@@@1@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TScaling2@N@0@@Z; Math::operator*<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,Math::TScaling2<double> const &)
0x18003e571  mov     rdx, rax
0x18003e574  lea     r8, ?c_halfSamplePx@Gfx@@3V?$TUnits@NUDevicePixels@Math@@@Math@@B; Math::TUnits<double,Math::DevicePixels> const Gfx::c_halfSamplePx
0x18003e57b  lea     rcx, [rsp+3D8h+var_398]
0x18003e580  call    ??$snap_outward_cast@V?$TUnits@HUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBV?$TUnits@NUDevicePixels@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TUnits<double,Math::DevicePixels> const &)
0x18003e585  lea     rcx, [rsp+3D8h+var_398]
0x18003e58a  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x18003e58f  test    al, al
0x18003e591  jnz     loc_18003E7E7
0x18003e597  mov     eax, dword ptr [rsp+3D8h+var_390+4]
0x18003e59b  sub     eax, dword ptr [rsp+3D8h+var_398+4]
0x18003e59f  mov     ecx, dword ptr [rsp+3D8h+var_390]
0x18003e5a3  sub     ecx, dword ptr [rsp+3D8h+var_398]
0x18003e5a7  mov     dword ptr [rsp+3D8h+var_398], ecx
0x18003e5ab  mov     dword ptr [rsp+3D8h+var_398+4], eax
0x18003e5af  mov     rax, [rsp+3D8h+var_398]
0x18003e5b4  mov     [rsp+3D8h+var_398], rax
0x18003e5b9  cmp     dword ptr [rsp+3D8h+var_398+4], 32h ; '2'
0x18003e5be  jb      short loc_18003E5C5
0x18003e5c0  cmp     eax, 32h ; '2'
0x18003e5c3  jnb     short loc_18003E5D5
0x18003e5c5  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x18003e5cd  movaps  [rsp+3D8h+var_358], xmm0
0x18003e5d5  mov     rcx, [rdi+8]
0x18003e5d9  test    rcx, rcx
0x18003e5dc  jnz     loc_18003E7A5
0x18003e5e2  movsd   xmm0, qword ptr [rsp+3D8h+var_358+8]
0x18003e5eb  movsd   xmm1, qword ptr [rsp+3D8h+var_348+8]
0x18003e5f4  comisd  xmm0, xmm1
0x18003e5f8  ja      short loc_18003E5FD
0x18003e5fa  movaps  xmm1, xmm0
0x18003e5fd  movsd   xmm2, qword ptr [rsp+3D8h+var_358]
0x18003e606  movsd   xmm0, qword ptr [rsp+3D8h+var_348]
0x18003e60f  comisd  xmm2, xmm0
0x18003e613  ja      short loc_18003E618
0x18003e615  movaps  xmm0, xmm2
0x18003e618  movsd   [rsp+3D8h+var_398], xmm0
0x18003e61e  movsd   [rsp+3D8h+var_390], xmm1
0x18003e624  lea     r8, [rsp+3D8h+var_398]
0x18003e629  lea     rdx, [rsp+3D8h+var_368]
0x18003e62e  lea     rcx, [rsp+3D8h+var_328]
0x18003e636  call    ??$?DV?$TUnits@HUDevicePixels@Math@@@Math@@NV?$TUnits@NUDevicePixels@Math@@@1@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TScaling2@N@0@@Z; Math::operator*<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,Math::TScaling2<double> const &)
0x18003e63b  mov     rdx, rax
0x18003e63e  lea     r8, ?c_halfSamplePx@Gfx@@3V?$TUnits@NUDevicePixels@Math@@@Math@@B; Math::TUnits<double,Math::DevicePixels> const Gfx::c_halfSamplePx
0x18003e645  lea     rcx, [rsp+3D8h+var_388]
0x18003e64a  call    ??$snap_outward_cast@V?$TUnits@HUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBV?$TUnits@NUDevicePixels@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TUnits<double,Math::DevicePixels> const &)
0x18003e64f  mov     eax, [rsp+3D8h+var_380]
0x18003e653  cmp     [rsp+3D8h+var_388], eax
0x18003e657  jge     loc_18003E748
0x18003e65d  mov     eax, [rsp+3D8h+var_37C]
0x18003e661  cmp     [rsp+3D8h+var_384], eax
0x18003e665  jge     loc_18003E748
0x18003e66b  mov     rcx, [rdi+10h]
0x18003e66f  mov     rax, [rcx]
0x18003e672  lea     rdx, [rsp+3D8h+var_388]
0x18003e677  mov     rax, [rax+1D8h]
0x18003e67e  call    cs:__guard_dispatch_icall_fptr
0x18003e684  mov     rcx, [rdi+10h]
0x18003e688  mov     rax, [rcx]
0x18003e68b  mov     rax, [rax+60h]
0x18003e68f  call    cs:__guard_dispatch_icall_fptr
0x18003e695  mov     rdx, rax
0x18003e698  lea     rcx, [rsp+3D8h+var_2E8]
0x18003e6a0  call    cs:__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z; ARC::ExceptionScope::ExceptionScope(ARC::IFactory const *)
0x18003e6a6  nop
0x18003e6a7  mov     rdx, [r12]
0x18003e6ab  add     rdx, 8; struct Gfx::DrawContext *
0x18003e6af  lea     r9, [rsp+3D8h+var_378]; struct Gfx::Bounds *
0x18003e6b4  mov     r8, [rdi+10h]; struct Gfx::ISpriteTarget *
0x18003e6b8  lea     rcx, [rsp+3D8h+var_298]; this
0x18003e6c0  call    ??0SpriteDrawContext@SpriteUpdateStrategy@Gfx@@QEAA@AEAVDrawContext@2@AEAUISpriteTarget@2@AEAVBounds@2@@Z; Gfx::SpriteUpdateStrategy::SpriteDrawContext::SpriteDrawContext(Gfx::DrawContext &,Gfx::ISpriteTarget &,Gfx::Bounds &)
0x18003e6c5  nop
0x18003e6c6  mov     rcx, [r12]
0x18003e6ca  mov     rax, [rcx]
0x18003e6cd  mov     [rsp+3D8h+var_3B0], r15d
0x18003e6d2  mov     dword ptr [rsp+3D8h+var_3B8], r14d
0x18003e6d7  mov     r9, r13
0x18003e6da  mov     r8d, [rdi+38h]
0x18003e6de  lea     rdx, [rsp+3D8h+var_298]
0x18003e6e6  mov     rax, [rax]
0x18003e6e9  call    cs:__guard_dispatch_icall_fptr
0x18003e6ef  lea     rcx, [rsp+3D8h+var_298]; this
0x18003e6f7  call    ?Commit@SpriteDrawContext@SpriteUpdateStrategy@Gfx@@QEAAXXZ; Gfx::SpriteUpdateStrategy::SpriteDrawContext::Commit(void)
0x18003e6fc  nop
0x18003e6fd  lea     rcx, [rsp+3D8h+var_150]; this
0x18003e705  call    ??1Clip@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Clip::~Clip(void)
0x18003e70a  lea     rcx, [rsp+3D8h+var_200]; this
0x18003e712  call    ??1Frame@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Frame::~Frame(void)
0x18003e717  mov     rax, [rsp+3D8h+var_210]
0x18003e71f  test    rax, rax
0x18003e722  jz      short loc_18003E72B
0x18003e724  mov     dword ptr [rax+68h], 2
0x18003e72b  lea     rcx, [rsp+3D8h+var_2E8]
0x18003e733  call    cs:__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ; ARC::ExceptionScope::RethrowCachedException(void)
0x18003e739  nop
0x18003e73a  lea     rcx, [rsp+3D8h+var_2E8]
0x18003e742  call    cs:__imp_??1ExceptionScope@ARC@@QEAA@XZ; ARC::ExceptionScope::~ExceptionScope(void)
0x18003e748  mov     rcx, [rdi+10h]
0x18003e74c  mov     rax, [rcx]
0x18003e74f  lea     r8, [rsp+3D8h+var_368]
0x18003e754  mov     rdx, rbx
0x18003e757  mov     rax, [rax+1E0h]
0x18003e75e  call    cs:__guard_dispatch_icall_fptr
0x18003e764  mov     rax, [r12]
0x18003e768  mov     rcx, [rax+38h]
0x18003e76c  mov     rax, [rdi+18h]
0x18003e770  movups  xmm0, xmmword ptr [rcx+38h]
0x18003e774  movdqu  xmmword ptr [rax], xmm0
0x18003e778  mov     rcx, [rdi+10h]
0x18003e77c  mov     rax, [rcx]
0x18003e77f  mov     rax, [rax+1F0h]
0x18003e786  call    cs:__guard_dispatch_icall_fptr
0x18003e78c  cmp     eax, 3
0x18003e78f  setnb   al
0x18003e792  add     rsp, 3A0h
0x18003e799  pop     r15
0x18003e79b  pop     r14
0x18003e79d  pop     r13
0x18003e79f  pop     r12
0x18003e7a1  pop     rdi
0x18003e7a2  pop     rsi
0x18003e7a3  pop     rbx
0x18003e7a4  retn
0x18003e7a5  mov     rax, [rcx]
0x18003e7a8  mov     rax, [rax+18h]
0x18003e7ac  call    cs:__guard_dispatch_icall_fptr
0x18003e7b2  test    eax, eax
0x18003e7b4  jz      loc_18003E5E2
0x18003e7ba  mov     rcx, [rdi+8]
0x18003e7be  mov     rax, [rcx]
0x18003e7c1  mov     rax, [rax+18h]
0x18003e7c5  call    cs:__guard_dispatch_icall_fptr
0x18003e7cb  mov     dword ptr [rsp+3D8h+var_398], eax
0x18003e7cf  mov     dword ptr [rsp+3D8h+var_398+4], eax
0x18003e7d3  lea     rdx, [rsp+3D8h+var_398]
0x18003e7d8  lea     rcx, [rsp+3D8h+var_378]
0x18003e7dd  call    ?ImposeSizeLimit@Bounds@Gfx@@QEAAXAEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; Gfx::Bounds::ImposeSizeLimit(Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &)
0x18003e7e2  jmp     loc_18003E5E2
0x18003e7e7  mov     [rsp+3D8h+var_398], 0
0x18003e7f0  jmp     loc_18003E5AF
0x18003e7f5  movups  xmm0, xmmword ptr [rdx]
0x18003e7f8  movups  [rsp+3D8h+var_328], xmm0
0x18003e800  movups  xmm1, xmmword ptr [rdx+10h]
0x18003e804  movups  [rsp+3D8h+var_318], xmm1
0x18003e80c  movups  xmm0, xmmword ptr [rdx+20h]
0x18003e810  movups  [rsp+3D8h+var_308], xmm0
0x18003e818  lea     rax, [rsp+3D8h+var_328]
0x18003e820  jmp     loc_18003E445
0x18003e825  movaps  xmm2, xmm0
0x18003e828  movsd   qword ptr [rsp+3D8h+var_358], xmm0
0x18003e831  movaps  xmm4, xmm0
0x18003e834  jmp     loc_18003E50F
0x18003e839  movaps  xmm1, xmm0
0x18003e83c  movsd   qword ptr [rsp+3D8h+var_358+8], xmm0
0x18003e845  jmp     loc_18003E52A
0x18003e84a  mov     rdi, [rsp+3D8h+arg_0]
0x18003e852  mov     r15d, [rsp+3D8h+arg_18]
0x18003e85a  mov     r14d, [rsp+3D8h+arg_10]
0x18003e862  mov     r13, [rsp+3D8h+arg_8]
0x18003e86a  mov     r12, [rsp+3D8h+var_330]
0x18003e872  mov     rbx, [rsp+3D8h+var_338]
0x18003e87a  jmp     loc_18003E6A7
```
