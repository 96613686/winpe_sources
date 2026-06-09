# sqlite3BtreeIndexMoveto

- ea: `0x180025a20`
- end: `0x180026194`
- name: `sqlite3BtreeIndexMoveto`
- size: `1908`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800286a4`
- `0x180035468`
- `0x18003d990`

## callees

- `0x180022a7c`
- `0x180024640`
- `0x1800257e0`
- `0x180025a20`
- `0x18002619c`
- `0x18002625c`
- `0x180027340`
- `0x180033ab0`
- `0x180035150`
- `0x180038a0c`
- `0x180038d00`
- `0x180041eb0`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeIndexMoveto(__int64 a1, _QWORD *a2, int *a3)
{
  __int64 v5; // rcx
  _QWORD *v6; // rbp
  char v7; // r9
  char v8; // al
  char v9; // r8
  __int64 v10; // rdx
  __int16 v11; // r9
  __int64 (__fastcall *v12)(); // rdi
  __int64 v13; // r10
  int i; // r8d
  __int64 result; // rax
  unsigned int inited; // edi
  int v17; // ecx
  __int64 v18; // r8
  unsigned __int8 *v19; // rdx
  __int64 v20; // rcx
  unsigned __int8 *v21; // rdx
  _BYTE *v22; // rax
  __int64 v23; // rsi
  int v24; // r12d
  int v25; // r15d
  int j; // r14d
  int v27; // r14d
  unsigned __int8 *v28; // rdx
  __int64 v29; // rcx
  int v30; // edi
  int v31; // eax
  __int64 v32; // rcx
  unsigned int v33; // esi
  __int64 v34; // rax
  unsigned __int32 v35; // esi
  __int64 v36; // rcx
  __int64 v37; // rax
  _DWORD *v38; // r14
  __int64 v39; // rcx
  __int64 v40; // rbp
  __int64 v41; // rcx
  __int64 v42; // r13
  __int64 v43; // rcx
  __int64 v44; // rdx
  char *v45; // rbp
  unsigned __int8 *v46; // rdx
  __int64 v47; // rcx
  unsigned __int8 *v48; // rdx
  int v49; // eax
  char v50; // al
  __int64 v51; // rcx
  int v52; // eax
  int v53; // eax
  int v54; // eax
  __int64 (__fastcall *v55)(); // [rsp+80h] [rbp+8h]
  __int64 v58; // [rsp+98h] [rbp+20h] BYREF

  v5 = *a2;
  v6 = a2;
  if ( *(_WORD *)(*a2 + 8LL) > 0xDu )
    goto LABEL_16;
  v7 = **(_BYTE **)(v5 + 24);
  if ( !v7 )
  {
    v8 = 1;
    v9 = -1;
    goto LABEL_4;
  }
  if ( (v7 & 2) != 0 )
  {
LABEL_16:
    v12 = sqlite3VdbeRecordCompare;
    goto LABEL_6;
  }
  v8 = -1;
  v9 = 1;
LABEL_4:
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
      goto LABEL_6;
    }
    goto LABEL_16;
  }
  v12 = vdbeRecordCompareInt;
  v6[2] = *(_QWORD *)v10;
LABEL_6:
  *((_BYTE *)v6 + 31) = 0;
  v55 = v12;
  if ( !*(_BYTE *)a1 )
  {
    v13 = *(_QWORD *)(a1 + 136);
    if ( *(_BYTE *)(v13 + 8) )
    {
      for ( i = 0; i < *(char *)(a1 + 84); ++i )
      {
        if ( *(_WORD *)(a1 + 2LL * i + 88) < *(_WORD *)(*(_QWORD *)(a1 + 8LL * i + 144) + 24LL) )
          goto LABEL_12;
      }
      v17 = *(unsigned __int16 *)(a1 + 86);
      if ( v17 == *(unsigned __int16 *)(v13 + 24) - 1 )
      {
        v46 = (unsigned __int8 *)(*(_QWORD *)(v13 + 104)
                                + (unsigned __int16)(*(_WORD *)(v13 + 26)
                                                   & __ROR2__(
                                                       *(_WORD *)((unsigned int)(2 * v17) + *(_QWORD *)(v13 + 96)),
                                                       8)));
        v47 = *v46;
        if ( (unsigned int)v47 > *(unsigned __int8 *)(v13 + 11) )
        {
          v53 = v46[1];
          if ( (v53 & 0x80u) != 0 )
            goto LABEL_25;
          v47 = v53 + ((unsigned __int8)(v47 & 0x7F) << 7);
          if ( (unsigned int)v47 > *(unsigned __int16 *)(v13 + 14) )
            goto LABEL_25;
          v48 = v46 + 2;
        }
        else
        {
          v48 = v46 + 1;
        }
        v49 = ((__int64 (__fastcall *)(__int64, unsigned __int8 *, _QWORD *))v12)(v47, v48, v6);
        if ( v49 <= 0 && !*((_BYTE *)v6 + 31) )
        {
          *a3 = v49;
          return 0;
        }
      }
LABEL_25:
      if ( *(char *)(a1 + 84) > 0 )
      {
        v18 = *(_QWORD *)(a1 + 136);
        v19 = (unsigned __int8 *)(*(_QWORD *)(v18 + 104)
                                + (unsigned __int16)(*(_WORD *)(v18 + 26) & __ROR2__(**(_WORD **)(v18 + 96), 8)));
        v20 = *v19;
        if ( (unsigned int)v20 <= *(unsigned __int8 *)(v18 + 11) )
        {
          v21 = v19 + 1;
LABEL_28:
          if ( ((int (__fastcall *)(__int64, unsigned __int8 *, _QWORD *))v12)(v20, v21, v6) <= 0
            && !*((_BYTE *)v6 + 31) )
          {
            v22 = *(_BYTE **)(a1 + 136);
            *(_BYTE *)(a1 + 1) &= ~4u;
            if ( *v22 )
              goto LABEL_31;
            return sqlite3ReportError(11, 76787, "database corruption");
          }
          goto LABEL_89;
        }
        v52 = v19[1];
        if ( (v52 & 0x80u) == 0 )
        {
          v20 = v52 + ((unsigned __int8)(v20 & 0x7F) << 7);
          if ( (unsigned int)v20 <= *(unsigned __int16 *)(v18 + 14) )
          {
            v21 = v19 + 2;
            goto LABEL_28;
          }
        }
      }
LABEL_89:
      *((_BYTE *)v6 + 31) = 0;
    }
  }
LABEL_12:
  result = moveToRoot(a1);
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result == 16 )
    {
      *a3 = -1;
      return 0;
    }
  }
  else
  {
    while ( 1 )
    {
LABEL_31:
      v23 = *(_QWORD *)(a1 + 136);
      v24 = 0;
      v25 = *(unsigned __int16 *)(v23 + 24) - 1;
      for ( j = v25; ; j = v25 + v24 )
      {
        v27 = j >> 1;
        v28 = (unsigned __int8 *)(*(_QWORD *)(v23 + 104)
                                + (unsigned __int16)(*(_WORD *)(v23 + 26)
                                                   & __ROR2__(*(_WORD *)(2 * v27 + *(_QWORD *)(v23 + 96)), 8)));
        v29 = *v28;
        if ( (unsigned int)v29 > *(unsigned __int8 *)(v23 + 11) )
        {
          v31 = v28[1];
          if ( (v31 & 0x80u) != 0
            || (v32 = v31 + ((unsigned __int8)(v29 & 0x7F) << 7), (unsigned int)v32 > *(unsigned __int16 *)(v23 + 14)) )
          {
            (*(void (__fastcall **)(__int64, unsigned __int8 *, __int64))(v23 + 128))(
              v23,
              &v28[-*(unsigned __int8 *)(v23 + 10)],
              a1 + 48);
            v42 = *(int *)(a1 + 48);
            if ( (int)v42 < 2
              || (v43 = *(_QWORD *)(a1 + 32),
                  v44 = (unsigned int)v42 % *(_DWORD *)(v43 + 56),
                  (unsigned int)v42 / *(_DWORD *)(v43 + 56) > *(_DWORD *)(v43 + 64)) )
            {
              sqlite3_log(
                11,
                "%s at line %d of [%.10s]",
                "database corruption",
                76874,
                "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
              inited = 11;
              goto LABEL_18;
            }
            v45 = 0;
            v58 = 0;
            if ( (unsigned int)(v42 + 17) <= 0x7FFFFEFE )
            {
              if ( dword_1800D0870 )
              {
                sqlite3_mutex_enter(xmmword_1800D0D78);
                mallocWithAlarm((unsigned int)(v42 + 18), &v58);
                sqlite3_mutex_leave(xmmword_1800D0D78);
                v45 = (char *)v58;
              }
              else
              {
                v45 = (char *)((__int64 (__fastcall *)(_QWORD, __int64))qword_1800D0890)((unsigned int)(v42 + 18), v44);
              }
            }
            if ( !v45 )
            {
              inited = 7;
              goto LABEL_18;
            }
            *(_WORD *)(a1 + 86) = v27;
            inited = accessPayload(a1, 0, v42, v45, 0);
            *(_OWORD *)&v45[v42] = 0;
            *(_WORD *)&v45[v42 + 16] = 0;
            *(_BYTE *)(a1 + 1) &= ~4u;
            if ( inited )
            {
              sqlite3_free(v45);
              goto LABEL_18;
            }
            v30 = sqlite3VdbeRecordCompareWithSkip((unsigned int)v42, v45, a2, 0);
            if ( dword_1800D0870 )
            {
              sqlite3_mutex_enter(xmmword_1800D0D78);
              v54 = ((__int64 (__fastcall *)(char *))xmmword_1800D08A8)(v45);
              --qword_1800D0E38;
              qword_1800D0DF0 -= v54;
              ((void (__fastcall *)(char *))xmmword_1800D0898)(v45);
              sqlite3_mutex_leave(xmmword_1800D0D78);
            }
            else
            {
              ((void (__fastcall *)(char *))xmmword_1800D0898)(v45);
            }
            v6 = a2;
          }
          else
          {
            v30 = ((__int64 (__fastcall *)(__int64, unsigned __int8 *, _QWORD *))v12)(v32, v28 + 2, v6);
          }
        }
        else
        {
          v30 = ((__int64 (__fastcall *)(__int64, unsigned __int8 *, _QWORD *))v12)(v29, v28 + 1, v6);
        }
        if ( v30 >= 0 )
        {
          if ( v30 <= 0 )
          {
            inited = 0;
            *a3 = 0;
            *(_WORD *)(a1 + 86) = v27;
            if ( *((_BYTE *)v6 + 31) )
              inited = sqlite3ReportError(11, 76906, "database corruption");
            goto LABEL_18;
          }
          v25 = v27 - 1;
        }
        else
        {
          v24 = v27 + 1;
        }
        if ( v24 > v25 )
          break;
        v12 = v55;
      }
      if ( *(_BYTE *)(v23 + 8) )
      {
        *(_WORD *)(a1 + 86) = v27;
        *a3 = v30;
        inited = 0;
        goto LABEL_18;
      }
      v33 = v24 >= *(unsigned __int16 *)(v23 + 24)
          ? *(_DWORD *)(*(unsigned __int8 *)(v23 + 9) + *(_QWORD *)(v23 + 80) + 8LL)
          : *(_DWORD *)((unsigned __int16)(*(_WORD *)(v23 + 26)
                                         & __ROR2__(*(_WORD *)(2 * v24 + *(_QWORD *)(v23 + 96)), 8))
                      + *(_QWORD *)(v23 + 80));
      *(_BYTE *)(a1 + 1) &= 0xF9u;
      v34 = *(char *)(a1 + 84);
      *(_WORD *)(a1 + 70) = 0;
      v35 = _byteswap_ulong(v33);
      if ( (char)v34 >= 19 )
        return sqlite3ReportError(11, 76937, "database corruption");
      *(_WORD *)(a1 + 2 * v34 + 88) = v24;
      v36 = *(char *)(a1 + 84);
      v37 = *(_QWORD *)(a1 + 136);
      v58 = 0;
      *(_QWORD *)(a1 + 8 * v36 + 144) = v37;
      v38 = *(_DWORD **)(a1 + 32);
      ++*(_BYTE *)(a1 + 84);
      *(_WORD *)(a1 + 86) = 0;
      if ( v35 > v38[16] )
      {
        *(_QWORD *)(a1 + 136) = 0;
        inited = sqlite3ReportError(11, 73175, "database corruption");
        if ( inited )
          goto LABEL_79;
      }
      else
      {
        inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v38 + 272LL))(
                   *(_QWORD *)v38,
                   v35,
                   &v58,
                   *(unsigned __int8 *)(a1 + 2));
        if ( inited )
          goto LABEL_78;
        v39 = v58;
        v40 = *(_QWORD *)(v58 + 16);
        if ( !*(_BYTE *)v40 )
        {
          if ( v35 != *(_DWORD *)(v40 + 4) )
          {
            *(_QWORD *)(v40 + 80) = *(_QWORD *)(v58 + 8);
            v50 = 100;
            if ( v35 != 1 )
              v50 = 0;
            *(_QWORD *)(v40 + 112) = v39;
            *(_BYTE *)(v40 + 9) = v50;
            *(_QWORD *)(v40 + 72) = v38;
            *(_DWORD *)(v40 + 4) = v35;
          }
          inited = btreeInitPage(v40);
          if ( inited )
          {
            releasePage(v40);
LABEL_78:
            *(_QWORD *)(a1 + 136) = 0;
LABEL_79:
            v51 = *(char *)(a1 + 84);
            *(_BYTE *)(a1 + 84) = v51 - 1;
            *(_QWORD *)(a1 + 136) = *(_QWORD *)(a1 + 8 * v51 + 136);
LABEL_18:
            *(_WORD *)(a1 + 70) = 0;
            return inited;
          }
        }
        *(_QWORD *)(a1 + 136) = v40;
      }
      v41 = *(_QWORD *)(a1 + 136);
      if ( *(_WORD *)(v41 + 24) )
      {
        v6 = a2;
        v12 = v55;
        if ( *(_BYTE *)(v41 + 1) == *(_BYTE *)(a1 + 85) )
          continue;
      }
      releasePage(v41);
      inited = sqlite3ReportError(11, 76948, "database corruption");
      if ( inited )
        goto LABEL_79;
      v6 = a2;
      v12 = v55;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180025a20  mov     [rsp+arg_10], r8
0x180025a25  mov     [rsp+arg_8], rdx
0x180025a2a  push    rbx
0x180025a2b  push    rbp
0x180025a2c  push    rsi
0x180025a2d  push    rdi
0x180025a2e  sub     rsp, 58h
0x180025a32  mov     rbx, rcx
0x180025a35  mov     rsi, r8
0x180025a38  mov     rcx, [rdx]
0x180025a3b  mov     rbp, rdx
0x180025a3e  cmp     word ptr [rcx+8], 0Dh
0x180025a43  ja      loc_180025B02
0x180025a49  mov     rax, [rcx+18h]
0x180025a4d  movzx   r9d, byte ptr [rax]
0x180025a51  test    r9b, r9b
0x180025a54  jnz     loc_180025AFC
0x180025a5a  mov     al, 1
0x180025a5c  mov     r8b, 0FFh
0x180025a5f  mov     rdx, [rdx+8]
0x180025a63  movzx   r9d, word ptr [rdx+14h]
0x180025a68  mov     [rbp+20h], r8b
0x180025a6c  mov     [rbp+21h], al
0x180025a6f  test    r9b, 4
0x180025a73  jz      loc_180025B47
0x180025a79  mov     rax, [rdx]
0x180025a7c  lea     rdi, vdbeRecordCompareInt
0x180025a83  mov     [rbp+10h], rax
0x180025a87  mov     byte ptr [rbp+1Fh], 0
0x180025a8b  cmp     byte ptr [rbx], 0
0x180025a8e  mov     [rsp+78h+arg_0], rdi
0x180025a96  mov     [rsp+78h+var_30], r13
0x180025a9b  jnz     short loc_180025ADA
0x180025a9d  mov     r10, [rbx+88h]
0x180025aa4  cmp     byte ptr [r10+8], 0
0x180025aa9  jz      short loc_180025ADA
0x180025aab  movsx   r9d, byte ptr [rbx+54h]
0x180025ab0  xor     r13d, r13d
0x180025ab3  mov     r8d, r13d
0x180025ab6  cmp     r8d, r9d
0x180025ab9  jge     loc_180025B78
0x180025abf  movsxd  rdx, r8d
0x180025ac2  mov     rax, [rbx+rdx*8+90h]
0x180025aca  movzx   ecx, word ptr [rax+18h]
0x180025ace  cmp     [rbx+rdx*2+58h], cx
0x180025ad3  jb      short loc_180025ADD
0x180025ad5  inc     r8d
0x180025ad8  jmp     short loc_180025AB6
0x180025ada  xor     r13d, r13d
0x180025add  mov     rcx, rbx
0x180025ae0  call    moveToRoot
0x180025ae5  test    eax, eax
0x180025ae7  jz      loc_180025BFA
0x180025aed  cmp     eax, 10h
0x180025af0  jnz     short loc_180025B39
0x180025af2  mov     dword ptr [rsi], 0FFFFFFFFh
0x180025af8  xor     eax, eax
0x180025afa  jmp     short loc_180025B39
0x180025afc  test    r9b, 2
0x180025b00  jz      short loc_180025B6E
0x180025b02  lea     rdi, sqlite3VdbeRecordCompare
0x180025b09  jmp     loc_180025A87
0x180025b0e  mov     rax, [rsp+78h+arg_10]
0x180025b16  xor     r13d, r13d
0x180025b19  mov     [rbx+56h], r14w
0x180025b1e  mov     [rax], edi
0x180025b20  mov     edi, r13d
0x180025b23  mov     [rbx+46h], r13w
0x180025b28  mov     eax, edi
0x180025b2a  mov     r14, [rsp+78h+var_38]
0x180025b2f  mov     r12, [rsp+78h+var_28]
0x180025b34  mov     r15, [rsp+78h+var_40]
0x180025b39  mov     r13, [rsp+78h+var_30]
0x180025b3e  add     rsp, 58h
0x180025b42  pop     rdi
0x180025b43  pop     rsi
0x180025b44  pop     rbp
0x180025b45  pop     rbx
0x180025b46  retn
0x180025b47  test    r9b, 39h
0x180025b4b  jnz     short loc_180025B02
0x180025b4d  cmp     qword ptr [rcx+20h], 0
0x180025b52  jnz     short loc_180025B02
0x180025b54  mov     rax, [rdx+8]
0x180025b58  lea     rdi, vdbeRecordCompareString
0x180025b5f  mov     [rbp+10h], rax
0x180025b63  mov     eax, [rdx+10h]
0x180025b66  mov     [rbp+18h], eax
0x180025b69  jmp     loc_180025A87
0x180025b6e  mov     al, 0FFh
0x180025b70  mov     r8b, 1
0x180025b73  jmp     loc_180025A5F
0x180025b78  movzx   eax, word ptr [r10+18h]
0x180025b7d  movzx   ecx, word ptr [rbx+56h]
0x180025b81  dec     eax
0x180025b83  cmp     ecx, eax
0x180025b85  jz      loc_180025F15
0x180025b8b  cmp     [rbx+54h], r13b
0x180025b8f  jle     loc_1800260B4
0x180025b95  mov     r8, [rbx+88h]
0x180025b9c  mov     rax, [r8+60h]
0x180025ba0  movzx   ecx, word ptr [rax]
0x180025ba3  movzx   eax, word ptr [r8+1Ah]
0x180025ba8  ror     cx, 8
0x180025bac  movzx   edx, cx
0x180025baf  and     rdx, rax
0x180025bb2  movzx   eax, byte ptr [r8+0Bh]
0x180025bb7  add     rdx, [r8+68h]
0x180025bbb  movzx   ecx, byte ptr [rdx]
0x180025bbe  cmp     ecx, eax
0x180025bc0  ja      loc_180025FEC
0x180025bc6  inc     rdx
0x180025bc9  mov     r8, rbp
0x180025bcc  mov     rax, rdi
0x180025bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bd4  test    eax, eax
0x180025bd6  jg      loc_1800260B4
0x180025bdc  cmp     [rbp+1Fh], r13b
0x180025be0  jnz     loc_1800260B4
0x180025be6  mov     rax, [rbx+88h]
0x180025bed  and     byte ptr [rbx+1], 0FBh
0x180025bf1  cmp     [rax], r13b
0x180025bf4  jz      loc_180026147
0x180025bfa  mov     [rsp+78h+var_28], r12
0x180025bff  mov     [rsp+78h+var_38], r14
0x180025c04  mov     [rsp+78h+var_40], r15
0x180025c09  nop     dword ptr [rax+00000000h]
0x180025c10  mov     rsi, [rbx+88h]
0x180025c17  mov     r12d, r13d
0x180025c1a  movzx   r15d, word ptr [rsi+18h]
0x180025c1f  dec     r15d
0x180025c22  mov     r14d, r15d
0x180025c25  sar     r14d, 1
0x180025c28  lea     eax, [r14+r14]
0x180025c2c  movsxd  rcx, eax
0x180025c2f  mov     rax, [rsi+60h]
0x180025c33  movzx   edx, word ptr [rcx+rax]
0x180025c37  movzx   eax, word ptr [rsi+1Ah]
0x180025c3b  ror     dx, 8
0x180025c3f  movzx   edx, dx
0x180025c42  and     rdx, rax
0x180025c45  movzx   eax, byte ptr [rsi+0Bh]
0x180025c49  add     rdx, [rsi+68h]
0x180025c4d  movzx   ecx, byte ptr [rdx]
0x180025c50  cmp     ecx, eax
0x180025c52  ja      short loc_180025C8B
0x180025c54  mov     r8, rbp
0x180025c57  inc     rdx
0x180025c5a  mov     rax, rdi
0x180025c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c62  mov     edi, eax
0x180025c64  test    edi, edi
0x180025c66  jns     short loc_180025C7F
0x180025c68  lea     r12d, [r14+1]
0x180025c6c  cmp     r12d, r15d
0x180025c6f  jg      short loc_180025CBE
0x180025c71  mov     rdi, [rsp+78h+arg_0]
0x180025c79  lea     r14d, [r15+r12]
0x180025c7d  jmp     short loc_180025C25
0x180025c7f  jle     loc_180026016
0x180025c85  lea     r15d, [r14-1]
0x180025c89  jmp     short loc_180025C6C
0x180025c8b  movzx   eax, byte ptr [rdx+1]
0x180025c8f  test    al, al
0x180025c91  js      loc_180025E1E
0x180025c97  and     ecx, 7Fh
0x180025c9a  shl     ecx, 7
0x180025c9d  add     ecx, eax
0x180025c9f  movzx   eax, word ptr [rsi+0Eh]
0x180025ca3  cmp     ecx, eax
0x180025ca5  ja      loc_180025E1E
0x180025cab  add     rdx, 2
0x180025caf  mov     r8, rbp
0x180025cb2  mov     rax, rdi
0x180025cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cba  mov     edi, eax
0x180025cbc  jmp     short loc_180025C64
0x180025cbe  cmp     byte ptr [rsi+8], 0
0x180025cc2  jnz     loc_180025B0E
0x180025cc8  movzx   eax, word ptr [rsi+18h]
0x180025ccc  cmp     r12d, eax
0x180025ccf  jge     loc_180025F74
0x180025cd5  lea     eax, [r12+r12]
0x180025cd9  movsxd  rcx, eax
0x180025cdc  mov     rax, [rsi+60h]
0x180025ce0  movzx   edx, word ptr [rcx+rax]
0x180025ce4  movzx   eax, word ptr [rsi+1Ah]
0x180025ce8  ror     dx, 8
0x180025cec  movzx   ecx, dx
0x180025cef  and     rcx, rax
0x180025cf2  mov     rax, [rsi+50h]
0x180025cf6  mov     esi, [rcx+rax]
0x180025cf9  and     byte ptr [rbx+1], 0F9h
0x180025cfd  xor     r13d, r13d
0x180025d00  movsx   rax, byte ptr [rbx+54h]
0x180025d05  mov     [rbx+46h], r13w
0x180025d0a  bswap   esi
0x180025d0c  cmp     al, 13h
0x180025d0e  jge     loc_180026162
0x180025d14  mov     [rbx+rax*2+58h], r12w
0x180025d1a  movsx   rcx, byte ptr [rbx+54h]
0x180025d1f  mov     rax, [rbx+88h]
0x180025d26  mov     [rsp+78h+arg_18], r13
0x180025d2e  mov     [rbx+rcx*8+90h], rax
0x180025d36  mov     r14, [rbx+20h]
0x180025d3a  inc     byte ptr [rbx+54h]
0x180025d3d  mov     [rbx+56h], r13w
0x180025d42  cmp     esi, [r14+40h]
0x180025d46  ja      short loc_180025D92
0x180025d48  mov     rax, [r14]
0x180025d4b  lea     r8, [rsp+78h+arg_18]
0x180025d53  movzx   r9d, byte ptr [rbx+2]
0x180025d58  mov     rcx, rax
0x180025d5b  mov     edx, esi
0x180025d5d  mov     rax, [rax+110h]
0x180025d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d69  mov     edi, eax
0x180025d6b  test    eax, eax
0x180025d6d  jnz     loc_180025FC6
0x180025d73  mov     rcx, [rsp+78h+arg_18]
0x180025d7b  mov     rbp, [rcx+10h]
0x180025d7f  cmp     [rbp+0], r13b
0x180025d83  jz      loc_180025F85
0x180025d89  mov     [rbx+88h], rbp
0x180025d90  jmp     short loc_180025DB9
0x180025d92  lea     r8, aDatabaseCorrup; "database corruption"
0x180025d99  mov     [rbx+88h], r13
0x180025da0  mov     edx, 11DD7h
0x180025da5  mov     ecx, 0Bh
0x180025daa  call    sqlite3ReportError
0x180025daf  mov     edi, eax
0x180025db1  test    eax, eax
0x180025db3  jnz     loc_180025FCD
0x180025db9  mov     rcx, [rbx+88h]
0x180025dc0  cmp     word ptr [rcx+18h], 1
0x180025dc5  jb      short loc_180025DE4
0x180025dc7  movzx   eax, byte ptr [rbx+55h]
0x180025dcb  mov     rbp, [rsp+78h+arg_8]
0x180025dd3  mov     rdi, [rsp+78h+arg_0]
0x180025ddb  cmp     [rcx+1], al
0x180025dde  jz      loc_180025C10
0x180025de4  call    releasePage
0x180025de9  lea     r8, aDatabaseCorrup; "database corruption"
0x180025df0  mov     edx, 12C94h
0x180025df5  mov     ecx, 0Bh
0x180025dfa  call    sqlite3ReportError
0x180025dff  mov     edi, eax
0x180025e01  test    eax, eax
0x180025e03  jnz     loc_180025FCD
0x180025e09  mov     rbp, [rsp+78h+arg_8]
0x180025e11  mov     rdi, [rsp+78h+arg_0]
0x180025e19  jmp     loc_180025C10
0x180025e1e  movzx   eax, byte ptr [rsi+0Ah]
0x180025e22  lea     r8, [rbx+30h]
0x180025e26  sub     rdx, rax
0x180025e29  mov     rcx, rsi
0x180025e2c  mov     rax, [rsi+80h]
0x180025e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e38  movsxd  r13, dword ptr [rbx+30h]
0x180025e3c  cmp     r13d, 2
0x180025e40  jl      loc_18002607D
0x180025e46  mov     rcx, [rbx+20h]
0x180025e4a  xor     edx, edx
0x180025e4c  mov     eax, r13d
0x180025e4f  div     dword ptr [rcx+38h]
0x180025e52  cmp     eax, [rcx+40h]
0x180025e55  ja      loc_18002607D
0x180025e5b  xor     ebp, ebp
0x180025e5d  lea     eax, [r13+11h]
0x180025e61  mov     [rsp+78h+arg_18], rbp
0x180025e69  cmp     eax, 7FFFFEFEh
0x180025e6e  ja      short loc_180025E8F
0x180025e70  cmp     cs:dword_1800D0870, ebp
0x180025e76  jnz     loc_1800260BD
0x180025e7c  mov     rax, cs:qword_1800D0890
0x180025e83  lea     ecx, [r13+12h]
0x180025e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e8c  mov     rbp, rax
0x180025e8f  test    rbp, rbp
0x180025e92  jz      loc_18002618A
0x180025e98  mov     r9, rbp
0x180025e9b  mov     [rbx+56h], r14w
0x180025ea0  mov     r8d, r13d
0x180025ea3  mov     dword ptr [rsp+78h+var_58], 0
0x180025eab  xor     edx, edx
0x180025ead  mov     rcx, rbx
0x180025eb0  call    accessPayload
0x180025eb5  mov     edi, eax
0x180025eb7  xorps   xmm0, xmm0
0x180025eba  xor     eax, eax
0x180025ebc  movups  xmmword ptr [r13+rbp+0], xmm0
0x180025ec2  mov     [r13+rbp+10h], ax
0x180025ec8  and     byte ptr [rbx+1], 0FBh
0x180025ecc  test    edi, edi
0x180025ece  jnz     loc_18002617D
0x180025ed4  mov     r8, [rsp+78h+arg_8]
0x180025edc  xor     r9d, r9d
0x180025edf  mov     rdx, rbp
0x180025ee2  mov     ecx, r13d
0x180025ee5  call    sqlite3VdbeRecordCompareWithSkip
  ... truncated ...
```
