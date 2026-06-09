# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000bad8`
- end: `0x18000bc4f`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a768`

## callees

- `0x18000b92c`
- `0x18000b9fc`
- `0x18000bad8`

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
0x18000bad8  mov     [rsp+arg_0], rbx
0x18000badd  push    rdi
0x18000bade  sub     rsp, 20h
0x18000bae2  xor     eax, eax
0x18000bae4  xorps   xmm0, xmm0
0x18000bae7  mov     r10, rdx
0x18000baea  mov     rbx, rcx
0x18000baed  mov     r9d, r8d
0x18000baf0  movups  xmmword ptr [rcx], xmm0
0x18000baf3  mov     [rcx+10h], rax
0x18000baf7  test    r8d, r8d
0x18000bafa  jz      loc_18000BC33
0x18000bb00  sub     r9d, 1
0x18000bb04  jz      loc_18000BC23
0x18000bb0a  sub     r9d, 1
0x18000bb0e  jz      loc_18000BBAB
0x18000bb14  sub     r9d, 1
0x18000bb18  jz      loc_18000BBAB
0x18000bb1e  sub     r9d, 1
0x18000bb22  jz      loc_18000BC33
0x18000bb28  sub     r9d, 1
0x18000bb2c  jz      loc_18000BC23
0x18000bb32  sub     r9d, 1
0x18000bb36  jz      short loc_18000BBAB
0x18000bb38  cmp     r9d, 1
0x18000bb3c  jz      short loc_18000BBAB
0x18000bb3e  lea     r11d, [r8-140h]
0x18000bb45  lea     r9d, [rax+1]
0x18000bb49  cmp     r11d, 40h ; '@'
0x18000bb4d  jge     short loc_18000BB97
0x18000bb4f  mov     eax, [rdx+4]
0x18000bb52  lea     ecx, [r9+0Fh]
0x18000bb56  mov     edi, r11d
0x18000bb59  shl     edi, 5
0x18000bb5c  test    cl, al
0x18000bb5e  jz      short loc_18000BB72
0x18000bb60  mov     edx, eax
0x18000bb62  shr     edx, 5
0x18000bb65  and     edx, 3Fh
0x18000bb68  cmp     edx, r11d
0x18000bb6b  jnz     short loc_18000BB72
0x18000bb6d  mov     edx, r9d
0x18000bb70  jmp     short loc_18000BB74
0x18000bb72  xor     edx, edx
0x18000bb74  mov     [rbx+10h], edx
0x18000bb77  mov     edx, edi
0x18000bb79  xor     edx, eax
0x18000bb7b  and     edx, 7E0h
0x18000bb81  xor     edx, eax
0x18000bb83  or      edx, ecx
0x18000bb85  lock cmpxchg [r10+4], edx
0x18000bb8b  jnz     short loc_18000BB5C
0x18000bb8d  cmp     dword ptr [rbx+10h], 0
0x18000bb91  jnz     loc_18000BC41
0x18000bb97  mov     [rbx+8], r8d
0x18000bb9b  mov     [rbx+4], r9d
0x18000bb9f  mov     dword ptr [rbx+0Ch], 0
0x18000bba6  jmp     loc_18000BC41
0x18000bbab  xor     ecx, ecx
0x18000bbad  sub     r8d, 2
0x18000bbb1  jz      short loc_18000BBD9
0x18000bbb3  sub     r8d, 1
0x18000bbb7  jz      short loc_18000BBD2
0x18000bbb9  sub     r8d, 3
0x18000bbbd  jz      short loc_18000BBCB
0x18000bbbf  cmp     r8d, 1
0x18000bbc3  jnz     short loc_18000BBDE
0x18000bbc5  lea     ecx, [r8+0Fh]
0x18000bbc9  jmp     short loc_18000BBDE
0x18000bbcb  mov     ecx, 4
0x18000bbd0  jmp     short loc_18000BBDE
0x18000bbd2  mov     ecx, 8
0x18000bbd7  jmp     short loc_18000BBDE
0x18000bbd9  mov     ecx, 2
0x18000bbde  mov     edx, [rdx]
0x18000bbe0  mov     r9d, 1
0x18000bbe6  xor     eax, eax
0x18000bbe8  mov     r8d, ecx
0x18000bbeb  or      r8d, edx
0x18000bbee  cmp     r8d, edx
0x18000bbf1  mov     r11d, r8d
0x18000bbf4  setz    al
0x18000bbf7  or      r11d, r9d
0x18000bbfa  cmp     r8d, edx
0x18000bbfd  mov     [rbx+10h], eax
0x18000bc00  mov     eax, edx
0x18000bc02  cmovz   r11d, r8d
0x18000bc06  lock cmpxchg [r10], r11d
0x18000bc0b  jz      short loc_18000BC11
0x18000bc0d  mov     edx, eax
0x18000bc0f  jmp     short loc_18000BBE6
0x18000bc11  test    r9b, r11b
0x18000bc14  jz      short loc_18000BC1B
0x18000bc16  test    r9b, dl
0x18000bc19  jz      short loc_18000BC1E
0x18000bc1b  xor     r9d, r9d
0x18000bc1e  mov     [rbx], r9d
0x18000bc21  jmp     short loc_18000BC41
0x18000bc23  mov     r9, rbx
0x18000bc26  mov     edx, r8d
0x18000bc29  mov     rcx, r10
0x18000bc2c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000bc31  jmp     short loc_18000BC41
0x18000bc33  mov     r9, rbx
0x18000bc36  mov     edx, r8d
0x18000bc39  mov     rcx, r10
0x18000bc3c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000bc41  mov     rax, rbx
0x18000bc44  mov     rbx, [rsp+28h+arg_0]
0x18000bc49  add     rsp, 20h
0x18000bc4d  pop     rdi
0x18000bc4e  retn
```
