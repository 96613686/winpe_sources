# sqlite3BtreeIndexMoveto

- ea: `0x180010de0`
- end: `0x18001135f`
- name: `sqlite3BtreeIndexMoveto`
- size: `1407`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180021aa0`
- `0x1800381a0`
- `0x180056810`

## callees

- `0x180010de0`
- `0x1800117b4`
- `0x180012470`
- `0x180020d70`
- `0x18002c520`
- `0x18003a860`
- `0x18003af40`
- `0x18003eea0`
- `0x1800424e4`
- `0x1800520d4`
- `0x180056578`
- `0x180056c60`
- `0x180063758`
- `0x1800a8010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeIndexMoveto(__int64 a1, __int64 *a2, int *a3)
{
  __int64 v5; // rcx
  __int64 *v6; // r12
  char v7; // r9
  char v8; // al
  char v9; // r8
  __int64 v10; // rdx
  __int16 v11; // r9
  __int64 (__fastcall *v12)(); // rdi
  __int64 v13; // r9
  int i; // r8d
  __int64 v15; // rdx
  int v16; // eax
  __int64 result; // rax
  _BYTE *v18; // rax
  __int64 v19; // rsi
  int v20; // r14d
  int v21; // r15d
  int j; // ebp
  int v23; // ebp
  unsigned __int8 *v24; // rdx
  __int64 v25; // rcx
  int v26; // edi
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // r13
  char *v30; // rax
  unsigned __int8 *v31; // r12
  unsigned int inited; // edi
  unsigned int v33; // esi
  __int64 v34; // rax
  unsigned __int32 v35; // esi
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r14
  __int64 v39; // rbp
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 (__fastcall *v42)(); // [rsp+80h] [rbp+8h]
  __int64 v45; // [rsp+98h] [rbp+20h] BYREF

  v5 = *a2;
  v6 = a2;
  if ( *(_WORD *)(*a2 + 8) > 0xDu )
    goto LABEL_11;
  v7 = **(_BYTE **)(v5 + 24);
  if ( v7 )
  {
    if ( (v7 & 2) != 0 )
      goto LABEL_11;
    v8 = -1;
    v9 = 1;
  }
  else
  {
    v8 = 1;
    v9 = -1;
  }
  v10 = a2[1];
  v11 = *(_WORD *)(v10 + 20);
  *((_BYTE *)v6 + 32) = v9;
  *((_BYTE *)v6 + 33) = v8;
  if ( (v11 & 4) == 0 )
  {
    if ( (v11 & 0x39) == 0 && !*(_QWORD *)(v5 + 32) )
    {
      v12 = vdbeRecordCompareString;
      v6[2] = *(_QWORD *)(v10 + 8);
      *((_DWORD *)v6 + 6) = *(_DWORD *)(v10 + 16);
      goto LABEL_12;
    }
LABEL_11:
    v12 = sqlite3VdbeRecordCompare;
    goto LABEL_12;
  }
  v12 = vdbeRecordCompareInt;
  v6[2] = *(_QWORD *)v10;
LABEL_12:
  *((_BYTE *)v6 + 31) = 0;
  v42 = v12;
  if ( *(_BYTE *)a1 )
    goto LABEL_28;
  v13 = *(_QWORD *)(a1 + 136);
  if ( !*(_BYTE *)(v13 + 8) )
    goto LABEL_28;
  for ( i = 0; i < *(char *)(a1 + 84); ++i )
  {
    if ( *(_WORD *)(a1 + 2LL * i + 88) < *(_WORD *)(*(_QWORD *)(a1 + 8LL * i + 144) + 24LL) )
      goto LABEL_28;
  }
  v15 = *(unsigned __int16 *)(a1 + 86);
  if ( (_DWORD)v15 == *(unsigned __int16 *)(v13 + 24) - 1 )
  {
    v16 = indexCellCompare(a1, v15, v6, v12);
    if ( v16 <= 0 && !*((_BYTE *)v6 + 31) )
    {
      *a3 = v16;
      return 0;
    }
  }
  if ( *(char *)(a1 + 84) <= 0 || (int)indexCellCompare(a1, 0, v6, v12) > 0 || *((_BYTE *)v6 + 31) )
  {
    *((_BYTE *)v6 + 31) = 0;
LABEL_28:
    result = moveToRoot(a1);
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result == 16 )
      {
        *a3 = -1;
        return 0;
      }
      return result;
    }
LABEL_31:
    v19 = *(_QWORD *)(a1 + 136);
    v20 = 0;
    v21 = *(unsigned __int16 *)(v19 + 24) - 1;
    for ( j = v21; ; j = v21 + v20 )
    {
      v23 = j >> 1;
      v24 = (unsigned __int8 *)(*(_QWORD *)(v19 + 104)
                              + (unsigned __int16)(*(_WORD *)(v19 + 26)
                                                 & __ROR2__(*(_WORD *)(2 * v23 + *(_QWORD *)(v19 + 96)), 8)));
      v25 = *v24;
      if ( (unsigned int)v25 > *(unsigned __int8 *)(v19 + 11) )
      {
        v27 = v24[1];
        if ( (v27 & 0x80u) != 0
          || (v28 = v27 + ((unsigned __int8)(v25 & 0x7F) << 7), (unsigned int)v28 > *(unsigned __int16 *)(v19 + 14)) )
        {
          (*(void (__fastcall **)(__int64, unsigned __int8 *, __int64))(v19 + 128))(
            v19,
            &v24[-*(unsigned __int8 *)(v19 + 10)],
            a1 + 48);
          v29 = *(int *)(a1 + 48);
          if ( (int)v29 < 2
            || (unsigned int)v29 / *(_DWORD *)(*(_QWORD *)(a1 + 32) + 56LL) > *(_DWORD *)(*(_QWORD *)(a1 + 32) + 64LL) )
          {
            v41 = 76624;
LABEL_72:
            inited = sqlite3ReportError(11, v41, "database corruption");
LABEL_73:
            *(_WORD *)(a1 + 70) = 0;
            return inited;
          }
          v30 = (char *)sqlite3Malloc((int)v29 + 18);
          v31 = (unsigned __int8 *)v30;
          if ( !v30 )
          {
            inited = 7;
            goto LABEL_73;
          }
          *(_WORD *)(a1 + 86) = v23;
          inited = accessPayload(a1, 0, (unsigned int)v29, v30, 0);
          *(_OWORD *)&v31[v29] = 0;
          *(_WORD *)&v31[v29 + 16] = 0;
          *(_BYTE *)(a1 + 1) &= ~4u;
          if ( inited )
          {
            sqlite3_free(v31);
            goto LABEL_73;
          }
          v26 = sqlite3VdbeRecordCompareWithSkip(v29, v31, a2, 0);
          sqlite3_free(v31);
          v6 = a2;
        }
        else
        {
          v26 = ((__int64 (__fastcall *)(__int64, unsigned __int8 *, __int64 *))v12)(v28, v24 + 2, v6);
        }
      }
      else
      {
        v26 = ((__int64 (__fastcall *)(__int64, unsigned __int8 *, __int64 *))v12)(v25, v24 + 1, v6);
      }
      if ( v26 >= 0 )
      {
        if ( v26 <= 0 )
        {
          inited = 0;
          *a3 = 0;
          *(_WORD *)(a1 + 86) = v23;
          if ( *((_BYTE *)v6 + 31) )
          {
            v41 = 76656;
            goto LABEL_72;
          }
          goto LABEL_73;
        }
        v21 = v23 - 1;
      }
      else
      {
        v20 = v23 + 1;
      }
      if ( v20 > v21 )
      {
        if ( *(_BYTE *)(v19 + 8) )
        {
          *(_WORD *)(a1 + 86) = v23;
          *a3 = v26;
          inited = 0;
          goto LABEL_73;
        }
        if ( v20 < *(unsigned __int16 *)(v19 + 24) )
          v33 = *(_DWORD *)((unsigned __int16)(*(_WORD *)(v19 + 26)
                                             & __ROR2__(*(_WORD *)(2 * v20 + *(_QWORD *)(v19 + 96)), 8))
                          + *(_QWORD *)(v19 + 80));
        else
          v33 = *(_DWORD *)(*(unsigned __int8 *)(v19 + 9) + *(_QWORD *)(v19 + 80) + 8LL);
        *(_BYTE *)(a1 + 1) &= 0xF9u;
        v34 = *(char *)(a1 + 84);
        *(_WORD *)(a1 + 70) = 0;
        v35 = _byteswap_ulong(v33);
        if ( (char)v34 >= 19 )
        {
          sqlite3_log(
            11,
            "%s at line %d of [%.10s]",
            "database corruption",
            76687,
            "96c92aba00c8375bc32fafcdf12429c58bd8aabfcadab6683e35bbb9cdebf19e");
          return 11;
        }
        *(_WORD *)(a1 + 2 * v34 + 88) = v20;
        v36 = *(char *)(a1 + 84);
        v37 = *(_QWORD *)(a1 + 136);
        v45 = 0;
        *(_QWORD *)(a1 + 8 * v36 + 144) = v37;
        v38 = *(_QWORD *)(a1 + 32);
        ++*(_BYTE *)(a1 + 84);
        *(_WORD *)(a1 + 86) = 0;
        if ( v35 > *(_DWORD *)(v38 + 64) )
        {
          *(_QWORD *)(a1 + 136) = 0;
          sqlite3_log(
            11,
            "%s at line %d of [%.10s]",
            "database corruption",
            72925,
            "96c92aba00c8375bc32fafcdf12429c58bd8aabfcadab6683e35bbb9cdebf19e");
          inited = 11;
          goto LABEL_64;
        }
        inited = sqlite3PagerGet(*(_QWORD *)v38, v35, &v45, *(unsigned __int8 *)(a1 + 2));
        if ( inited )
          goto LABEL_62;
        v39 = *(_QWORD *)(v45 + 16);
        if ( !*(_BYTE *)v39 )
        {
          btreePageFromDbPage(v45, v35, v38);
          inited = btreeInitPage(v39);
          if ( inited )
          {
            sqlite3PagerUnrefNotNull(*(_QWORD *)(v39 + 112));
LABEL_62:
            *(_QWORD *)(a1 + 136) = 0;
LABEL_64:
            v40 = *(char *)(a1 + 84);
            *(_BYTE *)(a1 + 84) = v40 - 1;
            *(_QWORD *)(a1 + 136) = *(_QWORD *)(a1 + 8 * v40 + 136);
            goto LABEL_73;
          }
        }
        *(_QWORD *)(a1 + 136) = v39;
        if ( !*(_WORD *)(v39 + 24) || (v12 = v42, *(_BYTE *)(v39 + 1) != *(_BYTE *)(a1 + 85)) )
        {
          sqlite3PagerUnrefNotNull(*(_QWORD *)(v39 + 112));
          inited = sqlite3ReportError(11, 76698, "database corruption");
          if ( !inited )
          {
            v12 = v42;
            goto LABEL_31;
          }
          goto LABEL_64;
        }
        goto LABEL_31;
      }
      v12 = v42;
    }
  }
  v18 = *(_BYTE **)(a1 + 136);
  *(_BYTE *)(a1 + 1) &= ~4u;
  if ( *v18 )
    goto LABEL_31;
  return sqlite3ReportError(11, 76537, "database corruption");
}

```

## disassembly

```asm
0x180010de0  mov     [rsp+arg_10], r8
0x180010de5  mov     [rsp+arg_8], rdx
0x180010dea  push    rbx
0x180010deb  push    rdi
0x180010dec  push    r12
0x180010dee  push    r13
0x180010df0  sub     rsp, 58h
0x180010df4  mov     rbx, rcx
0x180010df7  mov     r13, r8
0x180010dfa  mov     rcx, [rdx]
0x180010dfd  mov     r12, rdx
0x180010e00  cmp     word ptr [rcx+8], 0Dh
0x180010e05  ja      short loc_180010E77
0x180010e07  mov     rax, [rcx+18h]
0x180010e0b  movzx   r9d, byte ptr [rax]
0x180010e0f  test    r9b, r9b
0x180010e12  jz      short loc_180010E21
0x180010e14  test    r9b, 2
0x180010e18  jnz     short loc_180010E77
0x180010e1a  mov     al, 0FFh
0x180010e1c  mov     r8b, 1
0x180010e1f  jmp     short loc_180010E26
0x180010e21  mov     al, 1
0x180010e23  mov     r8b, 0FFh
0x180010e26  mov     rdx, [rdx+8]
0x180010e2a  movzx   r9d, word ptr [rdx+14h]
0x180010e2f  mov     [r12+20h], r8b
0x180010e34  mov     [r12+21h], al
0x180010e39  test    r9b, 4
0x180010e3d  jz      short loc_180010E50
0x180010e3f  mov     rax, [rdx]
0x180010e42  lea     rdi, vdbeRecordCompareInt
0x180010e49  mov     [r12+10h], rax
0x180010e4e  jmp     short loc_180010E7E
0x180010e50  test    r9b, 39h
0x180010e54  jnz     short loc_180010E77
0x180010e56  cmp     qword ptr [rcx+20h], 0
0x180010e5b  jnz     short loc_180010E77
0x180010e5d  mov     rax, [rdx+8]
0x180010e61  lea     rdi, vdbeRecordCompareString
0x180010e68  mov     [r12+10h], rax
0x180010e6d  mov     eax, [rdx+10h]
0x180010e70  mov     [r12+18h], eax
0x180010e75  jmp     short loc_180010E7E
0x180010e77  lea     rdi, sqlite3VdbeRecordCompare
0x180010e7e  mov     byte ptr [r12+1Fh], 0
0x180010e84  cmp     byte ptr [rbx], 0
0x180010e87  mov     [rsp+78h+arg_0], rdi
0x180010e8f  jnz     loc_180010F5A
0x180010e95  mov     r9, [rbx+88h]
0x180010e9c  cmp     byte ptr [r9+8], 0
0x180010ea1  jz      loc_180010F5A
0x180010ea7  movsx   r10d, byte ptr [rbx+54h]
0x180010eac  xor     r8d, r8d
0x180010eaf  cmp     r8d, r10d
0x180010eb2  jge     short loc_180010ED3
0x180010eb4  movsxd  rdx, r8d
0x180010eb7  mov     rax, [rbx+rdx*8+90h]
0x180010ebf  movzx   ecx, word ptr [rax+18h]
0x180010ec3  cmp     [rbx+rdx*2+58h], cx
0x180010ec8  jb      loc_180010F5A
0x180010ece  inc     r8d
0x180010ed1  jmp     short loc_180010EAF
0x180010ed3  movzx   eax, word ptr [r9+18h]
0x180010ed8  movzx   edx, word ptr [rbx+56h]
0x180010edc  dec     eax
0x180010ede  cmp     edx, eax
0x180010ee0  jnz     short loc_180010F07
0x180010ee2  mov     r9, rdi
0x180010ee5  mov     r8, r12
0x180010ee8  mov     rcx, rbx
0x180010eeb  call    indexCellCompare
0x180010ef0  test    eax, eax
0x180010ef2  jg      short loc_180010F07
0x180010ef4  cmp     byte ptr [r12+1Fh], 0
0x180010efa  jnz     short loc_180010F07
0x180010efc  mov     [r13+0], eax
0x180010f00  xor     eax, eax
0x180010f02  jmp     loc_180011354
0x180010f07  cmp     byte ptr [rbx+54h], 0
0x180010f0b  jle     short loc_180010F54
0x180010f0d  mov     r9, rdi
0x180010f10  mov     r8, r12
0x180010f13  xor     edx, edx
0x180010f15  mov     rcx, rbx
0x180010f18  call    indexCellCompare
0x180010f1d  test    eax, eax
0x180010f1f  jg      short loc_180010F54
0x180010f21  cmp     byte ptr [r12+1Fh], 0
0x180010f27  jnz     short loc_180010F54
0x180010f29  mov     rax, [rbx+88h]
0x180010f30  and     byte ptr [rbx+1], 0FBh
0x180010f34  cmp     byte ptr [rax], 0
0x180010f37  jnz     short loc_180010F7E
0x180010f39  lea     r8, aDatabaseCorrup; "database corruption"
0x180010f40  mov     edx, 12AF9h
0x180010f45  mov     ecx, 0Bh
0x180010f4a  call    sqlite3ReportError
0x180010f4f  jmp     loc_180011354
0x180010f54  mov     byte ptr [r12+1Fh], 0
0x180010f5a  mov     rcx, rbx
0x180010f5d  call    moveToRoot
0x180010f62  test    eax, eax
0x180010f64  jz      short loc_180010F7E
0x180010f66  cmp     eax, 10h
0x180010f69  jnz     loc_180011354
0x180010f6f  mov     dword ptr [r13+0], 0FFFFFFFFh
0x180010f77  xor     eax, eax
0x180010f79  jmp     loc_180011354
0x180010f7e  mov     [rsp+78h+var_28], rbp
0x180010f83  mov     [rsp+78h+var_30], rsi
0x180010f88  mov     [rsp+78h+var_38], r14
0x180010f8d  mov     [rsp+78h+var_40], r15
0x180010f92  nop     dword ptr [rax+00h]
0x180010f96  nop     word ptr [rax+rax+00000000h]
0x180010fa0  mov     rsi, [rbx+88h]
0x180010fa7  xor     r14d, r14d
0x180010faa  movzx   r15d, word ptr [rsi+18h]
0x180010faf  dec     r15d
0x180010fb2  mov     ebp, r15d
0x180010fb5  sar     ebp, 1
0x180010fb7  lea     eax, ds:0[rbp*2]
0x180010fbe  movsxd  rcx, eax
0x180010fc1  mov     rax, [rsi+60h]
0x180010fc5  movzx   edx, word ptr [rcx+rax]
0x180010fc9  movzx   eax, word ptr [rsi+1Ah]
0x180010fcd  ror     dx, 8
0x180010fd1  movzx   edx, dx
0x180010fd4  and     rdx, rax
0x180010fd7  movzx   eax, byte ptr [rsi+0Bh]
0x180010fdb  add     rdx, [rsi+68h]
0x180010fdf  movzx   ecx, byte ptr [rdx]
0x180010fe2  cmp     ecx, eax
0x180010fe4  ja      short loc_180010FFB
0x180010fe6  mov     r8, r12
0x180010fe9  inc     rdx
0x180010fec  mov     rax, rdi
0x180010fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ff4  mov     edi, eax
0x180010ff6  jmp     loc_1800110E1
0x180010ffb  movzx   eax, byte ptr [rdx+1]
0x180010fff  test    al, al
0x180011001  js      short loc_180011029
0x180011003  and     ecx, 7Fh
0x180011006  shl     ecx, 7
0x180011009  add     ecx, eax
0x18001100b  movzx   eax, word ptr [rsi+0Eh]
0x18001100f  cmp     ecx, eax
0x180011011  ja      short loc_180011029
0x180011013  add     rdx, 2
0x180011017  mov     r8, r12
0x18001101a  mov     rax, rdi
0x18001101d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011022  mov     edi, eax
0x180011024  jmp     loc_1800110E1
0x180011029  movzx   eax, byte ptr [rsi+0Ah]
0x18001102d  lea     r8, [rbx+30h]
0x180011031  sub     rdx, rax
0x180011034  mov     rcx, rsi
0x180011037  mov     rax, [rsi+80h]
0x18001103e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011043  movsxd  r13, dword ptr [rbx+30h]
0x180011047  cmp     r13d, 2
0x18001104b  jl      loc_180011320
0x180011051  mov     rcx, [rbx+20h]
0x180011055  xor     edx, edx
0x180011057  mov     eax, r13d
0x18001105a  div     dword ptr [rcx+38h]
0x18001105d  cmp     eax, [rcx+40h]
0x180011060  ja      loc_180011320
0x180011066  lea     eax, [r13+12h]
0x18001106a  movsxd  rcx, eax
0x18001106d  call    sqlite3Malloc
0x180011072  mov     r12, rax
0x180011075  test    rax, rax
0x180011078  jz      loc_180011319
0x18001107e  mov     r9, rax
0x180011081  mov     [rbx+56h], bp
0x180011085  mov     r8d, r13d
0x180011088  mov     dword ptr [rsp+78h+var_58], 0
0x180011090  xor     edx, edx
0x180011092  mov     rcx, rbx
0x180011095  call    accessPayload
0x18001109a  mov     edi, eax
0x18001109c  xorps   xmm0, xmm0
0x18001109f  xor     eax, eax
0x1800110a1  movups  xmmword ptr [r13+r12+0], xmm0
0x1800110a7  mov     [r13+r12+10h], ax
0x1800110ad  and     byte ptr [rbx+1], 0FBh
0x1800110b1  test    edi, edi
0x1800110b3  jnz     loc_18001130F
0x1800110b9  mov     r8, [rsp+78h+arg_8]
0x1800110c1  xor     r9d, r9d
0x1800110c4  mov     rdx, r12
0x1800110c7  mov     ecx, r13d
0x1800110ca  call    sqlite3VdbeRecordCompareWithSkip
0x1800110cf  mov     rcx, r12
0x1800110d2  mov     edi, eax
0x1800110d4  call    sqlite3_free
0x1800110d9  mov     r12, [rsp+78h+arg_8]
0x1800110e1  test    edi, edi
0x1800110e3  jns     short loc_1800110EB
0x1800110e5  lea     r14d, [rbp+1]
0x1800110e9  jmp     short loc_1800110F5
0x1800110eb  jle     loc_1800112ED
0x1800110f1  lea     r15d, [rbp-1]
0x1800110f5  cmp     r14d, r15d
0x1800110f8  jg      short loc_18001110B
0x1800110fa  mov     rdi, [rsp+78h+arg_0]
0x180011102  lea     ebp, [r15+r14]
0x180011106  jmp     loc_180010FB5
0x18001110b  cmp     byte ptr [rsi+8], 0
0x18001110f  jnz     loc_1800112DB
0x180011115  movzx   eax, word ptr [rsi+18h]
0x180011119  cmp     r14d, eax
0x18001111c  jl      short loc_18001112C
0x18001111e  movzx   ecx, byte ptr [rsi+9]
0x180011122  mov     rax, [rsi+50h]
0x180011126  mov     esi, [rcx+rax+8]
0x18001112a  jmp     short loc_180011150
0x18001112c  lea     eax, [r14+r14]
0x180011130  movsxd  rcx, eax
0x180011133  mov     rax, [rsi+60h]
0x180011137  movzx   edx, word ptr [rcx+rax]
0x18001113b  movzx   eax, word ptr [rsi+1Ah]
0x18001113f  ror     dx, 8
0x180011143  movzx   ecx, dx
0x180011146  and     rcx, rax
0x180011149  mov     rax, [rsi+50h]
0x18001114d  mov     esi, [rcx+rax]
0x180011150  and     byte ptr [rbx+1], 0F9h
0x180011154  xor     edx, edx
0x180011156  movsx   rax, byte ptr [rbx+54h]
0x18001115b  mov     [rbx+46h], dx
0x18001115f  bswap   esi
0x180011161  cmp     al, 13h
0x180011163  jge     loc_1800112AA
0x180011169  mov     [rbx+rax*2+58h], r14w
0x18001116f  movsx   rcx, byte ptr [rbx+54h]
0x180011174  mov     rax, [rbx+88h]
0x18001117b  mov     [rsp+78h+arg_18], rdx
0x180011183  mov     [rbx+rcx*8+90h], rax
0x18001118b  mov     r14, [rbx+20h]
0x18001118f  inc     byte ptr [rbx+54h]
0x180011192  mov     [rbx+56h], dx
0x180011196  cmp     esi, [r14+40h]
0x18001119a  ja      loc_180011255
0x1800111a0  movzx   r9d, byte ptr [rbx+2]
0x1800111a5  lea     r8, [rsp+78h+arg_18]
0x1800111ad  mov     rcx, [r14]
0x1800111b0  mov     edx, esi
0x1800111b2  call    sqlite3PagerGet
0x1800111b7  mov     edi, eax
0x1800111b9  test    eax, eax
0x1800111bb  jnz     loc_180011248
0x1800111c1  mov     rcx, [rsp+78h+arg_18]
0x1800111c9  mov     rbp, [rcx+10h]
0x1800111cd  cmp     [rbp+0], al
0x1800111d0  jnz     short loc_1800111EA
0x1800111d2  mov     r8, r14
0x1800111d5  mov     edx, esi
0x1800111d7  call    btreePageFromDbPage
0x1800111dc  mov     rcx, rbp
0x1800111df  call    btreeInitPage
0x1800111e4  mov     edi, eax
0x1800111e6  test    eax, eax
0x1800111e8  jnz     short loc_18001123F
0x1800111ea  mov     [rbx+88h], rbp
0x1800111f1  cmp     word ptr [rbp+18h], 1
0x1800111f6  jb      short loc_18001120D
0x1800111f8  movzx   eax, byte ptr [rbx+55h]
0x1800111fc  mov     rdi, [rsp+78h+arg_0]
0x180011204  cmp     [rbp+1], al
0x180011207  jz      loc_180010FA0
0x18001120d  mov     rcx, [rbp+70h]
0x180011211  call    sqlite3PagerUnrefNotNull
0x180011216  lea     r8, aDatabaseCorrup; "database corruption"
0x18001121d  mov     edx, 12B9Ah
0x180011222  mov     ecx, 0Bh
0x180011227  call    sqlite3ReportError
0x18001122c  mov     edi, eax
0x18001122e  test    eax, eax
0x180011230  jnz     short loc_18001128B
0x180011232  mov     rdi, [rsp+78h+arg_0]
0x18001123a  jmp     loc_180010FA0
0x18001123f  mov     rcx, [rbp+70h]
0x180011243  call    sqlite3PagerUnrefNotNull
0x180011248  mov     qword ptr [rbx+88h], 0
0x180011253  jmp     short loc_18001128B
0x180011255  mov     [rbx+88h], rdx
0x18001125c  lea     rax, a20240523132527+14h; "96c92aba00c8375bc32fafcdf12429c58bd8aab"...
0x180011263  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x18001126a  mov     [rsp+78h+var_58], rax
0x18001126f  mov     r9d, 11CDDh
0x180011275  lea     r8, aDatabaseCorrup; "database corruption"
0x18001127c  mov     ecx, 0Bh
0x180011281  call    sqlite3_log
0x180011286  mov     edi, 0Bh
0x18001128b  movsx   rcx, byte ptr [rbx+54h]
0x180011290  lea     eax, [rcx-1]
  ... truncated ...
```
