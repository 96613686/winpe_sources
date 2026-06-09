# CompareT<C1DGeometry::CIntervalBound>(void const *,void const *)

- ea: `0x100459600`
- end: `0x10045967c`
- name: `??$CompareT@VCIntervalBound@C1DGeometry@@@@YAHPEBX0@Z`
- size: `124`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100459600`

## pseudocode

```c
__int64 __fastcall CompareT<C1DGeometry::CIntervalBound>(double *a1, double *a2)
{
  double v2; // xmm4_8
  int v3; // edx
  double v4; // xmm3_8
  double v5; // xmm2_8
  double v6; // xmm1_8
  int v7; // ecx
  int v8; // eax
  int v9; // eax

  v2 = *a2;
  v3 = -1;
  v4 = *a1;
  *(_QWORD *)&v5 = *(_QWORD *)&v2 & _xmm;
  *(_QWORD *)&v6 = *(_QWORD *)a1 & _xmm;
  if ( COERCE_DOUBLE(*(_QWORD *)&v2 & _xmm) > v6 )
    return 0xFFFFFFFFLL;
  if ( v6 == v5 )
  {
    v7 = -1;
    v8 = -1;
    if ( v4 > 0.0 )
      v7 = 1;
    if ( v2 > 0.0 )
      v8 = 1;
    if ( v7 < v8 )
      return 0xFFFFFFFFLL;
  }
  if ( v6 > v5 )
    return 1;
  if ( v6 == v5 )
  {
    v9 = -1;
    if ( v4 > 0.0 )
      v9 = 1;
    if ( v2 > 0.0 )
      v3 = 1;
    if ( v9 > v3 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x100459600  movsd   xmm4, qword ptr [rdx]
0x100459604  mov     edx, 0FFFFFFFFh
0x100459609  movsd   xmm3, qword ptr [rcx]
0x10045960d  movaps  xmm2, xmm4
0x100459610  andps   xmm2, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x100459617  movaps  xmm1, xmm3
0x10045961a  andps   xmm1, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x100459621  comisd  xmm2, xmm1
0x100459625  ja      short loc_100459679
0x100459627  ucomisd xmm1, xmm2
0x10045962b  lea     r8d, [rdx+2]
0x10045962f  xorps   xmm0, xmm0
0x100459632  jp      short loc_10045964E
0x100459634  jnz     short loc_10045964E
0x100459636  comisd  xmm3, xmm0
0x10045963a  mov     ecx, edx
0x10045963c  mov     eax, edx
0x10045963e  cmova   ecx, r8d
0x100459642  comisd  xmm4, xmm0
0x100459646  cmova   eax, r8d
0x10045964a  cmp     ecx, eax
0x10045964c  jl      short loc_100459679
0x10045964e  comisd  xmm1, xmm2
0x100459652  ja      short loc_100459675
0x100459654  ucomisd xmm1, xmm2
0x100459658  jp      short loc_100459672
0x10045965a  jnz     short loc_100459672
0x10045965c  comisd  xmm3, xmm0
0x100459660  mov     eax, edx
0x100459662  cmova   eax, r8d
0x100459666  comisd  xmm4, xmm0
0x10045966a  cmova   edx, r8d
0x10045966e  cmp     eax, edx
0x100459670  jg      short loc_100459675
0x100459672  xor     eax, eax
0x100459674  retn
0x100459675  mov     eax, r8d
0x100459678  retn
0x100459679  mov     eax, edx
0x10045967b  retn
```
