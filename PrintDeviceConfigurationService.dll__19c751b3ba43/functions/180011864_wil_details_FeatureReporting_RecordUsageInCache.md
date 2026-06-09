# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180011864`
- end: `0x1800119db`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f894`

## callees

- `0x1800116b8`
- `0x180011788`
- `0x180011864`

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
0x180011864  mov     [rsp+arg_0], rbx
0x180011869  push    rdi
0x18001186a  sub     rsp, 20h
0x18001186e  xor     eax, eax
0x180011870  xorps   xmm0, xmm0
0x180011873  mov     r10, rdx
0x180011876  mov     rbx, rcx
0x180011879  mov     r9d, r8d
0x18001187c  movups  xmmword ptr [rcx], xmm0
0x18001187f  mov     [rcx+10h], rax
0x180011883  test    r8d, r8d
0x180011886  jz      loc_1800119BF
0x18001188c  sub     r9d, 1
0x180011890  jz      loc_1800119AF
0x180011896  sub     r9d, 1
0x18001189a  jz      loc_180011937
0x1800118a0  sub     r9d, 1
0x1800118a4  jz      loc_180011937
0x1800118aa  sub     r9d, 1
0x1800118ae  jz      loc_1800119BF
0x1800118b4  sub     r9d, 1
0x1800118b8  jz      loc_1800119AF
0x1800118be  sub     r9d, 1
0x1800118c2  jz      short loc_180011937
0x1800118c4  cmp     r9d, 1
0x1800118c8  jz      short loc_180011937
0x1800118ca  lea     r11d, [r8-140h]
0x1800118d1  lea     r9d, [rax+1]
0x1800118d5  cmp     r11d, 40h ; '@'
0x1800118d9  jge     short loc_180011923
0x1800118db  mov     eax, [rdx+4]
0x1800118de  lea     ecx, [r9+0Fh]
0x1800118e2  mov     edi, r11d
0x1800118e5  shl     edi, 5
0x1800118e8  test    cl, al
0x1800118ea  jz      short loc_1800118FE
0x1800118ec  mov     edx, eax
0x1800118ee  shr     edx, 5
0x1800118f1  and     edx, 3Fh
0x1800118f4  cmp     edx, r11d
0x1800118f7  jnz     short loc_1800118FE
0x1800118f9  mov     edx, r9d
0x1800118fc  jmp     short loc_180011900
0x1800118fe  xor     edx, edx
0x180011900  mov     [rbx+10h], edx
0x180011903  mov     edx, edi
0x180011905  xor     edx, eax
0x180011907  and     edx, 7E0h
0x18001190d  xor     edx, eax
0x18001190f  or      edx, ecx
0x180011911  lock cmpxchg [r10+4], edx
0x180011917  jnz     short loc_1800118E8
0x180011919  cmp     dword ptr [rbx+10h], 0
0x18001191d  jnz     loc_1800119CD
0x180011923  mov     [rbx+8], r8d
0x180011927  mov     [rbx+4], r9d
0x18001192b  mov     dword ptr [rbx+0Ch], 0
0x180011932  jmp     loc_1800119CD
0x180011937  xor     ecx, ecx
0x180011939  sub     r8d, 2
0x18001193d  jz      short loc_180011965
0x18001193f  sub     r8d, 1
0x180011943  jz      short loc_18001195E
0x180011945  sub     r8d, 3
0x180011949  jz      short loc_180011957
0x18001194b  cmp     r8d, 1
0x18001194f  jnz     short loc_18001196A
0x180011951  lea     ecx, [r8+0Fh]
0x180011955  jmp     short loc_18001196A
0x180011957  mov     ecx, 4
0x18001195c  jmp     short loc_18001196A
0x18001195e  mov     ecx, 8
0x180011963  jmp     short loc_18001196A
0x180011965  mov     ecx, 2
0x18001196a  mov     edx, [rdx]
0x18001196c  mov     r9d, 1
0x180011972  xor     eax, eax
0x180011974  mov     r8d, ecx
0x180011977  or      r8d, edx
0x18001197a  cmp     r8d, edx
0x18001197d  mov     r11d, r8d
0x180011980  setz    al
0x180011983  or      r11d, r9d
0x180011986  cmp     r8d, edx
0x180011989  mov     [rbx+10h], eax
0x18001198c  mov     eax, edx
0x18001198e  cmovz   r11d, r8d
0x180011992  lock cmpxchg [r10], r11d
0x180011997  jz      short loc_18001199D
0x180011999  mov     edx, eax
0x18001199b  jmp     short loc_180011972
0x18001199d  test    r9b, r11b
0x1800119a0  jz      short loc_1800119A7
0x1800119a2  test    r9b, dl
0x1800119a5  jz      short loc_1800119AA
0x1800119a7  xor     r9d, r9d
0x1800119aa  mov     [rbx], r9d
0x1800119ad  jmp     short loc_1800119CD
0x1800119af  mov     r9, rbx
0x1800119b2  mov     edx, r8d
0x1800119b5  mov     rcx, r10
0x1800119b8  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800119bd  jmp     short loc_1800119CD
0x1800119bf  mov     r9, rbx
0x1800119c2  mov     edx, r8d
0x1800119c5  mov     rcx, r10
0x1800119c8  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1800119cd  mov     rax, rbx
0x1800119d0  mov     rbx, [rsp+28h+arg_0]
0x1800119d5  add     rsp, 20h
0x1800119d9  pop     rdi
0x1800119da  retn
```
