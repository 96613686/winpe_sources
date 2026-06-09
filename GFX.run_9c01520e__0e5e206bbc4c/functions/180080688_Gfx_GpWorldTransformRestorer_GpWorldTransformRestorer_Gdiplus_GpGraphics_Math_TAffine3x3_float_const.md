# Gfx::GpWorldTransformRestorer::GpWorldTransformRestorer(Gdiplus::GpGraphics &,Math::TAffine3x3<float> const &)

- ea: `0x180080688`
- end: `0x180080735`
- name: `??0GpWorldTransformRestorer@Gfx@@QEAA@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@M@Math@@@Z`
- size: `173`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180080644`
- `0x1800be430`
- `0x18015d2b8`
- `0x18017ccf4`

## callees

- `0x18007f398`
- `0x18007f754`
- `0x180080688`

## import_xrefs

- `gdiplus!GdipGetWorldTransform` at `0x1800806cd`
- `gdiplus!GdipGetWorldTransform` at `0x1800806cd`
- `gdiplus!GdipSetWorldTransform` at `0x1800806ff`
- `gdiplus!GdipSetWorldTransform` at `0x1800806ff`
- `gdiplus!GdipCreateMatrix` at `0x1800806b4`
- `gdiplus!GdipCreateMatrix` at `0x1800806b4`
- `gdiplus!GdipDeleteMatrix` at `0x18008071d`
- `gdiplus!GdipDeleteMatrix` at `0x18008071d`

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
0x180080688  mov     [rsp+arg_10], rbx
0x18008068d  mov     [rsp+arg_0], rcx
0x180080692  push    rsi
0x180080693  push    rdi
0x180080694  push    r14
0x180080696  sub     rsp, 20h
0x18008069a  mov     rsi, r8
0x18008069d  mov     rdi, rdx
0x1800806a0  mov     r14, rcx
0x1800806a3  mov     [rcx], rdx
0x1800806a6  lea     rbx, [rcx+8]
0x1800806aa  mov     qword ptr [rbx], 0
0x1800806b1  mov     rcx, rbx
0x1800806b4  call    cs:__imp_GdipCreateMatrix
0x1800806ba  mov     r9d, 248C05Ch
0x1800806c0  mov     ecx, eax
0x1800806c2  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800806c7  mov     rdx, [rbx]
0x1800806ca  mov     rcx, rdi
0x1800806cd  call    cs:__imp_GdipGetWorldTransform
0x1800806d3  mov     r9d, 248C05Dh
0x1800806d9  mov     ecx, eax
0x1800806db  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800806e0  mov     [rsp+38h+arg_8], 0
0x1800806e9  mov     rdx, rsi
0x1800806ec  lea     rcx, [rsp+38h+arg_8]
0x1800806f1  call    ??4GpMatrixHolder@Gfx@@QEAAXAEBU?$TAffine3x3@M@Math@@@Z; Gfx::GpMatrixHolder::operator=(Math::TAffine3x3<float> const &)
0x1800806f6  nop
0x1800806f7  mov     rdx, [rsp+38h+arg_8]
0x1800806fc  mov     rcx, [r14]
0x1800806ff  call    cs:__imp_GdipSetWorldTransform
0x180080705  mov     r9d, 248C05Eh
0x18008070b  mov     ecx, eax
0x18008070d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180080712  nop
0x180080713  mov     rcx, [rsp+38h+arg_8]
0x180080718  test    rcx, rcx
0x18008071b  jz      short loc_180080724
0x18008071d  call    cs:__imp_GdipDeleteMatrix
0x180080723  nop
0x180080724  mov     rax, r14
0x180080727  mov     rbx, [rsp+38h+arg_10]
0x18008072c  add     rsp, 20h
0x180080730  pop     r14
0x180080732  pop     rdi
0x180080733  pop     rsi
0x180080734  retn
```
