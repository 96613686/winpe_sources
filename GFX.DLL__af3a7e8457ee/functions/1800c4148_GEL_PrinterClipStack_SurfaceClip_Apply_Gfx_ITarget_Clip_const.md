# GEL::PrinterClipStack::SurfaceClip::Apply(Gfx::ITarget::Clip const &)

- ea: `0x1800c4148`
- end: `0x1800c4739`
- name: `?Apply@SurfaceClip@PrinterClipStack@GEL@@QEAAXAEBVClip@ITarget@Gfx@@@Z`
- size: `1521`
- prototype: `void __fastcall(GEL::PrinterClipStack::SurfaceClip *__hidden this, const struct Gfx::ITarget::Clip *)`
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x1800c2420`
- `0x1800c4080`

## callees

- `0x18002cc00`
- `0x1800502bc`
- `0x1800510b4`
- `0x1800573f0`
- `0x1800614d8`
- `0x180061a74`
- `0x180062394`
- `0x180065a50`
- `0x180066720`
- `0x180066750`
- `0x1800bff78`
- `0x1800c4148`
- `0x1801219dc`
- `0x1801590f8`
- `0x180163760`
- `0x180163a64`
- `0x18016f96c`
- `0x1801c949c`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800c4720`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800c4720`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c4265`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c42af`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c432c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c4399`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c4265`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c42af`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c432c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c4399`
- `gdiplus!GdipSetClipRectI` at `0x1800c46fb`
- `gdiplus!GdipSetClipRectI` at `0x1800c46fb`
- `gdiplus!GdipSetClipPath` at `0x1800c4285`
- `gdiplus!GdipSetClipPath` at `0x1800c434c`
- `gdiplus!GdipSetClipPath` at `0x1800c4417`
- `gdiplus!GdipSetClipPath` at `0x1800c4471`
- `gdiplus!GdipSetClipPath` at `0x1800c4285`
- `gdiplus!GdipSetClipPath` at `0x1800c434c`
- `gdiplus!GdipSetClipPath` at `0x1800c4417`
- `gdiplus!GdipSetClipPath` at `0x1800c4471`
- `gdiplus!GdipSetClipRect` at `0x1800c4545`
- `gdiplus!GdipSetClipRect` at `0x1800c45e1`
- `gdiplus!GdipSetClipRect` at `0x1800c4545`
- `gdiplus!GdipSetClipRect` at `0x1800c45e1`

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
0x1800c4148  mov     [rsp-8+arg_8], rbx
0x1800c414d  push    rbp
0x1800c414e  push    rsi
0x1800c414f  push    rdi
0x1800c4150  lea     rbp, [rsp-47h]
0x1800c4155  sub     rsp, 100h
0x1800c415c  mov     rsi, rdx
0x1800c415f  mov     rdi, rcx
0x1800c4162  cmp     qword ptr [rcx], 0
0x1800c4166  jnz     short loc_1800C4172
0x1800c4168  mov     ecx, 16CB046h
0x1800c416d  jmp     loc_1800C4720
0x1800c4172  mov     ecx, [rdx+18h]
0x1800c4175  test    ecx, ecx
0x1800c4177  jz      loc_1800C471B
0x1800c417d  sub     ecx, 1
0x1800c4180  jz      loc_1800C45FA
0x1800c4186  sub     ecx, 1
0x1800c4189  jz      loc_1800C455E
0x1800c418f  sub     ecx, 1
0x1800c4192  jz      loc_1800C448F
0x1800c4198  sub     ecx, 1
0x1800c419b  jz      loc_1800C442D
0x1800c41a1  sub     ecx, 1
0x1800c41a4  jz      loc_1800C43A0
0x1800c41aa  sub     ecx, 1
0x1800c41ad  jz      loc_1800C42B6
0x1800c41b3  cmp     ecx, 1
0x1800c41b6  jnz     loc_1800C4726
0x1800c41bc  mov     [rbp+57h+arg_0], 0
0x1800c41c4  mov     rcx, rsi; this
0x1800c41c7  call    ?GetClipGeometry@Clip@ITarget@Gfx@@QEBAAEBUIGeometry@ARC@@XZ; Gfx::ITarget::Clip::GetClipGeometry(void)
0x1800c41cc  mov     r9, rax
0x1800c41cf  mov     rcx, [rax]
0x1800c41d2  mov     rax, [rcx+10h]
0x1800c41d6  lea     r8, [rbp+57h+arg_0]
0x1800c41da  lea     rdx, _GUID_b9e550ba_696b_4605_ba63_041cafec3d57
0x1800c41e1  mov     rcx, r9
0x1800c41e4  call    cs:__guard_dispatch_icall_fptr
0x1800c41ea  test    al, al
0x1800c41ec  jz      loc_1800C42A8
0x1800c41f2  cmp     [rbp+57h+arg_0], 0
0x1800c41f7  jz      loc_1800C42A8
0x1800c41fd  mov     rcx, rdi; this
0x1800c4200  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800c4205  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800c4208  mov     rcx, rax; this
0x1800c420b  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800c4210  movups  xmm0, xmmword ptr [rdi+8]
0x1800c4214  movups  [rbp+57h+var_D0], xmm0
0x1800c4218  movups  xmm1, xmmword ptr [rdi+18h]
0x1800c421c  movups  [rbp+57h+var_C0], xmm1
0x1800c4220  movups  xmm0, xmmword ptr [rdi+28h]
0x1800c4224  movups  [rbp+57h+var_B0], xmm0
0x1800c4228  lea     rdx, [rbp+57h+var_A0]
0x1800c422c  mov     rcx, rsi
0x1800c422f  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x1800c4234  mov     rdx, rax
0x1800c4237  lea     r8, [rbp+57h+var_D0]
0x1800c423b  lea     rcx, [rbp+57h+var_70]
0x1800c423f  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x1800c4244  mov     r8, rax
0x1800c4247  mov     rdx, [rdi]
0x1800c424a  lea     rcx, [rsp+110h+var_E0]
0x1800c424f  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800c4254  nop
0x1800c4255  mov     rcx, [rbp+57h+arg_0]
0x1800c4259  test    rcx, rcx
0x1800c425c  jnz     short loc_1800C426C
0x1800c425e  xor     edx, edx
0x1800c4260  mov     ecx, 1E3C3840h
0x1800c4265  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800c426b  nop
0x1800c426c  mov     rax, [rcx]
0x1800c426f  mov     rax, [rax+10h]
0x1800c4273  call    cs:__guard_dispatch_icall_fptr
0x1800c4279  mov     r8d, 1
0x1800c427f  mov     rdx, rax
0x1800c4282  mov     rcx, [rdi]
0x1800c4285  call    cs:__imp_GdipSetClipPath
0x1800c428b  mov     r9d, 2511899h
0x1800c4291  mov     ecx, eax
0x1800c4293  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c4298  nop
0x1800c4299  lea     rcx, [rsp+110h+var_E0]; this
0x1800c429e  call    ??1GpWorldTransformRestorer@Gfx@@QEAA@XZ; Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer(void)
0x1800c42a3  jmp     loc_1800C436B
0x1800c42a8  xor     edx, edx
0x1800c42aa  mov     ecx, 1E082311h
0x1800c42af  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800c42b5  nop
0x1800c42b6  mov     [rbp+57h+arg_0], 0
0x1800c42be  mov     rcx, rsi; this
0x1800c42c1  call    ?GetClipGeometry@Clip@ITarget@Gfx@@QEBAAEBUIGeometry@ARC@@XZ; Gfx::ITarget::Clip::GetClipGeometry(void)
0x1800c42c6  mov     r9, rax
0x1800c42c9  mov     rcx, [rax]
0x1800c42cc  mov     rax, [rcx+10h]
0x1800c42d0  lea     r8, [rbp+57h+arg_0]
0x1800c42d4  lea     rdx, _GUID_b9e550ba_696b_4605_ba63_041cafec3d57
0x1800c42db  mov     rcx, r9
0x1800c42de  call    cs:__guard_dispatch_icall_fptr
0x1800c42e4  test    al, al
0x1800c42e6  jz      loc_1800C4392
0x1800c42ec  cmp     [rbp+57h+arg_0], 0
0x1800c42f1  jz      loc_1800C4392
0x1800c42f7  mov     rcx, rdi; this
0x1800c42fa  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800c42ff  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800c4302  mov     rcx, rax; this
0x1800c4305  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800c430a  lea     r8, [rdi+8]
0x1800c430e  mov     rdx, [rdi]
0x1800c4311  lea     rcx, [rsp+110h+var_E0]
0x1800c4316  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800c431b  nop
0x1800c431c  mov     rcx, [rbp+57h+arg_0]
0x1800c4320  test    rcx, rcx
0x1800c4323  jnz     short loc_1800C4333
0x1800c4325  xor     edx, edx
0x1800c4327  mov     ecx, 1E3C3840h
0x1800c432c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800c4332  nop
0x1800c4333  mov     rax, [rcx]
0x1800c4336  mov     rax, [rax+10h]
0x1800c433a  call    cs:__guard_dispatch_icall_fptr
0x1800c4340  mov     r8d, 1
0x1800c4346  mov     rdx, rax
0x1800c4349  mov     rcx, [rdi]
0x1800c434c  call    cs:__imp_GdipSetClipPath
0x1800c4352  mov     r9d, 2511898h
0x1800c4358  mov     ecx, eax
0x1800c435a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c435f  nop
0x1800c4360  lea     rcx, [rsp+110h+var_E0]; this
0x1800c4365  call    ??1GpWorldTransformRestorer@Gfx@@QEAA@XZ; Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer(void)
0x1800c436a  nop
0x1800c436b  mov     rcx, [rbp+57h+arg_0]
0x1800c436f  test    rcx, rcx
0x1800c4372  jz      loc_1800C4726
0x1800c4378  mov     [rbp+57h+arg_0], 0
0x1800c4380  mov     rax, [rcx]
0x1800c4383  mov     rax, [rax+8]
0x1800c4387  call    cs:__guard_dispatch_icall_fptr
0x1800c438d  jmp     loc_1800C4726
0x1800c4392  xor     edx, edx
0x1800c4394  mov     ecx, 1E082312h
0x1800c4399  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800c439f  nop
0x1800c43a0  mov     rcx, rsi; this
0x1800c43a3  call    ?GetClipPath@Clip@ITarget@Gfx@@QEBAAEBUIPath@GEL@@XZ; Gfx::ITarget::Clip::GetClipPath(void)
0x1800c43a8  mov     rbx, rax
0x1800c43ab  mov     rcx, rdi; this
0x1800c43ae  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800c43b3  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800c43b6  mov     rcx, rax; this
0x1800c43b9  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800c43be  movups  xmm0, xmmword ptr [rdi+8]
0x1800c43c2  movups  [rbp+57h+var_D0], xmm0
0x1800c43c6  movups  xmm1, xmmword ptr [rdi+18h]
0x1800c43ca  movups  [rbp+57h+var_C0], xmm1
0x1800c43ce  movups  xmm0, xmmword ptr [rdi+28h]
0x1800c43d2  movups  [rbp+57h+var_B0], xmm0
0x1800c43d6  lea     rdx, [rbp+57h+var_70]
0x1800c43da  mov     rcx, rsi
0x1800c43dd  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x1800c43e2  mov     rdx, rax
0x1800c43e5  lea     r8, [rbp+57h+var_D0]
0x1800c43e9  lea     rcx, [rbp+57h+var_A0]
0x1800c43ed  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x1800c43f2  mov     r8, rax
0x1800c43f5  mov     rdx, [rdi]
0x1800c43f8  lea     rcx, [rsp+110h+var_E0]
0x1800c43fd  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800c4402  nop
0x1800c4403  mov     rcx, rbx; this
0x1800c4406  call    ?PathToGpPath@GEL@@YAAEBVGpPath@Gdiplus@@AEBUIPath@1@@Z; GEL::PathToGpPath(GEL::IPath const &)
0x1800c440b  mov     r8d, 1
0x1800c4411  mov     rdx, rax
0x1800c4414  mov     rcx, [rdi]
0x1800c4417  call    cs:__imp_GdipSetClipPath
0x1800c441d  mov     r9d, 2511899h
0x1800c4423  mov     ecx, eax
0x1800c4425  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c442a  nop
0x1800c442b  jmp     short loc_1800C4485
0x1800c442d  mov     rcx, rsi; this
0x1800c4430  call    ?GetClipPath@Clip@ITarget@Gfx@@QEBAAEBUIPath@GEL@@XZ; Gfx::ITarget::Clip::GetClipPath(void)
0x1800c4435  mov     rbx, rax
0x1800c4438  mov     rcx, rdi; this
0x1800c443b  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800c4440  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800c4443  mov     rcx, rax; this
0x1800c4446  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800c444b  lea     r8, [rdi+8]
0x1800c444f  mov     rdx, [rdi]
0x1800c4452  lea     rcx, [rsp+110h+var_E0]
0x1800c4457  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800c445c  nop
0x1800c445d  mov     rcx, rbx; this
0x1800c4460  call    ?PathToGpPath@GEL@@YAAEBVGpPath@Gdiplus@@AEBUIPath@1@@Z; GEL::PathToGpPath(GEL::IPath const &)
0x1800c4465  mov     r8d, 1
0x1800c446b  mov     rdx, rax
0x1800c446e  mov     rcx, [rdi]
0x1800c4471  call    cs:__imp_GdipSetClipPath
0x1800c4477  mov     r9d, 2511898h
0x1800c447d  mov     ecx, eax
0x1800c447f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c4484  nop
0x1800c4485  lea     rcx, [rsp+110h+var_E0]
0x1800c448a  jmp     loc_1800C4714
0x1800c448f  lea     rax, [rsp+110h+var_E0]
0x1800c4494  lea     rcx, [rdx+20h]
0x1800c4498  mov     edx, 4
0x1800c449d  movsd   xmm0, qword ptr [rcx]
0x1800c44a1  cvtpd2ps xmm0, xmm0
0x1800c44a5  movss   dword ptr [rax], xmm0
0x1800c44a9  lea     rcx, [rcx+8]
0x1800c44ad  lea     rax, [rax+4]
0x1800c44b1  sub     rdx, 1
0x1800c44b5  jnz     short loc_1800C449D
0x1800c44b7  mov     rcx, rdi; this
0x1800c44ba  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800c44bf  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800c44c2  mov     rcx, rax; this
0x1800c44c5  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800c44ca  movups  xmm0, xmmword ptr [rdi+8]
0x1800c44ce  movups  [rbp+57h+var_A0], xmm0
0x1800c44d2  movups  xmm1, xmmword ptr [rdi+18h]
0x1800c44d6  movups  [rbp+57h+var_90], xmm1
0x1800c44da  movups  xmm0, xmmword ptr [rdi+28h]
0x1800c44de  movups  [rbp+57h+var_80], xmm0
0x1800c44e2  lea     rdx, [rbp+57h+var_70]
0x1800c44e6  mov     rcx, rsi
0x1800c44e9  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x1800c44ee  mov     rdx, rax
0x1800c44f1  lea     r8, [rbp+57h+var_A0]
0x1800c44f5  lea     rcx, [rbp+57h+var_40]
0x1800c44f9  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x1800c44fe  mov     r8, rax
0x1800c4501  mov     rdx, [rdi]
0x1800c4504  lea     rcx, [rbp+57h+var_D0]
0x1800c4508  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800c450d  nop
0x1800c450e  lea     rcx, [rsp+110h+var_E0]
0x1800c4513  call    ?GetHeight@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetHeight(void)
0x1800c4518  movaps  xmm1, xmm0
0x1800c451b  lea     rcx, [rsp+110h+var_E0]
0x1800c4520  call    ?GetWidth@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetWidth(void)
0x1800c4525  mov     [rsp+110h+var_E8], 1
0x1800c452d  movss   [rsp+110h+var_F0], xmm1
0x1800c4533  movaps  xmm3, xmm0
0x1800c4536  movss   xmm2, dword ptr [rsp+110h+var_E0+4]
0x1800c453c  movss   xmm1, dword ptr [rsp+110h+var_E0]
0x1800c4542  mov     rcx, [rdi]
0x1800c4545  call    cs:__imp_GdipSetClipRect
0x1800c454b  mov     r9d, 2511897h
0x1800c4551  mov     ecx, eax
0x1800c4553  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c4558  nop
0x1800c4559  jmp     loc_1800C4710
0x1800c455e  lea     rax, [rsp+110h+var_E0]
0x1800c4563  add     rsi, 20h ; ' '
0x1800c4567  mov     ecx, 4
0x1800c456c  movsd   xmm0, qword ptr [rsi]
0x1800c4570  cvtpd2ps xmm0, xmm0
0x1800c4574  movss   dword ptr [rax], xmm0
0x1800c4578  lea     rsi, [rsi+8]
0x1800c457c  lea     rax, [rax+4]
0x1800c4580  sub     rcx, 1
0x1800c4584  jnz     short loc_1800C456C
0x1800c4586  mov     rcx, rdi; this
0x1800c4589  call    ?GetUnusedClipHolder@SurfaceClip@PrinterClipStack@GEL@@QEAAAEAVGpClipHolder@Gfx@@XZ; GEL::PrinterClipStack::SurfaceClip::GetUnusedClipHolder(void)
0x1800c458e  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800c4591  mov     rcx, rax; this
0x1800c4594  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800c4599  lea     r8, [rdi+8]
0x1800c459d  mov     rdx, [rdi]
0x1800c45a0  lea     rcx, [rbp+57h+var_D0]
0x1800c45a4  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x1800c45a9  nop
0x1800c45aa  lea     rcx, [rsp+110h+var_E0]
0x1800c45af  call    ?GetHeight@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetHeight(void)
0x1800c45b4  movaps  xmm1, xmm0
0x1800c45b7  lea     rcx, [rsp+110h+var_E0]
0x1800c45bc  call    ?GetWidth@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetWidth(void)
0x1800c45c1  mov     [rsp+110h+var_E8], 1
0x1800c45c9  movss   [rsp+110h+var_F0], xmm1
0x1800c45cf  movaps  xmm3, xmm0
0x1800c45d2  movss   xmm2, dword ptr [rsp+110h+var_E0+4]
0x1800c45d8  movss   xmm1, dword ptr [rsp+110h+var_E0]
0x1800c45de  mov     rcx, [rdi]
0x1800c45e1  call    cs:__imp_GdipSetClipRect
0x1800c45e7  mov     r9d, 2511896h
0x1800c45ed  mov     ecx, eax
0x1800c45ef  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c45f4  nop
0x1800c45f5  jmp     loc_1800C4710
0x1800c45fa  lea     rdx, [rbp+57h+var_D0]
0x1800c45fe  mov     rcx, [rsi]
0x1800c4601  call    ?GetLogicalBounds@Frame@ITarget@Gfx@@QEBA?AV?$TConvertibleRectPx@H@3@XZ; Gfx::ITarget::Frame::GetLogicalBounds(void)
  ... truncated ...
```
