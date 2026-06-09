# CPrintAbstractHelper::WhyConstrainedFromTable(CPrintCoreConfig *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)

- ea: `0x180032998`
- end: `0x180032c0a`
- name: `?WhyConstrainedFromTable@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBD1PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z`
- size: `626`
- prototype: `int(CPrintAbstractHelper *__hidden this, struct CPrintCoreConfig *, const char *, const char *, const struct _PRINT_FEATURE_OPTION **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180032c10`

## callees

- `0x18003100c`
- `0x180032998`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall CPrintAbstractHelper::WhyConstrainedFromTable(
        CPrintAbstractHelper *this,
        struct CPrintCoreConfig *a2,
        const char *a3,
        const char *a4,
        struct _PRINT_FEATURE_OPTION **a5,
        unsigned int *a6)
{
  int v6; // edi
  __int64 v11; // rax
  const struct _PRINT_FEATURE_OPTION **v12; // rsi
  __int64 v13; // rbx
  unsigned int *v14; // r12
  const char *v15; // rax
  const char *v16; // r8
  int v17; // ecx
  int v18; // edx
  const char *v19; // rax
  const char *v20; // r8
  int v21; // ecx
  int v22; // edx
  char *v23; // rcx
  char *v24; // r8
  int v25; // eax
  int v26; // edx
  char *v27; // rax
  char *v28; // r8
  int v29; // ecx
  int v30; // edx
  int ConstraintsPair; // eax
  const char *v32; // rax
  const char *v33; // r8
  int v34; // ecx
  int v35; // edx
  const char *v36; // rax
  const char *v37; // r8
  int v38; // ecx
  int v39; // edx
  const char *v40; // rax
  const char *v41; // rdx
  int v42; // ecx
  int v43; // r8d
  char *v44; // rax
  char *v45; // r8
  int v46; // ecx
  int v47; // edx

  v6 = 0;
  v11 = (*(__int64 (__fastcall **)(CPrintAbstractHelper *))(*(_QWORD *)this + 120LL))(this);
  v12 = (const struct _PRINT_FEATURE_OPTION **)a5;
  v13 = v11;
  v14 = a6;
  *a5 = 0;
  *v14 = 0;
  while ( *(_DWORD *)v13 != 2 && !*v12 )
  {
    v15 = *(const char **)(v13 + 8);
    v16 = (const char *)(a3 - v15);
    a5 = 0;
    do
    {
      v17 = (unsigned __int8)v16[(_QWORD)v15];
      v18 = *(unsigned __int8 *)v15 - v17;
      if ( v18 )
        break;
      ++v15;
    }
    while ( v17 );
    if ( v18 )
      goto LABEL_26;
    v19 = *(const char **)(v13 + 16);
    v20 = (const char *)(a4 - v19);
    do
    {
      v21 = (unsigned __int8)v20[(_QWORD)v19];
      v22 = *(unsigned __int8 *)v19 - v21;
      if ( v22 )
        break;
      ++v19;
    }
    while ( v21 );
    if ( v22 )
    {
LABEL_26:
      v32 = *(const char **)(v13 + 24);
      v33 = (const char *)(a3 - v32);
      do
      {
        v34 = (unsigned __int8)v33[(_QWORD)v32];
        v35 = *(unsigned __int8 *)v32 - v34;
        if ( v35 )
          break;
        ++v32;
      }
      while ( v34 );
      if ( v35 )
        goto LABEL_48;
      if ( *(_DWORD *)v13 == 1 )
      {
        v36 = *(const char **)(v13 + 32);
        v37 = (const char *)(a4 - v36);
        do
        {
          v38 = (unsigned __int8)v37[(_QWORD)v36];
          v39 = *(unsigned __int8 *)v36 - v38;
          if ( v39 )
            break;
          ++v36;
        }
        while ( v38 );
        if ( v39 )
          goto LABEL_48;
      }
      else
      {
        if ( *(_DWORD *)v13 )
          goto LABEL_48;
        v40 = *(const char **)(v13 + 32);
        v41 = (const char *)(a4 - v40);
        do
        {
          v42 = (unsigned __int8)v41[(_QWORD)v40];
          v43 = *(unsigned __int8 *)v40 - v42;
          if ( v43 )
            break;
          ++v40;
        }
        while ( v42 );
        if ( !v43 )
          goto LABEL_48;
      }
      v6 = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, _QWORD, struct CPrintCoreConfig *, struct _PRINT_FEATURE_OPTION ***))(*(_QWORD *)this + 88LL))(
             this,
             *(_QWORD *)(v13 + 8),
             a2,
             &a5);
      if ( v6 >= 0 )
      {
        v44 = *(char **)(v13 + 16);
        v45 = (char *)((char *)a5 - v44);
        do
        {
          v46 = (unsigned __int8)v45[(_QWORD)v44];
          v47 = (unsigned __int8)*v44 - v46;
          if ( v47 )
            break;
          ++v44;
        }
        while ( v46 );
        if ( !v47 )
        {
          ConstraintsPair = CreateConstraintsPair(
                              a2,
                              *(const char **)(v13 + 24),
                              *(const char **)(v13 + 32),
                              *(const char **)(v13 + 8),
                              (const char *)a5,
                              v12,
                              v14);
          goto LABEL_47;
        }
      }
LABEL_48:
      v13 += 40;
      if ( v6 < 0 )
        return (unsigned int)v6;
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, _QWORD, struct CPrintCoreConfig *, struct _PRINT_FEATURE_OPTION ***))(*(_QWORD *)this + 88LL))(
             this,
             *(_QWORD *)(v13 + 24),
             a2,
             &a5);
      if ( v6 < 0 || !a5 )
        goto LABEL_48;
      if ( *(_DWORD *)v13 )
      {
        if ( *(_DWORD *)v13 != 1 )
          goto LABEL_48;
        v27 = *(char **)(v13 + 32);
        v28 = (char *)((char *)a5 - v27);
        do
        {
          v29 = (unsigned __int8)v28[(_QWORD)v27];
          v30 = (unsigned __int8)*v27 - v29;
          if ( v30 )
            break;
          ++v27;
        }
        while ( v29 );
        if ( v30 )
          goto LABEL_48;
LABEL_25:
        ConstraintsPair = CreateConstraintsPair(
                            a2,
                            *(const char **)(v13 + 8),
                            *(const char **)(v13 + 16),
                            *(const char **)(v13 + 24),
                            (const char *)a5,
                            v12,
                            v14);
LABEL_47:
        v6 = ConstraintsPair;
        goto LABEL_48;
      }
      v23 = *(char **)(v13 + 32);
      v24 = (char *)((char *)a5 - v23);
      do
      {
        v25 = (unsigned __int8)v24[(_QWORD)v23];
        v26 = (unsigned __int8)*v23 - v25;
        if ( v26 )
          break;
        ++v23;
      }
      while ( v25 );
      if ( v26 )
        goto LABEL_25;
      v13 += 40;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180032998  push    rbx
0x18003299a  push    rbp
0x18003299b  push    rsi
0x18003299c  push    rdi
0x18003299d  push    r12
0x18003299f  push    r13
0x1800329a1  push    r14
0x1800329a3  push    r15
0x1800329a5  sub     rsp, 48h
0x1800329a9  mov     rax, [rcx]
0x1800329ac  xor     edi, edi
0x1800329ae  mov     rbp, r9
0x1800329b1  mov     r13, r8
0x1800329b4  mov     r15, rdx
0x1800329b7  mov     r14, rcx
0x1800329ba  mov     rax, [rax+78h]
0x1800329be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329c3  mov     rsi, [rsp+88h+arg_20]
0x1800329cb  mov     rbx, rax
0x1800329ce  mov     r12, [rsp+88h+arg_28]
0x1800329d6  mov     [rsi], rdi
0x1800329d9  mov     [r12], edi
0x1800329dd  cmp     dword ptr [rbx], 2
0x1800329e0  jz      loc_180032BF7
0x1800329e6  cmp     qword ptr [rsi], 0
0x1800329ea  jnz     loc_180032BF7
0x1800329f0  mov     rax, [rbx+8]
0x1800329f4  mov     r8, r13
0x1800329f7  sub     r8, rax
0x1800329fa  mov     [rsp+88h+arg_20], 0
0x180032a06  movzx   edx, byte ptr [rax]
0x180032a09  movzx   ecx, byte ptr [rax+r8]
0x180032a0e  sub     edx, ecx
0x180032a10  jnz     short loc_180032A19
0x180032a12  inc     rax
0x180032a15  test    ecx, ecx
0x180032a17  jnz     short loc_180032A06
0x180032a19  test    edx, edx
0x180032a1b  jnz     loc_180032AFC
0x180032a21  mov     rax, [rbx+10h]
0x180032a25  mov     r8, rbp
0x180032a28  sub     r8, rax
0x180032a2b  movzx   edx, byte ptr [rax]
0x180032a2e  movzx   ecx, byte ptr [rax+r8]
0x180032a33  sub     edx, ecx
0x180032a35  jnz     short loc_180032A3E
0x180032a37  inc     rax
0x180032a3a  test    ecx, ecx
0x180032a3c  jnz     short loc_180032A2B
0x180032a3e  test    edx, edx
0x180032a40  jnz     loc_180032AFC
0x180032a46  mov     rax, [r14]
0x180032a49  lea     r9, [rsp+88h+arg_20]
0x180032a51  mov     rdx, [rbx+18h]
0x180032a55  mov     r8, r15
0x180032a58  mov     rcx, r14
0x180032a5b  mov     rax, [rax+58h]
0x180032a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a64  mov     edi, eax
0x180032a66  test    eax, eax
0x180032a68  js      loc_180032BEB
0x180032a6e  mov     r9, [rsp+88h+arg_20]
0x180032a76  test    r9, r9
0x180032a79  jz      loc_180032BEB
0x180032a7f  cmp     dword ptr [rbx], 0
0x180032a82  jnz     short loc_180032AAE
0x180032a84  mov     rcx, [rbx+20h]
0x180032a88  mov     r8, r9
0x180032a8b  sub     r8, rcx
0x180032a8e  movzx   edx, byte ptr [rcx]
0x180032a91  movzx   eax, byte ptr [rcx+r8]
0x180032a96  sub     edx, eax
0x180032a98  jnz     short loc_180032AA1
0x180032a9a  inc     rcx
0x180032a9d  test    eax, eax
0x180032a9f  jnz     short loc_180032A8E
0x180032aa1  test    edx, edx
0x180032aa3  jnz     short loc_180032ADC
0x180032aa5  add     rbx, 28h ; '('
0x180032aa9  jmp     loc_1800329DD
0x180032aae  cmp     dword ptr [rbx], 1
0x180032ab1  jnz     loc_180032BEB
0x180032ab7  mov     rax, [rbx+20h]
0x180032abb  mov     r8, r9
0x180032abe  sub     r8, rax
0x180032ac1  movzx   edx, byte ptr [rax]
0x180032ac4  movzx   ecx, byte ptr [rax+r8]
0x180032ac9  sub     edx, ecx
0x180032acb  jnz     short loc_180032AD4
0x180032acd  inc     rax
0x180032ad0  test    ecx, ecx
0x180032ad2  jnz     short loc_180032AC1
0x180032ad4  test    edx, edx
0x180032ad6  jnz     loc_180032BEB
0x180032adc  mov     r8, [rbx+10h]
0x180032ae0  mov     rdx, [rbx+8]
0x180032ae4  mov     [rsp+88h+var_58], r12
0x180032ae9  mov     [rsp+88h+var_60], rsi
0x180032aee  mov     [rsp+88h+var_68], r9
0x180032af3  mov     r9, [rbx+18h]
0x180032af7  jmp     loc_180032BE1
0x180032afc  mov     rax, [rbx+18h]
0x180032b00  mov     r8, r13
0x180032b03  sub     r8, rax
0x180032b06  movzx   edx, byte ptr [rax]
0x180032b09  movzx   ecx, byte ptr [rax+r8]
0x180032b0e  sub     edx, ecx
0x180032b10  jnz     short loc_180032B19
0x180032b12  inc     rax
0x180032b15  test    ecx, ecx
0x180032b17  jnz     short loc_180032B06
0x180032b19  test    edx, edx
0x180032b1b  jnz     loc_180032BEB
0x180032b21  cmp     dword ptr [rbx], 1
0x180032b24  jnz     short loc_180032B4D
0x180032b26  mov     rax, [rbx+20h]
0x180032b2a  mov     r8, rbp
0x180032b2d  sub     r8, rax
0x180032b30  movzx   edx, byte ptr [rax]
0x180032b33  movzx   ecx, byte ptr [rax+r8]
0x180032b38  sub     edx, ecx
0x180032b3a  jnz     short loc_180032B43
0x180032b3c  inc     rax
0x180032b3f  test    ecx, ecx
0x180032b41  jnz     short loc_180032B30
0x180032b43  test    edx, edx
0x180032b45  jnz     loc_180032BEB
0x180032b4b  jmp     short loc_180032B79
0x180032b4d  cmp     dword ptr [rbx], 0
0x180032b50  jnz     loc_180032BEB
0x180032b56  mov     rax, [rbx+20h]
0x180032b5a  mov     rdx, rbp
0x180032b5d  sub     rdx, rax
0x180032b60  movzx   r8d, byte ptr [rax]
0x180032b64  movzx   ecx, byte ptr [rax+rdx]
0x180032b68  sub     r8d, ecx
0x180032b6b  jnz     short loc_180032B74
0x180032b6d  inc     rax
0x180032b70  test    ecx, ecx
0x180032b72  jnz     short loc_180032B60
0x180032b74  test    r8d, r8d
0x180032b77  jz      short loc_180032BEB
0x180032b79  mov     rax, [r14]
0x180032b7c  lea     r9, [rsp+88h+arg_20]
0x180032b84  mov     rdx, [rbx+8]
0x180032b88  mov     r8, r15
0x180032b8b  mov     rcx, r14
0x180032b8e  mov     rax, [rax+58h]
0x180032b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b97  mov     edi, eax
0x180032b99  test    eax, eax
0x180032b9b  js      short loc_180032BEB
0x180032b9d  mov     r9, [rsp+88h+arg_20]
0x180032ba5  mov     rax, [rbx+10h]
0x180032ba9  mov     r8, r9
0x180032bac  sub     r8, rax
0x180032baf  movzx   edx, byte ptr [rax]
0x180032bb2  movzx   ecx, byte ptr [rax+r8]
0x180032bb7  sub     edx, ecx
0x180032bb9  jnz     short loc_180032BC2
0x180032bbb  inc     rax
0x180032bbe  test    ecx, ecx
0x180032bc0  jnz     short loc_180032BAF
0x180032bc2  test    edx, edx
0x180032bc4  jnz     short loc_180032BEB
0x180032bc6  mov     r8, [rbx+20h]; char *
0x180032bca  mov     rdx, [rbx+18h]; char *
0x180032bce  mov     [rsp+88h+var_58], r12; unsigned int *
0x180032bd3  mov     [rsp+88h+var_60], rsi; struct _PRINT_FEATURE_OPTION **
0x180032bd8  mov     [rsp+88h+var_68], r9; char *
0x180032bdd  mov     r9, [rbx+8]; char *
0x180032be1  mov     rcx, r15; struct CPrintCoreConfig *
0x180032be4  call    ?CreateConstraintsPair@@YAJPEAVCPrintCoreConfig@@PEBD111PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z; CreateConstraintsPair(CPrintCoreConfig *,char const *,char const *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)
0x180032be9  mov     edi, eax
0x180032beb  add     rbx, 28h ; '('
0x180032bef  test    edi, edi
0x180032bf1  jns     loc_1800329DD
0x180032bf7  mov     eax, edi
0x180032bf9  add     rsp, 48h
0x180032bfd  pop     r15
0x180032bff  pop     r14
0x180032c01  pop     r13
0x180032c03  pop     r12
0x180032c05  pop     rdi
0x180032c06  pop     rsi
0x180032c07  pop     rbp
0x180032c08  pop     rbx
0x180032c09  retn
```
