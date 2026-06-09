# sqlite3BtreeDelete

- ea: `0x18001cea8`
- end: `0x18001d2ae`
- name: `sqlite3BtreeDelete`
- size: `1030`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18002a050`

## callees

- `0x18001cea8`
- `0x18001df6c`
- `0x18001e3c8`
- `0x18001fe60`
- `0x180020e14`
- `0x1800217c0`
- `0x18002395c`
- `0x180024414`
- `0x180025870`
- `0x1800259b0`
- `0x180025ce0`
- `0x1800499a4`
- `0x180054a34`
- `0x180055ed0`
- `0x180060134`
- `0x180066bec`
- `0x18007211c`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeDelete(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  char v3; // r15
  unsigned __int8 v5; // al
  __int64 result; // rax
  unsigned int v7; // ecx
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int16 v10; // r12
  __int64 v11; // r13
  __int16 v12; // si
  unsigned __int64 v13; // r13
  _BYTE *v14; // rsi
  char v15; // r12
  __int64 v16; // r15
  int v17; // r8d
  unsigned int v18; // eax
  unsigned int v19; // r15d
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // r14d
  __int64 v23; // rsi
  __int64 v24; // r9
  __int64 v25; // r8
  __int16 v26; // dx
  unsigned __int64 v27; // r15
  unsigned int v28; // r13d
  unsigned __int64 v29; // r8
  __int64 v30; // rdx
  unsigned int v31; // esi
  __int64 v32; // rcx
  __int64 v33; // [rsp+30h] [rbp-20h]
  __int64 v34; // [rsp+30h] [rbp-20h]
  __int128 v35; // [rsp+38h] [rbp-18h] BYREF
  __int64 v36; // [rsp+48h] [rbp-8h]
  char v37; // [rsp+90h] [rbp+40h]
  int v38; // [rsp+90h] [rbp+40h]
  unsigned int inserted; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v40; // [rsp+A8h] [rbp+58h]

  v2 = *(_QWORD *)(a1 + 8);
  v3 = a2;
  v33 = *(_QWORD *)(v2 + 8);
  v36 = 0;
  v5 = *(_BYTE *)a1;
  v35 = 0;
  if ( !v5 )
    goto LABEL_5;
  if ( v5 < 3u )
  {
    v9 = 80440;
    return sqlite3ReportError(11, v9, "database corruption");
  }
  result = btreeRestoreCursorPosition();
  if ( !(_DWORD)result && !*(_BYTE *)a1 )
  {
LABEL_5:
    v7 = *(unsigned __int16 *)(a1 + 86);
    v8 = *(_QWORD *)(a1 + 136);
    v40 = v7;
    if ( *(unsigned __int16 *)(v8 + 24) <= v7 )
    {
      v9 = 80449;
      return sqlite3ReportError(11, v9, "database corruption");
    }
    v10 = *(_WORD *)(v8 + 26);
    v11 = *(_QWORD *)(v8 + 80);
    v37 = *(_BYTE *)(a1 + 84);
    v12 = __ROR2__(*(_WORD *)(2 * v7 + *(_QWORD *)(v8 + 96)), 8);
    if ( *(int *)(v8 + 20) < 0 && (unsigned int)btreeComputeFreeSpace(v8) )
    {
      v9 = 80453;
      return sqlite3ReportError(11, v9, "database corruption");
    }
    v13 = (unsigned __int16)(v12 & v10) + v11;
    if ( v13 < *(_QWORD *)(v8 + 96) + (unsigned __int64)*(unsigned __int16 *)(v8 + 24) )
    {
      v9 = 80456;
      return sqlite3ReportError(11, v9, "database corruption");
    }
    v14 = (_BYTE *)(v8 + 8);
    v15 = 1;
    if ( (v3 & 2) == 0 )
    {
      v16 = v33;
      v15 = 0;
      goto LABEL_22;
    }
    if ( *v14 )
    {
      v16 = v33;
      v17 = (*(unsigned __int16 (__fastcall **)(__int64, unsigned __int64))(v8 + 120))(v8, v13);
      a2 = 2 * *(_DWORD *)(v33 + 56) / 3u;
      if ( v17 + *(_DWORD *)(v8 + 20) + 2 <= (int)a2 && *(_WORD *)(v8 + 24) != 1 )
      {
        v15 = 2;
LABEL_22:
        if ( *v14 || (result = sqlite3BtreePrevious(a1, a2), !(_DWORD)result) )
        {
          if ( (*(_BYTE *)(a1 + 1) & 0x20) == 0
            || (result = saveAllCursors(v16, *(unsigned int *)(a1 + 80), a1), !(_DWORD)result) )
          {
            if ( !*(_QWORD *)(a1 + 128) && *(_BYTE *)(v2 + 19) )
              invalidateIncrblobCursors(v2, *(unsigned int *)(a1 + 80), *(_QWORD *)(a1 + 48), 0);
            result = sqlite3PagerWrite(*(_QWORD *)(v8 + 112));
            if ( !(_DWORD)result )
            {
              (*(void (__fastcall **)(__int64, unsigned __int64, __int128 *))(v8 + 128))(v8, v13, &v35);
              v18 = WORD2(v36) == (_DWORD)v36 ? 0 : clearCellOverflow(v8, v13, &v35);
              v19 = v40;
              inserted = v18;
              dropCell(v8, v40, HIWORD(v36), &inserted);
              result = inserted;
              if ( !inserted )
              {
                v22 = v37;
                if ( *(_BYTE *)(v8 + 8) )
                  goto LABEL_46;
                v23 = *(_QWORD *)(a1 + 136);
                if ( *(_DWORD *)(v23 + 20) >= (signed int)inserted
                  || (result = btreeComputeFreeSpace(*(_QWORD *)(a1 + 136)), !(_DWORD)result) )
                {
                  if ( v37 >= *(char *)(a1 + 84) - 1 )
                  {
                    v24 = 136;
                  }
                  else
                  {
                    _mm_lfence();
                    v24 = 8LL * v37 + 152;
                  }
                  v25 = *(_QWORD *)(v23 + 80);
                  v26 = __ROR2__(*(_WORD *)(*(_QWORD *)(v23 + 96) + 2LL * *(unsigned __int16 *)(v23 + 24) - 2), 8);
                  v27 = v25 + (unsigned __int16)(*(_WORD *)(v23 + 26) & v26);
                  if ( v27 < v25 + 4 )
                  {
                    v9 = 80547;
                    return sqlite3ReportError(11, v9, "database corruption");
                  }
                  v38 = *(_DWORD *)(*(_QWORD *)(v24 + a1) + 4LL);
                  v28 = (*(unsigned __int16 (__fastcall **)(__int64, __int64))(v23 + 120))(
                          v23,
                          v25 + (unsigned __int16)(*(_WORD *)(v23 + 26) & v26));
                  v34 = *(_QWORD *)(v33 + 136);
                  inserted = sqlite3PagerWrite(*(_QWORD *)(v23 + 112));
                  if ( inserted )
                  {
                    v19 = v40;
                  }
                  else
                  {
                    v29 = v27 - 4;
                    v19 = v40;
                    inserted = insertCell(v8, v40, v29, v28 + 4, v34, v38);
                  }
                  dropCell(v23, (unsigned int)*(unsigned __int16 *)(v23 + 24) - 1, v28, &inserted);
                  result = inserted;
                  if ( !inserted )
                  {
LABEL_46:
                    v30 = (unsigned int)(2 * *(_DWORD *)(*(_QWORD *)(a1 + 32) + 56LL));
                    if ( 3 * *(_DWORD *)(*(_QWORD *)(a1 + 136) + 20LL) <= (int)v30 || (v31 = balance(a1)) == 0 )
                    {
                      if ( *(char *)(a1 + 84) <= v22 )
                        goto LABEL_53;
                      sqlite3PagerUnrefNotNull(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 112LL), v30, v20, v21);
                      --*(_BYTE *)(a1 + 84);
                      while ( 1 )
                      {
                        v32 = *(_QWORD *)(a1 + 8LL * *(char *)(a1 + 84) + 144);
                        if ( *(char *)(a1 + 84) <= v22 )
                          break;
                        --*(_BYTE *)(a1 + 84);
                        releasePage(v32);
                      }
                      *(_QWORD *)(a1 + 136) = v32;
                      v31 = balance(a1);
                      if ( !v31 )
                      {
LABEL_53:
                        if ( (unsigned __int8)v15 <= 1u )
                        {
                          v31 = moveToRoot(a1);
                          if ( v15 )
                          {
                            btreeReleaseAllCursorPages(a1);
                            *(_BYTE *)a1 = 3;
                          }
                          if ( v31 == 16 )
                            return 0;
                        }
                        else
                        {
                          *(_BYTE *)a1 = 2;
                          if ( v19 < *(unsigned __int16 *)(v8 + 24) )
                          {
                            *(_DWORD *)(a1 + 4) = 1;
                          }
                          else
                          {
                            *(_DWORD *)(a1 + 4) = -1;
                            *(_WORD *)(a1 + 86) = *(_WORD *)(v8 + 24) - 1;
                          }
                          return 0;
                        }
                      }
                    }
                    return v31;
                  }
                }
              }
            }
          }
        }
        return result;
      }
    }
    else
    {
      v16 = v33;
    }
    result = saveCursorKey(a1);
    if ( (_DWORD)result )
      return result;
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x18001cea8  mov     [rsp-38h+arg_8], rbx
0x18001cead  push    rbp
0x18001ceae  push    rsi
0x18001ceaf  push    rdi
0x18001ceb0  push    r12
0x18001ceb2  push    r13
0x18001ceb4  push    r14
0x18001ceb6  push    r15
0x18001ceb8  mov     rbp, rsp
0x18001cebb  sub     rsp, 50h
0x18001cebf  mov     r14, [rcx+8]
0x18001cec3  xorps   xmm0, xmm0
0x18001cec6  mov     r15b, dl
0x18001cec9  mov     rbx, rcx
0x18001cecc  mov     rax, [r14+8]
0x18001ced0  mov     [rbp+var_20], rax
0x18001ced4  xor     eax, eax
0x18001ced6  mov     [rbp+var_8], rax
0x18001ceda  mov     al, [rcx]
0x18001cedc  movups  [rbp+var_18], xmm0
0x18001cee0  test    al, al
0x18001cee2  jz      short loc_18001CEFD
0x18001cee4  cmp     al, 3
0x18001cee6  jb      short loc_18001CF1A
0x18001cee8  call    btreeRestoreCursorPosition
0x18001ceed  test    eax, eax
0x18001ceef  jnz     loc_18001D296
0x18001cef5  cmp     [rbx], al
0x18001cef7  jnz     loc_18001D296
0x18001cefd  movzx   ecx, word ptr [rbx+56h]
0x18001cf01  mov     rdi, [rbx+88h]
0x18001cf08  mov     [rbp+arg_18], ecx
0x18001cf0b  movzx   eax, word ptr [rdi+18h]
0x18001cf0f  cmp     eax, ecx
0x18001cf11  ja      short loc_18001CF35
0x18001cf13  mov     edx, 13A41h
0x18001cf18  jmp     short loc_18001CF1F
0x18001cf1a  mov     edx, 13A38h
0x18001cf1f  lea     r8, aDatabaseCorrup; "database corruption"
0x18001cf26  mov     ecx, 0Bh
0x18001cf2b  call    sqlite3ReportError
0x18001cf30  jmp     loc_18001D296
0x18001cf35  mov     al, [rbx+54h]
0x18001cf38  add     ecx, ecx
0x18001cf3a  movzx   r12d, word ptr [rdi+1Ah]
0x18001cf3f  mov     r13, [rdi+50h]
0x18001cf43  mov     byte ptr [rbp+arg_0], al
0x18001cf46  mov     rax, [rdi+60h]
0x18001cf4a  movzx   esi, word ptr [rcx+rax]
0x18001cf4e  ror     si, 8
0x18001cf52  cmp     dword ptr [rdi+14h], 0
0x18001cf56  jge     short loc_18001CF6B
0x18001cf58  mov     rcx, rdi
0x18001cf5b  call    btreeComputeFreeSpace
0x18001cf60  test    eax, eax
0x18001cf62  jz      short loc_18001CF6B
0x18001cf64  mov     edx, 13A45h
0x18001cf69  jmp     short loc_18001CF1F
0x18001cf6b  movzx   eax, si
0x18001cf6e  mov     rcx, r12
0x18001cf71  and     rcx, rax
0x18001cf74  movzx   eax, word ptr [rdi+18h]
0x18001cf78  add     rax, [rdi+60h]
0x18001cf7c  add     r13, rcx
0x18001cf7f  cmp     r13, rax
0x18001cf82  jnb     short loc_18001CF8B
0x18001cf84  mov     edx, 13A48h
0x18001cf89  jmp     short loc_18001CF1F
0x18001cf8b  lea     rsi, [rdi+8]
0x18001cf8f  mov     r12d, 1
0x18001cf95  test    r15b, 2
0x18001cf99  jnz     short loc_18001CFA4
0x18001cf9b  mov     r15, [rbp+var_20]
0x18001cf9f  xor     r12b, r12b
0x18001cfa2  jmp     short loc_18001CFFC
0x18001cfa4  cmp     byte ptr [rsi], 0
0x18001cfa7  jz      short loc_18001CFE8
0x18001cfa9  mov     rax, [rdi+78h]
0x18001cfad  mov     rdx, r13
0x18001cfb0  mov     rcx, rdi
0x18001cfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfb8  mov     r15, [rbp+var_20]
0x18001cfbc  movzx   r8d, ax
0x18001cfc0  mov     eax, 0AAAAAAABh
0x18001cfc5  mov     ecx, [r15+38h]
0x18001cfc9  add     ecx, ecx
0x18001cfcb  mul     ecx
0x18001cfcd  mov     ecx, [rdi+14h]
0x18001cfd0  add     ecx, 2
0x18001cfd3  shr     edx, 1
0x18001cfd5  add     ecx, r8d
0x18001cfd8  cmp     ecx, edx
0x18001cfda  jg      short loc_18001CFEC
0x18001cfdc  cmp     [rdi+18h], r12w
0x18001cfe1  jz      short loc_18001CFEC
0x18001cfe3  mov     r12b, 2
0x18001cfe6  jmp     short loc_18001CFFC
0x18001cfe8  mov     r15, [rbp+var_20]
0x18001cfec  mov     rcx, rbx
0x18001cfef  call    saveCursorKey
0x18001cff4  test    eax, eax
0x18001cff6  jnz     loc_18001D296
0x18001cffc  cmp     byte ptr [rsi], 0
0x18001cfff  jnz     short loc_18001D011
0x18001d001  mov     rcx, rbx
0x18001d004  call    sqlite3BtreePrevious
0x18001d009  test    eax, eax
0x18001d00b  jnz     loc_18001D296
0x18001d011  test    byte ptr [rbx+1], 20h
0x18001d015  jz      short loc_18001D02D
0x18001d017  mov     edx, [rbx+50h]
0x18001d01a  mov     r8, rbx
0x18001d01d  mov     rcx, r15
0x18001d020  call    saveAllCursors
0x18001d025  test    eax, eax
0x18001d027  jnz     loc_18001D296
0x18001d02d  cmp     qword ptr [rbx+80h], 0
0x18001d035  jnz     short loc_18001D050
0x18001d037  cmp     byte ptr [r14+13h], 0
0x18001d03c  jz      short loc_18001D050
0x18001d03e  mov     r8, [rbx+30h]
0x18001d042  xor     r9d, r9d
0x18001d045  mov     edx, [rbx+50h]
0x18001d048  mov     rcx, r14
0x18001d04b  call    invalidateIncrblobCursors
0x18001d050  mov     rcx, [rdi+70h]
0x18001d054  call    sqlite3PagerWrite
0x18001d059  test    eax, eax
0x18001d05b  jnz     loc_18001D296
0x18001d061  mov     rax, [rdi+80h]
0x18001d068  lea     r8, [rbp+var_18]
0x18001d06c  mov     rdx, r13
0x18001d06f  mov     rcx, rdi
0x18001d072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d077  movzx   eax, word ptr [rbp+var_8+4]
0x18001d07b  cmp     eax, dword ptr [rbp+var_8]
0x18001d07e  jz      short loc_18001D091
0x18001d080  lea     r8, [rbp+var_18]
0x18001d084  mov     rdx, r13
0x18001d087  mov     rcx, rdi
0x18001d08a  call    clearCellOverflow
0x18001d08f  jmp     short loc_18001D093
0x18001d091  xor     eax, eax
0x18001d093  mov     r15d, [rbp+arg_18]
0x18001d097  lea     r9, [rbp+arg_10]
0x18001d09b  movzx   r8d, word ptr [rbp+var_8+6]
0x18001d0a0  mov     edx, r15d
0x18001d0a3  mov     rcx, rdi
0x18001d0a6  mov     [rbp+arg_10], eax
0x18001d0a9  call    dropCell
0x18001d0ae  mov     eax, [rbp+arg_10]
0x18001d0b1  test    eax, eax
0x18001d0b3  jnz     loc_18001D296
0x18001d0b9  movsx   r14, byte ptr [rbp+arg_0]
0x18001d0be  cmp     [rdi+8], al
0x18001d0c1  jnz     loc_18001D1C3
0x18001d0c7  mov     rsi, [rbx+88h]
0x18001d0ce  cmp     [rsi+14h], eax
0x18001d0d1  jge     short loc_18001D0E3
0x18001d0d3  mov     rcx, rsi
0x18001d0d6  call    btreeComputeFreeSpace
0x18001d0db  test    eax, eax
0x18001d0dd  jnz     loc_18001D296
0x18001d0e3  movsx   eax, byte ptr [rbx+54h]
0x18001d0e7  dec     eax
0x18001d0e9  cmp     r14d, eax
0x18001d0ec  jge     short loc_18001D0FB
0x18001d0ee  lfence
0x18001d0f1  lea     r9, ds:98h[r14*8]
0x18001d0f9  jmp     short loc_18001D101
0x18001d0fb  mov     r9d, 88h
0x18001d101  mov     rax, [rsi+60h]
0x18001d105  mov     r8, [rsi+50h]
0x18001d109  movzx   ecx, word ptr [rsi+18h]
0x18001d10d  movzx   edx, word ptr [rax+rcx*2-2]
0x18001d112  movzx   eax, word ptr [rsi+1Ah]
0x18001d116  ror     dx, 8
0x18001d11a  movzx   r15d, dx
0x18001d11e  and     r15, rax
0x18001d121  lea     rax, [r8+4]
0x18001d125  add     r15, r8
0x18001d128  cmp     r15, rax
0x18001d12b  jnb     short loc_18001D137
0x18001d12d  mov     edx, 13AA3h
0x18001d132  jmp     loc_18001CF1F
0x18001d137  mov     rax, [r9+rbx]
0x18001d13b  mov     rdx, r15
0x18001d13e  mov     rcx, rsi
0x18001d141  mov     eax, [rax+4]
0x18001d144  mov     [rbp+arg_0], eax
0x18001d147  mov     rax, [rsi+78h]
0x18001d14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d150  mov     rcx, [rsi+70h]
0x18001d154  movzx   r13d, ax
0x18001d158  mov     rax, [rbp+var_20]
0x18001d15c  mov     rax, [rax+88h]
0x18001d163  mov     [rbp+var_20], rax
0x18001d167  call    sqlite3PagerWrite
0x18001d16c  mov     [rbp+arg_10], eax
0x18001d16f  test    eax, eax
0x18001d171  jnz     short loc_18001D19F
0x18001d173  mov     eax, [rbp+arg_0]
0x18001d176  lea     r8, [r15-4]
0x18001d17a  mov     r15d, [rbp+arg_18]
0x18001d17e  lea     r9d, [r13+4]
0x18001d182  mov     [rsp+50h+var_28], eax
0x18001d186  mov     edx, r15d
0x18001d189  mov     rax, [rbp+var_20]
0x18001d18d  mov     rcx, rdi
0x18001d190  mov     [rsp+50h+var_30], rax
0x18001d195  call    insertCell
0x18001d19a  mov     [rbp+arg_10], eax
0x18001d19d  jmp     short loc_18001D1A3
0x18001d19f  mov     r15d, [rbp+arg_18]
0x18001d1a3  movzx   edx, word ptr [rsi+18h]
0x18001d1a7  lea     r9, [rbp+arg_10]
0x18001d1ab  dec     edx
0x18001d1ad  mov     r8d, r13d
0x18001d1b0  mov     rcx, rsi
0x18001d1b3  call    dropCell
0x18001d1b8  mov     eax, [rbp+arg_10]
0x18001d1bb  test    eax, eax
0x18001d1bd  jnz     loc_18001D296
0x18001d1c3  mov     rax, [rbx+20h]
0x18001d1c7  mov     edx, [rax+38h]
0x18001d1ca  mov     rax, [rbx+88h]
0x18001d1d1  add     edx, edx
0x18001d1d3  mov     ecx, [rax+14h]
0x18001d1d6  lea     eax, [rcx+rcx*2]
0x18001d1d9  cmp     eax, edx
0x18001d1db  jle     short loc_18001D1EF
0x18001d1dd  mov     rcx, rbx
0x18001d1e0  call    balance
0x18001d1e5  mov     esi, eax
0x18001d1e7  test    eax, eax
0x18001d1e9  jnz     loc_18001D294
0x18001d1ef  movsx   eax, byte ptr [rbx+54h]
0x18001d1f3  cmp     eax, r14d
0x18001d1f6  jle     short loc_18001D241
0x18001d1f8  mov     rcx, [rbx+88h]
0x18001d1ff  mov     rcx, [rcx+70h]
0x18001d203  call    sqlite3PagerUnrefNotNull
0x18001d208  dec     byte ptr [rbx+54h]
0x18001d20b  jmp     short loc_18001D217
0x18001d20d  dec     dl
0x18001d20f  mov     [rbx+54h], dl
0x18001d212  call    releasePage
0x18001d217  movsx   edx, byte ptr [rbx+54h]
0x18001d21b  movsx   rax, dl
0x18001d21f  mov     rcx, [rbx+rax*8+90h]
0x18001d227  cmp     edx, r14d
0x18001d22a  jg      short loc_18001D20D
0x18001d22c  mov     [rbx+88h], rcx
0x18001d233  mov     rcx, rbx
0x18001d236  call    balance
0x18001d23b  mov     esi, eax
0x18001d23d  test    eax, eax
0x18001d23f  jnz     short loc_18001D294
0x18001d241  mov     ecx, 1
0x18001d246  cmp     r12b, cl
0x18001d249  jbe     short loc_18001D272
0x18001d24b  mov     byte ptr [rbx], 2
0x18001d24e  movzx   eax, word ptr [rdi+18h]
0x18001d252  cmp     r15d, eax
0x18001d255  jb      short loc_18001D26B
0x18001d257  mov     dword ptr [rbx+4], 0FFFFFFFFh
0x18001d25e  movzx   eax, word ptr [rdi+18h]
0x18001d262  sub     ax, cx
0x18001d265  mov     [rbx+56h], ax
0x18001d269  jmp     short loc_18001D26E
0x18001d26b  mov     [rbx+4], ecx
0x18001d26e  xor     esi, esi
0x18001d270  jmp     short loc_18001D294
0x18001d272  mov     rcx, rbx
0x18001d275  call    moveToRoot
0x18001d27a  mov     esi, eax
0x18001d27c  test    r12b, r12b
0x18001d27f  jz      short loc_18001D28C
0x18001d281  mov     rcx, rbx
0x18001d284  call    btreeReleaseAllCursorPages
0x18001d289  mov     byte ptr [rbx], 3
0x18001d28c  xor     ecx, ecx
0x18001d28e  cmp     esi, 10h
0x18001d291  cmovz   esi, ecx
0x18001d294  mov     eax, esi
0x18001d296  mov     rbx, [rsp+50h+arg_8]
0x18001d29e  add     rsp, 50h
0x18001d2a2  pop     r15
0x18001d2a4  pop     r14
0x18001d2a6  pop     r13
0x18001d2a8  pop     r12
0x18001d2aa  pop     rdi
0x18001d2ab  pop     rsi
0x18001d2ac  pop     rbp
0x18001d2ad  retn
```
