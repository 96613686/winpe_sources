# GEL::Printer::EndTile(void)

- ea: `0x1800c50e0`
- end: `0x1800c52ae`
- name: `?EndTile@Printer@GEL@@UEAA_NXZ`
- size: `462`
- prototype: `bool __fastcall(GEL::Printer *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800c4f10`

## callees

- `0x18002cc00`
- `0x1800573f0`
- `0x18005f290`
- `0x180060884`
- `0x180061c38`
- `0x180062394`
- `0x180064bb8`
- `0x180064e30`
- `0x1800a9b44`
- `0x1800c50e0`
- `0x1801219dc`

## import_xrefs

- `gdiplus!GdipDrawRectangleI` at `0x1800c5248`
- `gdiplus!GdipDrawRectangleI` at `0x1800c5248`
- `gdiplus!GdipSetClipRegion` at `0x1800c5189`
- `gdiplus!GdipSetClipRegion` at `0x1800c5189`
- `gdiplus!GdipDeletePen` at `0x1800c5269`
- `gdiplus!GdipDeletePen` at `0x1800c5269`
- `gdiplus!GdipCreatePen1` at `0x1800c51d9`
- `gdiplus!GdipCreatePen1` at `0x1800c51d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GEL::Printer::EndTile(GEL::Printer *this)
{
  __int64 result; // rax
  char v3; // al
  GEL::GraphicsSurface *v4; // rax
  struct Gdiplus::GpGraphics *GpGraphics; // rax
  __int64 v6; // rbx
  GEL::GraphicsSurface *v7; // rax
  struct Gdiplus::GpGraphics *v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // r14d
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // ebx
  unsigned int v21; // edi
  unsigned int *v22; // rcx
  unsigned int v23; // esi
  __int64 v24; // rbp
  GEL::GraphicsSurface *v25; // rax
  struct Gdiplus::GpGraphics *v26; // rax
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  _BYTE v30[88]; // [rsp+30h] [rbp-58h] BYREF
  char v31; // [rsp+90h] [rbp+8h] BYREF
  char v32; // [rsp+98h] [rbp+10h] BYREF
  __int64 v33; // [rsp+A0h] [rbp+18h] BYREF

  result = (*(__int64 (__fastcall **)(GEL::Printer *))(*(_QWORD *)this + 808LL))(this);
  if ( (_BYTE)result )
  {
    v3 = *((_BYTE *)this + 449);
    if ( v3 && !*((_QWORD *)this + 39) )
    {
      GEL::FailureException::ThrowTag(0x85831Au);
      __debugbreak();
    }
    *((_BYTE *)this + 448) = 0;
    if ( v3 && *((_QWORD *)this + 46) )
    {
      v4 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 312);
      GpGraphics = GEL::GraphicsSurface::GetGpGraphics(v4);
      GEL::GDIPixelModeRestorer::GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v30, GpGraphics);
      v6 = *((_QWORD *)this + 46);
      v7 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 312);
      v8 = GEL::GraphicsSurface::GetGpGraphics(v7);
      v9 = GdipSetClipRegion(v8, v6, 0);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 38869152);
      ARC::GDIPlus::TGpHolder<Gdiplus::GpRegion>::Empty((char *)this + 368);
      if ( *((_BYTE *)this + 451) )
      {
        v33 = 0;
        v13 = GdipCreatePen1(4278190080LL, v12, 2, &v33);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v13, v14, v15, 38869153);
        v16 = *(_DWORD *)Math::TRect<Math::TUnits<int,Math::DevicePixels>>::GetHeight((char *)this + 324, &v31);
        v20 = *(_DWORD *)Math::TRect<Math::TUnits<int,Math::DevicePixels>>::GetWidth(v17, &v32, v18, v19);
        v21 = *((_DWORD *)this + 82);
        v23 = *v22;
        v24 = v33;
        v25 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 312);
        v26 = GEL::GraphicsSurface::GetGpGraphics(v25);
        v27 = GdipDrawRectangleI(v26, v24, v23, v21, v20, v16);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v27, v28, v29, 38869154);
        if ( v33 )
          GdipDeletePen();
      }
      GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v30);
    }
    result = 1;
    *((_DWORD *)this + 82) = 1;
    *((_DWORD *)this + 81) = 1;
    *(_QWORD *)((char *)this + 332) = 0;
    *((_BYTE *)this + 452) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800c50e0  push    rbx
0x1800c50e2  push    rbp
0x1800c50e3  push    rsi
0x1800c50e4  push    rdi
0x1800c50e5  push    r12
0x1800c50e7  push    r14
0x1800c50e9  push    r15
0x1800c50eb  sub     rsp, 50h
0x1800c50ef  mov     r15, rcx
0x1800c50f2  mov     rax, [rcx]
0x1800c50f5  mov     rax, [rax+328h]
0x1800c50fc  call    cs:__guard_dispatch_icall_fptr
0x1800c5102  test    al, al
0x1800c5104  jz      loc_1800C529F
0x1800c510a  mov     al, [r15+1C1h]
0x1800c5111  lea     r12, [r15+138h]
0x1800c5118  test    al, al
0x1800c511a  jz      short loc_1800C512E
0x1800c511c  cmp     qword ptr [r12], 0
0x1800c5121  jnz     short loc_1800C512E
0x1800c5123  mov     ecx, 85831Ah; unsigned int
0x1800c5128  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800c512d  int     3; Trap to Debugger
0x1800c512e  mov     byte ptr [r15+1C0h], 0
0x1800c5136  test    al, al
0x1800c5138  jz      loc_1800C527A
0x1800c513e  lea     rdi, [r15+170h]
0x1800c5145  cmp     qword ptr [rdi], 0
0x1800c5149  jz      loc_1800C527A
0x1800c514f  mov     rcx, r12
0x1800c5152  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c5157  mov     rcx, rax; this
0x1800c515a  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c515f  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x1800c5162  lea     rcx, [rsp+88h+var_58]; this
0x1800c5167  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800c516c  nop
0x1800c516d  mov     rbx, [rdi]
0x1800c5170  mov     rcx, r12
0x1800c5173  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c5178  mov     rcx, rax; this
0x1800c517b  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c5180  xor     r8d, r8d
0x1800c5183  mov     rdx, rbx
0x1800c5186  mov     rcx, rax
0x1800c5189  call    cs:__imp_GdipSetClipRegion
0x1800c518f  mov     r9d, 25118A0h
0x1800c5195  mov     ecx, eax
0x1800c5197  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c519c  mov     rcx, rdi
0x1800c519f  call    ?Empty@?$TGpHolder@VGpRegion@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpRegion>::Empty(void)
0x1800c51a4  cmp     byte ptr [r15+1C3h], 0
0x1800c51ac  jz      loc_1800C5270
0x1800c51b2  mov     [rsp+88h+arg_10], 0
0x1800c51be  lea     r9, [rsp+88h+arg_10]
0x1800c51c6  mov     r8d, 2
0x1800c51cc  movss   xmm1, cs:__real@3f800000
0x1800c51d4  mov     ecx, 0FF000000h
0x1800c51d9  call    cs:__imp_GdipCreatePen1
0x1800c51df  mov     r9d, 25118A1h
0x1800c51e5  mov     ecx, eax
0x1800c51e7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c51ec  lea     rcx, [r15+144h]
0x1800c51f3  lea     rdx, [rsp+88h+arg_0]
0x1800c51fb  call    ?GetHeight@?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@QEBA?AV?$TUnits@HUDevicePixels@Math@@@2@XZ; Math::TRect<Math::TUnits<int,Math::DevicePixels>>::GetHeight(void)
0x1800c5200  mov     r14d, [rax]
0x1800c5203  lea     rdx, [rsp+88h+arg_8]
0x1800c520b  call    ?GetWidth@?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@QEBA?AV?$TUnits@HUDevicePixels@Math@@@2@XZ; Math::TRect<Math::TUnits<int,Math::DevicePixels>>::GetWidth(void)
0x1800c5210  mov     ebx, [rax]
0x1800c5212  mov     edi, [r15+148h]
0x1800c5219  mov     esi, [rcx]
0x1800c521b  mov     rbp, [rsp+88h+arg_10]
0x1800c5223  mov     rcx, r12
0x1800c5226  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c522b  mov     rcx, rax; this
0x1800c522e  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c5233  mov     [rsp+88h+var_60], r14d
0x1800c5238  mov     [rsp+88h+var_68], ebx
0x1800c523c  mov     r9d, edi
0x1800c523f  mov     r8d, esi
0x1800c5242  mov     rdx, rbp
0x1800c5245  mov     rcx, rax
0x1800c5248  call    cs:__imp_GdipDrawRectangleI
0x1800c524e  mov     r9d, 25118A2h
0x1800c5254  mov     ecx, eax
0x1800c5256  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c525b  nop
0x1800c525c  mov     rcx, [rsp+88h+arg_10]
0x1800c5264  test    rcx, rcx
0x1800c5267  jz      short loc_1800C5270
0x1800c5269  call    cs:__imp_GdipDeletePen
0x1800c526f  nop
0x1800c5270  lea     rcx, [rsp+88h+var_58]; this
0x1800c5275  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800c527a  mov     eax, 1
0x1800c527f  mov     [r15+148h], eax
0x1800c5286  mov     [r15+144h], eax
0x1800c528d  mov     qword ptr [r15+14Ch], 0
0x1800c5298  mov     [r15+1C4h], al
0x1800c529f  add     rsp, 50h
0x1800c52a3  pop     r15
0x1800c52a5  pop     r14
0x1800c52a7  pop     r12
0x1800c52a9  pop     rdi
0x1800c52aa  pop     rsi
0x1800c52ab  pop     rbp
0x1800c52ac  pop     rbx
0x1800c52ad  retn
```
