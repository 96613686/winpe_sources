# sqlite3ParseUri

- ea: `0x180121780`
- end: `0x180121dac`
- name: `sqlite3ParseUri`
- size: `1580`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800ac8c0`
- `0x1800e91d0`

## callees

- `0x18011de20`
- `0x180121780`
- `0x1801558d0`
- `0x180156350`
- `0x1802421a0`
- `0x180242ca0`
- `0x180242d80`
- `0x180242e40`

## string_xrefs

- `0x1801218fb`: `invalid uri authority: %.*s`
- `0x180121b67`: `cache`
- `0x180121b96`: `access`

## pseudocode

```c
__int64 __fastcall sqlite3ParseUri(const char *a1, __int64 a2, unsigned int *a3, __int64 *a4, char **a5, __int64 *a6)
{
  unsigned int v6; // r12d
  __int64 *v7; // r15
  const char *v9; // rsi
  size_t v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // r12d
  int v14; // esi
  __int64 v15; // rcx
  __int64 v16; // r11
  __int64 v17; // rax
  _DWORD *v18; // r14
  int v19; // r8d
  char *v20; // r14
  char v21; // al
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // r9d
  int v25; // ecx
  char *v26; // rbx
  __int64 v27; // r11
  __int64 v28; // rdx
  __int64 v29; // r10
  char *v30; // rcx
  char v31; // al
  bool v32; // zf
  char *v33; // rcx
  char v34; // dl
  char v35; // al
  __int64 v36; // rax
  size_t v37; // rax
  char *v38; // rbx
  int v39; // edi
  const char *v40; // r14
  size_t v41; // rbp
  int v42; // r15d
  char **v43; // rsi
  int v44; // r12d
  const char *v45; // r13
  const char *v46; // rbx
  __int64 v47; // rdi
  int v48; // ecx
  _DWORD *v49; // r14
  __int64 result; // rax
  __int64 v51; // rdi
  __int64 v52; // rax
  __int64 v53; // rbx
  unsigned int v54; // [rsp+20h] [rbp-58h]
  char *v55; // [rsp+28h] [rbp-50h]
  const char *v56; // [rsp+80h] [rbp+8h]
  unsigned int v57; // [rsp+88h] [rbp+10h]

  v56 = a1;
  v6 = *a3;
  v7 = a4;
  v57 = 0;
  v9 = a1;
  if ( a2 )
    v10 = strlen((const char *)a2) & 0x3FFFFFFF;
  else
    v10 = 0;
  if ( ((v6 & 0x40) != 0 || byte_1803379C6)
    && (unsigned int)v10 >= 5
    && *(_DWORD *)a2 == 1701603686
    && *(_BYTE *)(a2 + 4) == 58 )
  {
    v11 = 0;
    v12 = 0;
    _mm_lfence();
    v13 = v6 | 0x40;
    v14 = 0;
    v54 = v13;
    v15 = 0;
    v16 = (unsigned int)(v10 + 8);
    if ( (unsigned int)v10 >= 2uLL )
    {
      do
      {
        v11 += *(_BYTE *)(a2 + v15) == 38;
        v17 = *(_BYTE *)(a2 + v15 + 1) == 38;
        v15 += 2;
        v12 += v17;
      }
      while ( v15 < (__int64)(v10 - 1) );
    }
    if ( v15 < (unsigned int)v10 )
      v16 += *(_BYTE *)(v15 + a2) == 38;
    v18 = (_DWORD *)sqlite3Malloc(v16 + v12 + v11);
    if ( v18 )
    {
      v19 = 5;
      *v18 = 0;
      v20 = (char *)(v18 + 1);
      v55 = v20;
      if ( *(_BYTE *)(a2 + 5) == 47 && *(_BYTE *)(a2 + 6) == 47 )
      {
        v21 = *(_BYTE *)(a2 + 7);
        v19 = 7;
        if ( v21 )
        {
          v22 = a2 + 7;
          do
          {
            if ( v21 == 47 )
              break;
            v21 = *(_BYTE *)++v22;
            ++v19;
          }
          while ( v21 );
          if ( v19 != 7 && (v19 != 16 || *(_QWORD *)(a2 + 7) != 0x736F686C61636F6CLL || *(_BYTE *)(a2 + 15) != 116) )
          {
            v57 = 1;
            v23 = sqlite3_mprintf("invalid uri authority: %.*s", v19 - 7, (const char *)(a2 + 7));
            goto LABEL_112;
          }
        }
      }
      v24 = 0;
      LOBYTE(v25) = *(_BYTE *)(v19 + a2);
      if ( (_BYTE)v25 )
      {
        v26 = v20;
        while ( 1 )
        {
          v27 = v19;
          if ( (_BYTE)v25 == 35 )
          {
LABEL_62:
            if ( v24 == 1 )
            {
              v36 = v14++;
              v20[v36] = 0;
            }
            goto LABEL_64;
          }
          ++v19;
          if ( (_BYTE)v25 == 37 )
          {
            v28 = *(unsigned __int8 *)(v19 + a2);
            if ( (*((_BYTE *)&qword_18026E9A0 + v28) & 8) != 0 )
            {
              v29 = *(unsigned __int8 *)(v19 + a2 + 1);
              if ( (*((_BYTE *)&qword_18026E9A0 + v29) & 8) != 0 )
              {
                v19 += 2;
                v25 = (((_BYTE)v29 - 7 * (((char)v29 >> 6) & 1)) & 0xF)
                    + 16 * (((_BYTE)v28 - 7 * (((char)v28 >> 6) & 1)) & 0xF);
                if ( !v25 )
                {
                  v30 = (char *)(a2 + v19);
                  v31 = *v30;
                  if ( *v30 )
                  {
                    while ( v31 != 35 )
                    {
                      if ( v24 )
                      {
                        if ( v24 == 1 && v31 == 61 )
                          goto LABEL_61;
                        v32 = v31 == 38;
                      }
                      else
                      {
                        v32 = v31 == 63;
                      }
                      if ( !v32 )
                      {
                        v31 = *++v30;
                        ++v19;
                        if ( v31 )
                          continue;
                      }
                      goto LABEL_61;
                    }
                  }
                  goto LABEL_61;
                }
                goto LABEL_60;
              }
            }
          }
          if ( v24 == 1 )
            break;
          if ( !v24 )
          {
            if ( (_BYTE)v25 != 63 )
              goto LABEL_60;
LABEL_58:
            v24 = 1;
LABEL_59:
            LOBYTE(v25) = 0;
            goto LABEL_60;
          }
          if ( (_BYTE)v25 == 38 )
            goto LABEL_58;
LABEL_60:
          ++v14;
          *v26++ = v25;
LABEL_61:
          LOBYTE(v25) = *(_BYTE *)(v19 + a2);
          if ( !(_BYTE)v25 )
            goto LABEL_62;
        }
        if ( (_BYTE)v25 != 38 && (_BYTE)v25 != 61 )
          goto LABEL_60;
        if ( !*(v26 - 1) )
        {
          v33 = (char *)(v27 + a2 + 1);
          v34 = *v33;
          if ( *v33 )
          {
            do
            {
              if ( v34 == 35 )
                break;
              if ( *(v33 - 1) == 38 )
                break;
              v35 = *++v33;
              ++v19;
              v34 = v35;
            }
            while ( v35 );
          }
          goto LABEL_61;
        }
        if ( (_BYTE)v25 == 38 )
        {
          ++v14;
          *v26++ = 0;
        }
        else
        {
          v24 = 2;
        }
        goto LABEL_59;
      }
LABEL_64:
      *(_DWORD *)&v20[v14] = 0;
      if ( v20 )
      {
        _mm_lfence();
        v37 = strlen(v20) & 0x3FFFFFFF;
      }
      else
      {
        v37 = 0;
      }
      v38 = &v20[v37 + 1];
      if ( *v38 )
      {
        while ( 1 )
        {
          v39 = strlen(v38) & 0x3FFFFFFF;
          v40 = &v38[v39 + 1];
          if ( v40 )
            v41 = strlen(v40) & 0x3FFFFFFF;
          else
            LODWORD(v41) = 0;
          if ( v39 != 3 )
            break;
          if ( *(_WORD *)v38 != 26230 || v38[2] != 115 )
            goto LABEL_90;
          v9 = &v38[v39 + 1];
          v56 = v9;
LABEL_91:
          v38 = (char *)&v40[(unsigned int)(v41 + 1)];
          if ( !*v38 )
          {
            v20 = v55;
            v7 = a4;
            goto LABEL_100;
          }
        }
        if ( v39 == 5 )
        {
          if ( *(_DWORD *)v38 == 1751343459 && v38[4] == 101 )
          {
            v42 = 393216;
            v43 = &off_18033A088;
            v44 = 393216;
            v45 = "cache";
            goto LABEL_82;
          }
        }
        else if ( v39 == 4 && *(_DWORD *)v38 == 1701080941 )
        {
          v42 = 135;
          v43 = &off_18033A0C0;
          v44 = v13 & 0x87;
          v45 = "access";
LABEL_82:
          v46 = *v43;
          v47 = 0;
          if ( !*v43 )
            goto LABEL_86;
          while ( (_DWORD)v41 != (strlen(v46) & 0x3FFFFFFF) || memcmp(v40, v46, (unsigned int)v41) )
          {
            ++v47;
            v46 = v43[2 * v47];
            if ( !v46 )
              goto LABEL_86;
          }
          v48 = (int)v43[2 * v47 + 1];
          if ( !v48 )
          {
LABEL_86:
            v57 = 1;
            v23 = sqlite3_mprintf("no such %s mode: %s", v45, v40);
            goto LABEL_112;
          }
          if ( (int)(v48 & 0xFFFFFF7F) > v44 )
          {
            v57 = 3;
            v23 = sqlite3_mprintf("%s mode not allowed: %s", v45, v40);
            goto LABEL_112;
          }
          LOBYTE(v13) = v48 | ~(_BYTE)v42 & v54;
          v54 = v48 | ~v42 & v54;
        }
LABEL_90:
        v9 = v56;
        goto LABEL_91;
      }
      v9 = v56;
      goto LABEL_100;
    }
    return 7;
  }
  v49 = (_DWORD *)sqlite3Malloc((unsigned int)(v10 + 8));
  if ( !v49 )
    return 7;
  *v49 = 0;
  v20 = (char *)(v49 + 1);
  v55 = v20;
  if ( (_DWORD)v10 )
    memmove(v20, (const void *)a2, (unsigned int)v10);
  *(_DWORD *)&v20[v10] = 0;
  v54 = v6 & 0xFFFFFFBF;
LABEL_100:
  if ( (_BYTE)word_1803379C4 )
  {
    v52 = xmmword_180337A30(2);
    v51 = v52;
    if ( v52 )
      xmmword_180337A40(v52);
  }
  else
  {
    v51 = 0;
  }
  v53 = qword_1803DC8B0;
  if ( qword_1803DC8B0 && v9 )
  {
    do
    {
      if ( !strcmp(v9, *(const char **)(v53 + 24)) )
        break;
      v53 = *(_QWORD *)(v53 + 16);
    }
    while ( v53 );
  }
  if ( v51 )
    xmmword_180337A50(v51);
  *v7 = v53;
  if ( !v53 )
  {
    v57 = 1;
    v23 = sqlite3_mprintf("no such vfs: %s", v9);
LABEL_112:
    *a6 = v23;
    sqlite3_free_filename(v55);
    v20 = 0;
  }
  *a3 = v54;
  result = v57;
  *a5 = v20;
  return result;
}

```

## disassembly

```asm
0x180121780  mov     [rsp+arg_18], r9
0x180121785  mov     [rsp+arg_10], r8
0x18012178a  mov     [rsp+arg_0], rcx
0x18012178f  push    rbx
0x180121790  push    rsi
0x180121791  push    rdi
0x180121792  push    r12
0x180121794  push    r15
0x180121796  sub     rsp, 50h
0x18012179a  mov     r12d, [r8]
0x18012179d  mov     r15, r9
0x1801217a0  mov     [rsp+78h+arg_8], 0
0x1801217ab  mov     rdi, rdx
0x1801217ae  mov     rsi, rcx
0x1801217b1  test    rdx, rdx
0x1801217b4  jnz     short loc_1801217BA
0x1801217b6  xor     ebx, ebx
0x1801217b8  jmp     short loc_1801217CB
0x1801217ba  mov     rcx, rdi; Str
0x1801217bd  call    strlen
0x1801217c2  mov     rbx, rax
0x1801217c5  and     ebx, 3FFFFFFFh
0x1801217cb  mov     [rsp+78h+var_30], rbp
0x1801217d0  mov     [rsp+78h+var_38], r13
0x1801217d5  mov     [rsp+78h+var_40], r14
0x1801217da  test    r12b, 40h
0x1801217de  jnz     short loc_1801217ED
0x1801217e0  cmp     cs:byte_1803379C6, 0
0x1801217e7  jz      loc_180121C7B
0x1801217ed  cmp     ebx, 5
0x1801217f0  jb      loc_180121C7B
0x1801217f6  cmp     dword ptr [rdi], 656C6966h
0x1801217fc  jnz     loc_180121C7B
0x180121802  cmp     byte ptr [rdi+4], 3Ah ; ':'
0x180121806  jnz     loc_180121C7B
0x18012180c  xor     edx, edx
0x18012180e  xor     r8d, r8d
0x180121811  lfence
0x180121814  or      r12d, 40h
0x180121818  mov     r10d, ebx
0x18012181b  xor     esi, esi
0x18012181d  mov     [rsp+78h+var_58], r12d
0x180121822  xor     ecx, ecx
0x180121824  lea     r11d, [rbx+8]
0x180121828  cmp     r10, 2
0x18012182c  jb      short loc_180121854
0x18012182e  lea     r9, [rbx-1]
0x180121832  xor     eax, eax
0x180121834  cmp     byte ptr [rdi+rcx], 26h ; '&'
0x180121838  setz    al
0x18012183b  add     rdx, rax
0x18012183e  xor     eax, eax
0x180121840  cmp     byte ptr [rdi+rcx+1], 26h ; '&'
0x180121845  setz    al
0x180121848  add     rcx, 2
0x18012184c  add     r8, rax
0x18012184f  cmp     rcx, r9
0x180121852  jl      short loc_180121832
0x180121854  cmp     rcx, r10
0x180121857  jge     short loc_180121865
0x180121859  xor     eax, eax
0x18012185b  cmp     byte ptr [rcx+rdi], 26h ; '&'
0x18012185f  setz    al
0x180121862  add     r11, rax
0x180121865  lea     rcx, [r8+rdx]
0x180121869  add     rcx, r11
0x18012186c  call    sqlite3Malloc
0x180121871  mov     r14, rax
0x180121874  test    rax, rax
0x180121877  jz      loc_180121C8B
0x18012187d  xor     eax, eax
0x18012187f  mov     r8d, 5
0x180121885  mov     [r14], eax
0x180121888  add     r14, 4
0x18012188c  cmp     byte ptr [rdi+5], 2Fh ; '/'
0x180121890  mov     [rsp+78h+var_50], r14
0x180121895  jnz     short loc_18012190C
0x180121897  cmp     byte ptr [rdi+6], 2Fh ; '/'
0x18012189b  jnz     short loc_18012190C
0x18012189d  movzx   eax, byte ptr [rdi+7]
0x1801218a1  mov     r8d, 7
0x1801218a7  test    al, al
0x1801218a9  jz      short loc_18012190C
0x1801218ab  lea     rcx, [rdi+7]
0x1801218af  nop
0x1801218b0  cmp     al, 2Fh ; '/'
0x1801218b2  jz      short loc_1801218C2
0x1801218b4  movzx   eax, byte ptr [rcx+1]
0x1801218b8  inc     rcx
0x1801218bb  inc     r8d
0x1801218be  test    al, al
0x1801218c0  jnz     short loc_1801218B0
0x1801218c2  cmp     r8d, 7
0x1801218c6  jz      short loc_18012190C
0x1801218c8  cmp     r8d, 10h
0x1801218cc  jnz     short loc_1801218E8
0x1801218ce  mov     rax, 736F686C61636F6Ch
0x1801218d8  cmp     rax, [rdi+7]
0x1801218dc  jnz     short loc_1801218E8
0x1801218de  mov     eax, 74h ; 't'
0x1801218e3  cmp     al, [rdi+0Fh]
0x1801218e6  jz      short loc_18012190C
0x1801218e8  lea     edx, [r8-7]
0x1801218ec  mov     [rsp+78h+arg_8], 1
0x1801218f7  lea     r8, [rdi+7]
0x1801218fb  lea     rcx, aInvalidUriAuth; "invalid uri authority: %.*s"
0x180121902  call    sqlite3_mprintf
0x180121907  jmp     loc_180121D59
0x18012190c  movsxd  rax, r8d
0x18012190f  xor     r9d, r9d
0x180121912  movzx   ecx, byte ptr [rax+rdi]
0x180121916  test    cl, cl
0x180121918  jz      loc_180121AA0
0x18012191e  mov     rbx, r14
0x180121921  lea     rbp, qword_18026E9A0
0x180121928  nop     dword ptr [rax+rax+00000000h]
0x180121930  movsxd  r11, r8d
0x180121933  cmp     cl, 23h ; '#'
0x180121936  jz      loc_180121A90
0x18012193c  inc     r8d
0x18012193f  cmp     cl, 25h ; '%'
0x180121942  jnz     loc_180121A02
0x180121948  movsxd  rax, r8d
0x18012194b  movzx   edx, byte ptr [rax+rdi]
0x18012194f  test    byte ptr [rdx+rbp], 8
0x180121953  jz      loc_180121A02
0x180121959  movsxd  rax, r8d
0x18012195c  movzx   r10d, byte ptr [rax+rdi+1]
0x180121962  test    byte ptr [r10+rbp], 8
0x180121967  jz      loc_180121A02
0x18012196d  movzx   eax, dl
0x180121970  add     r8d, 2
0x180121974  sar     al, 6
0x180121977  and     al, 1
0x180121979  movzx   eax, al
0x18012197c  imul    ecx, eax, 7
0x18012197f  movzx   eax, r10b
0x180121983  sar     al, 6
0x180121986  and     al, 1
0x180121988  movzx   eax, al
0x18012198b  sub     dl, cl
0x18012198d  imul    ecx, eax, 7
0x180121990  movzx   eax, r10b
0x180121994  and     edx, 0Fh
0x180121997  add     edx, edx
0x180121999  sub     al, cl
0x18012199b  and     eax, 0Fh
0x18012199e  lea     ecx, [rax+rdx*8]
0x1801219a1  test    ecx, ecx
0x1801219a3  jnz     loc_180121A7A
0x1801219a9  movsxd  rcx, r8d
0x1801219ac  add     rcx, rdi
0x1801219af  movzx   eax, byte ptr [rcx]
0x1801219b2  test    al, al
0x1801219b4  jz      loc_180121A81
0x1801219ba  nop     word ptr [rax+rax+00h]
0x1801219c0  cmp     al, 23h ; '#'
0x1801219c2  jz      loc_180121A81
0x1801219c8  test    r9d, r9d
0x1801219cb  jnz     short loc_1801219D1
0x1801219cd  cmp     al, 3Fh ; '?'
0x1801219cf  jmp     short loc_1801219E9
0x1801219d1  cmp     r9d, 1
0x1801219d5  jnz     short loc_1801219E1
0x1801219d7  cmp     al, 3Dh ; '='
0x1801219d9  jz      loc_180121A81
0x1801219df  jmp     short loc_1801219E7
0x1801219e1  cmp     r9d, 2
0x1801219e5  jnz     short loc_1801219EF
0x1801219e7  cmp     al, 26h ; '&'
0x1801219e9  jz      loc_180121A81
0x1801219ef  movzx   eax, byte ptr [rcx+1]
0x1801219f3  inc     rcx
0x1801219f6  inc     r8d
0x1801219f9  test    al, al
0x1801219fb  jnz     short loc_1801219C0
0x1801219fd  jmp     loc_180121A81
0x180121a02  cmp     r9d, 1
0x180121a06  jnz     short loc_180121A5B
0x180121a08  cmp     cl, 26h ; '&'
0x180121a0b  jz      short loc_180121A12
0x180121a0d  cmp     cl, 3Dh ; '='
0x180121a10  jnz     short loc_180121A7A
0x180121a12  cmp     byte ptr [rbx-1], 0
0x180121a16  jnz     short loc_180121A44
0x180121a18  lea     rcx, [rdi+1]
0x180121a1c  add     rcx, r11
0x180121a1f  movzx   edx, byte ptr [rcx]
0x180121a22  test    dl, dl
0x180121a24  jz      short loc_180121A81
0x180121a26  cmp     dl, 23h ; '#'
0x180121a29  jz      short loc_180121A81
0x180121a2b  cmp     byte ptr [rcx-1], 26h ; '&'
0x180121a2f  jz      short loc_180121A81
0x180121a31  movzx   eax, byte ptr [rcx+1]
0x180121a35  inc     rcx
0x180121a38  inc     r8d
0x180121a3b  movzx   edx, al
0x180121a3e  test    al, al
0x180121a40  jnz     short loc_180121A26
0x180121a42  jmp     short loc_180121A81
0x180121a44  cmp     cl, 26h ; '&'
0x180121a47  jnz     short loc_180121A53
0x180121a49  inc     esi
0x180121a4b  mov     byte ptr [rbx], 0
0x180121a4e  inc     rbx
0x180121a51  jmp     short loc_180121A78
0x180121a53  mov     r9d, 2
0x180121a59  jmp     short loc_180121A78
0x180121a5b  test    r9d, r9d
0x180121a5e  jnz     short loc_180121A67
0x180121a60  cmp     cl, 3Fh ; '?'
0x180121a63  jz      short loc_180121A72
0x180121a65  jmp     short loc_180121A7A
0x180121a67  cmp     r9d, 2
0x180121a6b  jnz     short loc_180121A7A
0x180121a6d  cmp     cl, 26h ; '&'
0x180121a70  jnz     short loc_180121A7A
0x180121a72  mov     r9d, 1
0x180121a78  xor     cl, cl
0x180121a7a  inc     esi
0x180121a7c  mov     [rbx], cl
0x180121a7e  inc     rbx
0x180121a81  movsxd  rax, r8d
0x180121a84  movzx   ecx, byte ptr [rax+rdi]
0x180121a88  test    cl, cl
0x180121a8a  jnz     loc_180121930
0x180121a90  cmp     r9d, 1
0x180121a94  jnz     short loc_180121AA0
0x180121a96  movsxd  rax, esi
0x180121a99  inc     esi
0x180121a9b  mov     byte ptr [rax+r14], 0
0x180121aa0  xor     ecx, ecx
0x180121aa2  movsxd  rax, esi
0x180121aa5  mov     [rax+r14], ecx
0x180121aa9  test    r14, r14
0x180121aac  jnz     short loc_180121AB2
0x180121aae  xor     eax, eax
0x180121ab0  jmp     short loc_180121AC2
0x180121ab2  lfence
0x180121ab5  mov     rcx, r14; Str
0x180121ab8  call    strlen
0x180121abd  and     eax, 3FFFFFFFh
0x180121ac2  lea     rbx, [rax+1]
0x180121ac6  add     rbx, r14
0x180121ac9  cmp     byte ptr [rbx], 0
0x180121acc  jz      loc_180121CC6
0x180121ad2  mov     r13d, 6676h
0x180121ad8  mov     r15d, 65h ; 'e'
0x180121ade  mov     rcx, rbx; Str
0x180121ae1  mov     esi, 73h ; 's'
0x180121ae6  call    strlen
0x180121aeb  mov     rdi, rax
0x180121aee  and     edi, 3FFFFFFFh
0x180121af4  lea     r14d, [rdi+1]
0x180121af8  add     r14, rbx
0x180121afb  jnz     short loc_180121B01
0x180121afd  xor     ebp, ebp
0x180121aff  jmp     short loc_180121B12
0x180121b01  mov     rcx, r14; Str
0x180121b04  call    strlen
0x180121b09  mov     rbp, rax
0x180121b0c  and     ebp, 3FFFFFFFh
0x180121b12  cmp     edi, 3
0x180121b15  jnz     short loc_180121B3B
0x180121b17  cmp     r13w, [rbx]
0x180121b1b  jnz     loc_180121C33
0x180121b21  cmp     sil, [rbx+2]
0x180121b25  jnz     loc_180121C33
0x180121b2b  mov     rsi, r14
0x180121b2e  mov     [rsp+78h+arg_0], r14
0x180121b36  jmp     loc_180121C3B
0x180121b3b  cmp     edi, 5
0x180121b3e  jnz     short loc_180121B70
0x180121b40  mov     eax, 68636163h
0x180121b45  cmp     eax, [rbx]
0x180121b47  jnz     loc_180121C33
0x180121b4d  cmp     r15b, [rbx+4]
0x180121b51  jnz     loc_180121C33
0x180121b57  mov     r15d, 60000h
0x180121b5d  lea     rsi, off_18033A088; "shared"
0x180121b64  mov     r12d, r15d
0x180121b67  lea     r13, aCache; "cache"
0x180121b6e  jmp     short loc_180121B9D
0x180121b70  cmp     edi, 4
0x180121b73  jnz     loc_180121C33
0x180121b79  mov     eax, 65646F6Dh
0x180121b7e  cmp     eax, [rbx]
0x180121b80  jnz     loc_180121C33
0x180121b86  mov     r15d, 87h
0x180121b8c  lea     rsi, off_18033A0C0; "ro"
0x180121b93  and     r12d, r15d
0x180121b96  lea     r13, aAccess; "access"
0x180121b9d  mov     rbx, [rsi]
0x180121ba0  xor     edi, edi
0x180121ba2  test    rbx, rbx
0x180121ba5  jz      short loc_180121BDC
0x180121ba7  mov     rcx, rbx; Str
0x180121baa  call    strlen
0x180121baf  and     eax, 3FFFFFFFh
  ... truncated ...
```
