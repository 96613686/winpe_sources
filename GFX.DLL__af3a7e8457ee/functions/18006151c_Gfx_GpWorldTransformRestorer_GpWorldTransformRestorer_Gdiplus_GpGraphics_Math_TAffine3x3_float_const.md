# Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<float> const &)

- ea: `0x18006151c`
- end: `0x1800615c9`
- name: `??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@M@Math@@@Z`
- size: `173`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800614d8`
- `0x180065124`
- `0x1800c01c8`
- `0x18014a234`
- `0x180178678`

## callees

- `0x18006151c`
- `0x180061fe8`
- `0x180062394`

## import_xrefs

- `gdiplus!GdipGetWorldTransform` at `0x180061561`
- `gdiplus!GdipGetWorldTransform` at `0x180061561`
- `gdiplus!GdipSetWorldTransform` at `0x180061593`
- `gdiplus!GdipSetWorldTransform` at `0x180061593`
- `gdiplus!GdipCreateMatrix` at `0x180061548`
- `gdiplus!GdipCreateMatrix` at `0x180061548`
- `gdiplus!GdipDeleteMatrix` at `0x1800615b1`
- `gdiplus!GdipDeleteMatrix` at `0x1800615b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(_QWORD *a1, __int64 a2, __int64 a3)
{
  _QWORD *v6; // rbx
  unsigned int Matrix; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int WorldTransform; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v17; // [rsp+48h] [rbp+10h] BYREF

  *a1 = a2;
  v6 = a1 + 1;
  a1[1] = 0;
  Matrix = GdipCreateMatrix(a1 + 1);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(Matrix, v8, v9, 38322268);
  WorldTransform = GdipGetWorldTransform(a2, *v6);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(WorldTransform, v11, v12, 38322269);
  v17 = 0;
  Gfx::GpMatrixHolder::operator=(&v17, a3);
  v13 = GdipSetWorldTransform(*a1, v17);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v13, v14, v15, 38322270);
  if ( v17 )
    GdipDeleteMatrix(v17);
  return a1;
}

```

## disassembly

```asm
0x18006151c  mov     [rsp+arg_10], rbx
0x180061521  mov     [rsp+arg_0], rcx
0x180061526  push    rsi
0x180061527  push    rdi
0x180061528  push    r14
0x18006152a  sub     rsp, 20h
0x18006152e  mov     rsi, r8
0x180061531  mov     rdi, rdx
0x180061534  mov     r14, rcx
0x180061537  mov     [rcx], rdx
0x18006153a  lea     rbx, [rcx+8]
0x18006153e  mov     qword ptr [rbx], 0
0x180061545  mov     rcx, rbx
0x180061548  call    cs:__imp_GdipCreateMatrix
0x18006154e  mov     r9d, 248C05Ch
0x180061554  mov     ecx, eax
0x180061556  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006155b  mov     rdx, [rbx]
0x18006155e  mov     rcx, rdi
0x180061561  call    cs:__imp_GdipGetWorldTransform
0x180061567  mov     r9d, 248C05Dh
0x18006156d  mov     ecx, eax
0x18006156f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180061574  mov     [rsp+38h+arg_8], 0
0x18006157d  mov     rdx, rsi
0x180061580  lea     rcx, [rsp+38h+arg_8]
0x180061585  call    ??4GpMatrixHolder@Gfx@@QEAAXAEBU?$TAffine3x3@M@Math@@@Z; Gfx::GpMatrixHolder::operator=(Math::TAffine3x3<float> const &)
0x18006158a  nop
0x18006158b  mov     rdx, [rsp+38h+arg_8]
0x180061590  mov     rcx, [r14]
0x180061593  call    cs:__imp_GdipSetWorldTransform
0x180061599  mov     r9d, 248C05Eh
0x18006159f  mov     ecx, eax
0x1800615a1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800615a6  nop
0x1800615a7  mov     rcx, [rsp+38h+arg_8]
0x1800615ac  test    rcx, rcx
0x1800615af  jz      short loc_1800615B8
0x1800615b1  call    cs:__imp_GdipDeleteMatrix
0x1800615b7  nop
0x1800615b8  mov     rax, r14
0x1800615bb  mov     rbx, [rsp+38h+arg_10]
0x1800615c0  add     rsp, 20h
0x1800615c4  pop     r14
0x1800615c6  pop     rdi
0x1800615c7  pop     rsi
0x1800615c8  retn
```
