# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140010d74`
- end: `0x140010ef1`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: `_DWORD *__fastcall(__int64, volatile signed __int32 *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010f74`

## callees

- `0x140010bc8`
- `0x140010c98`
- `0x140010d74`

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
0x140010d74  mov     [rsp+arg_0], rbx
0x140010d79  push    rdi
0x140010d7a  sub     rsp, 20h
0x140010d7e  xor     eax, eax
0x140010d80  xorps   xmm0, xmm0
0x140010d83  mov     edi, r9d
0x140010d86  mov     r11, rdx
0x140010d89  mov     r9, rcx
0x140010d8c  mov     r10d, r8d
0x140010d8f  movups  xmmword ptr [rcx], xmm0
0x140010d92  mov     [rcx+10h], rax
0x140010d96  test    r8d, r8d
0x140010d99  jz      loc_140010ED7
0x140010d9f  sub     r10d, 1
0x140010da3  jz      loc_140010ECA
0x140010da9  sub     r10d, 1
0x140010dad  jz      loc_140010E4C
0x140010db3  sub     r10d, 1
0x140010db7  jz      loc_140010E4C
0x140010dbd  sub     r10d, 1
0x140010dc1  jz      loc_140010ED7
0x140010dc7  sub     r10d, 1
0x140010dcb  jz      loc_140010ECA
0x140010dd1  sub     r10d, 1
0x140010dd5  jz      short loc_140010E4C
0x140010dd7  cmp     r10d, 1
0x140010ddb  jz      short loc_140010E4C
0x140010ddd  lea     r10d, [r8-140h]
0x140010de4  cmp     r10d, 40h ; '@'
0x140010de8  jge     short loc_140010E37
0x140010dea  mov     eax, [rdx+4]
0x140010ded  mov     ebx, r10d
0x140010df0  shl     ebx, 5
0x140010df3  mov     ecx, 10h
0x140010df8  test    cl, al
0x140010dfa  jz      short loc_140010E10
0x140010dfc  mov     edx, eax
0x140010dfe  shr     edx, 5
0x140010e01  and     edx, 3Fh
0x140010e04  cmp     edx, r10d
0x140010e07  jnz     short loc_140010E10
0x140010e09  mov     edx, 1
0x140010e0e  jmp     short loc_140010E12
0x140010e10  xor     edx, edx
0x140010e12  mov     [r9+10h], edx
0x140010e16  mov     edx, ebx
0x140010e18  xor     edx, eax
0x140010e1a  and     edx, 7E0h
0x140010e20  xor     edx, eax
0x140010e22  or      edx, ecx
0x140010e24  lock cmpxchg [r11+4], edx
0x140010e2a  jnz     short loc_140010DF8
0x140010e2c  cmp     dword ptr [r9+10h], 0
0x140010e31  jnz     loc_140010EE2
0x140010e37  mov     [r9+8], r8d
0x140010e3b  mov     dword ptr [r9+4], 1
0x140010e43  mov     [r9+0Ch], edi
0x140010e47  jmp     loc_140010EE2
0x140010e4c  xor     ecx, ecx
0x140010e4e  sub     r8d, 2
0x140010e52  jz      short loc_140010E7A
0x140010e54  sub     r8d, 1
0x140010e58  jz      short loc_140010E73
0x140010e5a  sub     r8d, 3
0x140010e5e  jz      short loc_140010E6C
0x140010e60  cmp     r8d, 1
0x140010e64  jnz     short loc_140010E7F
0x140010e66  lea     ecx, [r8+0Fh]
0x140010e6a  jmp     short loc_140010E7F
0x140010e6c  mov     ecx, 4
0x140010e71  jmp     short loc_140010E7F
0x140010e73  mov     ecx, 8
0x140010e78  jmp     short loc_140010E7F
0x140010e7a  mov     ecx, 2
0x140010e7f  mov     edx, [rdx]
0x140010e81  xor     eax, eax
0x140010e83  mov     r8d, ecx
0x140010e86  or      r8d, edx
0x140010e89  cmp     r8d, edx
0x140010e8c  mov     r10d, r8d
0x140010e8f  setz    al
0x140010e92  or      r10d, 1
0x140010e96  cmp     r8d, edx
0x140010e99  mov     [r9+10h], eax
0x140010e9d  mov     eax, edx
0x140010e9f  cmovz   r10d, r8d
0x140010ea3  lock cmpxchg [r11], r10d
0x140010ea8  jz      short loc_140010EAE
0x140010eaa  mov     edx, eax
0x140010eac  jmp     short loc_140010E81
0x140010eae  test    r10b, 1
0x140010eb2  setnz   cl
0x140010eb5  test    dl, 1
0x140010eb8  setz    al
0x140010ebb  test    al, cl
0x140010ebd  mov     eax, 0
0x140010ec2  setnz   al
0x140010ec5  mov     [r9], eax
0x140010ec8  jmp     short loc_140010EE2
0x140010eca  mov     edx, r8d
0x140010ecd  mov     rcx, r11
0x140010ed0  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x140010ed5  jmp     short loc_140010EE2
0x140010ed7  mov     edx, r8d
0x140010eda  mov     rcx, r11
0x140010edd  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140010ee2  mov     rbx, [rsp+28h+arg_0]
0x140010ee7  mov     rax, r9
0x140010eea  add     rsp, 20h
0x140010eee  pop     rdi
0x140010eef  retn
```
