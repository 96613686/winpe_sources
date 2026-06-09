# sqlite3_complete

- ea: `0x180093d10`
- end: `0x180093fcd`
- name: `sqlite3_complete`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180093fe0`

## callees

- `0x1800367a0`
- `0x18003a860`
- `0x180093d10`

## string_xrefs

- `0x180093ecf`: `create`
- `0x180093e7e`: `temporary`

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
    for ( i = 0; ; i = *((_BYTE *)&qword_1800BA5A0[i] + v7) )
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
                if ( (*((_BYTE *)&qword_1800ADE90 + v4) & 0x46) != 0 )
                {
                  for ( j = 1; (*((_BYTE *)&qword_1800ADE90 + v1[j]) & 0x46) != 0; ++j )
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
  sqlite3ReportError(21, 179517, "misuse");
  return 0;
}

```

## disassembly

```asm
0x180093d10  push    rbx
0x180093d12  push    rsi
0x180093d13  push    rdi
0x180093d14  push    r14
0x180093d16  push    r15
0x180093d18  sub     rsp, 20h
0x180093d1c  mov     rbx, rcx
0x180093d1f  test    rcx, rcx
0x180093d22  jnz     short loc_180093D3F
0x180093d24  lea     r8, aMisuse; "misuse"
0x180093d2b  mov     edx, 2BD3Dh
0x180093d30  lea     ecx, [rbx+15h]
0x180093d33  call    sqlite3ReportError
0x180093d38  xor     eax, eax
0x180093d3a  jmp     loc_180093FC1
0x180093d3f  mov     r15d, 2
0x180093d45  lea     r9, __ImageBase
0x180093d4c  xor     sil, sil
0x180093d4f  lea     r14d, [r15-1]
0x180093d53  movzx   r8d, byte ptr [rbx]
0x180093d57  test    r8b, r8b
0x180093d5a  jz      loc_180093FB9
0x180093d60  movsx   edx, r8b
0x180093d64  cmp     edx, 27h ; '''
0x180093d67  jg      short loc_180093DA3
0x180093d69  jz      loc_180093EFD
0x180093d6f  mov     ecx, edx
0x180093d71  sub     ecx, 9
0x180093d74  jz      loc_180093F9E
0x180093d7a  sub     ecx, r14d
0x180093d7d  jz      loc_180093F9E
0x180093d83  sub     ecx, r15d
0x180093d86  jz      loc_180093F9E
0x180093d8c  sub     ecx, r14d
0x180093d8f  jz      loc_180093F9E
0x180093d95  sub     ecx, 13h
0x180093d98  jz      loc_180093F9E
0x180093d9e  cmp     ecx, r15d
0x180093da1  jmp     short loc_180093DCA
0x180093da3  cmp     edx, 2Dh ; '-'
0x180093da6  jz      loc_180093F82
0x180093dac  cmp     edx, 2Fh ; '/'
0x180093daf  jz      loc_180093F45
0x180093db5  cmp     edx, 3Bh ; ';'
0x180093db8  jz      loc_180093F41
0x180093dbe  cmp     edx, 5Bh ; '['
0x180093dc1  jz      loc_180093F1C
0x180093dc7  cmp     edx, 60h ; '`'
0x180093dca  jz      loc_180093EFD
0x180093dd0  test    byte ptr [r8+r9+0ADE90h], 46h
0x180093dd9  jz      loc_180093F4B
0x180093ddf  movzx   eax, byte ptr [rbx+1]
0x180093de3  mov     edi, r14d
0x180093de6  test    byte ptr [rax+r9+0ADE90h], 46h
0x180093def  jz      short loc_180093E06
0x180093df1  add     edi, r14d
0x180093df4  movsxd  rax, edi
0x180093df7  movzx   ecx, byte ptr [rax+rbx]
0x180093dfb  test    byte ptr [rcx+r9+0ADE90h], 46h
0x180093e04  jnz     short loc_180093DF1
0x180093e06  mov     al, r8b
0x180093e09  cmp     r8b, 43h ; 'C'
0x180093e0d  jz      loc_180093EC7
0x180093e13  cmp     al, 45h ; 'E'
0x180093e15  jz      short loc_180093E87
0x180093e17  cmp     al, 54h ; 'T'
0x180093e19  jz      short loc_180093E2F
0x180093e1b  cmp     al, 63h ; 'c'
0x180093e1d  jz      loc_180093EC7
0x180093e23  cmp     al, 65h ; 'e'
0x180093e25  jz      short loc_180093E87
0x180093e27  cmp     al, 74h ; 't'
0x180093e29  jnz     loc_180093EE5
0x180093e2f  cmp     edi, 7
0x180093e32  jnz     short loc_180093E56
0x180093e34  mov     r8d, edi
0x180093e37  lea     rdx, aTrigger; "trigger"
0x180093e3e  mov     rcx, rbx
0x180093e41  call    sqlite3_strnicmp
0x180093e46  test    eax, eax
0x180093e48  jnz     loc_180093EE5
0x180093e4e  lea     edx, [rdi-1]
0x180093e51  jmp     loc_180093EE8
0x180093e56  cmp     edi, 4
0x180093e59  jnz     short loc_180093E76
0x180093e5b  mov     r8d, edi
0x180093e5e  lea     rdx, aTemp; "temp"
0x180093e65  mov     rcx, rbx
0x180093e68  call    sqlite3_strnicmp
0x180093e6d  test    eax, eax
0x180093e6f  jnz     short loc_180093EE5
0x180093e71  lea     edx, [rax+5]
0x180093e74  jmp     short loc_180093EE8
0x180093e76  cmp     edi, 9
0x180093e79  jnz     short loc_180093EE5
0x180093e7b  mov     r8d, edi
0x180093e7e  lea     rdx, aTemporary; "temporary"
0x180093e85  jmp     short loc_180093E65
0x180093e87  cmp     edi, 3
0x180093e8a  jnz     short loc_180093EA7
0x180093e8c  mov     r8d, edi
0x180093e8f  lea     rdx, aEnd; "end"
0x180093e96  mov     rcx, rbx
0x180093e99  call    sqlite3_strnicmp
0x180093e9e  test    eax, eax
0x180093ea0  jnz     short loc_180093EE5
0x180093ea2  lea     edx, [rdi+4]
0x180093ea5  jmp     short loc_180093EE8
0x180093ea7  cmp     edi, 7
0x180093eaa  jnz     short loc_180093EE5
0x180093eac  mov     r8d, edi
0x180093eaf  lea     rdx, aExplain_0; "explain"
0x180093eb6  mov     rcx, rbx
0x180093eb9  call    sqlite3_strnicmp
0x180093ebe  test    eax, eax
0x180093ec0  jnz     short loc_180093EE5
0x180093ec2  lea     edx, [rdi-4]
0x180093ec5  jmp     short loc_180093EE8
0x180093ec7  cmp     edi, 6
0x180093eca  jnz     short loc_180093EE5
0x180093ecc  mov     r8d, edi
0x180093ecf  lea     rdx, aCreate_0; "create"
0x180093ed6  mov     rcx, rbx
0x180093ed9  call    sqlite3_strnicmp
0x180093ede  lea     edx, [rdi-2]
0x180093ee1  test    eax, eax
0x180093ee3  jz      short loc_180093EE8
0x180093ee5  mov     rdx, r15
0x180093ee8  lea     eax, [rdi-1]
0x180093eeb  movsxd  rcx, eax
0x180093eee  lea     r9, __ImageBase
0x180093ef5  add     rbx, rcx
0x180093ef8  jmp     loc_180093FA1
0x180093efd  add     rbx, r14
0x180093f00  mov     al, [rbx]
0x180093f02  test    al, al
0x180093f04  jz      loc_180093D38
0x180093f0a  movsx   eax, al
0x180093f0d  cmp     eax, edx
0x180093f0f  jz      short loc_180093F36
0x180093f11  add     rbx, r14
0x180093f14  mov     al, [rbx]
0x180093f16  test    al, al
0x180093f18  jnz     short loc_180093F0A
0x180093f1a  jmp     short loc_180093F36
0x180093f1c  add     rbx, r14
0x180093f1f  mov     al, [rbx]
0x180093f21  test    al, al
0x180093f23  jz      loc_180093D38
0x180093f29  cmp     al, 5Dh ; ']'
0x180093f2b  jz      short loc_180093F36
0x180093f2d  add     rbx, r14
0x180093f30  mov     al, [rbx]
0x180093f32  test    al, al
0x180093f34  jnz     short loc_180093F29
0x180093f36  cmp     byte ptr [rbx], 0
0x180093f39  jz      loc_180093D38
0x180093f3f  jmp     short loc_180093F4B
0x180093f41  xor     edx, edx
0x180093f43  jmp     short loc_180093FA1
0x180093f45  cmp     byte ptr [rbx+1], 2Ah ; '*'
0x180093f49  jz      short loc_180093F50
0x180093f4b  mov     rdx, r15
0x180093f4e  jmp     short loc_180093FA1
0x180093f50  add     rbx, r15
0x180093f53  mov     cl, [rbx]
0x180093f55  test    cl, cl
0x180093f57  jz      loc_180093D38
0x180093f5d  lea     rax, [rbx+1]
0x180093f61  cmp     cl, 2Ah ; '*'
0x180093f64  jnz     short loc_180093F6B
0x180093f66  cmp     byte ptr [rax], 2Fh ; '/'
0x180093f69  jz      short loc_180093F74
0x180093f6b  mov     cl, [rax]
0x180093f6d  mov     rbx, rax
0x180093f70  test    cl, cl
0x180093f72  jnz     short loc_180093F5D
0x180093f74  cmp     byte ptr [rbx], 0
0x180093f77  jz      loc_180093D38
0x180093f7d  add     rbx, r14
0x180093f80  jmp     short loc_180093F9E
0x180093f82  cmp     byte ptr [rbx+1], 2Dh ; '-'
0x180093f86  jnz     short loc_180093F4B
0x180093f88  cmp     r8b, 0Ah
0x180093f8c  jz      short loc_180093F99
0x180093f8e  add     rbx, r14
0x180093f91  mov     r8b, [rbx]
0x180093f94  test    r8b, r8b
0x180093f97  jnz     short loc_180093F88
0x180093f99  cmp     byte ptr [rbx], 0
0x180093f9c  jz      short loc_180093FB9
0x180093f9e  mov     rdx, r14
0x180093fa1  movzx   eax, sil
0x180093fa5  add     rbx, r14
0x180093fa8  lea     rcx, [rdx+rax*8]
0x180093fac  mov     sil, [rcx+r9+0BA5A0h]
0x180093fb4  jmp     loc_180093D53
0x180093fb9  xor     eax, eax
0x180093fbb  cmp     sil, r14b
0x180093fbe  setz    al
0x180093fc1  add     rsp, 20h
0x180093fc5  pop     r15
0x180093fc7  pop     r14
0x180093fc9  pop     rdi
0x180093fca  pop     rsi
0x180093fcb  pop     rbx
0x180093fcc  retn
```
