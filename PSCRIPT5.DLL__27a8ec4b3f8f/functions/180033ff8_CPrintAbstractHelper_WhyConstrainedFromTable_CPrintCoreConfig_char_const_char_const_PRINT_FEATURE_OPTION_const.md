# CPrintAbstractHelper::WhyConstrainedFromTable(CPrintCoreConfig *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)

- ea: `0x180033ff8`
- end: `0x18003426b`
- name: `?WhyConstrainedFromTable@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBD1PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z`
- size: `627`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *this, struct CPrintCoreConfig *, const char *, const char *, struct _PRINT_FEATURE_OPTION **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180034280`

## callees

- `0x180032650`
- `0x180033ff8`
- `0x18005f010`

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
0x180033ff8  push    rbx
0x180033ffa  push    rbp
0x180033ffb  push    rsi
0x180033ffc  push    rdi
0x180033ffd  push    r12
0x180033fff  push    r13
0x180034001  push    r14
0x180034003  push    r15
0x180034005  sub     rsp, 48h
0x180034009  mov     rax, [rcx]
0x18003400c  xor     edi, edi
0x18003400e  mov     rbp, r9
0x180034011  mov     r13, r8
0x180034014  mov     r15, rdx
0x180034017  mov     r14, rcx
0x18003401a  mov     rax, [rax+78h]
0x18003401e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034023  mov     rsi, [rsp+88h+arg_20]
0x18003402b  mov     rbx, rax
0x18003402e  mov     r12, [rsp+88h+arg_28]
0x180034036  mov     [rsi], rdi
0x180034039  mov     [r12], edi
0x18003403d  cmp     dword ptr [rbx], 2
0x180034040  jz      loc_180034257
0x180034046  cmp     qword ptr [rsi], 0
0x18003404a  jnz     loc_180034257
0x180034050  mov     rax, [rbx+8]
0x180034054  mov     r8, r13
0x180034057  sub     r8, rax
0x18003405a  mov     [rsp+88h+arg_20], 0
0x180034066  movzx   edx, byte ptr [rax]
0x180034069  movzx   ecx, byte ptr [rax+r8]
0x18003406e  sub     edx, ecx
0x180034070  jnz     short loc_180034079
0x180034072  inc     rax
0x180034075  test    ecx, ecx
0x180034077  jnz     short loc_180034066
0x180034079  test    edx, edx
0x18003407b  jnz     loc_18003415C
0x180034081  mov     rax, [rbx+10h]
0x180034085  mov     r8, rbp
0x180034088  sub     r8, rax
0x18003408b  movzx   edx, byte ptr [rax]
0x18003408e  movzx   ecx, byte ptr [rax+r8]
0x180034093  sub     edx, ecx
0x180034095  jnz     short loc_18003409E
0x180034097  inc     rax
0x18003409a  test    ecx, ecx
0x18003409c  jnz     short loc_18003408B
0x18003409e  test    edx, edx
0x1800340a0  jnz     loc_18003415C
0x1800340a6  mov     rax, [r14]
0x1800340a9  lea     r9, [rsp+88h+arg_20]
0x1800340b1  mov     rdx, [rbx+18h]
0x1800340b5  mov     r8, r15
0x1800340b8  mov     rcx, r14
0x1800340bb  mov     rax, [rax+58h]
0x1800340bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800340c4  mov     edi, eax
0x1800340c6  test    eax, eax
0x1800340c8  js      loc_18003424B
0x1800340ce  mov     r9, [rsp+88h+arg_20]
0x1800340d6  test    r9, r9
0x1800340d9  jz      loc_18003424B
0x1800340df  cmp     dword ptr [rbx], 0
0x1800340e2  jnz     short loc_18003410E
0x1800340e4  mov     rcx, [rbx+20h]
0x1800340e8  mov     r8, r9
0x1800340eb  sub     r8, rcx
0x1800340ee  movzx   edx, byte ptr [rcx]
0x1800340f1  movzx   eax, byte ptr [rcx+r8]
0x1800340f6  sub     edx, eax
0x1800340f8  jnz     short loc_180034101
0x1800340fa  inc     rcx
0x1800340fd  test    eax, eax
0x1800340ff  jnz     short loc_1800340EE
0x180034101  test    edx, edx
0x180034103  jnz     short loc_18003413C
0x180034105  add     rbx, 28h ; '('
0x180034109  jmp     loc_18003403D
0x18003410e  cmp     dword ptr [rbx], 1
0x180034111  jnz     loc_18003424B
0x180034117  mov     rax, [rbx+20h]
0x18003411b  mov     r8, r9
0x18003411e  sub     r8, rax
0x180034121  movzx   edx, byte ptr [rax]
0x180034124  movzx   ecx, byte ptr [rax+r8]
0x180034129  sub     edx, ecx
0x18003412b  jnz     short loc_180034134
0x18003412d  inc     rax
0x180034130  test    ecx, ecx
0x180034132  jnz     short loc_180034121
0x180034134  test    edx, edx
0x180034136  jnz     loc_18003424B
0x18003413c  mov     r8, [rbx+10h]
0x180034140  mov     rdx, [rbx+8]
0x180034144  mov     [rsp+88h+var_58], r12
0x180034149  mov     [rsp+88h+var_60], rsi
0x18003414e  mov     [rsp+88h+var_68], r9
0x180034153  mov     r9, [rbx+18h]
0x180034157  jmp     loc_180034241
0x18003415c  mov     rax, [rbx+18h]
0x180034160  mov     r8, r13
0x180034163  sub     r8, rax
0x180034166  movzx   edx, byte ptr [rax]
0x180034169  movzx   ecx, byte ptr [rax+r8]
0x18003416e  sub     edx, ecx
0x180034170  jnz     short loc_180034179
0x180034172  inc     rax
0x180034175  test    ecx, ecx
0x180034177  jnz     short loc_180034166
0x180034179  test    edx, edx
0x18003417b  jnz     loc_18003424B
0x180034181  cmp     dword ptr [rbx], 1
0x180034184  jnz     short loc_1800341AD
0x180034186  mov     rax, [rbx+20h]
0x18003418a  mov     r8, rbp
0x18003418d  sub     r8, rax
0x180034190  movzx   edx, byte ptr [rax]
0x180034193  movzx   ecx, byte ptr [rax+r8]
0x180034198  sub     edx, ecx
0x18003419a  jnz     short loc_1800341A3
0x18003419c  inc     rax
0x18003419f  test    ecx, ecx
0x1800341a1  jnz     short loc_180034190
0x1800341a3  test    edx, edx
0x1800341a5  jnz     loc_18003424B
0x1800341ab  jmp     short loc_1800341D9
0x1800341ad  cmp     dword ptr [rbx], 0
0x1800341b0  jnz     loc_18003424B
0x1800341b6  mov     rax, [rbx+20h]
0x1800341ba  mov     rdx, rbp
0x1800341bd  sub     rdx, rax
0x1800341c0  movzx   r8d, byte ptr [rax]
0x1800341c4  movzx   ecx, byte ptr [rax+rdx]
0x1800341c8  sub     r8d, ecx
0x1800341cb  jnz     short loc_1800341D4
0x1800341cd  inc     rax
0x1800341d0  test    ecx, ecx
0x1800341d2  jnz     short loc_1800341C0
0x1800341d4  test    r8d, r8d
0x1800341d7  jz      short loc_18003424B
0x1800341d9  mov     rax, [r14]
0x1800341dc  lea     r9, [rsp+88h+arg_20]
0x1800341e4  mov     rdx, [rbx+8]
0x1800341e8  mov     r8, r15
0x1800341eb  mov     rcx, r14
0x1800341ee  mov     rax, [rax+58h]
0x1800341f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341f7  mov     edi, eax
0x1800341f9  test    eax, eax
0x1800341fb  js      short loc_18003424B
0x1800341fd  mov     r9, [rsp+88h+arg_20]
0x180034205  mov     rax, [rbx+10h]
0x180034209  mov     r8, r9
0x18003420c  sub     r8, rax
0x18003420f  movzx   edx, byte ptr [rax]
0x180034212  movzx   ecx, byte ptr [rax+r8]
0x180034217  sub     edx, ecx
0x180034219  jnz     short loc_180034222
0x18003421b  inc     rax
0x18003421e  test    ecx, ecx
0x180034220  jnz     short loc_18003420F
0x180034222  test    edx, edx
0x180034224  jnz     short loc_18003424B
0x180034226  mov     r8, [rbx+20h]; char *
0x18003422a  mov     rdx, [rbx+18h]; char *
0x18003422e  mov     [rsp+88h+var_58], r12; unsigned int *
0x180034233  mov     [rsp+88h+var_60], rsi; struct _PRINT_FEATURE_OPTION **
0x180034238  mov     [rsp+88h+var_68], r9; char *
0x18003423d  mov     r9, [rbx+8]; char *
0x180034241  mov     rcx, r15; struct CPrintCoreConfig *
0x180034244  call    ?CreateConstraintsPair@@YAJPEAVCPrintCoreConfig@@PEBD111PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z; CreateConstraintsPair(CPrintCoreConfig *,char const *,char const *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)
0x180034249  mov     edi, eax
0x18003424b  add     rbx, 28h ; '('
0x18003424f  test    edi, edi
0x180034251  jns     loc_18003403D
0x180034257  mov     eax, edi
0x180034259  add     rsp, 48h
0x18003425d  pop     r15
0x18003425f  pop     r14
0x180034261  pop     r13
0x180034263  pop     r12
0x180034265  pop     rdi
0x180034266  pop     rsi
0x180034267  pop     rbp
0x180034268  pop     rbx
0x180034269  retn
```
