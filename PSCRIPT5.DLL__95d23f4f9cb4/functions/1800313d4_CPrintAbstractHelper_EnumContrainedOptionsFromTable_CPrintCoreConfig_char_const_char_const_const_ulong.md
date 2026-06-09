# CPrintAbstractHelper::EnumContrainedOptionsFromTable(CPrintCoreConfig *,char const *,char const * * * const,ulong *)

- ea: `0x1800313d4`
- end: `0x1800316ae`
- name: `?EnumContrainedOptionsFromTable@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBDQEAPEAPEBDPEAK@Z`
- size: `730`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *__hidden this, struct CPrintCoreConfig *, const char *, const char ***const, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180031350`

## callees

- `0x1800313d4`
- `0x180032d54`
- `0x18005d010`

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
0x1800313d4  mov     [rsp-40h+arg_10], r8
0x1800313d9  mov     [rsp-40h+arg_8], rdx
0x1800313de  push    rbp
0x1800313df  push    rbx
0x1800313e0  push    rsi
0x1800313e1  push    rdi
0x1800313e2  push    r12
0x1800313e4  push    r13
0x1800313e6  push    r14
0x1800313e8  push    r15
0x1800313ea  mov     rbp, rsp
0x1800313ed  sub     rsp, 48h
0x1800313f1  mov     rax, [rcx]
0x1800313f4  xor     ebx, ebx
0x1800313f6  mov     r12, r9
0x1800313f9  mov     [rbp+arg_0], ebx
0x1800313fc  mov     r14, r8
0x1800313ff  mov     [rbp+var_18], rbx
0x180031403  mov     r15, rcx
0x180031406  mov     rax, [rax+78h]
0x18003140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003140f  mov     r13, rax
0x180031412  mov     [r12], rbx
0x180031416  mov     rax, [rbp+arg_20]
0x18003141a  lea     r9, [rbp+arg_0]
0x18003141e  lea     r8, [rbp+var_18]
0x180031422  mov     rdx, r14
0x180031425  mov     [rax], ebx
0x180031427  mov     rcx, [r15]
0x18003142a  mov     rax, [rcx+28h]
0x18003142e  mov     rcx, r15
0x180031431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031436  cmp     [rbp+arg_0], 0
0x18003143a  mov     ebx, eax
0x18003143c  jz      loc_18003169B
0x180031442  cmp     dword ptr [r13+0], 2
0x180031447  mov     rsi, r13
0x18003144a  jz      loc_180031687
0x180031450  mov     rax, [rsi+8]
0x180031454  xor     edi, edi
0x180031456  mov     rdx, r14
0x180031459  mov     [rbp+arg_18], rdi
0x18003145d  sub     rdx, rax
0x180031460  movzx   r8d, byte ptr [rax]
0x180031464  movzx   ecx, byte ptr [rax+rdx]
0x180031468  sub     r8d, ecx
0x18003146b  jnz     short loc_180031474
0x18003146d  inc     rax
0x180031470  test    ecx, ecx
0x180031472  jnz     short loc_180031460
0x180031474  lea     r14, [rsi+10h]
0x180031478  test    r8d, r8d
0x18003147b  jnz     loc_180031531
0x180031481  mov     rax, [rbp+var_18]
0x180031485  mov     rcx, [r14]
0x180031488  mov     r8, [rax]
0x18003148b  sub     r8, rcx
0x18003148e  movzx   edx, byte ptr [rcx]
0x180031491  movzx   eax, byte ptr [rcx+r8]
0x180031496  sub     edx, eax
0x180031498  jnz     short loc_1800314A1
0x18003149a  inc     rcx
0x18003149d  test    eax, eax
0x18003149f  jnz     short loc_18003148E
0x1800314a1  test    edx, edx
0x1800314a3  jnz     loc_180031531
0x1800314a9  mov     rax, [r15]
0x1800314ac  lea     r9, [rbp+arg_18]
0x1800314b0  mov     r8, [rbp+arg_8]
0x1800314b4  mov     rcx, r15
0x1800314b7  mov     rdx, [r13+18h]
0x1800314bb  mov     rax, [rax+58h]
0x1800314bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314c4  mov     ebx, eax
0x1800314c6  test    eax, eax
0x1800314c8  js      loc_18003166B
0x1800314ce  cmp     [rsi], edi
0x1800314d0  jnz     short loc_1800314FD
0x1800314d2  mov     rax, [rsi+20h]
0x1800314d6  mov     rdx, [rbp+arg_18]
0x1800314da  sub     rdx, rax
0x1800314dd  movzx   r8d, byte ptr [rax]
0x1800314e1  movzx   ecx, byte ptr [rax+rdx]
0x1800314e5  sub     r8d, ecx
0x1800314e8  jnz     short loc_1800314F1
0x1800314ea  inc     rax
0x1800314ed  test    ecx, ecx
0x1800314ef  jnz     short loc_1800314DD
0x1800314f1  test    r8d, r8d
0x1800314f4  setnz   dil
0x1800314f8  jmp     loc_180031621
0x1800314fd  cmp     dword ptr [rsi], 1
0x180031500  jnz     loc_18003164C
0x180031506  mov     rax, [rsi+20h]
0x18003150a  mov     r8, [rbp+arg_18]
0x18003150e  sub     r8, rax
0x180031511  movzx   ecx, byte ptr [rax]
0x180031514  movzx   edx, byte ptr [rax+r8]
0x180031519  sub     ecx, edx
0x18003151b  jnz     short loc_180031524
0x18003151d  inc     rax
0x180031520  test    edx, edx
0x180031522  jnz     short loc_180031511
0x180031524  test    ecx, ecx
0x180031526  jnz     loc_180031621
0x18003152c  jmp     loc_180031616
0x180031531  mov     rax, [rsi+18h]
0x180031535  mov     r8, [rbp+arg_10]
0x180031539  sub     r8, rax
0x18003153c  movzx   edx, byte ptr [rax]
0x18003153f  movzx   ecx, byte ptr [rax+r8]
0x180031544  sub     edx, ecx
0x180031546  jnz     short loc_18003154F
0x180031548  inc     rax
0x18003154b  test    ecx, ecx
0x18003154d  jnz     short loc_18003153C
0x18003154f  test    edx, edx
0x180031551  jnz     loc_18003161D
0x180031557  mov     rax, [rbp+var_18]
0x18003155b  mov     rcx, [rsi+20h]
0x18003155f  mov     r8, [rax]
0x180031562  sub     r8, rcx
0x180031565  movzx   edx, byte ptr [rcx]
0x180031568  movzx   eax, byte ptr [rcx+r8]
0x18003156d  sub     edx, eax
0x18003156f  jnz     short loc_180031578
0x180031571  inc     rcx
0x180031574  test    eax, eax
0x180031576  jnz     short loc_180031565
0x180031578  test    edx, edx
0x18003157a  jnz     short loc_1800315D0
0x18003157c  cmp     dword ptr [rsi], 1
0x18003157f  jnz     loc_18003161D
0x180031585  mov     rax, [r15]
0x180031588  lea     r9, [rbp+arg_18]
0x18003158c  mov     r8, [rbp+arg_8]
0x180031590  mov     rcx, r15
0x180031593  mov     rdx, [r13+8]
0x180031597  mov     rax, [rax+58h]
0x18003159b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315a0  mov     ebx, eax
0x1800315a2  test    eax, eax
0x1800315a4  js      loc_18003166B
0x1800315aa  mov     rax, [r14]
0x1800315ad  mov     r8, [rbp+arg_18]
0x1800315b1  sub     r8, rax
0x1800315b4  movzx   ecx, byte ptr [rax]
0x1800315b7  movzx   edx, byte ptr [rax+r8]
0x1800315bc  sub     ecx, edx
0x1800315be  jnz     loc_180031524
0x1800315c4  inc     rax
0x1800315c7  test    edx, edx
0x1800315c9  jnz     short loc_1800315B4
0x1800315cb  jmp     loc_180031524
0x1800315d0  cmp     [rsi], edi
0x1800315d2  jnz     short loc_18003161D
0x1800315d4  mov     rax, [r15]
0x1800315d7  lea     r9, [rbp+arg_18]
0x1800315db  mov     r8, [rbp+arg_8]
0x1800315df  mov     rcx, r15
0x1800315e2  mov     rdx, [r13+8]
0x1800315e6  mov     rax, [rax+58h]
0x1800315ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315ef  mov     ebx, eax
0x1800315f1  test    eax, eax
0x1800315f3  js      short loc_18003166B
0x1800315f5  mov     rax, [r14]
0x1800315f8  mov     r8, [rbp+arg_18]
0x1800315fc  sub     r8, rax
0x1800315ff  movzx   ecx, byte ptr [rax]
0x180031602  movzx   edx, byte ptr [rax+r8]
0x180031607  sub     ecx, edx
0x180031609  jnz     short loc_180031612
0x18003160b  inc     rax
0x18003160e  test    edx, edx
0x180031610  jnz     short loc_1800315FF
0x180031612  test    ecx, ecx
0x180031614  jnz     short loc_180031676
0x180031616  mov     edi, 1
0x18003161b  jmp     short loc_180031625
0x18003161d  test    ebx, ebx
0x18003161f  js      short loc_18003166B
0x180031621  test    edi, edi
0x180031623  jz      short loc_180031676
0x180031625  cmp     qword ptr [r12], 0
0x18003162a  jnz     short loc_18003164C
0x18003162c  mov     edx, [rbp+arg_0]
0x18003162f  mov     rcx, [rbp+arg_8]; this
0x180031633  shl     rdx, 3; unsigned __int64
0x180031637  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x18003163c  mov     [r12], rax
0x180031640  test    rax, rax
0x180031643  jnz     short loc_18003164C
0x180031645  mov     ebx, 8007000Eh
0x18003164a  jmp     short loc_180031676
0x18003164c  test    edi, edi
0x18003164e  jz      short loc_180031676
0x180031650  mov     r9, [rbp+arg_20]
0x180031654  mov     rax, [rbp+var_18]
0x180031658  mov     rdx, [r12]
0x18003165c  mov     r8d, [r9]
0x18003165f  mov     rcx, [rax]
0x180031662  mov     [rdx+r8*8], rcx
0x180031666  inc     dword ptr [r9]
0x180031669  jmp     short loc_180031676
0x18003166b  xor     eax, eax
0x18003166d  cmp     ebx, 80004005h
0x180031673  cmovz   ebx, eax
0x180031676  mov     r14, [rbp+arg_10]
0x18003167a  add     rsi, 28h ; '('
0x18003167e  cmp     dword ptr [rsi], 2
0x180031681  jnz     loc_180031450
0x180031687  mov     eax, [rbp+arg_0]
0x18003168a  add     [rbp+var_18], 8
0x18003168f  add     eax, 0FFFFFFFFh
0x180031692  mov     [rbp+arg_0], eax
0x180031695  jnz     loc_180031442
0x18003169b  mov     eax, ebx
0x18003169d  add     rsp, 48h
0x1800316a1  pop     r15
0x1800316a3  pop     r14
0x1800316a5  pop     r13
0x1800316a7  pop     r12
0x1800316a9  pop     rdi
0x1800316aa  pop     rsi
0x1800316ab  pop     rbx
0x1800316ac  pop     rbp
0x1800316ad  retn
```
