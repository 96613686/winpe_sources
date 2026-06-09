# sqlite3_complete

- ea: `0x18009afc0`
- end: `0x18009b27d`
- name: `sqlite3_complete`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18009b290`

## callees

- `0x18002619c`
- `0x18003d760`
- `0x18009afc0`

## string_xrefs

- `0x18009b17f`: `create`
- `0x18009b12e`: `temporary`

## pseudocode

```c
_BOOL8 __fastcall sqlite3_complete(unsigned __int8 *a1)
{
  unsigned __int8 *v1; // rbx
  unsigned __int8 i; // si
  __int64 v4; // r8
  bool v5; // zf
  int j; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  const char *v9; // rdx
  int v10; // eax
  char v11; // al
  char v12; // al
  char *v13; // rbx
  char v14; // cl
  char *v15; // rax

  v1 = a1;
  if ( a1 )
  {
    for ( i = 0; ; i = *((_BYTE *)&qword_1800C1160[i] + v7) )
    {
      v4 = *v1;
      if ( !(_BYTE)v4 )
        return i == 1;
      if ( (char)v4 > 39 )
      {
        if ( (char)v4 == 45 )
        {
          if ( v1[1] != 45 )
            goto LABEL_59;
          do
          {
            if ( (_BYTE)v4 == 10 )
              break;
            LOBYTE(v4) = *++v1;
          }
          while ( *v1 );
          if ( !*v1 )
            return i == 1;
        }
        else
        {
          if ( (char)v4 != 47 )
          {
            if ( (char)v4 == 59 )
            {
              v7 = 0;
              goto LABEL_71;
            }
            if ( (char)v4 == 91 )
            {
              v12 = *++v1;
              if ( !*v1 )
                return 0;
              do
              {
                if ( v12 == 93 )
                  break;
                v12 = *++v1;
              }
              while ( *v1 );
            }
            else
            {
              v5 = (char)v4 == 96;
LABEL_19:
              if ( !v5 )
              {
                if ( (*((_BYTE *)&qword_1800B4FF0 + v4) & 0x46) != 0 )
                {
                  for ( j = 1; (*((_BYTE *)&qword_1800B4FF0 + v1[j]) & 0x46) != 0; ++j )
                    ;
                  if ( (_BYTE)v4 != 67 )
                  {
                    if ( (_BYTE)v4 == 69 )
                      goto LABEL_38;
                    if ( (_BYTE)v4 == 84 )
                      goto LABEL_29;
                    if ( (_BYTE)v4 != 99 )
                    {
                      if ( (_BYTE)v4 != 101 )
                      {
                        if ( (_BYTE)v4 == 116 )
                        {
LABEL_29:
                          if ( j == 7 )
                          {
                            if ( !(unsigned int)sqlite3_strnicmp(v1, "trigger", 7) )
                            {
                              v7 = 6;
LABEL_47:
                              v1 += j - 1;
                              goto LABEL_71;
                            }
                          }
                          else
                          {
                            if ( j == 4 )
                            {
                              v8 = 4;
                              v9 = "temp";
                            }
                            else
                            {
                              if ( j != 9 )
                                goto LABEL_46;
                              v8 = 9;
                              v9 = "temporary";
                            }
                            if ( !(unsigned int)sqlite3_strnicmp(v1, v9, v8) )
                            {
                              v7 = 5;
                              goto LABEL_47;
                            }
                          }
                        }
LABEL_46:
                        v7 = 2;
                        goto LABEL_47;
                      }
LABEL_38:
                      if ( j == 3 )
                      {
                        if ( !(unsigned int)sqlite3_strnicmp(v1, "end", 3) )
                        {
                          v7 = 7;
                          goto LABEL_47;
                        }
                      }
                      else if ( j == 7 && !(unsigned int)sqlite3_strnicmp(v1, "explain", 7) )
                      {
                        v7 = 3;
                        goto LABEL_47;
                      }
                      goto LABEL_46;
                    }
                  }
                  if ( j == 6 )
                  {
                    v10 = sqlite3_strnicmp(v1, "create", 6);
                    v7 = 4;
                    if ( !v10 )
                      goto LABEL_47;
                  }
                  goto LABEL_46;
                }
                goto LABEL_59;
              }
LABEL_48:
              v11 = *++v1;
              if ( !*v1 )
                return 0;
              do
              {
                if ( v11 == (char)v4 )
                  break;
                v11 = *++v1;
              }
              while ( *v1 );
            }
            if ( !*v1 )
              return 0;
LABEL_59:
            v7 = 2;
            goto LABEL_71;
          }
          if ( v1[1] != 42 )
            goto LABEL_59;
          v13 = (char *)(v1 + 2);
          v14 = *v13;
          if ( !*v13 )
            return 0;
          do
          {
            v15 = v13 + 1;
            if ( v14 == 42 && *v15 == 47 )
              break;
            v14 = *v15;
            ++v13;
          }
          while ( *v15 );
          if ( !*v13 )
            return 0;
          v1 = (unsigned __int8 *)(v13 + 1);
        }
      }
      else
      {
        if ( (char)v4 == 39 )
          goto LABEL_48;
        if ( (char)v4 != 9 && (char)v4 != 10 && (char)v4 != 12 && (char)v4 != 13 && (char)v4 != 32 )
        {
          v5 = (char)v4 == 34;
          goto LABEL_19;
        }
      }
      v7 = 1;
LABEL_71:
      ++v1;
    }
  }
  sqlite3ReportError(21, 179948, "misuse");
  return 0;
}

```

## disassembly

```asm
0x18009afc0  push    rbx
0x18009afc2  push    rsi
0x18009afc3  push    rdi
0x18009afc4  push    r14
0x18009afc6  push    r15
0x18009afc8  sub     rsp, 20h
0x18009afcc  mov     rbx, rcx
0x18009afcf  test    rcx, rcx
0x18009afd2  jnz     short loc_18009AFEF
0x18009afd4  lea     r8, aMisuse; "misuse"
0x18009afdb  mov     edx, 2BEECh
0x18009afe0  lea     ecx, [rbx+15h]
0x18009afe3  call    sqlite3ReportError
0x18009afe8  xor     eax, eax
0x18009afea  jmp     loc_18009B271
0x18009afef  mov     r15d, 2
0x18009aff5  lea     r9, __ImageBase
0x18009affc  xor     sil, sil
0x18009afff  lea     r14d, [r15-1]
0x18009b003  movzx   r8d, byte ptr [rbx]
0x18009b007  test    r8b, r8b
0x18009b00a  jz      loc_18009B269
0x18009b010  movsx   edx, r8b
0x18009b014  cmp     edx, 27h ; '''
0x18009b017  jg      short loc_18009B053
0x18009b019  jz      loc_18009B1AD
0x18009b01f  mov     ecx, edx
0x18009b021  sub     ecx, 9
0x18009b024  jz      loc_18009B24E
0x18009b02a  sub     ecx, r14d
0x18009b02d  jz      loc_18009B24E
0x18009b033  sub     ecx, r15d
0x18009b036  jz      loc_18009B24E
0x18009b03c  sub     ecx, r14d
0x18009b03f  jz      loc_18009B24E
0x18009b045  sub     ecx, 13h
0x18009b048  jz      loc_18009B24E
0x18009b04e  cmp     ecx, r15d
0x18009b051  jmp     short loc_18009B07A
0x18009b053  cmp     edx, 2Dh ; '-'
0x18009b056  jz      loc_18009B232
0x18009b05c  cmp     edx, 2Fh ; '/'
0x18009b05f  jz      loc_18009B1F5
0x18009b065  cmp     edx, 3Bh ; ';'
0x18009b068  jz      loc_18009B1F1
0x18009b06e  cmp     edx, 5Bh ; '['
0x18009b071  jz      loc_18009B1CC
0x18009b077  cmp     edx, 60h ; '`'
0x18009b07a  jz      loc_18009B1AD
0x18009b080  test    byte ptr [r8+r9+0B4FF0h], 46h
0x18009b089  jz      loc_18009B1FB
0x18009b08f  movzx   eax, byte ptr [rbx+1]
0x18009b093  mov     edi, r14d
0x18009b096  test    byte ptr [rax+r9+0B4FF0h], 46h
0x18009b09f  jz      short loc_18009B0B6
0x18009b0a1  add     edi, r14d
0x18009b0a4  movsxd  rax, edi
0x18009b0a7  movzx   ecx, byte ptr [rax+rbx]
0x18009b0ab  test    byte ptr [rcx+r9+0B4FF0h], 46h
0x18009b0b4  jnz     short loc_18009B0A1
0x18009b0b6  mov     al, r8b
0x18009b0b9  cmp     r8b, 43h ; 'C'
0x18009b0bd  jz      loc_18009B177
0x18009b0c3  cmp     al, 45h ; 'E'
0x18009b0c5  jz      short loc_18009B137
0x18009b0c7  cmp     al, 54h ; 'T'
0x18009b0c9  jz      short loc_18009B0DF
0x18009b0cb  cmp     al, 63h ; 'c'
0x18009b0cd  jz      loc_18009B177
0x18009b0d3  cmp     al, 65h ; 'e'
0x18009b0d5  jz      short loc_18009B137
0x18009b0d7  cmp     al, 74h ; 't'
0x18009b0d9  jnz     loc_18009B195
0x18009b0df  cmp     edi, 7
0x18009b0e2  jnz     short loc_18009B106
0x18009b0e4  mov     r8d, edi
0x18009b0e7  lea     rdx, aTrigger; "trigger"
0x18009b0ee  mov     rcx, rbx
0x18009b0f1  call    sqlite3_strnicmp
0x18009b0f6  test    eax, eax
0x18009b0f8  jnz     loc_18009B195
0x18009b0fe  lea     edx, [rdi-1]
0x18009b101  jmp     loc_18009B198
0x18009b106  cmp     edi, 4
0x18009b109  jnz     short loc_18009B126
0x18009b10b  mov     r8d, edi
0x18009b10e  lea     rdx, aTemp; "temp"
0x18009b115  mov     rcx, rbx
0x18009b118  call    sqlite3_strnicmp
0x18009b11d  test    eax, eax
0x18009b11f  jnz     short loc_18009B195
0x18009b121  lea     edx, [rax+5]
0x18009b124  jmp     short loc_18009B198
0x18009b126  cmp     edi, 9
0x18009b129  jnz     short loc_18009B195
0x18009b12b  mov     r8d, edi
0x18009b12e  lea     rdx, aTemporary; "temporary"
0x18009b135  jmp     short loc_18009B115
0x18009b137  cmp     edi, 3
0x18009b13a  jnz     short loc_18009B157
0x18009b13c  mov     r8d, edi
0x18009b13f  lea     rdx, aEnd; "end"
0x18009b146  mov     rcx, rbx
0x18009b149  call    sqlite3_strnicmp
0x18009b14e  test    eax, eax
0x18009b150  jnz     short loc_18009B195
0x18009b152  lea     edx, [rdi+4]
0x18009b155  jmp     short loc_18009B198
0x18009b157  cmp     edi, 7
0x18009b15a  jnz     short loc_18009B195
0x18009b15c  mov     r8d, edi
0x18009b15f  lea     rdx, aExplain_0; "explain"
0x18009b166  mov     rcx, rbx
0x18009b169  call    sqlite3_strnicmp
0x18009b16e  test    eax, eax
0x18009b170  jnz     short loc_18009B195
0x18009b172  lea     edx, [rdi-4]
0x18009b175  jmp     short loc_18009B198
0x18009b177  cmp     edi, 6
0x18009b17a  jnz     short loc_18009B195
0x18009b17c  mov     r8d, edi
0x18009b17f  lea     rdx, aCreate_0; "create"
0x18009b186  mov     rcx, rbx
0x18009b189  call    sqlite3_strnicmp
0x18009b18e  lea     edx, [rdi-2]
0x18009b191  test    eax, eax
0x18009b193  jz      short loc_18009B198
0x18009b195  mov     rdx, r15
0x18009b198  lea     eax, [rdi-1]
0x18009b19b  movsxd  rcx, eax
0x18009b19e  lea     r9, __ImageBase
0x18009b1a5  add     rbx, rcx
0x18009b1a8  jmp     loc_18009B251
0x18009b1ad  add     rbx, r14
0x18009b1b0  mov     al, [rbx]
0x18009b1b2  test    al, al
0x18009b1b4  jz      loc_18009AFE8
0x18009b1ba  movsx   eax, al
0x18009b1bd  cmp     eax, edx
0x18009b1bf  jz      short loc_18009B1E6
0x18009b1c1  add     rbx, r14
0x18009b1c4  mov     al, [rbx]
0x18009b1c6  test    al, al
0x18009b1c8  jnz     short loc_18009B1BA
0x18009b1ca  jmp     short loc_18009B1E6
0x18009b1cc  add     rbx, r14
0x18009b1cf  mov     al, [rbx]
0x18009b1d1  test    al, al
0x18009b1d3  jz      loc_18009AFE8
0x18009b1d9  cmp     al, 5Dh ; ']'
0x18009b1db  jz      short loc_18009B1E6
0x18009b1dd  add     rbx, r14
0x18009b1e0  mov     al, [rbx]
0x18009b1e2  test    al, al
0x18009b1e4  jnz     short loc_18009B1D9
0x18009b1e6  cmp     byte ptr [rbx], 0
0x18009b1e9  jz      loc_18009AFE8
0x18009b1ef  jmp     short loc_18009B1FB
0x18009b1f1  xor     edx, edx
0x18009b1f3  jmp     short loc_18009B251
0x18009b1f5  cmp     byte ptr [rbx+1], 2Ah ; '*'
0x18009b1f9  jz      short loc_18009B200
0x18009b1fb  mov     rdx, r15
0x18009b1fe  jmp     short loc_18009B251
0x18009b200  add     rbx, r15
0x18009b203  mov     cl, [rbx]
0x18009b205  test    cl, cl
0x18009b207  jz      loc_18009AFE8
0x18009b20d  lea     rax, [rbx+1]
0x18009b211  cmp     cl, 2Ah ; '*'
0x18009b214  jnz     short loc_18009B21B
0x18009b216  cmp     byte ptr [rax], 2Fh ; '/'
0x18009b219  jz      short loc_18009B224
0x18009b21b  mov     cl, [rax]
0x18009b21d  mov     rbx, rax
0x18009b220  test    cl, cl
0x18009b222  jnz     short loc_18009B20D
0x18009b224  cmp     byte ptr [rbx], 0
0x18009b227  jz      loc_18009AFE8
0x18009b22d  add     rbx, r14
0x18009b230  jmp     short loc_18009B24E
0x18009b232  cmp     byte ptr [rbx+1], 2Dh ; '-'
0x18009b236  jnz     short loc_18009B1FB
0x18009b238  cmp     r8b, 0Ah
0x18009b23c  jz      short loc_18009B249
0x18009b23e  add     rbx, r14
0x18009b241  mov     r8b, [rbx]
0x18009b244  test    r8b, r8b
0x18009b247  jnz     short loc_18009B238
0x18009b249  cmp     byte ptr [rbx], 0
0x18009b24c  jz      short loc_18009B269
0x18009b24e  mov     rdx, r14
0x18009b251  movzx   eax, sil
0x18009b255  add     rbx, r14
0x18009b258  lea     rcx, [rdx+rax*8]
0x18009b25c  mov     sil, [rcx+r9+0C1160h]
0x18009b264  jmp     loc_18009B003
0x18009b269  xor     eax, eax
0x18009b26b  cmp     sil, r14b
0x18009b26e  setz    al
0x18009b271  add     rsp, 20h
0x18009b275  pop     r15
0x18009b277  pop     r14
0x18009b279  pop     rdi
0x18009b27a  pop     rsi
0x18009b27b  pop     rbx
0x18009b27c  retn
```
