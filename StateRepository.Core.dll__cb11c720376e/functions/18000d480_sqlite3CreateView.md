# sqlite3CreateView

- ea: `0x18000d480`
- end: `0x18000d768`
- name: `sqlite3CreateView`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180031b38`

## callees

- `0x18000c850`
- `0x18000cb64`
- `0x18000d480`
- `0x18000d770`
- `0x18000ded0`
- `0x18000e5c0`
- `0x18000e808`
- `0x18000e944`
- `0x180015168`
- `0x180060ce8`
- `0x18006910e`
- `0x180086e18`

## pseudocode

```c
__int64 __fastcall sqlite3CreateView(
        __int64 *a1,
        _DWORD *a2,
        _OWORD *a3,
        __int64 a4,
        _DWORD *a5,
        __int64 a6,
        int a7,
        int a8)
{
  __int64 v12; // r14
  __int64 v13; // rsi
  __int64 v14; // rcx
  int v15; // r9d
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rdi
  __int64 v21; // rax
  int v22; // edx
  int v23; // edx
  __int64 v24; // r8
  __int64 i; // rcx
  __int64 result; // rax
  __int64 v27; // rax
  __int128 v28; // [rsp+40h] [rbp-69h] BYREF
  __int64 *v29; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v30[4]; // [rsp+58h] [rbp-51h] BYREF
  int v31; // [rsp+78h] [rbp-31h]
  __int16 v32; // [rsp+7Ch] [rbp-2Dh]
  __int64 **v33; // [rsp+80h] [rbp-29h]
  __int64 v34; // [rsp+88h] [rbp-21h]
  bool v35; // [rsp+90h] [rbp-19h]
  __int64 v36; // [rsp+98h] [rbp-11h]
  const char *v37; // [rsp+A0h] [rbp-9h]
  __int64 v38; // [rsp+A8h] [rbp-1h]

  v28 = 0;
  memset_0(&v29, 0, 0x60u);
  v12 = *a1;
  if ( *((__int16 *)a1 + 152) > 0 )
  {
    sqlite3ErrorMsg(a1, "parameters are not allowed in views");
LABEL_28:
    v20 = a6;
    goto LABEL_18;
  }
  sqlite3StartTable(a1, a3, a4, a7, 1, 0, a8);
  v13 = a1[44];
  if ( !v13 || *((_DWORD *)a1 + 13) )
    goto LABEL_28;
  *(_DWORD *)(v13 + 48) |= 0x200u;
  if ( *(_DWORD *)(a4 + 8) )
  {
    if ( *(_BYTE *)(*a1 + 197) )
    {
      a4 = 0;
      sqlite3ErrorMsg(a1, "corrupt database");
    }
    else if ( (int)sqlite3FindDb(*a1, a3) < 0 )
    {
      sqlite3ErrorMsg(a1, "unknown database %T", a3);
    }
  }
  else
  {
    a4 = (__int64)a3;
  }
  v14 = *(_QWORD *)(v13 + 96);
  v15 = -32768;
  if ( v14 )
  {
    v16 = *(_QWORD *)(v12 + 32);
    v15 = 0;
    if ( *(_QWORD *)(v16 + 24) != v14 )
    {
      do
        ++v15;
      while ( *(_QWORD *)(32LL * v15 + v16 + 24) != v14 );
    }
  }
  v17 = *a1;
  v29 = a1;
  v18 = 32LL * v15;
  v36 = *(_QWORD *)(v18 + *(_QWORD *)(v17 + 32));
  v19 = *(_QWORD *)(v18 + *(_QWORD *)(v17 + 32) + 24);
  v37 = "view";
  v35 = v15 == 1;
  v38 = a4;
  v20 = a6;
  v30[1] = fixExprCb;
  v34 = v19;
  v30[2] = fixSelectCb;
  v30[0] = a1;
  v30[3] = guard_check_icall_nop;
  v33 = &v29;
  v31 = 0;
  v32 = 0;
  if ( !(unsigned int)sqlite3WalkSelect(v30, a6) )
  {
    *(_DWORD *)(a6 + 4) |= 0x200000u;
    if ( *((_BYTE *)a1 + 308) >= 2u )
    {
      v21 = a6;
      v20 = 0;
    }
    else
    {
      v21 = sqlite3SelectDup(v12, a6, 1);
    }
    *(_QWORD *)(v13 + 64) = v21;
    *(_QWORD *)(v13 + 32) = sqlite3ExprListDup(v12, a5, 1);
    *(_BYTE *)(v13 + 63) = 2;
    if ( !*(_BYTE *)(v12 + 103) )
    {
      v28 = *((_OWORD *)a1 + 18);
      v22 = v28;
      if ( *(_BYTE *)v28 != 59 )
      {
        v22 = DWORD2(v28) + v28;
        *(_QWORD *)&v28 = DWORD2(v28) + (_QWORD)v28;
      }
      v23 = v22 - *a2;
      v24 = *(_QWORD *)a2;
      DWORD2(v28) = 0;
      for ( i = *(unsigned __int8 *)(v23 + v24 - 1);
            (*((_BYTE *)&qword_18009E630 + i) & 1) != 0;
            i = *(unsigned __int8 *)(v27 + v24 - 2) )
      {
        v27 = v23--;
      }
      DWORD2(v28) = 1;
      *(_QWORD *)&v28 = v24 + v23 - 1;
      sqlite3EndTable(a1, 0, &v28, 0, 0);
    }
  }
LABEL_18:
  result = sqlite3SelectDelete(v12, v20);
  if ( *((_BYTE *)a1 + 308) >= 2u )
    result = sqlite3RenameExprlistUnmap(a1, a5);
  if ( a5 )
    return exprListDeleteNN(v12, a5);
  return result;
}

```

## disassembly

```asm
0x18000d480  push    rbp
0x18000d482  push    rbx
0x18000d483  push    rsi
0x18000d484  push    rdi
0x18000d485  push    r13
0x18000d487  push    r14
0x18000d489  push    r15
0x18000d48b  lea     rbp, [rsp-7]
0x18000d490  sub     rsp, 0B0h
0x18000d497  mov     r13, rdx
0x18000d49a  mov     r15, r8
0x18000d49d  xor     edx, edx; Val
0x18000d49f  mov     rbx, rcx
0x18000d4a2  xorps   xmm0, xmm0
0x18000d4a5  lea     rcx, [rbp+37h+var_90]; void *
0x18000d4a9  mov     rdi, r9
0x18000d4ac  movups  [rbp+37h+var_A0], xmm0
0x18000d4b0  lea     r8d, [rdx+60h]; Size
0x18000d4b4  call    memset_0
0x18000d4b9  mov     r14, [rbx]
0x18000d4bc  xor     ecx, ecx
0x18000d4be  cmp     [rbx+130h], cx
0x18000d4c5  jg      loc_18000D711
0x18000d4cb  mov     eax, [rbp+37h+arg_38]
0x18000d4ce  mov     r8, rdi
0x18000d4d1  mov     r9d, [rbp+37h+arg_30]
0x18000d4d5  mov     rdx, r15
0x18000d4d8  mov     [rsp+0E0h+var_B0], eax
0x18000d4dc  mov     [rsp+0E0h+var_B8], ecx
0x18000d4e0  mov     rcx, rbx
0x18000d4e3  mov     dword ptr [rsp+0E0h+var_C0], 1
0x18000d4eb  call    sqlite3StartTable
0x18000d4f0  mov     rsi, [rbx+160h]
0x18000d4f7  xor     eax, eax
0x18000d4f9  test    rsi, rsi
0x18000d4fc  jz      loc_18000D720
0x18000d502  cmp     [rbx+34h], eax
0x18000d505  jnz     loc_18000D720
0x18000d50b  bts     dword ptr [rsi+30h], 9
0x18000d510  cmp     [rdi+8], eax
0x18000d513  ja      loc_18000D6D4
0x18000d519  mov     rdi, r15
0x18000d51c  xor     r15d, r15d
0x18000d51f  mov     rcx, [rsi+60h]
0x18000d523  mov     r9d, 0FFFF8000h
0x18000d529  test    rcx, rcx
0x18000d52c  jz      short loc_18000D54C
0x18000d52e  mov     rdx, [r14+20h]
0x18000d532  mov     r9d, r15d
0x18000d535  cmp     [rdx+18h], rcx
0x18000d539  jz      short loc_18000D54C
0x18000d53b  inc     r9d
0x18000d53e  movsxd  rax, r9d
0x18000d541  shl     rax, 5
0x18000d545  cmp     [rax+rdx+18h], rcx
0x18000d54a  jnz     short loc_18000D53B
0x18000d54c  mov     rdx, [rbx]
0x18000d54f  mov     [rbp+37h+var_90], rbx
0x18000d553  movsxd  r8, r9d
0x18000d556  shl     r8, 5
0x18000d55a  mov     rax, [rdx+20h]
0x18000d55e  cmp     r9d, 1
0x18000d562  mov     rcx, [r8+rax]
0x18000d566  mov     [rbp+37h+var_48], rcx
0x18000d56a  mov     rax, [rdx+20h]
0x18000d56e  mov     rcx, [r8+rax+18h]
0x18000d573  lea     rax, aView_0; "view"
0x18000d57a  mov     [rbp+37h+var_40], rax
0x18000d57e  setz    [rbp+37h+var_50]
0x18000d582  lea     rax, fixExprCb
0x18000d589  mov     [rbp+37h+var_38], rdi
0x18000d58d  mov     rdi, [rbp+37h+arg_28]
0x18000d591  mov     [rbp+37h+var_80], rax
0x18000d595  mov     rdx, rdi
0x18000d598  lea     rax, fixSelectCb
0x18000d59f  mov     [rbp+37h+var_58], rcx
0x18000d5a3  mov     [rbp+37h+var_78], rax
0x18000d5a7  lea     rcx, [rbp+37h+var_88]
0x18000d5ab  lea     rax, _guard_check_icall_nop
0x18000d5b2  mov     [rbp+37h+var_88], rbx
0x18000d5b6  mov     [rbp+37h+var_70], rax
0x18000d5ba  lea     rax, [rbp+37h+var_90]
0x18000d5be  mov     [rbp+37h+var_60], rax
0x18000d5c2  mov     [rbp+37h+var_68], r15d
0x18000d5c6  mov     [rbp+37h+var_64], r15w
0x18000d5cb  call    sqlite3WalkSelect
0x18000d5d0  test    eax, eax
0x18000d5d2  jnz     loc_18000D689
0x18000d5d8  bts     dword ptr [rdi+4], 15h
0x18000d5dd  cmp     byte ptr [rbx+134h], 2
0x18000d5e4  jnb     loc_18000D706
0x18000d5ea  lea     r8d, [rax+1]
0x18000d5ee  mov     rdx, rdi
0x18000d5f1  mov     rcx, r14
0x18000d5f4  call    sqlite3SelectDup
0x18000d5f9  mov     rdx, [rbp+37h+arg_20]
0x18000d5fd  mov     r8d, 1
0x18000d603  mov     rcx, r14
0x18000d606  mov     [rsi+40h], rax
0x18000d60a  call    sqlite3ExprListDup
0x18000d60f  mov     [rsi+20h], rax
0x18000d613  mov     byte ptr [rsi+3Fh], 2
0x18000d617  cmp     [r14+67h], r15b
0x18000d61b  jnz     short loc_18000D689
0x18000d61d  movups  xmm0, xmmword ptr [rbx+120h]
0x18000d624  movq    rdx, xmm0
0x18000d629  movups  [rbp+37h+var_A0], xmm0
0x18000d62d  cmp     byte ptr [rdx], 3Bh ; ';'
0x18000d630  jnz     loc_18000D6C5
0x18000d636  sub     edx, [r13+0]
0x18000d63a  lea     r10, qword_18009E630
0x18000d641  mov     r8, [r13+0]
0x18000d645  mov     r9d, 1
0x18000d64b  movsxd  rax, edx
0x18000d64e  mov     dword ptr [rbp+37h+var_A0+8], r15d
0x18000d652  movzx   ecx, byte ptr [rax+r8-1]
0x18000d658  test    [rcx+r10], r9b
0x18000d65c  jnz     loc_18000D746
0x18000d662  lea     eax, [rdx-1]
0x18000d665  mov     dword ptr [rbp+37h+var_A0+8], r9d
0x18000d669  movsxd  rcx, eax
0x18000d66c  xor     r9d, r9d
0x18000d66f  add     rcx, r8
0x18000d672  mov     [rsp+0E0h+var_C0], r15
0x18000d677  mov     qword ptr [rbp+37h+var_A0], rcx
0x18000d67b  lea     r8, [rbp+37h+var_A0]
0x18000d67f  mov     rcx, rbx
0x18000d682  xor     edx, edx
0x18000d684  call    sqlite3EndTable
0x18000d689  mov     rdx, rdi
0x18000d68c  mov     rcx, r14
0x18000d68f  call    sqlite3SelectDelete
0x18000d694  cmp     byte ptr [rbx+134h], 2
0x18000d69b  jnb     loc_18000D757
0x18000d6a1  cmp     [rbp+37h+arg_20], r15
0x18000d6a5  jz      short loc_18000D6B3
0x18000d6a7  mov     rdx, [rbp+37h+arg_20]
0x18000d6ab  mov     rcx, r14
0x18000d6ae  call    exprListDeleteNN
0x18000d6b3  add     rsp, 0B0h
0x18000d6ba  pop     r15
0x18000d6bc  pop     r14
0x18000d6be  pop     r13
0x18000d6c0  pop     rdi
0x18000d6c1  pop     rsi
0x18000d6c2  pop     rbx
0x18000d6c3  pop     rbp
0x18000d6c4  retn
0x18000d6c5  mov     eax, dword ptr [rbp+37h+var_A0+8]
0x18000d6c8  add     rdx, rax
0x18000d6cb  mov     qword ptr [rbp+37h+var_A0], rdx
0x18000d6cf  jmp     loc_18000D636
0x18000d6d4  mov     rcx, [rbx]
0x18000d6d7  cmp     [rcx+0C5h], al
0x18000d6dd  jnz     short loc_18000D72C
0x18000d6df  mov     rdx, r15
0x18000d6e2  call    sqlite3FindDb
0x18000d6e7  test    eax, eax
0x18000d6e9  jns     loc_18000D51C
0x18000d6ef  mov     r8, r15
0x18000d6f2  lea     rdx, aUnknownDatabas_0; "unknown database %T"
0x18000d6f9  mov     rcx, rbx
0x18000d6fc  call    sqlite3ErrorMsg
0x18000d701  jmp     loc_18000D51C
0x18000d706  mov     rax, rdi
0x18000d709  mov     rdi, r15
0x18000d70c  jmp     loc_18000D5F9
0x18000d711  lea     rdx, aParametersAreN; "parameters are not allowed in views"
0x18000d718  mov     rcx, rbx
0x18000d71b  call    sqlite3ErrorMsg
0x18000d720  mov     rdi, [rbp+37h+arg_28]
0x18000d724  xor     r15d, r15d
0x18000d727  jmp     loc_18000D689
0x18000d72c  xor     r15d, r15d
0x18000d72f  lea     rdx, aCorruptDatabas; "corrupt database"
0x18000d736  mov     rcx, rbx
0x18000d739  mov     edi, r15d
0x18000d73c  call    sqlite3ErrorMsg
0x18000d741  jmp     loc_18000D51F
0x18000d746  movsxd  rax, edx
0x18000d749  sub     edx, r9d
0x18000d74c  movzx   ecx, byte ptr [rax+r8-2]
0x18000d752  jmp     loc_18000D658
0x18000d757  mov     rdx, [rbp+37h+arg_20]
0x18000d75b  mov     rcx, rbx
0x18000d75e  call    sqlite3RenameExprlistUnmap
0x18000d763  jmp     loc_18000D6A1
```
