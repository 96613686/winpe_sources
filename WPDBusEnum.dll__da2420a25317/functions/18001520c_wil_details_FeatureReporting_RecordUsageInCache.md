# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001520c`
- end: `0x180015382`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014ed8`

## callees

- `0x180015060`
- `0x180015130`
- `0x18001520c`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r9d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 i; // edx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_31;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v5 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
      goto LABEL_16;
    v6 = *((_DWORD *)a2 + 1);
    do
    {
      v7 = (v6 & 0x10) != 0 && ((v6 >> 5) & 0x3F) == v5;
      *(_DWORD *)(a1 + 16) = v7;
      v8 = v6;
      v6 = _InterlockedCompareExchange(
             a2 + 1,
             v6 ^ ((unsigned __int16)v6 ^ (unsigned __int16)(32 * v5)) & 0x7E0 | 0x10,
             v6);
    }
    while ( v8 != v6 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
    }
    return a1;
  }
LABEL_17:
  v9 = 0;
  v10 = a3 - 2;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( v12 )
      {
        if ( v12 == 1 )
          v9 = 16;
      }
      else
      {
        v9 = 4;
      }
    }
    else
    {
      v9 = 8;
    }
  }
  else
  {
    v9 = 2;
  }
  for ( i = *a2; ; i = v15 )
  {
    v14 = i | v9 | 1;
    *(_DWORD *)(a1 + 16) = (i | v9) == i;
    if ( (i | v9) == i )
      v14 = i | v9;
    v15 = _InterlockedCompareExchange(a2, v14, i);
    if ( i == v15 )
      break;
  }
  *(_DWORD *)a1 = (v14 & 1) != 0 && (i & 1) == 0;
  return a1;
}

```

## disassembly

```asm
0x18001520c  push    rbx
0x18001520e  sub     rsp, 20h
0x180015212  xor     eax, eax
0x180015214  xorps   xmm0, xmm0
0x180015217  mov     r10, rdx
0x18001521a  mov     rbx, rcx
0x18001521d  mov     r9d, r8d
0x180015220  movups  xmmword ptr [rcx], xmm0
0x180015223  mov     [rcx+10h], rax
0x180015227  test    r8d, r8d
0x18001522a  jz      loc_18001536B
0x180015230  sub     r9d, 1
0x180015234  jz      loc_18001535B
0x18001523a  sub     r9d, 1
0x18001523e  jz      loc_1800152DF
0x180015244  sub     r9d, 1
0x180015248  jz      loc_1800152DF
0x18001524e  sub     r9d, 1
0x180015252  jz      loc_18001536B
0x180015258  sub     r9d, 1
0x18001525c  jz      loc_18001535B
0x180015262  sub     r9d, 1
0x180015266  jz      short loc_1800152DF
0x180015268  cmp     r9d, 1
0x18001526c  jz      short loc_1800152DF
0x18001526e  lea     r9d, [r8-140h]
0x180015275  cmp     r9d, 40h ; '@'
0x180015279  jge     short loc_1800152C8
0x18001527b  mov     eax, [rdx+4]
0x18001527e  mov     r11d, r9d
0x180015281  shl     r11d, 5
0x180015285  mov     ecx, 10h
0x18001528a  test    cl, al
0x18001528c  jz      short loc_1800152A2
0x18001528e  mov     edx, eax
0x180015290  shr     edx, 5
0x180015293  and     edx, 3Fh
0x180015296  cmp     edx, r9d
0x180015299  jnz     short loc_1800152A2
0x18001529b  mov     edx, 1
0x1800152a0  jmp     short loc_1800152A4
0x1800152a2  xor     edx, edx
0x1800152a4  mov     [rbx+10h], edx
0x1800152a7  mov     edx, r11d
0x1800152aa  xor     edx, eax
0x1800152ac  and     edx, 7E0h
0x1800152b2  xor     edx, eax
0x1800152b4  or      edx, ecx
0x1800152b6  lock cmpxchg [r10+4], edx
0x1800152bc  jnz     short loc_18001528A
0x1800152be  cmp     dword ptr [rbx+10h], 0
0x1800152c2  jnz     loc_180015379
0x1800152c8  mov     [rbx+8], r8d
0x1800152cc  mov     dword ptr [rbx+4], 1
0x1800152d3  mov     dword ptr [rbx+0Ch], 0
0x1800152da  jmp     loc_180015379
0x1800152df  xor     ecx, ecx
0x1800152e1  sub     r8d, 2
0x1800152e5  jz      short loc_18001530D
0x1800152e7  sub     r8d, 1
0x1800152eb  jz      short loc_180015306
0x1800152ed  sub     r8d, 3
0x1800152f1  jz      short loc_1800152FF
0x1800152f3  cmp     r8d, 1
0x1800152f7  jnz     short loc_180015312
0x1800152f9  lea     ecx, [r8+0Fh]
0x1800152fd  jmp     short loc_180015312
0x1800152ff  mov     ecx, 4
0x180015304  jmp     short loc_180015312
0x180015306  mov     ecx, 8
0x18001530b  jmp     short loc_180015312
0x18001530d  mov     ecx, 2
0x180015312  mov     edx, [rdx]
0x180015314  xor     eax, eax
0x180015316  mov     r8d, ecx
0x180015319  or      r8d, edx
0x18001531c  cmp     r8d, edx
0x18001531f  mov     r9d, r8d
0x180015322  setz    al
0x180015325  or      r9d, 1
0x180015329  cmp     r8d, edx
0x18001532c  mov     [rbx+10h], eax
0x18001532f  mov     eax, edx
0x180015331  cmovz   r9d, r8d
0x180015335  lock cmpxchg [r10], r9d
0x18001533a  jz      short loc_180015340
0x18001533c  mov     edx, eax
0x18001533e  jmp     short loc_180015314
0x180015340  test    r9b, 1
0x180015344  setnz   cl
0x180015347  test    dl, 1
0x18001534a  setz    al
0x18001534d  test    al, cl
0x18001534f  mov     eax, 0
0x180015354  setnz   al
0x180015357  mov     [rbx], eax
0x180015359  jmp     short loc_180015379
0x18001535b  mov     r9, rbx
0x18001535e  mov     edx, r8d
0x180015361  mov     rcx, r10
0x180015364  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180015369  jmp     short loc_180015379
0x18001536b  mov     r9, rbx
0x18001536e  mov     edx, r8d
0x180015371  mov     rcx, r10
0x180015374  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180015379  mov     rax, rbx
0x18001537c  add     rsp, 20h
0x180015380  pop     rbx
0x180015381  retn
```
