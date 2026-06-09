# GetEmpty(GeoDataAllocator *)

- ea: `0x10040ddc0`
- end: `0x10040de65`
- name: `?GetEmpty@@YAJPEAUGeoDataAllocator@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(struct GeoDataAllocator *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x10040fad0`
- `0x100415040`
- `0x1004162a0`
- `0x100418440`
- `0x10041a990`

## callees

- `0x10040d210`
- `0x10040ddc0`
- `0x100421170`
- `0x100424ba0`
- `0x100425400`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall GetEmpty(struct GeoDataAllocator *a1)
{
  __int64 v1; // r8
  __int64 v2; // r9
  int v3; // ebx
  __int64 v5; // [rsp+20h] [rbp-108h] BYREF
  char v6; // [rsp+28h] [rbp-100h]
  __int64 v7; // [rsp+30h] [rbp-F8h]
  __int64 v8; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE v9[24]; // [rsp+48h] [rbp-E0h] BYREF
  _BYTE v10[24]; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE v11[24]; // [rsp+78h] [rbp-B0h] BYREF
  _BYTE v12[112]; // [rsp+90h] [rbp-98h] BYREF
  int v13; // [rsp+100h] [rbp-28h]

  v7 = -2;
  GeometryDataBuilder::GeometryDataBuilder((GeometryDataBuilder *)&v8, a1, 0);
  v13 = 1;
  v5 = -1;
  v6 = 7;
  v3 = ArrayOverPages<Shape,SOS_Or_CRT_Allocator<Shape>>::Add(v11, &v5, v1, v2);
  if ( v3 >= 0 )
    v3 = GeometryDataBuilder::EndGeometry((GeometryDataBuilder *)&v8, 1);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v12);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v11);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v10);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v9);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x10040ddc0  push    rbx
0x10040ddc2  sub     rsp, 120h
0x10040ddc9  mov     [rsp+128h+var_F8], 0FFFFFFFFFFFFFFFEh
0x10040ddd2  xor     r8d, r8d; struct COriginalPoints *
0x10040ddd5  mov     rdx, rcx; struct GeoDataAllocator *
0x10040ddd8  lea     rcx, [rsp+128h+var_E8]; this
0x10040dddd  call    ??0GeometryDataBuilder@@QEAA@PEAUGeoDataAllocator@@PEAVCOriginalPoints@@@Z; GeometryDataBuilder::GeometryDataBuilder(GeoDataAllocator *,COriginalPoints *)
0x10040dde2  nop
0x10040dde3  mov     [rsp+128h+var_28], 1
0x10040ddee  mov     [rsp+128h+var_108], 0FFFFFFFFFFFFFFFFh
0x10040ddf7  mov     [rsp+128h+var_100], 7
0x10040ddfc  lea     rdx, [rsp+128h+var_108]
0x10040de01  lea     rcx, [rsp+128h+var_B0]
0x10040de06  call    ?Add@?$ArrayOverPages@UShape@@V?$SOS_Or_CRT_Allocator@UShape@@@@@@QEAAJAEBUShape@@@Z; ArrayOverPages<Shape,SOS_Or_CRT_Allocator<Shape>>::Add(Shape const &)
0x10040de0b  mov     ebx, eax
0x10040de0d  test    eax, eax
0x10040de0f  js      short loc_10040DE1F
0x10040de11  mov     dl, 1; bool
0x10040de13  lea     rcx, [rsp+128h+var_E8]; this
0x10040de18  call    ?EndGeometry@GeometryDataBuilder@@UEAAJ_N@Z; GeometryDataBuilder::EndGeometry(bool)
0x10040de1d  mov     ebx, eax
0x10040de1f  lea     rcx, [rsp+128h+var_98]
0x10040de27  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040de2c  nop
0x10040de2d  lea     rcx, [rsp+128h+var_B0]
0x10040de32  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040de37  nop
0x10040de38  lea     rcx, [rsp+128h+var_C8]
0x10040de3d  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040de42  nop
0x10040de43  lea     rcx, [rsp+128h+var_E0]
0x10040de48  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040de4d  nop
0x10040de4e  lea     rax, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x10040de55  mov     [rsp+128h+var_E8], rax
0x10040de5a  mov     eax, ebx
0x10040de5c  add     rsp, 120h
0x10040de63  pop     rbx
0x10040de64  retn
```
