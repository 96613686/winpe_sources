# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000495c`
- end: `0x140004ad9`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: `_DWORD *__fastcall(__int64, volatile signed __int32 *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004b68`

## callees

- `0x1400047b0`
- `0x140004880`
- `0x14000495c`

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
0x14000495c  mov     [rsp+arg_0], rbx
0x140004961  push    rdi
0x140004962  sub     rsp, 20h
0x140004966  xor     eax, eax
0x140004968  xorps   xmm0, xmm0
0x14000496b  mov     edi, r9d
0x14000496e  mov     r11, rdx
0x140004971  mov     r9, rcx
0x140004974  mov     r10d, r8d
0x140004977  movups  xmmword ptr [rcx], xmm0
0x14000497a  mov     [rcx+10h], rax
0x14000497e  test    r8d, r8d
0x140004981  jz      loc_140004ABF
0x140004987  sub     r10d, 1
0x14000498b  jz      loc_140004AB2
0x140004991  sub     r10d, 1
0x140004995  jz      loc_140004A34
0x14000499b  sub     r10d, 1
0x14000499f  jz      loc_140004A34
0x1400049a5  sub     r10d, 1
0x1400049a9  jz      loc_140004ABF
0x1400049af  sub     r10d, 1
0x1400049b3  jz      loc_140004AB2
0x1400049b9  sub     r10d, 1
0x1400049bd  jz      short loc_140004A34
0x1400049bf  cmp     r10d, 1
0x1400049c3  jz      short loc_140004A34
0x1400049c5  lea     r10d, [r8-140h]
0x1400049cc  cmp     r10d, 40h ; '@'
0x1400049d0  jge     short loc_140004A1F
0x1400049d2  mov     eax, [rdx+4]
0x1400049d5  mov     ebx, r10d
0x1400049d8  shl     ebx, 5
0x1400049db  mov     ecx, 10h
0x1400049e0  test    cl, al
0x1400049e2  jz      short loc_1400049F8
0x1400049e4  mov     edx, eax
0x1400049e6  shr     edx, 5
0x1400049e9  and     edx, 3Fh
0x1400049ec  cmp     edx, r10d
0x1400049ef  jnz     short loc_1400049F8
0x1400049f1  mov     edx, 1
0x1400049f6  jmp     short loc_1400049FA
0x1400049f8  xor     edx, edx
0x1400049fa  mov     [r9+10h], edx
0x1400049fe  mov     edx, ebx
0x140004a00  xor     edx, eax
0x140004a02  and     edx, 7E0h
0x140004a08  xor     edx, eax
0x140004a0a  or      edx, ecx
0x140004a0c  lock cmpxchg [r11+4], edx
0x140004a12  jnz     short loc_1400049E0
0x140004a14  cmp     dword ptr [r9+10h], 0
0x140004a19  jnz     loc_140004ACA
0x140004a1f  mov     [r9+8], r8d
0x140004a23  mov     dword ptr [r9+4], 1
0x140004a2b  mov     [r9+0Ch], edi
0x140004a2f  jmp     loc_140004ACA
0x140004a34  xor     ecx, ecx
0x140004a36  sub     r8d, 2
0x140004a3a  jz      short loc_140004A62
0x140004a3c  sub     r8d, 1
0x140004a40  jz      short loc_140004A5B
0x140004a42  sub     r8d, 3
0x140004a46  jz      short loc_140004A54
0x140004a48  cmp     r8d, 1
0x140004a4c  jnz     short loc_140004A67
0x140004a4e  lea     ecx, [r8+0Fh]
0x140004a52  jmp     short loc_140004A67
0x140004a54  mov     ecx, 4
0x140004a59  jmp     short loc_140004A67
0x140004a5b  mov     ecx, 8
0x140004a60  jmp     short loc_140004A67
0x140004a62  mov     ecx, 2
0x140004a67  mov     edx, [rdx]
0x140004a69  xor     eax, eax
0x140004a6b  mov     r8d, ecx
0x140004a6e  or      r8d, edx
0x140004a71  cmp     r8d, edx
0x140004a74  mov     r10d, r8d
0x140004a77  setz    al
0x140004a7a  or      r10d, 1
0x140004a7e  cmp     r8d, edx
0x140004a81  mov     [r9+10h], eax
0x140004a85  mov     eax, edx
0x140004a87  cmovz   r10d, r8d
0x140004a8b  lock cmpxchg [r11], r10d
0x140004a90  jz      short loc_140004A96
0x140004a92  mov     edx, eax
0x140004a94  jmp     short loc_140004A69
0x140004a96  test    r10b, 1
0x140004a9a  setnz   cl
0x140004a9d  test    dl, 1
0x140004aa0  setz    al
0x140004aa3  test    al, cl
0x140004aa5  mov     eax, 0
0x140004aaa  setnz   al
0x140004aad  mov     [r9], eax
0x140004ab0  jmp     short loc_140004ACA
0x140004ab2  mov     edx, r8d
0x140004ab5  mov     rcx, r11
0x140004ab8  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x140004abd  jmp     short loc_140004ACA
0x140004abf  mov     edx, r8d
0x140004ac2  mov     rcx, r11
0x140004ac5  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140004aca  mov     rbx, [rsp+28h+arg_0]
0x140004acf  mov     rax, r9
0x140004ad2  add     rsp, 20h
0x140004ad6  pop     rdi
0x140004ad7  retn
```
