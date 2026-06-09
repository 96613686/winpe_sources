# GEL::PrinterClipStack::SurfaceClip::Apply(Gfx::ITarget::Clip const &)

- ea: `0x1800a60b8`
- end: `0x1800a66a9`
- name: `?Apply@SurfaceClip@PrinterClipStack@GEL@@QEAAXAEBVClip@ITarget@Gfx@@@Z`
- size: `1521`
- prototype: `void __fastcall(GEL::PrinterClipStack::SurfaceClip *__hidden this, const struct Gfx::ITarget::Clip *)`
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x1800a4ab0`
- `0x1800a5ff0`

## callees

- `0x18002d050`
- `0x180051ac0`
- `0x180052528`
- `0x180057e70`
- `0x18006e578`
- `0x18006e604`
- `0x18007ef58`
- `0x18007f754`
- `0x180080644`
- `0x180099b00`
- `0x1800a60b8`
- `0x18011d5a0`
- `0x18015aaa8`
- `0x18015d388`
- `0x180166ff0`
- `0x180168454`
- `0x180179988`
- `0x1801ce13c`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800a6690`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800a6690`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a61d5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a621f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a629c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a6309`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a61d5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a621f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a629c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a6309`
- `gdiplus!GdipSetClipRectI` at `0x1800a666b`
- `gdiplus!GdipSetClipRectI` at `0x1800a666b`
- `gdiplus!GdipSetClipPath` at `0x1800a61f5`
- `gdiplus!GdipSetClipPath` at `0x1800a62bc`
- `gdiplus!GdipSetClipPath` at `0x1800a6387`
- `gdiplus!GdipSetClipPath` at `0x1800a63e1`
- `gdiplus!GdipSetClipPath` at `0x1800a61f5`
- `gdiplus!GdipSetClipPath` at `0x1800a62bc`
- `gdiplus!GdipSetClipPath` at `0x1800a6387`
- `gdiplus!GdipSetClipPath` at `0x1800a63e1`
- `gdiplus!GdipSetClipRect` at `0x1800a64b5`
- `gdiplus!GdipSetClipRect` at `0x1800a6551`
- `gdiplus!GdipSetClipRect` at `0x1800a64b5`
- `gdiplus!GdipSetClipRect` at `0x1800a6551`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall GEL::PrinterClipStack::SurfaceClip::Apply(
        GEL::PrinterClipStack::SurfaceClip *this,
        const struct Gfx::ITarget::Clip *a2)
{
  __int64 v4; // rcx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  const struct ARC::IGeometry *ClipGeometry; // rax
  Gfx::GpClipHolder *UnusedClipHolder; // rax
  __int64 LocalToDeviceTransform; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  const struct ARC::IGeometry *v21; // rax
  Gfx::GpClipHolder *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rcx
  GEL *ClipPath; // rbx
  Gfx::GpClipHolder *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  const struct GEL::IPath *v33; // rdx
  const struct Gdiplus::GpPath *v34; // rax
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  GEL *v38; // rbx
  Gfx::GpClipHolder *v39; // rax
  const struct GEL::IPath *v40; // rdx
  const struct Gdiplus::GpPath *v41; // rax
  unsigned int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // r8
  Gfx::GpWorldTransformRestorer *v45; // rcx
  float *v46; // rax
  double *v47; // rcx
  __int64 v48; // rdx
  Gfx::GpClipHolder *v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  unsigned int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // r8
  float *v55; // rax
  double *v56; // rsi
  __int64 v57; // rcx
  Gfx::GpClipHolder *v58; // rax
  unsigned int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // r8
  __m128i v62; // xmm0
  char v63; // al
  Gfx::GpClipHolder *v64; // rax
  __int64 v65; // rax
  unsigned int *Height; // rax
  __int64 v67; // r8
  unsigned int *Width; // rax
  int v69; // r9d
  unsigned int v70; // eax
  __int64 v71; // rdx
  __int64 v72; // r8
  __m128i v73; // [rsp+30h] [rbp-89h] BYREF
  __int128 v74; // [rsp+40h] [rbp-79h] BYREF
  __int128 v75; // [rsp+50h] [rbp-69h]
  __int128 v76; // [rsp+60h] [rbp-59h]
  __int128 v77; // [rsp+70h] [rbp-49h] BYREF
  __int128 v78; // [rsp+80h] [rbp-39h]
  __int128 v79; // [rsp+90h] [rbp-29h]
  _BYTE v80[48]; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v81[64]; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v82; // [rsp+120h] [rbp+67h] BYREF
  char v83; // [rsp+130h] [rbp+77h] BYREF

  if ( !*(_QWORD *)this )
  {
    v4 = 23900230;
LABEL_44:
    MsoShipAssertTagProc(v4);
    return;
  }
  v5 = *((_DWORD *)a2 + 6);
  if ( !v5 )
  {
    v4 = 23900232;
    goto LABEL_44;
  }
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 != 1 )
                return;
              v82 = 0;
              ClipGeometry = Gfx::ITarget::Clip::GetClipGeometry(a2);
              if ( (*(unsigned __int8 (__fastcall **)(const struct ARC::IGeometry *, GUID *, __int64 *))(*(_QWORD *)ClipGeometry + 16LL))(
                     ClipGeometry,
                     &GUID_b9e550ba_696b_4605_ba63_041cafec3d57,
                     &v82)
                && v82 )
              {
                UnusedClipHolder = GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(this);
                Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
                v74 = *(_OWORD *)((char *)this + 8);
                v75 = *(_OWORD *)((char *)this + 24);
                v76 = *(_OWORD *)((char *)this + 40);
                LocalToDeviceTransform = Gfx::ITarget::Clip::GetLocalToDeviceTransform(a2, &v77);
                v15 = Math::operator*<double,double,double>(v80, LocalToDeviceTransform, &v74);
                Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v73, *(_QWORD *)this, v15);
                v16 = v82;
                if ( !v82 )
                  CrashWithRecovery(0x1E3C3840u, 0);
                v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                v18 = GdipSetClipPath(*(_QWORD *)this, v17, 1);
                Gfx::GdipStatus_ThrowOnFailureMessageTag(v18, v19, v20, 38869145);
                Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer((Gfx::GpWorldTransformRestorer *)&v73);
LABEL_22:
                v28 = v82;
                if ( v82 )
                {
                  v82 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
                }
                return;
              }
              CrashWithRecovery(0x1E082311u, 0);
            }
            v82 = 0;
            v21 = Gfx::ITarget::Clip::GetClipGeometry(a2);
            if ( (*(unsigned __int8 (__fastcall **)(const struct ARC::IGeometry *, GUID *, __int64 *))(*(_QWORD *)v21 + 16LL))(
                   v21,
                   &GUID_b9e550ba_696b_4605_ba63_041cafec3d57,
                   &v82)
              && v82 )
            {
              v22 = GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(this);
              Gfx::GpClipHolder::SaveClipRegion(v22, *(const struct Gdiplus::GpGraphics **)this);
              Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v73, *(_QWORD *)this, (char *)this + 8);
              v23 = v82;
              if ( !v82 )
                CrashWithRecovery(0x1E3C3840u, 0);
              v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
              v25 = GdipSetClipPath(*(_QWORD *)this, v24, 1);
              Gfx::GdipStatus_ThrowOnFailureMessageTag(v25, v26, v27, 38869144);
              Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer((Gfx::GpWorldTransformRestorer *)&v73);
              goto LABEL_22;
            }
            CrashWithRecovery(0x1E082312u, 0);
          }
          ClipPath = Gfx::ITarget::Clip::GetClipPath(a2);
          v30 = GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(this);
          Gfx::GpClipHolder::SaveClipRegion(v30, *(const struct Gdiplus::GpGraphics **)this);
          v74 = *(_OWORD *)((char *)this + 8);
          v75 = *(_OWORD *)((char *)this + 24);
          v76 = *(_OWORD *)((char *)this + 40);
          v31 = Gfx::ITarget::Clip::GetLocalToDeviceTransform(a2, v80);
          v32 = Math::operator*<double,double,double>(&v77, v31, &v74);
          Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v73, *(_QWORD *)this, v32);
          v34 = GEL::PathToGpPath(ClipPath, v33);
          v35 = GdipSetClipPath(*(_QWORD *)this, v34, 1);
          Gfx::GdipStatus_ThrowOnFailureMessageTag(v35, v36, v37, 38869145);
        }
        else
        {
          v38 = Gfx::ITarget::Clip::GetClipPath(a2);
          v39 = GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(this);
          Gfx::GpClipHolder::SaveClipRegion(v39, *(const struct Gdiplus::GpGraphics **)this);
          Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v73, *(_QWORD *)this, (char *)this + 8);
          v41 = GEL::PathToGpPath(v38, v40);
          v42 = GdipSetClipPath(*(_QWORD *)this, v41, 1);
          Gfx::GdipStatus_ThrowOnFailureMessageTag(v42, v43, v44, 38869144);
        }
        v45 = (Gfx::GpWorldTransformRestorer *)&v73;
LABEL_42:
        Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer(v45);
        return;
      }
      v46 = (float *)&v73;
      v47 = (double *)((char *)a2 + 32);
      v48 = 4;
      do
      {
        *v46++ = *v47++;
        --v48;
      }
      while ( v48 );
      v49 = GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(this);
      Gfx::GpClipHolder::SaveClipRegion(v49, *(const struct Gdiplus::GpGraphics **)this);
      v77 = *(_OWORD *)((char *)this + 8);
      v78 = *(_OWORD *)((char *)this + 24);
      v79 = *(_OWORD *)((char *)this + 40);
      v50 = Gfx::ITarget::Clip::GetLocalToDeviceTransform(a2, v80);
      v51 = Math::operator*<double,double,double>(v81, v50, &v77);
      Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v74, *(_QWORD *)this, v51);
      Math::TRect<float>::GetHeight(&v73);
      Math::TRect<float>::GetWidth(&v73);
      v52 = GdipSetClipRect(*(_QWORD *)this);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v52, v53, v54, 38869143);
    }
    else
    {
      v55 = (float *)&v73;
      v56 = (double *)((char *)a2 + 32);
      v57 = 4;
      do
      {
        *v55++ = *v56++;
        --v57;
      }
      while ( v57 );
      v58 = GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(this);
      Gfx::GpClipHolder::SaveClipRegion(v58, *(const struct Gdiplus::GpGraphics **)this);
      Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v74, *(_QWORD *)this, (char *)this + 8);
      Math::TRect<float>::GetHeight(&v73);
      Math::TRect<float>::GetWidth(&v73);
      v59 = GdipSetClipRect(*(_QWORD *)this);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v59, v60, v61, 38869142);
    }
LABEL_41:
    v45 = (Gfx::GpWorldTransformRestorer *)&v74;
    goto LABEL_42;
  }
  v62 = *(__m128i *)Gfx::ITarget::Frame::GetLogicalBounds(*(_QWORD *)a2, &v74);
  v73 = v62;
  if ( *((_BYTE *)this + 76) )
  {
    if ( !*((_QWORD *)a2 + 1) )
    {
      if ( *((_DWORD *)a2 + 6) )
      {
        *(double *)v62.m128i_i64 = Math::TRect<int>::IsDegenerate(&v73);
        if ( v63
          || v62.m128i_i64[0] != 0x8000000080000000uLL
          || _mm_srli_si128(v62, 8).m128i_u64[0] != 0x7FFFFFFF7FFFFFFFLL )
        {
          v64 = GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(this);
          Gfx::GpClipHolder::SaveClipRegion(v64, *(const struct Gdiplus::GpGraphics **)this);
          v77 = *(_OWORD *)((char *)this + 8);
          v78 = *(_OWORD *)((char *)this + 24);
          v79 = *(_OWORD *)((char *)this + 40);
          v65 = Math::operator*<double,double,double>(v81, *(_QWORD *)a2 + 96LL, &v77);
          Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v74, *(_QWORD *)this, v65);
          Height = (unsigned int *)Math::TRect<Math::TUnits<int,Math::DevicePixels>>::GetHeight(&v73, &v82);
          Width = (unsigned int *)Math::TRect<Math::TUnits<int,Math::DevicePixels>>::GetWidth(&v73, &v83, v67, *Height);
          v70 = GdipSetClipRectI(
                  *(_QWORD *)this,
                  v62.m128i_u32[0],
                  v73.m128i_u32[1],
                  *Width,
                  v69,
                  1,
                  v73.m128i_i64[0],
                  v73.m128i_i64[1]);
          Gfx::GdipStatus_ThrowOnFailureMessageTag(v70, v71, v72, 38869146);
          goto LABEL_41;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800a60b8  mov     [rsp-8+arg_8], rbx
0x1800a60bd  push    rbp
0x1800a60be  push    rsi
0x1800a60bf  push    rdi
0x1800a60c0  lea     rbp, [rsp-47h]
0x1800a60c5  sub     rsp, 100h
0x1800a60cc  mov     rsi, rdx
0x1800a60cf  mov     rdi, rcx
0x1800a60d2  cmp     qword ptr [rcx], 0
0x1800a60d6  jnz     short loc_1800A60E2
0x1800a60d8  mov     ecx, 16CB046h
0x1800a60dd  jmp     loc_1800A6690
0x1800a60e2  mov     ecx, [rdx+18h]
0x1800a60e5  test    ecx, ecx
0x1800a60e7  jz      loc_1800A668B
0x1800a60ed  sub     ecx, 1
0x1800a60f0  jz      loc_1800A656A
0x1800a60f6  sub     ecx, 1
0x1800a60f9  jz      loc_1800A64CE
0x1800a60ff  sub     ecx, 1
0x1800a6102  jz      loc_1800A63FF
0x1800a6108  sub     ecx, 1
0x1800a610b  jz      loc_1800A639D
0x1800a6111  sub     ecx, 1
0x1800a6114  jz      loc_1800A6310
0x1800a611a  sub     ecx, 1
0x1800a611d  jz      loc_1800A6226
0x1800a6123  cmp     ecx, 1
0x1800a6126  jnz     loc_1800A6696
0x1800a612c  mov     [rbp+57h+arg_0], 0
0x1800a6134  mov     rcx, rsi; this
0x1800a6137  call    ?GetClipGeometry@Clip@ITarget@Gfx@@QEBAAEBUIGeometry@ARC@@XZ; Gfx::ITarget::Clip::GetClipGeometry(void)
0x1800a613c  mov     r9, rax
0x1800a613f  mov     rcx, [rax]
0x1800a6142  mov     rax, [rcx+10h]
0x1800a6146  lea     r8, [rbp+57h+arg_0]
0x1800a614a  lea     rdx, _GUID_b9e550ba_696b_4605_ba63_041cafec3d57
0x1800a6151  mov     rcx, r9
0x1800a6154  call    cs:__guard_dispatch_icall_fptr
0x1800a615a  test    al, al
0x1800a615c  jz      loc_1800A6218
0x1800a6162  cmp     [rbp+57h+arg_0], 0
0x1800a6167  jz      loc_1800A6218
0x1800a616d  mov     rcx, rdi; this
0x1800a6170  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800a6175  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800a6178  mov     rcx, rax; this
0x1800a617b  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800a6180  movups  xmm0, xmmword ptr [rdi+8]
0x1800a6184  movups  [rbp+57h+var_D0], xmm0
0x1800a6188  movups  xmm1, xmmword ptr [rdi+18h]
0x1800a618c  movups  [rbp+57h+var_C0], xmm1
0x1800a6190  movups  xmm0, xmmword ptr [rdi+28h]
0x1800a6194  movups  [rbp+57h+var_B0], xmm0
0x1800a6198  lea     rdx, [rbp+57h+var_A0]
0x1800a619c  mov     rcx, rsi
0x1800a619f  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x1800a61a4  mov     rdx, rax
0x1800a61a7  lea     r8, [rbp+57h+var_D0]
0x1800a61ab  lea     rcx, [rbp+57h+var_70]
0x1800a61af  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x1800a61b4  mov     r8, rax
0x1800a61b7  mov     rdx, [rdi]
0x1800a61ba  lea     rcx, [rsp+110h+var_E0]
0x1800a61bf  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800a61c4  nop
0x1800a61c5  mov     rcx, [rbp+57h+arg_0]
0x1800a61c9  test    rcx, rcx
0x1800a61cc  jnz     short loc_1800A61DC
0x1800a61ce  xor     edx, edx
0x1800a61d0  mov     ecx, 1E3C3840h
0x1800a61d5  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a61db  nop
0x1800a61dc  mov     rax, [rcx]
0x1800a61df  mov     rax, [rax+10h]
0x1800a61e3  call    cs:__guard_dispatch_icall_fptr
0x1800a61e9  mov     r8d, 1
0x1800a61ef  mov     rdx, rax
0x1800a61f2  mov     rcx, [rdi]
0x1800a61f5  call    cs:__imp_GdipSetClipPath
0x1800a61fb  mov     r9d, 2511899h
0x1800a6201  mov     ecx, eax
0x1800a6203  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a6208  nop
0x1800a6209  lea     rcx, [rsp+110h+var_E0]; this
0x1800a620e  call    ??1GpWorldTransformRestorer@Gfx@@QEAA@XZ; Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer(void)
0x1800a6213  jmp     loc_1800A62DB
0x1800a6218  xor     edx, edx
0x1800a621a  mov     ecx, 1E082311h
0x1800a621f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a6225  nop
0x1800a6226  mov     [rbp+57h+arg_0], 0
0x1800a622e  mov     rcx, rsi; this
0x1800a6231  call    ?GetClipGeometry@Clip@ITarget@Gfx@@QEBAAEBUIGeometry@ARC@@XZ; Gfx::ITarget::Clip::GetClipGeometry(void)
0x1800a6236  mov     r9, rax
0x1800a6239  mov     rcx, [rax]
0x1800a623c  mov     rax, [rcx+10h]
0x1800a6240  lea     r8, [rbp+57h+arg_0]
0x1800a6244  lea     rdx, _GUID_b9e550ba_696b_4605_ba63_041cafec3d57
0x1800a624b  mov     rcx, r9
0x1800a624e  call    cs:__guard_dispatch_icall_fptr
0x1800a6254  test    al, al
0x1800a6256  jz      loc_1800A6302
0x1800a625c  cmp     [rbp+57h+arg_0], 0
0x1800a6261  jz      loc_1800A6302
0x1800a6267  mov     rcx, rdi; this
0x1800a626a  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800a626f  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800a6272  mov     rcx, rax; this
0x1800a6275  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800a627a  lea     r8, [rdi+8]
0x1800a627e  mov     rdx, [rdi]
0x1800a6281  lea     rcx, [rsp+110h+var_E0]
0x1800a6286  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800a628b  nop
0x1800a628c  mov     rcx, [rbp+57h+arg_0]
0x1800a6290  test    rcx, rcx
0x1800a6293  jnz     short loc_1800A62A3
0x1800a6295  xor     edx, edx
0x1800a6297  mov     ecx, 1E3C3840h
0x1800a629c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a62a2  nop
0x1800a62a3  mov     rax, [rcx]
0x1800a62a6  mov     rax, [rax+10h]
0x1800a62aa  call    cs:__guard_dispatch_icall_fptr
0x1800a62b0  mov     r8d, 1
0x1800a62b6  mov     rdx, rax
0x1800a62b9  mov     rcx, [rdi]
0x1800a62bc  call    cs:__imp_GdipSetClipPath
0x1800a62c2  mov     r9d, 2511898h
0x1800a62c8  mov     ecx, eax
0x1800a62ca  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a62cf  nop
0x1800a62d0  lea     rcx, [rsp+110h+var_E0]; this
0x1800a62d5  call    ??1GpWorldTransformRestorer@Gfx@@QEAA@XZ; Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer(void)
0x1800a62da  nop
0x1800a62db  mov     rcx, [rbp+57h+arg_0]
0x1800a62df  test    rcx, rcx
0x1800a62e2  jz      loc_1800A6696
0x1800a62e8  mov     [rbp+57h+arg_0], 0
0x1800a62f0  mov     rax, [rcx]
0x1800a62f3  mov     rax, [rax+8]
0x1800a62f7  call    cs:__guard_dispatch_icall_fptr
0x1800a62fd  jmp     loc_1800A6696
0x1800a6302  xor     edx, edx
0x1800a6304  mov     ecx, 1E082312h
0x1800a6309  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a630f  nop
0x1800a6310  mov     rcx, rsi; this
0x1800a6313  call    ?GetClipPath@Clip@ITarget@Gfx@@QEBAAEBUIPath@GEL@@XZ; Gfx::ITarget::Clip::GetClipPath(void)
0x1800a6318  mov     rbx, rax
0x1800a631b  mov     rcx, rdi; this
0x1800a631e  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800a6323  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800a6326  mov     rcx, rax; this
0x1800a6329  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800a632e  movups  xmm0, xmmword ptr [rdi+8]
0x1800a6332  movups  [rbp+57h+var_D0], xmm0
0x1800a6336  movups  xmm1, xmmword ptr [rdi+18h]
0x1800a633a  movups  [rbp+57h+var_C0], xmm1
0x1800a633e  movups  xmm0, xmmword ptr [rdi+28h]
0x1800a6342  movups  [rbp+57h+var_B0], xmm0
0x1800a6346  lea     rdx, [rbp+57h+var_70]
0x1800a634a  mov     rcx, rsi
0x1800a634d  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x1800a6352  mov     rdx, rax
0x1800a6355  lea     r8, [rbp+57h+var_D0]
0x1800a6359  lea     rcx, [rbp+57h+var_A0]
0x1800a635d  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x1800a6362  mov     r8, rax
0x1800a6365  mov     rdx, [rdi]
0x1800a6368  lea     rcx, [rsp+110h+var_E0]
0x1800a636d  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800a6372  nop
0x1800a6373  mov     rcx, rbx; this
0x1800a6376  call    ?PathToGpPath@GEL@@YAAEBVGpPath@Gdiplus@@AEBUIPath@1@@Z; GEL::PathToGpPath(GEL::IPath const &)
0x1800a637b  mov     r8d, 1
0x1800a6381  mov     rdx, rax
0x1800a6384  mov     rcx, [rdi]
0x1800a6387  call    cs:__imp_GdipSetClipPath
0x1800a638d  mov     r9d, 2511899h
0x1800a6393  mov     ecx, eax
0x1800a6395  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a639a  nop
0x1800a639b  jmp     short loc_1800A63F5
0x1800a639d  mov     rcx, rsi; this
0x1800a63a0  call    ?GetClipPath@Clip@ITarget@Gfx@@QEBAAEBUIPath@GEL@@XZ; Gfx::ITarget::Clip::GetClipPath(void)
0x1800a63a5  mov     rbx, rax
0x1800a63a8  mov     rcx, rdi; this
0x1800a63ab  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800a63b0  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800a63b3  mov     rcx, rax; this
0x1800a63b6  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800a63bb  lea     r8, [rdi+8]
0x1800a63bf  mov     rdx, [rdi]
0x1800a63c2  lea     rcx, [rsp+110h+var_E0]
0x1800a63c7  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800a63cc  nop
0x1800a63cd  mov     rcx, rbx; this
0x1800a63d0  call    ?PathToGpPath@GEL@@YAAEBVGpPath@Gdiplus@@AEBUIPath@1@@Z; GEL::PathToGpPath(GEL::IPath const &)
0x1800a63d5  mov     r8d, 1
0x1800a63db  mov     rdx, rax
0x1800a63de  mov     rcx, [rdi]
0x1800a63e1  call    cs:__imp_GdipSetClipPath
0x1800a63e7  mov     r9d, 2511898h
0x1800a63ed  mov     ecx, eax
0x1800a63ef  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a63f4  nop
0x1800a63f5  lea     rcx, [rsp+110h+var_E0]
0x1800a63fa  jmp     loc_1800A6684
0x1800a63ff  lea     rax, [rsp+110h+var_E0]
0x1800a6404  lea     rcx, [rdx+20h]
0x1800a6408  mov     edx, 4
0x1800a640d  movsd   xmm0, qword ptr [rcx]
0x1800a6411  cvtpd2ps xmm0, xmm0
0x1800a6415  movss   dword ptr [rax], xmm0
0x1800a6419  lea     rcx, [rcx+8]
0x1800a641d  lea     rax, [rax+4]
0x1800a6421  sub     rdx, 1
0x1800a6425  jnz     short loc_1800A640D
0x1800a6427  mov     rcx, rdi; this
0x1800a642a  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800a642f  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800a6432  mov     rcx, rax; this
0x1800a6435  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800a643a  movups  xmm0, xmmword ptr [rdi+8]
0x1800a643e  movups  [rbp+57h+var_A0], xmm0
0x1800a6442  movups  xmm1, xmmword ptr [rdi+18h]
0x1800a6446  movups  [rbp+57h+var_90], xmm1
0x1800a644a  movups  xmm0, xmmword ptr [rdi+28h]
0x1800a644e  movups  [rbp+57h+var_80], xmm0
0x1800a6452  lea     rdx, [rbp+57h+var_70]
0x1800a6456  mov     rcx, rsi
0x1800a6459  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x1800a645e  mov     rdx, rax
0x1800a6461  lea     r8, [rbp+57h+var_A0]
0x1800a6465  lea     rcx, [rbp+57h+var_40]
0x1800a6469  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x1800a646e  mov     r8, rax
0x1800a6471  mov     rdx, [rdi]
0x1800a6474  lea     rcx, [rbp+57h+var_D0]
0x1800a6478  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800a647d  nop
0x1800a647e  lea     rcx, [rsp+110h+var_E0]
0x1800a6483  call    ?GetHeight@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetHeight(void)
0x1800a6488  movaps  xmm1, xmm0
0x1800a648b  lea     rcx, [rsp+110h+var_E0]
0x1800a6490  call    ?GetWidth@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetWidth(void)
0x1800a6495  mov     [rsp+110h+var_E8], 1
0x1800a649d  movss   [rsp+110h+var_F0], xmm1
0x1800a64a3  movaps  xmm3, xmm0
0x1800a64a6  movss   xmm2, dword ptr [rsp+110h+var_E0+4]
0x1800a64ac  movss   xmm1, dword ptr [rsp+110h+var_E0]
0x1800a64b2  mov     rcx, [rdi]
0x1800a64b5  call    cs:__imp_GdipSetClipRect
0x1800a64bb  mov     r9d, 2511897h
0x1800a64c1  mov     ecx, eax
0x1800a64c3  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a64c8  nop
0x1800a64c9  jmp     loc_1800A6680
0x1800a64ce  lea     rax, [rsp+110h+var_E0]
0x1800a64d3  add     rsi, 20h ; ' '
0x1800a64d7  mov     ecx, 4
0x1800a64dc  movsd   xmm0, qword ptr [rsi]
0x1800a64e0  cvtpd2ps xmm0, xmm0
0x1800a64e4  movss   dword ptr [rax], xmm0
0x1800a64e8  lea     rsi, [rsi+8]
0x1800a64ec  lea     rax, [rax+4]
0x1800a64f0  sub     rcx, 1
0x1800a64f4  jnz     short loc_1800A64DC
0x1800a64f6  mov     rcx, rdi; this
0x1800a64f9  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800a64fe  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800a6501  mov     rcx, rax; this
0x1800a6504  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800a6509  lea     r8, [rdi+8]
0x1800a650d  mov     rdx, [rdi]
0x1800a6510  lea     rcx, [rbp+57h+var_D0]
0x1800a6514  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800a6519  nop
0x1800a651a  lea     rcx, [rsp+110h+var_E0]
0x1800a651f  call    ?GetHeight@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetHeight(void)
0x1800a6524  movaps  xmm1, xmm0
0x1800a6527  lea     rcx, [rsp+110h+var_E0]
0x1800a652c  call    ?GetWidth@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetWidth(void)
0x1800a6531  mov     [rsp+110h+var_E8], 1
0x1800a6539  movss   [rsp+110h+var_F0], xmm1
0x1800a653f  movaps  xmm3, xmm0
0x1800a6542  movss   xmm2, dword ptr [rsp+110h+var_E0+4]
0x1800a6548  movss   xmm1, dword ptr [rsp+110h+var_E0]
0x1800a654e  mov     rcx, [rdi]
0x1800a6551  call    cs:__imp_GdipSetClipRect
0x1800a6557  mov     r9d, 2511896h
0x1800a655d  mov     ecx, eax
0x1800a655f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a6564  nop
0x1800a6565  jmp     loc_1800A6680
0x1800a656a  lea     rdx, [rbp+57h+var_D0]
0x1800a656e  mov     rcx, [rsi]
0x1800a6571  call    ?GetLogicalBounds@Frame@ITarget@Gfx@@QEBA?AV?$TConvertibleRectPx@H@3@XZ; Gfx::ITarget::Frame::GetLogicalBounds(void)
  ... truncated ...
```
