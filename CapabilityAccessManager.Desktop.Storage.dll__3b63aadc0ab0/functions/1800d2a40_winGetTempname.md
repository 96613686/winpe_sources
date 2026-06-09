# winGetTempname

- ea: `0x1800d2a40`
- end: `0x1800d301d`
- name: `winGetTempname`
- size: `1501`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001ac10`
- `0x18001aef0`

## callees

- `0x180003a40`
- `0x180005640`
- `0x180005980`
- `0x180005b30`
- `0x180088560`
- `0x1800d2a40`
- `0x1800d3240`
- `0x1800d3c00`
- `0x1800e4dce`
- `0x18010d010`

## string_xrefs

- `0x1800d2c28`: `winGetTempname1`
- `0x1800d2b65`: `winGetTempname2`
- `0x1800d3007`: `winGetTempname4`
- `0x1800d2cfe`: `winGetTempname5`

## pseudocode

```c
__int64 __fastcall winGetTempname(__int64 a1, const char **a2)
{
  __int64 v2; // rdi
  int v4; // r14d
  char *v5; // rax
  const char *v6; // rsi
  char v7; // bl
  int v8; // r15d
  __int64 v9; // rax
  const char *v10; // rbp
  __int64 v11; // rax
  void *v12; // rax
  void *v13; // rbx
  DWORD v14; // edx
  __int64 result; // rax
  const char *v16; // rax
  const char *v17; // rbp
  size_t v18; // rax
  char v19; // dl
  __int64 v20; // rax
  const char *v21; // r8
  __int64 v22; // rax
  int v23; // eax
  char v24; // cl
  size_t v25; // rax
  char *v26; // rbx
  DWORD v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  unsigned __int8 v31; // r8
  unsigned __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rdx
  unsigned __int64 v41; // r8
  unsigned __int64 v42; // rcx
  __int64 v43; // rdx
  int v44; // [rsp+20h] [rbp-28h]

  v2 = *(int *)(a1 + 8);
  v4 = v2 + 2;
  v5 = (char *)sqlite3Malloc((int)v2 + 2);
  v6 = v5;
  if ( !v5 )
    return 3082;
  memset_0(v5, 0, v4);
  v7 = word_18013C1B4;
  v8 = v2 - 22;
  if ( (_BYTE)word_18013C1B4 )
  {
    v9 = ((__int64 (__fastcall *)(__int64))xmmword_18013C220)(11);
    if ( v9 )
      ((void (__fastcall *)(__int64))xmmword_18013C230)(v9);
    v7 = word_18013C1B4;
  }
  v10 = sqlite3_temp_directory;
  if ( !sqlite3_temp_directory )
  {
    if ( v7 )
    {
      v11 = ((__int64 (__fastcall *)(__int64))xmmword_18013C220)(11);
      if ( v11 )
        ((void (__fastcall *)(__int64))xmmword_18013C240)(v11);
    }
    v12 = (void *)sqlite3Malloc(2 * v2);
    v13 = v12;
    if ( v12 )
    {
      memset_0(v12, 0, 2 * v2);
      if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, void *))off_18013CC08)((unsigned int)v2, v13) )
      {
        sqlite3_free(v13);
        sqlite3_free(v6);
        v14 = off_18013CB78();
        return winLogErrorAtLine(6410, v14, (unsigned int)"winGetTempname2", 0, 50682);
      }
      v16 = (const char *)winUnicodeToUtf8(v13);
      v17 = v16;
      if ( v16 )
      {
        sqlite3_snprintf((unsigned int)v2, v6, "%s", v16);
        sqlite3_free(v17);
        sqlite3_free(v13);
        goto LABEL_32;
      }
      sqlite3_free(v13);
    }
    sqlite3_free(v6);
    return 3082;
  }
  v18 = strlen_0(sqlite3_temp_directory) & 0x3FFFFFFF;
  if ( (_DWORD)v18 )
  {
    v19 = v10[(unsigned int)v18 - 1];
    if ( v19 != 47 && v19 != 92 )
      LODWORD(v18) = v18 + 1;
    if ( (int)v18 > v8 )
    {
      if ( v7 )
      {
        v20 = ((__int64 (__fastcall *)(__int64))xmmword_18013C220)(11);
        if ( v20 )
          ((void (__fastcall *)(__int64))xmmword_18013C240)(v20);
      }
      sqlite3_free(v6);
      v44 = 50581;
      v21 = "winGetTempname1";
      return winLogErrorAtLine(1, 0, (_DWORD)v21, 0, v44);
    }
    sqlite3_snprintf((unsigned int)v2, v6, "%s", v10);
    v7 = word_18013C1B4;
  }
  if ( v7 )
  {
    v22 = ((__int64 (__fastcall *)(__int64))xmmword_18013C220)(11);
    if ( v22 )
      ((void (__fastcall *)(__int64))xmmword_18013C240)(v22);
  }
LABEL_32:
  v23 = strlen_0(v6) & 0x3FFFFFFF;
  if ( v23 )
  {
    v24 = v6[v23 - 1];
    if ( v24 == 47 || v24 == 92 )
      goto LABEL_37;
    if ( v23 + 1 < v8 + 1 )
    {
      *(_WORD *)&v6[v23] = 92;
LABEL_37:
      v25 = strlen_0(v6) & 0x3FFFFFFF;
      if ( (int)v25 + 24 <= v4 )
      {
        sqlite3_snprintf((unsigned int)(v4 - v25 - 16), &v6[(unsigned int)v25], "etilqs_");
        v26 = (char *)&v6[strlen_0(v6) & 0x3FFFFFFF];
        sqlite3_randomness(15, v26);
        v27 = off_18013CAA0();
        v28 = ((unsigned __int8)(v27 + *v26) * (unsigned __int128)0x842108421084211uLL) >> 64;
        *v26 = aAbcdefghijklmn[(unsigned __int8)(v27 + *v26)
                             - 62 * ((v28 + (((unsigned __int64)(unsigned __int8)(v27 + *v26) - v28) >> 1)) >> 5)];
        v29 = ((unsigned __int8)(BYTE1(v27) + v26[1]) * (unsigned __int128)0x842108421084211uLL) >> 64;
        v26[1] = aAbcdefghijklmn[(unsigned __int8)(BYTE1(v27) + v26[1])
                               - 62
                               * ((v29 + (((unsigned __int64)(unsigned __int8)(BYTE1(v27) + v26[1]) - v29) >> 1)) >> 5)];
        v30 = ((unsigned __int8)(v26[2] + ((unsigned __int16)(v27 >> 8) >> 8)) * (unsigned __int128)0x842108421084211uLL) >> 64;
        v31 = v26[3] + (v27 >> 8 >> 16);
        v26[2] = aAbcdefghijklmn[(unsigned __int8)(v26[2] + ((unsigned __int16)(v27 >> 8) >> 8))
                               - 62
                               * ((v30
                                 + (((unsigned __int64)(unsigned __int8)(v26[2] + ((unsigned __int16)(v27 >> 8) >> 8))
                                   - v30) >> 1)) >> 5)];
        v32 = (unsigned __int8)v26[4];
        v26[3] = aAbcdefghijklmn[v31 % 0x3EuLL];
        v26[4] = aAbcdefghijklmn[v32 % 0x3E];
        v33 = ((unsigned __int8)v26[5] * (unsigned __int128)0x842108421084211uLL) >> 64;
        v26[5] = aAbcdefghijklmn[(unsigned __int8)v26[5]
                               - 62 * ((v33 + (((unsigned __int64)(unsigned __int8)v26[5] - v33) >> 1)) >> 5)];
        v34 = ((unsigned __int8)v26[6] * (unsigned __int128)0x842108421084211uLL) >> 64;
        v26[6] = aAbcdefghijklmn[(unsigned __int8)v26[6]
                               - 62 * ((v34 + (((unsigned __int64)(unsigned __int8)v26[6] - v34) >> 1)) >> 5)];
        v35 = ((unsigned __int8)v26[7] * (unsigned __int128)0x842108421084211uLL) >> 64;
        v36 = (unsigned __int8)v26[8];
        v26[7] = aAbcdefghijklmn[(unsigned __int8)v26[7]
                               - 62 * ((v35 + (((unsigned __int64)(unsigned __int8)v26[7] - v35) >> 1)) >> 5)];
        LOBYTE(v27) = aAbcdefghijklmn[v36 % 0x3E];
        v37 = (unsigned __int8)v26[9];
        v26[8] = v27;
        LOBYTE(v27) = aAbcdefghijklmn[v37 % 0x3E];
        v38 = (unsigned __int8)v26[10];
        v26[9] = v27;
        v26[10] = aAbcdefghijklmn[v38 % 0x3E];
        v39 = (unsigned __int8)v26[11];
        v40 = ((unsigned __int8)v26[11] * (unsigned __int128)0x842108421084211uLL) >> 64;
        v41 = (unsigned __int8)v26[13];
        *(_WORD *)(v26 + 15) = 0;
        LOBYTE(v27) = aAbcdefghijklmn[v39 - 62 * ((v40 + ((unsigned __int64)(v39 - v40) >> 1)) >> 5)];
        v42 = (unsigned __int8)v26[12];
        v26[11] = v27;
        v26[12] = aAbcdefghijklmn[v42 % 0x3E];
        v26[13] = aAbcdefghijklmn[v41 % 0x3E];
        v43 = ((unsigned __int8)v26[14] * (unsigned __int128)0x842108421084211uLL) >> 64;
        v26[14] = aAbcdefghijklmn[(unsigned __int8)v26[14]
                                - 62 * ((v43 + (((unsigned __int64)(unsigned __int8)v26[14] - v43) >> 1)) >> 5)];
        result = 0;
        *a2 = v6;
        return result;
      }
      sqlite3_free(v6);
      v44 = 50750;
      v21 = "winGetTempname5";
      return winLogErrorAtLine(1, 0, (_DWORD)v21, 0, v44);
    }
  }
  sqlite3_free(v6);
  v44 = 50732;
  v21 = "winGetTempname4";
  return winLogErrorAtLine(1, 0, (_DWORD)v21, 0, v44);
}

```

## disassembly

```asm
0x1800d2a40  mov     [rsp+arg_10], rbx
0x1800d2a45  mov     [rsp+arg_18], rsi
0x1800d2a4a  push    rdi
0x1800d2a4b  push    r12
0x1800d2a4d  push    r14
0x1800d2a4f  sub     rsp, 30h
0x1800d2a53  movsxd  rdi, dword ptr [rcx+8]
0x1800d2a57  mov     r12, rdx
0x1800d2a5a  lea     r14d, [rdi+2]
0x1800d2a5e  movsxd  rbx, r14d
0x1800d2a61  mov     rcx, rbx
0x1800d2a64  call    sqlite3Malloc
0x1800d2a69  mov     rsi, rax
0x1800d2a6c  test    rax, rax
0x1800d2a6f  jz      loc_1800D3013
0x1800d2a75  mov     [rsp+48h+arg_0], rbp
0x1800d2a7a  mov     r8, rbx; Size
0x1800d2a7d  xor     edx, edx; Val
0x1800d2a7f  mov     [rsp+48h+arg_8], r15
0x1800d2a84  mov     rcx, rax; void *
0x1800d2a87  call    memset_0
0x1800d2a8c  movzx   ebx, byte ptr cs:word_18013C1B4
0x1800d2a93  lea     r15d, [rdi-16h]
0x1800d2a97  test    bl, bl
0x1800d2a99  jz      short loc_1800D2AC7
0x1800d2a9b  mov     rax, qword ptr cs:xmmword_18013C220
0x1800d2aa2  mov     ecx, 0Bh
0x1800d2aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2aac  test    rax, rax
0x1800d2aaf  jz      short loc_1800D2AC0
0x1800d2ab1  mov     rcx, rax
0x1800d2ab4  mov     rax, qword ptr cs:xmmword_18013C230
0x1800d2abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2ac0  movzx   ebx, byte ptr cs:word_18013C1B4
0x1800d2ac7  mov     rbp, cs:sqlite3_temp_directory
0x1800d2ace  test    rbp, rbp
0x1800d2ad1  jnz     loc_1800D2BC3
0x1800d2ad7  test    bl, bl
0x1800d2ad9  jz      short loc_1800D2B00
0x1800d2adb  mov     rax, qword ptr cs:xmmword_18013C220
0x1800d2ae2  mov     ecx, 0Bh
0x1800d2ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2aec  test    rax, rax
0x1800d2aef  jz      short loc_1800D2B00
0x1800d2af1  mov     rcx, rax
0x1800d2af4  mov     rax, qword ptr cs:xmmword_18013C240
0x1800d2afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2b00  mov     rbp, rdi
0x1800d2b03  add     rbp, rbp
0x1800d2b06  mov     rcx, rbp
0x1800d2b09  call    sqlite3Malloc
0x1800d2b0e  mov     rbx, rax
0x1800d2b11  test    rax, rax
0x1800d2b14  jz      loc_1800D2BB4
0x1800d2b1a  mov     r8, rbp; Size
0x1800d2b1d  xor     edx, edx; Val
0x1800d2b1f  mov     rcx, rax; void *
0x1800d2b22  call    memset_0
0x1800d2b27  mov     rax, cs:off_18013CC08
0x1800d2b2e  mov     rdx, rbx
0x1800d2b31  mov     ecx, edi
0x1800d2b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2b38  mov     rcx, rbx
0x1800d2b3b  test    eax, eax
0x1800d2b3d  jnz     short loc_1800D2B76
0x1800d2b3f  call    sqlite3_free
0x1800d2b44  mov     rcx, rsi
0x1800d2b47  call    sqlite3_free
0x1800d2b4c  mov     rax, cs:off_18013CB78
0x1800d2b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2b58  mov     edx, eax
0x1800d2b5a  mov     [rsp+48h+var_28], 0C5FAh
0x1800d2b62  xor     r9d, r9d
0x1800d2b65  lea     r8, aWingettempname_2; "winGetTempname2"
0x1800d2b6c  mov     ecx, 190Ah
0x1800d2b71  jmp     loc_1800D2C36
0x1800d2b76  call    winUnicodeToUtf8
0x1800d2b7b  mov     rbp, rax
0x1800d2b7e  test    rax, rax
0x1800d2b81  jz      short loc_1800D2BAC
0x1800d2b83  mov     r9, rax
0x1800d2b86  lea     r8, aS_7; "%s"
0x1800d2b8d  mov     rdx, rsi
0x1800d2b90  mov     ecx, edi
0x1800d2b92  call    sqlite3_snprintf
0x1800d2b97  mov     rcx, rbp
0x1800d2b9a  call    sqlite3_free
0x1800d2b9f  mov     rcx, rbx
0x1800d2ba2  call    sqlite3_free
0x1800d2ba7  jmp     loc_1800D2C9D
0x1800d2bac  mov     rcx, rbx
0x1800d2baf  call    sqlite3_free
0x1800d2bb4  mov     rcx, rsi
0x1800d2bb7  call    sqlite3_free
0x1800d2bbc  mov     eax, 0C0Ah
0x1800d2bc1  jmp     short loc_1800D2C3B
0x1800d2bc3  mov     rcx, rbp; Str
0x1800d2bc6  call    strlen_0
0x1800d2bcb  and     eax, 3FFFFFFFh
0x1800d2bd0  jbe     loc_1800D2C74
0x1800d2bd6  movzx   edx, byte ptr [rax+rbp-1]
0x1800d2bdb  cmp     dl, 2Fh ; '/'
0x1800d2bde  jz      short loc_1800D2BE7
0x1800d2be0  cmp     dl, 5Ch ; '\'
0x1800d2be3  jz      short loc_1800D2BE7
0x1800d2be5  inc     eax
0x1800d2be7  cmp     eax, r15d
0x1800d2bea  jle     short loc_1800D2C59
0x1800d2bec  test    bl, bl
0x1800d2bee  jz      short loc_1800D2C15
0x1800d2bf0  mov     rax, qword ptr cs:xmmword_18013C220
0x1800d2bf7  mov     ecx, 0Bh
0x1800d2bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2c01  test    rax, rax
0x1800d2c04  jz      short loc_1800D2C15
0x1800d2c06  mov     rcx, rax
0x1800d2c09  mov     rax, qword ptr cs:xmmword_18013C240
0x1800d2c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2c15  mov     rcx, rsi
0x1800d2c18  call    sqlite3_free
0x1800d2c1d  xor     r9d, r9d
0x1800d2c20  mov     [rsp+48h+var_28], 0C595h
0x1800d2c28  lea     r8, aWingettempname; "winGetTempname1"
0x1800d2c2f  mov     ecx, 1
0x1800d2c34  xor     edx, edx
0x1800d2c36  call    winLogErrorAtLine
0x1800d2c3b  mov     rbp, [rsp+48h+arg_0]
0x1800d2c40  mov     r15, [rsp+48h+arg_8]
0x1800d2c45  mov     rbx, [rsp+48h+arg_10]
0x1800d2c4a  mov     rsi, [rsp+48h+arg_18]
0x1800d2c4f  add     rsp, 30h
0x1800d2c53  pop     r14
0x1800d2c55  pop     r12
0x1800d2c57  pop     rdi
0x1800d2c58  retn
0x1800d2c59  mov     r9, rbp
0x1800d2c5c  lea     r8, aS_7; "%s"
0x1800d2c63  mov     rdx, rsi
0x1800d2c66  mov     ecx, edi
0x1800d2c68  call    sqlite3_snprintf
0x1800d2c6d  movzx   ebx, byte ptr cs:word_18013C1B4
0x1800d2c74  test    bl, bl
0x1800d2c76  jz      short loc_1800D2C9D
0x1800d2c78  mov     rax, qword ptr cs:xmmword_18013C220
0x1800d2c7f  mov     ecx, 0Bh
0x1800d2c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2c89  test    rax, rax
0x1800d2c8c  jz      short loc_1800D2C9D
0x1800d2c8e  mov     rcx, rax
0x1800d2c91  mov     rax, qword ptr cs:xmmword_18013C240
0x1800d2c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2c9d  mov     rcx, rsi; Str
0x1800d2ca0  call    strlen_0
0x1800d2ca5  and     eax, 3FFFFFFFh
0x1800d2caa  jbe     loc_1800D2FF4
0x1800d2cb0  movzx   ecx, byte ptr [rax+rsi-1]
0x1800d2cb5  mov     edx, eax
0x1800d2cb7  cmp     cl, 2Fh ; '/'
0x1800d2cba  jz      short loc_1800D2CD6
0x1800d2cbc  cmp     cl, 5Ch ; '\'
0x1800d2cbf  jz      short loc_1800D2CD6
0x1800d2cc1  lea     ecx, [rax+1]
0x1800d2cc4  lea     eax, [r15+1]
0x1800d2cc8  cmp     ecx, eax
0x1800d2cca  jge     loc_1800D2FF4
0x1800d2cd0  mov     word ptr [rdx+rsi], 5Ch ; '\'
0x1800d2cd6  mov     rcx, rsi; Str
0x1800d2cd9  call    strlen_0
0x1800d2cde  and     eax, 3FFFFFFFh
0x1800d2ce3  lea     ecx, [rax+18h]
0x1800d2ce6  cmp     ecx, r14d
0x1800d2ce9  jle     short loc_1800D2D0A
0x1800d2ceb  mov     rcx, rsi
0x1800d2cee  call    sqlite3_free
0x1800d2cf3  xor     r9d, r9d
0x1800d2cf6  mov     [rsp+48h+var_28], 0C63Eh
0x1800d2cfe  lea     r8, aWingettempname_1; "winGetTempname5"
0x1800d2d05  jmp     loc_1800D2C2F
0x1800d2d0a  sub     r14d, eax
0x1800d2d0d  mov     edx, eax
0x1800d2d0f  add     rdx, rsi
0x1800d2d12  lea     r8, aEtilqs; "etilqs_"
0x1800d2d19  lea     ecx, [r14-10h]
0x1800d2d1d  call    sqlite3_snprintf
0x1800d2d22  mov     rcx, rsi; Str
0x1800d2d25  call    strlen_0
0x1800d2d2a  mov     rdi, rax
0x1800d2d2d  mov     ecx, 0Fh
0x1800d2d32  and     edi, 3FFFFFFFh
0x1800d2d38  lea     rbx, [rdi+rsi]
0x1800d2d3c  mov     rdx, rbx
0x1800d2d3f  call    sqlite3_randomness
0x1800d2d44  mov     rax, cs:off_18013CAA0
0x1800d2d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2d50  mov     r9d, eax
0x1800d2d53  movzx   ecx, byte ptr [rbx]
0x1800d2d56  add     cl, al
0x1800d2d58  shr     r9d, 8
0x1800d2d5c  movzx   r8d, cl
0x1800d2d60  lea     r11, aAbcdefghijklmn; "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLM"...
0x1800d2d67  mov     r10, 842108421084211h
0x1800d2d71  mov     rax, r10
0x1800d2d74  mul     r8
0x1800d2d77  mov     eax, r8d
0x1800d2d7a  sub     rax, rdx
0x1800d2d7d  shr     rax, 1
0x1800d2d80  add     rax, rdx
0x1800d2d83  shr     rax, 5
0x1800d2d87  imul    rax, 3Eh ; '>'
0x1800d2d8b  sub     r8, rax
0x1800d2d8e  movzx   eax, byte ptr [r8+r11]
0x1800d2d93  mov     r8d, r9d
0x1800d2d96  mov     [rbx], al
0x1800d2d98  movzx   eax, byte ptr [rbx+1]
0x1800d2d9c  add     al, r9b
0x1800d2d9f  shr     r8d, 8
0x1800d2da3  movzx   ecx, al
0x1800d2da6  mov     rax, r10
0x1800d2da9  mul     rcx
0x1800d2dac  mov     eax, ecx
0x1800d2dae  sub     rax, rdx
0x1800d2db1  shr     rax, 1
0x1800d2db4  add     rax, rdx
0x1800d2db7  shr     rax, 5
0x1800d2dbb  imul    rax, 3Eh ; '>'
0x1800d2dbf  sub     rcx, rax
0x1800d2dc2  movzx   eax, byte ptr [rcx+r11]
0x1800d2dc7  mov     [rbx+1], al
0x1800d2dca  movzx   eax, r8b
0x1800d2dce  add     al, [rbx+2]
0x1800d2dd1  movzx   ecx, al
0x1800d2dd4  mov     rax, r10
0x1800d2dd7  mul     rcx
0x1800d2dda  mov     eax, ecx
0x1800d2ddc  shr     r8d, 8
0x1800d2de0  add     r8b, [rbx+3]
0x1800d2de4  sub     rax, rdx
0x1800d2de7  shr     rax, 1
0x1800d2dea  add     rax, rdx
0x1800d2ded  shr     rax, 5
0x1800d2df1  imul    rax, 3Eh ; '>'
0x1800d2df5  sub     rcx, rax
0x1800d2df8  movzx   eax, byte ptr [rcx+r11]
0x1800d2dfd  mov     [rbx+2], al
0x1800d2e00  mov     rax, r10
0x1800d2e03  movzx   ecx, r8b
0x1800d2e07  mul     rcx
0x1800d2e0a  mov     eax, ecx
0x1800d2e0c  sub     rax, rdx
0x1800d2e0f  shr     rax, 1
0x1800d2e12  add     rax, rdx
0x1800d2e15  shr     rax, 5
0x1800d2e19  imul    rax, 3Eh ; '>'
0x1800d2e1d  sub     rcx, rax
0x1800d2e20  movzx   eax, byte ptr [rcx+r11]
0x1800d2e25  movzx   ecx, byte ptr [rbx+4]
0x1800d2e29  mov     [rbx+3], al
0x1800d2e2c  mov     rax, r10
0x1800d2e2f  mul     rcx
0x1800d2e32  mov     eax, ecx
0x1800d2e34  sub     rax, rdx
0x1800d2e37  shr     rax, 1
0x1800d2e3a  add     rax, rdx
0x1800d2e3d  shr     rax, 5
0x1800d2e41  imul    rax, 3Eh ; '>'
0x1800d2e45  sub     rcx, rax
0x1800d2e48  movzx   eax, byte ptr [rcx+r11]
0x1800d2e4d  mov     [rbx+4], al
0x1800d2e50  mov     rax, r10
0x1800d2e53  movzx   ecx, byte ptr [rbx+5]
0x1800d2e57  mul     rcx
0x1800d2e5a  mov     eax, ecx
0x1800d2e5c  sub     rax, rdx
0x1800d2e5f  shr     rax, 1
0x1800d2e62  add     rax, rdx
0x1800d2e65  shr     rax, 5
0x1800d2e69  imul    rax, 3Eh ; '>'
0x1800d2e6d  sub     rcx, rax
0x1800d2e70  movzx   eax, byte ptr [rcx+r11]
0x1800d2e75  mov     [rbx+5], al
0x1800d2e78  mov     rax, r10
0x1800d2e7b  movzx   ecx, byte ptr [rbx+6]
0x1800d2e7f  mul     rcx
0x1800d2e82  mov     eax, ecx
0x1800d2e84  sub     rax, rdx
0x1800d2e87  shr     rax, 1
0x1800d2e8a  add     rax, rdx
0x1800d2e8d  shr     rax, 5
0x1800d2e91  imul    rax, 3Eh ; '>'
0x1800d2e95  sub     rcx, rax
0x1800d2e98  movzx   eax, byte ptr [rcx+r11]
0x1800d2e9d  mov     [rbx+6], al
0x1800d2ea0  mov     rax, r10
0x1800d2ea3  movzx   ecx, byte ptr [rbx+7]
0x1800d2ea7  mul     rcx
0x1800d2eaa  mov     eax, ecx
0x1800d2eac  sub     rax, rdx
0x1800d2eaf  shr     rax, 1
0x1800d2eb2  add     rax, rdx
0x1800d2eb5  shr     rax, 5
  ... truncated ...
```
