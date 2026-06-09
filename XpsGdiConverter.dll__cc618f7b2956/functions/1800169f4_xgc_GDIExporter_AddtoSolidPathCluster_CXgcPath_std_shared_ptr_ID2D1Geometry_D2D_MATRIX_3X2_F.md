# xgc::GDIExporter::AddtoSolidPathCluster(CXgcPath *,std::shared_ptr<ID2D1Geometry> &,D2D_MATRIX_3X2_F)

- ea: `0x1800169f4`
- end: `0x180016ab5`
- name: `?AddtoSolidPathCluster@GDIExporter@xgc@@QEAAXPEAVCXgcPath@@AEAV?$shared_ptr@UID2D1Geometry@@@std@@UD2D_MATRIX_3X2_F@@@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800192f0`

## callees

- `0x18000d61c`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e990`
- `0x180011b0c`
- `0x1800169f4`
- `0x18002a16c`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
double __fastcall xgc::GDIExporter::AddtoSolidPathCluster(__int64 a1)
{
  __int64 v2; // r8
  _QWORD *v3; // r10
  __int64 v4; // r11
  __int64 v5; // rcx
  int v6; // ebx
  int v7; // edx
  const char *v8; // r8
  int v9; // r9d
  SolidPathCluster *v10; // r9
  unsigned int v12[4]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v13[16]; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v14[5]; // [rsp+50h] [rbp-28h] BYREF

  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v13);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(v2) )
  {
    v12[0] = 0;
    v5 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL);
    v14[0] = 0;
    v14[1] = v12;
    v14[2] = v13;
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD *))(*(_QWORD *)v5 + 72LL))(v5, *v3, v4, v14);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v14);
    if ( (v12[0] & 0x80000000) != 0 )
      xpsrdr::ThrowHRException((xpsrdr *)v12[0], v7, v8, v9);
    if ( v6 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v6, v7, v8, v9);
  }
  std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(v12, v13);
  SolidPathCluster::PushXgcPath(v10);
  return std::_Ptr_base<ID2D1RenderTarget>::_Decref(v13);
}

```

## disassembly

```asm
0x1800169f4  push    rbp
0x1800169f6  push    rbx
0x1800169f7  push    rsi
0x1800169f8  push    rdi
0x1800169f9  mov     rbp, rsp
0x1800169fc  sub     rsp, 78h
0x180016a00  mov     r11, r9
0x180016a03  mov     r10, r8
0x180016a06  mov     rsi, rdx
0x180016a09  mov     rdi, rcx
0x180016a0c  lea     rcx, [rbp+var_38]
0x180016a10  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180016a15  nop
0x180016a16  mov     rcx, r8
0x180016a19  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180016a1e  test    al, al
0x180016a20  jz      short loc_180016A83
0x180016a22  mov     [rbp+var_48], 0
0x180016a29  mov     rax, [rdi+18h]
0x180016a2d  mov     rcx, [rax+10h]
0x180016a31  mov     [rbp+var_28], 0
0x180016a39  lea     rax, [rbp+var_48]
0x180016a3d  mov     [rbp+var_20], rax
0x180016a41  lea     rax, [rbp+var_38]
0x180016a45  mov     [rbp+var_18], rax
0x180016a49  mov     rax, [rcx]
0x180016a4c  lea     r9, [rbp+var_28]
0x180016a50  mov     r8, r11
0x180016a53  mov     rdx, [r10]
0x180016a56  mov     rax, [rax+48h]
0x180016a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a5f  mov     ebx, eax
0x180016a61  lea     rcx, [rbp+var_28]
0x180016a65  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180016a6a  mov     ecx, [rbp+var_48]; this
0x180016a6d  test    ecx, ecx
0x180016a6f  jns     short loc_180016A77
0x180016a71  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180016a77  test    ebx, ebx
0x180016a79  jns     short loc_180016A83
0x180016a7b  mov     ecx, ebx; this
0x180016a7d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180016a83  mov     r9, [rdi+58h]
0x180016a87  lea     rdx, [rbp+var_38]
0x180016a8b  lea     rcx, [rbp+var_48]
0x180016a8f  call    ??$?0UID2D1TransformedGeometry@@$0A@@?$shared_ptr@UID2D1Geometry@@@std@@QEAA@AEBV?$shared_ptr@UID2D1TransformedGeometry@@@1@@Z; std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(std::shared_ptr<ID2D1TransformedGeometry> const &)
0x180016a94  mov     r8, rax
0x180016a97  mov     rdx, rsi
0x180016a9a  mov     rcx, r9; this
0x180016a9d  call    ?PushXgcPath@SolidPathCluster@@QEAAXPEAVCXgcPath@@V?$shared_ptr@UID2D1Geometry@@@std@@@Z; SolidPathCluster::PushXgcPath(CXgcPath *,std::shared_ptr<ID2D1Geometry>)
0x180016aa2  nop
0x180016aa3  lea     rcx, [rbp+var_38]
0x180016aa7  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180016aac  add     rsp, 78h
0x180016ab0  pop     rdi
0x180016ab1  pop     rsi
0x180016ab2  pop     rbx
0x180016ab3  pop     rbp
0x180016ab4  retn
```
