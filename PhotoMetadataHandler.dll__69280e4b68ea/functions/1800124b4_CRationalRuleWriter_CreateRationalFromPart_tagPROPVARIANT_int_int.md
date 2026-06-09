# CRationalRuleWriter::CreateRationalFromPart(tagPROPVARIANT *,int,int)

- ea: `0x1800124b4`
- end: `0x18001264b`
- name: `?CreateRationalFromPart@CRationalRuleWriter@@AEAAJPEAUtagPROPVARIANT@@HH@Z`
- size: `407`
- prototype: `int(CRationalRuleWriter *__hidden this, struct tagPROPVARIANT *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012f00`

## callees

- `0x180009140`
- `0x1800096f0`
- `0x18000f004`
- `0x1800124b4`
- `0x1800132dc`
- `0x1800141ec`
- `0x180014244`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800125ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800125fd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001260e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001261f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012630`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800125ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800125fd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001260e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001261f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012630`

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
0x1800124b4  push    rbp
0x1800124b6  push    rbx
0x1800124b7  push    rsi
0x1800124b8  push    rdi
0x1800124b9  lea     rbp, [rsp-3Fh]
0x1800124be  sub     rsp, 0B8h
0x1800124c5  mov     ebx, r9d
0x1800124c8  mov     esi, r8d
0x1800124cb  mov     rdi, rdx
0x1800124ce  mov     rdx, rcx
0x1800124d1  xorps   xmm0, xmm0
0x1800124d4  xor     eax, eax
0x1800124d6  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x1800124da  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x1800124de  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x1800124e2  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x1800124e6  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x1800124ea  mov     qword ptr [rbp+57h+var_40+10h], rax
0x1800124ee  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1800124f2  mov     qword ptr [rbp+57h+var_58+10h], rax
0x1800124f6  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800124fa  mov     qword ptr [rbp+57h+pvar+10h], rax
0x1800124fe  mov     rcx, [rcx+30h]
0x180012502  mov     rax, [rcx]
0x180012505  mov     r8, [rdx+8]
0x180012509  lea     r9, [rbp+57h+pvarSrc]
0x18001250d  mov     r8, [r8+10h]
0x180012511  mov     rdx, [rdx+28h]
0x180012515  mov     rax, [rax+20h]
0x180012519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001251e  test    eax, eax
0x180012520  js      short loc_1800125A0
0x180012522  test    ebx, ebx
0x180012524  jz      short loc_180012563
0x180012526  lea     rax, [rbp+57h+var_A0]
0x18001252a  mov     [rsp+0D0h+var_B0], rax; PROPVARIANT *
0x18001252f  lea     r9, [rbp+57h+pvar]; PROPVARIANT *
0x180012533  lea     r8, [rbp+57h+var_58]; PROPVARIANT *
0x180012537  lea     rdx, [rbp+57h+var_40]; pvar
0x18001253b  lea     rcx, [rbp+57h+pvarSrc]; pvarSrc
0x18001253f  call    ?ConvertGPSCoordinateTextToVector@@YAJPEBUtagPROPVARIANT@@PEAU1@111@Z; ConvertGPSCoordinateTextToVector(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180012544  mov     ebx, eax
0x180012546  test    eax, eax
0x180012548  jns     short loc_1800125AE
0x18001254a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012551  jz      loc_1800125E8
0x180012557  mov     ecx, eax; int
0x180012559  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001255e  jmp     loc_1800125E8
0x180012563  cmp     word ptr [rdi], 14h
0x180012567  ja      short loc_18001257A
0x180012569  movzx   eax, word ptr [rdi]
0x18001256c  mov     ecx, 11000Ch
0x180012571  bt      ecx, eax
0x180012574  jnb     short loc_18001257A
0x180012576  mov     al, 1
0x180012578  jmp     short loc_18001257C
0x18001257a  xor     al, al
0x18001257c  mov     [rsp+0D0h+var_A8], al; bool
0x180012580  lea     rax, [rbp+57h+var_A0]
0x180012584  mov     [rsp+0D0h+var_B0], rax; struct tagPROPVARIANT *
0x180012589  lea     r9, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18001258d  lea     r8, [rbp+57h+var_58]; struct tagPROPVARIANT *
0x180012591  lea     rdx, [rbp+57h+var_40]; struct tagPROPVARIANT *
0x180012595  lea     rcx, [rbp+57h+pvarSrc]; struct tagPROPVARIANT *
0x180012599  call    ?ConvertRationalText@@YAJPEBUtagPROPVARIANT@@PEAU1@111_N@Z; ConvertRationalText(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,bool)
0x18001259e  jmp     short loc_180012544
0x1800125a0  mov     rdx, rdi; struct tagPROPVARIANT *
0x1800125a3  lea     rcx, [rbp+57h+var_A0]; struct tagPROPVARIANT *
0x1800125a7  call    ?CreateDefaultProxyVariant@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; CreateDefaultProxyVariant(tagPROPVARIANT *,tagPROPVARIANT const *)
0x1800125ac  jmp     short loc_180012544
0x1800125ae  xor     r8d, r8d
0x1800125b1  test    esi, esi
0x1800125b3  cmovz   r8, rdi; struct tagPROPVARIANT *
0x1800125b7  neg     esi
0x1800125b9  sbb     rdx, rdx
0x1800125bc  and     rdx, rdi; struct tagPROPVARIANT *
0x1800125bf  lea     rcx, [rbp+57h+var_A0]; struct tagPROPVARIANT *
0x1800125c3  call    ?UpdateRationalPropvar@@YAJPEAUtagPROPVARIANT@@PEBU1@1@Z; UpdateRationalPropvar(tagPROPVARIANT *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x1800125c8  mov     ebx, eax
0x1800125ca  test    eax, eax
0x1800125cc  jns     short loc_1800125DB
0x1800125ce  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800125d5  jnz     short loc_180012557
0x1800125d7  test    eax, eax
0x1800125d9  js      short loc_1800125E8
0x1800125db  lea     rdx, [rbp+57h+var_A0]; struct tagPROPVARIANT *
0x1800125df  mov     rcx, rdi; struct tagPROPVARIANT *
0x1800125e2  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x1800125e7  nop
0x1800125e8  lea     rcx, [rbp+57h+pvar]; pvar
0x1800125ec  call    cs:__imp_PropVariantClear
0x1800125f3  nop     dword ptr [rax+rax+00h]
0x1800125f8  nop
0x1800125f9  lea     rcx, [rbp+57h+var_58]; pvar
0x1800125fd  call    cs:__imp_PropVariantClear
0x180012604  nop     dword ptr [rax+rax+00h]
0x180012609  nop
0x18001260a  lea     rcx, [rbp+57h+var_40]; pvar
0x18001260e  call    cs:__imp_PropVariantClear
0x180012615  nop     dword ptr [rax+rax+00h]
0x18001261a  nop
0x18001261b  lea     rcx, [rbp+57h+var_A0]; pvar
0x18001261f  call    cs:__imp_PropVariantClear
0x180012626  nop     dword ptr [rax+rax+00h]
0x18001262b  nop
0x18001262c  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180012630  call    cs:__imp_PropVariantClear
0x180012637  nop     dword ptr [rax+rax+00h]
0x18001263c  mov     eax, ebx
0x18001263e  add     rsp, 0B8h
0x180012645  pop     rdi
0x180012646  pop     rsi
0x180012647  pop     rbx
0x180012648  pop     rbp
0x180012649  retn
```
