# sqlite3LoadExtension

- ea: `0x1800857f8`
- end: `0x180085c6e`
- name: `sqlite3LoadExtension`
- size: `1142`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180096400`

## callees

- `0x180012470`
- `0x18002b81c`
- `0x18002b8ec`
- `0x1800367a0`
- `0x18003f650`
- `0x180042bb0`
- `0x1800857f8`
- `0x1800964a0`
- `0x180096550`
- `0x1800a6d08`
- `0x1800a8010`

## string_xrefs

- `0x18008586b`: `sqlite3_extension_init`
- `0x180085b62`: `error during initialization: %s`
- `0x180085c31`: `unable to open shared library [%.*s]`

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
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r13
  __int64 v19; // rdx
  __int64 v20; // r8
  int v22; // eax
  int v23; // r8d
  int v24; // edx
  unsigned int j; // ecx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // ebx
  const char *v30; // rax
  int v31; // eax
  void *v32; // rdi
  __int64 v33; // rax
  __int64 v34; // rax
  const char *v35; // rax
  __int64 v36; // [rsp+30h] [rbp-58h]
  __int64 v37; // [rsp+38h] [rbp-50h]
  __int64 v38; // [rsp+40h] [rbp-48h]
  int v39; // [rsp+90h] [rbp+8h]
  __int64 (__fastcall *v40)(__int64 *, const char **, __int64 (__fastcall **)()); // [rsp+90h] [rbp+8h]
  const char *v42; // [rsp+A8h] [rbp+20h] BYREF

  v4 = *a1;
  v42 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v38 = v8;
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
        v35 = (const char *)sqlite3_malloc64(v8 + 300, a2, a3);
        v42 = v35;
        *a4 = v35;
        if ( v35 )
        {
          sqlite3_snprintf((unsigned int)(v8 + 300), v35, "unable to open shared library [%.*s]", 260, a2);
          (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v8 + 299), v42);
        }
      }
      return 1;
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(v4 + 72))(v4);
    for ( i = 0; ; i = v39 + 1 )
    {
      v39 = i;
      if ( i >= 1 )
        break;
      if ( v10 )
        goto LABEL_21;
      v36 = i;
      v37 = sqlite3_mprintf("%s.%s", a2, off_1800AA488[i]);
      v12 = v37;
      if ( !v37 )
        return 7;
      v13 = -1;
      do
        ++v13;
      while ( off_1800AA488[v36][v13] );
      if ( (unsigned __int64)(v13 + v8 + 1) <= 0x104 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, __int64))(v4 + 72))(v4, v37);
        v12 = v37;
        v10 = v14;
      }
      sqlite3_free(v12);
    }
    if ( !v10 )
      goto LABEL_53;
LABEL_21:
    v15 = 0;
    v40 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, const char *))(v4 + 88))(
                                                                                         v4,
                                                                                         v10,
                                                                                         v9);
    if ( !v40 )
    {
      if ( a3 )
        goto LABEL_37;
      v18 = (int)sqlite3Strlen30(a2, v16, v17);
      v15 = (_QWORD *)sqlite3_malloc64(v18 + 30, v19, v20);
      if ( !v15 )
      {
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        return 7;
      }
      *v15 = 0x5F336574696C7173LL;
      do
        LODWORD(v18) = v18 - 1;
      while ( (int)v18 >= 0 && a2[(unsigned int)v18] != 47 && a2[(unsigned int)v18] != 92 );
      v22 = sqlite3_strnicmp(&a2[(int)v18 + 1], "lib", 3);
      v23 = 8;
      v24 = v18 + (v22 != 0 ? 1 : 4);
      for ( j = a2[v24]; a2[v24]; j = a2[++v24] )
      {
        if ( j == 46 )
          break;
        if ( (*((_BYTE *)&qword_1800ADE90 + (unsigned __int8)j) & 2) != 0 )
        {
          v26 = j;
          v27 = v23++;
          *((_BYTE *)v15 + v27) = *((_BYTE *)qword_1800ADCF0 + v26);
        }
      }
      strcpy((char *)v15 + v23, "_init");
      v40 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(v4 + 88))(
                                                                                           v4,
                                                                                           v10,
                                                                                           v15);
      if ( !v40 )
      {
        v9 = (const char *)v15;
LABEL_37:
        if ( a4 )
        {
          v28 = -1;
          do
            ++v28;
          while ( v9[v28] );
          v29 = v28 + v38;
          v30 = (const char *)sqlite3_malloc64(v28 + v38 + 300, v16, v17);
          v42 = v30;
          *a4 = v30;
          if ( v30 )
          {
            sqlite3_snprintf((unsigned int)(v29 + 300), v30, "no entry point [%s] in shared library [%s]", v9, a2);
            (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v29 + 299), v42);
          }
        }
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        sqlite3_free(v15);
        return 1;
      }
    }
    sqlite3_free(v15);
    v31 = v40(a1, &v42, off_1800A9840);
    if ( v31 )
    {
      if ( v31 != 256 )
      {
        if ( a4 )
          *a4 = (const char *)sqlite3_mprintf("error during initialization: %s", v42);
        sqlite3_free(v42);
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        return 1;
      }
    }
    else
    {
      v32 = (void *)sqlite3DbMallocZero(a1, 8LL * *((int *)a1 + 59) + 8);
      if ( !v32 )
        return 7;
      v33 = *((int *)a1 + 59);
      if ( (int)v33 > 0 )
        memcpy_0(v32, (const void *)a1[30], 8 * v33);
      sqlite3DbFree(a1, a1[30]);
      v34 = *((int *)a1 + 59);
      a1[30] = (__int64)v32;
      *((_QWORD *)v32 + v34) = v10;
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
0x1800857f8  mov     rax, rsp
0x1800857fb  mov     [rax+18h], r8
0x1800857ff  push    rbx
0x180085800  push    rsi
0x180085801  push    rdi
0x180085802  push    r12
0x180085804  push    r13
0x180085806  push    r14
0x180085808  push    r15
0x18008580a  sub     rsp, 50h
0x18008580e  mov     rdi, [rcx]
0x180085811  mov     rsi, r9
0x180085814  mov     r12, rdx
0x180085817  mov     qword ptr [rax+20h], 0
0x18008581f  mov     rbx, rcx
0x180085822  or      r14, 0FFFFFFFFFFFFFFFFh
0x180085826  inc     r14
0x180085829  cmp     byte ptr [rdx+r14], 0
0x18008582e  jnz     short loc_180085826
0x180085830  mov     [rsp+88h+var_48], r14
0x180085835  test    rsi, rsi
0x180085838  jz      short loc_180085841
0x18008583a  mov     qword ptr [r9], 0
0x180085841  mov     eax, [rcx+30h]
0x180085844  bt      rax, 10h
0x180085849  jb      short loc_180085868
0x18008584b  test    rsi, rsi
0x18008584e  jz      loc_180085C59
0x180085854  lea     rcx, aNotAuthorized; "not authorized"
0x18008585b  call    sqlite3_mprintf
0x180085860  mov     [rsi], rax
0x180085863  jmp     loc_180085C59
0x180085868  test    r8, r8
0x18008586b  lea     rax, aSqlite3Extensi; "sqlite3_extension_init"
0x180085872  mov     r13, r8
0x180085875  cmovz   r13, rax
0x180085879  lea     rax, [r14-1]
0x18008587d  cmp     rax, 103h
0x180085883  ja      loc_180085C02
0x180085889  mov     rax, [rdi+48h]
0x18008588d  mov     rcx, rdi
0x180085890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085895  mov     r15, rax
0x180085898  xor     eax, eax
0x18008589a  mov     dword ptr [rsp+88h+arg_0], eax
0x1800858a1  lea     rcx, __ImageBase
0x1800858a8  cmp     eax, 1
0x1800858ab  jge     loc_180085944
0x1800858b1  test    r15, r15
0x1800858b4  jnz     loc_18008594D
0x1800858ba  cdqe
0x1800858bc  mov     rdx, r12
0x1800858bf  mov     [rsp+88h+var_58], rax
0x1800858c4  mov     r8, ds:rva off_1800AA488[rcx+rax*8]; "dll" ...
0x1800858cc  lea     rcx, aSS_5; "%s.%s"
0x1800858d3  call    sqlite3_mprintf
0x1800858d8  mov     [rsp+88h+var_50], rax
0x1800858dd  mov     rdx, rax
0x1800858e0  test    rax, rax
0x1800858e3  jz      loc_1800859AC
0x1800858e9  mov     rax, [rsp+88h+var_58]
0x1800858ee  lea     r9, __ImageBase
0x1800858f5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800858f9  mov     r8, ds:rva off_1800AA488[r9+rax*8]; "dll" ...
0x180085901  inc     rcx
0x180085904  cmp     byte ptr [r8+rcx], 0
0x180085909  jnz     short loc_180085901
0x18008590b  lea     rax, [r14+1]
0x18008590f  add     rax, rcx
0x180085912  cmp     rax, 104h
0x180085918  ja      short loc_18008592E
0x18008591a  mov     rax, [rdi+48h]
0x18008591e  mov     rcx, rdi
0x180085921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085926  mov     rdx, [rsp+88h+var_50]
0x18008592b  mov     r15, rax
0x18008592e  mov     rcx, rdx
0x180085931  call    sqlite3_free
0x180085936  mov     eax, dword ptr [rsp+88h+arg_0]
0x18008593d  inc     eax
0x18008593f  jmp     loc_18008589A
0x180085944  test    r15, r15
0x180085947  jz      loc_180085C02
0x18008594d  mov     rax, [rdi+58h]
0x180085951  mov     r8, r13
0x180085954  mov     rdx, r15
0x180085957  mov     rcx, rdi
0x18008595a  xor     r14d, r14d
0x18008595d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085962  mov     [rsp+88h+arg_0], rax
0x18008596a  test    rax, rax
0x18008596d  jnz     loc_180085B1C
0x180085973  cmp     [rsp+88h+arg_10], r14
0x18008597b  jnz     loc_180085A92
0x180085981  mov     rcx, r12
0x180085984  call    sqlite3Strlen30
0x180085989  movsxd  r13, eax
0x18008598c  lea     rcx, [r13+1Eh]
0x180085990  call    sqlite3_malloc64
0x180085995  mov     r14, rax
0x180085998  test    rax, rax
0x18008599b  jnz     short loc_1800859B6
0x18008599d  mov     rax, [rdi+60h]
0x1800859a1  mov     rdx, r15
0x1800859a4  mov     rcx, rdi
0x1800859a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800859ac  mov     eax, 7
0x1800859b1  jmp     loc_180085C5E
0x1800859b6  mov     rax, 5F336574696C7173h
0x1800859c0  mov     [r14], rax
0x1800859c3  jmp     short loc_1800859D5
0x1800859c5  cmp     byte ptr [r13+r12+0], 2Fh ; '/'
0x1800859cb  jz      short loc_1800859DB
0x1800859cd  cmp     byte ptr [r13+r12+0], 5Ch ; '\'
0x1800859d3  jz      short loc_1800859DB
0x1800859d5  sub     r13d, 1
0x1800859d9  jns     short loc_1800859C5
0x1800859db  lea     eax, [r13+1]
0x1800859df  mov     r8d, 3
0x1800859e5  movsxd  rcx, eax
0x1800859e8  lea     rdx, aLib; "lib"
0x1800859ef  add     rcx, r12
0x1800859f2  call    sqlite3_strnicmp
0x1800859f7  neg     eax
0x1800859f9  mov     r8d, 8
0x1800859ff  sbb     ecx, ecx
0x180085a01  and     ecx, 0FFFFFFFDh
0x180085a04  lea     edx, [rcx+4]
0x180085a07  add     edx, r13d
0x180085a0a  movsxd  rax, edx
0x180085a0d  movsx   ecx, byte ptr [rax+r12]
0x180085a12  test    ecx, ecx
0x180085a14  jz      short loc_180085A52
0x180085a16  lea     r9, __ImageBase
0x180085a1d  cmp     ecx, 2Eh ; '.'
0x180085a20  jz      short loc_180085A52
0x180085a22  movzx   eax, cl
0x180085a25  test    byte ptr [rax+r9+0ADE90h], 2
0x180085a2e  jz      short loc_180085A44
0x180085a30  mov     eax, ecx
0x180085a32  movsxd  rcx, r8d
0x180085a35  inc     r8d
0x180085a38  mov     al, [rax+r9+0ADCF0h]
0x180085a40  mov     [rcx+r14], al
0x180085a44  inc     edx
0x180085a46  movsxd  rax, edx
0x180085a49  movsx   ecx, byte ptr [rax+r12]
0x180085a4e  test    ecx, ecx
0x180085a50  jnz     short loc_180085A1D
0x180085a52  mov     eax, dword ptr cs:aInit; "_init"
0x180085a58  mov     rdx, r15
0x180085a5b  movsxd  rcx, r8d
0x180085a5e  mov     r8, r14
0x180085a61  mov     [rcx+r14], eax
0x180085a65  movzx   eax, word ptr cs:aInit+4; "t"
0x180085a6c  mov     [rcx+r14+4], ax
0x180085a72  mov     rcx, rdi
0x180085a75  mov     rax, [rdi+58h]
0x180085a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085a7e  mov     [rsp+88h+arg_0], rax
0x180085a86  test    rax, rax
0x180085a89  jnz     loc_180085B1C
0x180085a8f  mov     r13, r14
0x180085a92  test    rsi, rsi
0x180085a95  jz      short loc_180085B00
0x180085a97  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180085a9b  inc     rcx
0x180085a9e  cmp     byte ptr [rcx+r13], 0
0x180085aa3  jnz     short loc_180085A9B
0x180085aa5  mov     rbx, [rsp+88h+var_48]
0x180085aaa  add     rbx, rcx
0x180085aad  lea     rcx, [rbx+12Ch]
0x180085ab4  call    sqlite3_malloc64
0x180085ab9  mov     [rsp+88h+arg_18], rax
0x180085ac1  mov     [rsi], rax
0x180085ac4  test    rax, rax
0x180085ac7  jz      short loc_180085B00
0x180085ac9  mov     r9, r13
0x180085acc  mov     [rsp+88h+var_68], r12
0x180085ad1  lea     r8, aNoEntryPointSI; "no entry point [%s] in shared library ["...
0x180085ad8  mov     rdx, rax
0x180085adb  lea     ecx, [rbx+12Ch]
0x180085ae1  call    sqlite3_snprintf
0x180085ae6  mov     r8, [rsp+88h+arg_18]
0x180085aee  lea     edx, [rbx+12Bh]
0x180085af4  mov     rax, [rdi+50h]
0x180085af8  mov     rcx, rdi
0x180085afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b00  mov     rax, [rdi+60h]
0x180085b04  mov     rdx, r15
0x180085b07  mov     rcx, rdi
0x180085b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b0f  mov     rcx, r14
0x180085b12  call    sqlite3_free
0x180085b17  jmp     loc_180085C59
0x180085b1c  mov     rcx, r14
0x180085b1f  call    sqlite3_free
0x180085b24  mov     rax, [rsp+88h+arg_0]
0x180085b2c  lea     r8, off_1800A9840
0x180085b33  lea     rdx, [rsp+88h+arg_18]
0x180085b3b  mov     rcx, rbx
0x180085b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b43  test    eax, eax
0x180085b45  jz      short loc_180085B92
0x180085b47  cmp     eax, 100h
0x180085b4c  jnz     short loc_180085B55
0x180085b4e  xor     eax, eax
0x180085b50  jmp     loc_180085C5E
0x180085b55  test    rsi, rsi
0x180085b58  jz      short loc_180085B71
0x180085b5a  mov     rdx, [rsp+88h+arg_18]
0x180085b62  lea     rcx, aErrorDuringIni; "error during initialization: %s"
0x180085b69  call    sqlite3_mprintf
0x180085b6e  mov     [rsi], rax
0x180085b71  mov     rcx, [rsp+88h+arg_18]
0x180085b79  call    sqlite3_free
0x180085b7e  mov     rax, [rdi+60h]
0x180085b82  mov     rdx, r15
0x180085b85  mov     rcx, rdi
0x180085b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b8d  jmp     loc_180085C59
0x180085b92  movsxd  rdx, dword ptr [rbx+0ECh]
0x180085b99  mov     rcx, rbx
0x180085b9c  lea     rdx, ds:8[rdx*8]
0x180085ba4  call    sqlite3DbMallocZero
0x180085ba9  mov     rdi, rax
0x180085bac  test    rax, rax
0x180085baf  jz      loc_1800859AC
0x180085bb5  movsxd  rax, dword ptr [rbx+0ECh]
0x180085bbc  test    eax, eax
0x180085bbe  jle     short loc_180085BD6
0x180085bc0  mov     rdx, [rbx+0F0h]; Src
0x180085bc7  mov     r8, rax
0x180085bca  shl     r8, 3; Size
0x180085bce  mov     rcx, rdi; void *
0x180085bd1  call    memcpy_0
0x180085bd6  mov     rdx, [rbx+0F0h]
0x180085bdd  mov     rcx, rbx
0x180085be0  call    sqlite3DbFree
0x180085be5  movsxd  rax, dword ptr [rbx+0ECh]
0x180085bec  mov     [rbx+0F0h], rdi
0x180085bf3  mov     [rdi+rax*8], r15
0x180085bf7  inc     dword ptr [rbx+0ECh]
0x180085bfd  jmp     loc_180085B4E
0x180085c02  test    rsi, rsi
0x180085c05  jz      short loc_180085C59
0x180085c07  lea     rbx, [r14+12Ch]
0x180085c0e  mov     rcx, rbx
0x180085c11  call    sqlite3_malloc64
0x180085c16  mov     [rsp+88h+arg_18], rax
0x180085c1e  mov     [rsi], rax
0x180085c21  test    rax, rax
0x180085c24  jz      short loc_180085C59
0x180085c26  mov     r9d, 104h
0x180085c2c  mov     [rsp+88h+var_68], r12
0x180085c31  lea     r8, aUnableToOpenSh; "unable to open shared library [%.*s]"
0x180085c38  mov     rdx, rax
0x180085c3b  mov     ecx, ebx
0x180085c3d  call    sqlite3_snprintf
0x180085c42  mov     r8, [rsp+88h+arg_18]
0x180085c4a  lea     edx, [rbx-1]
0x180085c4d  mov     rax, [rdi+50h]
0x180085c51  mov     rcx, rdi
0x180085c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c59  mov     eax, 1
0x180085c5e  add     rsp, 50h
0x180085c62  pop     r15
0x180085c64  pop     r14
0x180085c66  pop     r13
0x180085c68  pop     r12
0x180085c6a  pop     rdi
0x180085c6b  pop     rsi
0x180085c6c  pop     rbx
0x180085c6d  retn
```
