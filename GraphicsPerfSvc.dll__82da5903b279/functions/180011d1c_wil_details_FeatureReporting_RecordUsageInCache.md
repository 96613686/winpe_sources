# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180011d1c`
- end: `0x180011e97`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ff48`

## callees

- `0x180011b70`
- `0x180011c40`
- `0x180011d1c`

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
0x180011d1c  mov     [rsp+arg_0], rbx
0x180011d21  mov     [rsp+arg_8], rsi
0x180011d26  push    rdi
0x180011d27  sub     rsp, 20h
0x180011d2b  xor     eax, eax
0x180011d2d  xorps   xmm0, xmm0
0x180011d30  mov     esi, r9d
0x180011d33  mov     r11, rdx
0x180011d36  mov     r9, rcx
0x180011d39  mov     r10d, r8d
0x180011d3c  movups  xmmword ptr [rcx], xmm0
0x180011d3f  mov     [rcx+10h], rax
0x180011d43  test    r8d, r8d
0x180011d46  jz      loc_180011E79
0x180011d4c  sub     r10d, 1
0x180011d50  jz      loc_180011E6C
0x180011d56  sub     r10d, 1
0x180011d5a  jz      loc_180011DF3
0x180011d60  sub     r10d, 1
0x180011d64  jz      loc_180011DF3
0x180011d6a  sub     r10d, 1
0x180011d6e  jz      loc_180011E79
0x180011d74  sub     r10d, 1
0x180011d78  jz      loc_180011E6C
0x180011d7e  sub     r10d, 1
0x180011d82  jz      short loc_180011DF3
0x180011d84  cmp     r10d, 1
0x180011d88  jz      short loc_180011DF3
0x180011d8a  lea     ebx, [r8-140h]
0x180011d91  lea     r10d, [rax+1]
0x180011d95  cmp     ebx, 40h ; '@'
0x180011d98  jge     short loc_180011DE2
0x180011d9a  mov     eax, [rdx+4]
0x180011d9d  lea     ecx, [r10+0Fh]
0x180011da1  mov     edi, ebx
0x180011da3  shl     edi, 5
0x180011da6  test    cl, al
0x180011da8  jz      short loc_180011DBB
0x180011daa  mov     edx, eax
0x180011dac  shr     edx, 5
0x180011daf  and     edx, 3Fh
0x180011db2  cmp     edx, ebx
0x180011db4  jnz     short loc_180011DBB
0x180011db6  mov     edx, r10d
0x180011db9  jmp     short loc_180011DBD
0x180011dbb  xor     edx, edx
0x180011dbd  mov     [r9+10h], edx
0x180011dc1  mov     edx, edi
0x180011dc3  xor     edx, eax
0x180011dc5  and     edx, 7E0h
0x180011dcb  xor     edx, eax
0x180011dcd  or      edx, ecx
0x180011dcf  lock cmpxchg [r11+4], edx
0x180011dd5  jnz     short loc_180011DA6
0x180011dd7  cmp     dword ptr [r9+10h], 0
0x180011ddc  jnz     loc_180011E84
0x180011de2  mov     [r9+8], r8d
0x180011de6  mov     [r9+4], r10d
0x180011dea  mov     [r9+0Ch], esi
0x180011dee  jmp     loc_180011E84
0x180011df3  xor     ecx, ecx
0x180011df5  sub     r8d, 2
0x180011df9  jz      short loc_180011E21
0x180011dfb  sub     r8d, 1
0x180011dff  jz      short loc_180011E1A
0x180011e01  sub     r8d, 3
0x180011e05  jz      short loc_180011E13
0x180011e07  cmp     r8d, 1
0x180011e0b  jnz     short loc_180011E26
0x180011e0d  lea     ecx, [r8+0Fh]
0x180011e11  jmp     short loc_180011E26
0x180011e13  mov     ecx, 4
0x180011e18  jmp     short loc_180011E26
0x180011e1a  mov     ecx, 8
0x180011e1f  jmp     short loc_180011E26
0x180011e21  mov     ecx, 2
0x180011e26  mov     edx, [rdx]
0x180011e28  mov     r10d, 1
0x180011e2e  xor     eax, eax
0x180011e30  mov     r8d, ecx
0x180011e33  or      r8d, edx
0x180011e36  cmp     r8d, edx
0x180011e39  mov     ebx, r8d
0x180011e3c  setz    al
0x180011e3f  or      ebx, r10d
0x180011e42  cmp     r8d, edx
0x180011e45  mov     [r9+10h], eax
0x180011e49  mov     eax, edx
0x180011e4b  cmovz   ebx, r8d
0x180011e4f  lock cmpxchg [r11], ebx
0x180011e54  jz      short loc_180011E5A
0x180011e56  mov     edx, eax
0x180011e58  jmp     short loc_180011E2E
0x180011e5a  test    r10b, bl
0x180011e5d  jz      short loc_180011E64
0x180011e5f  test    r10b, dl
0x180011e62  jz      short loc_180011E67
0x180011e64  xor     r10d, r10d
0x180011e67  mov     [r9], r10d
0x180011e6a  jmp     short loc_180011E84
0x180011e6c  mov     edx, r8d
0x180011e6f  mov     rcx, r11
0x180011e72  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180011e77  jmp     short loc_180011E84
0x180011e79  mov     edx, r8d
0x180011e7c  mov     rcx, r11
0x180011e7f  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180011e84  mov     rbx, [rsp+28h+arg_0]
0x180011e89  mov     rax, r9
0x180011e8c  mov     rsi, [rsp+28h+arg_8]
0x180011e91  add     rsp, 20h
0x180011e95  pop     rdi
0x180011e96  retn
```
