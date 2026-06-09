# CRationalRuleWriter::WriteRulePath(RULE_PATH_INFO const *,tagPROPVARIANT const *)

- ea: `0x180012f00`
- end: `0x1800132d4`
- name: `?WriteRulePath@CRationalRuleWriter@@MEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@@Z`
- size: `980`
- prototype: `__int64 __fastcall(CRationalRuleWriter *__hidden this, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006fc0`
- `0x1800074fc`
- `0x18000f004`
- `0x1800124b4`
- `0x1800127e4`
- `0x180012f00`
- `0x1800132dc`
- `0x180013df0`
- `0x180014390`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012f32`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180012f32`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012ffa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001302b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800130d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013180`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800132b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012ffa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001302b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800130d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013180`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800132b3`

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
0x180012f00  push    rbp
0x180012f02  push    rbx
0x180012f03  push    rsi
0x180012f04  push    rdi
0x180012f05  push    r12
0x180012f07  push    r14
0x180012f09  push    r15
0x180012f0b  mov     rbp, rsp
0x180012f0e  sub     rsp, 80h
0x180012f15  mov     r14, r8
0x180012f18  mov     r15, rdx
0x180012f1b  mov     rdi, rcx
0x180012f1e  xorps   xmm0, xmm0
0x180012f21  xor     eax, eax
0x180012f23  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180012f27  mov     qword ptr [rbp+pvarDest+10h], rax
0x180012f2b  mov     rdx, r8; pvarSrc
0x180012f2e  lea     rcx, [rbp+pvarDest]; pvarDest
0x180012f32  call    cs:__imp_PropVariantCopy
0x180012f39  nop     dword ptr [rax+rax+00h]
0x180012f3e  mov     ebx, eax
0x180012f40  xor     r12d, r12d
0x180012f43  test    eax, eax
0x180012f45  jns     short loc_180012F5C
0x180012f47  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012f4e  jnz     loc_1800132A7
0x180012f54  test    eax, eax
0x180012f56  js      loc_1800132AF
0x180012f5c  mov     esi, 1
0x180012f61  mov     rcx, [rdi+20h]
0x180012f65  mov     edx, [rcx+18h]
0x180012f68  sub     edx, 2
0x180012f6b  jz      loc_1800131A8
0x180012f71  sub     edx, esi
0x180012f73  jz      loc_1800131A3
0x180012f79  sub     edx, 2
0x180012f7c  jz      loc_18001319E
0x180012f82  sub     edx, esi
0x180012f84  jz      loc_180013196
0x180012f8a  sub     edx, 2
0x180012f8d  jz      loc_180013047
0x180012f93  cmp     edx, esi
0x180012f95  jnz     loc_1800131D5
0x180012f9b  xorps   xmm0, xmm0
0x180012f9e  xor     eax, eax
0x180012fa0  movups  xmmword ptr [rbp+pvar], xmm0
0x180012fa4  mov     qword ptr [rbp+pvar+10h], rax
0x180012fa8  mov     rcx, [rdi+30h]
0x180012fac  mov     rax, [rcx]
0x180012faf  mov     r8, [rdi+8]
0x180012fb3  lea     r9, [rbp+pvar]
0x180012fb7  mov     r8, [r8+10h]
0x180012fbb  mov     rdx, [rdi+28h]
0x180012fbf  mov     rax, [rax+20h]
0x180012fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fc8  mov     ebx, eax
0x180012fca  test    eax, eax
0x180012fcc  js      short loc_18001301A
0x180012fce  mov     rdx, r14; struct tagPROPVARIANT *
0x180012fd1  lea     rcx, [rbp+pvar]; struct tagPROPVARIANT *
0x180012fd5  call    ?UpdateGPSRefValue@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; UpdateGPSRefValue(tagPROPVARIANT *,tagPROPVARIANT const *)
0x180012fda  mov     ebx, eax
0x180012fdc  test    eax, eax
0x180012fde  jns     short loc_18001300B
0x180012fe0  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180012fe7  jz      short loc_180012FF2
0x180012fe9  mov     ecx, eax; int
0x180012feb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012ff0  jmp     short loc_180012FF6
0x180012ff2  test    eax, eax
0x180012ff4  jns     short loc_18001300B
0x180012ff6  lea     rcx, [rbp+pvar]; pvar
0x180012ffa  call    cs:__imp_PropVariantClear
0x180013001  nop     dword ptr [rax+rax+00h]
0x180013006  jmp     loc_1800132AF
0x18001300b  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x18001300f  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180013013  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x180013018  jmp     short loc_180013027
0x18001301a  cmp     eax, 88982F40h
0x18001301f  jnz     short loc_18001303C
0x180013021  mov     ebx, r12d
0x180013024  mov     esi, r12d
0x180013027  lea     rcx, [rbp+pvar]; pvar
0x18001302b  call    cs:__imp_PropVariantClear
0x180013032  nop     dword ptr [rax+rax+00h]
0x180013037  jmp     loc_1800131D5
0x18001303c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180013043  jz      short loc_180012FF6
0x180013045  jmp     short loc_180012FE9
0x180013047  mov     ecx, 1014h
0x18001304c  movzx   eax, word ptr [r14]
0x180013050  sub     ax, cx
0x180013053  cmp     ax, si
0x180013056  ja      loc_1800131D5
0x18001305c  cmp     dword ptr [r14+8], 3
0x180013061  jnz     loc_1800131D5
0x180013067  xorps   xmm0, xmm0
0x18001306a  xor     eax, eax
0x18001306c  movups  xmmword ptr [rbp+var_38], xmm0
0x180013070  mov     qword ptr [rbp+var_38+10h], rax
0x180013074  movups  xmmword ptr [rbp+pvar], xmm0
0x180013078  mov     qword ptr [rbp+pvar+10h], rax
0x18001307c  mov     rcx, [rdi+30h]
0x180013080  mov     rax, [rcx]
0x180013083  mov     r8, [rdi+8]
0x180013087  lea     r9, [rbp+var_38]
0x18001308b  mov     r8, [r8+8]
0x18001308f  mov     rdx, [rdi+28h]
0x180013093  mov     rax, [rax+20h]
0x180013097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001309c  mov     ebx, eax
0x18001309e  test    eax, eax
0x1800130a0  js      loc_180013134
0x1800130a6  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x1800130aa  lea     rcx, [rbp+pvar]; pvar
0x1800130ae  call    ?ExtractRefFromGPSCoord@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; ExtractRefFromGPSCoord(tagPROPVARIANT *,tagPROPVARIANT const *)
0x1800130b3  mov     ebx, eax
0x1800130b5  test    eax, eax
0x1800130b7  jns     short loc_1800130E9
0x1800130b9  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800130c0  jz      short loc_1800130CB
0x1800130c2  mov     ecx, eax; int
0x1800130c4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800130c9  jmp     short loc_1800130CF
0x1800130cb  test    eax, eax
0x1800130cd  jns     short loc_1800130E9
0x1800130cf  lea     rcx, [rbp+pvar]; pvar
0x1800130d3  call    cs:__imp_PropVariantClear
0x1800130da  nop     dword ptr [rax+rax+00h]
0x1800130df  nop
0x1800130e0  lea     rcx, [rbp+var_38]
0x1800130e4  jmp     loc_180012FFA
0x1800130e9  cmp     word ptr [rbp+pvar], r12w
0x1800130ee  jz      loc_18001317C
0x1800130f4  lea     rdx, [rbp+var_38]; pvarDest
0x1800130f8  lea     rcx, [rbp+pvar]; pvarSrc
0x1800130fc  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180013101  mov     ebx, eax
0x180013103  test    eax, eax
0x180013105  jns     short loc_180013112
0x180013107  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001310e  jz      short loc_1800130CF
0x180013110  jmp     short loc_1800130C2
0x180013112  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x180013116  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001311a  call    ?UpdateGPSRefValue@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; UpdateGPSRefValue(tagPROPVARIANT *,tagPROPVARIANT const *)
0x18001311f  mov     ebx, eax
0x180013121  test    eax, eax
0x180013123  jns     short loc_18001317C
0x180013125  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18001312c  jnz     short loc_1800130C2
0x18001312e  test    eax, eax
0x180013130  jns     short loc_18001317C
0x180013132  jmp     short loc_1800130CF
0x180013134  cmp     eax, 88982F40h
0x180013139  jnz     short loc_180013107
0x18001313b  mov     rcx, [rdi+20h]
0x18001313f  lea     r9, [rbp+var_38]; struct tagPROPVARIANT *
0x180013143  lea     r8, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180013147  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x18001314b  mov     rcx, [rcx]; struct _tagpropertykey *
0x18001314e  call    ?ConstructGPSCoordProxyWithRef@@YAJAEBU_tagpropertykey@@PEBUtagPROPVARIANT@@1PEAU2@@Z; ConstructGPSCoordProxyWithRef(_tagpropertykey const &,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)
0x180013153  mov     ebx, eax
0x180013155  test    eax, eax
0x180013157  jns     short loc_18001316E
0x180013159  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180013160  jnz     loc_1800130C2
0x180013166  test    eax, eax
0x180013168  js      loc_1800130CF
0x18001316e  lea     rdx, [rbp+var_38]; struct tagPROPVARIANT *
0x180013172  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180013176  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x18001317b  nop
0x18001317c  lea     rcx, [rbp+pvar]; pvar
0x180013180  call    cs:__imp_PropVariantClear
0x180013187  nop     dword ptr [rax+rax+00h]
0x18001318c  nop
0x18001318d  lea     rcx, [rbp+var_38]
0x180013191  jmp     loc_18001302B
0x180013196  mov     r9d, esi
0x180013199  xor     r8d, r8d
0x18001319c  jmp     short loc_1800131AE
0x18001319e  mov     r9d, esi
0x1800131a1  jmp     short loc_1800131AB
0x1800131a3  xor     r9d, r9d
0x1800131a6  jmp     short loc_180013199
0x1800131a8  xor     r9d, r9d; int
0x1800131ab  mov     r8d, esi; int
0x1800131ae  lea     rdx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x1800131b2  mov     rcx, rdi; this
0x1800131b5  call    ?CreateRationalFromPart@CRationalRuleWriter@@AEAAJPEAUtagPROPVARIANT@@HH@Z; CRationalRuleWriter::CreateRationalFromPart(tagPROPVARIANT *,int,int)
0x1800131ba  test    eax, eax
0x1800131bc  mov     ebx, eax
0x1800131be  jns     short loc_1800131D5
0x1800131c0  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800131c7  jnz     loc_1800132A7
0x1800131cd  test    eax, eax
0x1800131cf  js      loc_1800132AF
0x1800131d5  cmp     [r15+20h], r12
0x1800131d9  jz      loc_180013285
0x1800131df  xorps   xmm0, xmm0
0x1800131e2  xor     eax, eax
0x1800131e4  movups  xmmword ptr [rbp+pvar], xmm0
0x1800131e8  mov     qword ptr [rbp+pvar+10h], rax
0x1800131ec  lea     rdx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x1800131f0  lea     rcx, [rbp+pvar]; pvar
0x1800131f4  call    ?ExtractRefFromGPSCoord@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; ExtractRefFromGPSCoord(tagPROPVARIANT *,tagPROPVARIANT const *)
0x1800131f9  mov     ebx, eax
0x1800131fb  test    eax, eax
0x1800131fd  jns     short loc_18001321A
0x1800131ff  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180013206  jz      short loc_180013211
0x180013208  mov     ecx, eax; int
0x18001320a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001320f  jmp     short loc_180013215
0x180013211  test    eax, eax
0x180013213  jns     short loc_18001321A
0x180013215  jmp     loc_180012FF6
0x18001321a  cmp     word ptr [rbp+pvar], r12w
0x18001321f  jz      short loc_18001324C
0x180013221  mov     rcx, [rdi+28h]
0x180013225  mov     rax, [rcx]
0x180013228  lea     r8, [rbp+pvar]
0x18001322c  mov     rdx, [r15+20h]
0x180013230  mov     rax, [rax+38h]
0x180013234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013239  mov     ebx, eax
0x18001323b  test    eax, eax
0x18001323d  jns     short loc_18001324C
0x18001323f  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180013246  jnz     short loc_180013208
0x180013248  test    eax, eax
0x18001324a  js      short loc_180013215
0x18001324c  test    esi, esi
0x18001324e  jz      short loc_180013215
0x180013250  mov     rax, [rdi]
0x180013253  lea     rcx, [rbp+pvarDest]
0x180013257  mov     [rsp+80h+var_60], rcx
0x18001325c  mov     r9d, [r15+0Ch]
0x180013260  mov     r8d, [r15+8]
0x180013264  mov     rdx, [r15+18h]
0x180013268  mov     rcx, rdi
0x18001326b  mov     rax, [rax+40h]
0x18001326f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013274  mov     ebx, eax
0x180013276  test    eax, eax
0x180013278  jns     short loc_180013215
0x18001327a  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180013281  jnz     short loc_180013208
0x180013283  jmp     short loc_180013215
0x180013285  test    esi, esi
0x180013287  jz      short loc_1800132AF
0x180013289  lea     r8, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18001328d  mov     rdx, r15; struct RULE_PATH_INFO *
0x180013290  mov     rcx, rdi; this
0x180013293  call    ?WriteRulePath@CRuleWriter@@MEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@@Z; CRuleWriter::WriteRulePath(RULE_PATH_INFO const *,tagPROPVARIANT const *)
0x180013298  mov     ebx, eax
0x18001329a  test    eax, eax
0x18001329c  jns     short loc_1800132AF
0x18001329e  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800132a5  jz      short loc_1800132AF
0x1800132a7  mov     ecx, eax; int
0x1800132a9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800132ae  nop
0x1800132af  lea     rcx, [rbp+pvarDest]; pvar
0x1800132b3  call    cs:__imp_PropVariantClear
0x1800132ba  nop     dword ptr [rax+rax+00h]
0x1800132bf  mov     eax, ebx
0x1800132c1  add     rsp, 80h
0x1800132c8  pop     r15
0x1800132ca  pop     r14
0x1800132cc  pop     r12
0x1800132ce  pop     rdi
0x1800132cf  pop     rsi
0x1800132d0  pop     rbx
0x1800132d1  pop     rbp
0x1800132d2  retn
```
