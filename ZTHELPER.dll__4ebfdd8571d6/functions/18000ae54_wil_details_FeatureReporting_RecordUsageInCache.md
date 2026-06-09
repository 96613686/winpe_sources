# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000ae54`
- end: `0x18000afd0`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: `_DWORD *__fastcall(__int64, volatile signed __int32 *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b120`

## callees

- `0x18000aca8`
- `0x18000ad78`
- `0x18000ae54`

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
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a3, (_DWORD *)a1);
      return v6;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3, a3, (_DWORD *)a1);
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
0x18000ae54  mov     [rsp+arg_0], rbx
0x18000ae59  push    rdi
0x18000ae5a  sub     rsp, 20h
0x18000ae5e  xor     eax, eax
0x18000ae60  xorps   xmm0, xmm0
0x18000ae63  mov     edi, r9d
0x18000ae66  mov     r11, rdx
0x18000ae69  mov     r9, rcx
0x18000ae6c  mov     r10d, r8d
0x18000ae6f  movups  xmmword ptr [rcx], xmm0
0x18000ae72  mov     [rcx+10h], rax
0x18000ae76  test    r8d, r8d
0x18000ae79  jz      loc_18000AFB7
0x18000ae7f  sub     r10d, 1
0x18000ae83  jz      loc_18000AFAA
0x18000ae89  sub     r10d, 1
0x18000ae8d  jz      loc_18000AF2C
0x18000ae93  sub     r10d, 1
0x18000ae97  jz      loc_18000AF2C
0x18000ae9d  sub     r10d, 1
0x18000aea1  jz      loc_18000AFB7
0x18000aea7  sub     r10d, 1
0x18000aeab  jz      loc_18000AFAA
0x18000aeb1  sub     r10d, 1
0x18000aeb5  jz      short loc_18000AF2C
0x18000aeb7  cmp     r10d, 1
0x18000aebb  jz      short loc_18000AF2C
0x18000aebd  lea     r10d, [r8-140h]
0x18000aec4  cmp     r10d, 40h ; '@'
0x18000aec8  jge     short loc_18000AF17
0x18000aeca  mov     eax, [rdx+4]
0x18000aecd  mov     ebx, r10d
0x18000aed0  shl     ebx, 5
0x18000aed3  mov     ecx, 10h
0x18000aed8  test    cl, al
0x18000aeda  jz      short loc_18000AEF0
0x18000aedc  mov     edx, eax
0x18000aede  shr     edx, 5
0x18000aee1  and     edx, 3Fh
0x18000aee4  cmp     edx, r10d
0x18000aee7  jnz     short loc_18000AEF0
0x18000aee9  mov     edx, 1
0x18000aeee  jmp     short loc_18000AEF2
0x18000aef0  xor     edx, edx
0x18000aef2  mov     [r9+10h], edx
0x18000aef6  mov     edx, ebx
0x18000aef8  xor     edx, eax
0x18000aefa  and     edx, 7E0h
0x18000af00  xor     edx, eax
0x18000af02  or      edx, ecx
0x18000af04  lock cmpxchg [r11+4], edx
0x18000af0a  jnz     short loc_18000AED8
0x18000af0c  cmp     dword ptr [r9+10h], 0
0x18000af11  jnz     loc_18000AFC2
0x18000af17  mov     [r9+8], r8d
0x18000af1b  mov     dword ptr [r9+4], 1
0x18000af23  mov     [r9+0Ch], edi
0x18000af27  jmp     loc_18000AFC2
0x18000af2c  xor     ecx, ecx
0x18000af2e  sub     r8d, 2
0x18000af32  jz      short loc_18000AF5A
0x18000af34  sub     r8d, 1
0x18000af38  jz      short loc_18000AF53
0x18000af3a  sub     r8d, 3
0x18000af3e  jz      short loc_18000AF4C
0x18000af40  cmp     r8d, 1
0x18000af44  jnz     short loc_18000AF5F
0x18000af46  lea     ecx, [r8+0Fh]
0x18000af4a  jmp     short loc_18000AF5F
0x18000af4c  mov     ecx, 4
0x18000af51  jmp     short loc_18000AF5F
0x18000af53  mov     ecx, 8
0x18000af58  jmp     short loc_18000AF5F
0x18000af5a  mov     ecx, 2
0x18000af5f  mov     edx, [rdx]
0x18000af61  xor     eax, eax
0x18000af63  mov     r8d, ecx
0x18000af66  or      r8d, edx
0x18000af69  cmp     r8d, edx
0x18000af6c  mov     r10d, r8d
0x18000af6f  setz    al
0x18000af72  or      r10d, 1
0x18000af76  cmp     r8d, edx
0x18000af79  mov     [r9+10h], eax
0x18000af7d  mov     eax, edx
0x18000af7f  cmovz   r10d, r8d
0x18000af83  lock cmpxchg [r11], r10d
0x18000af88  jz      short loc_18000AF8E
0x18000af8a  mov     edx, eax
0x18000af8c  jmp     short loc_18000AF61
0x18000af8e  test    r10b, 1
0x18000af92  setnz   cl
0x18000af95  test    dl, 1
0x18000af98  setz    al
0x18000af9b  test    al, cl
0x18000af9d  mov     eax, 0
0x18000afa2  setnz   al
0x18000afa5  mov     [r9], eax
0x18000afa8  jmp     short loc_18000AFC2
0x18000afaa  mov     edx, r8d
0x18000afad  mov     rcx, r11
0x18000afb0  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000afb5  jmp     short loc_18000AFC2
0x18000afb7  mov     edx, r8d
0x18000afba  mov     rcx, r11
0x18000afbd  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000afc2  mov     rbx, [rsp+28h+arg_0]
0x18000afc7  mov     rax, r9
0x18000afca  add     rsp, 20h
0x18000afce  pop     rdi
0x18000afcf  retn
```
