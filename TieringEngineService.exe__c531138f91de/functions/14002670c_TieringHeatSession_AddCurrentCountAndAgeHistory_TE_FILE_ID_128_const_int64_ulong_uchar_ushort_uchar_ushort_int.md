# TieringHeatSession::AddCurrentCountAndAgeHistory(TE_FILE_ID_128 const *,__int64,ulong,uchar,ushort,uchar,ushort *,int *,ulong *,ulong *)

- ea: `0x14002670c`
- end: `0x140026e8a`
- name: `?AddCurrentCountAndAgeHistory@TieringHeatSession@@QEAAXPEBUTE_FILE_ID_128@@_JKEGEPEAGPEAHPEAK4@Z`
- size: `1918`
- prototype: `void __fastcall(TieringHeatSession *this, const struct TE_FILE_ID_128 *, __int64, unsigned int, unsigned __int8, unsigned __int16, unsigned __int8, unsigned __int16 *, int *, unsigned int *, unsigned int *)`
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140026e90`
- `0x140028848`
- `0x140029268`
- `0x140029b44`
- `0x14002ac14`
- `0x140030e10`
- `0x140031e04`

## callees

- `0x140004a68`
- `0x140009f1c`
- `0x1400261c8`
- `0x14002670c`
- `0x14002b7d0`
- `0x14002b868`
- `0x14002b908`

## pseudocode

```c
void __fastcall TieringHeatSession::AddCurrentCountAndAgeHistory(
        TieringHeatSession *this,
        const struct TE_FILE_ID_128 *a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 a5,
        unsigned __int16 a6,
        unsigned __int8 a7,
        unsigned __int16 *a8,
        int *a9,
        unsigned int *a10,
        unsigned int *a11)
{
  TieringHeatSession *v13; // rdi
  unsigned int v14; // r14d
  _QWORD *v15; // rbx
  unsigned int v16; // ebp
  int v17; // ebp
  int v18; // eax
  unsigned __int16 *v19; // rdi
  __int64 i; // rcx
  unsigned int *v21; // r15
  unsigned int *v22; // r12
  _QWORD *v23; // rbx
  unsigned int v24; // ebp
  unsigned int v25; // r13d
  unsigned int v26; // r15d
  int k; // r14d
  __int64 v28; // r8
  unsigned int v29; // r10d
  unsigned int j; // r9d
  unsigned int v31; // r8d
  unsigned int v32; // eax
  unsigned int v33; // ecx
  int v34; // eax
  int v35; // edi
  unsigned int v36; // ecx
  __int64 v37; // rdx
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // edi
  __int64 v41; // r9
  __int64 v43; // [rsp+B0h] [rbp+18h]

  v43 = a3;
  v13 = this;
  v14 = (*(_BYTE *)(**((_QWORD **)this + 5) + 328LL) - a5) & 0x7F;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, a3, *((_QWORD *)a2 + 1), *(_QWORD *)a2);
      a3 = v43;
      v15 = WPP_GLOBAL_Control;
    }
    if ( v15 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
      {
        WPP_SF_q(v15[2], 33, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, a3);
        v15 = WPP_GLOBAL_Control;
      }
      if ( v15 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
        {
          WPP_SF_d(v15[2], 34, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, a4);
          v15 = WPP_GLOBAL_Control;
        }
        if ( v15 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
          {
            WPP_SF_d(v15[2], 35, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, a5);
            v15 = WPP_GLOBAL_Control;
          }
          if ( v15 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
            {
              WPP_SF_d(v15[2], 36, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, a6);
              v15 = WPP_GLOBAL_Control;
            }
            if ( v15 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
              {
                WPP_SF_d(v15[2], 37, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, a7);
                v15 = WPP_GLOBAL_Control;
              }
              if ( v15 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
                {
                  WPP_SF_d(
                    v15[2],
                    38,
                    &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
                    *(unsigned __int8 *)(**((_QWORD **)v13 + 5) + 328LL));
                  v15 = WPP_GLOBAL_Control;
                }
                if ( v15 != &WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
                  {
                    WPP_SF_d(v15[2], 39, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, v14);
                    v15 = WPP_GLOBAL_Control;
                  }
                  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
                  {
                    WPP_SF_DDDDDDD(v15[2], 40, a8[3], *a8, a8[1], a8[2], a8[3], a8[4], a8[5], a8[6]);
                    v15 = WPP_GLOBAL_Control;
                    v13 = this;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v14 )
  {
    v16 = a4;
  }
  else
  {
    v17 = *a8;
    if ( (_WORD)v17 == 0xFFFF )
      v17 = 0;
    v16 = a4 + v17;
  }
  if ( v16 > 0x2D0 )
  {
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
      WPP_SF_iiiDS(
        v15[2],
        41,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        v43,
        a4,
        *(_QWORD *)(*((_QWORD *)v13 + 5) + 112LL));
    v16 = 720;
  }
  if ( v14 > 0x5F || (v18 = 0, a4) )
    v18 = 1;
  *a9 = v18;
  if ( !v14 )
    goto LABEL_60;
  if ( v14 >= 0x7F )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_iiiDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)a2 + 1),
        *(_QWORD *)a2,
        v43,
        v14,
        *(_QWORD *)(*((_QWORD *)v13 + 5) + 112LL));
    }
    v19 = a8 + 1;
    for ( i = 6; i; --i )
      *v19++ = 0;
LABEL_60:
    *a8 = v16;
    goto LABEL_61;
  }
  v29 = v14 + a5;
  for ( j = a5 + 1; j <= v29; *a8 = v33 )
  {
    v31 = 6;
    while ( a8[v31] == 0xFFFF || j % (1 << v31) )
    {
      if ( (--v31 & 0x80000000) != 0 )
      {
        v32 = 0;
        if ( j == v29 )
          v32 = v16;
        v33 = (v32 + *a8) >> 1;
        goto LABEL_74;
      }
    }
    if ( v31 < 6 )
    {
      v34 = a8[v31];
      if ( a8[v31 + 1] == 0xFFFF )
        a8[v31 + 1] = v34;
      else
        a8[v31 + 1] = ((unsigned int)a8[v31 + 1] + v34) >> 1;
    }
    while ( (--v31 & 0x80000000) == 0 )
      a8[v31 + 1] = a8[v31];
    LOWORD(v33) = 0;
    if ( j == v29 )
      LOWORD(v33) = v16;
LABEL_74:
    ++j;
  }
LABEL_61:
  v21 = a10;
  v22 = a11;
  if ( __PAIR128__((unsigned __int64)a11, (unsigned __int64)a10) == 0 )
  {
LABEL_113:
    v23 = WPP_GLOBAL_Control;
    goto LABEL_114;
  }
  v23 = WPP_GLOBAL_Control;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  for ( k = 0; k < 7; ++k )
  {
    if ( a8[k] == 0xFFFF )
      break;
    if ( k )
    {
      v28 = (unsigned int)(1 << k) >> 1;
      if ( *(unsigned __int8 *)(**((_QWORD **)this + 5) + 328LL) % (unsigned int)(1 << k) >= (unsigned int)v28 )
        v28 = (unsigned int)(1 << k);
    }
    else
    {
      v28 = 1;
    }
    v25 += v28;
    v35 = v28 * a8[k];
    v26 += v35;
    v36 = v26 / v25;
    if ( (unsigned int)k >= 6 || a8[k + 1] == 0xFFFF )
      v37 = v36;
    else
      v37 = a8[k + 1];
    if ( v36 > v24 )
    {
      v38 = (v26 / v25) >> 1;
      if ( (unsigned int)v37 >= v38 && (unsigned int)v37 <= v36 + v38 )
        v24 = v26 / v25;
    }
    if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 5u )
    {
      WPP_SF_dLLLLLLL(v23[2], v37, v28, (unsigned int)k, v28, v35, v25, v26, v36, v37, v24);
      v23 = WPP_GLOBAL_Control;
    }
  }
  v22 = a11;
  v21 = a10;
  if ( v24 > 0x2D0 )
    v24 = 720;
  if ( a11 )
  {
    *a11 = v24;
    v23 = WPP_GLOBAL_Control;
  }
  if ( a10 )
  {
    if ( (a7 & 0x20) != 0 )
    {
      if ( a6 )
      {
        v39 = *(_DWORD *)(**((_QWORD **)this + 5) + 320LL);
        if ( a6 < v39 && (!v43 || (a7 & 0x10) == 0) )
        {
          v24 *= v39 / a6;
          if ( v24 > 0x5A0 )
            v24 = 1440;
        }
      }
    }
    *a10 = v24;
    goto LABEL_113;
  }
LABEL_114:
  if ( v23 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 5u )
    {
      WPP_SF_d(v23[2], 44, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, (unsigned int)*a9);
      v23 = WPP_GLOBAL_Control;
    }
    if ( v23 != &WPP_GLOBAL_Control )
    {
      v40 = -1;
      if ( (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 5u )
      {
        if ( v21 )
          v41 = *v21;
        else
          v41 = 0xFFFFFFFFLL;
        WPP_SF_d(v23[2], 45, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, v41);
        v23 = WPP_GLOBAL_Control;
      }
      if ( v23 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 5u )
        {
          if ( v22 )
            v40 = *v22;
          WPP_SF_d(v23[2], 46, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, v40);
          v23 = WPP_GLOBAL_Control;
        }
        if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 && *((_BYTE *)v23 + 25) >= 5u )
          WPP_SF_DDDDDDD(v23[2], 47, a8[3], *a8, a8[1], a8[2], a8[3], a8[4], a8[5], a8[6]);
      }
    }
  }
}

```

## disassembly

```asm
0x14002670c  mov     r11, rsp
0x14002670f  mov     [r11+10h], rbx
0x140026713  mov     [r11+18h], r8
0x140026717  mov     [r11+8], rcx
0x14002671b  push    rbp
0x14002671c  push    rsi
0x14002671d  push    rdi
0x14002671e  push    r12
0x140026720  push    r13
0x140026722  push    r14
0x140026724  push    r15
0x140026726  sub     rsp, 60h
0x14002672a  mov     rax, [rcx+28h]
0x14002672e  mov     r15d, r9d
0x140026731  movzx   r13d, [rsp+98h+arg_20]
0x14002673a  mov     r12, rdx
0x14002673d  mov     rsi, [rsp+98h+arg_38]
0x140026745  mov     rdi, rcx
0x140026748  mov     rax, [rax]
0x14002674b  movzx   r14d, byte ptr [rax+148h]
0x140026753  sub     r14d, r13d
0x140026756  and     r14d, 7Fh
0x14002675a  mov     rbx, cs:WPP_GLOBAL_Control
0x140026761  lea     rdx, WPP_GLOBAL_Control
0x140026768  mov     bpl, 5
0x14002676b  cmp     rbx, rdx
0x14002676e  jz      loc_1400269D0
0x140026774  test    byte ptr [rbx+1Ch], 1
0x140026778  jz      short loc_1400267AC
0x14002677a  cmp     [rbx+19h], bpl
0x14002677e  jb      short loc_1400267AC
0x140026780  mov     rax, [r12]
0x140026784  mov     r9, [r12+8]
0x140026789  mov     rcx, [rbx+10h]
0x14002678d  mov     [r11-78h], rax
0x140026791  call    WPP_SF_ii
0x140026796  mov     r8, [rsp+98h+arg_10]
0x14002679e  lea     rdx, WPP_GLOBAL_Control
0x1400267a5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400267ac  cmp     rbx, rdx
0x1400267af  jz      loc_1400269D0
0x1400267b5  test    byte ptr [rbx+1Ch], 1
0x1400267b9  jz      short loc_1400267E7
0x1400267bb  cmp     [rbx+19h], bpl
0x1400267bf  jb      short loc_1400267E7
0x1400267c1  mov     rcx, [rbx+10h]
0x1400267c5  mov     r9, r8
0x1400267c8  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x1400267cf  mov     edx, 21h ; '!'
0x1400267d4  call    WPP_SF_q
0x1400267d9  mov     rbx, cs:WPP_GLOBAL_Control
0x1400267e0  lea     rdx, WPP_GLOBAL_Control
0x1400267e7  cmp     rbx, rdx
0x1400267ea  jz      loc_1400269D0
0x1400267f0  test    byte ptr [rbx+1Ch], 1
0x1400267f4  jz      short loc_140026822
0x1400267f6  cmp     [rbx+19h], bpl
0x1400267fa  jb      short loc_140026822
0x1400267fc  mov     rcx, [rbx+10h]
0x140026800  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140026807  mov     edx, 22h ; '"'
0x14002680c  mov     r9d, r15d
0x14002680f  call    WPP_SF_d
0x140026814  mov     rbx, cs:WPP_GLOBAL_Control
0x14002681b  lea     rdx, WPP_GLOBAL_Control
0x140026822  cmp     rbx, rdx
0x140026825  jz      loc_1400269D0
0x14002682b  test    byte ptr [rbx+1Ch], 1
0x14002682f  jz      short loc_14002685D
0x140026831  cmp     [rbx+19h], bpl
0x140026835  jb      short loc_14002685D
0x140026837  mov     rcx, [rbx+10h]
0x14002683b  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140026842  mov     edx, 23h ; '#'
0x140026847  mov     r9d, r13d
0x14002684a  call    WPP_SF_d
0x14002684f  mov     rbx, cs:WPP_GLOBAL_Control
0x140026856  lea     rdx, WPP_GLOBAL_Control
0x14002685d  cmp     rbx, rdx
0x140026860  jz      loc_1400269D0
0x140026866  test    byte ptr [rbx+1Ch], 1
0x14002686a  jz      short loc_14002689E
0x14002686c  cmp     [rbx+19h], bpl
0x140026870  jb      short loc_14002689E
0x140026872  movzx   r9d, [rsp+98h+arg_28]
0x14002687b  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140026882  mov     rcx, [rbx+10h]
0x140026886  mov     edx, 24h ; '$'
0x14002688b  call    WPP_SF_d
0x140026890  mov     rbx, cs:WPP_GLOBAL_Control
0x140026897  lea     rdx, WPP_GLOBAL_Control
0x14002689e  cmp     rbx, rdx
0x1400268a1  jz      loc_1400269D0
0x1400268a7  test    byte ptr [rbx+1Ch], 1
0x1400268ab  jz      short loc_1400268DF
0x1400268ad  cmp     [rbx+19h], bpl
0x1400268b1  jb      short loc_1400268DF
0x1400268b3  movzx   r9d, [rsp+98h+arg_30]
0x1400268bc  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x1400268c3  mov     rcx, [rbx+10h]
0x1400268c7  mov     edx, 25h ; '%'
0x1400268cc  call    WPP_SF_d
0x1400268d1  mov     rbx, cs:WPP_GLOBAL_Control
0x1400268d8  lea     rdx, WPP_GLOBAL_Control
0x1400268df  cmp     rbx, rdx
0x1400268e2  jz      loc_1400269D0
0x1400268e8  test    byte ptr [rbx+1Ch], 1
0x1400268ec  jz      short loc_140026926
0x1400268ee  cmp     [rbx+19h], bpl
0x1400268f2  jb      short loc_140026926
0x1400268f4  mov     rax, [rdi+28h]
0x1400268f8  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x1400268ff  mov     edx, 26h ; '&'
0x140026904  mov     rcx, [rax]
0x140026907  movzx   r9d, byte ptr [rcx+148h]
0x14002690f  mov     rcx, [rbx+10h]
0x140026913  call    WPP_SF_d
0x140026918  mov     rbx, cs:WPP_GLOBAL_Control
0x14002691f  lea     rdx, WPP_GLOBAL_Control
0x140026926  cmp     rbx, rdx
0x140026929  jz      loc_1400269D0
0x14002692f  test    byte ptr [rbx+1Ch], 1
0x140026933  jz      short loc_140026961
0x140026935  cmp     [rbx+19h], bpl
0x140026939  jb      short loc_140026961
0x14002693b  mov     rcx, [rbx+10h]
0x14002693f  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140026946  mov     edx, 27h ; '''
0x14002694b  mov     r9d, r14d
0x14002694e  call    WPP_SF_d
0x140026953  mov     rbx, cs:WPP_GLOBAL_Control
0x14002695a  lea     rdx, WPP_GLOBAL_Control
0x140026961  cmp     rbx, rdx
0x140026964  jz      short loc_1400269D0
0x140026966  test    byte ptr [rbx+1Ch], 1
0x14002696a  jz      short loc_1400269D0
0x14002696c  cmp     [rbx+19h], bpl
0x140026970  jb      short loc_1400269D0
0x140026972  movzx   ecx, word ptr [rsi+0Ah]
0x140026976  mov     edx, 28h ; '('
0x14002697b  movzx   eax, word ptr [rsi+0Ch]
0x14002697f  movzx   edi, word ptr [rsi+8]
0x140026983  movzx   r8d, word ptr [rsi+6]
0x140026988  movzx   r10d, word ptr [rsi+4]
0x14002698d  movzx   r11d, word ptr [rsi+2]
0x140026992  movzx   r9d, word ptr [rsi]
0x140026996  mov     [rsp+98h+var_50], eax
0x14002699a  mov     [rsp+98h+var_58], ecx
0x14002699e  mov     rcx, [rbx+10h]
0x1400269a2  mov     dword ptr [rsp+98h+var_60], edi
0x1400269a6  mov     [rsp+98h+var_68], r8d
0x1400269ab  mov     dword ptr [rsp+98h+var_70], r10d
0x1400269b0  mov     dword ptr [rsp+98h+var_78], r11d
0x1400269b5  call    WPP_SF_DDDDDDD
0x1400269ba  mov     rbx, cs:WPP_GLOBAL_Control
0x1400269c1  lea     rdx, WPP_GLOBAL_Control
0x1400269c8  mov     rdi, [rsp+98h+arg_0]
0x1400269d0  xor     r11d, r11d
0x1400269d3  mov     ecx, 0FFFFh
0x1400269d8  test    r14d, r14d
0x1400269db  jz      short loc_1400269E2
0x1400269dd  mov     ebp, r15d
0x1400269e0  jmp     short loc_1400269EF
0x1400269e2  movzx   ebp, word ptr [rsi]
0x1400269e5  cmp     bp, cx
0x1400269e8  cmovz   ebp, r11d
0x1400269ec  add     ebp, r15d
0x1400269ef  mov     eax, 2D0h
0x1400269f4  cmp     ebp, eax
0x1400269f6  jbe     short loc_140026A5C
0x1400269f8  cmp     rbx, rdx
0x1400269fb  jz      short loc_140026A5A
0x1400269fd  test    byte ptr [rbx+1Ch], 1
0x140026a01  jz      short loc_140026A5A
0x140026a03  cmp     byte ptr [rbx+19h], 5
0x140026a07  jb      short loc_140026A5A
0x140026a09  mov     rax, [rdi+28h]
0x140026a0d  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140026a14  mov     r9, [r12+8]
0x140026a19  mov     edx, 29h ; ')'
0x140026a1e  mov     rcx, [rbx+10h]
0x140026a22  mov     rax, [rax+70h]
0x140026a26  mov     [rsp+98h+var_60], rax
0x140026a2b  mov     rax, [rsp+98h+arg_10]
0x140026a33  mov     [rsp+98h+var_68], r15d
0x140026a38  mov     [rsp+98h+var_70], rax
0x140026a3d  mov     rax, [r12]
0x140026a41  mov     [rsp+98h+var_78], rax
0x140026a46  call    WPP_SF_iiiDS
0x140026a4b  xor     r11d, r11d
0x140026a4e  lea     rdx, WPP_GLOBAL_Control
0x140026a55  mov     eax, 2D0h
0x140026a5a  mov     ebp, eax
0x140026a5c  cmp     r14d, 5Fh ; '_'
0x140026a60  ja      short loc_140026A6A
0x140026a62  mov     eax, r11d
0x140026a65  test    r15d, r15d
0x140026a68  jz      short loc_140026A6F
0x140026a6a  mov     eax, 1
0x140026a6f  mov     rcx, [rsp+98h+arg_40]
0x140026a77  mov     ebx, 6
0x140026a7c  mov     [rcx], eax
0x140026a7e  test    r14d, r14d
0x140026a81  jz      short loc_140026AF6
0x140026a83  cmp     r14d, 7Fh
0x140026a87  jb      loc_140026B58
0x140026a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140026a94  cmp     rcx, rdx
0x140026a97  jz      short loc_140026AE8
0x140026a99  test    byte ptr [rcx+1Ch], 1
0x140026a9d  jz      short loc_140026AE8
0x140026a9f  cmp     byte ptr [rcx+19h], 5
0x140026aa3  jb      short loc_140026AE8
0x140026aa5  mov     rax, [rdi+28h]
0x140026aa9  lea     edx, [rbx+24h]
0x140026aac  mov     r9, [r12+8]
0x140026ab1  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140026ab8  mov     rcx, [rcx+10h]
0x140026abc  mov     rax, [rax+70h]
0x140026ac0  mov     [rsp+98h+var_60], rax
0x140026ac5  mov     rax, [rsp+98h+arg_10]
0x140026acd  mov     [rsp+98h+var_68], r14d
0x140026ad2  mov     [rsp+98h+var_70], rax
0x140026ad7  mov     rax, [r12]
0x140026adb  mov     [rsp+98h+var_78], rax
0x140026ae0  call    WPP_SF_iiiDS
0x140026ae5  xor     r11d, r11d
0x140026ae8  lea     rdi, [rsi+2]
0x140026aec  movzx   eax, r11w
0x140026af0  mov     rcx, rbx
0x140026af3  rep stosw
0x140026af6  mov     [rsi], bp
0x140026af9  mov     r15, [rsp+98h+arg_48]
0x140026b01  mov     r12, [rsp+98h+arg_50]
0x140026b09  test    r15, r15
0x140026b0c  jnz     short loc_140026B17
0x140026b0e  test    r12, r12
0x140026b11  jz      loc_140026D51
0x140026b17  mov     rbx, cs:WPP_GLOBAL_Control
0x140026b1e  mov     ebp, r11d
0x140026b21  mov     r12, [rsp+98h+arg_0]
0x140026b29  mov     r13d, r11d
0x140026b2c  mov     r15d, r11d
0x140026b2f  mov     r14d, r11d
0x140026b32  mov     r10d, 0FFFFh
0x140026b38  mov     r9d, r14d
0x140026b3b  cmp     [rsi+r9*2], r10w
0x140026b40  jz      loc_140026CC8
0x140026b46  test    r14d, r14d
0x140026b49  jnz     loc_140026BFC
0x140026b4f  lea     r8d, [r14+1]
0x140026b53  jmp     loc_140026C26
0x140026b58  lea     r10d, [r14+r13]
0x140026b5c  lea     r9d, [r13+1]
0x140026b60  cmp     r9d, r10d
0x140026b63  ja      short loc_140026AF9
0x140026b65  mov     r14d, 0FFFFh
0x140026b6b  mov     r8d, ebx
0x140026b6e  mov     eax, r8d
0x140026b71  cmp     [rsi+rax*2], r14w
0x140026b76  jz      short loc_140026B8D
0x140026b78  xor     edx, edx
0x140026b7a  mov     ecx, r8d
0x140026b7d  mov     edi, 1
0x140026b82  mov     eax, r9d
0x140026b85  shl     edi, cl
0x140026b87  div     edi
0x140026b89  test    edx, edx
0x140026b8b  jz      short loc_140026BB3
0x140026b8d  sub     r8d, 1
0x140026b91  jns     short loc_140026B6E
0x140026b93  movzx   ecx, word ptr [rsi]
0x140026b96  cmp     r9d, r10d
0x140026b99  mov     eax, r11d
0x140026b9c  cmovz   eax, ebp
0x140026b9f  add     ecx, eax
0x140026ba1  shr     ecx, 1
0x140026ba3  inc     r9d
0x140026ba6  mov     [rsi], cx
0x140026ba9  cmp     r9d, r10d
0x140026bac  jbe     short loc_140026B6B
0x140026bae  jmp     loc_140026AF9
0x140026bb3  cmp     r8d, ebx
0x140026bb6  jnb     short loc_140026BEB
0x140026bb8  mov     edx, r8d
0x140026bbb  movzx   eax, word ptr [rsi+rdx*2]
0x140026bbf  cmp     [rsi+rdx*2+2], r14w
0x140026bc5  jz      short loc_140026BD9
0x140026bc7  mov     ecx, eax
0x140026bc9  movzx   eax, word ptr [rsi+rdx*2+2]
0x140026bce  add     ecx, eax
0x140026bd0  shr     ecx, 1
0x140026bd2  mov     [rsi+rdx*2+2], cx
0x140026bd7  jmp     short loc_140026BEB
0x140026bd9  mov     [rsi+rdx*2+2], ax
0x140026bde  jmp     short loc_140026BEB
0x140026be0  movzx   eax, word ptr [rsi+r8*2]
0x140026be5  mov     [rsi+r8*2+2], ax
0x140026beb  sub     r8d, 1
0x140026bef  jns     short loc_140026BE0
  ... truncated ...
```
