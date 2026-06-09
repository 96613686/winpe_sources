# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000be58`
- end: `0x14000bfcf`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a330`

## callees

- `0x14000bcac`
- `0x14000bd7c`
- `0x14000be58`

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
0x14000be58  mov     [rsp+arg_0], rbx
0x14000be5d  push    rdi
0x14000be5e  sub     rsp, 20h
0x14000be62  xor     eax, eax
0x14000be64  xorps   xmm0, xmm0
0x14000be67  mov     r10, rdx
0x14000be6a  mov     rbx, rcx
0x14000be6d  mov     r9d, r8d
0x14000be70  movups  xmmword ptr [rcx], xmm0
0x14000be73  mov     [rcx+10h], rax
0x14000be77  test    r8d, r8d
0x14000be7a  jz      loc_14000BFB3
0x14000be80  sub     r9d, 1
0x14000be84  jz      loc_14000BFA3
0x14000be8a  sub     r9d, 1
0x14000be8e  jz      loc_14000BF2B
0x14000be94  sub     r9d, 1
0x14000be98  jz      loc_14000BF2B
0x14000be9e  sub     r9d, 1
0x14000bea2  jz      loc_14000BFB3
0x14000bea8  sub     r9d, 1
0x14000beac  jz      loc_14000BFA3
0x14000beb2  sub     r9d, 1
0x14000beb6  jz      short loc_14000BF2B
0x14000beb8  cmp     r9d, 1
0x14000bebc  jz      short loc_14000BF2B
0x14000bebe  lea     r11d, [r8-140h]
0x14000bec5  lea     r9d, [rax+1]
0x14000bec9  cmp     r11d, 40h ; '@'
0x14000becd  jge     short loc_14000BF17
0x14000becf  mov     eax, [rdx+4]
0x14000bed2  lea     ecx, [r9+0Fh]
0x14000bed6  mov     edi, r11d
0x14000bed9  shl     edi, 5
0x14000bedc  test    cl, al
0x14000bede  jz      short loc_14000BEF2
0x14000bee0  mov     edx, eax
0x14000bee2  shr     edx, 5
0x14000bee5  and     edx, 3Fh
0x14000bee8  cmp     edx, r11d
0x14000beeb  jnz     short loc_14000BEF2
0x14000beed  mov     edx, r9d
0x14000bef0  jmp     short loc_14000BEF4
0x14000bef2  xor     edx, edx
0x14000bef4  mov     [rbx+10h], edx
0x14000bef7  mov     edx, edi
0x14000bef9  xor     edx, eax
0x14000befb  and     edx, 7E0h
0x14000bf01  xor     edx, eax
0x14000bf03  or      edx, ecx
0x14000bf05  lock cmpxchg [r10+4], edx
0x14000bf0b  jnz     short loc_14000BEDC
0x14000bf0d  cmp     dword ptr [rbx+10h], 0
0x14000bf11  jnz     loc_14000BFC1
0x14000bf17  mov     [rbx+8], r8d
0x14000bf1b  mov     [rbx+4], r9d
0x14000bf1f  mov     dword ptr [rbx+0Ch], 0
0x14000bf26  jmp     loc_14000BFC1
0x14000bf2b  xor     ecx, ecx
0x14000bf2d  sub     r8d, 2
0x14000bf31  jz      short loc_14000BF59
0x14000bf33  sub     r8d, 1
0x14000bf37  jz      short loc_14000BF52
0x14000bf39  sub     r8d, 3
0x14000bf3d  jz      short loc_14000BF4B
0x14000bf3f  cmp     r8d, 1
0x14000bf43  jnz     short loc_14000BF5E
0x14000bf45  lea     ecx, [r8+0Fh]
0x14000bf49  jmp     short loc_14000BF5E
0x14000bf4b  mov     ecx, 4
0x14000bf50  jmp     short loc_14000BF5E
0x14000bf52  mov     ecx, 8
0x14000bf57  jmp     short loc_14000BF5E
0x14000bf59  mov     ecx, 2
0x14000bf5e  mov     edx, [rdx]
0x14000bf60  mov     r9d, 1
0x14000bf66  xor     eax, eax
0x14000bf68  mov     r8d, ecx
0x14000bf6b  or      r8d, edx
0x14000bf6e  cmp     r8d, edx
0x14000bf71  mov     r11d, r8d
0x14000bf74  setz    al
0x14000bf77  or      r11d, r9d
0x14000bf7a  cmp     r8d, edx
0x14000bf7d  mov     [rbx+10h], eax
0x14000bf80  mov     eax, edx
0x14000bf82  cmovz   r11d, r8d
0x14000bf86  lock cmpxchg [r10], r11d
0x14000bf8b  jz      short loc_14000BF91
0x14000bf8d  mov     edx, eax
0x14000bf8f  jmp     short loc_14000BF66
0x14000bf91  test    r9b, r11b
0x14000bf94  jz      short loc_14000BF9B
0x14000bf96  test    r9b, dl
0x14000bf99  jz      short loc_14000BF9E
0x14000bf9b  xor     r9d, r9d
0x14000bf9e  mov     [rbx], r9d
0x14000bfa1  jmp     short loc_14000BFC1
0x14000bfa3  mov     r9, rbx
0x14000bfa6  mov     edx, r8d
0x14000bfa9  mov     rcx, r10
0x14000bfac  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14000bfb1  jmp     short loc_14000BFC1
0x14000bfb3  mov     r9, rbx
0x14000bfb6  mov     edx, r8d
0x14000bfb9  mov     rcx, r10
0x14000bfbc  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14000bfc1  mov     rax, rbx
0x14000bfc4  mov     rbx, [rsp+28h+arg_0]
0x14000bfc9  add     rsp, 20h
0x14000bfcd  pop     rdi
0x14000bfce  retn
```
