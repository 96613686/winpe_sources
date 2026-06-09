# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180019cc8`
- end: `0x180019e44`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800163d4`

## callees

- `0x180019b1c`
- `0x180019bec`
- `0x180019cc8`

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
0x180019cc8  mov     [rsp+arg_0], rbx
0x180019ccd  push    rdi
0x180019cce  sub     rsp, 20h
0x180019cd2  xor     eax, eax
0x180019cd4  xorps   xmm0, xmm0
0x180019cd7  mov     edi, r9d
0x180019cda  mov     r11, rdx
0x180019cdd  mov     r9, rcx
0x180019ce0  mov     r10d, r8d
0x180019ce3  movups  xmmword ptr [rcx], xmm0
0x180019ce6  mov     [rcx+10h], rax
0x180019cea  test    r8d, r8d
0x180019ced  jz      loc_180019E2B
0x180019cf3  sub     r10d, 1
0x180019cf7  jz      loc_180019E1E
0x180019cfd  sub     r10d, 1
0x180019d01  jz      loc_180019DA0
0x180019d07  sub     r10d, 1
0x180019d0b  jz      loc_180019DA0
0x180019d11  sub     r10d, 1
0x180019d15  jz      loc_180019E2B
0x180019d1b  sub     r10d, 1
0x180019d1f  jz      loc_180019E1E
0x180019d25  sub     r10d, 1
0x180019d29  jz      short loc_180019DA0
0x180019d2b  cmp     r10d, 1
0x180019d2f  jz      short loc_180019DA0
0x180019d31  lea     r10d, [r8-140h]
0x180019d38  cmp     r10d, 40h ; '@'
0x180019d3c  jge     short loc_180019D8B
0x180019d3e  mov     eax, [rdx+4]
0x180019d41  mov     ebx, r10d
0x180019d44  shl     ebx, 5
0x180019d47  mov     ecx, 10h
0x180019d4c  test    cl, al
0x180019d4e  jz      short loc_180019D64
0x180019d50  mov     edx, eax
0x180019d52  shr     edx, 5
0x180019d55  and     edx, 3Fh
0x180019d58  cmp     edx, r10d
0x180019d5b  jnz     short loc_180019D64
0x180019d5d  mov     edx, 1
0x180019d62  jmp     short loc_180019D66
0x180019d64  xor     edx, edx
0x180019d66  mov     [r9+10h], edx
0x180019d6a  mov     edx, ebx
0x180019d6c  xor     edx, eax
0x180019d6e  and     edx, 7E0h
0x180019d74  xor     edx, eax
0x180019d76  or      edx, ecx
0x180019d78  lock cmpxchg [r11+4], edx
0x180019d7e  jnz     short loc_180019D4C
0x180019d80  cmp     dword ptr [r9+10h], 0
0x180019d85  jnz     loc_180019E36
0x180019d8b  mov     [r9+8], r8d
0x180019d8f  mov     dword ptr [r9+4], 1
0x180019d97  mov     [r9+0Ch], edi
0x180019d9b  jmp     loc_180019E36
0x180019da0  xor     ecx, ecx
0x180019da2  sub     r8d, 2
0x180019da6  jz      short loc_180019DCE
0x180019da8  sub     r8d, 1
0x180019dac  jz      short loc_180019DC7
0x180019dae  sub     r8d, 3
0x180019db2  jz      short loc_180019DC0
0x180019db4  cmp     r8d, 1
0x180019db8  jnz     short loc_180019DD3
0x180019dba  lea     ecx, [r8+0Fh]
0x180019dbe  jmp     short loc_180019DD3
0x180019dc0  mov     ecx, 4
0x180019dc5  jmp     short loc_180019DD3
0x180019dc7  mov     ecx, 8
0x180019dcc  jmp     short loc_180019DD3
0x180019dce  mov     ecx, 2
0x180019dd3  mov     edx, [rdx]
0x180019dd5  xor     eax, eax
0x180019dd7  mov     r8d, ecx
0x180019dda  or      r8d, edx
0x180019ddd  cmp     r8d, edx
0x180019de0  mov     r10d, r8d
0x180019de3  setz    al
0x180019de6  or      r10d, 1
0x180019dea  cmp     r8d, edx
0x180019ded  mov     [r9+10h], eax
0x180019df1  mov     eax, edx
0x180019df3  cmovz   r10d, r8d
0x180019df7  lock cmpxchg [r11], r10d
0x180019dfc  jz      short loc_180019E02
0x180019dfe  mov     edx, eax
0x180019e00  jmp     short loc_180019DD5
0x180019e02  test    r10b, 1
0x180019e06  setnz   cl
0x180019e09  test    dl, 1
0x180019e0c  setz    al
0x180019e0f  test    al, cl
0x180019e11  mov     eax, 0
0x180019e16  setnz   al
0x180019e19  mov     [r9], eax
0x180019e1c  jmp     short loc_180019E36
0x180019e1e  mov     edx, r8d
0x180019e21  mov     rcx, r11
0x180019e24  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180019e29  jmp     short loc_180019E36
0x180019e2b  mov     edx, r8d
0x180019e2e  mov     rcx, r11
0x180019e31  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180019e36  mov     rbx, [rsp+28h+arg_0]
0x180019e3b  mov     rax, r9
0x180019e3e  add     rsp, 20h
0x180019e42  pop     rdi
0x180019e43  retn
```
