# CGeodeticRTree::UpdateEnvelope(CRTree::Envelope const &,CRTree::Envelope &)

- ea: `0x100455d50`
- end: `0x100455e10`
- name: `?UpdateEnvelope@CGeodeticRTree@@MEBAXAEBUEnvelope@CRTree@@AEAU23@@Z`
- size: `192`
- prototype: `void __fastcall(CGeodeticRTree *__hidden this, const struct CRTree::Envelope *, struct CRTree::Envelope *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x100408bc0`
- `0x100408db0`
- `0x1004676d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CGeodeticRTree::UpdateEnvelope(
        CGeodeticRTree *this,
        const struct CRTree::Envelope *a2,
        struct CRTree::Envelope *a3)
{
  __int64 v5; // xmm2_8
  __int64 v6; // xmm2_8
  __int128 v7; // [rsp+20h] [rbp-E8h] BYREF
  __int64 v8; // [rsp+30h] [rbp-D8h]
  __int64 v9; // [rsp+38h] [rbp-D0h]
  _BYTE v10[16]; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v11; // [rsp+50h] [rbp-B8h]
  __int128 v12; // [rsp+60h] [rbp-A8h]
  _BYTE v13[104]; // [rsp+A0h] [rbp-68h] BYREF

  v9 = -2;
  v5 = *((_QWORD *)a3 + 2);
  v7 = *(_OWORD *)a3;
  v8 = v5;
  CCap::CCap((CCap *)v10, *((double *)a3 + 3), (const struct CPoint3D *)&v7);
  v6 = *((_QWORD *)a2 + 2);
  v7 = *(_OWORD *)a2;
  v8 = v6;
  CCap::CCap((CCap *)v13, *((double *)a2 + 3), (const struct CPoint3D *)&v7);
  CCap::UnionWith((CCap *)v10, (const struct CCap *)v13);
  *(_OWORD *)a3 = v11;
  *((_OWORD *)a3 + 1) = v12;
  CCap::~CCap((CCap *)v13);
  CCap::~CCap((CCap *)v10);
}

```

## disassembly

```asm
0x100455d50  push    rdi
0x100455d52  sub     rsp, 100h
0x100455d59  mov     [rsp+108h+var_D0], 0FFFFFFFFFFFFFFFEh
0x100455d62  mov     [rsp+108h+arg_0], rbx
0x100455d6a  mov     rdi, r8
0x100455d6d  mov     rbx, rdx
0x100455d70  movsd   xmm2, qword ptr [r8+10h]
0x100455d76  movups  xmm0, xmmword ptr [r8]
0x100455d7a  movups  [rsp+108h+var_E8], xmm0
0x100455d7f  movsd   [rsp+108h+var_D8], xmm2
0x100455d85  lea     r8, [rsp+108h+var_E8]; struct CPoint3D *
0x100455d8a  movsd   xmm1, qword ptr [rdi+18h]; double
0x100455d8f  lea     rcx, [rsp+108h+var_C8]; this
0x100455d94  call    ??0CCap@@QEAA@NAEBVCPoint3D@@@Z; CCap::CCap(double,CPoint3D const &)
0x100455d99  nop
0x100455d9a  movsd   xmm2, qword ptr [rbx+10h]
0x100455d9f  movups  xmm0, xmmword ptr [rbx]
0x100455da2  movups  [rsp+108h+var_E8], xmm0
0x100455da7  movsd   [rsp+108h+var_D8], xmm2
0x100455dad  lea     r8, [rsp+108h+var_E8]; struct CPoint3D *
0x100455db2  movsd   xmm1, qword ptr [rbx+18h]; double
0x100455db7  lea     rcx, [rsp+108h+var_68]; this
0x100455dbf  call    ??0CCap@@QEAA@NAEBVCPoint3D@@@Z; CCap::CCap(double,CPoint3D const &)
0x100455dc4  lea     rdx, [rsp+108h+var_68]; struct CCap *
0x100455dcc  lea     rcx, [rsp+108h+var_C8]; this
0x100455dd1  call    ?UnionWith@CCap@@QEAAXAEBV1@@Z; CCap::UnionWith(CCap const &)
0x100455dd6  movaps  xmm0, [rsp+108h+var_B8]
0x100455ddb  movups  xmmword ptr [rdi], xmm0
0x100455dde  movaps  xmm0, [rsp+108h+var_A8]
0x100455de3  movups  xmmword ptr [rdi+10h], xmm0
0x100455de7  lea     rcx, [rsp+108h+var_68]; this
0x100455def  call    ??1CCap@@UEAA@XZ; CCap::~CCap(void)
0x100455df4  nop
0x100455df5  lea     rcx, [rsp+108h+var_C8]; this
0x100455dfa  call    ??1CCap@@UEAA@XZ; CCap::~CCap(void)
0x100455dff  mov     rbx, [rsp+108h+arg_0]
0x100455e07  add     rsp, 100h
0x100455e0e  pop     rdi
0x100455e0f  retn
```
