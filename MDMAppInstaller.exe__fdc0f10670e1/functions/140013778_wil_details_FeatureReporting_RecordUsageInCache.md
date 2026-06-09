# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140013778`
- end: `0x1400138ef`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010260`

## callees

- `0x1400135cc`
- `0x14001369c`
- `0x140013778`

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
0x140013778  mov     [rsp+arg_0], rbx
0x14001377d  push    rdi
0x14001377e  sub     rsp, 20h
0x140013782  xor     eax, eax
0x140013784  xorps   xmm0, xmm0
0x140013787  mov     r10, rdx
0x14001378a  mov     rbx, rcx
0x14001378d  mov     r9d, r8d
0x140013790  movups  xmmword ptr [rcx], xmm0
0x140013793  mov     [rcx+10h], rax
0x140013797  test    r8d, r8d
0x14001379a  jz      loc_1400138D3
0x1400137a0  sub     r9d, 1
0x1400137a4  jz      loc_1400138C3
0x1400137aa  sub     r9d, 1
0x1400137ae  jz      loc_14001384B
0x1400137b4  sub     r9d, 1
0x1400137b8  jz      loc_14001384B
0x1400137be  sub     r9d, 1
0x1400137c2  jz      loc_1400138D3
0x1400137c8  sub     r9d, 1
0x1400137cc  jz      loc_1400138C3
0x1400137d2  sub     r9d, 1
0x1400137d6  jz      short loc_14001384B
0x1400137d8  cmp     r9d, 1
0x1400137dc  jz      short loc_14001384B
0x1400137de  lea     r11d, [r8-140h]
0x1400137e5  lea     r9d, [rax+1]
0x1400137e9  cmp     r11d, 40h ; '@'
0x1400137ed  jge     short loc_140013837
0x1400137ef  mov     eax, [rdx+4]
0x1400137f2  lea     ecx, [r9+0Fh]
0x1400137f6  mov     edi, r11d
0x1400137f9  shl     edi, 5
0x1400137fc  test    cl, al
0x1400137fe  jz      short loc_140013812
0x140013800  mov     edx, eax
0x140013802  shr     edx, 5
0x140013805  and     edx, 3Fh
0x140013808  cmp     edx, r11d
0x14001380b  jnz     short loc_140013812
0x14001380d  mov     edx, r9d
0x140013810  jmp     short loc_140013814
0x140013812  xor     edx, edx
0x140013814  mov     [rbx+10h], edx
0x140013817  mov     edx, edi
0x140013819  xor     edx, eax
0x14001381b  and     edx, 7E0h
0x140013821  xor     edx, eax
0x140013823  or      edx, ecx
0x140013825  lock cmpxchg [r10+4], edx
0x14001382b  jnz     short loc_1400137FC
0x14001382d  cmp     dword ptr [rbx+10h], 0
0x140013831  jnz     loc_1400138E1
0x140013837  mov     [rbx+8], r8d
0x14001383b  mov     [rbx+4], r9d
0x14001383f  mov     dword ptr [rbx+0Ch], 0
0x140013846  jmp     loc_1400138E1
0x14001384b  xor     ecx, ecx
0x14001384d  sub     r8d, 2
0x140013851  jz      short loc_140013879
0x140013853  sub     r8d, 1
0x140013857  jz      short loc_140013872
0x140013859  sub     r8d, 3
0x14001385d  jz      short loc_14001386B
0x14001385f  cmp     r8d, 1
0x140013863  jnz     short loc_14001387E
0x140013865  lea     ecx, [r8+0Fh]
0x140013869  jmp     short loc_14001387E
0x14001386b  mov     ecx, 4
0x140013870  jmp     short loc_14001387E
0x140013872  mov     ecx, 8
0x140013877  jmp     short loc_14001387E
0x140013879  mov     ecx, 2
0x14001387e  mov     edx, [rdx]
0x140013880  mov     r9d, 1
0x140013886  xor     eax, eax
0x140013888  mov     r8d, ecx
0x14001388b  or      r8d, edx
0x14001388e  cmp     r8d, edx
0x140013891  mov     r11d, r8d
0x140013894  setz    al
0x140013897  or      r11d, r9d
0x14001389a  cmp     r8d, edx
0x14001389d  mov     [rbx+10h], eax
0x1400138a0  mov     eax, edx
0x1400138a2  cmovz   r11d, r8d
0x1400138a6  lock cmpxchg [r10], r11d
0x1400138ab  jz      short loc_1400138B1
0x1400138ad  mov     edx, eax
0x1400138af  jmp     short loc_140013886
0x1400138b1  test    r9b, r11b
0x1400138b4  jz      short loc_1400138BB
0x1400138b6  test    r9b, dl
0x1400138b9  jz      short loc_1400138BE
0x1400138bb  xor     r9d, r9d
0x1400138be  mov     [rbx], r9d
0x1400138c1  jmp     short loc_1400138E1
0x1400138c3  mov     r9, rbx
0x1400138c6  mov     edx, r8d
0x1400138c9  mov     rcx, r10
0x1400138cc  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1400138d1  jmp     short loc_1400138E1
0x1400138d3  mov     r9, rbx
0x1400138d6  mov     edx, r8d
0x1400138d9  mov     rcx, r10
0x1400138dc  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1400138e1  mov     rax, rbx
0x1400138e4  mov     rbx, [rsp+28h+arg_0]
0x1400138e9  add     rsp, 20h
0x1400138ed  pop     rdi
0x1400138ee  retn
```
