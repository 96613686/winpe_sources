# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140004fac`
- end: `0x140005128`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400051b8`

## callees

- `0x140004e00`
- `0x140004ed0`
- `0x140004fac`

## pseudocode

```c
int *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  int *v6; // r9
  unsigned int v7; // ebx
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 v15; // edx
  int v16; // r10d
  signed __int32 v17; // ebx
  signed __int32 v18; // eax

  v6 = (int *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_35;
    case 1u:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_34;
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
  v15 = *a2;
  v16 = 1;
  while ( 1 )
  {
    v17 = v15 | v11 | 1;
    v6[4] = (v15 | v11) == v15;
    if ( (v15 | v11) == v15 )
      v17 = v15 | v11;
    v18 = _InterlockedCompareExchange(a2, v17, v15);
    if ( v15 == v18 )
      break;
    v15 = v18;
  }
  if ( (v17 & 1) == 0 || (v15 & 1) != 0 )
    v16 = 0;
  *v6 = v16;
  return v6;
}

```

## disassembly

```asm
0x140004fac  mov     [rsp+arg_0], rbx
0x140004fb1  mov     [rsp+arg_8], rsi
0x140004fb6  push    rdi
0x140004fb7  sub     rsp, 20h
0x140004fbb  xor     eax, eax
0x140004fbd  xorps   xmm0, xmm0
0x140004fc0  mov     esi, r9d
0x140004fc3  mov     r11, rdx
0x140004fc6  mov     r9, rcx
0x140004fc9  mov     r10d, r8d
0x140004fcc  movups  xmmword ptr [rcx], xmm0
0x140004fcf  mov     [rcx+10h], rax
0x140004fd3  test    r8d, r8d
0x140004fd6  jz      loc_140005109
0x140004fdc  sub     r10d, 1
0x140004fe0  jz      loc_1400050FC
0x140004fe6  sub     r10d, 1
0x140004fea  jz      loc_140005083
0x140004ff0  sub     r10d, 1
0x140004ff4  jz      loc_140005083
0x140004ffa  sub     r10d, 1
0x140004ffe  jz      loc_140005109
0x140005004  sub     r10d, 1
0x140005008  jz      loc_1400050FC
0x14000500e  sub     r10d, 1
0x140005012  jz      short loc_140005083
0x140005014  cmp     r10d, 1
0x140005018  jz      short loc_140005083
0x14000501a  lea     ebx, [r8-140h]
0x140005021  lea     r10d, [rax+1]
0x140005025  cmp     ebx, 40h ; '@'
0x140005028  jge     short loc_140005072
0x14000502a  mov     eax, [rdx+4]
0x14000502d  lea     ecx, [r10+0Fh]
0x140005031  mov     edi, ebx
0x140005033  shl     edi, 5
0x140005036  test    cl, al
0x140005038  jz      short loc_14000504B
0x14000503a  mov     edx, eax
0x14000503c  shr     edx, 5
0x14000503f  and     edx, 3Fh
0x140005042  cmp     edx, ebx
0x140005044  jnz     short loc_14000504B
0x140005046  mov     edx, r10d
0x140005049  jmp     short loc_14000504D
0x14000504b  xor     edx, edx
0x14000504d  mov     [r9+10h], edx
0x140005051  mov     edx, edi
0x140005053  xor     edx, eax
0x140005055  and     edx, 7E0h
0x14000505b  xor     edx, eax
0x14000505d  or      edx, ecx
0x14000505f  lock cmpxchg [r11+4], edx
0x140005065  jnz     short loc_140005036
0x140005067  cmp     dword ptr [r9+10h], 0
0x14000506c  jnz     loc_140005114
0x140005072  mov     [r9+8], r8d
0x140005076  mov     [r9+4], r10d
0x14000507a  mov     [r9+0Ch], esi
0x14000507e  jmp     loc_140005114
0x140005083  xor     ecx, ecx
0x140005085  sub     r8d, 2
0x140005089  jz      short loc_1400050B1
0x14000508b  sub     r8d, 1
0x14000508f  jz      short loc_1400050AA
0x140005091  sub     r8d, 3
0x140005095  jz      short loc_1400050A3
0x140005097  cmp     r8d, 1
0x14000509b  jnz     short loc_1400050B6
0x14000509d  lea     ecx, [r8+0Fh]
0x1400050a1  jmp     short loc_1400050B6
0x1400050a3  mov     ecx, 4
0x1400050a8  jmp     short loc_1400050B6
0x1400050aa  mov     ecx, 8
0x1400050af  jmp     short loc_1400050B6
0x1400050b1  mov     ecx, 2
0x1400050b6  mov     edx, [rdx]
0x1400050b8  mov     r10d, 1
0x1400050be  xor     eax, eax
0x1400050c0  mov     r8d, ecx
0x1400050c3  or      r8d, edx
0x1400050c6  cmp     r8d, edx
0x1400050c9  mov     ebx, r8d
0x1400050cc  setz    al
0x1400050cf  or      ebx, r10d
0x1400050d2  cmp     r8d, edx
0x1400050d5  mov     [r9+10h], eax
0x1400050d9  mov     eax, edx
0x1400050db  cmovz   ebx, r8d
0x1400050df  lock cmpxchg [r11], ebx
0x1400050e4  jz      short loc_1400050EA
0x1400050e6  mov     edx, eax
0x1400050e8  jmp     short loc_1400050BE
0x1400050ea  test    r10b, bl
0x1400050ed  jz      short loc_1400050F4
0x1400050ef  test    r10b, dl
0x1400050f2  jz      short loc_1400050F7
0x1400050f4  xor     r10d, r10d
0x1400050f7  mov     [r9], r10d
0x1400050fa  jmp     short loc_140005114
0x1400050fc  mov     edx, r8d
0x1400050ff  mov     rcx, r11
0x140005102  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x140005107  jmp     short loc_140005114
0x140005109  mov     edx, r8d
0x14000510c  mov     rcx, r11
0x14000510f  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140005114  mov     rbx, [rsp+28h+arg_0]
0x140005119  mov     rax, r9
0x14000511c  mov     rsi, [rsp+28h+arg_8]
0x140005121  add     rsp, 20h
0x140005125  pop     rdi
0x140005126  retn
```
