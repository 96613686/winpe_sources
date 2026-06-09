# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180009740`
- end: `0x180009a1a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007a1c`

## callees

- `0x180009740`

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
0x180009740  push    rbx
0x180009742  push    rbp
0x180009743  push    rsi
0x180009744  push    rdi
0x180009745  xor     eax, eax
0x180009747  xorps   xmm0, xmm0
0x18000974a  mov     r11d, r8d
0x18000974d  mov     rsi, rdx
0x180009750  mov     r10, rcx
0x180009753  mov     r9d, r8d
0x180009756  movups  xmmword ptr [rcx], xmm0
0x180009759  mov     [rcx+10h], rax
0x18000975d  test    r8d, r8d
0x180009760  jz      loc_180009944
0x180009766  sub     r9d, 1
0x18000976a  jz      loc_18000988B
0x180009770  sub     r9d, 1
0x180009774  jz      loc_180009812
0x18000977a  sub     r9d, 1
0x18000977e  jz      loc_180009812
0x180009784  sub     r9d, 1
0x180009788  jz      loc_180009944
0x18000978e  sub     r9d, 1
0x180009792  jz      loc_18000988B
0x180009798  sub     r9d, 1
0x18000979c  jz      short loc_180009812
0x18000979e  cmp     r9d, 1
0x1800097a2  jz      short loc_180009812
0x1800097a4  add     r8d, 0FFFFFEC0h
0x1800097ab  lea     ebx, [rax+1]
0x1800097ae  cmp     r8d, 40h ; '@'
0x1800097b2  jge     short loc_1800097FD
0x1800097b4  mov     eax, [rdx+4]
0x1800097b7  lea     ecx, [rbx+0Fh]
0x1800097ba  mov     r9d, r8d
0x1800097bd  shl     r9d, 5
0x1800097c1  test    cl, al
0x1800097c3  jz      short loc_1800097D6
0x1800097c5  mov     edx, eax
0x1800097c7  shr     edx, 5
0x1800097ca  and     edx, 3Fh
0x1800097cd  cmp     edx, r8d
0x1800097d0  jnz     short loc_1800097D6
0x1800097d2  mov     edx, ebx
0x1800097d4  jmp     short loc_1800097D8
0x1800097d6  xor     edx, edx
0x1800097d8  mov     [r10+10h], edx
0x1800097dc  mov     edx, r9d
0x1800097df  xor     edx, eax
0x1800097e1  and     edx, 7E0h
0x1800097e7  xor     edx, eax
0x1800097e9  or      edx, ecx
0x1800097eb  lock cmpxchg [rsi+4], edx
0x1800097f0  jnz     short loc_1800097C1
0x1800097f2  cmp     dword ptr [r10+10h], 0
0x1800097f7  jnz     loc_180009A12
0x1800097fd  mov     [r10+8], r11d
0x180009801  mov     [r10+4], ebx
0x180009805  mov     dword ptr [r10+0Ch], 0
0x18000980d  jmp     loc_180009A12
0x180009812  xor     ecx, ecx
0x180009814  sub     r11d, 2
0x180009818  jz      short loc_180009840
0x18000981a  sub     r11d, 1
0x18000981e  jz      short loc_180009839
0x180009820  sub     r11d, 3
0x180009824  jz      short loc_180009832
0x180009826  cmp     r11d, 1
0x18000982a  jnz     short loc_180009845
0x18000982c  lea     ecx, [r11+0Fh]
0x180009830  jmp     short loc_180009845
0x180009832  mov     ecx, 4
0x180009837  jmp     short loc_180009845
0x180009839  mov     ecx, 8
0x18000983e  jmp     short loc_180009845
0x180009840  mov     ecx, 2
0x180009845  mov     edx, [rdx]
0x180009847  mov     ebx, 1
0x18000984c  xor     eax, eax
0x18000984e  mov     r8d, ecx
0x180009851  or      r8d, edx
0x180009854  cmp     r8d, edx
0x180009857  mov     r9d, r8d
0x18000985a  setz    al
0x18000985d  or      r9d, ebx
0x180009860  cmp     r8d, edx
0x180009863  mov     [r10+10h], eax
0x180009867  mov     eax, edx
0x180009869  cmovz   r9d, r8d
0x18000986d  lock cmpxchg [rsi], r9d
0x180009872  jz      short loc_180009878
0x180009874  mov     edx, eax
0x180009876  jmp     short loc_18000984C
0x180009878  test    bl, r9b
0x18000987b  jz      short loc_180009881
0x18000987d  test    bl, dl
0x18000987f  jz      short loc_180009883
0x180009881  xor     ebx, ebx
0x180009883  mov     [r10], ebx
0x180009886  jmp     loc_180009A12
0x18000988b  mov     ecx, [rdx]
0x18000988d  xor     r9d, r9d
0x180009890  cmp     r11d, 5
0x180009894  mov     ebx, 1
0x180009899  setz    r9b
0x18000989d  mov     eax, ecx
0x18000989f  mov     dword ptr [r10+4], 0
0x1800098a7  or      eax, ebx
0x1800098a9  mov     edx, eax
0x1800098ab  shr     edx, 16h
0x1800098ae  and     edx, ebx
0x1800098b0  cmp     edx, r9d
0x1800098b3  jz      short loc_1800098F5
0x1800098b5  mov     r8d, eax
0x1800098b8  shr     r8d, 0Fh
0x1800098bc  and     r8d, 7Fh
0x1800098c0  jbe     short loc_1800098DA
0x1800098c2  cmp     r11d, ebx
0x1800098c5  mov     [r10+4], r8d
0x1800098c9  mov     edx, 5
0x1800098ce  cmovnz  edx, ebx
0x1800098d1  and     eax, 0FFC07FFFh
0x1800098d6  mov     [r10+8], edx
0x1800098da  xor     r8d, r8d
0x1800098dd  mov     edx, 400000h
0x1800098e2  cmp     r11d, 5
0x1800098e6  cmovz   r8d, edx
0x1800098ea  mov     edx, eax
0x1800098ec  btr     edx, 16h
0x1800098f0  mov     eax, r8d
0x1800098f3  or      eax, edx
0x1800098f5  mov     edx, eax
0x1800098f7  shr     edx, 0Fh
0x1800098fa  and     edx, 7Fh
0x1800098fd  lea     r8d, [rdx+1]
0x180009901  cmp     r8d, 7Fh
0x180009905  ja      short loc_18000990C
0x180009907  cmp     r8d, edx
0x18000990a  jnb     short loc_180009917
0x18000990c  mov     r8d, ebx
0x18000990f  mov     [r10+8], r11d
0x180009913  mov     [r10+4], edx
0x180009917  shl     r8d, 0Fh
0x18000991b  xor     r8d, eax
0x18000991e  and     r8d, 3F8000h
0x180009925  xor     r8d, eax
0x180009928  mov     eax, ecx
0x18000992a  lock cmpxchg [rsi], r8d
0x18000992f  jz      short loc_180009938
0x180009931  mov     ecx, eax
0x180009933  jmp     loc_18000989D
0x180009938  not     ecx
0x18000993a  and     ecx, ebx
0x18000993c  mov     [r10], ecx
0x18000993f  jmp     loc_180009A0A
0x180009944  mov     edx, [rdx]
0x180009946  xor     ebp, ebp
0x180009948  lea     ecx, [rbp+4]
0x18000994b  cmp     r11d, ecx
0x18000994e  lea     ebx, [rcx-3]
0x180009951  setz    bpl
0x180009955  mov     eax, edx
0x180009957  mov     dword ptr [r10+4], 0
0x18000995f  or      eax, ebx
0x180009961  mov     r8d, eax
0x180009964  shr     r8d, 0Eh
0x180009968  and     r8d, ebx
0x18000996b  cmp     r8d, ebp
0x18000996e  jz      short loc_1800099B7
0x180009970  mov     edi, eax
0x180009972  shr     edi, 5
0x180009975  and     edi, 1FFh
0x18000997b  jbe     short loc_180009999
0x18000997d  mov     r8d, r11d
0x180009980  mov     [r10+4], edi
0x180009984  neg     r8d
0x180009987  sbb     r9d, r9d
0x18000998a  not     r9d
0x18000998d  and     r9d, ecx
0x180009990  mov     [r10+8], r9d
0x180009994  and     eax, 0FFFFC01Fh
0x180009999  xor     r9d, r9d
0x18000999c  mov     r8d, 4000h
0x1800099a2  cmp     r11d, ecx
0x1800099a5  cmovz   r9d, r8d
0x1800099a9  mov     r8d, eax
0x1800099ac  btr     r8d, 0Eh
0x1800099b1  mov     eax, r9d
0x1800099b4  or      eax, r8d
0x1800099b7  mov     r8d, eax
0x1800099ba  shr     r8d, 5
0x1800099be  and     r8d, 1FFh
0x1800099c5  lea     r9d, [r8+1]
0x1800099c9  cmp     r9d, 1FFh
0x1800099d0  ja      short loc_1800099D7
0x1800099d2  cmp     r9d, r8d
0x1800099d5  jnb     short loc_1800099E2
0x1800099d7  mov     r9d, ebx
0x1800099da  mov     [r10+8], r11d
0x1800099de  mov     [r10+4], r8d
0x1800099e2  shl     r9d, 5
0x1800099e6  xor     r9d, eax
0x1800099e9  and     r9d, 3FE0h
0x1800099f0  xor     r9d, eax
0x1800099f3  mov     eax, edx
0x1800099f5  lock cmpxchg [rsi], r9d
0x1800099fa  jz      short loc_180009A03
0x1800099fc  mov     edx, eax
0x1800099fe  jmp     loc_180009955
0x180009a03  not     edx
0x180009a05  and     edx, ebx
0x180009a07  mov     [r10], edx
0x180009a0a  mov     dword ptr [r10+10h], 0
0x180009a12  mov     rax, r10
0x180009a15  pop     rdi
0x180009a16  pop     rsi
0x180009a17  pop     rbp
0x180009a18  pop     rbx
0x180009a19  retn
```
