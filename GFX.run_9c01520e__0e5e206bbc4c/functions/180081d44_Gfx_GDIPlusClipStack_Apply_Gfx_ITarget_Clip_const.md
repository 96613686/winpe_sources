# Gfx::GDIPlusClipStack::Apply(Gfx::ITarget::Clip const &)

- ea: `0x180081d44`
- end: `0x180082265`
- name: `?Apply@GDIPlusClipStack@Gfx@@QEAAXAEBVClip@ITarget@2@@Z`
- size: `1313`
- prototype: `void __fastcall(Gfx::GDIPlusClipStack *__hidden this, const struct Gfx::ITarget::Clip *)`
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x180081c40`
- `0x180081c8c`

## callees

- `0x18002d050`
- `0x180052528`
- `0x180057e70`
- `0x18006e578`
- `0x18006e604`
- `0x18007ef58`
- `0x18007f754`
- `0x180080644`
- `0x180081d44`
- `0x180083478`
- `0x180099b00`
- `0x18011d5a0`
- `0x18015aaa8`
- `0x18015d388`
- `0x180166ff0`
- `0x180179988`
- `0x1801ce13c`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180081d71`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180082246`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180081d71`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180082246`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180081e51`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180081e9a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180081f01`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180081f5f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180081e51`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180081e9a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180081f01`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180081f5f`
- `gdiplus!GdipSetClipRectI` at `0x180082222`
- `gdiplus!GdipSetClipRectI` at `0x180082222`
- `gdiplus!GdipSetClipPath` at `0x180081e71`
- `gdiplus!GdipSetClipPath` at `0x180081f21`
- `gdiplus!GdipSetClipPath` at `0x180081fb8`
- `gdiplus!GdipSetClipPath` at `0x18008200b`
- `gdiplus!GdipSetClipPath` at `0x180081e71`
- `gdiplus!GdipSetClipPath` at `0x180081f21`
- `gdiplus!GdipSetClipPath` at `0x180081fb8`
- `gdiplus!GdipSetClipPath` at `0x18008200b`
- `gdiplus!GdipSetClipRect` at `0x1800820a9`
- `gdiplus!GdipSetClipRect` at `0x180082133`
- `gdiplus!GdipSetClipRect` at `0x1800820a9`
- `gdiplus!GdipSetClipRect` at `0x180082133`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Gfx::GDIPlusClipStack::Apply(Gfx::GDIPlusClipStack *this, const struct Gfx::ITarget::Clip *a2)
{
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  const struct ARC::IGeometry *ClipGeometry; // rax
  __int64 LocalToDeviceTransform; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  const struct ARC::IGeometry *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rcx
  GEL *ClipPath; // rbx
  __int64 v26; // rax
  const struct GEL::IPath *v27; // rdx
  const struct Gdiplus::GpPath *v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  Gfx::GpWorldTransformRestorer *v32; // rcx
  GEL *v33; // rbx
  const struct GEL::IPath *v34; // rdx
  const struct Gdiplus::GpPath *v35; // rax
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  float *v40; // rax
  double *v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rax
  unsigned int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // r8
  float *v47; // rax
  double *v48; // rsi
  __int64 v49; // rcx
  __m128i v50; // xmm0
  char v51; // al
  unsigned int *Height; // rax
  __int64 v53; // r8
  unsigned int *Width; // rax
  int v55; // r9d
  unsigned int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r8
  __m128i v59; // [rsp+30h] [rbp-49h] BYREF
  Gfx::GDIPlusClipStack *v60; // [rsp+40h] [rbp-39h]
  Gfx::GpClipHolder *UnusedClipHolder; // [rsp+48h] [rbp-31h]
  char v62; // [rsp+50h] [rbp-29h]
  _BYTE v63[48]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v64[56]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v65; // [rsp+E0h] [rbp+67h] BYREF
  char v66; // [rsp+F0h] [rbp+77h] BYREF

  if ( !*(_QWORD *)this )
  {
    MsoShipAssertTagProc(1884303);
    return;
  }
  v60 = this;
  UnusedClipHolder = 0;
  v62 = 0;
  v4 = *((_DWORD *)a2 + 6);
  if ( !v4 )
  {
    MsoShipAssertTagProc(1884305);
    return;
  }
  v5 = v4 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( !v6 )
    {
      v47 = (float *)&v59;
      v48 = (double *)((char *)a2 + 32);
      v49 = 4;
      do
      {
        *v47++ = *v48++;
        --v49;
      }
      while ( v49 );
      UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
      Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
      Math::TRect<float>::GetHeight(&v59);
      Math::TRect<float>::GetWidth(&v59);
      v36 = GdipSetClipRect(*(_QWORD *)this);
      v39 = 38901318;
      goto LABEL_33;
    }
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
            if ( v10 != 1 )
              return;
            v65 = 0;
            ClipGeometry = Gfx::ITarget::Clip::GetClipGeometry(a2);
            if ( (*(unsigned __int8 (__fastcall **)(const struct ARC::IGeometry *, GUID *, __int64 *))(*(_QWORD *)ClipGeometry + 16LL))(
                   ClipGeometry,
                   &GUID_b9e550ba_696b_4605_ba63_041cafec3d57,
                   &v65)
              && v65 )
            {
              UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
              Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
              LocalToDeviceTransform = Gfx::ITarget::Clip::GetLocalToDeviceTransform(a2, v63);
              Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v59, *(_QWORD *)this, LocalToDeviceTransform);
              v13 = v65;
              if ( !v65 )
                CrashWithRecovery(0x1E3C3840u, 0);
              v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              v15 = GdipSetClipPath(*(_QWORD *)this, v14, 1);
              Gfx::GdipStatus_ThrowOnFailureMessageTag(v15, v16, v17, 38901321);
              Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer((Gfx::GpWorldTransformRestorer *)&v59);
LABEL_22:
              v24 = v65;
              if ( v65 )
              {
                v65 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
              }
              return;
            }
            CrashWithRecovery(0x1E082313u, 0);
          }
          v65 = 0;
          v18 = Gfx::ITarget::Clip::GetClipGeometry(a2);
          if ( (*(unsigned __int8 (__fastcall **)(const struct ARC::IGeometry *, GUID *, __int64 *))(*(_QWORD *)v18 + 16LL))(
                 v18,
                 &GUID_b9e550ba_696b_4605_ba63_041cafec3d57,
                 &v65)
            && v65 )
          {
            UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
            Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
            v19 = v65;
            if ( !v65 )
              CrashWithRecovery(0x1E3C3840u, 0);
            v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            v21 = GdipSetClipPath(*(_QWORD *)this, v20, 1);
            Gfx::GdipStatus_ThrowOnFailureMessageTag(v21, v22, v23, 38901320);
            goto LABEL_22;
          }
          CrashWithRecovery(0x1E082314u, 0);
        }
        ClipPath = Gfx::ITarget::Clip::GetClipPath(a2);
        UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
        Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
        v26 = Gfx::ITarget::Clip::GetLocalToDeviceTransform(a2, v63);
        Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v59, *(_QWORD *)this, v26);
        v28 = GEL::PathToGpPath(ClipPath, v27);
        v29 = GdipSetClipPath(*(_QWORD *)this, v28, 1);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v29, v30, v31, 38901321);
        v32 = (Gfx::GpWorldTransformRestorer *)&v59;
LABEL_42:
        Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer(v32);
        return;
      }
      v33 = Gfx::ITarget::Clip::GetClipPath(a2);
      UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
      Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
      v35 = GEL::PathToGpPath(v33, v34);
      v36 = GdipSetClipPath(*(_QWORD *)this, v35, 1);
      v39 = 38901320;
LABEL_33:
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v36, v37, v38, v39);
      return;
    }
    v40 = (float *)&v59;
    v41 = (double *)((char *)a2 + 32);
    v42 = 4;
    do
    {
      *v40++ = *v41++;
      --v42;
    }
    while ( v42 );
    UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
    Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
    v43 = Gfx::ITarget::Clip::GetLocalToDeviceTransform(a2, v64);
    Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(v63, *(_QWORD *)this, v43);
    Math::TRect<float>::GetHeight(&v59);
    Math::TRect<float>::GetWidth(&v59);
    v44 = GdipSetClipRect(*(_QWORD *)this);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v44, v45, v46, 38901319);
LABEL_41:
    v32 = (Gfx::GpWorldTransformRestorer *)v63;
    goto LABEL_42;
  }
  v50 = *(__m128i *)Gfx::ITarget::Frame::GetLogicalBounds(*(_QWORD *)a2, v63);
  v59 = v50;
  if ( *((_BYTE *)this + 28) )
  {
    if ( !*((_QWORD *)a2 + 1) )
    {
      if ( *((_DWORD *)a2 + 6) )
      {
        *(double *)v50.m128i_i64 = Math::TRect<int>::IsDegenerate(&v59);
        if ( v51
          || v50.m128i_i64[0] != 0x8000000080000000uLL
          || _mm_srli_si128(v50, 8).m128i_u64[0] != 0x7FFFFFFF7FFFFFFFLL )
        {
          UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
          Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
          Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(v63, *(_QWORD *)this, *(_QWORD *)a2 + 96LL);
          Height = (unsigned int *)Math::TRect<Math::TUnits<int,Math::DevicePixels>>::GetHeight(&v59, &v65);
          Width = (unsigned int *)Math::TRect<Math::TUnits<int,Math::DevicePixels>>::GetWidth(&v59, &v66, v53, *Height);
          v56 = GdipSetClipRectI(
                  *(_QWORD *)this,
                  v50.m128i_u32[0],
                  v59.m128i_u32[1],
                  *Width,
                  v55,
                  1,
                  v59.m128i_i64[0],
                  v59.m128i_i64[1]);
          Gfx::GdipStatus_ThrowOnFailureMessageTag(v56, v57, v58, 38901322);
          goto LABEL_41;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180081d44  mov     [rsp-8+arg_8], rbx
0x180081d49  mov     [rsp-8+arg_18], rsi
0x180081d4e  push    rbp
0x180081d4f  push    rdi
0x180081d50  push    r14
0x180081d52  lea     rbp, [rsp-47h]
0x180081d57  sub     rsp, 0C0h
0x180081d5e  mov     rsi, rdx
0x180081d61  mov     rdi, rcx
0x180081d64  xor     r14d, r14d
0x180081d67  cmp     [rcx], r14
0x180081d6a  jnz     short loc_180081D7C
0x180081d6c  mov     ecx, 1CC08Fh
0x180081d71  call    cs:__imp_MsoShipAssertTagProc
0x180081d77  jmp     loc_18008224D
0x180081d7c  mov     [rbp+57h+var_90], rdi
0x180081d80  mov     [rbp+57h+var_88], r14
0x180081d84  mov     [rbp+57h+var_80], r14b
0x180081d88  mov     ecx, [rdx+18h]
0x180081d8b  test    ecx, ecx
0x180081d8d  jz      loc_180082241
0x180081d93  sub     ecx, 1
0x180081d96  jz      loc_18008214B
0x180081d9c  sub     ecx, 1
0x180081d9f  jz      loc_1800820C2
0x180081da5  sub     ecx, 1
0x180081da8  jz      loc_18008201C
0x180081dae  sub     ecx, 1
0x180081db1  jz      loc_180081FD5
0x180081db7  sub     ecx, 1
0x180081dba  jz      loc_180081F66
0x180081dc0  sub     ecx, 1
0x180081dc3  jz      loc_180081EA1
0x180081dc9  cmp     ecx, 1
0x180081dcc  jnz     loc_18008224D
0x180081dd2  mov     [rbp+57h+arg_0], r14
0x180081dd6  mov     rcx, rsi; this
0x180081dd9  call    ?GetClipGeometry@Clip@ITarget@Gfx@@QEBAAEBUIGeometry@ARC@@XZ; Gfx::ITarget::Clip::GetClipGeometry(void)
0x180081dde  mov     r9, rax
0x180081de1  mov     rcx, [rax]
0x180081de4  mov     rax, [rcx+10h]
0x180081de8  lea     r8, [rbp+57h+arg_0]
0x180081dec  lea     rdx, _GUID_b9e550ba_696b_4605_ba63_041cafec3d57
0x180081df3  mov     rcx, r9
0x180081df6  call    cs:__guard_dispatch_icall_fptr
0x180081dfc  test    al, al
0x180081dfe  jz      loc_180081E93
0x180081e04  cmp     [rbp+57h+arg_0], r14
0x180081e08  jz      loc_180081E93
0x180081e0e  mov     rcx, rdi; this
0x180081e11  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x180081e16  mov     [rbp+57h+var_88], rax
0x180081e1a  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x180081e1d  mov     rcx, rax; this
0x180081e20  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x180081e25  lea     rdx, [rbp+57h+var_78]
0x180081e29  mov     rcx, rsi
0x180081e2c  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x180081e31  mov     r8, rax
0x180081e34  mov     rdx, [rdi]
0x180081e37  lea     rcx, [rbp+57h+var_A0]
0x180081e3b  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x180081e40  nop
0x180081e41  mov     rcx, [rbp+57h+arg_0]
0x180081e45  test    rcx, rcx
0x180081e48  jnz     short loc_180081E58
0x180081e4a  xor     edx, edx
0x180081e4c  mov     ecx, 1E3C3840h
0x180081e51  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180081e57  nop
0x180081e58  mov     rax, [rcx]
0x180081e5b  mov     rax, [rax+10h]
0x180081e5f  call    cs:__guard_dispatch_icall_fptr
0x180081e65  mov     r8d, 1
0x180081e6b  mov     rdx, rax
0x180081e6e  mov     rcx, [rdi]
0x180081e71  call    cs:__imp_GdipSetClipPath
0x180081e77  mov     r9d, 2519649h
0x180081e7d  mov     ecx, eax
0x180081e7f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180081e84  nop
0x180081e85  lea     rcx, [rbp+57h+var_A0]; this
0x180081e89  call    ??1GpWorldTransformRestorer@Gfx@@QEAA@XZ; Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer(void)
0x180081e8e  jmp     loc_180081F35
0x180081e93  xor     edx, edx
0x180081e95  mov     ecx, 1E082313h
0x180081e9a  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180081ea0  nop
0x180081ea1  mov     [rbp+57h+arg_0], r14
0x180081ea5  mov     rcx, rsi; this
0x180081ea8  call    ?GetClipGeometry@Clip@ITarget@Gfx@@QEBAAEBUIGeometry@ARC@@XZ; Gfx::ITarget::Clip::GetClipGeometry(void)
0x180081ead  mov     r9, rax
0x180081eb0  mov     rcx, [rax]
0x180081eb3  mov     rax, [rcx+10h]
0x180081eb7  lea     r8, [rbp+57h+arg_0]
0x180081ebb  lea     rdx, _GUID_b9e550ba_696b_4605_ba63_041cafec3d57
0x180081ec2  mov     rcx, r9
0x180081ec5  call    cs:__guard_dispatch_icall_fptr
0x180081ecb  test    al, al
0x180081ecd  jz      loc_180081F58
0x180081ed3  cmp     [rbp+57h+arg_0], r14
0x180081ed7  jz      short loc_180081F58
0x180081ed9  mov     rcx, rdi; this
0x180081edc  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x180081ee1  mov     [rbp+57h+var_88], rax
0x180081ee5  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x180081ee8  mov     rcx, rax; this
0x180081eeb  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x180081ef0  nop
0x180081ef1  mov     rcx, [rbp+57h+arg_0]
0x180081ef5  test    rcx, rcx
0x180081ef8  jnz     short loc_180081F08
0x180081efa  xor     edx, edx
0x180081efc  mov     ecx, 1E3C3840h
0x180081f01  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180081f07  nop
0x180081f08  mov     rax, [rcx]
0x180081f0b  mov     rax, [rax+10h]
0x180081f0f  call    cs:__guard_dispatch_icall_fptr
0x180081f15  mov     r8d, 1
0x180081f1b  mov     rdx, rax
0x180081f1e  mov     rcx, [rdi]
0x180081f21  call    cs:__imp_GdipSetClipPath
0x180081f27  mov     r9d, 2519648h
0x180081f2d  mov     ecx, eax
0x180081f2f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180081f34  nop
0x180081f35  mov     rcx, [rbp+57h+arg_0]
0x180081f39  test    rcx, rcx
0x180081f3c  jz      loc_18008224D
0x180081f42  mov     [rbp+57h+arg_0], r14
0x180081f46  mov     rax, [rcx]
0x180081f49  mov     rax, [rax+8]
0x180081f4d  call    cs:__guard_dispatch_icall_fptr
0x180081f53  jmp     loc_18008224D
0x180081f58  xor     edx, edx
0x180081f5a  mov     ecx, 1E082314h
0x180081f5f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180081f65  nop
0x180081f66  mov     rcx, rsi; this
0x180081f69  call    ?GetClipPath@Clip@ITarget@Gfx@@QEBAAEBUIPath@GEL@@XZ; Gfx::ITarget::Clip::GetClipPath(void)
0x180081f6e  mov     rbx, rax
0x180081f71  mov     rcx, rdi; this
0x180081f74  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x180081f79  mov     [rbp+57h+var_88], rax
0x180081f7d  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x180081f80  mov     rcx, rax; this
0x180081f83  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x180081f88  lea     rdx, [rbp+57h+var_78]
0x180081f8c  mov     rcx, rsi
0x180081f8f  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x180081f94  mov     r8, rax
0x180081f97  mov     rdx, [rdi]
0x180081f9a  lea     rcx, [rbp+57h+var_A0]
0x180081f9e  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x180081fa3  nop
0x180081fa4  mov     rcx, rbx; this
0x180081fa7  call    ?PathToGpPath@GEL@@YAAEBVGpPath@Gdiplus@@AEBUIPath@1@@Z; GEL::PathToGpPath(GEL::IPath const &)
0x180081fac  mov     r8d, 1
0x180081fb2  mov     rdx, rax
0x180081fb5  mov     rcx, [rdi]
0x180081fb8  call    cs:__imp_GdipSetClipPath
0x180081fbe  mov     r9d, 2519649h
0x180081fc4  mov     ecx, eax
0x180081fc6  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180081fcb  nop
0x180081fcc  lea     rcx, [rbp+57h+var_A0]
0x180081fd0  jmp     loc_18008223A
0x180081fd5  mov     rcx, rsi; this
0x180081fd8  call    ?GetClipPath@Clip@ITarget@Gfx@@QEBAAEBUIPath@GEL@@XZ; Gfx::ITarget::Clip::GetClipPath(void)
0x180081fdd  mov     rbx, rax
0x180081fe0  mov     rcx, rdi; this
0x180081fe3  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x180081fe8  mov     [rbp+57h+var_88], rax
0x180081fec  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x180081fef  mov     rcx, rax; this
0x180081ff2  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x180081ff7  mov     rcx, rbx; this
0x180081ffa  call    ?PathToGpPath@GEL@@YAAEBVGpPath@Gdiplus@@AEBUIPath@1@@Z; GEL::PathToGpPath(GEL::IPath const &)
0x180081fff  mov     r8d, 1
0x180082005  mov     rdx, rax
0x180082008  mov     rcx, [rdi]
0x18008200b  call    cs:__imp_GdipSetClipPath
0x180082011  mov     r9d, 2519648h
0x180082017  jmp     loc_18008213F
0x18008201c  lea     rax, [rbp+57h+var_A0]
0x180082020  lea     rcx, [rdx+20h]
0x180082024  mov     edx, 4
0x180082029  movsd   xmm0, qword ptr [rcx]
0x18008202d  cvtpd2ps xmm0, xmm0
0x180082031  movss   dword ptr [rax], xmm0
0x180082035  lea     rcx, [rcx+8]
0x180082039  lea     rax, [rax+4]
0x18008203d  sub     rdx, 1
0x180082041  jnz     short loc_180082029
0x180082043  mov     rcx, rdi; this
0x180082046  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x18008204b  mov     [rbp+57h+var_88], rax
0x18008204f  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x180082052  mov     rcx, rax; this
0x180082055  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x18008205a  lea     rdx, [rbp+57h+var_48]
0x18008205e  mov     rcx, rsi
0x180082061  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x180082066  mov     r8, rax
0x180082069  mov     rdx, [rdi]
0x18008206c  lea     rcx, [rbp+57h+var_78]
0x180082070  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x180082075  nop
0x180082076  lea     rcx, [rbp+57h+var_A0]
0x18008207a  call    ?GetHeight@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetHeight(void)
0x18008207f  movaps  xmm1, xmm0
0x180082082  lea     rcx, [rbp+57h+var_A0]
0x180082086  call    ?GetWidth@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetWidth(void)
0x18008208b  mov     [rsp+0D0h+var_A8], 1
0x180082093  movss   [rsp+0D0h+var_B0], xmm1
0x180082099  movaps  xmm3, xmm0
0x18008209c  movss   xmm2, dword ptr [rbp+57h+var_A0+4]
0x1800820a1  movss   xmm1, dword ptr [rbp+57h+var_A0]
0x1800820a6  mov     rcx, [rdi]
0x1800820a9  call    cs:__imp_GdipSetClipRect
0x1800820af  mov     r9d, 2519647h
0x1800820b5  mov     ecx, eax
0x1800820b7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800820bc  nop
0x1800820bd  jmp     loc_180082236
0x1800820c2  lea     rax, [rbp+57h+var_A0]
0x1800820c6  add     rsi, 20h ; ' '
0x1800820ca  mov     ecx, 4
0x1800820cf  movsd   xmm0, qword ptr [rsi]
0x1800820d3  cvtpd2ps xmm0, xmm0
0x1800820d7  movss   dword ptr [rax], xmm0
0x1800820db  lea     rsi, [rsi+8]
0x1800820df  lea     rax, [rax+4]
0x1800820e3  sub     rcx, 1
0x1800820e7  jnz     short loc_1800820CF
0x1800820e9  mov     rcx, rdi; this
0x1800820ec  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x1800820f1  mov     [rbp+57h+var_88], rax
0x1800820f5  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800820f8  mov     rcx, rax; this
0x1800820fb  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x180082100  lea     rcx, [rbp+57h+var_A0]
0x180082104  call    ?GetHeight@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetHeight(void)
0x180082109  movaps  xmm1, xmm0
0x18008210c  lea     rcx, [rbp+57h+var_A0]
0x180082110  call    ?GetWidth@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetWidth(void)
0x180082115  mov     [rsp+0D0h+var_A8], 1
0x18008211d  movss   [rsp+0D0h+var_B0], xmm1
0x180082123  movaps  xmm3, xmm0
0x180082126  movss   xmm2, dword ptr [rbp+57h+var_A0+4]
0x18008212b  movss   xmm1, dword ptr [rbp+57h+var_A0]
0x180082130  mov     rcx, [rdi]
0x180082133  call    cs:__imp_GdipSetClipRect
0x180082139  mov     r9d, 2519646h
0x18008213f  mov     ecx, eax
0x180082141  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180082146  jmp     loc_18008224D
0x18008214b  lea     rdx, [rbp+57h+var_78]
0x18008214f  mov     rcx, [rsi]
0x180082152  call    ?GetLogicalBounds@Frame@ITarget@Gfx@@QEBA?AV?$TConvertibleRectPx@H@3@XZ; Gfx::ITarget::Frame::GetLogicalBounds(void)
0x180082157  movups  xmm0, xmmword ptr [rax]
0x18008215a  movups  [rbp+57h+var_A0], xmm0
0x18008215e  cmp     [rdi+1Ch], r14b
0x180082162  jz      loc_18008224D
0x180082168  cmp     [rsi+8], r14
0x18008216c  jnz     loc_18008224D
0x180082172  cmp     [rsi+18h], r14d
0x180082176  jz      loc_18008224D
0x18008217c  lea     rcx, [rbp+57h+var_A0]
0x180082180  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x180082185  movq    rbx, xmm0
0x18008218a  test    al, al
0x18008218c  jnz     short loc_1800821C1
0x18008218e  mov     ecx, 80000000h
0x180082193  cmp     ebx, ecx
0x180082195  jnz     short loc_1800821C1
0x180082197  mov     rax, rbx
0x18008219a  shr     rax, 20h
0x18008219e  cmp     eax, ecx
0x1800821a0  jnz     short loc_1800821C1
0x1800821a2  psrldq  xmm0, 8
0x1800821a7  movq    rax, xmm0
0x1800821ac  mov     ecx, 7FFFFFFFh
0x1800821b1  cmp     eax, ecx
0x1800821b3  jnz     short loc_1800821C1
0x1800821b5  shr     rax, 20h
0x1800821b9  cmp     eax, ecx
0x1800821bb  jz      loc_18008224D
0x1800821c1  mov     rcx, rdi; this
0x1800821c4  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x1800821c9  mov     [rbp+57h+var_88], rax
0x1800821cd  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800821d0  mov     rcx, rax; this
0x1800821d3  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800821d8  mov     r8, [rsi]
0x1800821db  add     r8, 60h ; '`'
0x1800821df  mov     rdx, [rdi]
0x1800821e2  lea     rcx, [rbp+57h+var_78]
0x1800821e6  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
  ... truncated ...
```
