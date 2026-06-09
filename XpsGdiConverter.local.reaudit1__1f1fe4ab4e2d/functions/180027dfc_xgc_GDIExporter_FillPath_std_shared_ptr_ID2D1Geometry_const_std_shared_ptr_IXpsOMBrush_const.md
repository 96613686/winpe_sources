# xgc::GDIExporter::FillPath(std::shared_ptr<ID2D1Geometry> const &,std::shared_ptr<IXpsOMBrush> const &)

- ea: `0x180027dfc`
- end: `0x180027ecd`
- name: `?FillPath@GDIExporter@xgc@@AEAAXAEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBV?$shared_ptr@UIXpsOMBrush@@@4@@Z`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180016afc`
- `0x180028f54`

## callees

- `0x180025488`
- `0x180027cd4`
- `0x180027d3c`
- `0x180027dfc`
- `0x180030284`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall xgc::GDIExporter::FillPath(
        __int64 a1,
        _QWORD *a2,
        __int64 (__fastcall ****a3)(__int64, GUID *, __int64 *))
{
  __int64 v5; // r11
  float v6; // xmm2_4
  int v7; // eax
  int v8; // edx
  const char *v9; // r8
  int v10; // r9d
  _BYTE v11[24]; // [rsp+30h] [rbp-88h] BYREF
  xpsrdr *v12; // [rsp+48h] [rbp-70h]
  char v13; // [rsp+C0h] [rbp+8h] BYREF

  xgc::CGDIPathData::CGDIPathData(v11, *(_QWORD *)(a1 + 8), 1, a1 + 4);
  v6 = *(float *)(xgc::CDeviceContext::CurrentScale(*(_QWORD *)(v5 + 8), &v13) + 4);
  if ( COERCE_FLOAT(LODWORD(v6) & _xmm) < 0.00000011920929 )
    v6 = FLOAT_1_0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*a2 + 72LL))(*a2, 0, 0);
  if ( v7 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v7, v8, v9, v10);
  if ( (int)v12 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, v8, v9, v10);
  xgc::CGDIPathData::Fill((xgc::CGDIPathData *)v11, a3, (__int64)v9, 0.050000001 / v6);
  xgc::CGDIPathData::~CGDIPathData((xgc::CGDIPathData *)v11);
}

```

## disassembly

```asm
0x180027dfc  mov     [rsp+arg_8], rbx
0x180027e01  push    rdi
0x180027e02  sub     rsp, 0B0h
0x180027e09  mov     rbx, r8
0x180027e0c  mov     rdi, rdx
0x180027e0f  mov     r11, rcx
0x180027e12  lea     r9, [rcx+4]
0x180027e16  mov     r8d, 1
0x180027e1c  mov     rdx, [rcx+8]
0x180027e20  lea     rcx, [rsp+0B8h+var_88]
0x180027e25  call    ??0CGDIPathData@xgc@@QEAA@AEAVCDeviceContext@1@W4Enum@PathDataPurpose@1@AEAUSqmDWordCounter@1@@Z; xgc::CGDIPathData::CGDIPathData(xgc::CDeviceContext &,xgc::PathDataPurpose::Enum,xgc::SqmDWordCounter &)
0x180027e2a  nop
0x180027e2b  lea     rdx, [rsp+0B8h+arg_0]
0x180027e33  mov     rcx, [r11+8]
0x180027e37  call    ?CurrentScale@CDeviceContext@xgc@@QEBA?AUMinMaxScaling@xpsrdr@@XZ; xgc::CDeviceContext::CurrentScale(void)
0x180027e3c  movss   xmm2, dword ptr [rax+4]
0x180027e41  movaps  xmm1, xmm2
0x180027e44  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180027e4b  movss   xmm0, cs:__real@34000000
0x180027e53  comiss  xmm0, xmm1
0x180027e56  jbe     short loc_180027E60
0x180027e58  movss   xmm2, cs:__real@3f800000
0x180027e60  mov     rcx, [rdi]
0x180027e63  mov     rax, [rcx]
0x180027e66  movss   xmm3, cs:__real@3d4ccccd
0x180027e6e  divss   xmm3, xmm2
0x180027e72  lea     rdx, [rsp+0B8h+var_88]
0x180027e77  mov     [rsp+0B8h+var_98], rdx
0x180027e7c  xor     r8d, r8d
0x180027e7f  xor     edx, edx
0x180027e81  mov     rax, [rax+48h]
0x180027e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e8a  test    eax, eax
0x180027e8c  jns     short loc_180027E96
0x180027e8e  mov     ecx, eax; this
0x180027e90  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180027e96  mov     ecx, dword ptr [rsp+0B8h+var_70]; this
0x180027e9a  test    ecx, ecx
0x180027e9c  jns     short loc_180027EA4
0x180027e9e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180027ea4  mov     rdx, rbx
0x180027ea7  lea     rcx, [rsp+0B8h+var_88]; this
0x180027eac  call    ?Fill@CGDIPathData@xgc@@QEBAXAEBV?$shared_ptr@UIXpsOMBrush@@@std@@@Z; xgc::CGDIPathData::Fill(std::shared_ptr<IXpsOMBrush> const &)
0x180027eb1  nop
0x180027eb2  lea     rcx, [rsp+0B8h+var_88]; this
0x180027eb7  call    ??1CGDIPathData@xgc@@UEAA@XZ; xgc::CGDIPathData::~CGDIPathData(void)
0x180027ebc  mov     rbx, [rsp+0B8h+arg_8]
0x180027ec4  add     rsp, 0B0h
0x180027ecb  pop     rdi
0x180027ecc  retn
```
