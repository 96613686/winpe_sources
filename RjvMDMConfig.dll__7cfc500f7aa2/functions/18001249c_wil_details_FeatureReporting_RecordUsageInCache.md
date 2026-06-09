# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001249c`
- end: `0x180012614`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c790`

## callees

- `0x1800122f0`
- `0x1800123c0`
- `0x18001249c`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r11d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 v13; // edx
  int v14; // r9d
  signed __int32 v15; // r11d
  signed __int32 v16; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_35;
    case 1:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_34;
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
  v13 = *a2;
  v14 = 1;
  while ( 1 )
  {
    v15 = v13 | v9 | 1;
    *(_DWORD *)(a1 + 16) = (v13 | v9) == v13;
    if ( (v13 | v9) == v13 )
      v15 = v13 | v9;
    v16 = _InterlockedCompareExchange(a2, v15, v13);
    if ( v13 == v16 )
      break;
    v13 = v16;
  }
  if ( (v15 & 1) == 0 || (v13 & 1) != 0 )
    v14 = 0;
  *(_DWORD *)a1 = v14;
  return a1;
}

```

## disassembly

```asm
0x18001249c  mov     [rsp+arg_0], rbx
0x1800124a1  push    rdi
0x1800124a2  sub     rsp, 20h
0x1800124a6  xor     eax, eax
0x1800124a8  xorps   xmm0, xmm0
0x1800124ab  mov     r10, rdx
0x1800124ae  mov     rbx, rcx
0x1800124b1  mov     r9d, r8d
0x1800124b4  movups  xmmword ptr [rcx], xmm0
0x1800124b7  mov     [rcx+10h], rax
0x1800124bb  test    r8d, r8d
0x1800124be  jz      loc_1800125F7
0x1800124c4  sub     r9d, 1
0x1800124c8  jz      loc_1800125E7
0x1800124ce  sub     r9d, 1
0x1800124d2  jz      loc_18001256F
0x1800124d8  sub     r9d, 1
0x1800124dc  jz      loc_18001256F
0x1800124e2  sub     r9d, 1
0x1800124e6  jz      loc_1800125F7
0x1800124ec  sub     r9d, 1
0x1800124f0  jz      loc_1800125E7
0x1800124f6  sub     r9d, 1
0x1800124fa  jz      short loc_18001256F
0x1800124fc  cmp     r9d, 1
0x180012500  jz      short loc_18001256F
0x180012502  lea     r11d, [r8-140h]
0x180012509  lea     r9d, [rax+1]
0x18001250d  cmp     r11d, 40h ; '@'
0x180012511  jge     short loc_18001255B
0x180012513  mov     eax, [rdx+4]
0x180012516  lea     ecx, [r9+0Fh]
0x18001251a  mov     edi, r11d
0x18001251d  shl     edi, 5
0x180012520  test    cl, al
0x180012522  jz      short loc_180012536
0x180012524  mov     edx, eax
0x180012526  shr     edx, 5
0x180012529  and     edx, 3Fh
0x18001252c  cmp     edx, r11d
0x18001252f  jnz     short loc_180012536
0x180012531  mov     edx, r9d
0x180012534  jmp     short loc_180012538
0x180012536  xor     edx, edx
0x180012538  mov     [rbx+10h], edx
0x18001253b  mov     edx, edi
0x18001253d  xor     edx, eax
0x18001253f  and     edx, 7E0h
0x180012545  xor     edx, eax
0x180012547  or      edx, ecx
0x180012549  lock cmpxchg [r10+4], edx
0x18001254f  jnz     short loc_180012520
0x180012551  cmp     dword ptr [rbx+10h], 0
0x180012555  jnz     loc_180012605
0x18001255b  mov     [rbx+8], r8d
0x18001255f  mov     [rbx+4], r9d
0x180012563  mov     dword ptr [rbx+0Ch], 0
0x18001256a  jmp     loc_180012605
0x18001256f  xor     ecx, ecx
0x180012571  sub     r8d, 2
0x180012575  jz      short loc_18001259D
0x180012577  sub     r8d, 1
0x18001257b  jz      short loc_180012596
0x18001257d  sub     r8d, 3
0x180012581  jz      short loc_18001258F
0x180012583  cmp     r8d, 1
0x180012587  jnz     short loc_1800125A2
0x180012589  lea     ecx, [r8+0Fh]
0x18001258d  jmp     short loc_1800125A2
0x18001258f  mov     ecx, 4
0x180012594  jmp     short loc_1800125A2
0x180012596  mov     ecx, 8
0x18001259b  jmp     short loc_1800125A2
0x18001259d  mov     ecx, 2
0x1800125a2  mov     edx, [rdx]
0x1800125a4  mov     r9d, 1
0x1800125aa  xor     eax, eax
0x1800125ac  mov     r8d, ecx
0x1800125af  or      r8d, edx
0x1800125b2  cmp     r8d, edx
0x1800125b5  mov     r11d, r8d
0x1800125b8  setz    al
0x1800125bb  or      r11d, r9d
0x1800125be  cmp     r8d, edx
0x1800125c1  mov     [rbx+10h], eax
0x1800125c4  mov     eax, edx
0x1800125c6  cmovz   r11d, r8d
0x1800125ca  lock cmpxchg [r10], r11d
0x1800125cf  jz      short loc_1800125D5
0x1800125d1  mov     edx, eax
0x1800125d3  jmp     short loc_1800125AA
0x1800125d5  test    r9b, r11b
0x1800125d8  jz      short loc_1800125DF
0x1800125da  test    r9b, dl
0x1800125dd  jz      short loc_1800125E2
0x1800125df  xor     r9d, r9d
0x1800125e2  mov     [rbx], r9d
0x1800125e5  jmp     short loc_180012605
0x1800125e7  mov     r9, rbx
0x1800125ea  mov     edx, r8d
0x1800125ed  mov     rcx, r10
0x1800125f0  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800125f5  jmp     short loc_180012605
0x1800125f7  mov     r9, rbx
0x1800125fa  mov     edx, r8d
0x1800125fd  mov     rcx, r10
0x180012600  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180012605  mov     rax, rbx
0x180012608  mov     rbx, [rsp+28h+arg_0]
0x18001260d  add     rsp, 20h
0x180012611  pop     rdi
0x180012612  retn
```
