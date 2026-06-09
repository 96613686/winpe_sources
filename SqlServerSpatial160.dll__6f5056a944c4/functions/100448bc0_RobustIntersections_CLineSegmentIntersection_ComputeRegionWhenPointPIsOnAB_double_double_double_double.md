# RobustIntersections::CLineSegmentIntersection::ComputeRegionWhenPointPIsOnAB(double,double,double,double)

- ea: `0x100448bc0`
- end: `0x100448c55`
- name: `?ComputeRegionWhenPointPIsOnAB@CLineSegmentIntersection@RobustIntersections@@CA?AW4REGION@12@NNNN@Z`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1004473b0`

## callees

- `0x100448bc0`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::ComputeRegionWhenPointPIsOnAB(
        double a1,
        double a2,
        double a3,
        double a4)
{
  __int64 result; // rax
  bool v5; // zf
  bool v6; // cc

  if ( a1 == 0.0 )
  {
    if ( a2 > 0.0 )
    {
      if ( a4 >= 0.0 )
      {
        if ( a4 != 0.0 )
        {
          if ( a2 > a4 )
            return 2;
          goto LABEL_7;
        }
        return 1;
      }
      return 0;
    }
    if ( a4 > 0.0 )
      return 0;
    if ( a4 == 0.0 )
      return 1;
    if ( a4 <= a2 )
    {
LABEL_7:
      v5 = a4 == a2;
      goto LABEL_23;
    }
    return 2;
  }
  if ( a1 <= 0.0 )
  {
    if ( a3 > 0.0 )
      return 0;
    if ( a3 == 0.0 )
      return 1;
    v6 = a3 <= a1;
  }
  else
  {
    if ( a3 < 0.0 )
      return 0;
    if ( a3 == 0.0 )
      return 1;
    v6 = a1 <= a3;
  }
  if ( !v6 )
    return 2;
  v5 = a3 == a1;
LABEL_23:
  result = 3;
  if ( !v5 )
    return 4;
  return result;
}

```

## disassembly

```asm
0x100448bc0  xorps   xmm4, xmm4
0x100448bc3  ucomisd xmm0, xmm4
0x100448bc7  jp      short loc_100448C14
0x100448bc9  jnz     short loc_100448C14
0x100448bcb  comisd  xmm1, xmm4
0x100448bcf  jbe     short loc_100448BF1
0x100448bd1  comisd  xmm4, xmm3
0x100448bd5  ja      short loc_100448BF7
0x100448bd7  ucomisd xmm3, xmm4
0x100448bdb  jp      short loc_100448BDF
0x100448bdd  jz      short loc_100448C02
0x100448bdf  comisd  xmm1, xmm3
0x100448be3  jbe     short loc_100448BEB
0x100448be5  mov     eax, 2
0x100448bea  retn
0x100448beb  ucomisd xmm3, xmm1
0x100448bef  jmp     short loc_100448C46
0x100448bf1  comisd  xmm3, xmm4
0x100448bf5  jbe     short loc_100448BFA
0x100448bf7  xor     eax, eax
0x100448bf9  retn
0x100448bfa  ucomisd xmm3, xmm4
0x100448bfe  jp      short loc_100448C08
0x100448c00  jnz     short loc_100448C08
0x100448c02  mov     eax, 1
0x100448c07  retn
0x100448c08  comisd  xmm3, xmm1
0x100448c0c  jbe     short loc_100448BEB
0x100448c0e  mov     eax, 2
0x100448c13  retn
0x100448c14  comisd  xmm0, xmm4
0x100448c18  jbe     short loc_100448C2E
0x100448c1a  comisd  xmm4, xmm2
0x100448c1e  ja      short loc_100448BF7
0x100448c20  ucomisd xmm2, xmm4
0x100448c24  jp      short loc_100448C28
0x100448c26  jz      short loc_100448C02
0x100448c28  comisd  xmm0, xmm2
0x100448c2c  jmp     short loc_100448C40
0x100448c2e  comisd  xmm2, xmm4
0x100448c32  ja      short loc_100448BF7
0x100448c34  ucomisd xmm2, xmm4
0x100448c38  jp      short loc_100448C3C
0x100448c3a  jz      short loc_100448C02
0x100448c3c  comisd  xmm2, xmm0
0x100448c40  ja      short loc_100448C0E
0x100448c42  ucomisd xmm2, xmm0
0x100448c46  jp      short loc_100448C4F
0x100448c48  mov     eax, 3
0x100448c4d  jz      short locret_100448C54
0x100448c4f  mov     eax, 4
0x100448c54  retn
```
