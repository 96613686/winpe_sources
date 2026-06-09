# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140001ad4`
- end: `0x140001c51`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001cd4`

## callees

- `0x140001928`
- `0x1400019f8`
- `0x140001ad4`

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
0x140001ad4  mov     [rsp+arg_0], rbx
0x140001ad9  push    rdi
0x140001ada  sub     rsp, 20h
0x140001ade  xor     eax, eax
0x140001ae0  xorps   xmm0, xmm0
0x140001ae3  mov     edi, r9d
0x140001ae6  mov     r11, rdx
0x140001ae9  mov     r9, rcx
0x140001aec  mov     r10d, r8d
0x140001aef  movups  xmmword ptr [rcx], xmm0
0x140001af2  mov     [rcx+10h], rax
0x140001af6  test    r8d, r8d
0x140001af9  jz      loc_140001C37
0x140001aff  sub     r10d, 1
0x140001b03  jz      loc_140001C2A
0x140001b09  sub     r10d, 1
0x140001b0d  jz      loc_140001BAC
0x140001b13  sub     r10d, 1
0x140001b17  jz      loc_140001BAC
0x140001b1d  sub     r10d, 1
0x140001b21  jz      loc_140001C37
0x140001b27  sub     r10d, 1
0x140001b2b  jz      loc_140001C2A
0x140001b31  sub     r10d, 1
0x140001b35  jz      short loc_140001BAC
0x140001b37  cmp     r10d, 1
0x140001b3b  jz      short loc_140001BAC
0x140001b3d  lea     r10d, [r8-140h]
0x140001b44  cmp     r10d, 40h ; '@'
0x140001b48  jge     short loc_140001B97
0x140001b4a  mov     eax, [rdx+4]
0x140001b4d  mov     ebx, r10d
0x140001b50  shl     ebx, 5
0x140001b53  mov     ecx, 10h
0x140001b58  test    cl, al
0x140001b5a  jz      short loc_140001B70
0x140001b5c  mov     edx, eax
0x140001b5e  shr     edx, 5
0x140001b61  and     edx, 3Fh
0x140001b64  cmp     edx, r10d
0x140001b67  jnz     short loc_140001B70
0x140001b69  mov     edx, 1
0x140001b6e  jmp     short loc_140001B72
0x140001b70  xor     edx, edx
0x140001b72  mov     [r9+10h], edx
0x140001b76  mov     edx, ebx
0x140001b78  xor     edx, eax
0x140001b7a  and     edx, 7E0h
0x140001b80  xor     edx, eax
0x140001b82  or      edx, ecx
0x140001b84  lock cmpxchg [r11+4], edx
0x140001b8a  jnz     short loc_140001B58
0x140001b8c  cmp     dword ptr [r9+10h], 0
0x140001b91  jnz     loc_140001C42
0x140001b97  mov     [r9+8], r8d
0x140001b9b  mov     dword ptr [r9+4], 1
0x140001ba3  mov     [r9+0Ch], edi
0x140001ba7  jmp     loc_140001C42
0x140001bac  xor     ecx, ecx
0x140001bae  sub     r8d, 2
0x140001bb2  jz      short loc_140001BDA
0x140001bb4  sub     r8d, 1
0x140001bb8  jz      short loc_140001BD3
0x140001bba  sub     r8d, 3
0x140001bbe  jz      short loc_140001BCC
0x140001bc0  cmp     r8d, 1
0x140001bc4  jnz     short loc_140001BDF
0x140001bc6  lea     ecx, [r8+0Fh]
0x140001bca  jmp     short loc_140001BDF
0x140001bcc  mov     ecx, 4
0x140001bd1  jmp     short loc_140001BDF
0x140001bd3  mov     ecx, 8
0x140001bd8  jmp     short loc_140001BDF
0x140001bda  mov     ecx, 2
0x140001bdf  mov     edx, [rdx]
0x140001be1  xor     eax, eax
0x140001be3  mov     r8d, ecx
0x140001be6  or      r8d, edx
0x140001be9  cmp     r8d, edx
0x140001bec  mov     r10d, r8d
0x140001bef  setz    al
0x140001bf2  or      r10d, 1
0x140001bf6  cmp     r8d, edx
0x140001bf9  mov     [r9+10h], eax
0x140001bfd  mov     eax, edx
0x140001bff  cmovz   r10d, r8d
0x140001c03  lock cmpxchg [r11], r10d
0x140001c08  jz      short loc_140001C0E
0x140001c0a  mov     edx, eax
0x140001c0c  jmp     short loc_140001BE1
0x140001c0e  test    r10b, 1
0x140001c12  setnz   cl
0x140001c15  test    dl, 1
0x140001c18  setz    al
0x140001c1b  test    al, cl
0x140001c1d  mov     eax, 0
0x140001c22  setnz   al
0x140001c25  mov     [r9], eax
0x140001c28  jmp     short loc_140001C42
0x140001c2a  mov     edx, r8d
0x140001c2d  mov     rcx, r11
0x140001c30  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x140001c35  jmp     short loc_140001C42
0x140001c37  mov     edx, r8d
0x140001c3a  mov     rcx, r11
0x140001c3d  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140001c42  mov     rbx, [rsp+28h+arg_0]
0x140001c47  mov     rax, r9
0x140001c4a  add     rsp, 20h
0x140001c4e  pop     rdi
0x140001c4f  retn
```
