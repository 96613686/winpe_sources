# CompareT<CGeodeticScannerConstruction::CPointFigure>(void const *,void const *)

- ea: `0x1004654e0`
- end: `0x10046550c`
- name: `??$CompareT@VCPointFigure@CGeodeticScannerConstruction@@@@YAHPEBX0@Z`
- size: `44`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1004654e0`

## pseudocode

```c
__int64 __fastcall CompareT<CGeodeticScannerConstruction::CPointFigure>(double *a1, double *a2)
{
  double v2; // xmm2_8
  double v3; // xmm1_8

  v2 = a2[1];
  v3 = a1[1];
  if ( v2 <= v3 )
    return v3 > v2;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1004654e0  sub     rsp, 28h
0x1004654e4  movsd   xmm2, qword ptr [rdx+8]
0x1004654e9  movsd   xmm1, qword ptr [rcx+8]
0x1004654ee  comisd  xmm2, xmm1
0x1004654f2  jbe     short loc_1004654FE
0x1004654f4  mov     eax, 0FFFFFFFFh
0x1004654f9  add     rsp, 28h
0x1004654fd  retn
0x1004654fe  xor     eax, eax
0x100465500  comisd  xmm1, xmm2
0x100465504  setnbe  al
0x100465507  add     rsp, 28h
0x10046550b  retn
```
