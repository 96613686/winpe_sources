# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000d3b4`
- end: `0x14000d52b`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000462c`

## callees

- `0x14000d208`
- `0x14000d2d8`
- `0x14000d3b4`

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
0x14000d3b4  mov     [rsp+arg_0], rbx
0x14000d3b9  push    rdi
0x14000d3ba  sub     rsp, 20h
0x14000d3be  xor     eax, eax
0x14000d3c0  xorps   xmm0, xmm0
0x14000d3c3  mov     r10, rdx
0x14000d3c6  mov     rbx, rcx
0x14000d3c9  mov     r9d, r8d
0x14000d3cc  movups  xmmword ptr [rcx], xmm0
0x14000d3cf  mov     [rcx+10h], rax
0x14000d3d3  test    r8d, r8d
0x14000d3d6  jz      loc_14000D50F
0x14000d3dc  sub     r9d, 1
0x14000d3e0  jz      loc_14000D4FF
0x14000d3e6  sub     r9d, 1
0x14000d3ea  jz      loc_14000D487
0x14000d3f0  sub     r9d, 1
0x14000d3f4  jz      loc_14000D487
0x14000d3fa  sub     r9d, 1
0x14000d3fe  jz      loc_14000D50F
0x14000d404  sub     r9d, 1
0x14000d408  jz      loc_14000D4FF
0x14000d40e  sub     r9d, 1
0x14000d412  jz      short loc_14000D487
0x14000d414  cmp     r9d, 1
0x14000d418  jz      short loc_14000D487
0x14000d41a  lea     r11d, [r8-140h]
0x14000d421  lea     r9d, [rax+1]
0x14000d425  cmp     r11d, 40h ; '@'
0x14000d429  jge     short loc_14000D473
0x14000d42b  mov     eax, [rdx+4]
0x14000d42e  lea     ecx, [r9+0Fh]
0x14000d432  mov     edi, r11d
0x14000d435  shl     edi, 5
0x14000d438  test    cl, al
0x14000d43a  jz      short loc_14000D44E
0x14000d43c  mov     edx, eax
0x14000d43e  shr     edx, 5
0x14000d441  and     edx, 3Fh
0x14000d444  cmp     edx, r11d
0x14000d447  jnz     short loc_14000D44E
0x14000d449  mov     edx, r9d
0x14000d44c  jmp     short loc_14000D450
0x14000d44e  xor     edx, edx
0x14000d450  mov     [rbx+10h], edx
0x14000d453  mov     edx, edi
0x14000d455  xor     edx, eax
0x14000d457  and     edx, 7E0h
0x14000d45d  xor     edx, eax
0x14000d45f  or      edx, ecx
0x14000d461  lock cmpxchg [r10+4], edx
0x14000d467  jnz     short loc_14000D438
0x14000d469  cmp     dword ptr [rbx+10h], 0
0x14000d46d  jnz     loc_14000D51D
0x14000d473  mov     [rbx+8], r8d
0x14000d477  mov     [rbx+4], r9d
0x14000d47b  mov     dword ptr [rbx+0Ch], 0
0x14000d482  jmp     loc_14000D51D
0x14000d487  xor     ecx, ecx
0x14000d489  sub     r8d, 2
0x14000d48d  jz      short loc_14000D4B5
0x14000d48f  sub     r8d, 1
0x14000d493  jz      short loc_14000D4AE
0x14000d495  sub     r8d, 3
0x14000d499  jz      short loc_14000D4A7
0x14000d49b  cmp     r8d, 1
0x14000d49f  jnz     short loc_14000D4BA
0x14000d4a1  lea     ecx, [r8+0Fh]
0x14000d4a5  jmp     short loc_14000D4BA
0x14000d4a7  mov     ecx, 4
0x14000d4ac  jmp     short loc_14000D4BA
0x14000d4ae  mov     ecx, 8
0x14000d4b3  jmp     short loc_14000D4BA
0x14000d4b5  mov     ecx, 2
0x14000d4ba  mov     edx, [rdx]
0x14000d4bc  mov     r9d, 1
0x14000d4c2  xor     eax, eax
0x14000d4c4  mov     r8d, ecx
0x14000d4c7  or      r8d, edx
0x14000d4ca  cmp     r8d, edx
0x14000d4cd  mov     r11d, r8d
0x14000d4d0  setz    al
0x14000d4d3  or      r11d, r9d
0x14000d4d6  cmp     r8d, edx
0x14000d4d9  mov     [rbx+10h], eax
0x14000d4dc  mov     eax, edx
0x14000d4de  cmovz   r11d, r8d
0x14000d4e2  lock cmpxchg [r10], r11d
0x14000d4e7  jz      short loc_14000D4ED
0x14000d4e9  mov     edx, eax
0x14000d4eb  jmp     short loc_14000D4C2
0x14000d4ed  test    r9b, r11b
0x14000d4f0  jz      short loc_14000D4F7
0x14000d4f2  test    r9b, dl
0x14000d4f5  jz      short loc_14000D4FA
0x14000d4f7  xor     r9d, r9d
0x14000d4fa  mov     [rbx], r9d
0x14000d4fd  jmp     short loc_14000D51D
0x14000d4ff  mov     r9, rbx
0x14000d502  mov     edx, r8d
0x14000d505  mov     rcx, r10
0x14000d508  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14000d50d  jmp     short loc_14000D51D
0x14000d50f  mov     r9, rbx
0x14000d512  mov     edx, r8d
0x14000d515  mov     rcx, r10
0x14000d518  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14000d51d  mov     rax, rbx
0x14000d520  mov     rbx, [rsp+28h+arg_0]
0x14000d525  add     rsp, 20h
0x14000d529  pop     rdi
0x14000d52a  retn
```
