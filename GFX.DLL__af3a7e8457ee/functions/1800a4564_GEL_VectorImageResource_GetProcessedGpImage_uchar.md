# GEL::VectorImageResource::GetProcessedGpImage(uchar)

- ea: `0x1800a4564`
- end: `0x1800a4715`
- name: `?GetProcessedGpImage@VectorImageResource@GEL@@QEAAPEAVGpImage@Gdiplus@@E@Z`
- size: `433`
- prototype: `struct Gdiplus::GpImage *__fastcall(GEL::VectorImageResource *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180062490`

## callees

- `0x18005f898`
- `0x180062394`
- `0x180064d9c`
- `0x1800a4564`
- `0x1800a4718`
- `0x1800a59e0`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a461c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a461c`
- `GDI32!DeleteDC` at `0x1800a468a`
- `GDI32!DeleteDC` at `0x1800a46f5`
- `GDI32!DeleteDC` at `0x1800a468a`
- `GDI32!DeleteDC` at `0x1800a46f5`
- `GDI32!CreateCompatibleDC` at `0x1800a45fd`
- `GDI32!CreateCompatibleDC` at `0x1800a45fd`
- `gdiplus!GdipCloneImage` at `0x1800a45bd`
- `gdiplus!GdipCloneImage` at `0x1800a45bd`
- `gdiplus!GdipEnumerateMetafileDestRect` at `0x1800a466e`
- `gdiplus!GdipEnumerateMetafileDestRect` at `0x1800a466e`
- `gdiplus!GdipDeleteGraphics` at `0x1800a469a`
- `gdiplus!GdipDeleteGraphics` at `0x1800a4709`
- `gdiplus!GdipDeleteGraphics` at `0x1800a469a`
- `gdiplus!GdipDeleteGraphics` at `0x1800a4709`
- `gdiplus!GdipCreateFromHDC` at `0x1800a46c0`
- `gdiplus!GdipCreateFromHDC` at `0x1800a46c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct Gdiplus::GpImage *__fastcall GEL::VectorImageResource::GetProcessedGpImage(
        GEL::VectorImageResource *this,
        char a2)
{
  struct Gdiplus::GpImage *result; // rax
  _QWORD *v4; // rsi
  __int64 v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  HDC CompatibleDC; // rax
  HDC v10; // rdi
  double *v11; // rax
  __int64 v12; // rdx
  float *v13; // rcx
  __int64 v14; // rbx
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  _BYTE v18[16]; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v19[16]; // [rsp+40h] [rbp-30h] BYREF
  _OWORD v20[2]; // [rsp+50h] [rbp-20h] BYREF
  char v21; // [rsp+98h] [rbp+28h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+30h] BYREF
  HDC v23; // [rsp+A8h] [rbp+38h]

  v21 = a2;
  if ( a2 == 1 || !*((_BYTE *)this + 41) )
    return (struct Gdiplus::GpImage *)*((_QWORD *)this + 1);
  v4 = (_QWORD *)((char *)this + 48);
  if ( a2 == *((_BYTE *)this + 42) )
  {
    result = (struct Gdiplus::GpImage *)*v4;
    if ( *v4 )
      return result;
  }
  ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty((char *)this + 48);
  v5 = ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(v4);
  v6 = GdipCloneImage(*((_QWORD *)this + 1), v5);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v6, v7, v8, 537147392);
  v20[0] = _mm_load_si128((const __m128i *)&_xmm);
  v20[1] = 0;
  if ( !(unsigned __int8)GEL::VectorImageResource::GetBounds(this, v20) )
    return (struct Gdiplus::GpImage *)*((_QWORD *)this + 1);
  v22 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v10 = CompatibleDC;
  v23 = CompatibleDC;
  if ( v22 )
  {
    CrashWithRecovery(0x1E55E058u, 0);
  }
  else
  {
    v15 = GdipCreateFromHDC(CompatibleDC, &v22);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v15, v16, v17, 537147363);
    v13 = (float *)v18;
    v11 = (double *)v20;
    v12 = 4;
  }
  do
  {
    *v13++ = *v11++;
    --v12;
  }
  while ( v12 );
  Math::GDIPlus::ToGDIPlusRectF(v19, v18);
  if ( (unsigned int)GdipEnumerateMetafileDestRect(v22, *v4, v19, sub_1801CBB60, &v21, 0) )
  {
    if ( v10 )
      DeleteDC(v10);
    if ( v22 )
      GdipDeleteGraphics();
    return (struct Gdiplus::GpImage *)*((_QWORD *)this + 1);
  }
  *((_BYTE *)this + 42) = v21;
  v14 = *((_QWORD *)this + 6);
  if ( v10 )
    DeleteDC(v10);
  if ( v22 )
    GdipDeleteGraphics();
  return (struct Gdiplus::GpImage *)v14;
}

```

## disassembly

```asm
0x1800a4564  mov     [rsp-18h+arg_0], rbx
0x1800a4569  mov     [rsp-18h+arg_8], dl
0x1800a456d  push    rbp
0x1800a456e  push    rsi
0x1800a456f  push    rdi
0x1800a4570  mov     rbp, rsp
0x1800a4573  sub     rsp, 70h
0x1800a4577  mov     rbx, rcx
0x1800a457a  cmp     dl, 1
0x1800a457d  jnz     short loc_1800A4593
0x1800a457f  mov     rax, [rbx+8]
0x1800a4583  mov     rbx, [rsp+70h+arg_0]
0x1800a458b  add     rsp, 70h
0x1800a458f  pop     rdi
0x1800a4590  pop     rsi
0x1800a4591  pop     rbp
0x1800a4592  retn
0x1800a4593  cmp     byte ptr [rcx+29h], 0
0x1800a4597  jz      short loc_1800A457F
0x1800a4599  lea     rsi, [rcx+30h]
0x1800a459d  cmp     dl, [rcx+2Ah]
0x1800a45a0  jz      loc_1800A46A8
0x1800a45a6  mov     rcx, rsi
0x1800a45a9  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800a45ae  mov     rcx, rsi
0x1800a45b1  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x1800a45b6  mov     rdx, rax
0x1800a45b9  mov     rcx, [rbx+8]
0x1800a45bd  call    cs:__imp_GdipCloneImage
0x1800a45c3  mov     r9d, 20043800h
0x1800a45c9  mov     ecx, eax
0x1800a45cb  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a45d0  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x1800a45d8  movups  [rbp+var_20], xmm0
0x1800a45dc  xorps   xmm0, xmm0
0x1800a45df  movups  [rbp+var_10], xmm0
0x1800a45e3  lea     rdx, [rbp+var_20]
0x1800a45e7  mov     rcx, rbx
0x1800a45ea  call    ?GetBounds@VectorImageResource@GEL@@UEBA_NAEAU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@@Z; GEL::VectorImageResource::GetBounds(Math::TRect<Math::TUnits<double,Math::DevicePixels>> &)
0x1800a45ef  test    al, al
0x1800a45f1  jz      short loc_1800A457F
0x1800a45f3  mov     [rbp+arg_10], 0
0x1800a45fb  xor     ecx, ecx; hdc
0x1800a45fd  call    cs:__imp_CreateCompatibleDC
0x1800a4603  mov     rdi, rax
0x1800a4606  mov     [rbp+arg_18], rax
0x1800a460a  cmp     [rbp+arg_10], 0
0x1800a460f  jz      loc_1800A46B9
0x1800a4615  xor     edx, edx
0x1800a4617  mov     ecx, 1E55E058h
0x1800a461c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a4622  nop
0x1800a4623  movsd   xmm0, qword ptr [rax]
0x1800a4627  cvtpd2ps xmm1, xmm0
0x1800a462b  movss   dword ptr [rcx], xmm1
0x1800a462f  add     rax, 8
0x1800a4633  add     rcx, 4
0x1800a4637  sub     rdx, 1
0x1800a463b  jnz     short loc_1800A4623
0x1800a463d  lea     rdx, [rbp+var_40]
0x1800a4641  lea     rcx, [rbp+var_30]
0x1800a4645  call    ?ToGDIPlusRectF@GDIPlus@Math@@YA?AVRectF@Gdiplus@@AEBU?$TRect@M@2@@Z; Math::GDIPlus::ToGDIPlusRectF(Math::TRect<float> const &)
0x1800a464a  mov     [rsp+70h+var_48], 0
0x1800a4653  lea     rax, [rbp+arg_8]
0x1800a4657  mov     [rsp+70h+var_50], rax
0x1800a465c  lea     r9, sub_1801CBB60
0x1800a4663  lea     r8, [rbp+var_30]
0x1800a4667  mov     rdx, [rsi]
0x1800a466a  mov     rcx, [rbp+arg_10]
0x1800a466e  call    cs:__imp_GdipEnumerateMetafileDestRect
0x1800a4674  test    eax, eax
0x1800a4676  jnz     short loc_1800A46ED
0x1800a4678  mov     al, [rbp+arg_8]
0x1800a467b  mov     [rbx+2Ah], al
0x1800a467e  mov     rbx, [rbx+30h]
0x1800a4682  test    rdi, rdi
0x1800a4685  jz      short loc_1800A4691
0x1800a4687  mov     rcx, rdi; hdc
0x1800a468a  call    cs:__imp_DeleteDC
0x1800a4690  nop
0x1800a4691  mov     rcx, [rbp+arg_10]
0x1800a4695  test    rcx, rcx
0x1800a4698  jz      short loc_1800A46A0
0x1800a469a  call    cs:__imp_GdipDeleteGraphics
0x1800a46a0  mov     rax, rbx
0x1800a46a3  jmp     loc_1800A4583
0x1800a46a8  mov     rax, [rsi]
0x1800a46ab  test    rax, rax
0x1800a46ae  jnz     loc_1800A4583
0x1800a46b4  jmp     loc_1800A45A6
0x1800a46b9  lea     rdx, [rbp+arg_10]
0x1800a46bd  mov     rcx, rdi
0x1800a46c0  call    cs:__imp_GdipCreateFromHDC
0x1800a46c6  mov     r9d, 200437E3h
0x1800a46cc  mov     ecx, eax
0x1800a46ce  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a46d3  lea     rcx, [rbp+var_40]
0x1800a46d7  lea     rax, [rbp+var_20]
0x1800a46db  mov     edx, 4
0x1800a46e0  movsd   xmm2, cs:__real@c7efffffe0000000
0x1800a46e8  jmp     loc_1800A4623
0x1800a46ed  test    rdi, rdi
0x1800a46f0  jz      short loc_1800A46FC
0x1800a46f2  mov     rcx, rdi; hdc
0x1800a46f5  call    cs:__imp_DeleteDC
0x1800a46fb  nop
0x1800a46fc  mov     rcx, [rbp+arg_10]
0x1800a4700  test    rcx, rcx
0x1800a4703  jz      loc_1800A457F
0x1800a4709  call    cs:__imp_GdipDeleteGraphics
0x1800a470f  jmp     loc_1800A457F
```
