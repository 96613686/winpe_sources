# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000b8e8`
- end: `0x18000ba5f`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009208`

## callees

- `0x18000b73c`
- `0x18000b80c`
- `0x18000b8e8`

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
0x18000b8e8  mov     [rsp+arg_0], rbx
0x18000b8ed  push    rdi
0x18000b8ee  sub     rsp, 20h
0x18000b8f2  xor     eax, eax
0x18000b8f4  xorps   xmm0, xmm0
0x18000b8f7  mov     r10, rdx
0x18000b8fa  mov     rbx, rcx
0x18000b8fd  mov     r9d, r8d
0x18000b900  movups  xmmword ptr [rcx], xmm0
0x18000b903  mov     [rcx+10h], rax
0x18000b907  test    r8d, r8d
0x18000b90a  jz      loc_18000BA43
0x18000b910  sub     r9d, 1
0x18000b914  jz      loc_18000BA33
0x18000b91a  sub     r9d, 1
0x18000b91e  jz      loc_18000B9BB
0x18000b924  sub     r9d, 1
0x18000b928  jz      loc_18000B9BB
0x18000b92e  sub     r9d, 1
0x18000b932  jz      loc_18000BA43
0x18000b938  sub     r9d, 1
0x18000b93c  jz      loc_18000BA33
0x18000b942  sub     r9d, 1
0x18000b946  jz      short loc_18000B9BB
0x18000b948  cmp     r9d, 1
0x18000b94c  jz      short loc_18000B9BB
0x18000b94e  lea     r11d, [r8-140h]
0x18000b955  lea     r9d, [rax+1]
0x18000b959  cmp     r11d, 40h ; '@'
0x18000b95d  jge     short loc_18000B9A7
0x18000b95f  mov     eax, [rdx+4]
0x18000b962  lea     ecx, [r9+0Fh]
0x18000b966  mov     edi, r11d
0x18000b969  shl     edi, 5
0x18000b96c  test    cl, al
0x18000b96e  jz      short loc_18000B982
0x18000b970  mov     edx, eax
0x18000b972  shr     edx, 5
0x18000b975  and     edx, 3Fh
0x18000b978  cmp     edx, r11d
0x18000b97b  jnz     short loc_18000B982
0x18000b97d  mov     edx, r9d
0x18000b980  jmp     short loc_18000B984
0x18000b982  xor     edx, edx
0x18000b984  mov     [rbx+10h], edx
0x18000b987  mov     edx, edi
0x18000b989  xor     edx, eax
0x18000b98b  and     edx, 7E0h
0x18000b991  xor     edx, eax
0x18000b993  or      edx, ecx
0x18000b995  lock cmpxchg [r10+4], edx
0x18000b99b  jnz     short loc_18000B96C
0x18000b99d  cmp     dword ptr [rbx+10h], 0
0x18000b9a1  jnz     loc_18000BA51
0x18000b9a7  mov     [rbx+8], r8d
0x18000b9ab  mov     [rbx+4], r9d
0x18000b9af  mov     dword ptr [rbx+0Ch], 0
0x18000b9b6  jmp     loc_18000BA51
0x18000b9bb  xor     ecx, ecx
0x18000b9bd  sub     r8d, 2
0x18000b9c1  jz      short loc_18000B9E9
0x18000b9c3  sub     r8d, 1
0x18000b9c7  jz      short loc_18000B9E2
0x18000b9c9  sub     r8d, 3
0x18000b9cd  jz      short loc_18000B9DB
0x18000b9cf  cmp     r8d, 1
0x18000b9d3  jnz     short loc_18000B9EE
0x18000b9d5  lea     ecx, [r8+0Fh]
0x18000b9d9  jmp     short loc_18000B9EE
0x18000b9db  mov     ecx, 4
0x18000b9e0  jmp     short loc_18000B9EE
0x18000b9e2  mov     ecx, 8
0x18000b9e7  jmp     short loc_18000B9EE
0x18000b9e9  mov     ecx, 2
0x18000b9ee  mov     edx, [rdx]
0x18000b9f0  mov     r9d, 1
0x18000b9f6  xor     eax, eax
0x18000b9f8  mov     r8d, ecx
0x18000b9fb  or      r8d, edx
0x18000b9fe  cmp     r8d, edx
0x18000ba01  mov     r11d, r8d
0x18000ba04  setz    al
0x18000ba07  or      r11d, r9d
0x18000ba0a  cmp     r8d, edx
0x18000ba0d  mov     [rbx+10h], eax
0x18000ba10  mov     eax, edx
0x18000ba12  cmovz   r11d, r8d
0x18000ba16  lock cmpxchg [r10], r11d
0x18000ba1b  jz      short loc_18000BA21
0x18000ba1d  mov     edx, eax
0x18000ba1f  jmp     short loc_18000B9F6
0x18000ba21  test    r9b, r11b
0x18000ba24  jz      short loc_18000BA2B
0x18000ba26  test    r9b, dl
0x18000ba29  jz      short loc_18000BA2E
0x18000ba2b  xor     r9d, r9d
0x18000ba2e  mov     [rbx], r9d
0x18000ba31  jmp     short loc_18000BA51
0x18000ba33  mov     r9, rbx
0x18000ba36  mov     edx, r8d
0x18000ba39  mov     rcx, r10
0x18000ba3c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000ba41  jmp     short loc_18000BA51
0x18000ba43  mov     r9, rbx
0x18000ba46  mov     edx, r8d
0x18000ba49  mov     rcx, r10
0x18000ba4c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000ba51  mov     rax, rbx
0x18000ba54  mov     rbx, [rsp+28h+arg_0]
0x18000ba59  add     rsp, 20h
0x18000ba5d  pop     rdi
0x18000ba5e  retn
```
