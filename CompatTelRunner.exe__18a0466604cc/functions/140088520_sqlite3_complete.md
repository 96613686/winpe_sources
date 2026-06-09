# sqlite3_complete

- ea: `0x140088520`
- end: `0x1400887e5`
- name: `sqlite3_complete`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400887f0`

## callees

- `0x140063280`
- `0x140088520`
- `0x14008eb20`

## string_xrefs

- `0x1400886de`: `create`
- `0x14008868d`: `temporary`

## pseudocode

```c
_BOOL8 __fastcall sqlite3_complete(unsigned __int8 *a1)
{
  unsigned __int8 *v1; // rbx
  signed __int8 v3; // r8
  unsigned __int8 v4; // si
  bool v5; // zf
  int i; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  const char *v9; // rdx
  int v10; // eax
  char v11; // al
  char v12; // al
  char *v13; // rbx
  char v14; // cl
  char *v15; // rax
  unsigned __int8 v16; // al

  v1 = a1;
  if ( a1 )
  {
    v3 = *a1;
    v4 = 0;
    if ( !*a1 )
      return v4 == 1;
    while ( 1 )
    {
      if ( v3 > 39 )
      {
        switch ( v3 )
        {
          case '-':
            if ( v1[1] == 45 )
            {
              v16 = *v1;
              if ( !*v1 )
                return v4 == 1;
              do
              {
                if ( v16 == 10 )
                  break;
                v16 = *++v1;
              }
              while ( *v1 );
              if ( !*v1 )
                return v4 == 1;
LABEL_70:
              v7 = 1;
              goto LABEL_71;
            }
            goto LABEL_58;
          case '/':
            if ( v1[1] == 42 )
            {
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
              goto LABEL_70;
            }
            goto LABEL_58;
          case ';':
            v7 = 0;
            goto LABEL_71;
          case '[':
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
            goto LABEL_54;
        }
        v5 = v3 == 96;
      }
      else
      {
        if ( v3 == 39 )
          goto LABEL_47;
        if ( v3 == 9 || v3 == 10 || v3 == 12 || v3 == 13 || v3 == 32 )
          goto LABEL_70;
        v5 = v3 == 34;
      }
      if ( v5 )
      {
LABEL_47:
        v11 = *++v1;
        if ( !*v1 )
          return 0;
        do
        {
          if ( v11 == v3 )
            break;
          v11 = *++v1;
        }
        while ( *v1 );
LABEL_54:
        if ( !*v1 )
          return 0;
LABEL_58:
        v7 = 2;
        goto LABEL_71;
      }
      if ( (byte_1400B2300[*v1] & 0x46) == 0 )
        goto LABEL_58;
      for ( i = 1; (byte_1400B2300[v1[i]] & 0x46) != 0; ++i )
        ;
      if ( v3 == 67 )
      {
LABEL_43:
        if ( i == 6 )
        {
          v10 = sqlite3_strnicmp(v1, "create", 6);
          v7 = 4;
          if ( !v10 )
            goto LABEL_46;
        }
LABEL_45:
        v7 = 2;
        goto LABEL_46;
      }
      if ( v3 != 69 )
      {
        if ( v3 == 84 )
          goto LABEL_28;
        if ( v3 == 99 )
          goto LABEL_43;
        if ( v3 != 101 )
          break;
      }
      if ( i == 3 )
      {
        if ( (unsigned int)sqlite3_strnicmp(v1, "end", 3) )
          goto LABEL_45;
        v7 = 7;
      }
      else
      {
        if ( i != 7 || (unsigned int)sqlite3_strnicmp(v1, "explain", 7) )
          goto LABEL_45;
        v7 = 3;
      }
LABEL_46:
      v1 += i - 1;
LABEL_71:
      v3 = *++v1;
      v4 = *((_BYTE *)&qword_1400B5970[v4] + v7);
      if ( !*v1 )
        return v4 == 1;
    }
    if ( v3 != 116 )
      goto LABEL_45;
LABEL_28:
    if ( i == 7 )
    {
      if ( (unsigned int)sqlite3_strnicmp(v1, "trigger", 7) )
        goto LABEL_45;
      v7 = 6;
    }
    else
    {
      if ( i == 4 )
      {
        v8 = 4;
        v9 = "temp";
      }
      else
      {
        if ( i != 9 )
          goto LABEL_45;
        v8 = 9;
        v9 = "temporary";
      }
      if ( (unsigned int)sqlite3_strnicmp(v1, v9, v8) )
        goto LABEL_45;
      v7 = 5;
    }
    goto LABEL_46;
  }
  sqlite3MisuseError(176141);
  return 0;
}

```

## disassembly

```asm
0x140088520  push    rbx
0x140088522  push    rsi
0x140088523  push    rdi
0x140088524  push    r14
0x140088526  push    r15
0x140088528  sub     rsp, 20h
0x14008852c  mov     rbx, rcx
0x14008852f  test    rcx, rcx
0x140088532  jnz     short loc_140088545
0x140088534  mov     ecx, 2B00Dh
0x140088539  call    sqlite3MisuseError
0x14008853e  xor     eax, eax
0x140088540  jmp     loc_1400887D9
0x140088545  mov     r8b, [rcx]
0x140088548  xor     sil, sil
0x14008854b  mov     r14d, 1
0x140088551  test    r8b, r8b
0x140088554  jz      loc_1400887D1
0x14008855a  lea     r15d, [r14+1]
0x14008855e  lea     r9, __ImageBase
0x140088565  movsx   edx, r8b
0x140088569  cmp     edx, 27h ; '''
0x14008856c  jg      short loc_1400885A8
0x14008856e  jz      loc_14008870C
0x140088574  mov     ecx, edx
0x140088576  sub     ecx, 9
0x140088579  jz      loc_1400887AF
0x14008857f  sub     ecx, r14d
0x140088582  jz      loc_1400887AF
0x140088588  sub     ecx, r15d
0x14008858b  jz      loc_1400887AF
0x140088591  sub     ecx, r14d
0x140088594  jz      loc_1400887AF
0x14008859a  sub     ecx, 13h
0x14008859d  jz      loc_1400887AF
0x1400885a3  cmp     ecx, r15d
0x1400885a6  jmp     short loc_1400885CF
0x1400885a8  cmp     edx, 2Dh ; '-'
0x1400885ab  jz      loc_140088791
0x1400885b1  cmp     edx, 2Fh ; '/'
0x1400885b4  jz      loc_140088754
0x1400885ba  cmp     edx, 3Bh ; ';'
0x1400885bd  jz      loc_140088750
0x1400885c3  cmp     edx, 5Bh ; '['
0x1400885c6  jz      loc_14008872B
0x1400885cc  cmp     edx, 60h ; '`'
0x1400885cf  jz      loc_14008870C
0x1400885d5  movzx   eax, byte ptr [rbx]
0x1400885d8  test    byte ptr [rax+r9+0B2300h], 46h
0x1400885e1  jz      loc_14008875A
0x1400885e7  movzx   eax, byte ptr [rbx+1]
0x1400885eb  mov     edi, r14d
0x1400885ee  test    byte ptr [rax+r9+0B2300h], 46h
0x1400885f7  jz      short loc_14008860E
0x1400885f9  add     edi, r14d
0x1400885fc  movsxd  rax, edi
0x1400885ff  movzx   ecx, byte ptr [rax+rbx]
0x140088603  test    byte ptr [rcx+r9+0B2300h], 46h
0x14008860c  jnz     short loc_1400885F9
0x14008860e  cmp     r8b, 43h ; 'C'
0x140088612  jz      loc_1400886D6
0x140088618  cmp     r8b, 45h ; 'E'
0x14008861c  jz      short loc_140088696
0x14008861e  cmp     r8b, 54h ; 'T'
0x140088622  jz      short loc_14008863E
0x140088624  cmp     r8b, 63h ; 'c'
0x140088628  jz      loc_1400886D6
0x14008862e  cmp     r8b, 65h ; 'e'
0x140088632  jz      short loc_140088696
0x140088634  cmp     r8b, 74h ; 't'
0x140088638  jnz     loc_1400886F4
0x14008863e  cmp     edi, 7
0x140088641  jnz     short loc_140088665
0x140088643  mov     r8d, edi
0x140088646  lea     rdx, aTrigger; "trigger"
0x14008864d  mov     rcx, rbx
0x140088650  call    sqlite3_strnicmp
0x140088655  test    eax, eax
0x140088657  jnz     loc_1400886F4
0x14008865d  lea     edx, [rdi-1]
0x140088660  jmp     loc_1400886F7
0x140088665  cmp     edi, 4
0x140088668  jnz     short loc_140088685
0x14008866a  mov     r8d, edi
0x14008866d  lea     rdx, aTemp_0; "temp"
0x140088674  mov     rcx, rbx
0x140088677  call    sqlite3_strnicmp
0x14008867c  test    eax, eax
0x14008867e  jnz     short loc_1400886F4
0x140088680  lea     edx, [rax+5]
0x140088683  jmp     short loc_1400886F7
0x140088685  cmp     edi, 9
0x140088688  jnz     short loc_1400886F4
0x14008868a  mov     r8d, edi
0x14008868d  lea     rdx, aTemporary; "temporary"
0x140088694  jmp     short loc_140088674
0x140088696  cmp     edi, 3
0x140088699  jnz     short loc_1400886B6
0x14008869b  mov     r8d, edi
0x14008869e  lea     rdx, aEnd; "end"
0x1400886a5  mov     rcx, rbx
0x1400886a8  call    sqlite3_strnicmp
0x1400886ad  test    eax, eax
0x1400886af  jnz     short loc_1400886F4
0x1400886b1  lea     edx, [rdi+4]
0x1400886b4  jmp     short loc_1400886F7
0x1400886b6  cmp     edi, 7
0x1400886b9  jnz     short loc_1400886F4
0x1400886bb  mov     r8d, edi
0x1400886be  lea     rdx, aExplain_0; "explain"
0x1400886c5  mov     rcx, rbx
0x1400886c8  call    sqlite3_strnicmp
0x1400886cd  test    eax, eax
0x1400886cf  jnz     short loc_1400886F4
0x1400886d1  lea     edx, [rdi-4]
0x1400886d4  jmp     short loc_1400886F7
0x1400886d6  cmp     edi, 6
0x1400886d9  jnz     short loc_1400886F4
0x1400886db  mov     r8d, edi
0x1400886de  lea     rdx, aCreate_0; "create"
0x1400886e5  mov     rcx, rbx
0x1400886e8  call    sqlite3_strnicmp
0x1400886ed  lea     edx, [rdi-2]
0x1400886f0  test    eax, eax
0x1400886f2  jz      short loc_1400886F7
0x1400886f4  mov     rdx, r15
0x1400886f7  lea     eax, [rdi-1]
0x1400886fa  movsxd  rcx, eax
0x1400886fd  lea     r9, __ImageBase
0x140088704  add     rbx, rcx
0x140088707  jmp     loc_1400887B2
0x14008870c  add     rbx, r14
0x14008870f  mov     al, [rbx]
0x140088711  test    al, al
0x140088713  jz      loc_14008853E
0x140088719  movsx   eax, al
0x14008871c  cmp     eax, edx
0x14008871e  jz      short loc_140088745
0x140088720  add     rbx, r14
0x140088723  mov     al, [rbx]
0x140088725  test    al, al
0x140088727  jnz     short loc_140088719
0x140088729  jmp     short loc_140088745
0x14008872b  add     rbx, r14
0x14008872e  mov     al, [rbx]
0x140088730  test    al, al
0x140088732  jz      loc_14008853E
0x140088738  cmp     al, 5Dh ; ']'
0x14008873a  jz      short loc_140088745
0x14008873c  add     rbx, r14
0x14008873f  mov     al, [rbx]
0x140088741  test    al, al
0x140088743  jnz     short loc_140088738
0x140088745  cmp     byte ptr [rbx], 0
0x140088748  jz      loc_14008853E
0x14008874e  jmp     short loc_14008875A
0x140088750  xor     edx, edx
0x140088752  jmp     short loc_1400887B2
0x140088754  cmp     byte ptr [rbx+1], 2Ah ; '*'
0x140088758  jz      short loc_14008875F
0x14008875a  mov     rdx, r15
0x14008875d  jmp     short loc_1400887B2
0x14008875f  add     rbx, r15
0x140088762  mov     cl, [rbx]
0x140088764  test    cl, cl
0x140088766  jz      loc_14008853E
0x14008876c  lea     rax, [rbx+1]
0x140088770  cmp     cl, 2Ah ; '*'
0x140088773  jnz     short loc_14008877A
0x140088775  cmp     byte ptr [rax], 2Fh ; '/'
0x140088778  jz      short loc_140088783
0x14008877a  mov     cl, [rax]
0x14008877c  mov     rbx, rax
0x14008877f  test    cl, cl
0x140088781  jnz     short loc_14008876C
0x140088783  cmp     byte ptr [rbx], 0
0x140088786  jz      loc_14008853E
0x14008878c  add     rbx, r14
0x14008878f  jmp     short loc_1400887AF
0x140088791  cmp     byte ptr [rbx+1], 2Dh ; '-'
0x140088795  jnz     short loc_14008875A
0x140088797  mov     al, [rbx]
0x140088799  test    al, al
0x14008879b  jz      short loc_1400887D1
0x14008879d  cmp     al, 0Ah
0x14008879f  jz      short loc_1400887AA
0x1400887a1  add     rbx, r14
0x1400887a4  mov     al, [rbx]
0x1400887a6  test    al, al
0x1400887a8  jnz     short loc_14008879D
0x1400887aa  cmp     byte ptr [rbx], 0
0x1400887ad  jz      short loc_1400887D1
0x1400887af  mov     rdx, r14
0x1400887b2  add     rbx, r14
0x1400887b5  movzx   eax, sil
0x1400887b9  mov     r8b, [rbx]
0x1400887bc  lea     rcx, [rdx+rax*8]
0x1400887c0  mov     sil, [rcx+r9+0B5970h]
0x1400887c8  test    r8b, r8b
0x1400887cb  jnz     loc_140088565
0x1400887d1  xor     eax, eax
0x1400887d3  cmp     sil, r14b
0x1400887d6  setz    al
0x1400887d9  add     rsp, 20h
0x1400887dd  pop     r15
0x1400887df  pop     r14
0x1400887e1  pop     rdi
0x1400887e2  pop     rsi
0x1400887e3  pop     rbx
0x1400887e4  retn
```
