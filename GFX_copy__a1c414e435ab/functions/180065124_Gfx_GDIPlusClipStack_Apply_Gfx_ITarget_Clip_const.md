# Gfx::GDIPlusClipStack::Apply(Gfx::ITarget::Clip const &)

- ea: `0x180065124`
- end: `0x1800656a2`
- name: `?Apply@GDIPlusClipStack@Gfx@@QEAAXAEBVClip@ITarget@2@@Z`
- size: `1406`
- prototype: `void __fastcall(Gfx::GDIPlusClipStack *__hidden this, const struct Gfx::ITarget::Clip *)`
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x180065020`
- `0x1800650d8`

## callees

- `0x1800502bc`
- `0x1800573f0`
- `0x180060904`
- `0x1800614d8`
- `0x18006151c`
- `0x180061a74`
- `0x180062394`
- `0x180065124`
- `0x180065a50`
- `0x180066720`
- `0x180066750`
- `0x1800bff78`
- `0x180138308`
- `0x1801590f8`
- `0x180163a64`
- `0x18016f96c`
- `0x1801c949c`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180065159`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18006567a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180065159`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18006567a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180065239`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180065282`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800652e9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180065347`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180065239`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180065282`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800652e9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180065347`
- `gdiplus!GdipSetClipRectI` at `0x180065648`
- `gdiplus!GdipSetClipRectI` at `0x180065648`
- `gdiplus!GdipSetClipPath` at `0x180065259`
- `gdiplus!GdipSetClipPath` at `0x180065309`
- `gdiplus!GdipSetClipPath` at `0x1800653a0`
- `gdiplus!GdipSetClipPath` at `0x1800653ef`
- `gdiplus!GdipSetClipPath` at `0x180065259`
- `gdiplus!GdipSetClipPath` at `0x180065309`
- `gdiplus!GdipSetClipPath` at `0x1800653a0`
- `gdiplus!GdipSetClipPath` at `0x1800653ef`
- `gdiplus!GdipSetClipRect` at `0x18006548d`
- `gdiplus!GdipSetClipRect` at `0x180065520`
- `gdiplus!GdipSetClipRect` at `0x18006548d`
- `gdiplus!GdipSetClipRect` at `0x180065520`
- `gdiplus!GdipSetWorldTransform` at `0x180065664`
- `gdiplus!GdipSetWorldTransform` at `0x180065664`

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
  __int64 v12; // rax
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
  GEL *v32; // rbx
  const struct GEL::IPath *v33; // rdx
  const struct Gdiplus::GpPath *v34; // rax
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  float *v39; // rax
  double *v40; // rcx
  __int64 v41; // rdx
  __int64 LocalToDeviceTransform; // rax
  unsigned int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  float *v46; // rax
  double *v47; // rsi
  __int64 v48; // rcx
  __m128i v49; // xmm6
  char v50; // al
  char v51; // r15
  unsigned __int64 v52; // xmm0_8
  double *v53; // rax
  float *v54; // rcx
  __int64 v55; // r8
  int v56; // eax
  unsigned int v57; // ebx
  unsigned int v58; // eax
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // [rsp+38h] [rbp-49h] BYREF
  __int64 v62; // [rsp+40h] [rbp-41h] BYREF
  __m128i v63; // [rsp+48h] [rbp-39h] BYREF
  Gfx::GDIPlusClipStack *v64; // [rsp+58h] [rbp-29h]
  Gfx::GpClipHolder *UnusedClipHolder; // [rsp+60h] [rbp-21h]
  char v66; // [rsp+68h] [rbp-19h]
  _BYTE v67[72]; // [rsp+70h] [rbp-11h] BYREF
  __int64 v68; // [rsp+E8h] [rbp+67h] BYREF

  if ( !*(_QWORD *)this )
  {
    MsoShipAssertTagProc(1884303);
    return;
  }
  v64 = this;
  UnusedClipHolder = 0;
  v66 = 0;
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
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( !v7 )
      {
        v39 = (float *)&v61;
        v40 = (double *)((char *)a2 + 32);
        v41 = 4;
        do
        {
          *v39++ = *v40++;
          --v41;
        }
        while ( v41 );
        UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
        Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
        LocalToDeviceTransform = Gfx::ITarget::Clip::GetLocalToDeviceTransform(a2, v67);
        Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v63, *(_QWORD *)this, LocalToDeviceTransform);
        Math::TRect<float>::GetHeight(&v61);
        Math::TRect<float>::GetWidth(&v61);
        v43 = GdipSetClipRect(*(_QWORD *)this);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v43, v44, v45, 38901319);
        goto LABEL_30;
      }
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
            v68 = 0;
            ClipGeometry = Gfx::ITarget::Clip::GetClipGeometry(a2);
            if ( (*(unsigned __int8 (__fastcall **)(const struct ARC::IGeometry *, GUID *, __int64 *))(*(_QWORD *)ClipGeometry + 16LL))(
                   ClipGeometry,
                   &GUID_b9e550ba_696b_4605_ba63_041cafec3d57,
                   &v68)
              && v68 )
            {
              UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
              Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
              v12 = Gfx::ITarget::Clip::GetLocalToDeviceTransform(a2, v67);
              Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v63, *(_QWORD *)this, v12);
              v13 = v68;
              if ( !v68 )
                CrashWithRecovery(0x1E3C3840u, 0);
              v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              v15 = GdipSetClipPath(*(_QWORD *)this, v14, 1);
              Gfx::GdipStatus_ThrowOnFailureMessageTag(v15, v16, v17, 38901321);
              Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer((Gfx::GpWorldTransformRestorer *)&v63);
LABEL_22:
              v24 = v68;
              if ( v68 )
              {
                v68 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
              }
              return;
            }
            CrashWithRecovery(0x1E082313u, 0);
          }
          v68 = 0;
          v18 = Gfx::ITarget::Clip::GetClipGeometry(a2);
          if ( (*(unsigned __int8 (__fastcall **)(const struct ARC::IGeometry *, GUID *, __int64 *))(*(_QWORD *)v18 + 16LL))(
                 v18,
                 &GUID_b9e550ba_696b_4605_ba63_041cafec3d57,
                 &v68)
            && v68 )
          {
            UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
            Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
            v19 = v68;
            if ( !v68 )
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
        v26 = Gfx::ITarget::Clip::GetLocalToDeviceTransform(a2, v67);
        Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v63, *(_QWORD *)this, v26);
        v28 = GEL::PathToGpPath(ClipPath, v27);
        v29 = GdipSetClipPath(*(_QWORD *)this, v28, 1);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v29, v30, v31, 38901321);
LABEL_30:
        Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer((Gfx::GpWorldTransformRestorer *)&v63);
        return;
      }
      v32 = Gfx::ITarget::Clip::GetClipPath(a2);
      UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
      Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
      v34 = GEL::PathToGpPath(v32, v33);
      v35 = GdipSetClipPath(*(_QWORD *)this, v34, 1);
      v38 = 38901320;
    }
    else
    {
      v46 = (float *)&v61;
      v47 = (double *)((char *)a2 + 32);
      v48 = 4;
      do
      {
        *v46++ = *v47++;
        --v48;
      }
      while ( v48 );
      UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
      Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
      Math::TRect<float>::GetHeight(&v61);
      Math::TRect<float>::GetWidth(&v61);
      v35 = GdipSetClipRect(*(_QWORD *)this);
      v38 = 38901318;
    }
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v35, v36, v37, v38);
    return;
  }
  v49 = *(__m128i *)Gfx::ITarget::Frame::GetLogicalBounds(*(_QWORD *)a2, v67);
  v63 = v49;
  if ( *((_BYTE *)this + 28) )
  {
    if ( !*((_QWORD *)a2 + 1) )
    {
      if ( *((_DWORD *)a2 + 6) )
      {
        Math::TRect<int>::IsDegenerate(&v63);
        v51 = v50;
        v52 = _mm_srli_si128(v49, 8).m128i_u64[0];
        if ( v50 || v49.m128i_i32[0] != 0x80000000 || v49.m128i_i32[1] != 0x80000000 || v52 != 0x7FFFFFFF7FFFFFFFLL )
        {
          UnusedClipHolder = Gfx::GDIPlusClipStack::GetUnusedClipHolder(this);
          Gfx::GpClipHolder::SaveClipRegion(UnusedClipHolder, *(const struct Gdiplus::GpGraphics **)this);
          v53 = (double *)(*(_QWORD *)a2 + 96LL);
          v54 = (float *)v67;
          v55 = 6;
          do
          {
            *v54++ = *v53++;
            --v55;
          }
          while ( v55 );
          Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(&v61, *(_QWORD *)this, v67);
          if ( v51 )
            v56 = 0;
          else
            v56 = _mm_cvtsi128_si32(_mm_srli_si128(v49, 12)) - v63.m128i_i32[1];
          if ( v51 )
            v57 = 0;
          else
            v57 = v52 - v49.m128i_i32[0];
          v58 = GdipSetClipRectI(
                  *(_QWORD *)this,
                  v49.m128i_u32[0],
                  *(__int64 *)((char *)v63.m128i_i64 + 4),
                  v57,
                  v56,
                  1,
                  v61,
                  v62);
          Gfx::GdipStatus_ThrowOnFailureMessageTag(v58, v59, v60, 38901322);
          GdipSetWorldTransform(v61, v62);
          ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::Empty(&v62);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180065124  mov     rax, rsp
0x180065127  mov     [rax+10h], rbx
0x18006512b  mov     [rax+18h], rsi
0x18006512f  push    rbp
0x180065130  push    rdi
0x180065131  push    r12
0x180065133  push    r14
0x180065135  push    r15
0x180065137  lea     rbp, [rax-5Fh]
0x18006513b  sub     rsp, 0B0h
0x180065142  movaps  xmmword ptr [rax-38h], xmm6
0x180065146  mov     rsi, rdx
0x180065149  mov     rdi, rcx
0x18006514c  xor     r12d, r12d
0x18006514f  cmp     [rcx], r12
0x180065152  jnz     short loc_180065164
0x180065154  mov     ecx, 1CC08Fh
0x180065159  call    cs:__imp_MsoShipAssertTagProc
0x18006515f  jmp     loc_180065681
0x180065164  mov     [rbp+57h+var_80], rdi
0x180065168  mov     [rbp+57h+var_78], r12
0x18006516c  mov     [rbp+57h+var_70], r12b
0x180065170  mov     ecx, [rdx+18h]
0x180065173  test    ecx, ecx
0x180065175  jz      loc_180065675
0x18006517b  sub     ecx, 1
0x18006517e  jz      loc_180065538
0x180065184  sub     ecx, 1
0x180065187  jz      loc_1800654AF
0x18006518d  sub     ecx, 1
0x180065190  jz      loc_180065400
0x180065196  sub     ecx, 1
0x180065199  jz      loc_1800653B9
0x18006519f  sub     ecx, 1
0x1800651a2  jz      loc_18006534E
0x1800651a8  sub     ecx, 1
0x1800651ab  jz      loc_180065289
0x1800651b1  cmp     ecx, 1
0x1800651b4  jnz     loc_180065681
0x1800651ba  mov     [rbp+57h+arg_0], r12
0x1800651be  mov     rcx, rsi; this
0x1800651c1  call    ?GetClipGeometry@Clip@ITarget@Gfx@@QEBAAEBUIGeometry@ARC@@XZ; Gfx::ITarget::Clip::GetClipGeometry(void)
0x1800651c6  mov     r9, rax
0x1800651c9  mov     rcx, [rax]
0x1800651cc  mov     rax, [rcx+10h]
0x1800651d0  lea     r8, [rbp+57h+arg_0]
0x1800651d4  lea     rdx, _GUID_b9e550ba_696b_4605_ba63_041cafec3d57
0x1800651db  mov     rcx, r9
0x1800651de  call    cs:__guard_dispatch_icall_fptr
0x1800651e4  test    al, al
0x1800651e6  jz      loc_18006527B
0x1800651ec  cmp     [rbp+57h+arg_0], r12
0x1800651f0  jz      loc_18006527B
0x1800651f6  mov     rcx, rdi; this
0x1800651f9  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x1800651fe  mov     [rbp+57h+var_78], rax
0x180065202  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x180065205  mov     rcx, rax; this
0x180065208  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x18006520d  lea     rdx, [rbp+57h+var_68]
0x180065211  mov     rcx, rsi
0x180065214  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x180065219  mov     r8, rax
0x18006521c  mov     rdx, [rdi]
0x18006521f  lea     rcx, [rbp+57h+var_90]
0x180065223  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x180065228  nop
0x180065229  mov     rcx, [rbp+57h+arg_0]
0x18006522d  test    rcx, rcx
0x180065230  jnz     short loc_180065240
0x180065232  xor     edx, edx
0x180065234  mov     ecx, 1E3C3840h
0x180065239  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006523f  nop
0x180065240  mov     rax, [rcx]
0x180065243  mov     rax, [rax+10h]
0x180065247  call    cs:__guard_dispatch_icall_fptr
0x18006524d  mov     r8d, 1
0x180065253  mov     rdx, rax
0x180065256  mov     rcx, [rdi]
0x180065259  call    cs:__imp_GdipSetClipPath
0x18006525f  mov     r9d, 2519649h
0x180065265  mov     ecx, eax
0x180065267  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006526c  nop
0x18006526d  lea     rcx, [rbp+57h+var_90]; this
0x180065271  call    ??1GpWorldTransformRestorer@Gfx@@QEAA@XZ; Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer(void)
0x180065276  jmp     loc_18006531D
0x18006527b  xor     edx, edx
0x18006527d  mov     ecx, 1E082313h
0x180065282  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180065288  nop
0x180065289  mov     [rbp+57h+arg_0], r12
0x18006528d  mov     rcx, rsi; this
0x180065290  call    ?GetClipGeometry@Clip@ITarget@Gfx@@QEBAAEBUIGeometry@ARC@@XZ; Gfx::ITarget::Clip::GetClipGeometry(void)
0x180065295  mov     r9, rax
0x180065298  mov     rcx, [rax]
0x18006529b  mov     rax, [rcx+10h]
0x18006529f  lea     r8, [rbp+57h+arg_0]
0x1800652a3  lea     rdx, _GUID_b9e550ba_696b_4605_ba63_041cafec3d57
0x1800652aa  mov     rcx, r9
0x1800652ad  call    cs:__guard_dispatch_icall_fptr
0x1800652b3  test    al, al
0x1800652b5  jz      loc_180065340
0x1800652bb  cmp     [rbp+57h+arg_0], r12
0x1800652bf  jz      short loc_180065340
0x1800652c1  mov     rcx, rdi; this
0x1800652c4  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x1800652c9  mov     [rbp+57h+var_78], rax
0x1800652cd  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800652d0  mov     rcx, rax; this
0x1800652d3  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800652d8  nop
0x1800652d9  mov     rcx, [rbp+57h+arg_0]
0x1800652dd  test    rcx, rcx
0x1800652e0  jnz     short loc_1800652F0
0x1800652e2  xor     edx, edx
0x1800652e4  mov     ecx, 1E3C3840h
0x1800652e9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800652ef  nop
0x1800652f0  mov     rax, [rcx]
0x1800652f3  mov     rax, [rax+10h]
0x1800652f7  call    cs:__guard_dispatch_icall_fptr
0x1800652fd  mov     r8d, 1
0x180065303  mov     rdx, rax
0x180065306  mov     rcx, [rdi]
0x180065309  call    cs:__imp_GdipSetClipPath
0x18006530f  mov     r9d, 2519648h
0x180065315  mov     ecx, eax
0x180065317  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006531c  nop
0x18006531d  mov     rcx, [rbp+57h+arg_0]
0x180065321  test    rcx, rcx
0x180065324  jz      loc_180065681
0x18006532a  mov     [rbp+57h+arg_0], r12
0x18006532e  mov     rax, [rcx]
0x180065331  mov     rax, [rax+8]
0x180065335  call    cs:__guard_dispatch_icall_fptr
0x18006533b  jmp     loc_180065681
0x180065340  xor     edx, edx
0x180065342  mov     ecx, 1E082314h
0x180065347  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006534d  nop
0x18006534e  mov     rcx, rsi; this
0x180065351  call    ?GetClipPath@Clip@ITarget@Gfx@@QEBAAEBUIPath@GEL@@XZ; Gfx::ITarget::Clip::GetClipPath(void)
0x180065356  mov     rbx, rax
0x180065359  mov     rcx, rdi; this
0x18006535c  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x180065361  mov     [rbp+57h+var_78], rax
0x180065365  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x180065368  mov     rcx, rax; this
0x18006536b  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x180065370  lea     rdx, [rbp+57h+var_68]
0x180065374  mov     rcx, rsi
0x180065377  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x18006537c  mov     r8, rax
0x18006537f  mov     rdx, [rdi]
0x180065382  lea     rcx, [rbp+57h+var_90]
0x180065386  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x18006538b  nop
0x18006538c  mov     rcx, rbx; this
0x18006538f  call    ?PathToGpPath@GEL@@YAAEBVGpPath@Gdiplus@@AEBUIPath@1@@Z; GEL::PathToGpPath(GEL::IPath const &)
0x180065394  mov     r8d, 1
0x18006539a  mov     rdx, rax
0x18006539d  mov     rcx, [rdi]
0x1800653a0  call    cs:__imp_GdipSetClipPath
0x1800653a6  mov     r9d, 2519649h
0x1800653ac  mov     ecx, eax
0x1800653ae  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800653b3  nop
0x1800653b4  jmp     loc_1800654A1
0x1800653b9  mov     rcx, rsi; this
0x1800653bc  call    ?GetClipPath@Clip@ITarget@Gfx@@QEBAAEBUIPath@GEL@@XZ; Gfx::ITarget::Clip::GetClipPath(void)
0x1800653c1  mov     rbx, rax
0x1800653c4  mov     rcx, rdi; this
0x1800653c7  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x1800653cc  mov     [rbp+57h+var_78], rax
0x1800653d0  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800653d3  mov     rcx, rax; this
0x1800653d6  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800653db  mov     rcx, rbx; this
0x1800653de  call    ?PathToGpPath@GEL@@YAAEBVGpPath@Gdiplus@@AEBUIPath@1@@Z; GEL::PathToGpPath(GEL::IPath const &)
0x1800653e3  mov     r8d, 1
0x1800653e9  mov     rdx, rax
0x1800653ec  mov     rcx, [rdi]
0x1800653ef  call    cs:__imp_GdipSetClipPath
0x1800653f5  mov     r9d, 2519648h
0x1800653fb  jmp     loc_18006552C
0x180065400  lea     rax, [rbp+57h+var_A0]
0x180065404  lea     rcx, [rdx+20h]
0x180065408  mov     edx, 4
0x18006540d  movsd   xmm0, qword ptr [rcx]
0x180065411  cvtpd2ps xmm0, xmm0
0x180065415  movss   dword ptr [rax], xmm0
0x180065419  lea     rcx, [rcx+8]
0x18006541d  lea     rax, [rax+4]
0x180065421  sub     rdx, 1
0x180065425  jnz     short loc_18006540D
0x180065427  mov     rcx, rdi; this
0x18006542a  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x18006542f  mov     [rbp+57h+var_78], rax
0x180065433  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x180065436  mov     rcx, rax; this
0x180065439  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x18006543e  lea     rdx, [rbp+57h+var_68]
0x180065442  mov     rcx, rsi
0x180065445  call    ?GetLocalToDeviceTransform@Clip@ITarget@Gfx@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Gfx::ITarget::Clip::GetLocalToDeviceTransform(void)
0x18006544a  mov     r8, rax
0x18006544d  mov     rdx, [rdi]
0x180065450  lea     rcx, [rbp+57h+var_90]
0x180065454  call    ??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &)
0x180065459  nop
0x18006545a  lea     rcx, [rbp+57h+var_A0]
0x18006545e  call    ?GetHeight@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetHeight(void)
0x180065463  movaps  xmm1, xmm0
0x180065466  lea     rcx, [rbp+57h+var_A0]
0x18006546a  call    ?GetWidth@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetWidth(void)
0x18006546f  mov     [rsp+0D0h+var_A8], 1
0x180065477  movss   [rsp+0D0h+var_B0], xmm1
0x18006547d  movaps  xmm3, xmm0
0x180065480  movss   xmm2, dword ptr [rbp+57h+var_A0+4]
0x180065485  movss   xmm1, dword ptr [rbp+57h+var_A0]
0x18006548a  mov     rcx, [rdi]
0x18006548d  call    cs:__imp_GdipSetClipRect
0x180065493  mov     r9d, 2519647h
0x180065499  mov     ecx, eax
0x18006549b  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800654a0  nop
0x1800654a1  lea     rcx, [rbp+57h+var_90]; this
0x1800654a5  call    ??1GpWorldTransformRestorer@Gfx@@QEAA@XZ; Gfx::GpWorldTransformRestorer::~GpWorldTransformRestorer(void)
0x1800654aa  jmp     loc_180065681
0x1800654af  lea     rax, [rbp+57h+var_A0]
0x1800654b3  add     rsi, 20h ; ' '
0x1800654b7  mov     ecx, 4
0x1800654bc  movsd   xmm0, qword ptr [rsi]
0x1800654c0  cvtpd2ps xmm0, xmm0
0x1800654c4  movss   dword ptr [rax], xmm0
0x1800654c8  lea     rsi, [rsi+8]
0x1800654cc  lea     rax, [rax+4]
0x1800654d0  sub     rcx, 1
0x1800654d4  jnz     short loc_1800654BC
0x1800654d6  mov     rcx, rdi; this
0x1800654d9  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x1800654de  mov     [rbp+57h+var_78], rax
0x1800654e2  mov     rdx, [rdi]; struct Gdiplus::GpGraphics *
0x1800654e5  mov     rcx, rax; this
0x1800654e8  call    ?SaveClipRegion@GpClipHolder@Gfx@@QEAAXAEBVGpGraphics@Gdiplus@@@Z; Gfx::GpClipHolder::SaveClipRegion(Gdiplus::GpGraphics const &)
0x1800654ed  lea     rcx, [rbp+57h+var_A0]
0x1800654f1  call    ?GetHeight@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetHeight(void)
0x1800654f6  movaps  xmm1, xmm0
0x1800654f9  lea     rcx, [rbp+57h+var_A0]
0x1800654fd  call    ?GetWidth@?$TRect@M@Math@@QEBAMXZ; Math::TRect<float>::GetWidth(void)
0x180065502  mov     [rsp+0D0h+var_A8], 1
0x18006550a  movss   [rsp+0D0h+var_B0], xmm1
0x180065510  movaps  xmm3, xmm0
0x180065513  movss   xmm2, dword ptr [rbp+57h+var_A0+4]
0x180065518  movss   xmm1, dword ptr [rbp+57h+var_A0]
0x18006551d  mov     rcx, [rdi]
0x180065520  call    cs:__imp_GdipSetClipRect
0x180065526  mov     r9d, 2519646h
0x18006552c  mov     ecx, eax
0x18006552e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180065533  jmp     loc_180065681
0x180065538  lea     rdx, [rbp+57h+var_68]
0x18006553c  mov     rcx, [rsi]
0x18006553f  call    ?GetLogicalBounds@Frame@ITarget@Gfx@@QEBA?AV?$TConvertibleRectPx@H@3@XZ; Gfx::ITarget::Frame::GetLogicalBounds(void)
0x180065544  movups  xmm6, xmmword ptr [rax]
0x180065547  movups  [rbp+57h+var_90], xmm6
0x18006554b  cmp     [rdi+1Ch], r12b
0x18006554f  jz      loc_180065681
0x180065555  cmp     [rsi+8], r12
0x180065559  jnz     loc_180065681
0x18006555f  cmp     [rsi+18h], r12d
0x180065563  jz      loc_180065681
0x180065569  lea     rcx, [rbp+57h+var_90]
0x18006556d  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x180065572  mov     r15b, al
0x180065575  movdqa  xmm0, xmm6
0x180065579  psrldq  xmm0, 8
0x18006557e  movq    rbx, xmm0
0x180065583  movq    r14, xmm6
0x180065588  test    al, al
0x18006558a  jnz     short loc_1800655B9
0x18006558c  mov     eax, 80000000h
0x180065591  cmp     r14d, eax
0x180065594  jnz     short loc_1800655B9
0x180065596  mov     rcx, r14
0x180065599  shr     rcx, 20h
0x18006559d  cmp     ecx, eax
0x18006559f  jnz     short loc_1800655B9
0x1800655a1  mov     ecx, 7FFFFFFFh
0x1800655a6  cmp     ebx, ecx
0x1800655a8  jnz     short loc_1800655B9
0x1800655aa  mov     rax, rbx
0x1800655ad  shr     rax, 20h
0x1800655b1  cmp     eax, ecx
0x1800655b3  jz      loc_180065681
0x1800655b9  mov     rcx, rdi; this
0x1800655bc  call    ?GetUnusedClipHolder@GDIPlusClipStack@Gfx@@AEAAAEAVGpClipHolder@2@XZ; Gfx::GDIPlusClipStack::GetUnusedClipHolder(void)
0x1800655c1  mov     [rbp+57h+var_78], rax
  ... truncated ...
```
