# CPrintAbstractHelper::EnumContrainedOptionsFromTable(CPrintCoreConfig *,char const *,char const * * * const,ulong *)

- ea: `0x180032a24`
- end: `0x180032cff`
- name: `?EnumContrainedOptionsFromTable@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBDQEAPEAPEBDPEAK@Z`
- size: `731`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *__hidden this, struct CPrintCoreConfig *, const char *, const char ***const, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800329a0`

## callees

- `0x180032a24`
- `0x1800343c8`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall CPrintAbstractHelper::EnumContrainedOptionsFromTable(
        CPrintAbstractHelper *this,
        struct CPrintCoreConfig *a2,
        const char *a3,
        const char ***const a4,
        unsigned int *a5)
{
  __int64 v5; // rax
  const char *v7; // r14
  __int64 v9; // r13
  int v10; // ebx
  __int64 v11; // rsi
  const char *v12; // rax
  int v13; // edi
  signed __int64 v14; // rdx
  int v15; // ecx
  int v16; // r8d
  const char **v17; // r14
  const char *v18; // rcx
  int v19; // eax
  int v20; // edx
  unsigned __int8 *v21; // rax
  __int64 v22; // rdx
  int v23; // ecx
  int v24; // r8d
  unsigned __int8 *v25; // rax
  __int64 v26; // r8
  int v27; // edx
  int v28; // ecx
  const char *v29; // rax
  signed __int64 v30; // r8
  int v31; // ecx
  int v32; // edx
  const char *v33; // rcx
  signed __int64 v34; // r8
  int v35; // eax
  int v36; // edx
  const char *v37; // rax
  int v38; // edx
  const char *v39; // rax
  int v40; // edx
  int v41; // ecx
  const char **v42; // rax
  unsigned int *v43; // r9
  const char **v45; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v46; // [rsp+90h] [rbp+48h] BYREF
  CPrintCoreConfig *v47; // [rsp+98h] [rbp+50h]
  const char *v48; // [rsp+A0h] [rbp+58h]
  __int64 v49; // [rsp+A8h] [rbp+60h] BYREF

  v48 = a3;
  v47 = a2;
  v5 = *(_QWORD *)this;
  v46 = 0;
  v7 = a3;
  v45 = 0;
  v9 = (*(__int64 (__fastcall **)(CPrintAbstractHelper *))(v5 + 120))(this);
  *a4 = 0;
  *a5 = 0;
  v10 = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, const char *, const char ***, unsigned int *))(*(_QWORD *)this + 40LL))(
          this,
          v7,
          &v45,
          &v46);
  if ( v46 )
  {
    while ( 1 )
    {
      v11 = v9;
      if ( *(_DWORD *)v9 != 2 )
        break;
LABEL_54:
      ++v45;
      if ( !--v46 )
        return (unsigned int)v10;
    }
    while ( 1 )
    {
      v12 = *(const char **)(v11 + 8);
      v13 = 0;
      v49 = 0;
      v14 = v7 - v12;
      do
      {
        v15 = (unsigned __int8)v12[v14];
        v16 = *(unsigned __int8 *)v12 - v15;
        if ( v16 )
          break;
        ++v12;
      }
      while ( v15 );
      v17 = (const char **)(v11 + 16);
      if ( !v16 )
      {
        v18 = *v17;
        do
        {
          v19 = (unsigned __int8)v18[*v45 - *v17];
          v20 = *(unsigned __int8 *)v18 - v19;
          if ( v20 )
            break;
          ++v18;
        }
        while ( v19 );
        if ( !v20 )
          break;
      }
      v29 = *(const char **)(v11 + 24);
      v30 = v48 - v29;
      do
      {
        v31 = (unsigned __int8)v29[v30];
        v32 = *(unsigned __int8 *)v29 - v31;
        if ( v32 )
          break;
        ++v29;
      }
      while ( v31 );
      if ( v32 )
      {
LABEL_44:
        if ( v10 < 0 )
        {
LABEL_51:
          if ( v10 == -2147467259 )
            v10 = 0;
          goto LABEL_53;
        }
LABEL_45:
        if ( !v13 )
          goto LABEL_53;
        goto LABEL_46;
      }
      v33 = *(const char **)(v11 + 32);
      v34 = *v45 - v33;
      do
      {
        v35 = (unsigned __int8)v33[v34];
        v36 = *(unsigned __int8 *)v33 - v35;
        if ( v36 )
          break;
        ++v33;
      }
      while ( v35 );
      if ( !v36 )
      {
        if ( *(_DWORD *)v11 != 1 )
          goto LABEL_44;
        v10 = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, _QWORD, CPrintCoreConfig *, __int64 *))(*(_QWORD *)this + 88LL))(
                this,
                *(_QWORD *)(v9 + 8),
                v47,
                &v49);
        if ( v10 < 0 )
          goto LABEL_51;
        v37 = *v17;
        do
        {
          v38 = (unsigned __int8)v37[v49 - (_QWORD)*v17];
          v28 = *(unsigned __int8 *)v37 - v38;
          if ( v28 )
            break;
          ++v37;
        }
        while ( v38 );
LABEL_21:
        if ( v28 )
          goto LABEL_45;
        goto LABEL_43;
      }
      if ( *(_DWORD *)v11 )
        goto LABEL_44;
      v10 = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, _QWORD, CPrintCoreConfig *, __int64 *))(*(_QWORD *)this + 88LL))(
              this,
              *(_QWORD *)(v9 + 8),
              v47,
              &v49);
      if ( v10 < 0 )
        goto LABEL_51;
      v39 = *v17;
      do
      {
        v40 = (unsigned __int8)v39[v49 - (_QWORD)*v17];
        v41 = *(unsigned __int8 *)v39 - v40;
        if ( v41 )
          break;
        ++v39;
      }
      while ( v40 );
      if ( v41 )
        goto LABEL_53;
LABEL_43:
      v13 = 1;
LABEL_46:
      if ( *a4 || (v42 = (const char **)CPrintCoreConfig::PrivateAlloc(v47, 8LL * v46), (*a4 = v42) != 0) )
      {
LABEL_49:
        if ( v13 )
        {
          v43 = a5;
          (*a4)[*a5] = *v45;
          ++*v43;
        }
        goto LABEL_53;
      }
      v10 = -2147024882;
LABEL_53:
      v7 = v48;
      v11 += 40;
      if ( *(_DWORD *)v11 == 2 )
        goto LABEL_54;
    }
    v10 = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, _QWORD, CPrintCoreConfig *, __int64 *))(*(_QWORD *)this + 88LL))(
            this,
            *(_QWORD *)(v9 + 24),
            v47,
            &v49);
    if ( v10 < 0 )
      goto LABEL_51;
    if ( !*(_DWORD *)v11 )
    {
      v21 = *(unsigned __int8 **)(v11 + 32);
      v22 = v49 - (_QWORD)v21;
      do
      {
        v23 = v21[v22];
        v24 = *v21 - v23;
        if ( v24 )
          break;
        ++v21;
      }
      while ( v23 );
      LOBYTE(v13) = v24 != 0;
      goto LABEL_45;
    }
    if ( *(_DWORD *)v11 != 1 )
      goto LABEL_49;
    v25 = *(unsigned __int8 **)(v11 + 32);
    v26 = v49 - (_QWORD)v25;
    do
    {
      v27 = v25[v26];
      v28 = *v25 - v27;
      if ( v28 )
        break;
      ++v25;
    }
    while ( v27 );
    goto LABEL_21;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180032a24  mov     [rsp-40h+arg_10], r8
0x180032a29  mov     [rsp-40h+arg_8], rdx
0x180032a2e  push    rbp
0x180032a2f  push    rbx
0x180032a30  push    rsi
0x180032a31  push    rdi
0x180032a32  push    r12
0x180032a34  push    r13
0x180032a36  push    r14
0x180032a38  push    r15
0x180032a3a  mov     rbp, rsp
0x180032a3d  sub     rsp, 48h
0x180032a41  mov     rax, [rcx]
0x180032a44  xor     ebx, ebx
0x180032a46  mov     r12, r9
0x180032a49  mov     [rbp+arg_0], ebx
0x180032a4c  mov     r14, r8
0x180032a4f  mov     [rbp+var_18], rbx
0x180032a53  mov     r15, rcx
0x180032a56  mov     rax, [rax+78h]
0x180032a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a5f  mov     r13, rax
0x180032a62  mov     [r12], rbx
0x180032a66  mov     rax, [rbp+arg_20]
0x180032a6a  lea     r9, [rbp+arg_0]
0x180032a6e  lea     r8, [rbp+var_18]
0x180032a72  mov     rdx, r14
0x180032a75  mov     [rax], ebx
0x180032a77  mov     rcx, [r15]
0x180032a7a  mov     rax, [rcx+28h]
0x180032a7e  mov     rcx, r15
0x180032a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a86  cmp     [rbp+arg_0], 0
0x180032a8a  mov     ebx, eax
0x180032a8c  jz      loc_180032CEB
0x180032a92  cmp     dword ptr [r13+0], 2
0x180032a97  mov     rsi, r13
0x180032a9a  jz      loc_180032CD7
0x180032aa0  mov     rax, [rsi+8]
0x180032aa4  xor     edi, edi
0x180032aa6  mov     rdx, r14
0x180032aa9  mov     [rbp+arg_18], rdi
0x180032aad  sub     rdx, rax
0x180032ab0  movzx   r8d, byte ptr [rax]
0x180032ab4  movzx   ecx, byte ptr [rax+rdx]
0x180032ab8  sub     r8d, ecx
0x180032abb  jnz     short loc_180032AC4
0x180032abd  inc     rax
0x180032ac0  test    ecx, ecx
0x180032ac2  jnz     short loc_180032AB0
0x180032ac4  lea     r14, [rsi+10h]
0x180032ac8  test    r8d, r8d
0x180032acb  jnz     loc_180032B81
0x180032ad1  mov     rax, [rbp+var_18]
0x180032ad5  mov     rcx, [r14]
0x180032ad8  mov     r8, [rax]
0x180032adb  sub     r8, rcx
0x180032ade  movzx   edx, byte ptr [rcx]
0x180032ae1  movzx   eax, byte ptr [rcx+r8]
0x180032ae6  sub     edx, eax
0x180032ae8  jnz     short loc_180032AF1
0x180032aea  inc     rcx
0x180032aed  test    eax, eax
0x180032aef  jnz     short loc_180032ADE
0x180032af1  test    edx, edx
0x180032af3  jnz     loc_180032B81
0x180032af9  mov     rax, [r15]
0x180032afc  lea     r9, [rbp+arg_18]
0x180032b00  mov     r8, [rbp+arg_8]
0x180032b04  mov     rcx, r15
0x180032b07  mov     rdx, [r13+18h]
0x180032b0b  mov     rax, [rax+58h]
0x180032b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b14  mov     ebx, eax
0x180032b16  test    eax, eax
0x180032b18  js      loc_180032CBB
0x180032b1e  cmp     [rsi], edi
0x180032b20  jnz     short loc_180032B4D
0x180032b22  mov     rax, [rsi+20h]
0x180032b26  mov     rdx, [rbp+arg_18]
0x180032b2a  sub     rdx, rax
0x180032b2d  movzx   r8d, byte ptr [rax]
0x180032b31  movzx   ecx, byte ptr [rax+rdx]
0x180032b35  sub     r8d, ecx
0x180032b38  jnz     short loc_180032B41
0x180032b3a  inc     rax
0x180032b3d  test    ecx, ecx
0x180032b3f  jnz     short loc_180032B2D
0x180032b41  test    r8d, r8d
0x180032b44  setnz   dil
0x180032b48  jmp     loc_180032C71
0x180032b4d  cmp     dword ptr [rsi], 1
0x180032b50  jnz     loc_180032C9C
0x180032b56  mov     rax, [rsi+20h]
0x180032b5a  mov     r8, [rbp+arg_18]
0x180032b5e  sub     r8, rax
0x180032b61  movzx   ecx, byte ptr [rax]
0x180032b64  movzx   edx, byte ptr [rax+r8]
0x180032b69  sub     ecx, edx
0x180032b6b  jnz     short loc_180032B74
0x180032b6d  inc     rax
0x180032b70  test    edx, edx
0x180032b72  jnz     short loc_180032B61
0x180032b74  test    ecx, ecx
0x180032b76  jnz     loc_180032C71
0x180032b7c  jmp     loc_180032C66
0x180032b81  mov     rax, [rsi+18h]
0x180032b85  mov     r8, [rbp+arg_10]
0x180032b89  sub     r8, rax
0x180032b8c  movzx   edx, byte ptr [rax]
0x180032b8f  movzx   ecx, byte ptr [rax+r8]
0x180032b94  sub     edx, ecx
0x180032b96  jnz     short loc_180032B9F
0x180032b98  inc     rax
0x180032b9b  test    ecx, ecx
0x180032b9d  jnz     short loc_180032B8C
0x180032b9f  test    edx, edx
0x180032ba1  jnz     loc_180032C6D
0x180032ba7  mov     rax, [rbp+var_18]
0x180032bab  mov     rcx, [rsi+20h]
0x180032baf  mov     r8, [rax]
0x180032bb2  sub     r8, rcx
0x180032bb5  movzx   edx, byte ptr [rcx]
0x180032bb8  movzx   eax, byte ptr [rcx+r8]
0x180032bbd  sub     edx, eax
0x180032bbf  jnz     short loc_180032BC8
0x180032bc1  inc     rcx
0x180032bc4  test    eax, eax
0x180032bc6  jnz     short loc_180032BB5
0x180032bc8  test    edx, edx
0x180032bca  jnz     short loc_180032C20
0x180032bcc  cmp     dword ptr [rsi], 1
0x180032bcf  jnz     loc_180032C6D
0x180032bd5  mov     rax, [r15]
0x180032bd8  lea     r9, [rbp+arg_18]
0x180032bdc  mov     r8, [rbp+arg_8]
0x180032be0  mov     rcx, r15
0x180032be3  mov     rdx, [r13+8]
0x180032be7  mov     rax, [rax+58h]
0x180032beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bf0  mov     ebx, eax
0x180032bf2  test    eax, eax
0x180032bf4  js      loc_180032CBB
0x180032bfa  mov     rax, [r14]
0x180032bfd  mov     r8, [rbp+arg_18]
0x180032c01  sub     r8, rax
0x180032c04  movzx   ecx, byte ptr [rax]
0x180032c07  movzx   edx, byte ptr [rax+r8]
0x180032c0c  sub     ecx, edx
0x180032c0e  jnz     loc_180032B74
0x180032c14  inc     rax
0x180032c17  test    edx, edx
0x180032c19  jnz     short loc_180032C04
0x180032c1b  jmp     loc_180032B74
0x180032c20  cmp     [rsi], edi
0x180032c22  jnz     short loc_180032C6D
0x180032c24  mov     rax, [r15]
0x180032c27  lea     r9, [rbp+arg_18]
0x180032c2b  mov     r8, [rbp+arg_8]
0x180032c2f  mov     rcx, r15
0x180032c32  mov     rdx, [r13+8]
0x180032c36  mov     rax, [rax+58h]
0x180032c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c3f  mov     ebx, eax
0x180032c41  test    eax, eax
0x180032c43  js      short loc_180032CBB
0x180032c45  mov     rax, [r14]
0x180032c48  mov     r8, [rbp+arg_18]
0x180032c4c  sub     r8, rax
0x180032c4f  movzx   ecx, byte ptr [rax]
0x180032c52  movzx   edx, byte ptr [rax+r8]
0x180032c57  sub     ecx, edx
0x180032c59  jnz     short loc_180032C62
0x180032c5b  inc     rax
0x180032c5e  test    edx, edx
0x180032c60  jnz     short loc_180032C4F
0x180032c62  test    ecx, ecx
0x180032c64  jnz     short loc_180032CC6
0x180032c66  mov     edi, 1
0x180032c6b  jmp     short loc_180032C75
0x180032c6d  test    ebx, ebx
0x180032c6f  js      short loc_180032CBB
0x180032c71  test    edi, edi
0x180032c73  jz      short loc_180032CC6
0x180032c75  cmp     qword ptr [r12], 0
0x180032c7a  jnz     short loc_180032C9C
0x180032c7c  mov     edx, [rbp+arg_0]
0x180032c7f  mov     rcx, [rbp+arg_8]; this
0x180032c83  shl     rdx, 3; unsigned __int64
0x180032c87  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x180032c8c  mov     [r12], rax
0x180032c90  test    rax, rax
0x180032c93  jnz     short loc_180032C9C
0x180032c95  mov     ebx, 8007000Eh
0x180032c9a  jmp     short loc_180032CC6
0x180032c9c  test    edi, edi
0x180032c9e  jz      short loc_180032CC6
0x180032ca0  mov     r9, [rbp+arg_20]
0x180032ca4  mov     rax, [rbp+var_18]
0x180032ca8  mov     rdx, [r12]
0x180032cac  mov     r8d, [r9]
0x180032caf  mov     rcx, [rax]
0x180032cb2  mov     [rdx+r8*8], rcx
0x180032cb6  inc     dword ptr [r9]
0x180032cb9  jmp     short loc_180032CC6
0x180032cbb  xor     eax, eax
0x180032cbd  cmp     ebx, 80004005h
0x180032cc3  cmovz   ebx, eax
0x180032cc6  mov     r14, [rbp+arg_10]
0x180032cca  add     rsi, 28h ; '('
0x180032cce  cmp     dword ptr [rsi], 2
0x180032cd1  jnz     loc_180032AA0
0x180032cd7  mov     eax, [rbp+arg_0]
0x180032cda  add     [rbp+var_18], 8
0x180032cdf  add     eax, 0FFFFFFFFh
0x180032ce2  mov     [rbp+arg_0], eax
0x180032ce5  jnz     loc_180032A92
0x180032ceb  mov     eax, ebx
0x180032ced  add     rsp, 48h
0x180032cf1  pop     r15
0x180032cf3  pop     r14
0x180032cf5  pop     r13
0x180032cf7  pop     r12
0x180032cf9  pop     rdi
0x180032cfa  pop     rsi
0x180032cfb  pop     rbx
0x180032cfc  pop     rbp
0x180032cfd  retn
```
