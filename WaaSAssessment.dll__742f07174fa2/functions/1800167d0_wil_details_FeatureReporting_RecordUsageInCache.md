# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800167d0`
- end: `0x180016aaa`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015674`

## callees

- `0x1800167d0`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // r8d
  unsigned __int32 v7; // eax
  BOOL v8; // edx
  unsigned __int32 v9; // ett
  int v10; // ecx
  signed __int32 v11; // edx
  int v12; // ebx
  signed __int32 v13; // r9d
  signed __int32 v14; // eax
  signed __int32 v15; // ecx
  BOOL v16; // r9d
  unsigned int v17; // eax
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // edx
  unsigned int v21; // r8d
  signed __int32 v22; // eax
  signed __int32 v23; // edx
  BOOL v24; // ebp
  unsigned int v25; // eax
  int v26; // r9d
  unsigned int v27; // r8d
  unsigned int v28; // r9d
  signed __int32 v29; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_49:
      v23 = *a2;
      v24 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v25 = v23 | 1;
        if ( (((v23 | 1u) >> 14) & 1) != v24 )
        {
          if ( ((v25 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v25 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v25 = v23 & 0xFFFFC01E | 1;
          }
          v26 = 0;
          if ( a3 == 4 )
            v26 = 0x4000;
          v25 = v25 & 0xFFFFBFFF | v26;
        }
        v27 = (v25 >> 5) & 0x1FF;
        v28 = v27 + 1;
        if ( v27 + 1 > 0x1FF || v28 < v27 )
        {
          LOWORD(v28) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v27;
        }
        v29 = _InterlockedCompareExchange(
                a2,
                v25 ^ ((unsigned __int16)v25 ^ (unsigned __int16)(32 * v28)) & 0x3FE0,
                v23);
        if ( v23 == v29 )
          break;
        v23 = v29;
      }
      *(_DWORD *)a1 = (v23 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v15 = *a2;
      v16 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v17 = v15 | 1;
        if ( (((v15 | 1u) >> 22) & 1) != v16 )
        {
          if ( ((v17 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v17 >> 15) & 0x7F;
            v18 = 5;
            if ( a3 != 1 )
              v18 = 1;
            v17 = v15 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v18;
          }
          v19 = 0;
          if ( a3 == 5 )
            v19 = 0x400000;
          v17 = v17 & 0xFFBFFFFF | v19;
        }
        v20 = (v17 >> 15) & 0x7F;
        v21 = v20 + 1;
        if ( v20 + 1 > 0x7F || v21 < v20 )
        {
          v21 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v20;
        }
        v22 = _InterlockedCompareExchange(a2, v17 ^ (v17 ^ (v21 << 15)) & 0x3F8000, v15);
        if ( v15 == v22 )
          break;
        v15 = v22;
      }
      *(_DWORD *)a1 = (v15 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v6 = a3 - 320;
    if ( v6 >= 64 )
      goto LABEL_16;
    v7 = *((_DWORD *)a2 + 1);
    do
    {
      v8 = (v7 & 0x10) != 0 && ((v7 >> 5) & 0x3F) == v6;
      *(_DWORD *)(a1 + 16) = v8;
      v9 = v7;
      v7 = _InterlockedCompareExchange(
             a2 + 1,
             v7 ^ ((unsigned __int16)v7 ^ (unsigned __int16)(32 * v6)) & 0x7E0 | 0x10,
             v7);
    }
    while ( v9 != v7 );
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
  v10 = 0;
  switch ( a3 )
  {
    case 2:
      v10 = 2;
      break;
    case 3:
      v10 = 8;
      break;
    case 6:
      v10 = 4;
      break;
    case 7:
      v10 = 16;
      break;
  }
  v11 = *a2;
  v12 = 1;
  while ( 1 )
  {
    v13 = v11 | v10 | 1;
    *(_DWORD *)(a1 + 16) = (v11 | v10) == v11;
    if ( (v11 | v10) == v11 )
      v13 = v11 | v10;
    v14 = _InterlockedCompareExchange(a2, v13, v11);
    if ( v11 == v14 )
      break;
    v11 = v14;
  }
  if ( (v13 & 1) == 0 || (v11 & 1) != 0 )
    v12 = 0;
  *(_DWORD *)a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x1800167d0  push    rbx
0x1800167d2  push    rbp
0x1800167d3  push    rsi
0x1800167d4  push    rdi
0x1800167d5  xor     eax, eax
0x1800167d7  xorps   xmm0, xmm0
0x1800167da  mov     r11d, r8d
0x1800167dd  mov     rsi, rdx
0x1800167e0  mov     r10, rcx
0x1800167e3  mov     r9d, r8d
0x1800167e6  movups  xmmword ptr [rcx], xmm0
0x1800167e9  mov     [rcx+10h], rax
0x1800167ed  test    r8d, r8d
0x1800167f0  jz      loc_1800169D4
0x1800167f6  sub     r9d, 1
0x1800167fa  jz      loc_18001691B
0x180016800  sub     r9d, 1
0x180016804  jz      loc_1800168A2
0x18001680a  sub     r9d, 1
0x18001680e  jz      loc_1800168A2
0x180016814  sub     r9d, 1
0x180016818  jz      loc_1800169D4
0x18001681e  sub     r9d, 1
0x180016822  jz      loc_18001691B
0x180016828  sub     r9d, 1
0x18001682c  jz      short loc_1800168A2
0x18001682e  cmp     r9d, 1
0x180016832  jz      short loc_1800168A2
0x180016834  add     r8d, 0FFFFFEC0h
0x18001683b  lea     ebx, [rax+1]
0x18001683e  cmp     r8d, 40h ; '@'
0x180016842  jge     short loc_18001688D
0x180016844  mov     eax, [rdx+4]
0x180016847  lea     ecx, [rbx+0Fh]
0x18001684a  mov     r9d, r8d
0x18001684d  shl     r9d, 5
0x180016851  test    cl, al
0x180016853  jz      short loc_180016866
0x180016855  mov     edx, eax
0x180016857  shr     edx, 5
0x18001685a  and     edx, 3Fh
0x18001685d  cmp     edx, r8d
0x180016860  jnz     short loc_180016866
0x180016862  mov     edx, ebx
0x180016864  jmp     short loc_180016868
0x180016866  xor     edx, edx
0x180016868  mov     [r10+10h], edx
0x18001686c  mov     edx, r9d
0x18001686f  xor     edx, eax
0x180016871  and     edx, 7E0h
0x180016877  xor     edx, eax
0x180016879  or      edx, ecx
0x18001687b  lock cmpxchg [rsi+4], edx
0x180016880  jnz     short loc_180016851
0x180016882  cmp     dword ptr [r10+10h], 0
0x180016887  jnz     loc_180016AA2
0x18001688d  mov     [r10+8], r11d
0x180016891  mov     [r10+4], ebx
0x180016895  mov     dword ptr [r10+0Ch], 0
0x18001689d  jmp     loc_180016AA2
0x1800168a2  xor     ecx, ecx
0x1800168a4  sub     r11d, 2
0x1800168a8  jz      short loc_1800168D0
0x1800168aa  sub     r11d, 1
0x1800168ae  jz      short loc_1800168C9
0x1800168b0  sub     r11d, 3
0x1800168b4  jz      short loc_1800168C2
0x1800168b6  cmp     r11d, 1
0x1800168ba  jnz     short loc_1800168D5
0x1800168bc  lea     ecx, [r11+0Fh]
0x1800168c0  jmp     short loc_1800168D5
0x1800168c2  mov     ecx, 4
0x1800168c7  jmp     short loc_1800168D5
0x1800168c9  mov     ecx, 8
0x1800168ce  jmp     short loc_1800168D5
0x1800168d0  mov     ecx, 2
0x1800168d5  mov     edx, [rdx]
0x1800168d7  mov     ebx, 1
0x1800168dc  xor     eax, eax
0x1800168de  mov     r8d, ecx
0x1800168e1  or      r8d, edx
0x1800168e4  cmp     r8d, edx
0x1800168e7  mov     r9d, r8d
0x1800168ea  setz    al
0x1800168ed  or      r9d, ebx
0x1800168f0  cmp     r8d, edx
0x1800168f3  mov     [r10+10h], eax
0x1800168f7  mov     eax, edx
0x1800168f9  cmovz   r9d, r8d
0x1800168fd  lock cmpxchg [rsi], r9d
0x180016902  jz      short loc_180016908
0x180016904  mov     edx, eax
0x180016906  jmp     short loc_1800168DC
0x180016908  test    bl, r9b
0x18001690b  jz      short loc_180016911
0x18001690d  test    bl, dl
0x18001690f  jz      short loc_180016913
0x180016911  xor     ebx, ebx
0x180016913  mov     [r10], ebx
0x180016916  jmp     loc_180016AA2
0x18001691b  mov     ecx, [rdx]
0x18001691d  xor     r9d, r9d
0x180016920  cmp     r11d, 5
0x180016924  mov     ebx, 1
0x180016929  setz    r9b
0x18001692d  mov     eax, ecx
0x18001692f  mov     dword ptr [r10+4], 0
0x180016937  or      eax, ebx
0x180016939  mov     edx, eax
0x18001693b  shr     edx, 16h
0x18001693e  and     edx, ebx
0x180016940  cmp     edx, r9d
0x180016943  jz      short loc_180016985
0x180016945  mov     r8d, eax
0x180016948  shr     r8d, 0Fh
0x18001694c  and     r8d, 7Fh
0x180016950  jbe     short loc_18001696A
0x180016952  cmp     r11d, ebx
0x180016955  mov     [r10+4], r8d
0x180016959  mov     edx, 5
0x18001695e  cmovnz  edx, ebx
0x180016961  and     eax, 0FFC07FFFh
0x180016966  mov     [r10+8], edx
0x18001696a  xor     r8d, r8d
0x18001696d  mov     edx, 400000h
0x180016972  cmp     r11d, 5
0x180016976  cmovz   r8d, edx
0x18001697a  mov     edx, eax
0x18001697c  btr     edx, 16h
0x180016980  mov     eax, r8d
0x180016983  or      eax, edx
0x180016985  mov     edx, eax
0x180016987  shr     edx, 0Fh
0x18001698a  and     edx, 7Fh
0x18001698d  lea     r8d, [rdx+1]
0x180016991  cmp     r8d, 7Fh
0x180016995  ja      short loc_18001699C
0x180016997  cmp     r8d, edx
0x18001699a  jnb     short loc_1800169A7
0x18001699c  mov     r8d, ebx
0x18001699f  mov     [r10+8], r11d
0x1800169a3  mov     [r10+4], edx
0x1800169a7  shl     r8d, 0Fh
0x1800169ab  xor     r8d, eax
0x1800169ae  and     r8d, 3F8000h
0x1800169b5  xor     r8d, eax
0x1800169b8  mov     eax, ecx
0x1800169ba  lock cmpxchg [rsi], r8d
0x1800169bf  jz      short loc_1800169C8
0x1800169c1  mov     ecx, eax
0x1800169c3  jmp     loc_18001692D
0x1800169c8  not     ecx
0x1800169ca  and     ecx, ebx
0x1800169cc  mov     [r10], ecx
0x1800169cf  jmp     loc_180016A9A
0x1800169d4  mov     edx, [rdx]
0x1800169d6  xor     ebp, ebp
0x1800169d8  lea     ecx, [rbp+4]
0x1800169db  cmp     r11d, ecx
0x1800169de  lea     ebx, [rcx-3]
0x1800169e1  setz    bpl
0x1800169e5  mov     eax, edx
0x1800169e7  mov     dword ptr [r10+4], 0
0x1800169ef  or      eax, ebx
0x1800169f1  mov     r8d, eax
0x1800169f4  shr     r8d, 0Eh
0x1800169f8  and     r8d, ebx
0x1800169fb  cmp     r8d, ebp
0x1800169fe  jz      short loc_180016A47
0x180016a00  mov     edi, eax
0x180016a02  shr     edi, 5
0x180016a05  and     edi, 1FFh
0x180016a0b  jbe     short loc_180016A29
0x180016a0d  mov     r8d, r11d
0x180016a10  mov     [r10+4], edi
0x180016a14  neg     r8d
0x180016a17  sbb     r9d, r9d
0x180016a1a  not     r9d
0x180016a1d  and     r9d, ecx
0x180016a20  mov     [r10+8], r9d
0x180016a24  and     eax, 0FFFFC01Fh
0x180016a29  xor     r9d, r9d
0x180016a2c  mov     r8d, 4000h
0x180016a32  cmp     r11d, ecx
0x180016a35  cmovz   r9d, r8d
0x180016a39  mov     r8d, eax
0x180016a3c  btr     r8d, 0Eh
0x180016a41  mov     eax, r9d
0x180016a44  or      eax, r8d
0x180016a47  mov     r8d, eax
0x180016a4a  shr     r8d, 5
0x180016a4e  and     r8d, 1FFh
0x180016a55  lea     r9d, [r8+1]
0x180016a59  cmp     r9d, 1FFh
0x180016a60  ja      short loc_180016A67
0x180016a62  cmp     r9d, r8d
0x180016a65  jnb     short loc_180016A72
0x180016a67  mov     r9d, ebx
0x180016a6a  mov     [r10+8], r11d
0x180016a6e  mov     [r10+4], r8d
0x180016a72  shl     r9d, 5
0x180016a76  xor     r9d, eax
0x180016a79  and     r9d, 3FE0h
0x180016a80  xor     r9d, eax
0x180016a83  mov     eax, edx
0x180016a85  lock cmpxchg [rsi], r9d
0x180016a8a  jz      short loc_180016A93
0x180016a8c  mov     edx, eax
0x180016a8e  jmp     loc_1800169E5
0x180016a93  not     edx
0x180016a95  and     edx, ebx
0x180016a97  mov     [r10], edx
0x180016a9a  mov     dword ptr [r10+10h], 0
0x180016aa2  mov     rax, r10
0x180016aa5  pop     rdi
0x180016aa6  pop     rsi
0x180016aa7  pop     rbp
0x180016aa8  pop     rbx
0x180016aa9  retn
```
