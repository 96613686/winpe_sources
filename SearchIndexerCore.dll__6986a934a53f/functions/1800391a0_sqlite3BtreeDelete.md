# sqlite3BtreeDelete

- ea: `0x1800391a0`
- end: `0x18003961d`
- name: `sqlite3BtreeDelete`
- size: `1149`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800286a4`

## callees

- `0x18002619c`
- `0x18002625c`
- `0x1800262c0`
- `0x1800266f0`
- `0x180027340`
- `0x180028090`
- `0x1800353b8`
- `0x180036b3c`
- `0x180038d78`
- `0x1800391a0`
- `0x180039798`
- `0x180039ce0`
- `0x18003b900`
- `0x18003d8e4`
- `0x18005dcd0`
- `0x18005f878`
- `0x180076d18`
- `0x1800b0010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeDelete(char *a1, __int64 a2)
{
  __int64 v2; // r14
  char v3; // r15
  unsigned __int8 v5; // al
  unsigned int v6; // ecx
  __int64 v7; // rdi
  __int16 v8; // r12
  __int64 v9; // r13
  __int16 v10; // si
  unsigned __int64 v11; // r13
  _BYTE *v12; // rsi
  char v13; // r12
  __int64 v14; // r15
  int v15; // r8d
  __int64 result; // rax
  unsigned int v17; // eax
  unsigned int v18; // r15d
  int v19; // r14d
  __int64 v20; // rcx
  unsigned int v21; // esi
  __int64 v22; // rsi
  __int64 v23; // r9
  __int64 v24; // r8
  __int16 v25; // dx
  unsigned __int64 v26; // r15
  unsigned int v27; // r13d
  unsigned __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // [rsp+30h] [rbp-20h]
  __int64 v31; // [rsp+30h] [rbp-20h]
  __int128 v32; // [rsp+38h] [rbp-18h] BYREF
  __int64 v33; // [rsp+48h] [rbp-8h]
  char v34; // [rsp+90h] [rbp+40h]
  int v35; // [rsp+90h] [rbp+40h]
  unsigned int inserted; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v37; // [rsp+A8h] [rbp+58h]

  v2 = *((_QWORD *)a1 + 1);
  v3 = a2;
  v30 = *(_QWORD *)(v2 + 8);
  v33 = 0;
  v5 = *a1;
  v32 = 0;
  if ( !v5 )
    goto LABEL_2;
  if ( v5 < 3u )
  {
    v29 = 80543;
    return sqlite3ReportError(11, v29, "database corruption");
  }
  result = btreeRestoreCursorPosition();
  if ( !(_DWORD)result && !*a1 )
  {
LABEL_2:
    v6 = *((unsigned __int16 *)a1 + 43);
    v7 = *((_QWORD *)a1 + 17);
    v37 = v6;
    if ( *(unsigned __int16 *)(v7 + 24) <= v6 )
    {
      v29 = 80552;
      return sqlite3ReportError(11, v29, "database corruption");
    }
    v8 = *(_WORD *)(v7 + 26);
    v9 = *(_QWORD *)(v7 + 80);
    v34 = a1[84];
    v10 = __ROR2__(*(_WORD *)(2 * v6 + *(_QWORD *)(v7 + 96)), 8);
    if ( *(int *)(v7 + 20) < 0 && (unsigned int)btreeComputeFreeSpace(v7) )
    {
      v29 = 80556;
      return sqlite3ReportError(11, v29, "database corruption");
    }
    v11 = (unsigned __int16)(v10 & v8) + v9;
    if ( v11 < *(_QWORD *)(v7 + 96) + (unsigned __int64)*(unsigned __int16 *)(v7 + 24) )
    {
      v29 = 80559;
      return sqlite3ReportError(11, v29, "database corruption");
    }
    v12 = (_BYTE *)(v7 + 8);
    v13 = 1;
    if ( (v3 & 2) != 0 )
    {
      if ( *v12 )
      {
        v14 = v30;
        v15 = (*(unsigned __int16 (__fastcall **)(__int64, unsigned __int64))(v7 + 120))(v7, v11);
        a2 = 2 * *(_DWORD *)(v30 + 56) / 3u;
        if ( v15 + *(_DWORD *)(v7 + 20) + 2 <= (int)a2 && *(_WORD *)(v7 + 24) != 1 )
        {
          v13 = 2;
          goto LABEL_10;
        }
      }
      else
      {
        v14 = v30;
      }
      result = saveCursorKey(a1);
      if ( (_DWORD)result )
        return result;
      goto LABEL_10;
    }
    v14 = v30;
    v13 = 0;
LABEL_10:
    if ( *v12 || (result = sqlite3BtreePrevious(a1, a2), !(_DWORD)result) )
    {
      if ( (a1[1] & 0x20) == 0 || (result = saveAllCursors(v14, *((unsigned int *)a1 + 20), a1), !(_DWORD)result) )
      {
        if ( !*((_QWORD *)a1 + 16) && *(_BYTE *)(v2 + 19) )
          invalidateIncrblobCursors(v2, *((unsigned int *)a1 + 20), *((_QWORD *)a1 + 6), 0);
        result = sqlite3PagerWrite(*(_QWORD *)(v7 + 112));
        if ( !(_DWORD)result )
        {
          (*(void (__fastcall **)(__int64, unsigned __int64, __int128 *))(v7 + 128))(v7, v11, &v32);
          v17 = WORD2(v33) == (_DWORD)v33 ? 0 : clearCellOverflow(v7, v11, &v32);
          v18 = v37;
          inserted = v17;
          dropCell(v7, v37, HIWORD(v33), &inserted);
          result = inserted;
          if ( !inserted )
          {
            v19 = v34;
            if ( *(_BYTE *)(v7 + 8) )
              goto LABEL_74;
            v22 = *((_QWORD *)a1 + 17);
            if ( *(int *)(v22 + 20) >= 0 || (result = btreeComputeFreeSpace(*((_QWORD *)a1 + 17)), !(_DWORD)result) )
            {
              if ( v34 < a1[84] - 1 )
              {
                _mm_lfence();
                v23 = 8LL * v34 + 152;
              }
              else
              {
                v23 = 136;
              }
              v24 = *(_QWORD *)(v22 + 80);
              v25 = __ROR2__(*(_WORD *)(*(_QWORD *)(v22 + 96) + 2LL * *(unsigned __int16 *)(v22 + 24) - 2), 8);
              v26 = v24 + (unsigned __int16)(*(_WORD *)(v22 + 26) & v25);
              if ( v26 < v24 + 4 )
              {
                v29 = 80650;
                return sqlite3ReportError(11, v29, "database corruption");
              }
              v35 = *(_DWORD *)(*(_QWORD *)&a1[v23] + 4LL);
              v27 = (*(unsigned __int16 (__fastcall **)(__int64, __int64))(v22 + 120))(
                      v22,
                      v24 + (unsigned __int16)(*(_WORD *)(v22 + 26) & v25));
              v31 = *(_QWORD *)(v30 + 136);
              inserted = sqlite3PagerWrite(*(_QWORD *)(v22 + 112));
              if ( inserted )
              {
                v18 = v37;
              }
              else
              {
                v28 = v26 - 4;
                v18 = v37;
                inserted = insertCell(v7, v37, v28, v27 + 4, v31, v35);
              }
              dropCell(v22, (unsigned int)*(unsigned __int16 *)(v22 + 24) - 1, v27, &inserted);
              result = inserted;
              if ( !inserted )
              {
LABEL_74:
                if ( 3 * *(_DWORD *)(*((_QWORD *)a1 + 17) + 20LL) <= 2 * *(_DWORD *)(*((_QWORD *)a1 + 4) + 56LL)
                  || (v21 = balance(a1)) == 0 )
                {
                  if ( a1[84] <= v19 )
                    goto LABEL_24;
                  sqlite3PagerUnrefNotNull(*(_QWORD *)(*((_QWORD *)a1 + 17) + 112LL));
                  --a1[84];
                  while ( 1 )
                  {
                    v20 = *(_QWORD *)&a1[8 * a1[84] + 144];
                    if ( a1[84] <= v19 )
                      break;
                    --a1[84];
                    releasePage(v20);
                  }
                  *((_QWORD *)a1 + 17) = v20;
                  v21 = balance(a1);
                  if ( !v21 )
                  {
LABEL_24:
                    if ( (unsigned __int8)v13 <= 1u )
                    {
                      v21 = moveToRoot(a1);
                      if ( v13 )
                      {
                        btreeReleaseAllCursorPages(a1);
                        *a1 = 3;
                      }
                      if ( v21 == 16 )
                        return 0;
                    }
                    else
                    {
                      *a1 = 2;
                      if ( v18 >= *(unsigned __int16 *)(v7 + 24) )
                      {
                        *((_DWORD *)a1 + 1) = -1;
                        *((_WORD *)a1 + 43) = *(_WORD *)(v7 + 24) - 1;
                      }
                      else
                      {
                        *((_DWORD *)a1 + 1) = 1;
                      }
                      return 0;
                    }
                  }
                }
                return v21;
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800391a0  mov     [rsp-38h+arg_8], rbx
0x1800391a5  push    rbp
0x1800391a6  push    rsi
0x1800391a7  push    rdi
0x1800391a8  push    r12
0x1800391aa  push    r13
0x1800391ac  push    r14
0x1800391ae  push    r15
0x1800391b0  mov     rbp, rsp
0x1800391b3  sub     rsp, 50h
0x1800391b7  mov     r14, [rcx+8]
0x1800391bb  xorps   xmm0, xmm0
0x1800391be  mov     r15b, dl
0x1800391c1  mov     rbx, rcx
0x1800391c4  mov     rax, [r14+8]
0x1800391c8  mov     [rbp+var_20], rax
0x1800391cc  xor     eax, eax
0x1800391ce  mov     [rbp+var_8], rax
0x1800391d2  mov     al, [rcx]
0x1800391d4  movups  [rbp+var_18], xmm0
0x1800391d8  test    al, al
0x1800391da  jnz     loc_18003957D
0x1800391e0  movzx   ecx, word ptr [rbx+56h]
0x1800391e4  mov     rdi, [rbx+88h]
0x1800391eb  mov     [rbp+arg_18], ecx
0x1800391ee  movzx   eax, word ptr [rdi+18h]
0x1800391f2  cmp     eax, ecx
0x1800391f4  jbe     loc_1800395BD
0x1800391fa  mov     al, [rbx+54h]
0x1800391fd  add     ecx, ecx
0x1800391ff  movzx   r12d, word ptr [rdi+1Ah]
0x180039204  mov     r13, [rdi+50h]
0x180039208  mov     byte ptr [rbp+arg_0], al
0x18003920b  mov     rax, [rdi+60h]
0x18003920f  movzx   esi, word ptr [rcx+rax]
0x180039213  ror     si, 8
0x180039217  cmp     dword ptr [rdi+14h], 0
0x18003921b  jl      loc_180039552
0x180039221  movzx   eax, si
0x180039224  mov     rcx, r12
0x180039227  and     rcx, rax
0x18003922a  movzx   eax, word ptr [rdi+18h]
0x18003922e  add     rax, [rdi+60h]
0x180039232  add     r13, rcx
0x180039235  cmp     r13, rax
0x180039238  jb      loc_1800395C4
0x18003923e  lea     rsi, [rdi+8]
0x180039242  mov     r12d, 1
0x180039248  test    r15b, 2
0x18003924c  jz      loc_1800393D4
0x180039252  cmp     byte ptr [rsi], 0
0x180039255  jz      loc_1800393E0
0x18003925b  mov     rax, [rdi+78h]
0x18003925f  mov     rdx, r13
0x180039262  mov     rcx, rdi
0x180039265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003926a  mov     r15, [rbp+var_20]
0x18003926e  movzx   r8d, ax
0x180039272  mov     eax, 0AAAAAAABh
0x180039277  mov     ecx, [r15+38h]
0x18003927b  add     ecx, ecx
0x18003927d  mul     ecx
0x18003927f  mov     ecx, [rdi+14h]
0x180039282  add     ecx, 2
0x180039285  shr     edx, 1
0x180039287  add     ecx, r8d
0x18003928a  cmp     ecx, edx
0x18003928c  jg      loc_1800393E4
0x180039292  cmp     [rdi+18h], r12w
0x180039297  jz      loc_1800393E4
0x18003929d  mov     r12b, 2
0x1800392a0  cmp     byte ptr [rsi], 0
0x1800392a3  jz      loc_18003942F
0x1800392a9  test    byte ptr [rbx+1], 20h
0x1800392ad  jnz     loc_1800395CB
0x1800392b3  cmp     qword ptr [rbx+80h], 0
0x1800392bb  jz      loc_1800395E6
0x1800392c1  mov     rcx, [rdi+70h]
0x1800392c5  call    sqlite3PagerWrite
0x1800392ca  test    eax, eax
0x1800392cc  jnz     loc_1800393BC
0x1800392d2  mov     rax, [rdi+80h]
0x1800392d9  lea     r8, [rbp+var_18]
0x1800392dd  mov     rdx, r13
0x1800392e0  mov     rcx, rdi
0x1800392e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392e8  movzx   eax, word ptr [rbp+var_8+4]
0x1800392ec  cmp     eax, dword ptr [rbp+var_8]
0x1800392ef  jnz     loc_180039569
0x1800392f5  xor     eax, eax
0x1800392f7  mov     r15d, [rbp+arg_18]
0x1800392fb  lea     r9, [rbp+arg_10]
0x1800392ff  movzx   r8d, word ptr [rbp+var_8+6]
0x180039304  mov     edx, r15d
0x180039307  mov     rcx, rdi
0x18003930a  mov     [rbp+arg_10], eax
0x18003930d  call    dropCell
0x180039312  mov     eax, [rbp+arg_10]
0x180039315  test    eax, eax
0x180039317  jnz     loc_1800393BC
0x18003931d  movsx   r14, byte ptr [rbp+arg_0]
0x180039322  cmp     [rdi+8], al
0x180039325  jz      loc_180039444
0x18003932b  mov     rax, [rbx+20h]
0x18003932f  mov     edx, [rax+38h]
0x180039332  mov     rax, [rbx+88h]
0x180039339  add     edx, edx
0x18003933b  mov     ecx, [rax+14h]
0x18003933e  lea     eax, [rcx+rcx*2]
0x180039341  cmp     eax, edx
0x180039343  jg      loc_18003940F
0x180039349  movsx   eax, byte ptr [rbx+54h]
0x18003934d  cmp     eax, r14d
0x180039350  jle     short loc_18003939B
0x180039352  mov     rcx, [rbx+88h]
0x180039359  mov     rcx, [rcx+70h]
0x18003935d  call    sqlite3PagerUnrefNotNull
0x180039362  dec     byte ptr [rbx+54h]
0x180039365  jmp     short loc_180039371
0x180039367  dec     dl
0x180039369  mov     [rbx+54h], dl
0x18003936c  call    releasePage
0x180039371  movsx   edx, byte ptr [rbx+54h]
0x180039375  movsx   rax, dl
0x180039379  mov     rcx, [rbx+rax*8+90h]
0x180039381  cmp     edx, r14d
0x180039384  jg      short loc_180039367
0x180039386  mov     [rbx+88h], rcx
0x18003938d  mov     rcx, rbx
0x180039390  call    balance
0x180039395  mov     esi, eax
0x180039397  test    eax, eax
0x180039399  jnz     short loc_1800393BA
0x18003939b  mov     ecx, 1
0x1800393a0  cmp     r12b, cl
0x1800393a3  jbe     short loc_1800393F6
0x1800393a5  mov     byte ptr [rbx], 2
0x1800393a8  movzx   eax, word ptr [rdi+18h]
0x1800393ac  cmp     r15d, eax
0x1800393af  jnb     loc_180039535
0x1800393b5  mov     [rbx+4], ecx
0x1800393b8  xor     esi, esi
0x1800393ba  mov     eax, esi
0x1800393bc  mov     rbx, [rsp+50h+arg_8]
0x1800393c4  add     rsp, 50h
0x1800393c8  pop     r15
0x1800393ca  pop     r14
0x1800393cc  pop     r13
0x1800393ce  pop     r12
0x1800393d0  pop     rdi
0x1800393d1  pop     rsi
0x1800393d2  pop     rbp
0x1800393d3  retn
0x1800393d4  mov     r15, [rbp+var_20]
0x1800393d8  xor     r12b, r12b
0x1800393db  jmp     loc_1800392A0
0x1800393e0  mov     r15, [rbp+var_20]
0x1800393e4  mov     rcx, rbx
0x1800393e7  call    saveCursorKey
0x1800393ec  test    eax, eax
0x1800393ee  jz      loc_1800392A0
0x1800393f4  jmp     short loc_1800393BC
0x1800393f6  mov     rcx, rbx
0x1800393f9  call    moveToRoot
0x1800393fe  mov     esi, eax
0x180039400  test    r12b, r12b
0x180039403  jnz     short loc_180039422
0x180039405  xor     ecx, ecx
0x180039407  cmp     esi, 10h
0x18003940a  cmovz   esi, ecx
0x18003940d  jmp     short loc_1800393BA
0x18003940f  mov     rcx, rbx
0x180039412  call    balance
0x180039417  mov     esi, eax
0x180039419  test    eax, eax
0x18003941b  jnz     short loc_1800393BA
0x18003941d  jmp     loc_180039349
0x180039422  mov     rcx, rbx
0x180039425  call    btreeReleaseAllCursorPages
0x18003942a  mov     byte ptr [rbx], 3
0x18003942d  jmp     short loc_180039405
0x18003942f  mov     rcx, rbx
0x180039432  call    sqlite3BtreePrevious
0x180039437  test    eax, eax
0x180039439  jz      loc_1800392A9
0x18003943f  jmp     loc_1800393BC
0x180039444  mov     rsi, [rbx+88h]
0x18003944b  cmp     dword ptr [rsi+14h], 0
0x18003944f  jl      loc_180039608
0x180039455  movsx   eax, byte ptr [rbx+54h]
0x180039459  dec     eax
0x18003945b  cmp     r14d, eax
0x18003945e  jl      loc_180039525
0x180039464  mov     r9d, 88h
0x18003946a  mov     rax, [rsi+60h]
0x18003946e  mov     r8, [rsi+50h]
0x180039472  movzx   ecx, word ptr [rsi+18h]
0x180039476  movzx   edx, word ptr [rax+rcx*2-2]
0x18003947b  movzx   eax, word ptr [rsi+1Ah]
0x18003947f  ror     dx, 8
0x180039483  movzx   r15d, dx
0x180039487  and     r15, rax
0x18003948a  lea     rax, [r8+4]
0x18003948e  add     r15, r8
0x180039491  cmp     r15, rax
0x180039494  jb      loc_1800395A2
0x18003949a  mov     rax, [r9+rbx]
0x18003949e  mov     rdx, r15
0x1800394a1  mov     rcx, rsi
0x1800394a4  mov     eax, [rax+4]
0x1800394a7  mov     [rbp+arg_0], eax
0x1800394aa  mov     rax, [rsi+78h]
0x1800394ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394b3  mov     rcx, [rsi+70h]
0x1800394b7  movzx   r13d, ax
0x1800394bb  mov     rax, [rbp+var_20]
0x1800394bf  mov     rax, [rax+88h]
0x1800394c6  mov     [rbp+var_20], rax
0x1800394ca  call    sqlite3PagerWrite
0x1800394cf  mov     [rbp+arg_10], eax
0x1800394d2  test    eax, eax
0x1800394d4  jnz     short loc_18003954C
0x1800394d6  mov     eax, [rbp+arg_0]
0x1800394d9  lea     r8, [r15-4]
0x1800394dd  mov     r15d, [rbp+arg_18]
0x1800394e1  lea     r9d, [r13+4]
0x1800394e5  mov     [rsp+50h+var_28], eax
0x1800394e9  mov     edx, r15d
0x1800394ec  mov     rax, [rbp+var_20]
0x1800394f0  mov     rcx, rdi
0x1800394f3  mov     [rsp+50h+var_30], rax
0x1800394f8  call    insertCell
0x1800394fd  mov     [rbp+arg_10], eax
0x180039500  movzx   edx, word ptr [rsi+18h]
0x180039504  lea     r9, [rbp+arg_10]
0x180039508  dec     edx
0x18003950a  mov     r8d, r13d
0x18003950d  mov     rcx, rsi
0x180039510  call    dropCell
0x180039515  mov     eax, [rbp+arg_10]
0x180039518  test    eax, eax
0x18003951a  jz      loc_18003932B
0x180039520  jmp     loc_1800393BC
0x180039525  lfence
0x180039528  lea     r9, ds:98h[r14*8]
0x180039530  jmp     loc_18003946A
0x180039535  mov     dword ptr [rbx+4], 0FFFFFFFFh
0x18003953c  movzx   eax, word ptr [rdi+18h]
0x180039540  sub     ax, cx
0x180039543  mov     [rbx+56h], ax
0x180039547  jmp     loc_1800393B8
0x18003954c  mov     r15d, [rbp+arg_18]
0x180039550  jmp     short loc_180039500
0x180039552  mov     rcx, rdi
0x180039555  call    btreeComputeFreeSpace
0x18003955a  test    eax, eax
0x18003955c  jz      loc_180039221
0x180039562  mov     edx, 13AACh
0x180039567  jmp     short loc_1800395A7
0x180039569  lea     r8, [rbp+var_18]
0x18003956d  mov     rdx, r13
0x180039570  mov     rcx, rdi
0x180039573  call    clearCellOverflow
0x180039578  jmp     loc_1800392F7
0x18003957d  cmp     al, 3
0x18003957f  jb      short loc_18003959B
0x180039581  call    btreeRestoreCursorPosition
0x180039586  test    eax, eax
0x180039588  jnz     loc_1800393BC
0x18003958e  cmp     [rbx], al
0x180039590  jz      loc_1800391E0
0x180039596  jmp     loc_1800393BC
0x18003959b  mov     edx, 13A9Fh
0x1800395a0  jmp     short loc_1800395A7
0x1800395a2  mov     edx, 13B0Ah
0x1800395a7  lea     r8, aDatabaseCorrup; "database corruption"
0x1800395ae  mov     ecx, 0Bh
0x1800395b3  call    sqlite3ReportError
0x1800395b8  jmp     loc_1800393BC
0x1800395bd  mov     edx, 13AA8h
0x1800395c2  jmp     short loc_1800395A7
0x1800395c4  mov     edx, 13AAFh
0x1800395c9  jmp     short loc_1800395A7
0x1800395cb  mov     edx, [rbx+50h]
0x1800395ce  mov     r8, rbx
0x1800395d1  mov     rcx, r15
0x1800395d4  call    saveAllCursors
0x1800395d9  test    eax, eax
0x1800395db  jnz     loc_1800393BC
0x1800395e1  jmp     loc_1800392B3
0x1800395e6  cmp     byte ptr [r14+13h], 0
0x1800395eb  jz      loc_1800392C1
0x1800395f1  mov     r8, [rbx+30h]
0x1800395f5  xor     r9d, r9d
0x1800395f8  mov     edx, [rbx+50h]
0x1800395fb  mov     rcx, r14
0x1800395fe  call    invalidateIncrblobCursors
0x180039603  jmp     loc_1800392C1
0x180039608  mov     rcx, rsi
0x18003960b  call    btreeComputeFreeSpace
  ... truncated ...
```
