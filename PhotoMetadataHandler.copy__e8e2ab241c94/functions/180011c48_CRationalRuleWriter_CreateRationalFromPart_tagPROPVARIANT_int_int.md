# CRationalRuleWriter::CreateRationalFromPart(tagPROPVARIANT *,int,int)

- ea: `0x180011c48`
- end: `0x180011dc0`
- name: `?CreateRationalFromPart@CRationalRuleWriter@@AEAAJPEAUtagPROPVARIANT@@HH@Z`
- size: `376`
- prototype: `int(CRationalRuleWriter *__hidden this, struct tagPROPVARIANT *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012620`

## callees

- `0x180008de0`
- `0x180009010`
- `0x18000e90c`
- `0x180011c48`
- `0x1800129d8`
- `0x18001384c`
- `0x1800138a0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011d80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011d8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011d96`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011da1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011dac`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011d80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011d8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011d96`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011da1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011dac`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRationalRuleWriter::CreateRationalFromPart(
        CRationalRuleWriter *this,
        struct tagPROPVARIANT *a2,
        int a3,
        int a4)
{
  int updated; // eax
  unsigned int v8; // ebx
  int v9; // ecx
  bool v10; // al
  const struct tagPROPVARIANT *v11; // r8
  PROPVARIANT v13; // [rsp+30h] [rbp-49h] BYREF
  PROPVARIANT pvarSrc; // [rsp+48h] [rbp-31h] BYREF
  PROPVARIANT pvar; // [rsp+60h] [rbp-19h] BYREF
  PROPVARIANT v16; // [rsp+78h] [rbp-1h] BYREF
  PROPVARIANT v17; // [rsp+90h] [rbp+17h] BYREF

  memset(&pvarSrc, 0, sizeof(pvarSrc));
  memset(&v13, 0, sizeof(v13));
  memset(&v17, 0, sizeof(v17));
  memset(&v16, 0, sizeof(v16));
  memset(&pvar, 0, sizeof(pvar));
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, PROPVARIANT *))(**((_QWORD **)this + 6) + 32LL))(
         *((_QWORD *)this + 6),
         *((_QWORD *)this + 5),
         *(_QWORD *)(*((_QWORD *)this + 1) + 16LL),
         &pvarSrc) < 0 )
  {
    updated = CreateDefaultProxyVariant(&v13, a2);
  }
  else if ( a4 )
  {
    updated = ConvertGPSCoordinateTextToVector(&pvarSrc, &v17, &v16, &pvar, &v13);
  }
  else
  {
    v10 = 0;
    if ( a2->vt <= 0x14u )
    {
      v9 = 1114124;
      if ( _bittest(&v9, a2->vt) )
        v10 = 1;
    }
    updated = ConvertRationalText(&pvarSrc, &v17, &v16, &pvar, &v13, v10);
  }
  v8 = updated;
  if ( updated >= 0 )
  {
    v11 = 0;
    if ( !a3 )
      v11 = a2;
    updated = UpdateRationalPropvar(
                &v13,
                (const struct tagPROPVARIANT *)((unsigned __int64)a2 & -(__int64)(a3 != 0)),
                v11);
    v8 = updated;
    if ( updated >= 0 )
    {
      TransferPropVariant(a2, &v13);
      goto LABEL_19;
    }
    if ( !g_doStackCaptures )
      goto LABEL_19;
    goto LABEL_6;
  }
  if ( g_doStackCaptures )
LABEL_6:
    DoStackCapture(updated);
LABEL_19:
  PropVariantClear(&pvar);
  PropVariantClear(&v16);
  PropVariantClear(&v17);
  PropVariantClear(&v13);
  PropVariantClear(&pvarSrc);
  return v8;
}

```

## disassembly

```asm
0x180011c48  push    rbp
0x180011c4a  push    rbx
0x180011c4b  push    rsi
0x180011c4c  push    rdi
0x180011c4d  lea     rbp, [rsp-3Fh]
0x180011c52  sub     rsp, 0B8h
0x180011c59  mov     ebx, r9d
0x180011c5c  mov     esi, r8d
0x180011c5f  mov     rdi, rdx
0x180011c62  mov     rdx, rcx
0x180011c65  xorps   xmm0, xmm0
0x180011c68  xor     eax, eax
0x180011c6a  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x180011c6e  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x180011c72  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x180011c76  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x180011c7a  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180011c7e  mov     qword ptr [rbp+57h+var_40+10h], rax
0x180011c82  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180011c86  mov     qword ptr [rbp+57h+var_58+10h], rax
0x180011c8a  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180011c8e  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180011c92  mov     rcx, [rcx+30h]
0x180011c96  mov     rax, [rcx]
0x180011c99  mov     r8, [rdx+8]
0x180011c9d  lea     r9, [rbp+57h+pvarSrc]
0x180011ca1  mov     r8, [r8+10h]
0x180011ca5  mov     rdx, [rdx+28h]
0x180011ca9  mov     rax, [rax+20h]
0x180011cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb2  test    eax, eax
0x180011cb4  js      short loc_180011D34
0x180011cb6  test    ebx, ebx
0x180011cb8  jz      short loc_180011CF7
0x180011cba  lea     rax, [rbp+57h+var_A0]
0x180011cbe  mov     [rsp+0D0h+var_B0], rax; PROPVARIANT *
0x180011cc3  lea     r9, [rbp+57h+pvar]; PROPVARIANT *
0x180011cc7  lea     r8, [rbp+57h+var_58]; PROPVARIANT *
0x180011ccb  lea     rdx, [rbp+57h+var_40]; pvar
0x180011ccf  lea     rcx, [rbp+57h+pvarSrc]; pvarSrc
0x180011cd3  call    ?ConvertGPSCoordinateTextToVector@@YAJPEBUtagPROPVARIANT@@PEAU1@111@Z; ConvertGPSCoordinateTextToVector(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180011cd8  mov     ebx, eax
0x180011cda  test    eax, eax
0x180011cdc  jns     short loc_180011D42
0x180011cde  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011ce5  jz      loc_180011D7C
0x180011ceb  mov     ecx, eax; int
0x180011ced  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011cf2  jmp     loc_180011D7C
0x180011cf7  cmp     word ptr [rdi], 14h
0x180011cfb  ja      short loc_180011D0E
0x180011cfd  movzx   eax, word ptr [rdi]
0x180011d00  mov     ecx, 11000Ch
0x180011d05  bt      ecx, eax
0x180011d08  jnb     short loc_180011D0E
0x180011d0a  mov     al, 1
0x180011d0c  jmp     short loc_180011D10
0x180011d0e  xor     al, al
0x180011d10  mov     [rsp+0D0h+var_A8], al; bool
0x180011d14  lea     rax, [rbp+57h+var_A0]
0x180011d18  mov     [rsp+0D0h+var_B0], rax; struct tagPROPVARIANT *
0x180011d1d  lea     r9, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180011d21  lea     r8, [rbp+57h+var_58]; struct tagPROPVARIANT *
0x180011d25  lea     rdx, [rbp+57h+var_40]; struct tagPROPVARIANT *
0x180011d29  lea     rcx, [rbp+57h+pvarSrc]; struct tagPROPVARIANT *
0x180011d2d  call    ?ConvertRationalText@@YAJPEBUtagPROPVARIANT@@PEAU1@111_N@Z; ConvertRationalText(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,bool)
0x180011d32  jmp     short loc_180011CD8
0x180011d34  mov     rdx, rdi; struct tagPROPVARIANT *
0x180011d37  lea     rcx, [rbp+57h+var_A0]; struct tagPROPVARIANT *
0x180011d3b  call    ?CreateDefaultProxyVariant@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; CreateDefaultProxyVariant(tagPROPVARIANT *,tagPROPVARIANT const *)
0x180011d40  jmp     short loc_180011CD8
0x180011d42  xor     r8d, r8d
0x180011d45  test    esi, esi
0x180011d47  cmovz   r8, rdi; struct tagPROPVARIANT *
0x180011d4b  neg     esi
0x180011d4d  sbb     rdx, rdx
0x180011d50  and     rdx, rdi; struct tagPROPVARIANT *
0x180011d53  lea     rcx, [rbp+57h+var_A0]; struct tagPROPVARIANT *
0x180011d57  call    ?UpdateRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z; UpdateRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x180011d5c  mov     ebx, eax
0x180011d5e  test    eax, eax
0x180011d60  jns     short loc_180011D6F
0x180011d62  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011d69  jnz     short loc_180011CEB
0x180011d6b  test    eax, eax
0x180011d6d  js      short loc_180011D7C
0x180011d6f  lea     rdx, [rbp+57h+var_A0]; struct tagPROPVARIANT *
0x180011d73  mov     rcx, rdi; struct tagPROPVARIANT *
0x180011d76  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x180011d7b  nop
0x180011d7c  lea     rcx, [rbp+57h+pvar]; pvar
0x180011d80  call    cs:__imp_PropVariantClear
0x180011d86  nop
0x180011d87  lea     rcx, [rbp+57h+var_58]; pvar
0x180011d8b  call    cs:__imp_PropVariantClear
0x180011d91  nop
0x180011d92  lea     rcx, [rbp+57h+var_40]; pvar
0x180011d96  call    cs:__imp_PropVariantClear
0x180011d9c  nop
0x180011d9d  lea     rcx, [rbp+57h+var_A0]; pvar
0x180011da1  call    cs:__imp_PropVariantClear
0x180011da7  nop
0x180011da8  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180011dac  call    cs:__imp_PropVariantClear
0x180011db2  mov     eax, ebx
0x180011db4  add     rsp, 0B8h
0x180011dbb  pop     rdi
0x180011dbc  pop     rsi
0x180011dbd  pop     rbx
0x180011dbe  pop     rbp
0x180011dbf  retn
```
