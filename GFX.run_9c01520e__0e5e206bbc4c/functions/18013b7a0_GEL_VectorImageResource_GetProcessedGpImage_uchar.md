# GEL::VectorImageResource::GetProcessedGpImage(uchar)

- ea: `0x18013b7a0`
- end: `0x18013b94c`
- name: `?GetProcessedGpImage@VectorImageResource@GEL@@QEAAPEAVGpImage@Gdiplus@@E@Z`
- size: `428`
- prototype: `struct Gdiplus::GpImage *__fastcall(GEL::VectorImageResource *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007f850`

## callees

- `0x18007f754`
- `0x18007faf8`
- `0x180082aac`
- `0x1800e48f0`
- `0x18013b7a0`
- `0x18013b950`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013b90c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18013b90c`
- `GDI32!DeleteDC` at `0x18013b8e7`
- `GDI32!DeleteDC` at `0x18013b92c`
- `GDI32!DeleteDC` at `0x18013b8e7`
- `GDI32!DeleteDC` at `0x18013b92c`
- `GDI32!CreateCompatibleDC` at `0x18013b839`
- `GDI32!CreateCompatibleDC` at `0x18013b839`
- `gdiplus!GdipCloneImage` at `0x18013b7f9`
- `gdiplus!GdipCloneImage` at `0x18013b7f9`
- `gdiplus!GdipEnumerateMetafileDestRect` at `0x18013b8cb`
- `gdiplus!GdipEnumerateMetafileDestRect` at `0x18013b8cb`
- `gdiplus!GdipDeleteGraphics` at `0x18013b8f7`
- `gdiplus!GdipDeleteGraphics` at `0x18013b940`
- `gdiplus!GdipDeleteGraphics` at `0x18013b8f7`
- `gdiplus!GdipDeleteGraphics` at `0x18013b940`
- `gdiplus!GdipCreateFromHDC` at `0x18013b858`
- `gdiplus!GdipCreateFromHDC` at `0x18013b858`

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
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  float *v14; // rcx
  double *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  _BYTE v18[16]; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v19[16]; // [rsp+40h] [rbp-30h] BYREF
  _OWORD v20[2]; // [rsp+50h] [rbp-20h] BYREF
  char v21; // [rsp+98h] [rbp+28h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+30h] BYREF
  HDC v23; // [rsp+A8h] [rbp+38h]

  v21 = a2;
  if ( a2 != 1 && *((_BYTE *)this + 41) )
  {
    v4 = (_QWORD *)((char *)this + 48);
    if ( a2 == *((_BYTE *)this + 42) )
      goto LABEL_17;
    while ( 1 )
    {
      ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(v4);
      v5 = ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(v4);
      v6 = GdipCloneImage(*((_QWORD *)this + 1), v5);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v6, v7, v8, 537147392);
      v20[0] = _mm_load_si128((const __m128i *)&_xmm);
      v20[1] = 0;
      if ( !(unsigned __int8)GEL::VectorImageResource::GetBounds(this, v20) )
        break;
      v22 = 0;
      CompatibleDC = CreateCompatibleDC(0);
      v10 = CompatibleDC;
      v23 = CompatibleDC;
      if ( !v22 )
      {
        v11 = GdipCreateFromHDC(CompatibleDC, &v22);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v11, v12, v13, 537147363);
        v14 = (float *)v18;
        v15 = (double *)v20;
        v16 = 4;
        do
        {
          *v14++ = *v15++;
          --v16;
        }
        while ( v16 );
        Math::GDIPlus::ToGDIPlusRectF(v19, v18);
        if ( !(unsigned int)GdipEnumerateMetafileDestRect(v22, *v4, v19, sub_1801D0700, &v21, 0) )
        {
          *((_BYTE *)this + 42) = v21;
          v17 = *((_QWORD *)this + 6);
          if ( v10 )
            DeleteDC(v10);
          if ( v22 )
            GdipDeleteGraphics();
          return (struct Gdiplus::GpImage *)v17;
        }
        if ( v10 )
          DeleteDC(v10);
        if ( v22 )
          GdipDeleteGraphics();
        return (struct Gdiplus::GpImage *)*((_QWORD *)this + 1);
      }
      CrashWithRecovery(0x1E55E058u, 0);
LABEL_17:
      result = (struct Gdiplus::GpImage *)*v4;
      if ( *v4 )
        return result;
    }
  }
  return (struct Gdiplus::GpImage *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x18013b7a0  mov     [rsp-18h+arg_0], rbx
0x18013b7a5  mov     [rsp-18h+arg_8], dl
0x18013b7a9  push    rbp
0x18013b7aa  push    rsi
0x18013b7ab  push    rdi
0x18013b7ac  mov     rbp, rsp
0x18013b7af  sub     rsp, 70h
0x18013b7b3  mov     rbx, rcx
0x18013b7b6  cmp     dl, 1
0x18013b7b9  jnz     short loc_18013B7CF
0x18013b7bb  mov     rax, [rbx+8]
0x18013b7bf  mov     rbx, [rsp+70h+arg_0]
0x18013b7c7  add     rsp, 70h
0x18013b7cb  pop     rdi
0x18013b7cc  pop     rsi
0x18013b7cd  pop     rbp
0x18013b7ce  retn
0x18013b7cf  cmp     byte ptr [rcx+29h], 0
0x18013b7d3  jz      short loc_18013B7BB
0x18013b7d5  lea     rsi, [rcx+30h]
0x18013b7d9  cmp     dl, [rcx+2Ah]
0x18013b7dc  jz      loc_18013B913
0x18013b7e2  mov     rcx, rsi
0x18013b7e5  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x18013b7ea  mov     rcx, rsi
0x18013b7ed  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x18013b7f2  mov     rdx, rax
0x18013b7f5  mov     rcx, [rbx+8]
0x18013b7f9  call    cs:__imp_GdipCloneImage
0x18013b7ff  mov     r9d, 20043800h
0x18013b805  mov     ecx, eax
0x18013b807  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18013b80c  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x18013b814  movups  [rbp+var_20], xmm0
0x18013b818  xorps   xmm0, xmm0
0x18013b81b  movups  [rbp+var_10], xmm0
0x18013b81f  lea     rdx, [rbp+var_20]
0x18013b823  mov     rcx, rbx
0x18013b826  call    ?GetBounds@VectorImageResource@GEL@@UEBA_NAEAU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@@Z; GEL::VectorImageResource::GetBounds(Math::TRect<Math::TUnits<double,Math::DevicePixels>> &)
0x18013b82b  test    al, al
0x18013b82d  jz      short loc_18013B7BB
0x18013b82f  mov     [rbp+arg_10], 0
0x18013b837  xor     ecx, ecx; hdc
0x18013b839  call    cs:__imp_CreateCompatibleDC
0x18013b83f  mov     rdi, rax
0x18013b842  mov     [rbp+arg_18], rax
0x18013b846  cmp     [rbp+arg_10], 0
0x18013b84b  jnz     loc_18013B905
0x18013b851  lea     rdx, [rbp+arg_10]
0x18013b855  mov     rcx, rax
0x18013b858  call    cs:__imp_GdipCreateFromHDC
0x18013b85e  mov     r9d, 200437E3h
0x18013b864  mov     ecx, eax
0x18013b866  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18013b86b  lea     rcx, [rbp+var_40]
0x18013b86f  lea     rax, [rbp+var_20]
0x18013b873  mov     edx, 4
0x18013b878  movsd   xmm2, cs:__real@c7efffffe0000000
0x18013b880  movsd   xmm0, qword ptr [rax]
0x18013b884  cvtpd2ps xmm1, xmm0
0x18013b888  movss   dword ptr [rcx], xmm1
0x18013b88c  add     rax, 8
0x18013b890  add     rcx, 4
0x18013b894  sub     rdx, 1
0x18013b898  jnz     short loc_18013B880
0x18013b89a  lea     rdx, [rbp+var_40]
0x18013b89e  lea     rcx, [rbp+var_30]
0x18013b8a2  call    ?ToGDIPlusRectF@GDIPlus@Math@@YA?AVRectF@Gdiplus@@AEBU?$TRect@M@2@@Z; Math::GDIPlus::ToGDIPlusRectF(Math::TRect<float> const &)
0x18013b8a7  mov     [rsp+70h+var_48], 0
0x18013b8b0  lea     rax, [rbp+arg_8]
0x18013b8b4  mov     [rsp+70h+var_50], rax
0x18013b8b9  lea     r9, sub_1801D0700
0x18013b8c0  lea     r8, [rbp+var_30]
0x18013b8c4  mov     rdx, [rsi]
0x18013b8c7  mov     rcx, [rbp+arg_10]
0x18013b8cb  call    cs:__imp_GdipEnumerateMetafileDestRect
0x18013b8d1  test    eax, eax
0x18013b8d3  jnz     short loc_18013B924
0x18013b8d5  mov     al, [rbp+arg_8]
0x18013b8d8  mov     [rbx+2Ah], al
0x18013b8db  mov     rbx, [rbx+30h]
0x18013b8df  test    rdi, rdi
0x18013b8e2  jz      short loc_18013B8EE
0x18013b8e4  mov     rcx, rdi; hdc
0x18013b8e7  call    cs:__imp_DeleteDC
0x18013b8ed  nop
0x18013b8ee  mov     rcx, [rbp+arg_10]
0x18013b8f2  test    rcx, rcx
0x18013b8f5  jz      short loc_18013B8FD
0x18013b8f7  call    cs:__imp_GdipDeleteGraphics
0x18013b8fd  mov     rax, rbx
0x18013b900  jmp     loc_18013B7BF
0x18013b905  xor     edx, edx
0x18013b907  mov     ecx, 1E55E058h
0x18013b90c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18013b912  nop
0x18013b913  mov     rax, [rsi]
0x18013b916  test    rax, rax
0x18013b919  jnz     loc_18013B7BF
0x18013b91f  jmp     loc_18013B7E2
0x18013b924  test    rdi, rdi
0x18013b927  jz      short loc_18013B933
0x18013b929  mov     rcx, rdi; hdc
0x18013b92c  call    cs:__imp_DeleteDC
0x18013b932  nop
0x18013b933  mov     rcx, [rbp+arg_10]
0x18013b937  test    rcx, rcx
0x18013b93a  jz      loc_18013B7BB
0x18013b940  call    cs:__imp_GdipDeleteGraphics
0x18013b946  jmp     loc_18013B7BB
```
