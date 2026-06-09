# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180007a84`
- end: `0x180007bff`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007d34`

## callees

- `0x1800078d8`
- `0x1800079a8`
- `0x180007a84`

## pseudocode

```c
int *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  int *v6; // r9
  unsigned int v7; // ebx
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 v15; // edx
  int v16; // r10d
  signed __int32 v17; // ebx
  signed __int32 v18; // eax

  v6 = (int *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_35;
    case 1u:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_34;
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
  v15 = *a2;
  v16 = 1;
  while ( 1 )
  {
    v17 = v15 | v11 | 1;
    v6[4] = (v15 | v11) == v15;
    if ( (v15 | v11) == v15 )
      v17 = v15 | v11;
    v18 = _InterlockedCompareExchange(a2, v17, v15);
    if ( v15 == v18 )
      break;
    v15 = v18;
  }
  if ( (v17 & 1) == 0 || (v15 & 1) != 0 )
    v16 = 0;
  *v6 = v16;
  return v6;
}

```

## disassembly

```asm
0x180007a84  mov     [rsp+arg_0], rbx
0x180007a89  mov     [rsp+arg_8], rsi
0x180007a8e  push    rdi
0x180007a8f  sub     rsp, 20h
0x180007a93  xor     eax, eax
0x180007a95  xorps   xmm0, xmm0
0x180007a98  mov     esi, r9d
0x180007a9b  mov     r11, rdx
0x180007a9e  mov     r9, rcx
0x180007aa1  mov     r10d, r8d
0x180007aa4  movups  xmmword ptr [rcx], xmm0
0x180007aa7  mov     [rcx+10h], rax
0x180007aab  test    r8d, r8d
0x180007aae  jz      loc_180007BE1
0x180007ab4  sub     r10d, 1
0x180007ab8  jz      loc_180007BD4
0x180007abe  sub     r10d, 1
0x180007ac2  jz      loc_180007B5B
0x180007ac8  sub     r10d, 1
0x180007acc  jz      loc_180007B5B
0x180007ad2  sub     r10d, 1
0x180007ad6  jz      loc_180007BE1
0x180007adc  sub     r10d, 1
0x180007ae0  jz      loc_180007BD4
0x180007ae6  sub     r10d, 1
0x180007aea  jz      short loc_180007B5B
0x180007aec  cmp     r10d, 1
0x180007af0  jz      short loc_180007B5B
0x180007af2  lea     ebx, [r8-140h]
0x180007af9  lea     r10d, [rax+1]
0x180007afd  cmp     ebx, 40h ; '@'
0x180007b00  jge     short loc_180007B4A
0x180007b02  mov     eax, [rdx+4]
0x180007b05  lea     ecx, [r10+0Fh]
0x180007b09  mov     edi, ebx
0x180007b0b  shl     edi, 5
0x180007b0e  test    cl, al
0x180007b10  jz      short loc_180007B23
0x180007b12  mov     edx, eax
0x180007b14  shr     edx, 5
0x180007b17  and     edx, 3Fh
0x180007b1a  cmp     edx, ebx
0x180007b1c  jnz     short loc_180007B23
0x180007b1e  mov     edx, r10d
0x180007b21  jmp     short loc_180007B25
0x180007b23  xor     edx, edx
0x180007b25  mov     [r9+10h], edx
0x180007b29  mov     edx, edi
0x180007b2b  xor     edx, eax
0x180007b2d  and     edx, 7E0h
0x180007b33  xor     edx, eax
0x180007b35  or      edx, ecx
0x180007b37  lock cmpxchg [r11+4], edx
0x180007b3d  jnz     short loc_180007B0E
0x180007b3f  cmp     dword ptr [r9+10h], 0
0x180007b44  jnz     loc_180007BEC
0x180007b4a  mov     [r9+8], r8d
0x180007b4e  mov     [r9+4], r10d
0x180007b52  mov     [r9+0Ch], esi
0x180007b56  jmp     loc_180007BEC
0x180007b5b  xor     ecx, ecx
0x180007b5d  sub     r8d, 2
0x180007b61  jz      short loc_180007B89
0x180007b63  sub     r8d, 1
0x180007b67  jz      short loc_180007B82
0x180007b69  sub     r8d, 3
0x180007b6d  jz      short loc_180007B7B
0x180007b6f  cmp     r8d, 1
0x180007b73  jnz     short loc_180007B8E
0x180007b75  lea     ecx, [r8+0Fh]
0x180007b79  jmp     short loc_180007B8E
0x180007b7b  mov     ecx, 4
0x180007b80  jmp     short loc_180007B8E
0x180007b82  mov     ecx, 8
0x180007b87  jmp     short loc_180007B8E
0x180007b89  mov     ecx, 2
0x180007b8e  mov     edx, [rdx]
0x180007b90  mov     r10d, 1
0x180007b96  xor     eax, eax
0x180007b98  mov     r8d, ecx
0x180007b9b  or      r8d, edx
0x180007b9e  cmp     r8d, edx
0x180007ba1  mov     ebx, r8d
0x180007ba4  setz    al
0x180007ba7  or      ebx, r10d
0x180007baa  cmp     r8d, edx
0x180007bad  mov     [r9+10h], eax
0x180007bb1  mov     eax, edx
0x180007bb3  cmovz   ebx, r8d
0x180007bb7  lock cmpxchg [r11], ebx
0x180007bbc  jz      short loc_180007BC2
0x180007bbe  mov     edx, eax
0x180007bc0  jmp     short loc_180007B96
0x180007bc2  test    r10b, bl
0x180007bc5  jz      short loc_180007BCC
0x180007bc7  test    r10b, dl
0x180007bca  jz      short loc_180007BCF
0x180007bcc  xor     r10d, r10d
0x180007bcf  mov     [r9], r10d
0x180007bd2  jmp     short loc_180007BEC
0x180007bd4  mov     edx, r8d
0x180007bd7  mov     rcx, r11
0x180007bda  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180007bdf  jmp     short loc_180007BEC
0x180007be1  mov     edx, r8d
0x180007be4  mov     rcx, r11
0x180007be7  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180007bec  mov     rbx, [rsp+28h+arg_0]
0x180007bf1  mov     rax, r9
0x180007bf4  mov     rsi, [rsp+28h+arg_8]
0x180007bf9  add     rsp, 20h
0x180007bfd  pop     rdi
0x180007bfe  retn
```
