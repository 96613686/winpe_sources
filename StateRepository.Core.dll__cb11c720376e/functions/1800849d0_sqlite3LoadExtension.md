# sqlite3LoadExtension

- ea: `0x1800849d0`
- end: `0x180084e46`
- name: `sqlite3LoadExtension`
- size: `1142`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008eec0`

## callees

- `0x180001110`
- `0x180005810`
- `0x180005b90`
- `0x18000a9e0`
- `0x18000aac0`
- `0x18000f720`
- `0x18004b050`
- `0x180067b40`
- `0x1800849d0`
- `0x180099814`
- `0x18009a010`

## string_xrefs

- `0x180084a43`: `sqlite3_extension_init`
- `0x180084d3a`: `error during initialization: %s`
- `0x180084e09`: `unable to open shared library [%.*s]`

## pseudocode

```c
__int64 __fastcall sqlite3LoadExtension(__int64 *a1, const char *a2, const char *a3, const char **a4)
{
  __int64 v4; // rdi
  __int64 v8; // r14
  const char *v9; // r13
  __int64 v10; // r15
  int i; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  _QWORD *v15; // r14
  __int64 v16; // r13
  int v18; // eax
  int v19; // r8d
  int v20; // edx
  unsigned int j; // ecx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // ebx
  const char *v26; // rax
  int v27; // eax
  void *v28; // rdi
  __int64 v29; // rax
  __int64 v30; // rax
  const char *v31; // rax
  __int64 v32; // [rsp+30h] [rbp-58h]
  __int64 v33; // [rsp+38h] [rbp-50h]
  __int64 v34; // [rsp+40h] [rbp-48h]
  int v35; // [rsp+90h] [rbp+8h]
  __int64 (__fastcall *v36)(__int64 *, const char **, __int64 (__fastcall **)()); // [rsp+90h] [rbp+8h]
  const char *v38; // [rsp+A8h] [rbp+20h] BYREF

  v4 = *a1;
  v38 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v34 = v8;
  if ( a4 )
    *a4 = 0;
  if ( (a1[6] & 0x10000) != 0 )
  {
    v9 = a3;
    if ( !a3 )
      v9 = "sqlite3_extension_init";
    if ( (unsigned __int64)(v8 - 1) > 0x103 )
    {
LABEL_53:
      if ( a4 )
      {
        v31 = (const char *)sqlite3_malloc64(v8 + 300);
        v38 = v31;
        *a4 = v31;
        if ( v31 )
        {
          sqlite3_snprintf((unsigned int)(v8 + 300), v31, "unable to open shared library [%.*s]", 260, a2);
          (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v8 + 299), v38);
        }
      }
      return 1;
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(v4 + 72))(v4);
    for ( i = 0; ; i = v35 + 1 )
    {
      v35 = i;
      if ( i >= 1 )
        break;
      if ( v10 )
        goto LABEL_21;
      v32 = i;
      v33 = sqlite3_mprintf("%s.%s", a2, off_18009C0D8[i]);
      v12 = v33;
      if ( !v33 )
        return 7;
      v13 = -1;
      do
        ++v13;
      while ( off_18009C0D8[v32][v13] );
      if ( (unsigned __int64)(v13 + v8 + 1) <= 0x104 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, __int64))(v4 + 72))(v4, v33);
        v12 = v33;
        v10 = v14;
      }
      sqlite3_free(v12);
    }
    if ( !v10 )
      goto LABEL_53;
LABEL_21:
    v15 = 0;
    v36 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, const char *))(v4 + 88))(
                                                                                         v4,
                                                                                         v10,
                                                                                         v9);
    if ( !v36 )
    {
      if ( a3 )
        goto LABEL_37;
      v16 = (int)sqlite3Strlen30(a2);
      v15 = (_QWORD *)sqlite3_malloc64(v16 + 30);
      if ( !v15 )
      {
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        return 7;
      }
      *v15 = 0x5F336574696C7173LL;
      do
        LODWORD(v16) = v16 - 1;
      while ( (int)v16 >= 0 && a2[(unsigned int)v16] != 47 && a2[(unsigned int)v16] != 92 );
      v18 = sqlite3_strnicmp(&a2[(int)v16 + 1], "lib", 3);
      v19 = 8;
      v20 = v16 + (v18 != 0 ? 1 : 4);
      for ( j = a2[v20]; a2[v20]; j = a2[++v20] )
      {
        if ( j == 46 )
          break;
        if ( (*((_BYTE *)&qword_18009E630 + (unsigned __int8)j) & 2) != 0 )
        {
          v22 = j;
          v23 = v19++;
          *((_BYTE *)v15 + v23) = *((_BYTE *)qword_18009E760 + v22);
        }
      }
      strcpy((char *)v15 + v19, "_init");
      v36 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(v4 + 88))(
                                                                                           v4,
                                                                                           v10,
                                                                                           v15);
      if ( !v36 )
      {
        v9 = (const char *)v15;
LABEL_37:
        if ( a4 )
        {
          v24 = -1;
          do
            ++v24;
          while ( v9[v24] );
          v25 = v24 + v34;
          v26 = (const char *)sqlite3_malloc64(v24 + v34 + 300);
          v38 = v26;
          *a4 = v26;
          if ( v26 )
          {
            sqlite3_snprintf((unsigned int)(v25 + 300), v26, "no entry point [%s] in shared library [%s]", v9, a2);
            (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v25 + 299), v38);
          }
        }
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        sqlite3_free(v15);
        return 1;
      }
    }
    sqlite3_free(v15);
    v27 = v36(a1, &v38, off_18009B6E0);
    if ( v27 )
    {
      if ( v27 != 256 )
      {
        if ( a4 )
          *a4 = (const char *)sqlite3_mprintf("error during initialization: %s", v38);
        sqlite3_free(v38);
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        return 1;
      }
    }
    else
    {
      v28 = (void *)sqlite3DbMallocZero(a1, 8LL * *((int *)a1 + 59) + 8);
      if ( !v28 )
        return 7;
      v29 = *((int *)a1 + 59);
      if ( (int)v29 > 0 )
        memcpy_0(v28, (const void *)a1[30], 8 * v29);
      sqlite3DbFree(a1, a1[30]);
      v30 = *((int *)a1 + 59);
      a1[30] = (__int64)v28;
      *((_QWORD *)v28 + v30) = v10;
      ++*((_DWORD *)a1 + 59);
    }
    return 0;
  }
  if ( a4 )
    *a4 = (const char *)sqlite3_mprintf("not authorized");
  return 1;
}

```

## disassembly

```asm
0x1800849d0  mov     rax, rsp
0x1800849d3  mov     [rax+18h], r8
0x1800849d7  push    rbx
0x1800849d8  push    rsi
0x1800849d9  push    rdi
0x1800849da  push    r12
0x1800849dc  push    r13
0x1800849de  push    r14
0x1800849e0  push    r15
0x1800849e2  sub     rsp, 50h
0x1800849e6  mov     rdi, [rcx]
0x1800849e9  mov     rsi, r9
0x1800849ec  mov     r12, rdx
0x1800849ef  mov     qword ptr [rax+20h], 0
0x1800849f7  mov     rbx, rcx
0x1800849fa  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800849fe  inc     r14
0x180084a01  cmp     byte ptr [rdx+r14], 0
0x180084a06  jnz     short loc_1800849FE
0x180084a08  mov     [rsp+88h+var_48], r14
0x180084a0d  test    rsi, rsi
0x180084a10  jz      short loc_180084A19
0x180084a12  mov     qword ptr [r9], 0
0x180084a19  mov     eax, [rcx+30h]
0x180084a1c  bt      rax, 10h
0x180084a21  jb      short loc_180084A40
0x180084a23  test    rsi, rsi
0x180084a26  jz      loc_180084E31
0x180084a2c  lea     rcx, aNotAuthorized; "not authorized"
0x180084a33  call    sqlite3_mprintf
0x180084a38  mov     [rsi], rax
0x180084a3b  jmp     loc_180084E31
0x180084a40  test    r8, r8
0x180084a43  lea     rax, aSqlite3Extensi; "sqlite3_extension_init"
0x180084a4a  mov     r13, r8
0x180084a4d  cmovz   r13, rax
0x180084a51  lea     rax, [r14-1]
0x180084a55  cmp     rax, 103h
0x180084a5b  ja      loc_180084DDA
0x180084a61  mov     rax, [rdi+48h]
0x180084a65  mov     rcx, rdi
0x180084a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a6d  mov     r15, rax
0x180084a70  xor     eax, eax
0x180084a72  mov     dword ptr [rsp+88h+arg_0], eax
0x180084a79  lea     rcx, cs:180000000h
0x180084a80  cmp     eax, 1
0x180084a83  jge     loc_180084B1C
0x180084a89  test    r15, r15
0x180084a8c  jnz     loc_180084B25
0x180084a92  cdqe
0x180084a94  mov     rdx, r12
0x180084a97  mov     [rsp+88h+var_58], rax
0x180084a9c  mov     r8, ds:rva off_18009C0D8[rcx+rax*8]; "dll" ...
0x180084aa4  lea     rcx, aSS_2; "%s.%s"
0x180084aab  call    sqlite3_mprintf
0x180084ab0  mov     [rsp+88h+var_50], rax
0x180084ab5  mov     rdx, rax
0x180084ab8  test    rax, rax
0x180084abb  jz      loc_180084B84
0x180084ac1  mov     rax, [rsp+88h+var_58]
0x180084ac6  lea     r9, cs:180000000h
0x180084acd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180084ad1  mov     r8, ds:rva off_18009C0D8[r9+rax*8]; "dll" ...
0x180084ad9  inc     rcx
0x180084adc  cmp     byte ptr [r8+rcx], 0
0x180084ae1  jnz     short loc_180084AD9
0x180084ae3  lea     rax, [r14+1]
0x180084ae7  add     rax, rcx
0x180084aea  cmp     rax, 104h
0x180084af0  ja      short loc_180084B06
0x180084af2  mov     rax, [rdi+48h]
0x180084af6  mov     rcx, rdi
0x180084af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084afe  mov     rdx, [rsp+88h+var_50]
0x180084b03  mov     r15, rax
0x180084b06  mov     rcx, rdx
0x180084b09  call    sqlite3_free
0x180084b0e  mov     eax, dword ptr [rsp+88h+arg_0]
0x180084b15  inc     eax
0x180084b17  jmp     loc_180084A72
0x180084b1c  test    r15, r15
0x180084b1f  jz      loc_180084DDA
0x180084b25  mov     rax, [rdi+58h]
0x180084b29  mov     r8, r13
0x180084b2c  mov     rdx, r15
0x180084b2f  mov     rcx, rdi
0x180084b32  xor     r14d, r14d
0x180084b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b3a  mov     [rsp+88h+arg_0], rax
0x180084b42  test    rax, rax
0x180084b45  jnz     loc_180084CF4
0x180084b4b  cmp     [rsp+88h+arg_10], r14
0x180084b53  jnz     loc_180084C6A
0x180084b59  mov     rcx, r12
0x180084b5c  call    sqlite3Strlen30
0x180084b61  movsxd  r13, eax
0x180084b64  lea     rcx, [r13+1Eh]
0x180084b68  call    sqlite3_malloc64
0x180084b6d  mov     r14, rax
0x180084b70  test    rax, rax
0x180084b73  jnz     short loc_180084B8E
0x180084b75  mov     rax, [rdi+60h]
0x180084b79  mov     rdx, r15
0x180084b7c  mov     rcx, rdi
0x180084b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b84  mov     eax, 7
0x180084b89  jmp     loc_180084E36
0x180084b8e  mov     rax, 5F336574696C7173h
0x180084b98  mov     [r14], rax
0x180084b9b  jmp     short loc_180084BAD
0x180084b9d  cmp     byte ptr [r13+r12+0], 2Fh ; '/'
0x180084ba3  jz      short loc_180084BB3
0x180084ba5  cmp     byte ptr [r13+r12+0], 5Ch ; '\'
0x180084bab  jz      short loc_180084BB3
0x180084bad  sub     r13d, 1
0x180084bb1  jns     short loc_180084B9D
0x180084bb3  lea     eax, [r13+1]
0x180084bb7  mov     r8d, 3
0x180084bbd  movsxd  rcx, eax
0x180084bc0  lea     rdx, aLib; "lib"
0x180084bc7  add     rcx, r12
0x180084bca  call    sqlite3_strnicmp
0x180084bcf  neg     eax
0x180084bd1  mov     r8d, 8
0x180084bd7  sbb     ecx, ecx
0x180084bd9  and     ecx, 0FFFFFFFDh
0x180084bdc  lea     edx, [rcx+4]
0x180084bdf  add     edx, r13d
0x180084be2  movsxd  rax, edx
0x180084be5  movsx   ecx, byte ptr [rax+r12]
0x180084bea  test    ecx, ecx
0x180084bec  jz      short loc_180084C2A
0x180084bee  lea     r9, cs:180000000h
0x180084bf5  cmp     ecx, 2Eh ; '.'
0x180084bf8  jz      short loc_180084C2A
0x180084bfa  movzx   eax, cl
0x180084bfd  test    byte ptr [rax+r9+9E630h], 2
0x180084c06  jz      short loc_180084C1C
0x180084c08  mov     eax, ecx
0x180084c0a  movsxd  rcx, r8d
0x180084c0d  inc     r8d
0x180084c10  mov     al, [rax+r9+9E760h]
0x180084c18  mov     [rcx+r14], al
0x180084c1c  inc     edx
0x180084c1e  movsxd  rax, edx
0x180084c21  movsx   ecx, byte ptr [rax+r12]
0x180084c26  test    ecx, ecx
0x180084c28  jnz     short loc_180084BF5
0x180084c2a  mov     eax, dword ptr cs:aInit; "_init"
0x180084c30  mov     rdx, r15
0x180084c33  movsxd  rcx, r8d
0x180084c36  mov     r8, r14
0x180084c39  mov     [rcx+r14], eax
0x180084c3d  movzx   eax, word ptr cs:aInit+4; "t"
0x180084c44  mov     [rcx+r14+4], ax
0x180084c4a  mov     rcx, rdi
0x180084c4d  mov     rax, [rdi+58h]
0x180084c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c56  mov     [rsp+88h+arg_0], rax
0x180084c5e  test    rax, rax
0x180084c61  jnz     loc_180084CF4
0x180084c67  mov     r13, r14
0x180084c6a  test    rsi, rsi
0x180084c6d  jz      short loc_180084CD8
0x180084c6f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180084c73  inc     rcx
0x180084c76  cmp     byte ptr [rcx+r13], 0
0x180084c7b  jnz     short loc_180084C73
0x180084c7d  mov     rbx, [rsp+88h+var_48]
0x180084c82  add     rbx, rcx
0x180084c85  lea     rcx, [rbx+12Ch]
0x180084c8c  call    sqlite3_malloc64
0x180084c91  mov     [rsp+88h+arg_18], rax
0x180084c99  mov     [rsi], rax
0x180084c9c  test    rax, rax
0x180084c9f  jz      short loc_180084CD8
0x180084ca1  mov     r9, r13
0x180084ca4  mov     [rsp+88h+var_68], r12
0x180084ca9  lea     r8, aNoEntryPointSI; "no entry point [%s] in shared library ["...
0x180084cb0  mov     rdx, rax
0x180084cb3  lea     ecx, [rbx+12Ch]
0x180084cb9  call    sqlite3_snprintf
0x180084cbe  mov     r8, [rsp+88h+arg_18]
0x180084cc6  lea     edx, [rbx+12Bh]
0x180084ccc  mov     rax, [rdi+50h]
0x180084cd0  mov     rcx, rdi
0x180084cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084cd8  mov     rax, [rdi+60h]
0x180084cdc  mov     rdx, r15
0x180084cdf  mov     rcx, rdi
0x180084ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084ce7  mov     rcx, r14
0x180084cea  call    sqlite3_free
0x180084cef  jmp     loc_180084E31
0x180084cf4  mov     rcx, r14
0x180084cf7  call    sqlite3_free
0x180084cfc  mov     rax, [rsp+88h+arg_0]
0x180084d04  lea     r8, off_18009B6E0
0x180084d0b  lea     rdx, [rsp+88h+arg_18]
0x180084d13  mov     rcx, rbx
0x180084d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d1b  test    eax, eax
0x180084d1d  jz      short loc_180084D6A
0x180084d1f  cmp     eax, 100h
0x180084d24  jnz     short loc_180084D2D
0x180084d26  xor     eax, eax
0x180084d28  jmp     loc_180084E36
0x180084d2d  test    rsi, rsi
0x180084d30  jz      short loc_180084D49
0x180084d32  mov     rdx, [rsp+88h+arg_18]
0x180084d3a  lea     rcx, aErrorDuringIni; "error during initialization: %s"
0x180084d41  call    sqlite3_mprintf
0x180084d46  mov     [rsi], rax
0x180084d49  mov     rcx, [rsp+88h+arg_18]
0x180084d51  call    sqlite3_free
0x180084d56  mov     rax, [rdi+60h]
0x180084d5a  mov     rdx, r15
0x180084d5d  mov     rcx, rdi
0x180084d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d65  jmp     loc_180084E31
0x180084d6a  movsxd  rdx, dword ptr [rbx+0ECh]
0x180084d71  mov     rcx, rbx
0x180084d74  lea     rdx, ds:8[rdx*8]
0x180084d7c  call    sqlite3DbMallocZero
0x180084d81  mov     rdi, rax
0x180084d84  test    rax, rax
0x180084d87  jz      loc_180084B84
0x180084d8d  movsxd  rax, dword ptr [rbx+0ECh]
0x180084d94  test    eax, eax
0x180084d96  jle     short loc_180084DAE
0x180084d98  mov     rdx, [rbx+0F0h]; Src
0x180084d9f  mov     r8, rax
0x180084da2  shl     r8, 3; Size
0x180084da6  mov     rcx, rdi; void *
0x180084da9  call    memcpy_0
0x180084dae  mov     rdx, [rbx+0F0h]
0x180084db5  mov     rcx, rbx
0x180084db8  call    sqlite3DbFree
0x180084dbd  movsxd  rax, dword ptr [rbx+0ECh]
0x180084dc4  mov     [rbx+0F0h], rdi
0x180084dcb  mov     [rdi+rax*8], r15
0x180084dcf  inc     dword ptr [rbx+0ECh]
0x180084dd5  jmp     loc_180084D26
0x180084dda  test    rsi, rsi
0x180084ddd  jz      short loc_180084E31
0x180084ddf  lea     rbx, [r14+12Ch]
0x180084de6  mov     rcx, rbx
0x180084de9  call    sqlite3_malloc64
0x180084dee  mov     [rsp+88h+arg_18], rax
0x180084df6  mov     [rsi], rax
0x180084df9  test    rax, rax
0x180084dfc  jz      short loc_180084E31
0x180084dfe  mov     r9d, 104h
0x180084e04  mov     [rsp+88h+var_68], r12
0x180084e09  lea     r8, aUnableToOpenSh; "unable to open shared library [%.*s]"
0x180084e10  mov     rdx, rax
0x180084e13  mov     ecx, ebx
0x180084e15  call    sqlite3_snprintf
0x180084e1a  mov     r8, [rsp+88h+arg_18]
0x180084e22  lea     edx, [rbx-1]
0x180084e25  mov     rax, [rdi+50h]
0x180084e29  mov     rcx, rdi
0x180084e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e31  mov     eax, 1
0x180084e36  add     rsp, 50h
0x180084e3a  pop     r15
0x180084e3c  pop     r14
0x180084e3e  pop     r13
0x180084e40  pop     r12
0x180084e42  pop     rdi
0x180084e43  pop     rsi
0x180084e44  pop     rbx
0x180084e45  retn
```
