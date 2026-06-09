# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000ed04`
- end: `0x18000ee7a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `374`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cd98`

## callees

- `0x18000eb58`
- `0x18000ec28`
- `0x18000ed04`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r9d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 i; // edx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_31;
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
  for ( i = *a2; ; i = v15 )
  {
    v14 = i | v9 | 1;
    *(_DWORD *)(a1 + 16) = (i | v9) == i;
    if ( (i | v9) == i )
      v14 = i | v9;
    v15 = _InterlockedCompareExchange(a2, v14, i);
    if ( i == v15 )
      break;
  }
  *(_DWORD *)a1 = (v14 & 1) != 0 && (i & 1) == 0;
  return a1;
}

```

## disassembly

```asm
0x18000ed04  push    rbx
0x18000ed06  sub     rsp, 20h
0x18000ed0a  xor     eax, eax
0x18000ed0c  xorps   xmm0, xmm0
0x18000ed0f  mov     r10, rdx
0x18000ed12  mov     rbx, rcx
0x18000ed15  mov     r9d, r8d
0x18000ed18  movups  xmmword ptr [rcx], xmm0
0x18000ed1b  mov     [rcx+10h], rax
0x18000ed1f  test    r8d, r8d
0x18000ed22  jz      loc_18000EE63
0x18000ed28  sub     r9d, 1
0x18000ed2c  jz      loc_18000EE53
0x18000ed32  sub     r9d, 1
0x18000ed36  jz      loc_18000EDD7
0x18000ed3c  sub     r9d, 1
0x18000ed40  jz      loc_18000EDD7
0x18000ed46  sub     r9d, 1
0x18000ed4a  jz      loc_18000EE63
0x18000ed50  sub     r9d, 1
0x18000ed54  jz      loc_18000EE53
0x18000ed5a  sub     r9d, 1
0x18000ed5e  jz      short loc_18000EDD7
0x18000ed60  cmp     r9d, 1
0x18000ed64  jz      short loc_18000EDD7
0x18000ed66  lea     r9d, [r8-140h]
0x18000ed6d  cmp     r9d, 40h ; '@'
0x18000ed71  jge     short loc_18000EDC0
0x18000ed73  mov     eax, [rdx+4]
0x18000ed76  mov     r11d, r9d
0x18000ed79  shl     r11d, 5
0x18000ed7d  mov     ecx, 10h
0x18000ed82  test    cl, al
0x18000ed84  jz      short loc_18000ED9A
0x18000ed86  mov     edx, eax
0x18000ed88  shr     edx, 5
0x18000ed8b  and     edx, 3Fh
0x18000ed8e  cmp     edx, r9d
0x18000ed91  jnz     short loc_18000ED9A
0x18000ed93  mov     edx, 1
0x18000ed98  jmp     short loc_18000ED9C
0x18000ed9a  xor     edx, edx
0x18000ed9c  mov     [rbx+10h], edx
0x18000ed9f  mov     edx, r11d
0x18000eda2  xor     edx, eax
0x18000eda4  and     edx, 7E0h
0x18000edaa  xor     edx, eax
0x18000edac  or      edx, ecx
0x18000edae  lock cmpxchg [r10+4], edx
0x18000edb4  jnz     short loc_18000ED82
0x18000edb6  cmp     dword ptr [rbx+10h], 0
0x18000edba  jnz     loc_18000EE71
0x18000edc0  mov     [rbx+8], r8d
0x18000edc4  mov     dword ptr [rbx+4], 1
0x18000edcb  mov     dword ptr [rbx+0Ch], 0
0x18000edd2  jmp     loc_18000EE71
0x18000edd7  xor     ecx, ecx
0x18000edd9  sub     r8d, 2
0x18000eddd  jz      short loc_18000EE05
0x18000eddf  sub     r8d, 1
0x18000ede3  jz      short loc_18000EDFE
0x18000ede5  sub     r8d, 3
0x18000ede9  jz      short loc_18000EDF7
0x18000edeb  cmp     r8d, 1
0x18000edef  jnz     short loc_18000EE0A
0x18000edf1  lea     ecx, [r8+0Fh]
0x18000edf5  jmp     short loc_18000EE0A
0x18000edf7  mov     ecx, 4
0x18000edfc  jmp     short loc_18000EE0A
0x18000edfe  mov     ecx, 8
0x18000ee03  jmp     short loc_18000EE0A
0x18000ee05  mov     ecx, 2
0x18000ee0a  mov     edx, [rdx]
0x18000ee0c  xor     eax, eax
0x18000ee0e  mov     r8d, ecx
0x18000ee11  or      r8d, edx
0x18000ee14  cmp     r8d, edx
0x18000ee17  mov     r9d, r8d
0x18000ee1a  setz    al
0x18000ee1d  or      r9d, 1
0x18000ee21  cmp     r8d, edx
0x18000ee24  mov     [rbx+10h], eax
0x18000ee27  mov     eax, edx
0x18000ee29  cmovz   r9d, r8d
0x18000ee2d  lock cmpxchg [r10], r9d
0x18000ee32  jz      short loc_18000EE38
0x18000ee34  mov     edx, eax
0x18000ee36  jmp     short loc_18000EE0C
0x18000ee38  test    r9b, 1
0x18000ee3c  setnz   cl
0x18000ee3f  test    dl, 1
0x18000ee42  setz    al
0x18000ee45  test    al, cl
0x18000ee47  mov     eax, 0
0x18000ee4c  setnz   al
0x18000ee4f  mov     [rbx], eax
0x18000ee51  jmp     short loc_18000EE71
0x18000ee53  mov     r9, rbx
0x18000ee56  mov     edx, r8d
0x18000ee59  mov     rcx, r10
0x18000ee5c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000ee61  jmp     short loc_18000EE71
0x18000ee63  mov     r9, rbx
0x18000ee66  mov     edx, r8d
0x18000ee69  mov     rcx, r10
0x18000ee6c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000ee71  mov     rax, rbx
0x18000ee74  add     rsp, 20h
0x18000ee78  pop     rbx
0x18000ee79  retn
```
