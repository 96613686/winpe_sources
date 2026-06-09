# sqlite3_complete

- ea: `0x18008d420`
- end: `0x18008d6dd`
- name: `sqlite3_complete`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008d6f0`

## callees

- `0x18004b050`
- `0x180060134`
- `0x18008d420`

## string_xrefs

- `0x18008d5df`: `create`
- `0x18008d58e`: `temporary`

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
    for ( i = 0; ; i = *((_BYTE *)&qword_1800AA7B0[i] + v7) )
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
                if ( (*((_BYTE *)&qword_18009E630 + v4) & 0x46) != 0 )
                {
                  for ( j = 1; (*((_BYTE *)&qword_18009E630 + v1[j]) & 0x46) != 0; ++j )
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
  sqlite3ReportError(21, 180869, "misuse");
  return 0;
}

```

## disassembly

```asm
0x18008d420  push    rbx
0x18008d422  push    rsi
0x18008d423  push    rdi
0x18008d424  push    r14
0x18008d426  push    r15
0x18008d428  sub     rsp, 20h
0x18008d42c  mov     rbx, rcx
0x18008d42f  test    rcx, rcx
0x18008d432  jnz     short loc_18008D44F
0x18008d434  lea     r8, aMisuse; "misuse"
0x18008d43b  mov     edx, 2C285h
0x18008d440  lea     ecx, [rbx+15h]
0x18008d443  call    sqlite3ReportError
0x18008d448  xor     eax, eax
0x18008d44a  jmp     loc_18008D6D1
0x18008d44f  mov     r15d, 2
0x18008d455  lea     r9, cs:180000000h
0x18008d45c  xor     sil, sil
0x18008d45f  lea     r14d, [r15-1]
0x18008d463  movzx   r8d, byte ptr [rbx]
0x18008d467  test    r8b, r8b
0x18008d46a  jz      loc_18008D6C9
0x18008d470  movsx   edx, r8b
0x18008d474  cmp     edx, 27h ; '''
0x18008d477  jg      short loc_18008D4B3
0x18008d479  jz      loc_18008D60D
0x18008d47f  mov     ecx, edx
0x18008d481  sub     ecx, 9
0x18008d484  jz      loc_18008D6AE
0x18008d48a  sub     ecx, r14d
0x18008d48d  jz      loc_18008D6AE
0x18008d493  sub     ecx, r15d
0x18008d496  jz      loc_18008D6AE
0x18008d49c  sub     ecx, r14d
0x18008d49f  jz      loc_18008D6AE
0x18008d4a5  sub     ecx, 13h
0x18008d4a8  jz      loc_18008D6AE
0x18008d4ae  cmp     ecx, r15d
0x18008d4b1  jmp     short loc_18008D4DA
0x18008d4b3  cmp     edx, 2Dh ; '-'
0x18008d4b6  jz      loc_18008D692
0x18008d4bc  cmp     edx, 2Fh ; '/'
0x18008d4bf  jz      loc_18008D655
0x18008d4c5  cmp     edx, 3Bh ; ';'
0x18008d4c8  jz      loc_18008D651
0x18008d4ce  cmp     edx, 5Bh ; '['
0x18008d4d1  jz      loc_18008D62C
0x18008d4d7  cmp     edx, 60h ; '`'
0x18008d4da  jz      loc_18008D60D
0x18008d4e0  test    byte ptr [r8+r9+9E630h], 46h
0x18008d4e9  jz      loc_18008D65B
0x18008d4ef  movzx   eax, byte ptr [rbx+1]
0x18008d4f3  mov     edi, r14d
0x18008d4f6  test    byte ptr [rax+r9+9E630h], 46h
0x18008d4ff  jz      short loc_18008D516
0x18008d501  add     edi, r14d
0x18008d504  movsxd  rax, edi
0x18008d507  movzx   ecx, byte ptr [rax+rbx]
0x18008d50b  test    byte ptr [rcx+r9+9E630h], 46h
0x18008d514  jnz     short loc_18008D501
0x18008d516  mov     al, r8b
0x18008d519  cmp     r8b, 43h ; 'C'
0x18008d51d  jz      loc_18008D5D7
0x18008d523  cmp     al, 45h ; 'E'
0x18008d525  jz      short loc_18008D597
0x18008d527  cmp     al, 54h ; 'T'
0x18008d529  jz      short loc_18008D53F
0x18008d52b  cmp     al, 63h ; 'c'
0x18008d52d  jz      loc_18008D5D7
0x18008d533  cmp     al, 65h ; 'e'
0x18008d535  jz      short loc_18008D597
0x18008d537  cmp     al, 74h ; 't'
0x18008d539  jnz     loc_18008D5F5
0x18008d53f  cmp     edi, 7
0x18008d542  jnz     short loc_18008D566
0x18008d544  mov     r8d, edi
0x18008d547  lea     rdx, aTrigger; "trigger"
0x18008d54e  mov     rcx, rbx
0x18008d551  call    sqlite3_strnicmp
0x18008d556  test    eax, eax
0x18008d558  jnz     loc_18008D5F5
0x18008d55e  lea     edx, [rdi-1]
0x18008d561  jmp     loc_18008D5F8
0x18008d566  cmp     edi, 4
0x18008d569  jnz     short loc_18008D586
0x18008d56b  mov     r8d, edi
0x18008d56e  lea     rdx, aTemp; "temp"
0x18008d575  mov     rcx, rbx
0x18008d578  call    sqlite3_strnicmp
0x18008d57d  test    eax, eax
0x18008d57f  jnz     short loc_18008D5F5
0x18008d581  lea     edx, [rax+5]
0x18008d584  jmp     short loc_18008D5F8
0x18008d586  cmp     edi, 9
0x18008d589  jnz     short loc_18008D5F5
0x18008d58b  mov     r8d, edi
0x18008d58e  lea     rdx, aTemporary; "temporary"
0x18008d595  jmp     short loc_18008D575
0x18008d597  cmp     edi, 3
0x18008d59a  jnz     short loc_18008D5B7
0x18008d59c  mov     r8d, edi
0x18008d59f  lea     rdx, aEnd; "end"
0x18008d5a6  mov     rcx, rbx
0x18008d5a9  call    sqlite3_strnicmp
0x18008d5ae  test    eax, eax
0x18008d5b0  jnz     short loc_18008D5F5
0x18008d5b2  lea     edx, [rdi+4]
0x18008d5b5  jmp     short loc_18008D5F8
0x18008d5b7  cmp     edi, 7
0x18008d5ba  jnz     short loc_18008D5F5
0x18008d5bc  mov     r8d, edi
0x18008d5bf  lea     rdx, aExplain_0; "explain"
0x18008d5c6  mov     rcx, rbx
0x18008d5c9  call    sqlite3_strnicmp
0x18008d5ce  test    eax, eax
0x18008d5d0  jnz     short loc_18008D5F5
0x18008d5d2  lea     edx, [rdi-4]
0x18008d5d5  jmp     short loc_18008D5F8
0x18008d5d7  cmp     edi, 6
0x18008d5da  jnz     short loc_18008D5F5
0x18008d5dc  mov     r8d, edi
0x18008d5df  lea     rdx, aCreate_0; "create"
0x18008d5e6  mov     rcx, rbx
0x18008d5e9  call    sqlite3_strnicmp
0x18008d5ee  lea     edx, [rdi-2]
0x18008d5f1  test    eax, eax
0x18008d5f3  jz      short loc_18008D5F8
0x18008d5f5  mov     rdx, r15
0x18008d5f8  lea     eax, [rdi-1]
0x18008d5fb  movsxd  rcx, eax
0x18008d5fe  lea     r9, cs:180000000h
0x18008d605  add     rbx, rcx
0x18008d608  jmp     loc_18008D6B1
0x18008d60d  add     rbx, r14
0x18008d610  mov     al, [rbx]
0x18008d612  test    al, al
0x18008d614  jz      loc_18008D448
0x18008d61a  movsx   eax, al
0x18008d61d  cmp     eax, edx
0x18008d61f  jz      short loc_18008D646
0x18008d621  add     rbx, r14
0x18008d624  mov     al, [rbx]
0x18008d626  test    al, al
0x18008d628  jnz     short loc_18008D61A
0x18008d62a  jmp     short loc_18008D646
0x18008d62c  add     rbx, r14
0x18008d62f  mov     al, [rbx]
0x18008d631  test    al, al
0x18008d633  jz      loc_18008D448
0x18008d639  cmp     al, 5Dh ; ']'
0x18008d63b  jz      short loc_18008D646
0x18008d63d  add     rbx, r14
0x18008d640  mov     al, [rbx]
0x18008d642  test    al, al
0x18008d644  jnz     short loc_18008D639
0x18008d646  cmp     byte ptr [rbx], 0
0x18008d649  jz      loc_18008D448
0x18008d64f  jmp     short loc_18008D65B
0x18008d651  xor     edx, edx
0x18008d653  jmp     short loc_18008D6B1
0x18008d655  cmp     byte ptr [rbx+1], 2Ah ; '*'
0x18008d659  jz      short loc_18008D660
0x18008d65b  mov     rdx, r15
0x18008d65e  jmp     short loc_18008D6B1
0x18008d660  add     rbx, r15
0x18008d663  mov     cl, [rbx]
0x18008d665  test    cl, cl
0x18008d667  jz      loc_18008D448
0x18008d66d  lea     rax, [rbx+1]
0x18008d671  cmp     cl, 2Ah ; '*'
0x18008d674  jnz     short loc_18008D67B
0x18008d676  cmp     byte ptr [rax], 2Fh ; '/'
0x18008d679  jz      short loc_18008D684
0x18008d67b  mov     cl, [rax]
0x18008d67d  mov     rbx, rax
0x18008d680  test    cl, cl
0x18008d682  jnz     short loc_18008D66D
0x18008d684  cmp     byte ptr [rbx], 0
0x18008d687  jz      loc_18008D448
0x18008d68d  add     rbx, r14
0x18008d690  jmp     short loc_18008D6AE
0x18008d692  cmp     byte ptr [rbx+1], 2Dh ; '-'
0x18008d696  jnz     short loc_18008D65B
0x18008d698  cmp     r8b, 0Ah
0x18008d69c  jz      short loc_18008D6A9
0x18008d69e  add     rbx, r14
0x18008d6a1  mov     r8b, [rbx]
0x18008d6a4  test    r8b, r8b
0x18008d6a7  jnz     short loc_18008D698
0x18008d6a9  cmp     byte ptr [rbx], 0
0x18008d6ac  jz      short loc_18008D6C9
0x18008d6ae  mov     rdx, r14
0x18008d6b1  movzx   eax, sil
0x18008d6b5  add     rbx, r14
0x18008d6b8  lea     rcx, [rdx+rax*8]
0x18008d6bc  mov     sil, [rcx+r9+0AA7B0h]
0x18008d6c4  jmp     loc_18008D463
0x18008d6c9  xor     eax, eax
0x18008d6cb  cmp     sil, r14b
0x18008d6ce  setz    al
0x18008d6d1  add     rsp, 20h
0x18008d6d5  pop     r15
0x18008d6d7  pop     r14
0x18008d6d9  pop     rdi
0x18008d6da  pop     rsi
0x18008d6db  pop     rbx
0x18008d6dc  retn
```
