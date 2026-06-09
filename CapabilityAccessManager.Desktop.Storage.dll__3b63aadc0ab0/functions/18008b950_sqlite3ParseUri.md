# sqlite3ParseUri

- ea: `0x18008b950`
- end: `0x18008bf58`
- name: `sqlite3ParseUri`
- size: `1544`
- prototype: `__int64 __usercall@<rax>(char *Str1@<rcx>, void *Src@<rdx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180017460`
- `0x180051310`

## callees

- `0x180005450`
- `0x180005980`
- `0x1800118a0`
- `0x180088560`
- `0x18008b950`
- `0x1800bf820`
- `0x1800e4dce`
- `0x1800e4df2`
- `0x1800e4dfe`

## string_xrefs

- `0x18008bab1`: `invalid uri authority: %.*s`
- `0x18008bc8f`: `cache`
- `0x18008bdf8`: `cache`
- `0x18008bd6b`: `access`

## pseudocode

```c
__int64 __fastcall sqlite3ParseUri(char *Str1, const char *Src, unsigned int *a3, __int64 *a4, char **a5, __int64 *a6)
{
  unsigned int v6; // r13d
  char *v8; // r15
  unsigned int v9; // edi
  __int64 v10; // rsi
  __int64 v11; // rbp
  __int64 v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  _DWORD *v16; // rax
  char *v17; // rdi
  int v18; // r13d
  int v19; // eax
  const char *v20; // r8
  unsigned int v21; // ebx
  __int64 v22; // rax
  int v23; // edi
  int v24; // r8d
  char v25; // dl
  __int64 v26; // r11
  __int64 v27; // r10
  __int64 v28; // r9
  int v29; // edx
  int v30; // eax
  char v31; // dl
  bool v32; // zf
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  size_t v36; // rax
  char *v37; // rbx
  size_t v38; // rdi
  const char *v39; // r12
  size_t v40; // rbp
  char **v41; // rsi
  int v42; // r15d
  int v43; // r13d
  int v44; // ebx
  char *v45; // rdi
  int v46; // eax
  int v47; // ecx
  int v48; // r15d
  __int64 v49; // rax
  _DWORD *v50; // rax
  char *v51; // rsi
  __int64 v52; // rax
  __int64 result; // rax
  char *Str; // [rsp+20h] [rbp-58h]
  const char *v55; // [rsp+28h] [rbp-50h]
  char *v56; // [rsp+80h] [rbp+8h]
  unsigned int v57; // [rsp+88h] [rbp+10h]

  v56 = Str1;
  v6 = *a3;
  v8 = Str1;
  if ( Src )
    v9 = strlen_0(Src) & 0x3FFFFFFF;
  else
    v9 = 0;
  if ( ((v6 & 0x40) != 0 || byte_18013C1B6) && v9 >= 5 && *(_DWORD *)Src == 1701603686 && Src[4] == 58 )
  {
    v10 = 0;
    v11 = v9 + 8;
    v12 = 0;
    LODWORD(v13) = 0;
    do
    {
      v14 = (int)v13;
      v10 += Src[(int)v13] == 38;
      v15 = Src[(int)v13 + 1] == 38;
      v13 = (unsigned int)(v13 + 2);
      v12 += v15;
    }
    while ( (int)v13 < (int)(v9 - 1) );
    if ( (int)v13 < (int)v9 )
    {
      v14 = Src[(int)v13] == 38;
      v11 += v14;
    }
    if ( !(unsigned int)sqlite3_initialize(v14, v13) )
    {
      v16 = (_DWORD *)sqlite3Malloc(v11 + v12 + v10);
      if ( v16 )
      {
        v17 = (char *)(v16 + 1);
        v18 = v6 | 0x40;
        *v16 = 0;
        v19 = 5;
        v57 = v18;
        Str = v17;
        if ( Src[5] == 47 && Src[6] == 47 )
        {
          v20 = Src + 7;
          v19 = 7;
          if ( Src[7] )
          {
            do
            {
              if ( Src[v19] == 47 )
                break;
              ++v19;
            }
            while ( Src[v19] );
            if ( v19 != 7 && (v19 != 16 || *(_QWORD *)v20 != 0x736F686C61636F6CLL || Src[15] != 116) )
            {
              v21 = 1;
              v22 = sqlite3_mprintf("invalid uri authority: %.*s", v19 - 7, v20);
              goto LABEL_99;
            }
          }
        }
        v23 = 0;
        v24 = 0;
        v25 = Src[v19];
        if ( v25 )
        {
          while ( 1 )
          {
            if ( v25 == 35 )
            {
LABEL_61:
              if ( v24 == 1 )
              {
                v34 = v23++;
                Str[v34] = 0;
              }
              goto LABEL_63;
            }
            v26 = v19++;
            if ( v25 == 37 )
            {
              v27 = (unsigned __int8)Src[v19];
              if ( (*((_BYTE *)&qword_1801147A0 + v27) & 8) != 0 )
              {
                v28 = (unsigned __int8)Src[v26 + 2];
                if ( (*((_BYTE *)&qword_1801147A0 + v28) & 8) != 0 )
                {
                  v29 = 16 * (((_BYTE)v27 - 7 * (((char)v27 >> 6) & 1)) & 0xF);
                  v30 = ((_BYTE)v28 - 7 * (((char)v28 >> 6) & 1)) & 0xF;
                  v32 = v30 + v29 == 0;
                  v25 = v30 + v29;
                  v19 = v26 + 3;
                  if ( v32 )
                  {
                    v31 = Src[v19];
                    if ( v31 )
                    {
                      while ( v31 != 35 )
                      {
                        if ( v24 )
                        {
                          if ( v24 == 1 && v31 == 61 )
                            goto LABEL_60;
                          v32 = v31 == 38;
                        }
                        else
                        {
                          v32 = v31 == 63;
                        }
                        if ( !v32 )
                        {
                          v31 = Src[++v19];
                          if ( v31 )
                            continue;
                        }
                        goto LABEL_60;
                      }
                    }
                    goto LABEL_60;
                  }
                  goto LABEL_59;
                }
              }
            }
            if ( v24 == 1 )
              break;
            if ( !v24 )
            {
              if ( v25 != 63 )
                goto LABEL_59;
LABEL_57:
              v24 = 1;
LABEL_58:
              v25 = 0;
              goto LABEL_59;
            }
            if ( v25 == 38 )
              goto LABEL_57;
LABEL_59:
            v33 = v23++;
            Str[v33] = v25;
LABEL_60:
            v25 = Src[v19];
            if ( !v25 )
              goto LABEL_61;
          }
          if ( v25 != 38 && v25 != 61 )
            goto LABEL_59;
          if ( !Str[v23 - 1] )
          {
            for ( ; Src[v19]; ++v19 )
            {
              if ( Src[v19] == 35 )
                break;
              if ( Src[v19 - 1] == 38 )
                break;
            }
            goto LABEL_60;
          }
          if ( v25 == 38 )
            Str[v23++] = 0;
          else
            v24 = 2;
          goto LABEL_58;
        }
LABEL_63:
        v35 = v23;
        v17 = Str;
        *(_DWORD *)&Str[v35] = 0;
        if ( Str )
          v36 = strlen_0(Str) & 0x3FFFFFFF;
        else
          v36 = 0;
        v37 = &Str[v36 + 1];
        if ( *v37 )
        {
          while ( 1 )
          {
            v38 = strlen_0(v37) & 0x3FFFFFFF;
            v39 = &v37[(unsigned int)(v38 + 1)];
            if ( v39 )
              v40 = strlen_0(v39) & 0x3FFFFFFF;
            else
              LODWORD(v40) = 0;
            if ( (_DWORD)v38 != 3 || *(_WORD *)v37 != 26230 || v37[2] != 115 )
              break;
            v8 = &v37[(unsigned int)(v38 + 1)];
            v56 = v8;
LABEL_95:
            v37 = (char *)&v39[(unsigned int)(v40 + 1)];
            if ( !*v37 )
            {
              v17 = Str;
              goto LABEL_97;
            }
          }
          v41 = 0;
          v42 = 0;
          v55 = 0;
          if ( (_DWORD)v38 == 5 )
          {
            if ( *(_DWORD *)v37 == 1751343459 && v37[4] == 101 )
            {
              v42 = 393216;
              v55 = "cache";
              v41 = &off_18013EED8;
            }
          }
          else if ( (_DWORD)v38 == 4 )
          {
            if ( *(_DWORD *)v37 == 1701080941 )
            {
              v42 = 135;
              v43 = v18 & 0x87;
              v55 = "access";
              v41 = &off_18013EF10;
LABEL_79:
              v44 = 0;
              if ( !*v41 )
                goto LABEL_89;
              while ( 1 )
              {
                v45 = v41[2 * v44];
                v46 = v45 ? strlen_0(v41[2 * v44]) & 0x3FFFFFFF : 0;
                if ( (_DWORD)v40 == v46 && !memcmp_0(v39, v45, (unsigned int)v40) )
                  break;
                if ( !v41[2 * ++v44] )
                  goto LABEL_89;
              }
              v47 = (int)v41[2 * v44 + 1];
              if ( !v47 )
              {
LABEL_89:
                v21 = 1;
                v22 = sqlite3_mprintf("no such %s mode: %s", v55, v39);
                v17 = Str;
                goto LABEL_99;
              }
              if ( (int)(v47 & 0xFFFFFF7F) > v43 )
              {
                v21 = 3;
                v22 = sqlite3_mprintf("%s mode not allowed: %s", v55, v39);
                v17 = Str;
LABEL_99:
                *a6 = v22;
                if ( v17 )
                {
                  while ( *(v17 - 1) || *(v17 - 2) || *(v17 - 3) || *(v17 - 4) )
                    --v17;
                  sqlite3_free(v17 - 4);
                }
                v17 = 0;
                goto LABEL_113;
              }
              v48 = ~v42;
              LOBYTE(v18) = v47 | v48 & v57;
              v57 = v47 | v48 & v57;
            }
LABEL_94:
            v8 = v56;
            goto LABEL_95;
          }
          v43 = v42;
          if ( v41 )
            goto LABEL_79;
          LOBYTE(v18) = v57;
          goto LABEL_94;
        }
        goto LABEL_97;
      }
    }
    return 7;
  }
  if ( (unsigned int)sqlite3_initialize(Str1, Src) )
    return 7;
  v50 = (_DWORD *)sqlite3Malloc(v9 + 8);
  if ( !v50 )
    return 7;
  v51 = (char *)(v50 + 1);
  *v50 = 0;
  if ( v9 )
    memcpy_0(v50 + 1, Src, v9);
  v52 = v9;
  v17 = v51;
  v57 = v6 & 0xFFFFFFBF;
  *(_DWORD *)&v51[v52] = 0;
LABEL_97:
  v21 = 0;
  v49 = sqlite3_vfs_find(v8);
  *a4 = v49;
  if ( !v49 )
  {
    v21 = 1;
    v22 = sqlite3_mprintf("no such vfs: %s", v8);
    goto LABEL_99;
  }
LABEL_113:
  *a3 = v57;
  result = v21;
  *a5 = v17;
  return result;
}

```

## disassembly

```asm
0x18008b950  mov     [rsp+arg_18], r9
0x18008b955  mov     [rsp+arg_10], r8
0x18008b95a  mov     [rsp+arg_0], rcx
0x18008b95f  push    rbx
0x18008b960  push    rdi
0x18008b961  push    r13
0x18008b963  push    r15
0x18008b965  sub     rsp, 58h
0x18008b969  mov     r13d, [r8]
0x18008b96c  mov     rbx, rdx
0x18008b96f  mov     r15, rcx
0x18008b972  test    rdx, rdx
0x18008b975  jnz     short loc_18008B97B
0x18008b977  xor     edi, edi
0x18008b979  jmp     short loc_18008B98C
0x18008b97b  mov     rcx, rbx; Str
0x18008b97e  call    strlen_0
0x18008b983  mov     rdi, rax
0x18008b986  and     edi, 3FFFFFFFh
0x18008b98c  mov     [rsp+78h+var_28], rbp
0x18008b991  mov     [rsp+78h+var_30], rsi
0x18008b996  mov     [rsp+78h+var_38], r12
0x18008b99b  mov     [rsp+78h+var_40], r14
0x18008b9a0  test    r13b, 40h
0x18008b9a4  jnz     short loc_18008B9B3
0x18008b9a6  cmp     cs:byte_18013C1B6, 0
0x18008b9ad  jz      loc_18008BEC2
0x18008b9b3  cmp     edi, 5
0x18008b9b6  jb      loc_18008BEC2
0x18008b9bc  cmp     dword ptr [rbx], 656C6966h
0x18008b9c2  jnz     loc_18008BEC2
0x18008b9c8  cmp     byte ptr [rbx+4], 3Ah ; ':'
0x18008b9cc  jnz     loc_18008BEC2
0x18008b9d2  xor     esi, esi
0x18008b9d4  lea     ebp, [rdi+8]
0x18008b9d7  xor     r14d, r14d
0x18008b9da  lea     r8d, [rdi-1]
0x18008b9de  xor     edx, edx
0x18008b9e0  xor     eax, eax
0x18008b9e2  movsxd  rcx, edx
0x18008b9e5  cmp     byte ptr [rcx+rbx], 26h ; '&'
0x18008b9e9  setz    al
0x18008b9ec  add     rsi, rax
0x18008b9ef  xor     eax, eax
0x18008b9f1  cmp     byte ptr [rcx+rbx+1], 26h ; '&'
0x18008b9f6  setz    al
0x18008b9f9  add     edx, 2
0x18008b9fc  add     r14, rax
0x18008b9ff  cmp     edx, r8d
0x18008ba02  jl      short loc_18008B9E0
0x18008ba04  cmp     edx, edi
0x18008ba06  jge     short loc_18008BA17
0x18008ba08  xor     ecx, ecx
0x18008ba0a  movsxd  rax, edx
0x18008ba0d  cmp     byte ptr [rax+rbx], 26h ; '&'
0x18008ba11  setz    cl
0x18008ba14  add     rbp, rcx
0x18008ba17  call    sqlite3_initialize
0x18008ba1c  test    eax, eax
0x18008ba1e  jnz     loc_18008BF34
0x18008ba24  lea     rcx, [r14+rsi]
0x18008ba28  add     rcx, rbp
0x18008ba2b  call    sqlite3Malloc
0x18008ba30  test    rax, rax
0x18008ba33  jz      loc_18008BF34
0x18008ba39  xor     ecx, ecx
0x18008ba3b  lea     rdi, [rax+4]
0x18008ba3f  or      r13d, 40h
0x18008ba43  mov     [rax], ecx
0x18008ba45  cmp     byte ptr [rbx+5], 2Fh ; '/'
0x18008ba49  mov     eax, 5
0x18008ba4e  mov     [rsp+78h+arg_8], r13d
0x18008ba56  mov     [rsp+78h+Str], rdi
0x18008ba5b  jnz     short loc_18008BAC2
0x18008ba5d  cmp     byte ptr [rbx+6], 2Fh ; '/'
0x18008ba61  jnz     short loc_18008BAC2
0x18008ba63  lea     r8, [rbx+7]
0x18008ba67  mov     eax, 7
0x18008ba6c  cmp     [r8], cl
0x18008ba6f  jz      short loc_18008BAC2
0x18008ba71  movsxd  rcx, eax
0x18008ba74  cmp     byte ptr [rcx+rbx], 2Fh ; '/'
0x18008ba78  jz      short loc_18008BA85
0x18008ba7a  inc     eax
0x18008ba7c  movsxd  rcx, eax
0x18008ba7f  cmp     byte ptr [rcx+rbx], 0
0x18008ba83  jnz     short loc_18008BA71
0x18008ba85  cmp     eax, 7
0x18008ba88  jz      short loc_18008BAC2
0x18008ba8a  cmp     eax, 10h
0x18008ba8d  jnz     short loc_18008BAA9
0x18008ba8f  mov     rcx, 736F686C61636F6Ch
0x18008ba99  cmp     rcx, [r8]
0x18008ba9c  jnz     short loc_18008BAA9
0x18008ba9e  mov     ecx, 74h ; 't'
0x18008baa3  cmp     cl, [r8+8]
0x18008baa7  jz      short loc_18008BAC2
0x18008baa9  lea     edx, [rax-7]
0x18008baac  mov     ebx, 1
0x18008bab1  lea     rcx, aInvalidUriAuth; "invalid uri authority: %.*s"
0x18008bab8  call    sqlite3_mprintf
0x18008babd  jmp     loc_18008BE6D
0x18008bac2  movsxd  rcx, eax
0x18008bac5  xor     edi, edi
0x18008bac7  xor     r8d, r8d
0x18008baca  movzx   edx, byte ptr [rcx+rbx]
0x18008bace  test    dl, dl
0x18008bad0  jz      loc_18008BC57
0x18008bad6  mov     rsi, [rsp+78h+Str]
0x18008badb  lea     rbp, qword_1801147A0
0x18008bae2  cmp     dl, 23h ; '#'
0x18008bae5  jz      loc_18008BC48
0x18008baeb  movsxd  r11, eax
0x18008baee  inc     eax
0x18008baf0  cmp     dl, 25h ; '%'
0x18008baf3  jnz     loc_18008BBB5
0x18008baf9  movsxd  rcx, eax
0x18008bafc  movzx   r10d, byte ptr [rcx+rbx]
0x18008bb01  test    byte ptr [r10+rbp], 8
0x18008bb06  jz      loc_18008BBB5
0x18008bb0c  movzx   r9d, byte ptr [r11+rbx+2]
0x18008bb12  test    byte ptr [r9+rbp], 8
0x18008bb17  jz      loc_18008BBB5
0x18008bb1d  movzx   eax, r10b
0x18008bb21  movzx   edx, r10b
0x18008bb25  sar     al, 6
0x18008bb28  and     al, 1
0x18008bb2a  movzx   eax, al
0x18008bb2d  imul    ecx, eax, 7
0x18008bb30  movzx   eax, r9b
0x18008bb34  sar     al, 6
0x18008bb37  and     al, 1
0x18008bb39  movzx   eax, al
0x18008bb3c  sub     dl, cl
0x18008bb3e  imul    ecx, eax, 7
0x18008bb41  movzx   eax, r9b
0x18008bb45  and     edx, 0Fh
0x18008bb48  shl     edx, 4
0x18008bb4b  sub     al, cl
0x18008bb4d  and     eax, 0Fh
0x18008bb50  add     edx, eax
0x18008bb52  lea     eax, [r11+3]
0x18008bb56  jnz     loc_18008BC31
0x18008bb5c  movsxd  rcx, eax
0x18008bb5f  movzx   edx, byte ptr [rcx+rbx]
0x18008bb63  test    dl, dl
0x18008bb65  jz      loc_18008BC39
0x18008bb6b  nop     dword ptr [rax+rax+00h]
0x18008bb70  cmp     dl, 23h ; '#'
0x18008bb73  jz      loc_18008BC39
0x18008bb79  test    r8d, r8d
0x18008bb7c  jnz     short loc_18008BB83
0x18008bb7e  cmp     dl, 3Fh ; '?'
0x18008bb81  jmp     short loc_18008BB9D
0x18008bb83  cmp     r8d, 1
0x18008bb87  jnz     short loc_18008BB94
0x18008bb89  cmp     dl, 3Dh ; '='
0x18008bb8c  jz      loc_18008BC39
0x18008bb92  jmp     short loc_18008BB9A
0x18008bb94  cmp     r8d, 2
0x18008bb98  jnz     short loc_18008BBA3
0x18008bb9a  cmp     dl, 26h ; '&'
0x18008bb9d  jz      loc_18008BC39
0x18008bba3  inc     eax
0x18008bba5  movsxd  rcx, eax
0x18008bba8  movzx   edx, byte ptr [rcx+rbx]
0x18008bbac  test    dl, dl
0x18008bbae  jnz     short loc_18008BB70
0x18008bbb0  jmp     loc_18008BC39
0x18008bbb5  cmp     r8d, 1
0x18008bbb9  jnz     short loc_18008BC12
0x18008bbbb  cmp     dl, 26h ; '&'
0x18008bbbe  jz      short loc_18008BBC5
0x18008bbc0  cmp     dl, 3Dh ; '='
0x18008bbc3  jnz     short loc_18008BC31
0x18008bbc5  movsxd  rcx, edi
0x18008bbc8  cmp     byte ptr [rcx+rsi-1], 0
0x18008bbcd  jnz     short loc_18008BBFD
0x18008bbcf  movsxd  rcx, eax
0x18008bbd2  cmp     byte ptr [rcx+rbx], 0
0x18008bbd6  jz      short loc_18008BC39
0x18008bbd8  nop     dword ptr [rax+rax+00000000h]
0x18008bbe0  movsxd  rcx, eax
0x18008bbe3  cmp     byte ptr [rcx+rbx], 23h ; '#'
0x18008bbe7  jz      short loc_18008BC39
0x18008bbe9  cmp     byte ptr [rcx+rbx-1], 26h ; '&'
0x18008bbee  jz      short loc_18008BC39
0x18008bbf0  inc     eax
0x18008bbf2  movsxd  rcx, eax
0x18008bbf5  cmp     byte ptr [rcx+rbx], 0
0x18008bbf9  jnz     short loc_18008BBE0
0x18008bbfb  jmp     short loc_18008BC39
0x18008bbfd  cmp     dl, 26h ; '&'
0x18008bc00  jnz     short loc_18008BC0A
0x18008bc02  mov     byte ptr [rcx+rsi], 0
0x18008bc06  inc     edi
0x18008bc08  jmp     short loc_18008BC2F
0x18008bc0a  mov     r8d, 2
0x18008bc10  jmp     short loc_18008BC2F
0x18008bc12  test    r8d, r8d
0x18008bc15  jnz     short loc_18008BC1E
0x18008bc17  cmp     dl, 3Fh ; '?'
0x18008bc1a  jz      short loc_18008BC29
0x18008bc1c  jmp     short loc_18008BC31
0x18008bc1e  cmp     r8d, 2
0x18008bc22  jnz     short loc_18008BC31
0x18008bc24  cmp     dl, 26h ; '&'
0x18008bc27  jnz     short loc_18008BC31
0x18008bc29  mov     r8d, 1
0x18008bc2f  xor     dl, dl
0x18008bc31  movsxd  rcx, edi
0x18008bc34  inc     edi
0x18008bc36  mov     [rcx+rsi], dl
0x18008bc39  movsxd  rcx, eax
0x18008bc3c  movzx   edx, byte ptr [rcx+rbx]
0x18008bc40  test    dl, dl
0x18008bc42  jnz     loc_18008BAE2
0x18008bc48  cmp     r8d, 1
0x18008bc4c  jnz     short loc_18008BC57
0x18008bc4e  movsxd  rax, edi
0x18008bc51  inc     edi
0x18008bc53  mov     byte ptr [rax+rsi], 0
0x18008bc57  movsxd  rax, edi
0x18008bc5a  xor     ecx, ecx
0x18008bc5c  mov     rdi, [rsp+78h+Str]
0x18008bc61  mov     [rax+rdi], ecx
0x18008bc64  test    rdi, rdi
0x18008bc67  jnz     short loc_18008BC6D
0x18008bc69  xor     eax, eax
0x18008bc6b  jmp     short loc_18008BC7A
0x18008bc6d  mov     rcx, rdi; Str
0x18008bc70  call    strlen_0
0x18008bc75  and     eax, 3FFFFFFFh
0x18008bc7a  lea     rbx, [rdi+1]
0x18008bc7e  add     rbx, rax
0x18008bc81  cmp     byte ptr [rbx], 0
0x18008bc84  jz      loc_18008BE3B
0x18008bc8a  mov     esi, 6676h
0x18008bc8f  lea     r14, aCache; "cache"
0x18008bc96  mov     rcx, rbx; Str
0x18008bc99  mov     r15d, 73h ; 's'
0x18008bc9f  call    strlen_0
0x18008bca4  mov     rdi, rax
0x18008bca7  and     edi, 3FFFFFFFh
0x18008bcad  lea     r12d, [rdi+1]
0x18008bcb1  add     r12, rbx
0x18008bcb4  jnz     short loc_18008BCBA
0x18008bcb6  xor     ebp, ebp
0x18008bcb8  jmp     short loc_18008BCCB
0x18008bcba  mov     rcx, r12; Str
0x18008bcbd  call    strlen_0
0x18008bcc2  mov     rbp, rax
0x18008bcc5  and     ebp, 3FFFFFFFh
0x18008bccb  cmp     edi, 3
0x18008bcce  jnz     short loc_18008BCEB
0x18008bcd0  cmp     si, [rbx]
0x18008bcd3  jnz     short loc_18008BCEB
0x18008bcd5  cmp     r15b, [rbx+2]
0x18008bcd9  jnz     short loc_18008BCEB
0x18008bcdb  mov     r15, r12
0x18008bcde  mov     [rsp+78h+arg_0], r12
0x18008bce6  jmp     loc_18008BE27
0x18008bceb  xor     esi, esi
0x18008bced  xor     r15d, r15d
0x18008bcf0  mov     [rsp+78h+var_50], rsi
0x18008bcf5  cmp     edi, 5
0x18008bcf8  jnz     short loc_18008BD53
0x18008bcfa  mov     eax, 68636163h
0x18008bcff  cmp     eax, [rbx]
0x18008bd01  jnz     short loc_18008BD1F
0x18008bd03  mov     eax, 65h ; 'e'
0x18008bd08  cmp     al, [rbx+4]
0x18008bd0b  jnz     short loc_18008BD1F
0x18008bd0d  mov     r15d, 60000h
0x18008bd13  mov     [rsp+78h+var_50], r14
0x18008bd18  lea     rsi, off_18013EED8; "shared"
0x18008bd1f  mov     r13d, r15d
0x18008bd22  test    rsi, rsi
0x18008bd25  jz      loc_18008BE12
0x18008bd2b  xor     ebx, ebx
0x18008bd2d  cmp     [rsi], rbx
0x18008bd30  jz      loc_18008BDB5
0x18008bd36  nop     word ptr [rax+rax+00000000h]
0x18008bd40  movsxd  r14, ebx
0x18008bd43  add     r14, r14
0x18008bd46  mov     rdi, [rsi+r14*8]
0x18008bd4a  test    rdi, rdi
0x18008bd4d  jnz     short loc_18008BD83
0x18008bd4f  xor     eax, eax
0x18008bd51  jmp     short loc_18008BD90
0x18008bd53  cmp     edi, 4
0x18008bd56  jnz     short loc_18008BD1F
0x18008bd58  mov     eax, 65646F6Dh
0x18008bd5d  cmp     eax, [rbx]
0x18008bd5f  jnz     loc_18008BE1A
0x18008bd65  mov     r15d, 87h
0x18008bd6b  lea     rax, aAccess; "access"
0x18008bd72  and     r13d, r15d
0x18008bd75  mov     [rsp+78h+var_50], rax
0x18008bd7a  lea     rsi, off_18013EF10; "ro"
  ... truncated ...
```
