# GEL::Scene::FillPixelRect(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,GEL::Color const &)

- ea: `0x1801602b0`
- end: `0x1801604de`
- name: `?FillPixelRect@Scene@GEL@@UEAAXAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@AEBUColor@2@@Z`
- size: `558`
- prototype: `__int64 __fastcall(GEL::Scene *this)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800532f8`
- `0x180057e70`
- `0x18007376c`
- `0x18007efec`
- `0x18007f754`
- `0x1800817d4`
- `0x180083630`
- `0x180083648`
- `0x1801602b0`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18016049f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18016049f`
- `gdiplus!GdipAddPathRectangleI` at `0x180160398`
- `gdiplus!GdipAddPathRectangleI` at `0x180160398`
- `gdiplus!GdipFillPath` at `0x180160421`
- `gdiplus!GdipFillPath` at `0x180160421`
- `gdiplus!GdipDeletePath` at `0x180160447`
- `gdiplus!GdipDeletePath` at `0x180160447`
- `gdiplus!GdipCreatePath` at `0x180160342`
- `gdiplus!GdipCreatePath` at `0x180160342`
- `gdiplus!GdipCreateSolidFill` at `0x180160403`
- `gdiplus!GdipCreateSolidFill` at `0x180160403`
- `gdiplus!GdipDeleteBrush` at `0x180160430`
- `gdiplus!GdipDeleteBrush` at `0x180160430`

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
0x1801602b0  mov     [rsp-18h+arg_8], rbx
0x1801602b5  push    rbp
0x1801602b6  push    rsi
0x1801602b7  push    rdi
0x1801602b8  mov     rbp, rsp
0x1801602bb  sub     rsp, 60h
0x1801602bf  mov     rsi, r8
0x1801602c2  mov     rdi, rdx
0x1801602c5  mov     rbx, rcx
0x1801602c8  cmp     byte ptr [rcx+30h], 0
0x1801602cc  jnz     loc_18016049A
0x1801602d2  call    ?EnsureGraphicsSurface@Scene@GEL@@QEAAAEAVGraphicsSurface@2@XZ; GEL::Scene::EnsureGraphicsSurface(void)
0x1801602d7  movups  xmm0, xmmword ptr [rdi]
0x1801602da  movdqu  [rbp+var_20], xmm0
0x1801602df  lea     rdx, [rax+40h]
0x1801602e3  lea     rcx, [rbp+var_20]
0x1801602e7  call    ??$IntersectWith@V?$TUnits@HUDevicePixels@Math@@@Math@@$0A@@?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@QEAAXAEBU01@@Z; Math::TRect<Math::TUnits<int,Math::DevicePixels>>::IntersectWith<Math::TUnits<int,Math::DevicePixels>,0>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1801602ec  movaps  xmm0, [rbp+var_20]
0x1801602f0  movdqa  [rbp+var_30], xmm0
0x1801602f5  movq    rax, xmm0
0x1801602fa  psrldq  xmm0, 8
0x1801602ff  movq    rcx, xmm0
0x180160304  cmp     eax, ecx
0x180160306  jge     loc_18016047B
0x18016030c  shr     rcx, 20h
0x180160310  shr     rax, 20h
0x180160314  cmp     eax, ecx
0x180160316  jge     loc_18016047B
0x18016031c  mov     rcx, rbx; this
0x18016031f  call    ?GetEmulatedGpGraphics@Scene@GEL@@QEAAPEAVGpGraphics@Gdiplus@@XZ; GEL::Scene::GetEmulatedGpGraphics(void)
0x180160324  mov     rdi, rax
0x180160327  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x18016032a  lea     rcx, [rbp+var_20]; this
0x18016032e  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x180160333  nop
0x180160334  mov     [rbp+arg_0], 0
0x18016033c  lea     rdx, [rbp+arg_0]
0x180160340  xor     ecx, ecx
0x180160342  call    cs:__imp_GdipCreatePath
0x180160348  mov     r9d, 2512017h
0x18016034e  mov     ecx, eax
0x180160350  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180160355  mov     eax, dword ptr [rbp+var_30+0Ch]
0x180160358  mov     r8d, dword ptr [rbp+var_30+4]
0x18016035c  mov     rdx, qword ptr [rbp+var_30]
0x180160360  mov     r9, qword ptr [rbp+var_30+8]
0x180160364  cmp     edx, r9d
0x180160367  jg      loc_18016048B
0x18016036d  cmp     r8d, eax
0x180160370  jg      loc_18016048B
0x180160376  mov     ecx, eax
0x180160378  sub     ecx, r8d
0x18016037b  cmp     edx, r9d
0x18016037e  jg      loc_180160492
0x180160384  cmp     r8d, eax
0x180160387  jg      loc_180160492
0x18016038d  sub     r9d, edx
0x180160390  mov     [rsp+60h+var_40], ecx
0x180160394  mov     rcx, [rbp+arg_0]
0x180160398  call    cs:__imp_GdipAddPathRectangleI
0x18016039e  mov     [rbp+arg_18], 0
0x1801603a6  movss   xmm0, dword ptr [rsi+0Ch]
0x1801603ab  movss   xmm1, cs:__real@437f0000
0x1801603b3  mulss   xmm0, xmm1
0x1801603b7  cvttss2si eax, xmm0
0x1801603bb  movzx   r8d, al
0x1801603bf  shl     r8d, 8
0x1801603c3  movss   xmm0, dword ptr [rsi]
0x1801603c7  mulss   xmm0, xmm1
0x1801603cb  cvttss2si eax, xmm0
0x1801603cf  movzx   ecx, al
0x1801603d2  or      ecx, r8d
0x1801603d5  shl     ecx, 8
0x1801603d8  movss   xmm0, dword ptr [rsi+4]
0x1801603dd  mulss   xmm0, xmm1
0x1801603e1  cvttss2si eax, xmm0
0x1801603e5  movzx   edx, al
0x1801603e8  or      ecx, edx
0x1801603ea  shl     ecx, 8
0x1801603ed  movss   xmm0, dword ptr [rsi+8]
0x1801603f2  mulss   xmm0, xmm1
0x1801603f6  cvttss2si eax, xmm0
0x1801603fa  movzx   edx, al
0x1801603fd  or      ecx, edx
0x1801603ff  lea     rdx, [rbp+arg_18]
0x180160403  call    cs:__imp_GdipCreateSolidFill
0x180160409  mov     r9d, 2512018h
0x18016040f  mov     ecx, eax
0x180160411  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180160416  mov     r8, [rbp+arg_0]
0x18016041a  mov     rdx, [rbp+arg_18]
0x18016041e  mov     rcx, rdi
0x180160421  call    cs:__imp_GdipFillPath
0x180160427  mov     rcx, [rbp+arg_18]
0x18016042b  test    rcx, rcx
0x18016042e  jz      short loc_18016043E
0x180160430  call    cs:__imp_GdipDeleteBrush
0x180160436  mov     [rbp+arg_18], 0
0x18016043e  mov     rcx, [rbp+arg_0]
0x180160442  test    rcx, rcx
0x180160445  jz      short loc_180160455
0x180160447  call    cs:__imp_GdipDeletePath
0x18016044d  mov     [rbp+arg_0], 0
0x180160455  lea     rcx, [rbp+var_20]; this
0x180160459  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x18016045e  mov     rcx, [rbx+10h]
0x180160462  mov     rax, [rcx]
0x180160465  mov     rax, [rax+270h]
0x18016046c  call    cs:__guard_dispatch_icall_fptr
0x180160472  cmp     byte ptr [rax+0D8h], 0
0x180160479  jnz     short loc_1801604B0
0x18016047b  mov     rbx, [rsp+60h+arg_8]
0x180160483  add     rsp, 60h
0x180160487  pop     rdi
0x180160488  pop     rsi
0x180160489  pop     rbp
0x18016048a  retn
0x18016048b  xor     ecx, ecx
0x18016048d  jmp     loc_18016037B
0x180160492  xor     r9d, r9d
0x180160495  jmp     loc_180160390
0x18016049a  mov     ecx, 2A05A2h
0x18016049f  call    cs:__imp_MsoShipAssertTagProc
0x1801604a5  mov     ecx, 2A05A3h; unsigned int
0x1801604aa  call    ?ThrowTag@CInvalidOperationException@Ofc@@SAXK@Z; Ofc::CInvalidOperationException::ThrowTag(ulong)
0x1801604af  int     3; Trap to Debugger
0x1801604b0  mov     rcx, [rbx+10h]
0x1801604b4  mov     rax, [rcx]
0x1801604b7  mov     rax, [rax+270h]
0x1801604be  call    cs:__guard_dispatch_icall_fptr
0x1801604c4  mov     r8, rax
0x1801604c7  mov     rcx, [rax]
0x1801604ca  mov     rax, [rcx+58h]
0x1801604ce  lea     rdx, [rbp+var_30]
0x1801604d2  mov     rcx, r8
0x1801604d5  call    cs:__guard_dispatch_icall_fptr
0x1801604db  jmp     short loc_18016047B
```
