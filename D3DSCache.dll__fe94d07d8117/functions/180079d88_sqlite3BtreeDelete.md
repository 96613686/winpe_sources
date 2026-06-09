# sqlite3BtreeDelete

- ea: `0x180079d88`
- end: `0x18007a18e`
- name: `sqlite3BtreeDelete`
- size: `1030`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180021aa0`

## callees

- `0x1800117b4`
- `0x180038d6c`
- `0x18003a860`
- `0x18003d0bc`
- `0x18003e45c`
- `0x18003eea0`
- `0x1800546cc`
- `0x1800561a0`
- `0x1800570d4`
- `0x180058600`
- `0x18005cf40`
- `0x1800638ac`
- `0x180063fa8`
- `0x180075a04`
- `0x180079d88`
- `0x18007a96c`
- `0x180088148`
- `0x1800a8010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeDelete(char *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  char v4; // r15
  unsigned __int8 v6; // al
  __int64 result; // rax
  unsigned int v8; // ecx
  __int64 v9; // rdi
  __int64 v10; // rdx
  __int16 v11; // r12
  __int64 v12; // r13
  __int16 v13; // si
  unsigned __int64 v14; // r13
  _BYTE *v15; // rsi
  char v16; // r12
  __int64 v17; // r15
  unsigned int v18; // eax
  unsigned int v19; // r15d
  int v20; // r14d
  __int64 v21; // rsi
  __int64 v22; // r9
  __int64 v23; // r8
  __int16 v24; // dx
  unsigned __int64 v25; // r15
  unsigned int v26; // r13d
  unsigned __int64 v27; // r8
  unsigned int v28; // esi
  __int64 v29; // rcx
  __int64 v30; // [rsp+30h] [rbp-20h]
  __int64 v31; // [rsp+30h] [rbp-20h]
  __int128 v32; // [rsp+38h] [rbp-18h] BYREF
  __int64 v33; // [rsp+48h] [rbp-8h]
  char v34; // [rsp+90h] [rbp+40h]
  int v35; // [rsp+90h] [rbp+40h]
  unsigned int inserted; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v37; // [rsp+A8h] [rbp+58h]

  v3 = *((_QWORD *)a1 + 1);
  v4 = a2;
  v30 = *(_QWORD *)(v3 + 8);
  v33 = 0;
  v6 = *a1;
  v32 = 0;
  if ( !v6 )
    goto LABEL_5;
  if ( v6 < 3u )
  {
    v10 = 80293;
    return sqlite3ReportError(11, v10, "database corruption");
  }
  result = btreeRestoreCursorPosition();
  if ( !(_DWORD)result && !*a1 )
  {
LABEL_5:
    v8 = *((unsigned __int16 *)a1 + 43);
    v9 = *((_QWORD *)a1 + 17);
    v37 = v8;
    if ( *(unsigned __int16 *)(v9 + 24) <= v8 )
    {
      v10 = 80302;
      return sqlite3ReportError(11, v10, "database corruption");
    }
    v11 = *(_WORD *)(v9 + 26);
    v12 = *(_QWORD *)(v9 + 80);
    v34 = a1[84];
    v13 = __ROR2__(*(_WORD *)(2 * v8 + *(_QWORD *)(v9 + 96)), 8);
    if ( *(int *)(v9 + 20) < 0 && (unsigned int)btreeComputeFreeSpace(v9) )
    {
      v10 = 80306;
      return sqlite3ReportError(11, v10, "database corruption");
    }
    v14 = (unsigned __int16)(v13 & v11) + v12;
    if ( v14 < *(_QWORD *)(v9 + 96) + (unsigned __int64)*(unsigned __int16 *)(v9 + 24) )
    {
      v10 = 80309;
      return sqlite3ReportError(11, v10, "database corruption");
    }
    v15 = (_BYTE *)(v9 + 8);
    v16 = 1;
    if ( (v4 & 2) == 0 )
    {
      v17 = v30;
      v16 = 0;
      goto LABEL_22;
    }
    if ( *v15 )
    {
      v17 = v30;
      a3 = (*(unsigned __int16 (__fastcall **)(__int64, unsigned __int64))(v9 + 120))(v9, v14);
      a2 = 2 * *(_DWORD *)(v30 + 56) / 3u;
      if ( (int)a3 + *(_DWORD *)(v9 + 20) + 2 <= (int)a2 && *(_WORD *)(v9 + 24) != 1 )
      {
        v16 = 2;
LABEL_22:
        if ( *v15 || (result = sqlite3BtreePrevious(a1, a2, a3), !(_DWORD)result) )
        {
          if ( (a1[1] & 0x20) == 0 || (result = saveAllCursors(v17, *((unsigned int *)a1 + 20), a1), !(_DWORD)result) )
          {
            if ( !*((_QWORD *)a1 + 16) && *(_BYTE *)(v3 + 19) )
              invalidateIncrblobCursors(v3, *((unsigned int *)a1 + 20), *((_QWORD *)a1 + 6), 0);
            result = sqlite3PagerWrite(*(_QWORD *)(v9 + 112));
            if ( !(_DWORD)result )
            {
              (*(void (__fastcall **)(__int64, unsigned __int64, __int128 *))(v9 + 128))(v9, v14, &v32);
              v18 = WORD2(v33) == (_DWORD)v33 ? 0 : clearCellOverflow(v9, v14, &v32);
              v19 = v37;
              inserted = v18;
              dropCell(v9, v37, HIWORD(v33), &inserted);
              result = inserted;
              if ( !inserted )
              {
                v20 = v34;
                if ( *(_BYTE *)(v9 + 8) )
                  goto LABEL_65;
                v21 = *((_QWORD *)a1 + 17);
                if ( *(_DWORD *)(v21 + 20) >= (signed int)inserted
                  || (result = btreeComputeFreeSpace(*((_QWORD *)a1 + 17)), !(_DWORD)result) )
                {
                  if ( v34 >= a1[84] - 1 )
                  {
                    v22 = 136;
                  }
                  else
                  {
                    _mm_lfence();
                    v22 = 8LL * v34 + 152;
                  }
                  v23 = *(_QWORD *)(v21 + 80);
                  v24 = __ROR2__(*(_WORD *)(*(_QWORD *)(v21 + 96) + 2LL * *(unsigned __int16 *)(v21 + 24) - 2), 8);
                  v25 = v23 + (unsigned __int16)(*(_WORD *)(v21 + 26) & v24);
                  if ( v25 < v23 + 4 )
                  {
                    v10 = 80400;
                    return sqlite3ReportError(11, v10, "database corruption");
                  }
                  v35 = *(_DWORD *)(*(_QWORD *)&a1[v22] + 4LL);
                  v26 = (*(unsigned __int16 (__fastcall **)(__int64, __int64))(v21 + 120))(
                          v21,
                          v23 + (unsigned __int16)(*(_WORD *)(v21 + 26) & v24));
                  v31 = *(_QWORD *)(v30 + 136);
                  inserted = sqlite3PagerWrite(*(_QWORD *)(v21 + 112));
                  if ( inserted )
                  {
                    v19 = v37;
                  }
                  else
                  {
                    v27 = v25 - 4;
                    v19 = v37;
                    inserted = insertCell(v9, v37, v27, v26 + 4, v31, v35);
                  }
                  dropCell(v21, (unsigned int)*(unsigned __int16 *)(v21 + 24) - 1, v26, &inserted);
                  result = inserted;
                  if ( !inserted )
                  {
LABEL_65:
                    if ( 3 * *(_DWORD *)(*((_QWORD *)a1 + 17) + 20LL) <= 2 * *(_DWORD *)(*((_QWORD *)a1 + 4) + 56LL)
                      || (v28 = balance(a1)) == 0 )
                    {
                      if ( a1[84] <= v20 )
                        goto LABEL_53;
                      sqlite3PagerUnrefNotNull(*(_QWORD *)(*((_QWORD *)a1 + 17) + 112LL));
                      --a1[84];
                      while ( 1 )
                      {
                        v29 = *(_QWORD *)&a1[8 * a1[84] + 144];
                        if ( a1[84] <= v20 )
                          break;
                        --a1[84];
                        releasePage(v29);
                      }
                      *((_QWORD *)a1 + 17) = v29;
                      v28 = balance(a1);
                      if ( !v28 )
                      {
LABEL_53:
                        if ( (unsigned __int8)v16 <= 1u )
                        {
                          v28 = moveToRoot(a1);
                          if ( v16 )
                          {
                            btreeReleaseAllCursorPages(a1);
                            *a1 = 3;
                          }
                          if ( v28 == 16 )
                            return 0;
                        }
                        else
                        {
                          *a1 = 2;
                          if ( v19 < *(unsigned __int16 *)(v9 + 24) )
                          {
                            *((_DWORD *)a1 + 1) = 1;
                          }
                          else
                          {
                            *((_DWORD *)a1 + 1) = -1;
                            *((_WORD *)a1 + 43) = *(_WORD *)(v9 + 24) - 1;
                          }
                          return 0;
                        }
                      }
                    }
                    return v28;
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
      v17 = v30;
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
0x180079d88  mov     [rsp-38h+arg_8], rbx
0x180079d8d  push    rbp
0x180079d8e  push    rsi
0x180079d8f  push    rdi
0x180079d90  push    r12
0x180079d92  push    r13
0x180079d94  push    r14
0x180079d96  push    r15
0x180079d98  mov     rbp, rsp
0x180079d9b  sub     rsp, 50h
0x180079d9f  mov     r14, [rcx+8]
0x180079da3  xorps   xmm0, xmm0
0x180079da6  mov     r15b, dl
0x180079da9  mov     rbx, rcx
0x180079dac  mov     rax, [r14+8]
0x180079db0  mov     [rbp+var_20], rax
0x180079db4  xor     eax, eax
0x180079db6  mov     [rbp+var_8], rax
0x180079dba  mov     al, [rcx]
0x180079dbc  movups  [rbp+var_18], xmm0
0x180079dc0  test    al, al
0x180079dc2  jz      short loc_180079DDD
0x180079dc4  cmp     al, 3
0x180079dc6  jb      short loc_180079DFA
0x180079dc8  call    btreeRestoreCursorPosition
0x180079dcd  test    eax, eax
0x180079dcf  jnz     loc_18007A176
0x180079dd5  cmp     [rbx], al
0x180079dd7  jnz     loc_18007A176
0x180079ddd  movzx   ecx, word ptr [rbx+56h]
0x180079de1  mov     rdi, [rbx+88h]
0x180079de8  mov     [rbp+arg_18], ecx
0x180079deb  movzx   eax, word ptr [rdi+18h]
0x180079def  cmp     eax, ecx
0x180079df1  ja      short loc_180079E15
0x180079df3  mov     edx, 139AEh
0x180079df8  jmp     short loc_180079DFF
0x180079dfa  mov     edx, 139A5h
0x180079dff  lea     r8, aDatabaseCorrup; "database corruption"
0x180079e06  mov     ecx, 0Bh
0x180079e0b  call    sqlite3ReportError
0x180079e10  jmp     loc_18007A176
0x180079e15  mov     al, [rbx+54h]
0x180079e18  add     ecx, ecx
0x180079e1a  movzx   r12d, word ptr [rdi+1Ah]
0x180079e1f  mov     r13, [rdi+50h]
0x180079e23  mov     byte ptr [rbp+arg_0], al
0x180079e26  mov     rax, [rdi+60h]
0x180079e2a  movzx   esi, word ptr [rcx+rax]
0x180079e2e  ror     si, 8
0x180079e32  cmp     dword ptr [rdi+14h], 0
0x180079e36  jge     short loc_180079E4B
0x180079e38  mov     rcx, rdi
0x180079e3b  call    btreeComputeFreeSpace
0x180079e40  test    eax, eax
0x180079e42  jz      short loc_180079E4B
0x180079e44  mov     edx, 139B2h
0x180079e49  jmp     short loc_180079DFF
0x180079e4b  movzx   eax, si
0x180079e4e  mov     rcx, r12
0x180079e51  and     rcx, rax
0x180079e54  movzx   eax, word ptr [rdi+18h]
0x180079e58  add     rax, [rdi+60h]
0x180079e5c  add     r13, rcx
0x180079e5f  cmp     r13, rax
0x180079e62  jnb     short loc_180079E6B
0x180079e64  mov     edx, 139B5h
0x180079e69  jmp     short loc_180079DFF
0x180079e6b  lea     rsi, [rdi+8]
0x180079e6f  mov     r12d, 1
0x180079e75  test    r15b, 2
0x180079e79  jnz     short loc_180079E84
0x180079e7b  mov     r15, [rbp+var_20]
0x180079e7f  xor     r12b, r12b
0x180079e82  jmp     short loc_180079EDC
0x180079e84  cmp     byte ptr [rsi], 0
0x180079e87  jz      short loc_180079EC8
0x180079e89  mov     rax, [rdi+78h]
0x180079e8d  mov     rdx, r13
0x180079e90  mov     rcx, rdi
0x180079e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e98  mov     r15, [rbp+var_20]
0x180079e9c  movzx   r8d, ax
0x180079ea0  mov     eax, 0AAAAAAABh
0x180079ea5  mov     ecx, [r15+38h]
0x180079ea9  add     ecx, ecx
0x180079eab  mul     ecx
0x180079ead  mov     ecx, [rdi+14h]
0x180079eb0  add     ecx, 2
0x180079eb3  shr     edx, 1
0x180079eb5  add     ecx, r8d
0x180079eb8  cmp     ecx, edx
0x180079eba  jg      short loc_180079ECC
0x180079ebc  cmp     [rdi+18h], r12w
0x180079ec1  jz      short loc_180079ECC
0x180079ec3  mov     r12b, 2
0x180079ec6  jmp     short loc_180079EDC
0x180079ec8  mov     r15, [rbp+var_20]
0x180079ecc  mov     rcx, rbx
0x180079ecf  call    saveCursorKey
0x180079ed4  test    eax, eax
0x180079ed6  jnz     loc_18007A176
0x180079edc  cmp     byte ptr [rsi], 0
0x180079edf  jnz     short loc_180079EF1
0x180079ee1  mov     rcx, rbx
0x180079ee4  call    sqlite3BtreePrevious
0x180079ee9  test    eax, eax
0x180079eeb  jnz     loc_18007A176
0x180079ef1  test    byte ptr [rbx+1], 20h
0x180079ef5  jz      short loc_180079F0D
0x180079ef7  mov     edx, [rbx+50h]
0x180079efa  mov     r8, rbx
0x180079efd  mov     rcx, r15
0x180079f00  call    saveAllCursors
0x180079f05  test    eax, eax
0x180079f07  jnz     loc_18007A176
0x180079f0d  cmp     qword ptr [rbx+80h], 0
0x180079f15  jnz     short loc_180079F30
0x180079f17  cmp     byte ptr [r14+13h], 0
0x180079f1c  jz      short loc_180079F30
0x180079f1e  mov     r8, [rbx+30h]
0x180079f22  xor     r9d, r9d
0x180079f25  mov     edx, [rbx+50h]
0x180079f28  mov     rcx, r14
0x180079f2b  call    invalidateIncrblobCursors
0x180079f30  mov     rcx, [rdi+70h]
0x180079f34  call    sqlite3PagerWrite
0x180079f39  test    eax, eax
0x180079f3b  jnz     loc_18007A176
0x180079f41  mov     rax, [rdi+80h]
0x180079f48  lea     r8, [rbp+var_18]
0x180079f4c  mov     rdx, r13
0x180079f4f  mov     rcx, rdi
0x180079f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079f57  movzx   eax, word ptr [rbp+var_8+4]
0x180079f5b  cmp     eax, dword ptr [rbp+var_8]
0x180079f5e  jz      short loc_180079F71
0x180079f60  lea     r8, [rbp+var_18]
0x180079f64  mov     rdx, r13
0x180079f67  mov     rcx, rdi
0x180079f6a  call    clearCellOverflow
0x180079f6f  jmp     short loc_180079F73
0x180079f71  xor     eax, eax
0x180079f73  mov     r15d, [rbp+arg_18]
0x180079f77  lea     r9, [rbp+arg_10]
0x180079f7b  movzx   r8d, word ptr [rbp+var_8+6]
0x180079f80  mov     edx, r15d
0x180079f83  mov     rcx, rdi
0x180079f86  mov     [rbp+arg_10], eax
0x180079f89  call    dropCell
0x180079f8e  mov     eax, [rbp+arg_10]
0x180079f91  test    eax, eax
0x180079f93  jnz     loc_18007A176
0x180079f99  movsx   r14, byte ptr [rbp+arg_0]
0x180079f9e  cmp     [rdi+8], al
0x180079fa1  jnz     loc_18007A0A3
0x180079fa7  mov     rsi, [rbx+88h]
0x180079fae  cmp     [rsi+14h], eax
0x180079fb1  jge     short loc_180079FC3
0x180079fb3  mov     rcx, rsi
0x180079fb6  call    btreeComputeFreeSpace
0x180079fbb  test    eax, eax
0x180079fbd  jnz     loc_18007A176
0x180079fc3  movsx   eax, byte ptr [rbx+54h]
0x180079fc7  dec     eax
0x180079fc9  cmp     r14d, eax
0x180079fcc  jge     short loc_180079FDB
0x180079fce  lfence
0x180079fd1  lea     r9, ds:98h[r14*8]
0x180079fd9  jmp     short loc_180079FE1
0x180079fdb  mov     r9d, 88h
0x180079fe1  mov     rax, [rsi+60h]
0x180079fe5  mov     r8, [rsi+50h]
0x180079fe9  movzx   ecx, word ptr [rsi+18h]
0x180079fed  movzx   edx, word ptr [rax+rcx*2-2]
0x180079ff2  movzx   eax, word ptr [rsi+1Ah]
0x180079ff6  ror     dx, 8
0x180079ffa  movzx   r15d, dx
0x180079ffe  and     r15, rax
0x18007a001  lea     rax, [r8+4]
0x18007a005  add     r15, r8
0x18007a008  cmp     r15, rax
0x18007a00b  jnb     short loc_18007A017
0x18007a00d  mov     edx, 13A10h
0x18007a012  jmp     loc_180079DFF
0x18007a017  mov     rax, [r9+rbx]
0x18007a01b  mov     rdx, r15
0x18007a01e  mov     rcx, rsi
0x18007a021  mov     eax, [rax+4]
0x18007a024  mov     [rbp+arg_0], eax
0x18007a027  mov     rax, [rsi+78h]
0x18007a02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a030  mov     rcx, [rsi+70h]
0x18007a034  movzx   r13d, ax
0x18007a038  mov     rax, [rbp+var_20]
0x18007a03c  mov     rax, [rax+88h]
0x18007a043  mov     [rbp+var_20], rax
0x18007a047  call    sqlite3PagerWrite
0x18007a04c  mov     [rbp+arg_10], eax
0x18007a04f  test    eax, eax
0x18007a051  jnz     short loc_18007A07F
0x18007a053  mov     eax, [rbp+arg_0]
0x18007a056  lea     r8, [r15-4]
0x18007a05a  mov     r15d, [rbp+arg_18]
0x18007a05e  lea     r9d, [r13+4]
0x18007a062  mov     [rsp+50h+var_28], eax
0x18007a066  mov     edx, r15d
0x18007a069  mov     rax, [rbp+var_20]
0x18007a06d  mov     rcx, rdi
0x18007a070  mov     [rsp+50h+var_30], rax
0x18007a075  call    insertCell
0x18007a07a  mov     [rbp+arg_10], eax
0x18007a07d  jmp     short loc_18007A083
0x18007a07f  mov     r15d, [rbp+arg_18]
0x18007a083  movzx   edx, word ptr [rsi+18h]
0x18007a087  lea     r9, [rbp+arg_10]
0x18007a08b  dec     edx
0x18007a08d  mov     r8d, r13d
0x18007a090  mov     rcx, rsi
0x18007a093  call    dropCell
0x18007a098  mov     eax, [rbp+arg_10]
0x18007a09b  test    eax, eax
0x18007a09d  jnz     loc_18007A176
0x18007a0a3  mov     rax, [rbx+20h]
0x18007a0a7  mov     edx, [rax+38h]
0x18007a0aa  mov     rax, [rbx+88h]
0x18007a0b1  add     edx, edx
0x18007a0b3  mov     ecx, [rax+14h]
0x18007a0b6  lea     eax, [rcx+rcx*2]
0x18007a0b9  cmp     eax, edx
0x18007a0bb  jle     short loc_18007A0CF
0x18007a0bd  mov     rcx, rbx
0x18007a0c0  call    balance
0x18007a0c5  mov     esi, eax
0x18007a0c7  test    eax, eax
0x18007a0c9  jnz     loc_18007A174
0x18007a0cf  movsx   eax, byte ptr [rbx+54h]
0x18007a0d3  cmp     eax, r14d
0x18007a0d6  jle     short loc_18007A121
0x18007a0d8  mov     rcx, [rbx+88h]
0x18007a0df  mov     rcx, [rcx+70h]
0x18007a0e3  call    sqlite3PagerUnrefNotNull
0x18007a0e8  dec     byte ptr [rbx+54h]
0x18007a0eb  jmp     short loc_18007A0F7
0x18007a0ed  dec     dl
0x18007a0ef  mov     [rbx+54h], dl
0x18007a0f2  call    releasePage
0x18007a0f7  movsx   edx, byte ptr [rbx+54h]
0x18007a0fb  movsx   rax, dl
0x18007a0ff  mov     rcx, [rbx+rax*8+90h]
0x18007a107  cmp     edx, r14d
0x18007a10a  jg      short loc_18007A0ED
0x18007a10c  mov     [rbx+88h], rcx
0x18007a113  mov     rcx, rbx
0x18007a116  call    balance
0x18007a11b  mov     esi, eax
0x18007a11d  test    eax, eax
0x18007a11f  jnz     short loc_18007A174
0x18007a121  mov     ecx, 1
0x18007a126  cmp     r12b, cl
0x18007a129  jbe     short loc_18007A152
0x18007a12b  mov     byte ptr [rbx], 2
0x18007a12e  movzx   eax, word ptr [rdi+18h]
0x18007a132  cmp     r15d, eax
0x18007a135  jb      short loc_18007A14B
0x18007a137  mov     dword ptr [rbx+4], 0FFFFFFFFh
0x18007a13e  movzx   eax, word ptr [rdi+18h]
0x18007a142  sub     ax, cx
0x18007a145  mov     [rbx+56h], ax
0x18007a149  jmp     short loc_18007A14E
0x18007a14b  mov     [rbx+4], ecx
0x18007a14e  xor     esi, esi
0x18007a150  jmp     short loc_18007A174
0x18007a152  mov     rcx, rbx
0x18007a155  call    moveToRoot
0x18007a15a  mov     esi, eax
0x18007a15c  test    r12b, r12b
0x18007a15f  jz      short loc_18007A16C
0x18007a161  mov     rcx, rbx
0x18007a164  call    btreeReleaseAllCursorPages
0x18007a169  mov     byte ptr [rbx], 3
0x18007a16c  xor     ecx, ecx
0x18007a16e  cmp     esi, 10h
0x18007a171  cmovz   esi, ecx
0x18007a174  mov     eax, esi
0x18007a176  mov     rbx, [rsp+50h+arg_8]
0x18007a17e  add     rsp, 50h
0x18007a182  pop     r15
0x18007a184  pop     r14
0x18007a186  pop     r13
0x18007a188  pop     r12
0x18007a18a  pop     rdi
0x18007a18b  pop     rsi
0x18007a18c  pop     rbp
0x18007a18d  retn
```
