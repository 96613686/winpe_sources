# CRationalRuleWriter::WriteRulePath(RULE_PATH_INFO const *,tagPROPVARIANT const *)

- ea: `0x180012620`
- end: `0x1800129cf`
- name: `?WriteRulePath@CRationalRuleWriter@@MEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@@Z`
- size: `943`
- prototype: `__int64 __fastcall(CRationalRuleWriter *__hidden this, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800084a0`
- `0x180008984`
- `0x18000e90c`
- `0x180011c48`
- `0x180011f44`
- `0x180012620`
- `0x1800129d8`
- `0x180013470`
- `0x1800139ec`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012652`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012652`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012714`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001273f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800127e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012888`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800129b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012714`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001273f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800127e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012888`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800129b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRationalRuleWriter::WriteRulePath(
        const struct _tagpropertykey ***this,
        const struct RULE_PATH_INFO *a2,
        const struct tagPROPVARIANT *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int v8; // esi
  int updated; // eax
  PROPVARIANT *p_pvar; // rcx
  PROPVARIANT *v11; // rcx
  HRESULT v12; // eax
  int v13; // r9d
  int v14; // r8d
  PROPVARIANT pvarDest; // [rsp+30h] [rbp-50h] BYREF
  PROPVARIANT v17; // [rsp+48h] [rbp-38h] BYREF
  PROPVARIANT pvar; // [rsp+60h] [rbp-20h] BYREF

  memset(&pvarDest, 0, sizeof(pvarDest));
  v6 = PropVariantCopy(&pvarDest, a3);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_69;
    goto LABEL_68;
  }
  v8 = 1;
  switch ( *((_DWORD *)this[4] + 6) )
  {
    case 2:
      v13 = 0;
      goto LABEL_48;
    case 3:
      v13 = 0;
      goto LABEL_44;
    case 5:
      v13 = 1;
LABEL_48:
      v14 = 1;
LABEL_49:
      v6 = CRationalRuleWriter::CreateRationalFromPart((CRationalRuleWriter *)this, &pvarDest, v14, v13);
      v7 = v6;
      if ( v6 < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_69;
        goto LABEL_68;
      }
      goto LABEL_52;
    case 6:
      v13 = 1;
LABEL_44:
      v14 = 0;
      goto LABEL_49;
  }
  if ( *((_DWORD *)this[4] + 6) != 8 )
  {
    if ( *((_DWORD *)this[4] + 6) != 9 )
      goto LABEL_52;
    memset(&pvar, 0, sizeof(pvar));
    updated = (*(__int64 (__fastcall **)(const struct _tagpropertykey **, const struct _tagpropertykey **, const struct _tagpropertykey *, PROPVARIANT *))&(*this[6])[1].fmtid.Data4[4])(
                this[6],
                this[5],
                this[1][2],
                &pvar);
    v7 = updated;
    if ( updated < 0 )
    {
      if ( updated != -2003292352 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_14;
        goto LABEL_13;
      }
      v7 = 0;
      v8 = 0;
    }
    else
    {
      updated = UpdateGPSRefValue(&pvar, a3);
      v7 = updated;
      if ( updated < 0 )
      {
        if ( !g_doStackCaptures )
        {
LABEL_14:
          p_pvar = &pvar;
LABEL_15:
          PropVariantClear(p_pvar);
          goto LABEL_69;
        }
LABEL_13:
        DoStackCapture(updated);
        goto LABEL_14;
      }
      TransferPropVariant(&pvarDest, &pvar);
    }
    v11 = &pvar;
    goto LABEL_20;
  }
  if ( (unsigned __int16)(a3->vt - 4116) <= 1u && a3->lVal == 3 )
  {
    memset(&v17, 0, sizeof(v17));
    memset(&pvar, 0, sizeof(pvar));
    v12 = (*(__int64 (__fastcall **)(const struct _tagpropertykey **, const struct _tagpropertykey **, const struct _tagpropertykey *, PROPVARIANT *))&(*this[6])[1].fmtid.Data4[4])(
            this[6],
            this[5],
            this[1][1],
            &v17);
    v7 = v12;
    if ( v12 < 0 )
    {
      if ( v12 != -2003292352 )
      {
LABEL_32:
        if ( !g_doStackCaptures )
          goto LABEL_29;
        goto LABEL_28;
      }
      v12 = ConstructGPSCoordProxyWithRef(*this[4], &pvar, &pvarDest, &v17);
      v7 = v12;
      if ( v12 < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_29;
        goto LABEL_28;
      }
      TransferPropVariant(&pvarDest, &v17);
    }
    else
    {
      v12 = ExtractRefFromGPSCoord(&pvar, &v17);
      v7 = v12;
      if ( v12 < 0 )
      {
        if ( !g_doStackCaptures )
        {
LABEL_29:
          PropVariantClear(&pvar);
          p_pvar = &v17;
          goto LABEL_15;
        }
LABEL_28:
        DoStackCapture(v12);
        goto LABEL_29;
      }
      if ( pvar.vt )
      {
        v12 = SniffAndConvertToWideString(&pvar, &v17);
        v7 = v12;
        if ( v12 < 0 )
          goto LABEL_32;
        v12 = UpdateGPSRefValue(&pvarDest, &v17);
        v7 = v12;
        if ( v12 < 0 )
        {
          if ( !g_doStackCaptures )
            goto LABEL_29;
          goto LABEL_28;
        }
      }
    }
    PropVariantClear(&pvar);
    v11 = &v17;
LABEL_20:
    PropVariantClear(v11);
  }
LABEL_52:
  if ( *((_QWORD *)a2 + 4) )
  {
    memset(&pvar, 0, sizeof(pvar));
    updated = ExtractRefFromGPSCoord(&pvar, &pvarDest);
    v7 = updated;
    if ( updated >= 0 )
    {
      if ( pvar.vt
        && (updated = (*(__int64 (__fastcall **)(const struct _tagpropertykey **, _QWORD, PROPVARIANT *))&(*this[5])[2].pid)(
                        this[5],
                        *((_QWORD *)a2 + 4),
                        &pvar),
            v7 = updated,
            updated < 0) )
      {
        if ( !g_doStackCaptures )
          goto LABEL_14;
      }
      else
      {
        if ( !v8 )
          goto LABEL_14;
        updated = ((__int64 (__fastcall *)(const struct _tagpropertykey ***, _QWORD, _QWORD, _QWORD, PROPVARIANT *))(*this)[8])(
                    this,
                    *((_QWORD *)a2 + 3),
                    *((unsigned int *)a2 + 2),
                    *((unsigned int *)a2 + 3),
                    &pvarDest);
        v7 = updated;
        if ( updated >= 0 || !g_doStackCaptures )
          goto LABEL_14;
      }
    }
    else if ( !g_doStackCaptures )
    {
      goto LABEL_14;
    }
    goto LABEL_13;
  }
  if ( v8 )
  {
    v6 = CRuleWriter::WriteRulePath((CRuleWriter *)this, a2, &pvarDest);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_doStackCaptures )
LABEL_68:
        DoStackCapture(v6);
    }
  }
LABEL_69:
  PropVariantClear(&pvarDest);
  return v7;
}

```

## disassembly

```asm
0x180012620  push    rbp
0x180012622  push    rbx
0x180012623  push    rsi
0x180012624  push    rdi
0x180012625  push    r12
0x180012627  push    r14
0x180012629  push    r15
0x18001262b  mov     rbp, rsp
0x18001262e  sub     rsp, 80h
0x180012635  mov     r14, r8
0x180012638  mov     r15, rdx
0x18001263b  mov     rdi, rcx
0x18001263e  xorps   xmm0, xmm0
0x180012641  xor     eax, eax
0x180012643  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180012647  mov     qword ptr [rbp+pvarDest+10h], rax
0x18001264b  mov     rdx, r8; pvarSrc
0x18001264e  lea     rcx, [rbp+pvarDest]; pvarDest
0x180012652  call    cs:__imp_PropVariantCopy
0x180012658  mov     ebx, eax
0x18001265a  xor     r12d, r12d
0x18001265d  test    eax, eax
0x18001265f  jns     short loc_180012676
0x180012661  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012668  jnz     loc_1800129A9
0x18001266e  test    eax, eax
0x180012670  js      loc_1800129B1
0x180012676  mov     esi, 1
0x18001267b  mov     rcx, [rdi+20h]
0x18001267f  mov     edx, [rcx+18h]
0x180012682  sub     edx, 2
0x180012685  jz      loc_1800128AA
0x18001268b  sub     edx, esi
0x18001268d  jz      loc_1800128A5
0x180012693  sub     edx, 2
0x180012696  jz      loc_1800128A0
0x18001269c  sub     edx, esi
0x18001269e  jz      loc_180012898
0x1800126a4  sub     edx, 2
0x1800126a7  jz      loc_180012755
0x1800126ad  cmp     edx, esi
0x1800126af  jnz     loc_1800128D7
0x1800126b5  xorps   xmm0, xmm0
0x1800126b8  xor     eax, eax
0x1800126ba  movups  xmmword ptr [rbp+pvar], xmm0
0x1800126be  mov     qword ptr [rbp+pvar+10h], rax
0x1800126c2  mov     rcx, [rdi+30h]
0x1800126c6  mov     rax, [rcx]
0x1800126c9  mov     r8, [rdi+8]
0x1800126cd  lea     r9, [rbp+pvar]
0x1800126d1  mov     r8, [r8+10h]
0x1800126d5  mov     rdx, [rdi+28h]
0x1800126d9  mov     rax, [rax+20h]
0x1800126dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126e2  mov     ebx, eax
0x1800126e4  test    eax, eax
0x1800126e6  js      short loc_18001272E
0x1800126e8  mov     rdx, r14; struct tagPROPVARIANT *
0x1800126eb  lea     rcx, [rbp+pvar]; struct tagPROPVARIANT *
0x1800126ef  call    ?UpdateGPSRefValue@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; UpdateGPSRefValue(tagPROPVARIANT *,tagPROPVARIANT const *)
0x1800126f4  mov     ebx, eax
0x1800126f6  test    eax, eax
0x1800126f8  jns     short loc_18001271F
0x1800126fa  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012701  jz      short loc_18001270C
0x180012703  mov     ecx, eax; int
0x180012705  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001270a  jmp     short loc_180012710
0x18001270c  test    eax, eax
0x18001270e  jns     short loc_18001271F
0x180012710  lea     rcx, [rbp+pvar]; pvar
0x180012714  call    cs:__imp_PropVariantClear
0x18001271a  jmp     loc_1800129B1
0x18001271f  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x180012723  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180012727  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x18001272c  jmp     short loc_18001273B
0x18001272e  cmp     eax, 88982F40h
0x180012733  jnz     short loc_18001274A
0x180012735  mov     ebx, r12d
0x180012738  mov     esi, r12d
0x18001273b  lea     rcx, [rbp+pvar]; pvar
0x18001273f  call    cs:__imp_PropVariantClear
0x180012745  jmp     loc_1800128D7
0x18001274a  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012751  jz      short loc_180012710
0x180012753  jmp     short loc_180012703
0x180012755  mov     ecx, 1014h
0x18001275a  movzx   eax, word ptr [r14]
0x18001275e  sub     ax, cx
0x180012761  cmp     ax, si
0x180012764  ja      loc_1800128D7
0x18001276a  cmp     dword ptr [r14+8], 3
0x18001276f  jnz     loc_1800128D7
0x180012775  xorps   xmm0, xmm0
0x180012778  xor     eax, eax
0x18001277a  movups  xmmword ptr [rbp+var_38], xmm0
0x18001277e  mov     qword ptr [rbp+var_38+10h], rax
0x180012782  movups  xmmword ptr [rbp+pvar], xmm0
0x180012786  mov     qword ptr [rbp+pvar+10h], rax
0x18001278a  mov     rcx, [rdi+30h]
0x18001278e  mov     rax, [rcx]
0x180012791  mov     r8, [rdi+8]
0x180012795  lea     r9, [rbp+var_38]
0x180012799  mov     r8, [r8+8]
0x18001279d  mov     rdx, [rdi+28h]
0x1800127a1  mov     rax, [rax+20h]
0x1800127a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127aa  mov     ebx, eax
0x1800127ac  test    eax, eax
0x1800127ae  js      loc_18001283C
0x1800127b4  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x1800127b8  lea     rcx, [rbp+pvar]; pvar
0x1800127bc  call    ?ExtractRefFromGPSCoord@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; ExtractRefFromGPSCoord(tagPROPVARIANT *,tagPROPVARIANT const *)
0x1800127c1  mov     ebx, eax
0x1800127c3  test    eax, eax
0x1800127c5  jns     short loc_1800127F1
0x1800127c7  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800127ce  jz      short loc_1800127D9
0x1800127d0  mov     ecx, eax; int
0x1800127d2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800127d7  jmp     short loc_1800127DD
0x1800127d9  test    eax, eax
0x1800127db  jns     short loc_1800127F1
0x1800127dd  lea     rcx, [rbp+pvar]; pvar
0x1800127e1  call    cs:__imp_PropVariantClear
0x1800127e7  nop
0x1800127e8  lea     rcx, [rbp+var_38]
0x1800127ec  jmp     loc_180012714
0x1800127f1  cmp     word ptr [rbp+pvar], r12w
0x1800127f6  jz      loc_180012884
0x1800127fc  lea     rdx, [rbp+var_38]; pvarDest
0x180012800  lea     rcx, [rbp+pvar]; pvarSrc
0x180012804  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180012809  mov     ebx, eax
0x18001280b  test    eax, eax
0x18001280d  jns     short loc_18001281A
0x18001280f  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012816  jz      short loc_1800127DD
0x180012818  jmp     short loc_1800127D0
0x18001281a  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x18001281e  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180012822  call    ?UpdateGPSRefValue@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; UpdateGPSRefValue(tagPROPVARIANT *,tagPROPVARIANT const *)
0x180012827  mov     ebx, eax
0x180012829  test    eax, eax
0x18001282b  jns     short loc_180012884
0x18001282d  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012834  jnz     short loc_1800127D0
0x180012836  test    eax, eax
0x180012838  jns     short loc_180012884
0x18001283a  jmp     short loc_1800127DD
0x18001283c  cmp     eax, 88982F40h
0x180012841  jnz     short loc_18001280F
0x180012843  mov     rcx, [rdi+20h]
0x180012847  lea     r9, [rbp+var_38]; struct tagPROPVARIANT *
0x18001284b  lea     r8, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001284f  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x180012853  mov     rcx, [rcx]; struct _tagpropertykey *
0x180012856  call    ?ConstructGPSCoordProxyWithRef@@YAJAEBU_tagpropertykey@@PEBUtagPROPVARIANT@@1PEAU2@@Z; ConstructGPSCoordProxyWithRef(_tagpropertykey const &,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)
0x18001285b  mov     ebx, eax
0x18001285d  test    eax, eax
0x18001285f  jns     short loc_180012876
0x180012861  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012868  jnz     loc_1800127D0
0x18001286e  test    eax, eax
0x180012870  js      loc_1800127DD
0x180012876  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x18001287a  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001287e  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x180012883  nop
0x180012884  lea     rcx, [rbp+pvar]; pvar
0x180012888  call    cs:__imp_PropVariantClear
0x18001288e  nop
0x18001288f  lea     rcx, [rbp+var_38]
0x180012893  jmp     loc_18001273F
0x180012898  mov     r9d, esi
0x18001289b  xor     r8d, r8d
0x18001289e  jmp     short loc_1800128B0
0x1800128a0  mov     r9d, esi
0x1800128a3  jmp     short loc_1800128AD
0x1800128a5  xor     r9d, r9d
0x1800128a8  jmp     short loc_18001289B
0x1800128aa  xor     r9d, r9d; int
0x1800128ad  mov     r8d, esi; int
0x1800128b0  lea     rdx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x1800128b4  mov     rcx, rdi; this
0x1800128b7  call    ?CreateRationalFromPart@CRationalRuleWriter@@AEAAJPEAUtagPROPVARIANT@@HH@Z; CRationalRuleWriter::CreateRationalFromPart(tagPROPVARIANT *,int,int)
0x1800128bc  test    eax, eax
0x1800128be  mov     ebx, eax
0x1800128c0  jns     short loc_1800128D7
0x1800128c2  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800128c9  jnz     loc_1800129A9
0x1800128cf  test    eax, eax
0x1800128d1  js      loc_1800129B1
0x1800128d7  cmp     [r15+20h], r12
0x1800128db  jz      loc_180012987
0x1800128e1  xorps   xmm0, xmm0
0x1800128e4  xor     eax, eax
0x1800128e6  movups  xmmword ptr [rbp+pvar], xmm0
0x1800128ea  mov     qword ptr [rbp+pvar+10h], rax
0x1800128ee  lea     rdx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x1800128f2  lea     rcx, [rbp+pvar]; pvar
0x1800128f6  call    ?ExtractRefFromGPSCoord@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; ExtractRefFromGPSCoord(tagPROPVARIANT *,tagPROPVARIANT const *)
0x1800128fb  mov     ebx, eax
0x1800128fd  test    eax, eax
0x1800128ff  jns     short loc_18001291C
0x180012901  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012908  jz      short loc_180012913
0x18001290a  mov     ecx, eax; int
0x18001290c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012911  jmp     short loc_180012917
0x180012913  test    eax, eax
0x180012915  jns     short loc_18001291C
0x180012917  jmp     loc_180012710
0x18001291c  cmp     word ptr [rbp+pvar], r12w
0x180012921  jz      short loc_18001294E
0x180012923  mov     rcx, [rdi+28h]
0x180012927  mov     rax, [rcx]
0x18001292a  lea     r8, [rbp+pvar]
0x18001292e  mov     rdx, [r15+20h]
0x180012932  mov     rax, [rax+38h]
0x180012936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001293b  mov     ebx, eax
0x18001293d  test    eax, eax
0x18001293f  jns     short loc_18001294E
0x180012941  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012948  jnz     short loc_18001290A
0x18001294a  test    eax, eax
0x18001294c  js      short loc_180012917
0x18001294e  test    esi, esi
0x180012950  jz      short loc_180012917
0x180012952  mov     rax, [rdi]
0x180012955  lea     rcx, [rbp+pvarDest]
0x180012959  mov     [rsp+80h+var_60], rcx
0x18001295e  mov     r9d, [r15+0Ch]
0x180012962  mov     r8d, [r15+8]
0x180012966  mov     rdx, [r15+18h]
0x18001296a  mov     rcx, rdi
0x18001296d  mov     rax, [rax+40h]
0x180012971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012976  mov     ebx, eax
0x180012978  test    eax, eax
0x18001297a  jns     short loc_180012917
0x18001297c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012983  jnz     short loc_18001290A
0x180012985  jmp     short loc_180012917
0x180012987  test    esi, esi
0x180012989  jz      short loc_1800129B1
0x18001298b  lea     r8, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001298f  mov     rdx, r15; struct RULE_PATH_INFO *
0x180012992  mov     rcx, rdi; this
0x180012995  call    ?WriteRulePath@CRuleWriter@@MEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@@Z; CRuleWriter::WriteRulePath(RULE_PATH_INFO const *,tagPROPVARIANT const *)
0x18001299a  mov     ebx, eax
0x18001299c  test    eax, eax
0x18001299e  jns     short loc_1800129B1
0x1800129a0  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800129a7  jz      short loc_1800129B1
0x1800129a9  mov     ecx, eax; int
0x1800129ab  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800129b0  nop
0x1800129b1  lea     rcx, [rbp+pvarDest]; pvar
0x1800129b5  call    cs:__imp_PropVariantClear
0x1800129bb  mov     eax, ebx
0x1800129bd  add     rsp, 80h
0x1800129c4  pop     r15
0x1800129c6  pop     r14
0x1800129c8  pop     r12
0x1800129ca  pop     rdi
0x1800129cb  pop     rsi
0x1800129cc  pop     rbx
0x1800129cd  pop     rbp
0x1800129ce  retn
```
