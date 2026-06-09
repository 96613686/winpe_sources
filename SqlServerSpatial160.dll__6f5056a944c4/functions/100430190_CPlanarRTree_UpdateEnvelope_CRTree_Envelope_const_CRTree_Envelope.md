# CPlanarRTree::UpdateEnvelope(CRTree::Envelope const &,CRTree::Envelope &)

- ea: `0x100430190`
- end: `0x1004301e2`
- name: `?UpdateEnvelope@CPlanarRTree@@MEBAXAEBUEnvelope@CRTree@@AEAU23@@Z`
- size: `82`
- prototype: `void __fastcall(CPlanarRTree *__hidden this, const struct CRTree::Envelope *, struct CRTree::Envelope *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x100430190`

## pseudocode

```c
void __fastcall CPlanarRTree::UpdateEnvelope(
        CPlanarRTree *this,
        const struct CRTree::Envelope *a2,
        struct CRTree::Envelope *a3)
{
  double v3; // xmm1_8
  double v4; // xmm0_8
  double v5; // xmm0_8

  if ( *(double *)a3 > *(double *)a2 )
    *(_QWORD *)a3 = *(_QWORD *)a2;
  v3 = *((double *)a2 + 1);
  if ( *((double *)a3 + 1) > v3 )
    *((double *)a3 + 1) = v3;
  v4 = *((double *)a2 + 2);
  if ( v4 > *((double *)a3 + 2) )
    *((double *)a3 + 2) = v4;
  v5 = *((double *)a2 + 3);
  if ( v5 > *((double *)a3 + 3) )
    *((double *)a3 + 3) = v5;
}

```

## disassembly

```asm
0x100430190  movsd   xmm1, qword ptr [rdx]
0x100430194  movsd   xmm0, qword ptr [r8]
0x100430199  comisd  xmm0, xmm1
0x10043019d  jbe     short loc_1004301A4
0x10043019f  movsd   qword ptr [r8], xmm1
0x1004301a4  movsd   xmm1, qword ptr [rdx+8]
0x1004301a9  movsd   xmm0, qword ptr [r8+8]
0x1004301af  comisd  xmm0, xmm1
0x1004301b3  jbe     short loc_1004301BB
0x1004301b5  movsd   qword ptr [r8+8], xmm1
0x1004301bb  movsd   xmm0, qword ptr [rdx+10h]
0x1004301c0  comisd  xmm0, qword ptr [r8+10h]
0x1004301c6  jbe     short loc_1004301CE
0x1004301c8  movsd   qword ptr [r8+10h], xmm0
0x1004301ce  movsd   xmm0, qword ptr [rdx+18h]
0x1004301d3  comisd  xmm0, qword ptr [r8+18h]
0x1004301d9  jbe     short locret_1004301E1
0x1004301db  movsd   qword ptr [r8+18h], xmm0
0x1004301e1  retn
```
