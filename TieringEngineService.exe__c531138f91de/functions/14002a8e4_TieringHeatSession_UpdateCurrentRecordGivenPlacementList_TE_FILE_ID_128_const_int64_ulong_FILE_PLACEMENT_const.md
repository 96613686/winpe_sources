# TieringHeatSession::UpdateCurrentRecordGivenPlacementList(TE_FILE_ID_128 const *,__int64,ulong,_FILE_PLACEMENT const *,unsigned __int64,int,int,int,uchar,ushort)

- ea: `0x14002a8e4`
- end: `0x14002ac0e`
- name: `?UpdateCurrentRecordGivenPlacementList@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@_JKPEBU_FILE_PLACEMENT@@_KHHHEG@Z`
- size: `810`
- prototype: `__int64 __fastcall(TieringHeatSession *this, const struct TE_FILE_ID_128 *, unsigned __int64, unsigned int, const struct _FILE_PLACEMENT *, unsigned __int64, int, int, int, unsigned __int8, unsigned __int16)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14002b15c`
- `0x140030e10`

## callees

- `0x14002a8e4`
- `0x14002ac14`
- `0x14002bc8c`
- `0x14002bd3c`
- `0x14002be08`

## import_xrefs

- `ESENT!JetDelete` at `0x14002ab3c`
- `ESENT!JetDelete` at `0x14002ab3c`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::UpdateCurrentRecordGivenPlacementList(
        TieringHeatSession *this,
        const struct TE_FILE_ID_128 *a2,
        unsigned __int64 a3,
        unsigned int a4,
        const struct _FILE_PLACEMENT *a5,
        unsigned __int64 a6,
        int a7,
        int a8,
        int a9,
        unsigned __int8 a10,
        unsigned __int16 a11)
{
  const struct TE_FILE_ID_128 *v13; // rdi
  unsigned __int8 v15; // bl
  __int64 v16; // rax
  int v17; // r11d
  unsigned __int64 v18; // rbp
  unsigned __int8 v20; // r12
  unsigned __int64 v21; // r9
  int v22; // r10d
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rax
  signed __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  char v27; // dl
  char v28; // al
  unsigned __int64 v29; // r9
  unsigned int updated; // ebx
  int v31; // r8d
  _QWORD *v32; // rcx
  int v33; // edx
  unsigned int v35; // [rsp+50h] [rbp-48h]
  unsigned __int64 v36; // [rsp+58h] [rbp-40h]
  int v38; // [rsp+B0h] [rbp+18h]

  v13 = a2;
  if ( a3 < a6 && !a9 )
  {
    v15 = a10 & 0xF3;
    v16 = **((_QWORD **)this + 5);
    v38 = *(_DWORD *)(v16 + 316);
    v35 = *(_DWORD *)(v16 + 320);
    if ( a7 )
    {
      if ( a8 )
        v15 |= 8u;
      else
        v15 |= 4u;
    }
    v17 = 0;
    v18 = a3 + 0x100000;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    if ( !a4 )
      goto LABEL_35;
    v23 = *(unsigned int *)(v16 + 316);
    v36 = v23;
    while ( 1 )
    {
      v24 = *(_QWORD *)a5;
      v25 = *((_QWORD *)a5 + 2) * v23 + *(_QWORD *)a5;
      if ( *(_QWORD *)a5 <= a3 )
      {
        if ( v25 > (__int64)a3 )
        {
          v26 = v25 - a3;
          goto LABEL_19;
        }
        if ( v24 < a3 )
          goto LABEL_16;
      }
      if ( v25 > (__int64)v18 )
      {
LABEL_16:
        if ( v24 >= v18 || v25 < (__int64)v18 )
        {
          v26 = 0;
          if ( v24 > v18 )
            goto LABEL_30;
        }
        else
        {
          v26 = v18 - v24;
        }
      }
      else
      {
        v26 = *((_QWORD *)a5 + 2) * v23;
      }
LABEL_19:
      if ( v26 > 0x100000 )
      {
        v26 = 0x100000;
LABEL_22:
        v27 = *((_BYTE *)a5 + 24);
        if ( v27 )
        {
          if ( v17 )
          {
            v28 = v20;
            if ( v20 != v27 )
              v28 = 64;
            v20 = v28;
          }
          else
          {
            v20 = *((_BYTE *)a5 + 24);
          }
          v21 += v26;
          ++v17;
        }
        goto LABEL_29;
      }
      if ( v26 )
        goto LABEL_22;
LABEL_29:
      a5 = (const struct _FILE_PLACEMENT *)((char *)a5 + 32);
      if ( ++v22 >= a4 )
      {
LABEL_30:
        v13 = a2;
        if ( v20 && v21 )
        {
          if ( v38 )
            v29 = v21 / v36;
          else
            LOWORD(v29) = a11;
          goto LABEL_40;
        }
LABEL_35:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_iiiS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            87,
            (_DWORD)a5,
            *((_QWORD *)v13 + 1),
            *(_QWORD *)v13,
            a3,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
        }
        LOWORD(v29) = 0;
LABEL_40:
        if ( (unsigned __int16)v29 > v35 )
          LOWORD(v29) = v35;
        updated = TieringHeatSession::UpdateHeatRecordForPlacement(this, v13, a3, v29, v20, v15, v18 >= a6, a7);
        if ( updated )
        {
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v33 = 88;
            goto LABEL_52;
          }
        }
        return updated;
      }
    }
  }
  updated = JetDelete(*((_QWORD *)this + 1), *((_QWORD *)this + 3));
  if ( updated )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = 85;
LABEL_52:
      WPP_SF_iiiSL(
        v32[2],
        v33,
        v31,
        *((_QWORD *)v13 + 1),
        *(_QWORD *)v13,
        a3,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        updated);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_iiiiDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v31,
      *((_QWORD *)v13 + 1),
      *(_QWORD *)v13,
      a3,
      a6,
      a9,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
  }
  return updated;
}

```

## disassembly

```asm
0x14002a8e4  mov     [rsp+arg_18], rbx
0x14002a8e9  mov     [rsp+arg_8], rdx
0x14002a8ee  push    rbp
0x14002a8ef  push    rsi
0x14002a8f0  push    rdi
0x14002a8f1  push    r12
0x14002a8f3  push    r13
0x14002a8f5  push    r14
0x14002a8f7  push    r15
0x14002a8f9  sub     rsp, 60h
0x14002a8fd  mov     r12, [rsp+98h+arg_28]
0x14002a905  mov     r13d, r9d
0x14002a908  mov     ebp, [rsp+98h+arg_40]
0x14002a90f  mov     rsi, r8
0x14002a912  mov     rdi, rdx
0x14002a915  mov     r15, rcx
0x14002a918  cmp     r8, r12
0x14002a91b  jnb     loc_14002AB34
0x14002a921  test    ebp, ebp
0x14002a923  jnz     loc_14002AB34
0x14002a929  mov     rax, [rcx+28h]
0x14002a92d  mov     bl, [rsp+98h+arg_48]
0x14002a934  and     bl, 0F3h
0x14002a937  mov     rax, [rax]
0x14002a93a  mov     ecx, [rax+13Ch]
0x14002a940  mov     eax, [rax+140h]
0x14002a946  mov     [rsp+98h+arg_10], ecx
0x14002a94d  mov     [rsp+98h+var_48], eax
0x14002a951  cmp     [rsp+98h+arg_30], ebp
0x14002a958  jz      short loc_14002A96B
0x14002a95a  cmp     [rsp+98h+arg_38], ebp
0x14002a961  jz      short loc_14002A968
0x14002a963  or      bl, 8
0x14002a966  jmp     short loc_14002A96B
0x14002a968  or      bl, 4
0x14002a96b  xor     r11d, r11d
0x14002a96e  lea     rbp, [r8+100000h]
0x14002a975  mov     r8, [rsp+98h+arg_20]
0x14002a97d  lea     r14, WPP_GLOBAL_Control
0x14002a984  xor     r12b, r12b
0x14002a987  xor     r9d, r9d
0x14002a98a  xor     r10d, r10d
0x14002a98d  test    r13d, r13d
0x14002a990  jz      loc_14002AA72
0x14002a996  mov     rdi, rcx
0x14002a999  mov     [rsp+98h+var_40], rcx
0x14002a99e  mov     rax, [r8]
0x14002a9a1  mov     rdx, rdi
0x14002a9a4  imul    rdx, [r8+10h]
0x14002a9a9  lea     rcx, [rdx+rax]
0x14002a9ad  cmp     rax, rsi
0x14002a9b0  ja      short loc_14002A9C1
0x14002a9b2  cmp     rcx, rsi
0x14002a9b5  jle     short loc_14002A9BC
0x14002a9b7  sub     rcx, rsi
0x14002a9ba  jmp     short loc_14002A9E4
0x14002a9bc  cmp     rax, rsi
0x14002a9bf  jb      short loc_14002A9CB
0x14002a9c1  cmp     rcx, rbp
0x14002a9c4  jg      short loc_14002A9CB
0x14002a9c6  mov     rcx, rdx
0x14002a9c9  jmp     short loc_14002A9E4
0x14002a9cb  cmp     rax, rbp
0x14002a9ce  jnb     short loc_14002A9DD
0x14002a9d0  cmp     rcx, rbp
0x14002a9d3  jl      short loc_14002A9DD
0x14002a9d5  mov     rcx, rbp
0x14002a9d8  sub     rcx, rax
0x14002a9db  jmp     short loc_14002A9E4
0x14002a9dd  xor     ecx, ecx
0x14002a9df  cmp     rax, rbp
0x14002a9e2  ja      short loc_14002AA3C
0x14002a9e4  mov     eax, 100000h
0x14002a9e9  cmp     rcx, rax
0x14002a9ec  jbe     short loc_14002A9F2
0x14002a9ee  mov     ecx, eax
0x14002a9f0  jmp     short loc_14002A9F7
0x14002a9f2  test    rcx, rcx
0x14002a9f5  jz      short loc_14002AA2C
0x14002a9f7  mov     dl, [r8+18h]
0x14002a9fb  test    dl, dl
0x14002a9fd  jz      short loc_14002AA2C
0x14002a9ff  test    r11d, r11d
0x14002aa02  jnz     short loc_14002AA09
0x14002aa04  mov     r12b, dl
0x14002aa07  jmp     short loc_14002AA26
0x14002aa09  cmp     r12b, dl
0x14002aa0c  movzx   eax, r12b
0x14002aa10  mov     [rsp+98h+arg_0], 40h ; '@'
0x14002aa1b  cmovnz  eax, [rsp+98h+arg_0]
0x14002aa23  mov     r12b, al
0x14002aa26  add     r9, rcx
0x14002aa29  inc     r11d
0x14002aa2c  add     r8, 20h ; ' '
0x14002aa30  inc     r10d
0x14002aa33  cmp     r10d, r13d
0x14002aa36  jb      loc_14002A99E
0x14002aa3c  mov     rdi, [rsp+98h+arg_8]
0x14002aa44  test    r12b, r12b
0x14002aa47  jz      short loc_14002AA72
0x14002aa49  test    r9, r9
0x14002aa4c  jz      short loc_14002AA72
0x14002aa4e  cmp     [rsp+98h+arg_10], 0
0x14002aa56  jbe     short loc_14002AA67
0x14002aa58  mov     rax, r9
0x14002aa5b  xor     edx, edx
0x14002aa5d  div     [rsp+98h+var_40]
0x14002aa62  mov     r9, rax
0x14002aa65  jmp     short loc_14002AABC
0x14002aa67  movzx   r9d, [rsp+98h+arg_50]
0x14002aa70  jmp     short loc_14002AABC
0x14002aa72  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa79  cmp     rcx, r14
0x14002aa7c  jz      short loc_14002AAB6
0x14002aa7e  test    byte ptr [rcx+1Ch], 1
0x14002aa82  jz      short loc_14002AAB6
0x14002aa84  cmp     byte ptr [rcx+19h], 5
0x14002aa88  jb      short loc_14002AAB6
0x14002aa8a  mov     rax, [r15+28h]
0x14002aa8e  mov     edx, 57h ; 'W'
0x14002aa93  mov     r9, [rdi+8]
0x14002aa97  mov     rcx, [rcx+10h]
0x14002aa9b  mov     rax, [rax+70h]
0x14002aa9f  mov     qword ptr [rsp+98h+var_68], rax
0x14002aaa4  mov     rax, [rdi]
0x14002aaa7  mov     qword ptr [rsp+98h+var_70], rsi
0x14002aaac  mov     qword ptr [rsp+98h+var_78], rax
0x14002aab1  call    WPP_SF_iiiS
0x14002aab6  xor     eax, eax
0x14002aab8  movzx   r9d, ax
0x14002aabc  mov     ecx, [rsp+98h+var_48]
0x14002aac0  movzx   eax, r9w
0x14002aac4  cmp     eax, ecx
0x14002aac6  jbe     short loc_14002AACC
0x14002aac8  movzx   r9d, cx; unsigned __int16
0x14002aacc  mov     ecx, [rsp+98h+arg_30]
0x14002aad3  xor     eax, eax
0x14002aad5  cmp     rbp, [rsp+98h+arg_28]
0x14002aadd  mov     r8, rsi; __int64
0x14002aae0  mov     [rsp+98h+var_60], ecx; int
0x14002aae4  mov     rdx, rdi; struct TE_FILE_ID_128 *
0x14002aae7  setnb   al
0x14002aaea  mov     rcx, r15; this
0x14002aaed  mov     [rsp+98h+var_68], eax; int
0x14002aaf1  mov     [rsp+98h+var_70], bl; unsigned __int8
0x14002aaf5  mov     [rsp+98h+var_78], r12b; unsigned __int8
0x14002aafa  call    ?UpdateHeatRecordForPlacement@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@_JGEEHH@Z; TieringHeatSession::UpdateHeatRecordForPlacement(TE_FILE_ID_128 const *,__int64,ushort,uchar,uchar,int,int)
0x14002aaff  mov     ebx, eax
0x14002ab01  test    eax, eax
0x14002ab03  jz      loc_14002ABF4
0x14002ab09  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab10  cmp     rcx, r14
0x14002ab13  jz      loc_14002ABF4
0x14002ab19  test    byte ptr [rcx+1Ch], 1
0x14002ab1d  jz      loc_14002ABF4
0x14002ab23  cmp     byte ptr [rcx+19h], 2
0x14002ab27  jb      loc_14002ABF4
0x14002ab2d  mov     edx, 58h ; 'X'
0x14002ab32  jmp     short loc_14002AB78
0x14002ab34  mov     rdx, [rcx+18h]; tableid
0x14002ab38  mov     rcx, [rcx+8]; sesid
0x14002ab3c  call    cs:__imp_JetDelete
0x14002ab42  mov     ebx, eax
0x14002ab44  test    eax, eax
0x14002ab46  jz      short loc_14002ABA5
0x14002ab48  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab4f  lea     r14, WPP_GLOBAL_Control
0x14002ab56  cmp     rcx, r14
0x14002ab59  jz      loc_14002ABF4
0x14002ab5f  test    byte ptr [rcx+1Ch], 1
0x14002ab63  jz      loc_14002ABF4
0x14002ab69  cmp     byte ptr [rcx+19h], 2
0x14002ab6d  jb      loc_14002ABF4
0x14002ab73  mov     edx, 55h ; 'U'
0x14002ab78  mov     rax, [r15+28h]
0x14002ab7c  mov     r9, [rdi+8]
0x14002ab80  mov     rcx, [rcx+10h]
0x14002ab84  mov     [rsp+98h+var_60], ebx
0x14002ab88  mov     rax, [rax+70h]
0x14002ab8c  mov     qword ptr [rsp+98h+var_68], rax
0x14002ab91  mov     rax, [rdi]
0x14002ab94  mov     qword ptr [rsp+98h+var_70], rsi
0x14002ab99  mov     qword ptr [rsp+98h+var_78], rax
0x14002ab9e  call    WPP_SF_iiiSL
0x14002aba3  jmp     short loc_14002ABF4
0x14002aba5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002abac  lea     r14, WPP_GLOBAL_Control
0x14002abb3  cmp     rcx, r14
0x14002abb6  jz      short loc_14002ABF4
0x14002abb8  test    byte ptr [rcx+1Ch], 1
0x14002abbc  jz      short loc_14002ABF4
0x14002abbe  cmp     byte ptr [rcx+19h], 5
0x14002abc2  jb      short loc_14002ABF4
0x14002abc4  mov     rax, [r15+28h]
0x14002abc8  mov     r9, [rdi+8]
0x14002abcc  mov     rcx, [rcx+10h]
0x14002abd0  mov     rdx, [rax+70h]
0x14002abd4  mov     rax, [rdi]
0x14002abd7  mov     [rsp+98h+var_58], rdx
0x14002abdc  mov     [rsp+98h+var_60], ebp
0x14002abe0  mov     qword ptr [rsp+98h+var_68], r12
0x14002abe5  mov     qword ptr [rsp+98h+var_70], rsi
0x14002abea  mov     qword ptr [rsp+98h+var_78], rax
0x14002abef  call    WPP_SF_iiiiDS
0x14002abf4  mov     eax, ebx
0x14002abf6  mov     rbx, [rsp+98h+arg_18]
0x14002abfe  add     rsp, 60h
0x14002ac02  pop     r15
0x14002ac04  pop     r14
0x14002ac06  pop     r13
0x14002ac08  pop     r12
0x14002ac0a  pop     rdi
0x14002ac0b  pop     rsi
0x14002ac0c  pop     rbp
0x14002ac0d  retn
```
