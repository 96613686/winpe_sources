# winGetTempname

- ea: `0x18016ddf0`
- end: `0x18016e397`
- name: `winGetTempname`
- size: `1447`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800b0fe0`
- `0x1800b1830`

## callees

- `0x180078d20`
- `0x180078d70`
- `0x18011de20`
- `0x180155860`
- `0x1801567c0`
- `0x1801570f0`
- `0x18016ddf0`
- `0x18016e5e0`
- `0x18016ef60`
- `0x180228f60`
- `0x180242860`
- `0x180242d80`

## string_xrefs

- `0x18016dfaf`: `winGetTempname1`
- `0x18016deeb`: `winGetTempname2`
- `0x18016e381`: `winGetTempname4`
- `0x18016e07e`: `winGetTempname5`

## pseudocode

```c
__int64 __fastcall winGetTempname(__int64 a1, const char **a2)
{
  __int64 v2; // rdi
  int v4; // r14d
  char *v5; // rax
  const char *v6; // rsi
  int v7; // r15d
  __int64 v8; // rax
  __int64 v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rbx
  DWORD v12; // eax
  __int64 result; // rax
  const char *v14; // rax
  const char *v15; // rbp
  size_t v16; // rax
  char v17; // dl
  __int64 v18; // rax
  const char *v19; // r8
  __int64 v20; // rax
  int v21; // eax
  char v22; // cl
  size_t v23; // rax
  char *v24; // rbx
  DWORD v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  unsigned __int8 v29; // r9
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // r8
  __int64 v40; // rdx
  int v41; // [rsp+20h] [rbp-28h]

  v2 = *(int *)(a1 + 8);
  v4 = v2 + 2;
  v5 = (char *)sqlite3Malloc((int)v2 + 2);
  v6 = v5;
  if ( !v5 )
    return 3082;
  memset(v5, 0, v4);
  v7 = v2 - 22;
  if ( (_BYTE)word_1803379C4 )
  {
    v8 = xmmword_180337A30(11);
    if ( v8 )
      xmmword_180337A40(v8);
  }
  if ( !sqlite3_temp_directory )
  {
    if ( (_BYTE)word_1803379C4 )
    {
      v9 = xmmword_180337A30(11);
      if ( v9 )
        xmmword_180337A50(v9);
    }
    v10 = (WCHAR *)sqlite3Malloc(2 * v2);
    v11 = v10;
    if ( v10 )
    {
      memset(v10, 0, 2 * v2);
      if ( !off_180337518(v2, v11) )
      {
        sqlite3_free(v11);
        sqlite3_free(v6);
        v12 = off_180337488();
        return winLogErrorAtLine(6410, v12, "winGetTempname2", 0, 51634);
      }
      v14 = (const char *)winUnicodeToUtf8(v11);
      v15 = v14;
      if ( v14 )
      {
        sqlite3_snprintf((unsigned int)v2, v6, "%s", v14);
        sqlite3_free(v15);
        sqlite3_free(v11);
        goto LABEL_31;
      }
      sqlite3_free(v11);
    }
    sqlite3_free(v6);
    return 3082;
  }
  v16 = strlen(sqlite3_temp_directory) & 0x3FFFFFFF;
  if ( (_DWORD)v16 )
  {
    v17 = sqlite3_temp_directory[(unsigned int)v16 - 1];
    if ( v17 != 47 && v17 != 92 )
      LODWORD(v16) = v16 + 1;
    _mm_lfence();
    if ( (int)v16 > v7 )
    {
      if ( (_BYTE)word_1803379C4 )
      {
        v18 = xmmword_180337A30(11);
        if ( v18 )
          xmmword_180337A50(v18);
      }
      sqlite3_free(v6);
      v41 = 51533;
      v19 = "winGetTempname1";
      return winLogErrorAtLine(1, 0, v19, 0, v41);
    }
    sqlite3_snprintf((unsigned int)v2, v6, "%s", sqlite3_temp_directory);
  }
  if ( (_BYTE)word_1803379C4 )
  {
    v20 = xmmword_180337A30(11);
    if ( v20 )
      xmmword_180337A50(v20);
  }
LABEL_31:
  v21 = strlen(v6) & 0x3FFFFFFF;
  if ( v21 )
  {
    v22 = v6[v21 - 1];
    if ( v22 == 47 || v22 == 92 )
      goto LABEL_36;
    if ( v21 + 1 < v7 + 1 )
    {
      *(_WORD *)&v6[v21] = 92;
LABEL_36:
      v23 = strlen(v6) & 0x3FFFFFFF;
      _mm_lfence();
      if ( (int)v23 + 24 <= v4 )
      {
        sqlite3_snprintf((unsigned int)(v4 - v23 - 16), &v6[(unsigned int)v23], "etilqs_");
        v24 = (char *)&v6[strlen(v6) & 0x3FFFFFFF];
        sqlite3_randomness(15, v24);
        v25 = off_1803373B0();
        _mm_lfence();
        v26 = ((unsigned __int8)(*v24 + v25) * (unsigned __int128)0x842108421084211uLL) >> 64;
        *v24 = aAbcdefghijklmn[(unsigned __int8)(*v24 + v25)
                             - 62 * ((v26 + (((unsigned __int64)(unsigned __int8)(*v24 + v25) - v26) >> 1)) >> 5)];
        v27 = ((unsigned __int8)(v24[1] + BYTE1(v25)) * (unsigned __int128)0x842108421084211uLL) >> 64;
        v24[1] = aAbcdefghijklmn[(unsigned __int8)(v24[1] + BYTE1(v25))
                               - 62
                               * ((v27 + (((unsigned __int64)(unsigned __int8)(v24[1] + BYTE1(v25)) - v27) >> 1)) >> 5)];
        v28 = ((unsigned __int8)(v24[2] + BYTE2(v25)) * (unsigned __int128)0x842108421084211uLL) >> 64;
        v29 = v24[3] + HIBYTE(v25);
        v24[2] = aAbcdefghijklmn[(unsigned __int8)(v24[2] + BYTE2(v25))
                               - 62
                               * ((v28 + (((unsigned __int64)(unsigned __int8)(v24[2] + BYTE2(v25)) - v28) >> 1)) >> 5)];
        v30 = (unsigned __int8)v24[4];
        v24[3] = aAbcdefghijklmn[v29 % 0x3EuLL];
        LOBYTE(v25) = aAbcdefghijklmn[v30 % 0x3E];
        v31 = (unsigned __int8)v24[5];
        v24[4] = v25;
        v24[5] = aAbcdefghijklmn[v31 % 0x3E];
        v32 = ((unsigned __int8)v24[6] * (unsigned __int128)0x842108421084211uLL) >> 64;
        v24[6] = aAbcdefghijklmn[(unsigned __int8)v24[6]
                               - 62 * ((v32 + (((unsigned __int64)(unsigned __int8)v24[6] - v32) >> 1)) >> 5)];
        v33 = ((unsigned __int8)v24[7] * (unsigned __int128)0x842108421084211uLL) >> 64;
        v24[7] = aAbcdefghijklmn[(unsigned __int8)v24[7]
                               - 62 * ((v33 + (((unsigned __int64)(unsigned __int8)v24[7] - v33) >> 1)) >> 5)];
        v34 = ((unsigned __int8)v24[8] * (unsigned __int128)0x842108421084211uLL) >> 64;
        v35 = (unsigned __int8)v24[9];
        v24[8] = aAbcdefghijklmn[(unsigned __int8)v24[8]
                               - 62 * ((v34 + (((unsigned __int64)(unsigned __int8)v24[8] - v34) >> 1)) >> 5)];
        LOBYTE(v25) = aAbcdefghijklmn[v35 % 0x3E];
        v36 = (unsigned __int8)v24[10];
        v24[9] = v25;
        LOBYTE(v25) = aAbcdefghijklmn[v36 % 0x3E];
        v37 = (unsigned __int8)v24[11];
        v24[10] = v25;
        LOBYTE(v25) = aAbcdefghijklmn[v37 % 0x3E];
        v38 = (unsigned __int8)v24[12];
        v24[11] = v25;
        v39 = (unsigned __int8)v24[13];
        *(_WORD *)(v24 + 15) = 0;
        v24[12] = aAbcdefghijklmn[v38 % 0x3E];
        v24[13] = aAbcdefghijklmn[v39 % 0x3E];
        v40 = ((unsigned __int8)v24[14] * (unsigned __int128)0x842108421084211uLL) >> 64;
        v24[14] = aAbcdefghijklmn[(unsigned __int8)v24[14]
                                - 62 * ((v40 + (((unsigned __int64)(unsigned __int8)v24[14] - v40) >> 1)) >> 5)];
        result = 0;
        *a2 = v6;
        return result;
      }
      sqlite3_free(v6);
      v41 = 51702;
      v19 = "winGetTempname5";
      return winLogErrorAtLine(1, 0, v19, 0, v41);
    }
  }
  sqlite3_free(v6);
  v41 = 51684;
  v19 = "winGetTempname4";
  return winLogErrorAtLine(1, 0, v19, 0, v41);
}

```

## disassembly

```asm
0x18016ddf0  mov     [rsp+arg_10], rbx
0x18016ddf5  mov     [rsp+arg_18], rsi
0x18016ddfa  push    rdi
0x18016ddfb  push    r12
0x18016ddfd  push    r14
0x18016ddff  sub     rsp, 30h
0x18016de03  movsxd  rdi, dword ptr [rcx+8]
0x18016de07  mov     r12, rdx
0x18016de0a  lea     r14d, [rdi+2]
0x18016de0e  movsxd  rbx, r14d
0x18016de11  mov     rcx, rbx
0x18016de14  call    sqlite3Malloc
0x18016de19  mov     rsi, rax
0x18016de1c  test    rax, rax
0x18016de1f  jz      loc_18016E38D
0x18016de25  mov     r8, rbx; Size
0x18016de28  mov     [rsp+48h+arg_8], r15
0x18016de2d  xor     edx, edx; Val
0x18016de2f  mov     rcx, rax; void *
0x18016de32  call    memset
0x18016de37  cmp     byte ptr cs:word_1803379C4, 0
0x18016de3e  lea     r15d, [rdi-16h]
0x18016de42  jz      short loc_18016DE5D
0x18016de44  mov     ecx, 0Bh
0x18016de49  call    qword ptr cs:xmmword_180337A30
0x18016de4f  test    rax, rax
0x18016de52  jz      short loc_18016DE5D
0x18016de54  mov     rcx, rax
0x18016de57  call    qword ptr cs:xmmword_180337A40
0x18016de5d  mov     rbx, cs:sqlite3_temp_directory
0x18016de64  mov     [rsp+48h+arg_0], rbp
0x18016de69  test    rbx, rbx
0x18016de6c  jnz     loc_18016DF4E
0x18016de72  cmp     byte ptr cs:word_1803379C4, bl
0x18016de78  jz      short loc_18016DE93
0x18016de7a  mov     ecx, 0Bh
0x18016de7f  call    qword ptr cs:xmmword_180337A30
0x18016de85  test    rax, rax
0x18016de88  jz      short loc_18016DE93
0x18016de8a  mov     rcx, rax
0x18016de8d  call    qword ptr cs:xmmword_180337A50
0x18016de93  mov     rbp, rdi
0x18016de96  add     rbp, rbp
0x18016de99  mov     rcx, rbp
0x18016de9c  call    sqlite3Malloc
0x18016dea1  mov     rbx, rax
0x18016dea4  test    rax, rax
0x18016dea7  jz      loc_18016DF3F
0x18016dead  mov     r8, rbp; Size
0x18016deb0  xor     edx, edx; Val
0x18016deb2  mov     rcx, rax; void *
0x18016deb5  call    memset
0x18016deba  mov     r8, cs:off_180337518
0x18016dec1  mov     rdx, rbx; lpBuffer
0x18016dec4  mov     ecx, edi; nBufferLength
0x18016dec6  call    r8 ; GetTempPathW_0
0x18016dec9  mov     rcx, rbx; lpWideCharStr
0x18016decc  test    eax, eax
0x18016dece  jnz     short loc_18016DF01
0x18016ded0  call    sqlite3_free
0x18016ded5  mov     rcx, rsi
0x18016ded8  call    sqlite3_free
0x18016dedd  call    cs:off_180337488
0x18016dee3  mov     [rsp+48h+var_28], 0C9B2h
0x18016deeb  lea     r8, aWingettempname_2; "winGetTempname2"
0x18016def2  mov     edx, eax
0x18016def4  xor     r9d, r9d
0x18016def7  mov     ecx, 190Ah
0x18016defc  jmp     loc_18016DFBD
0x18016df01  call    winUnicodeToUtf8
0x18016df06  mov     rbp, rax
0x18016df09  test    rax, rax
0x18016df0c  jz      short loc_18016DF37
0x18016df0e  mov     r9, rax
0x18016df11  lea     r8, aS_9; "%s"
0x18016df18  mov     rdx, rsi
0x18016df1b  mov     ecx, edi
0x18016df1d  call    sqlite3_snprintf
0x18016df22  mov     rcx, rbp
0x18016df25  call    sqlite3_free
0x18016df2a  mov     rcx, rbx
0x18016df2d  call    sqlite3_free
0x18016df32  jmp     loc_18016E01A
0x18016df37  mov     rcx, rbx
0x18016df3a  call    sqlite3_free
0x18016df3f  mov     rcx, rsi
0x18016df42  call    sqlite3_free
0x18016df47  mov     eax, 0C0Ah
0x18016df4c  jmp     short loc_18016DFC2
0x18016df4e  mov     rcx, rbx; Str
0x18016df51  call    strlen
0x18016df56  and     eax, 3FFFFFFFh
0x18016df5b  jbe     loc_18016DFF8
0x18016df61  movzx   edx, byte ptr [rax+rbx-1]
0x18016df66  cmp     dl, 2Fh ; '/'
0x18016df69  jz      short loc_18016DF72
0x18016df6b  cmp     dl, 5Ch ; '\'
0x18016df6e  jz      short loc_18016DF72
0x18016df70  inc     eax
0x18016df72  lfence
0x18016df75  cmp     eax, r15d
0x18016df78  jle     short loc_18016DFE0
0x18016df7a  cmp     byte ptr cs:word_1803379C4, 0
0x18016df81  jz      short loc_18016DF9C
0x18016df83  mov     ecx, 0Bh
0x18016df88  call    qword ptr cs:xmmword_180337A30
0x18016df8e  test    rax, rax
0x18016df91  jz      short loc_18016DF9C
0x18016df93  mov     rcx, rax
0x18016df96  call    qword ptr cs:xmmword_180337A50
0x18016df9c  mov     rcx, rsi
0x18016df9f  call    sqlite3_free
0x18016dfa4  xor     r9d, r9d
0x18016dfa7  mov     [rsp+48h+var_28], 0C94Dh
0x18016dfaf  lea     r8, aWingettempname; "winGetTempname1"
0x18016dfb6  mov     ecx, 1
0x18016dfbb  xor     edx, edx
0x18016dfbd  call    winLogErrorAtLine
0x18016dfc2  mov     rbp, [rsp+48h+arg_0]
0x18016dfc7  mov     r15, [rsp+48h+arg_8]
0x18016dfcc  mov     rbx, [rsp+48h+arg_10]
0x18016dfd1  mov     rsi, [rsp+48h+arg_18]
0x18016dfd6  add     rsp, 30h
0x18016dfda  pop     r14
0x18016dfdc  pop     r12
0x18016dfde  pop     rdi
0x18016dfdf  retn
0x18016dfe0  mov     r9, cs:sqlite3_temp_directory
0x18016dfe7  lea     r8, aS_9; "%s"
0x18016dfee  mov     rdx, rsi
0x18016dff1  mov     ecx, edi
0x18016dff3  call    sqlite3_snprintf
0x18016dff8  cmp     byte ptr cs:word_1803379C4, 0
0x18016dfff  jz      short loc_18016E01A
0x18016e001  mov     ecx, 0Bh
0x18016e006  call    qword ptr cs:xmmword_180337A30
0x18016e00c  test    rax, rax
0x18016e00f  jz      short loc_18016E01A
0x18016e011  mov     rcx, rax
0x18016e014  call    qword ptr cs:xmmword_180337A50
0x18016e01a  mov     rcx, rsi; Str
0x18016e01d  call    strlen
0x18016e022  and     eax, 3FFFFFFFh
0x18016e027  jbe     loc_18016E36E
0x18016e02d  movzx   ecx, byte ptr [rax+rsi-1]
0x18016e032  mov     edx, eax
0x18016e034  cmp     cl, 2Fh ; '/'
0x18016e037  jz      short loc_18016E053
0x18016e039  cmp     cl, 5Ch ; '\'
0x18016e03c  jz      short loc_18016E053
0x18016e03e  lea     ecx, [rax+1]
0x18016e041  lea     eax, [r15+1]
0x18016e045  cmp     ecx, eax
0x18016e047  jge     loc_18016E36E
0x18016e04d  mov     word ptr [rdx+rsi], 5Ch ; '\'
0x18016e053  mov     rcx, rsi; Str
0x18016e056  call    strlen
0x18016e05b  and     eax, 3FFFFFFFh
0x18016e060  lea     ecx, [rax+18h]
0x18016e063  lfence
0x18016e066  cmp     ecx, r14d
0x18016e069  jle     short loc_18016E08A
0x18016e06b  mov     rcx, rsi
0x18016e06e  call    sqlite3_free
0x18016e073  xor     r9d, r9d
0x18016e076  mov     [rsp+48h+var_28], 0C9F6h
0x18016e07e  lea     r8, aWingettempname_1; "winGetTempname5"
0x18016e085  jmp     loc_18016DFB6
0x18016e08a  sub     r14d, eax
0x18016e08d  mov     edx, eax
0x18016e08f  add     rdx, rsi
0x18016e092  lea     r8, aEtilqs; "etilqs_"
0x18016e099  lea     ecx, [r14-10h]
0x18016e09d  call    sqlite3_snprintf
0x18016e0a2  mov     rcx, rsi; Str
0x18016e0a5  call    strlen
0x18016e0aa  mov     rdi, rax
0x18016e0ad  mov     ecx, 0Fh
0x18016e0b2  and     edi, 3FFFFFFFh
0x18016e0b8  lea     rbx, [rdi+rsi]
0x18016e0bc  mov     rdx, rbx
0x18016e0bf  call    sqlite3_randomness
0x18016e0c4  call    cs:off_1803373B0
0x18016e0ca  mov     r9d, eax
0x18016e0cd  lfence
0x18016e0d0  movzx   ecx, al
0x18016e0d3  shr     r9d, 8
0x18016e0d7  add     cl, [rbx]
0x18016e0d9  lea     r11, aAbcdefghijklmn; "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLM"...
0x18016e0e0  movzx   r8d, cl
0x18016e0e4  mov     r10, 842108421084211h
0x18016e0ee  mov     ecx, r8d
0x18016e0f1  mov     rax, r10
0x18016e0f4  mul     r8
0x18016e0f7  sub     rcx, rdx
0x18016e0fa  shr     rcx, 1
0x18016e0fd  add     rcx, rdx
0x18016e100  shr     rcx, 5
0x18016e104  imul    rax, rcx, 3Eh ; '>'
0x18016e108  sub     r8, rax
0x18016e10b  movzx   eax, byte ptr [r8+r11]
0x18016e110  mov     [rbx], al
0x18016e112  movzx   eax, r9b
0x18016e116  add     al, [rbx+1]
0x18016e119  movzx   ecx, al
0x18016e11c  mov     rax, r10
0x18016e11f  mul     rcx
0x18016e122  mov     eax, ecx
0x18016e124  shr     r9d, 8
0x18016e128  sub     rax, rdx
0x18016e12b  shr     rax, 1
0x18016e12e  add     rax, rdx
0x18016e131  shr     rax, 5
0x18016e135  imul    rax, 3Eh ; '>'
0x18016e139  sub     rcx, rax
0x18016e13c  movzx   eax, byte ptr [rcx+r11]
0x18016e141  mov     [rbx+1], al
0x18016e144  movzx   eax, r9b
0x18016e148  add     al, [rbx+2]
0x18016e14b  movzx   ecx, al
0x18016e14e  mov     rax, r10
0x18016e151  mul     rcx
0x18016e154  mov     eax, ecx
0x18016e156  shr     r9d, 8
0x18016e15a  add     r9b, [rbx+3]
0x18016e15e  sub     rax, rdx
0x18016e161  shr     rax, 1
0x18016e164  add     rax, rdx
0x18016e167  shr     rax, 5
0x18016e16b  imul    rax, 3Eh ; '>'
0x18016e16f  sub     rcx, rax
0x18016e172  movzx   eax, byte ptr [rcx+r11]
0x18016e177  mov     [rbx+2], al
0x18016e17a  mov     rax, r10
0x18016e17d  movzx   ecx, r9b
0x18016e181  mul     rcx
0x18016e184  mov     eax, ecx
0x18016e186  sub     rax, rdx
0x18016e189  shr     rax, 1
0x18016e18c  add     rax, rdx
0x18016e18f  shr     rax, 5
0x18016e193  imul    rax, 3Eh ; '>'
0x18016e197  sub     rcx, rax
0x18016e19a  movzx   eax, byte ptr [rcx+r11]
0x18016e19f  movzx   ecx, byte ptr [rbx+4]
0x18016e1a3  mov     [rbx+3], al
0x18016e1a6  mov     rax, r10
0x18016e1a9  mul     rcx
0x18016e1ac  mov     eax, ecx
0x18016e1ae  sub     rax, rdx
0x18016e1b1  shr     rax, 1
0x18016e1b4  add     rax, rdx
0x18016e1b7  shr     rax, 5
0x18016e1bb  imul    rax, 3Eh ; '>'
0x18016e1bf  sub     rcx, rax
0x18016e1c2  movzx   eax, byte ptr [rcx+r11]
0x18016e1c7  movzx   ecx, byte ptr [rbx+5]
0x18016e1cb  mov     [rbx+4], al
0x18016e1ce  mov     rax, r10
0x18016e1d1  mul     rcx
0x18016e1d4  mov     eax, ecx
0x18016e1d6  sub     rax, rdx
0x18016e1d9  shr     rax, 1
0x18016e1dc  add     rax, rdx
0x18016e1df  shr     rax, 5
0x18016e1e3  imul    rax, 3Eh ; '>'
0x18016e1e7  sub     rcx, rax
0x18016e1ea  movzx   eax, byte ptr [rcx+r11]
0x18016e1ef  mov     [rbx+5], al
0x18016e1f2  mov     rax, r10
0x18016e1f5  movzx   ecx, byte ptr [rbx+6]
0x18016e1f9  mul     rcx
0x18016e1fc  mov     eax, ecx
0x18016e1fe  sub     rax, rdx
0x18016e201  shr     rax, 1
0x18016e204  add     rax, rdx
0x18016e207  shr     rax, 5
0x18016e20b  imul    rax, 3Eh ; '>'
0x18016e20f  sub     rcx, rax
0x18016e212  movzx   eax, byte ptr [rcx+r11]
0x18016e217  mov     [rbx+6], al
0x18016e21a  mov     rax, r10
0x18016e21d  movzx   ecx, byte ptr [rbx+7]
0x18016e221  mul     rcx
0x18016e224  mov     eax, ecx
0x18016e226  sub     rax, rdx
0x18016e229  shr     rax, 1
0x18016e22c  add     rax, rdx
0x18016e22f  shr     rax, 5
0x18016e233  imul    rax, 3Eh ; '>'
0x18016e237  sub     rcx, rax
0x18016e23a  movzx   eax, byte ptr [rcx+r11]
0x18016e23f  mov     [rbx+7], al
0x18016e242  mov     rax, r10
0x18016e245  movzx   ecx, byte ptr [rbx+8]
0x18016e249  mul     rcx
0x18016e24c  mov     eax, ecx
0x18016e24e  sub     rax, rdx
0x18016e251  shr     rax, 1
0x18016e254  add     rax, rdx
  ... truncated ...
```
