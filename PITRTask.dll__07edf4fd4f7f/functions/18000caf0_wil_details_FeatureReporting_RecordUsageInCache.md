# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000caf0`
- end: `0x18000cdca`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800089dc`

## callees

- `0x18000caf0`

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
0x18000caf0  push    rbx
0x18000caf2  push    rbp
0x18000caf3  push    rsi
0x18000caf4  push    rdi
0x18000caf5  xor     eax, eax
0x18000caf7  xorps   xmm0, xmm0
0x18000cafa  mov     r11d, r8d
0x18000cafd  mov     rsi, rdx
0x18000cb00  mov     r10, rcx
0x18000cb03  mov     r9d, r8d
0x18000cb06  movups  xmmword ptr [rcx], xmm0
0x18000cb09  mov     [rcx+10h], rax
0x18000cb0d  test    r8d, r8d
0x18000cb10  jz      loc_18000CCF4
0x18000cb16  sub     r9d, 1
0x18000cb1a  jz      loc_18000CC3B
0x18000cb20  sub     r9d, 1
0x18000cb24  jz      loc_18000CBC2
0x18000cb2a  sub     r9d, 1
0x18000cb2e  jz      loc_18000CBC2
0x18000cb34  sub     r9d, 1
0x18000cb38  jz      loc_18000CCF4
0x18000cb3e  sub     r9d, 1
0x18000cb42  jz      loc_18000CC3B
0x18000cb48  sub     r9d, 1
0x18000cb4c  jz      short loc_18000CBC2
0x18000cb4e  cmp     r9d, 1
0x18000cb52  jz      short loc_18000CBC2
0x18000cb54  add     r8d, 0FFFFFEC0h
0x18000cb5b  lea     ebx, [rax+1]
0x18000cb5e  cmp     r8d, 40h ; '@'
0x18000cb62  jge     short loc_18000CBAD
0x18000cb64  mov     eax, [rdx+4]
0x18000cb67  lea     ecx, [rbx+0Fh]
0x18000cb6a  mov     r9d, r8d
0x18000cb6d  shl     r9d, 5
0x18000cb71  test    cl, al
0x18000cb73  jz      short loc_18000CB86
0x18000cb75  mov     edx, eax
0x18000cb77  shr     edx, 5
0x18000cb7a  and     edx, 3Fh
0x18000cb7d  cmp     edx, r8d
0x18000cb80  jnz     short loc_18000CB86
0x18000cb82  mov     edx, ebx
0x18000cb84  jmp     short loc_18000CB88
0x18000cb86  xor     edx, edx
0x18000cb88  mov     [r10+10h], edx
0x18000cb8c  mov     edx, r9d
0x18000cb8f  xor     edx, eax
0x18000cb91  and     edx, 7E0h
0x18000cb97  xor     edx, eax
0x18000cb99  or      edx, ecx
0x18000cb9b  lock cmpxchg [rsi+4], edx
0x18000cba0  jnz     short loc_18000CB71
0x18000cba2  cmp     dword ptr [r10+10h], 0
0x18000cba7  jnz     loc_18000CDC2
0x18000cbad  mov     [r10+8], r11d
0x18000cbb1  mov     [r10+4], ebx
0x18000cbb5  mov     dword ptr [r10+0Ch], 0
0x18000cbbd  jmp     loc_18000CDC2
0x18000cbc2  xor     ecx, ecx
0x18000cbc4  sub     r11d, 2
0x18000cbc8  jz      short loc_18000CBF0
0x18000cbca  sub     r11d, 1
0x18000cbce  jz      short loc_18000CBE9
0x18000cbd0  sub     r11d, 3
0x18000cbd4  jz      short loc_18000CBE2
0x18000cbd6  cmp     r11d, 1
0x18000cbda  jnz     short loc_18000CBF5
0x18000cbdc  lea     ecx, [r11+0Fh]
0x18000cbe0  jmp     short loc_18000CBF5
0x18000cbe2  mov     ecx, 4
0x18000cbe7  jmp     short loc_18000CBF5
0x18000cbe9  mov     ecx, 8
0x18000cbee  jmp     short loc_18000CBF5
0x18000cbf0  mov     ecx, 2
0x18000cbf5  mov     edx, [rdx]
0x18000cbf7  mov     ebx, 1
0x18000cbfc  xor     eax, eax
0x18000cbfe  mov     r8d, ecx
0x18000cc01  or      r8d, edx
0x18000cc04  cmp     r8d, edx
0x18000cc07  mov     r9d, r8d
0x18000cc0a  setz    al
0x18000cc0d  or      r9d, ebx
0x18000cc10  cmp     r8d, edx
0x18000cc13  mov     [r10+10h], eax
0x18000cc17  mov     eax, edx
0x18000cc19  cmovz   r9d, r8d
0x18000cc1d  lock cmpxchg [rsi], r9d
0x18000cc22  jz      short loc_18000CC28
0x18000cc24  mov     edx, eax
0x18000cc26  jmp     short loc_18000CBFC
0x18000cc28  test    bl, r9b
0x18000cc2b  jz      short loc_18000CC31
0x18000cc2d  test    bl, dl
0x18000cc2f  jz      short loc_18000CC33
0x18000cc31  xor     ebx, ebx
0x18000cc33  mov     [r10], ebx
0x18000cc36  jmp     loc_18000CDC2
0x18000cc3b  mov     ecx, [rdx]
0x18000cc3d  xor     r9d, r9d
0x18000cc40  cmp     r11d, 5
0x18000cc44  mov     ebx, 1
0x18000cc49  setz    r9b
0x18000cc4d  mov     eax, ecx
0x18000cc4f  mov     dword ptr [r10+4], 0
0x18000cc57  or      eax, ebx
0x18000cc59  mov     edx, eax
0x18000cc5b  shr     edx, 16h
0x18000cc5e  and     edx, ebx
0x18000cc60  cmp     edx, r9d
0x18000cc63  jz      short loc_18000CCA5
0x18000cc65  mov     r8d, eax
0x18000cc68  shr     r8d, 0Fh
0x18000cc6c  and     r8d, 7Fh
0x18000cc70  jbe     short loc_18000CC8A
0x18000cc72  cmp     r11d, ebx
0x18000cc75  mov     [r10+4], r8d
0x18000cc79  mov     edx, 5
0x18000cc7e  cmovnz  edx, ebx
0x18000cc81  and     eax, 0FFC07FFFh
0x18000cc86  mov     [r10+8], edx
0x18000cc8a  xor     r8d, r8d
0x18000cc8d  mov     edx, 400000h
0x18000cc92  cmp     r11d, 5
0x18000cc96  cmovz   r8d, edx
0x18000cc9a  mov     edx, eax
0x18000cc9c  btr     edx, 16h
0x18000cca0  mov     eax, r8d
0x18000cca3  or      eax, edx
0x18000cca5  mov     edx, eax
0x18000cca7  shr     edx, 0Fh
0x18000ccaa  and     edx, 7Fh
0x18000ccad  lea     r8d, [rdx+1]
0x18000ccb1  cmp     r8d, 7Fh
0x18000ccb5  ja      short loc_18000CCBC
0x18000ccb7  cmp     r8d, edx
0x18000ccba  jnb     short loc_18000CCC7
0x18000ccbc  mov     r8d, ebx
0x18000ccbf  mov     [r10+8], r11d
0x18000ccc3  mov     [r10+4], edx
0x18000ccc7  shl     r8d, 0Fh
0x18000cccb  xor     r8d, eax
0x18000ccce  and     r8d, 3F8000h
0x18000ccd5  xor     r8d, eax
0x18000ccd8  mov     eax, ecx
0x18000ccda  lock cmpxchg [rsi], r8d
0x18000ccdf  jz      short loc_18000CCE8
0x18000cce1  mov     ecx, eax
0x18000cce3  jmp     loc_18000CC4D
0x18000cce8  not     ecx
0x18000ccea  and     ecx, ebx
0x18000ccec  mov     [r10], ecx
0x18000ccef  jmp     loc_18000CDBA
0x18000ccf4  mov     edx, [rdx]
0x18000ccf6  xor     ebp, ebp
0x18000ccf8  lea     ecx, [rbp+4]
0x18000ccfb  cmp     r11d, ecx
0x18000ccfe  lea     ebx, [rcx-3]
0x18000cd01  setz    bpl
0x18000cd05  mov     eax, edx
0x18000cd07  mov     dword ptr [r10+4], 0
0x18000cd0f  or      eax, ebx
0x18000cd11  mov     r8d, eax
0x18000cd14  shr     r8d, 0Eh
0x18000cd18  and     r8d, ebx
0x18000cd1b  cmp     r8d, ebp
0x18000cd1e  jz      short loc_18000CD67
0x18000cd20  mov     edi, eax
0x18000cd22  shr     edi, 5
0x18000cd25  and     edi, 1FFh
0x18000cd2b  jbe     short loc_18000CD49
0x18000cd2d  mov     r8d, r11d
0x18000cd30  mov     [r10+4], edi
0x18000cd34  neg     r8d
0x18000cd37  sbb     r9d, r9d
0x18000cd3a  not     r9d
0x18000cd3d  and     r9d, ecx
0x18000cd40  mov     [r10+8], r9d
0x18000cd44  and     eax, 0FFFFC01Fh
0x18000cd49  xor     r9d, r9d
0x18000cd4c  mov     r8d, 4000h
0x18000cd52  cmp     r11d, ecx
0x18000cd55  cmovz   r9d, r8d
0x18000cd59  mov     r8d, eax
0x18000cd5c  btr     r8d, 0Eh
0x18000cd61  mov     eax, r9d
0x18000cd64  or      eax, r8d
0x18000cd67  mov     r8d, eax
0x18000cd6a  shr     r8d, 5
0x18000cd6e  and     r8d, 1FFh
0x18000cd75  lea     r9d, [r8+1]
0x18000cd79  cmp     r9d, 1FFh
0x18000cd80  ja      short loc_18000CD87
0x18000cd82  cmp     r9d, r8d
0x18000cd85  jnb     short loc_18000CD92
0x18000cd87  mov     r9d, ebx
0x18000cd8a  mov     [r10+8], r11d
0x18000cd8e  mov     [r10+4], r8d
0x18000cd92  shl     r9d, 5
0x18000cd96  xor     r9d, eax
0x18000cd99  and     r9d, 3FE0h
0x18000cda0  xor     r9d, eax
0x18000cda3  mov     eax, edx
0x18000cda5  lock cmpxchg [rsi], r9d
0x18000cdaa  jz      short loc_18000CDB3
0x18000cdac  mov     edx, eax
0x18000cdae  jmp     loc_18000CD05
0x18000cdb3  not     edx
0x18000cdb5  and     edx, ebx
0x18000cdb7  mov     [r10], edx
0x18000cdba  mov     dword ptr [r10+10h], 0
0x18000cdc2  mov     rax, r10
0x18000cdc5  pop     rdi
0x18000cdc6  pop     rsi
0x18000cdc7  pop     rbp
0x18000cdc8  pop     rbx
0x18000cdc9  retn
```
