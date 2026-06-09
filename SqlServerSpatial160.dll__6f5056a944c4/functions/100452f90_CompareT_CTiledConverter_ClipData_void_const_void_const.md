# CompareT<CTiledConverter::ClipData>(void const *,void const *)

- ea: `0x100452f90`
- end: `0x100452fbc`
- name: `??$CompareT@UClipData@CTiledConverter@@@@YAHPEBX0@Z`
- size: `44`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100452f90`

## pseudocode

```c
__int64 __fastcall CompareT<CTiledConverter::ClipData>(double *a1, double *a2)
{
  double v2; // xmm3_8
  double v3; // xmm2_8

  v2 = a2[3];
  v3 = a1[3];
  if ( v2 <= v3 )
    return v3 > v2;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x100452f90  sub     rsp, 38h
0x100452f94  movsd   xmm3, qword ptr [rdx+18h]
0x100452f99  movsd   xmm2, qword ptr [rcx+18h]
0x100452f9e  comisd  xmm3, xmm2
0x100452fa2  jbe     short loc_100452FAE
0x100452fa4  mov     eax, 0FFFFFFFFh
0x100452fa9  add     rsp, 38h
0x100452fad  retn
0x100452fae  xor     eax, eax
0x100452fb0  comisd  xmm2, xmm3
0x100452fb4  setnbe  al
0x100452fb7  add     rsp, 38h
0x100452fbb  retn
```
