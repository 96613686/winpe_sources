# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800085d4`
- end: `0x180008750`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800081e8`

## callees

- `0x1800085d4`
- `0x1800089e8`
- `0x180017988`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        __int64 a3,
        int a4)
{
  _DWORD *v6; // r9
  int v7; // r10d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  signed __int32 i; // edx
  signed __int32 v16; // r10d
  signed __int32 v17; // eax

  v6 = (_DWORD *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return v6;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return v6;
    case 5:
      goto LABEL_31;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
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
0x1800085d4  mov     [rsp+arg_0], rbx
0x1800085d9  push    rdi
0x1800085da  sub     rsp, 20h
0x1800085de  xor     eax, eax
0x1800085e0  xorps   xmm0, xmm0
0x1800085e3  mov     edi, r9d
0x1800085e6  mov     r11, rdx
0x1800085e9  mov     r9, rcx
0x1800085ec  mov     r10d, r8d
0x1800085ef  movups  xmmword ptr [rcx], xmm0
0x1800085f2  mov     [rcx+10h], rax
0x1800085f6  test    r8d, r8d
0x1800085f9  jz      loc_180008737
0x1800085ff  sub     r10d, 1
0x180008603  jz      loc_18000872A
0x180008609  sub     r10d, 1
0x18000860d  jz      loc_1800086AC
0x180008613  sub     r10d, 1
0x180008617  jz      loc_1800086AC
0x18000861d  sub     r10d, 1
0x180008621  jz      loc_180008737
0x180008627  sub     r10d, 1
0x18000862b  jz      loc_18000872A
0x180008631  sub     r10d, 1
0x180008635  jz      short loc_1800086AC
0x180008637  cmp     r10d, 1
0x18000863b  jz      short loc_1800086AC
0x18000863d  lea     r10d, [r8-140h]
0x180008644  cmp     r10d, 40h ; '@'
0x180008648  jge     short loc_180008697
0x18000864a  mov     eax, [rdx+4]
0x18000864d  mov     ebx, r10d
0x180008650  shl     ebx, 5
0x180008653  mov     ecx, 10h
0x180008658  test    cl, al
0x18000865a  jz      short loc_180008670
0x18000865c  mov     edx, eax
0x18000865e  shr     edx, 5
0x180008661  and     edx, 3Fh
0x180008664  cmp     edx, r10d
0x180008667  jnz     short loc_180008670
0x180008669  mov     edx, 1
0x18000866e  jmp     short loc_180008672
0x180008670  xor     edx, edx
0x180008672  mov     [r9+10h], edx
0x180008676  mov     edx, ebx
0x180008678  xor     edx, eax
0x18000867a  and     edx, 7E0h
0x180008680  xor     edx, eax
0x180008682  or      edx, ecx
0x180008684  lock cmpxchg [r11+4], edx
0x18000868a  jnz     short loc_180008658
0x18000868c  cmp     dword ptr [r9+10h], 0
0x180008691  jnz     loc_180008742
0x180008697  mov     [r9+8], r8d
0x18000869b  mov     dword ptr [r9+4], 1
0x1800086a3  mov     [r9+0Ch], edi
0x1800086a7  jmp     loc_180008742
0x1800086ac  xor     ecx, ecx
0x1800086ae  sub     r8d, 2
0x1800086b2  jz      short loc_1800086DA
0x1800086b4  sub     r8d, 1
0x1800086b8  jz      short loc_1800086D3
0x1800086ba  sub     r8d, 3
0x1800086be  jz      short loc_1800086CC
0x1800086c0  cmp     r8d, 1
0x1800086c4  jnz     short loc_1800086DF
0x1800086c6  lea     ecx, [r8+0Fh]
0x1800086ca  jmp     short loc_1800086DF
0x1800086cc  mov     ecx, 4
0x1800086d1  jmp     short loc_1800086DF
0x1800086d3  mov     ecx, 8
0x1800086d8  jmp     short loc_1800086DF
0x1800086da  mov     ecx, 2
0x1800086df  mov     edx, [rdx]
0x1800086e1  xor     eax, eax
0x1800086e3  mov     r8d, ecx
0x1800086e6  or      r8d, edx
0x1800086e9  cmp     r8d, edx
0x1800086ec  mov     r10d, r8d
0x1800086ef  setz    al
0x1800086f2  or      r10d, 1
0x1800086f6  cmp     r8d, edx
0x1800086f9  mov     [r9+10h], eax
0x1800086fd  mov     eax, edx
0x1800086ff  cmovz   r10d, r8d
0x180008703  lock cmpxchg [r11], r10d
0x180008708  jz      short loc_18000870E
0x18000870a  mov     edx, eax
0x18000870c  jmp     short loc_1800086E1
0x18000870e  test    r10b, 1
0x180008712  setnz   cl
0x180008715  test    dl, 1
0x180008718  setz    al
0x18000871b  test    al, cl
0x18000871d  mov     eax, 0
0x180008722  setnz   al
0x180008725  mov     [r9], eax
0x180008728  jmp     short loc_180008742
0x18000872a  mov     edx, r8d
0x18000872d  mov     rcx, r11
0x180008730  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180008735  jmp     short loc_180008742
0x180008737  mov     edx, r8d
0x18000873a  mov     rcx, r11
0x18000873d  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180008742  mov     rbx, [rsp+28h+arg_0]
0x180008747  mov     rax, r9
0x18000874a  add     rsp, 20h
0x18000874e  pop     rdi
0x18000874f  retn
```
