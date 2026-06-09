# GEL::Scene::FillPixelRect(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,GEL::Color const &)

- ea: `0x1800c3080`
- end: `0x1800c32ae`
- name: `?FillPixelRect@Scene@GEL@@UEAAXAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@AEBUColor@2@@Z`
- size: `558`
- prototype: `__int64 __fastcall(GEL::Scene *this)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180052fc8`
- `0x1800573f0`
- `0x180060884`
- `0x180061c38`
- `0x180062394`
- `0x180076dfc`
- `0x1800c3080`
- `0x1800c3fd8`
- `0x1800c3ff0`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800c326f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800c326f`
- `gdiplus!GdipAddPathRectangleI` at `0x1800c3168`
- `gdiplus!GdipAddPathRectangleI` at `0x1800c3168`
- `gdiplus!GdipFillPath` at `0x1800c31f1`
- `gdiplus!GdipFillPath` at `0x1800c31f1`
- `gdiplus!GdipDeletePath` at `0x1800c3217`
- `gdiplus!GdipDeletePath` at `0x1800c3217`
- `gdiplus!GdipCreatePath` at `0x1800c3112`
- `gdiplus!GdipCreatePath` at `0x1800c3112`
- `gdiplus!GdipCreateSolidFill` at `0x1800c31d3`
- `gdiplus!GdipCreateSolidFill` at `0x1800c31d3`
- `gdiplus!GdipDeleteBrush` at `0x1800c3200`
- `gdiplus!GdipDeleteBrush` at `0x1800c3200`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
unsigned __int64 __fastcall GEL::Scene::FillPixelRect(GEL::Scene *this, __m128i *a2, float *a3)
{
  struct GEL::GraphicsSurface *v6; // rax
  unsigned __int64 result; // rax
  unsigned __int64 v8; // xmm0_8
  struct Gdiplus::GpGraphics *EmulatedGpGraphics; // rdi
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // ecx
  __int64 v14; // r9
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rax
  __m128i v20; // [rsp+30h] [rbp-30h] BYREF
  __m128i v21; // [rsp+40h] [rbp-20h] BYREF
  __int64 v22; // [rsp+80h] [rbp+20h] BYREF
  __int64 v23; // [rsp+98h] [rbp+38h] BYREF

  if ( *((_BYTE *)this + 48) )
  {
    MsoShipAssertTagProc(2753954);
    Ofc::CInvalidOperationException::ThrowTag(0x2A05A3u);
    __debugbreak();
  }
  v6 = GEL::Scene::EnsureGraphicsSurface(this);
  v21 = *a2;
  Math::TRect<Math::TUnits<int,Math::DevicePixels>>::IntersectWith<Math::TUnits<int,Math::DevicePixels>,0>(
    &v21,
    (char *)v6 + 64);
  v20 = v21;
  result = v21.m128i_i64[0];
  v8 = _mm_srli_si128(v21, 8).m128i_u64[0];
  if ( v21.m128i_i32[0] < (int)v8 )
  {
    result = HIDWORD(v21.m128i_i64[0]);
    if ( v21.m128i_i32[1] < SHIDWORD(v8) )
    {
      EmulatedGpGraphics = GEL::Scene::GetEmulatedGpGraphics(this);
      GEL::GDIPixelModeRestorer::GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)&v21, EmulatedGpGraphics);
      v22 = 0;
      v10 = GdipCreatePath(0, &v22);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v10, v11, v12, 38871063);
      if ( v20.m128i_i32[0] > v20.m128i_i32[2] || v20.m128i_i32[1] > v20.m128i_i32[3] )
        v13 = 0;
      else
        v13 = v20.m128i_i32[3] - v20.m128i_i32[1];
      if ( v20.m128i_i32[0] > v20.m128i_i32[2] || v20.m128i_i32[1] > v20.m128i_i32[3] )
        v14 = 0;
      else
        v14 = (unsigned int)(v20.m128i_i32[2] - v20.m128i_i32[0]);
      GdipAddPathRectangleI(v22, v20.m128i_i64[0], v20.m128i_u32[1], v14, v13);
      v23 = 0;
      GdipCreateSolidFill(
        (unsigned __int8)(int)(float)(a3[2] * 255.0)
      | (((unsigned __int8)(int)(float)(a3[1] * 255.0)
        | ((((unsigned __int8)(int)(float)(a3[3] * 255.0) << 8)
          | (unsigned int)(unsigned __int8)(int)(float)(*a3 * 255.0)) << 8)) << 8),
        &v23);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v15, v16, v17, 38871064);
      GdipFillPath(EmulatedGpGraphics, v23, v22);
      if ( v23 )
      {
        GdipDeleteBrush(v23, v18);
        v23 = 0;
      }
      if ( v22 )
      {
        GdipDeletePath();
        v22 = 0;
      }
      GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)&v21);
      result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 624LL))(*((_QWORD *)this + 2));
      if ( *(_BYTE *)(result + 216) )
      {
        v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 624LL))(*((_QWORD *)this + 2));
        return (*(__int64 (__fastcall **)(__int64, __m128i *))(*(_QWORD *)v19 + 88LL))(v19, &v20);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c3080  mov     [rsp-18h+arg_8], rbx
0x1800c3085  push    rbp
0x1800c3086  push    rsi
0x1800c3087  push    rdi
0x1800c3088  mov     rbp, rsp
0x1800c308b  sub     rsp, 60h
0x1800c308f  mov     rsi, r8
0x1800c3092  mov     rdi, rdx
0x1800c3095  mov     rbx, rcx
0x1800c3098  cmp     byte ptr [rcx+30h], 0
0x1800c309c  jnz     loc_1800C326A
0x1800c30a2  call    ?EnsureGraphicsSurface@Scene@GEL@@QEAAAEAVGraphicsSurface@2@XZ; GEL::Scene::EnsureGraphicsSurface(void)
0x1800c30a7  movups  xmm0, xmmword ptr [rdi]
0x1800c30aa  movdqu  [rbp+var_20], xmm0
0x1800c30af  lea     rdx, [rax+40h]
0x1800c30b3  lea     rcx, [rbp+var_20]
0x1800c30b7  call    ??$IntersectWith@V?$TUnits@HUDevicePixels@Math@@@Math@@$0A@@?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@QEAAXAEBU01@@Z; Math::TRect<Math::TUnits<int,Math::DevicePixels>>::IntersectWith<Math::TUnits<int,Math::DevicePixels>,0>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1800c30bc  movaps  xmm0, [rbp+var_20]
0x1800c30c0  movdqa  [rbp+var_30], xmm0
0x1800c30c5  movq    rax, xmm0
0x1800c30ca  psrldq  xmm0, 8
0x1800c30cf  movq    rcx, xmm0
0x1800c30d4  cmp     eax, ecx
0x1800c30d6  jge     loc_1800C324B
0x1800c30dc  shr     rcx, 20h
0x1800c30e0  shr     rax, 20h
0x1800c30e4  cmp     eax, ecx
0x1800c30e6  jge     loc_1800C324B
0x1800c30ec  mov     rcx, rbx; this
0x1800c30ef  call    ?GetEmulatedGpGraphics@Scene@GEL@@QEAAPEAVGpGraphics@Gdiplus@@XZ; GEL::Scene::GetEmulatedGpGraphics(void)
0x1800c30f4  mov     rdi, rax
0x1800c30f7  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x1800c30fa  lea     rcx, [rbp+var_20]; this
0x1800c30fe  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800c3103  nop
0x1800c3104  mov     [rbp+arg_0], 0
0x1800c310c  lea     rdx, [rbp+arg_0]
0x1800c3110  xor     ecx, ecx
0x1800c3112  call    cs:__imp_GdipCreatePath
0x1800c3118  mov     r9d, 2512017h
0x1800c311e  mov     ecx, eax
0x1800c3120  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c3125  mov     eax, dword ptr [rbp+var_30+0Ch]
0x1800c3128  mov     r8d, dword ptr [rbp+var_30+4]
0x1800c312c  mov     rdx, qword ptr [rbp+var_30]
0x1800c3130  mov     r9, qword ptr [rbp+var_30+8]
0x1800c3134  cmp     edx, r9d
0x1800c3137  jg      loc_1800C325B
0x1800c313d  cmp     r8d, eax
0x1800c3140  jg      loc_1800C325B
0x1800c3146  mov     ecx, eax
0x1800c3148  sub     ecx, r8d
0x1800c314b  cmp     edx, r9d
0x1800c314e  jg      loc_1800C3262
0x1800c3154  cmp     r8d, eax
0x1800c3157  jg      loc_1800C3262
0x1800c315d  sub     r9d, edx
0x1800c3160  mov     [rsp+60h+var_40], ecx
0x1800c3164  mov     rcx, [rbp+arg_0]
0x1800c3168  call    cs:__imp_GdipAddPathRectangleI
0x1800c316e  mov     [rbp+arg_18], 0
0x1800c3176  movss   xmm0, dword ptr [rsi+0Ch]
0x1800c317b  movss   xmm1, cs:__real@437f0000
0x1800c3183  mulss   xmm0, xmm1
0x1800c3187  cvttss2si eax, xmm0
0x1800c318b  movzx   r8d, al
0x1800c318f  shl     r8d, 8
0x1800c3193  movss   xmm0, dword ptr [rsi]
0x1800c3197  mulss   xmm0, xmm1
0x1800c319b  cvttss2si eax, xmm0
0x1800c319f  movzx   ecx, al
0x1800c31a2  or      ecx, r8d
0x1800c31a5  shl     ecx, 8
0x1800c31a8  movss   xmm0, dword ptr [rsi+4]
0x1800c31ad  mulss   xmm0, xmm1
0x1800c31b1  cvttss2si eax, xmm0
0x1800c31b5  movzx   edx, al
0x1800c31b8  or      ecx, edx
0x1800c31ba  shl     ecx, 8
0x1800c31bd  movss   xmm0, dword ptr [rsi+8]
0x1800c31c2  mulss   xmm0, xmm1
0x1800c31c6  cvttss2si eax, xmm0
0x1800c31ca  movzx   edx, al
0x1800c31cd  or      ecx, edx
0x1800c31cf  lea     rdx, [rbp+arg_18]
0x1800c31d3  call    cs:__imp_GdipCreateSolidFill
0x1800c31d9  mov     r9d, 2512018h
0x1800c31df  mov     ecx, eax
0x1800c31e1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c31e6  mov     r8, [rbp+arg_0]
0x1800c31ea  mov     rdx, [rbp+arg_18]
0x1800c31ee  mov     rcx, rdi
0x1800c31f1  call    cs:__imp_GdipFillPath
0x1800c31f7  mov     rcx, [rbp+arg_18]
0x1800c31fb  test    rcx, rcx
0x1800c31fe  jz      short loc_1800C320E
0x1800c3200  call    cs:__imp_GdipDeleteBrush
0x1800c3206  mov     [rbp+arg_18], 0
0x1800c320e  mov     rcx, [rbp+arg_0]
0x1800c3212  test    rcx, rcx
0x1800c3215  jz      short loc_1800C3225
0x1800c3217  call    cs:__imp_GdipDeletePath
0x1800c321d  mov     [rbp+arg_0], 0
0x1800c3225  lea     rcx, [rbp+var_20]; this
0x1800c3229  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800c322e  mov     rcx, [rbx+10h]
0x1800c3232  mov     rax, [rcx]
0x1800c3235  mov     rax, [rax+270h]
0x1800c323c  call    cs:__guard_dispatch_icall_fptr
0x1800c3242  cmp     byte ptr [rax+0D8h], 0
0x1800c3249  jnz     short loc_1800C3280
0x1800c324b  mov     rbx, [rsp+60h+arg_8]
0x1800c3253  add     rsp, 60h
0x1800c3257  pop     rdi
0x1800c3258  pop     rsi
0x1800c3259  pop     rbp
0x1800c325a  retn
0x1800c325b  xor     ecx, ecx
0x1800c325d  jmp     loc_1800C314B
0x1800c3262  xor     r9d, r9d
0x1800c3265  jmp     loc_1800C3160
0x1800c326a  mov     ecx, 2A05A2h
0x1800c326f  call    cs:__imp_MsoShipAssertTagProc
0x1800c3275  mov     ecx, 2A05A3h; unsigned int
0x1800c327a  call    ?ThrowTag@CInvalidOperationException@Ofc@@SAXK@Z; Ofc::CInvalidOperationException::ThrowTag(ulong)
0x1800c327f  int     3; Trap to Debugger
0x1800c3280  mov     rcx, [rbx+10h]
0x1800c3284  mov     rax, [rcx]
0x1800c3287  mov     rax, [rax+270h]
0x1800c328e  call    cs:__guard_dispatch_icall_fptr
0x1800c3294  mov     r8, rax
0x1800c3297  mov     rcx, [rax]
0x1800c329a  mov     rax, [rcx+58h]
0x1800c329e  lea     rdx, [rbp+var_30]
0x1800c32a2  mov     rcx, r8
0x1800c32a5  call    cs:__guard_dispatch_icall_fptr
0x1800c32ab  jmp     short loc_1800C324B
```
