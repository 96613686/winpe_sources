# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1400024e4`
- end: `0x14000266f`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002708`

## callees

- `0x14000232c`
- `0x140002400`
- `0x1400024e4`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4,
        unsigned int a5)
{
  _DWORD *v8; // r9
  int v9; // r8d
  unsigned __int32 v10; // eax
  BOOL v11; // edx
  unsigned __int32 v12; // ett
  int v13; // ecx
  signed __int32 i; // edx
  signed __int32 v15; // r10d
  signed __int32 v16; // eax

  v8 = (_DWORD *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_32;
    case 1u:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a5, a1);
      return v8;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3, a5, a1);
      return v8;
    case 5u:
      goto LABEL_31;
  }
  if ( a3 - 6 >= 2 )
  {
    v9 = a3 - 320;
    if ( v9 >= 64 )
      goto LABEL_16;
    v10 = *((_DWORD *)a2 + 1);
    do
    {
      v11 = (v10 & 0x10) != 0 && ((v10 >> 5) & 0x3F) == v9;
      *(_DWORD *)(a1 + 16) = v11;
      v12 = v10;
      v10 = _InterlockedCompareExchange(
              a2 + 1,
              v10 ^ ((unsigned __int16)v10 ^ (unsigned __int16)(32 * v9)) & 0x7E0 | 0x10,
              v10);
    }
    while ( v12 != v10 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 4) = a5;
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return v8;
  }
LABEL_17:
  v13 = 0;
  switch ( a3 )
  {
    case 2u:
      v13 = 2;
      break;
    case 3u:
      v13 = 8;
      break;
    case 6u:
      v13 = 4;
      break;
    case 7u:
      v13 = 16;
      break;
  }
  for ( i = *a2; ; i = v16 )
  {
    v15 = i | v13 | 1;
    v8[4] = (i | v13) == i;
    if ( (i | v13) == i )
      v15 = i | v13;
    v16 = _InterlockedCompareExchange(a2, v15, i);
    if ( i == v16 )
      break;
  }
  *v8 = (v15 & 1) != 0 && (i & 1) == 0;
  return v8;
}

```

## disassembly

```asm
0x1400024e4  mov     [rsp+arg_0], rbx
0x1400024e9  push    rdi
0x1400024ea  sub     rsp, 20h
0x1400024ee  xor     eax, eax
0x1400024f0  xorps   xmm0, xmm0
0x1400024f3  mov     edi, r9d
0x1400024f6  mov     r11d, r8d
0x1400024f9  mov     rbx, rdx
0x1400024fc  mov     r9, rcx
0x1400024ff  mov     r10d, r8d
0x140002502  movups  xmmword ptr [rcx], xmm0
0x140002505  mov     [rcx+10h], rax
0x140002509  test    r8d, r8d
0x14000250c  jz      loc_140002650
0x140002512  sub     r10d, 1
0x140002516  jz      loc_14000263E
0x14000251c  sub     r10d, 1
0x140002520  jz      loc_1400025C0
0x140002526  sub     r10d, 1
0x14000252a  jz      loc_1400025C0
0x140002530  sub     r10d, 1
0x140002534  jz      loc_140002650
0x14000253a  sub     r10d, 1
0x14000253e  jz      loc_14000263E
0x140002544  sub     r10d, 1
0x140002548  jz      short loc_1400025C0
0x14000254a  cmp     r10d, 1
0x14000254e  jz      short loc_1400025C0
0x140002550  add     r8d, 0FFFFFEC0h
0x140002557  cmp     r8d, 40h ; '@'
0x14000255b  jge     short loc_1400025AB
0x14000255d  mov     eax, [rdx+4]
0x140002560  mov     r10d, r8d
0x140002563  shl     r10d, 5
0x140002567  mov     ecx, 10h
0x14000256c  test    cl, al
0x14000256e  jz      short loc_140002584
0x140002570  mov     edx, eax
0x140002572  shr     edx, 5
0x140002575  and     edx, 3Fh
0x140002578  cmp     edx, r8d
0x14000257b  jnz     short loc_140002584
0x14000257d  mov     edx, 1
0x140002582  jmp     short loc_140002586
0x140002584  xor     edx, edx
0x140002586  mov     [r9+10h], edx
0x14000258a  mov     edx, r10d
0x14000258d  xor     edx, eax
0x14000258f  and     edx, 7E0h
0x140002595  xor     edx, eax
0x140002597  or      edx, ecx
0x140002599  lock cmpxchg [rbx+4], edx
0x14000259e  jnz     short loc_14000256C
0x1400025a0  cmp     dword ptr [r9+10h], 0
0x1400025a5  jnz     loc_140002660
0x1400025ab  mov     eax, [rsp+28h+arg_20]
0x1400025af  mov     [r9+4], eax
0x1400025b3  mov     [r9+8], r11d
0x1400025b7  mov     [r9+0Ch], edi
0x1400025bb  jmp     loc_140002660
0x1400025c0  xor     ecx, ecx
0x1400025c2  sub     r11d, 2
0x1400025c6  jz      short loc_1400025EE
0x1400025c8  sub     r11d, 1
0x1400025cc  jz      short loc_1400025E7
0x1400025ce  sub     r11d, 3
0x1400025d2  jz      short loc_1400025E0
0x1400025d4  cmp     r11d, 1
0x1400025d8  jnz     short loc_1400025F3
0x1400025da  lea     ecx, [r11+0Fh]
0x1400025de  jmp     short loc_1400025F3
0x1400025e0  mov     ecx, 4
0x1400025e5  jmp     short loc_1400025F3
0x1400025e7  mov     ecx, 8
0x1400025ec  jmp     short loc_1400025F3
0x1400025ee  mov     ecx, 2
0x1400025f3  mov     edx, [rdx]
0x1400025f5  xor     eax, eax
0x1400025f7  mov     r8d, ecx
0x1400025fa  or      r8d, edx
0x1400025fd  cmp     r8d, edx
0x140002600  mov     r10d, r8d
0x140002603  setz    al
0x140002606  or      r10d, 1
0x14000260a  cmp     r8d, edx
0x14000260d  mov     [r9+10h], eax
0x140002611  mov     eax, edx
0x140002613  cmovz   r10d, r8d
0x140002617  lock cmpxchg [rbx], r10d
0x14000261c  jz      short loc_140002622
0x14000261e  mov     edx, eax
0x140002620  jmp     short loc_1400025F5
0x140002622  test    r10b, 1
0x140002626  setnz   cl
0x140002629  test    dl, 1
0x14000262c  setz    al
0x14000262f  test    al, cl
0x140002631  mov     eax, 0
0x140002636  setnz   al
0x140002639  mov     [r9], eax
0x14000263c  jmp     short loc_140002660
0x14000263e  mov     r8d, [rsp+28h+arg_20]
0x140002643  mov     edx, r11d
0x140002646  mov     rcx, rbx
0x140002649  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14000264e  jmp     short loc_140002660
0x140002650  mov     r8d, [rsp+28h+arg_20]
0x140002655  mov     edx, r11d
0x140002658  mov     rcx, rbx
0x14000265b  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140002660  mov     rbx, [rsp+28h+arg_0]
0x140002665  mov     rax, r9
0x140002668  add     rsp, 20h
0x14000266c  pop     rdi
0x14000266d  retn
```
