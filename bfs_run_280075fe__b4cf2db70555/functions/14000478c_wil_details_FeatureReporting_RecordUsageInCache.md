# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000478c`
- end: `0x140004909`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004998`

## callees

- `0x1400045e0`
- `0x1400046b0`
- `0x14000478c`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  _DWORD *v6; // r9
  unsigned int v7; // r10d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 i; // edx
  signed __int32 v16; // r10d
  signed __int32 v17; // eax

  v6 = (_DWORD *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_32;
    case 1u:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_31;
  }
  if ( a3 - 6 >= 2 )
  {
    v7 = a3 - 320;
    if ( (int)(a3 - 320) >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return v6;
  }
LABEL_17:
  v11 = 0;
  v12 = a3 - 2;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 3;
      if ( v14 )
      {
        if ( v14 == 1 )
          v11 = 16;
      }
      else
      {
        v11 = 4;
      }
    }
    else
    {
      v11 = 8;
    }
  }
  else
  {
    v11 = 2;
  }
  for ( i = *a2; ; i = v17 )
  {
    v16 = i | v11 | 1;
    v6[4] = (i | v11) == i;
    if ( (i | v11) == i )
      v16 = i | v11;
    v17 = _InterlockedCompareExchange(a2, v16, i);
    if ( i == v17 )
      break;
  }
  *v6 = (v16 & 1) != 0 && (i & 1) == 0;
  return v6;
}

```

## disassembly

```asm
0x14000478c  mov     [rsp+arg_0], rbx
0x140004791  push    rdi
0x140004792  sub     rsp, 20h
0x140004796  xor     eax, eax
0x140004798  xorps   xmm0, xmm0
0x14000479b  mov     edi, r9d
0x14000479e  mov     r11, rdx
0x1400047a1  mov     r9, rcx
0x1400047a4  mov     r10d, r8d
0x1400047a7  movups  xmmword ptr [rcx], xmm0
0x1400047aa  mov     [rcx+10h], rax
0x1400047ae  test    r8d, r8d
0x1400047b1  jz      loc_1400048EF
0x1400047b7  sub     r10d, 1
0x1400047bb  jz      loc_1400048E2
0x1400047c1  sub     r10d, 1
0x1400047c5  jz      loc_140004864
0x1400047cb  sub     r10d, 1
0x1400047cf  jz      loc_140004864
0x1400047d5  sub     r10d, 1
0x1400047d9  jz      loc_1400048EF
0x1400047df  sub     r10d, 1
0x1400047e3  jz      loc_1400048E2
0x1400047e9  sub     r10d, 1
0x1400047ed  jz      short loc_140004864
0x1400047ef  cmp     r10d, 1
0x1400047f3  jz      short loc_140004864
0x1400047f5  lea     r10d, [r8-140h]
0x1400047fc  cmp     r10d, 40h ; '@'
0x140004800  jge     short loc_14000484F
0x140004802  mov     eax, [rdx+4]
0x140004805  mov     ebx, r10d
0x140004808  shl     ebx, 5
0x14000480b  mov     ecx, 10h
0x140004810  test    cl, al
0x140004812  jz      short loc_140004828
0x140004814  mov     edx, eax
0x140004816  shr     edx, 5
0x140004819  and     edx, 3Fh
0x14000481c  cmp     edx, r10d
0x14000481f  jnz     short loc_140004828
0x140004821  mov     edx, 1
0x140004826  jmp     short loc_14000482A
0x140004828  xor     edx, edx
0x14000482a  mov     [r9+10h], edx
0x14000482e  mov     edx, ebx
0x140004830  xor     edx, eax
0x140004832  and     edx, 7E0h
0x140004838  xor     edx, eax
0x14000483a  or      edx, ecx
0x14000483c  lock cmpxchg [r11+4], edx
0x140004842  jnz     short loc_140004810
0x140004844  cmp     dword ptr [r9+10h], 0
0x140004849  jnz     loc_1400048FA
0x14000484f  mov     [r9+8], r8d
0x140004853  mov     dword ptr [r9+4], 1
0x14000485b  mov     [r9+0Ch], edi
0x14000485f  jmp     loc_1400048FA
0x140004864  xor     ecx, ecx
0x140004866  sub     r8d, 2
0x14000486a  jz      short loc_140004892
0x14000486c  sub     r8d, 1
0x140004870  jz      short loc_14000488B
0x140004872  sub     r8d, 3
0x140004876  jz      short loc_140004884
0x140004878  cmp     r8d, 1
0x14000487c  jnz     short loc_140004897
0x14000487e  lea     ecx, [r8+0Fh]
0x140004882  jmp     short loc_140004897
0x140004884  mov     ecx, 4
0x140004889  jmp     short loc_140004897
0x14000488b  mov     ecx, 8
0x140004890  jmp     short loc_140004897
0x140004892  mov     ecx, 2
0x140004897  mov     edx, [rdx]
0x140004899  xor     eax, eax
0x14000489b  mov     r8d, ecx
0x14000489e  or      r8d, edx
0x1400048a1  cmp     r8d, edx
0x1400048a4  mov     r10d, r8d
0x1400048a7  setz    al
0x1400048aa  or      r10d, 1
0x1400048ae  cmp     r8d, edx
0x1400048b1  mov     [r9+10h], eax
0x1400048b5  mov     eax, edx
0x1400048b7  cmovz   r10d, r8d
0x1400048bb  lock cmpxchg [r11], r10d
0x1400048c0  jz      short loc_1400048C6
0x1400048c2  mov     edx, eax
0x1400048c4  jmp     short loc_140004899
0x1400048c6  test    r10b, 1
0x1400048ca  setnz   cl
0x1400048cd  test    dl, 1
0x1400048d0  setz    al
0x1400048d3  test    al, cl
0x1400048d5  mov     eax, 0
0x1400048da  setnz   al
0x1400048dd  mov     [r9], eax
0x1400048e0  jmp     short loc_1400048FA
0x1400048e2  mov     edx, r8d
0x1400048e5  mov     rcx, r11
0x1400048e8  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1400048ed  jmp     short loc_1400048FA
0x1400048ef  mov     edx, r8d
0x1400048f2  mov     rcx, r11
0x1400048f5  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1400048fa  mov     rbx, [rsp+28h+arg_0]
0x1400048ff  mov     rax, r9
0x140004902  add     rsp, 20h
0x140004906  pop     rdi
0x140004907  retn
```
