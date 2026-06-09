# CMetadataRDFReaderWriter::GetItemByPosition(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x1800022a8`
- end: `0x18000247d`
- name: `?GetItemByPosition@CMetadataRDFReaderWriter@@IEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `469`
- prototype: `int(CMetadataRDFReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800020e0`
- `0x1800021c0`

## callees

- `0x1800022a8`
- `0x180002484`
- `0x180002608`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002398`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000241a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002460`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002472`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002398`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000241a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002460`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002472`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::GetItemByPosition(
        CMetadataRDFReaderWriter *this,
        unsigned int a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4,
        PROPVARIANT *pvar)
{
  __int64 v5; // rax
  int v6; // ebx
  RDFItem *v10; // rsi
  int PropVariantValue; // eax
  int v13; // eax
  int v14; // eax
  unsigned __int16 *v15; // [rsp+40h] [rbp+8h] BYREF

  v5 = *((_QWORD *)this + 26);
  v6 = 0;
  v15 = 0;
  v10 = *(RDFItem **)(v5 + 8LL * a2);
  if ( a4 )
  {
    v13 = (*(__int64 (__fastcall **)(RDFItem *, unsigned __int16 **))(*(_QWORD *)v10 + 24LL))(v10, &v15);
    v6 = v13;
    if ( v13 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_28;
      goto LABEL_12;
    }
    v13 = PropVariantString(v15, a4);
    v6 = v13;
    if ( v13 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_28;
      goto LABEL_12;
    }
  }
  if ( !a3 )
    goto LABEL_3;
  v13 = (*(__int64 (__fastcall **)(RDFItem *, unsigned __int16 **))(*(_QWORD *)v10 + 48LL))(v10, &v15);
  v6 = v13;
  if ( v13 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_28;
LABEL_12:
    DoStackCapture(v13);
    goto LABEL_28;
  }
  if ( v15 )
  {
    v13 = PropVariantString(v15, a3);
    v6 = v13;
    if ( v13 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_28;
      goto LABEL_12;
    }
  }
  else
  {
    PropVariantClear((PROPVARIANT *)a3);
  }
LABEL_3:
  if ( !pvar )
    goto LABEL_8;
  if ( (*((_BYTE *)v10 + 8) & 4) == 0
    || (*((_BYTE *)v10 + 8) & 8) != 0
    || (v14 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, RDFItem *))(*(_QWORD *)this + 224LL))(this, v10),
        v6 = v14,
        v14 >= 0) )
  {
    PropVariantValue = RDFItem::GetPropVariantValue(v10, (struct tagPROPVARIANT *)pvar);
    v6 = PropVariantValue;
    if ( PropVariantValue < 0 && g_doStackCaptures )
      DoStackCapture(PropVariantValue);
LABEL_8:
    if ( v6 >= 0 )
      return (unsigned int)v6;
LABEL_28:
    if ( !pvar )
      goto LABEL_29;
    goto LABEL_17;
  }
  if ( g_doStackCaptures )
    DoStackCapture(v14);
LABEL_17:
  PropVariantClear(pvar);
LABEL_29:
  if ( a3 )
    PropVariantClear((PROPVARIANT *)a3);
  if ( a4 )
    PropVariantClear((PROPVARIANT *)a4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800022a8  mov     [rsp+arg_8], rbx
0x1800022ad  mov     [rsp+arg_10], rsi
0x1800022b2  push    rdi
0x1800022b3  push    r14
0x1800022b5  push    r15
0x1800022b7  sub     rsp, 20h
0x1800022bb  mov     rax, [rcx+0D0h]
0x1800022c2  xor     ebx, ebx
0x1800022c4  mov     edx, edx
0x1800022c6  mov     r14, r9
0x1800022c9  mov     [rsp+38h+arg_0], rbx
0x1800022ce  mov     rdi, r8
0x1800022d1  mov     r15, rcx
0x1800022d4  mov     rsi, [rax+rdx*8]
0x1800022d8  test    r9, r9
0x1800022db  jnz     short loc_180002332
0x1800022dd  test    rdi, rdi
0x1800022e0  jnz     loc_1800023E2
0x1800022e6  cmp     [rsp+38h+pvar], 0
0x1800022ec  jz      short loc_180002314
0x1800022ee  test    byte ptr [rsi+8], 4
0x1800022f2  jnz     short loc_180002365
0x1800022f4  mov     rdx, [rsp+38h+pvar]; struct tagPROPVARIANT *
0x1800022f9  mov     rcx, rsi; this
0x1800022fc  call    ?GetPropVariantValue@RDFItem@@QEAAJPEAUtagPROPVARIANT@@@Z; RDFItem::GetPropVariantValue(tagPROPVARIANT *)
0x180002301  mov     ebx, eax
0x180002303  test    eax, eax
0x180002305  jns     short loc_180002314
0x180002307  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000230e  jnz     loc_1800023A3
0x180002314  test    ebx, ebx
0x180002316  js      loc_18000244C
0x18000231c  mov     rsi, [rsp+38h+arg_10]
0x180002321  mov     eax, ebx
0x180002323  mov     rbx, [rsp+38h+arg_8]
0x180002328  add     rsp, 20h
0x18000232c  pop     r15
0x18000232e  pop     r14
0x180002330  pop     rdi
0x180002331  retn
0x180002332  mov     rax, [rsi]
0x180002335  lea     rdx, [rsp+38h+arg_0]
0x18000233a  mov     rcx, rsi
0x18000233d  mov     rax, [rax+18h]
0x180002341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002346  mov     ebx, eax
0x180002348  test    eax, eax
0x18000234a  jns     short loc_1800023AF
0x18000234c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002353  jz      loc_18000244C
0x180002359  mov     ecx, eax; int
0x18000235b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002360  jmp     loc_18000244C
0x180002365  test    byte ptr [rsi+8], 8
0x180002369  jnz     short loc_1800022F4
0x18000236b  mov     rax, [r15]
0x18000236e  mov     rdx, rsi
0x180002371  mov     rcx, r15
0x180002374  mov     rax, [rax+0E0h]
0x18000237b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002380  mov     ebx, eax
0x180002382  test    eax, eax
0x180002384  jns     loc_1800022F4
0x18000238a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002391  jnz     short loc_1800023D9
0x180002393  mov     rcx, [rsp+38h+pvar]; pvar
0x180002398  call    cs:__imp_PropVariantClear
0x18000239e  jmp     loc_180002458
0x1800023a3  mov     ecx, eax; int
0x1800023a5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800023aa  jmp     loc_180002314
0x1800023af  mov     rcx, [rsp+38h+arg_0]; unsigned __int16 *
0x1800023b4  mov     rdx, r14; struct tagPROPVARIANT *
0x1800023b7  call    ?PropVariantString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; PropVariantString(ushort const *,tagPROPVARIANT *)
0x1800023bc  mov     ebx, eax
0x1800023be  test    eax, eax
0x1800023c0  jns     loc_1800022DD
0x1800023c6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800023cd  jnz     short loc_180002359
0x1800023cf  test    eax, eax
0x1800023d1  jns     loc_1800022DD
0x1800023d7  jmp     short loc_18000244C
0x1800023d9  mov     ecx, eax; int
0x1800023db  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800023e0  jmp     short loc_180002393
0x1800023e2  mov     rax, [rsi]
0x1800023e5  lea     rdx, [rsp+38h+arg_0]
0x1800023ea  mov     rcx, rsi
0x1800023ed  mov     rax, [rax+30h]
0x1800023f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f6  mov     ebx, eax
0x1800023f8  test    eax, eax
0x1800023fa  jns     short loc_18000240D
0x1800023fc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002403  jnz     loc_180002359
0x180002409  test    eax, eax
0x18000240b  js      short loc_18000244C
0x18000240d  mov     rcx, [rsp+38h+arg_0]; unsigned __int16 *
0x180002412  test    rcx, rcx
0x180002415  jnz     short loc_180002425
0x180002417  mov     rcx, rdi; pvar
0x18000241a  call    cs:__imp_PropVariantClear
0x180002420  jmp     loc_1800022E6
0x180002425  mov     rdx, rdi; struct tagPROPVARIANT *
0x180002428  call    ?PropVariantString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; PropVariantString(ushort const *,tagPROPVARIANT *)
0x18000242d  mov     ebx, eax
0x18000242f  test    eax, eax
0x180002431  jns     loc_1800022E6
0x180002437  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000243e  jnz     loc_180002359
0x180002444  test    eax, eax
0x180002446  jns     loc_1800022E6
0x18000244c  cmp     [rsp+38h+pvar], 0
0x180002452  jnz     loc_180002393
0x180002458  test    rdi, rdi
0x18000245b  jz      short loc_180002466
0x18000245d  mov     rcx, rdi; pvar
0x180002460  call    cs:__imp_PropVariantClear
0x180002466  test    r14, r14
0x180002469  jz      loc_18000231C
0x18000246f  mov     rcx, r14; pvar
0x180002472  call    cs:__imp_PropVariantClear
0x180002478  jmp     loc_18000231C
```
