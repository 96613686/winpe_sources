# CRationalRuleReader::ReadRulePath(RULE_PATH_INFO const *,CReadResult * *)

- ea: `0x180006890`
- end: `0x180006c98`
- name: `?ReadRulePath@CRationalRuleReader@@UEAAJPEBURULE_PATH_INFO@@PEAPEAVCReadResult@@@Z`
- size: `1032`
- prototype: `__int64 __fastcall(CRationalRuleReader *__hidden this, const struct RULE_PATH_INFO *, struct CReadResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006890`
- `0x180006fc0`
- `0x1800074fc`
- `0x1800132dc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006b53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006b53`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000690f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800069b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800069c4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a15`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a26`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006ad1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006ae2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006af3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006b98`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006ba9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006c03`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006c14`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006c86`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000690f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800069b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800069c4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a15`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a26`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006ad1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006ae2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006af3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006b98`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006ba9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006c03`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006c14`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006c86`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRationalRuleReader::ReadRulePath(
        CRationalRuleReader *this,
        const struct RULE_PATH_INFO *a2,
        struct CReadResult **a3)
{
  __int64 v6; // rax
  int v7; // eax
  int updated; // ebx
  int v10; // ecx
  int v11; // eax
  unsigned int v12; // r14d
  char *v13; // rax
  __int128 v14; // xmm0
  BYTE *pData; // xmm1_8
  int v16; // ecx
  int v17; // eax
  char *v18; // rax
  __int128 v19; // xmm0
  BYTE *v20; // xmm1_8
  PROPVARIANT pvarDest; // [rsp+30h] [rbp-29h] BYREF
  PROPVARIANT pvarSrc; // [rsp+48h] [rbp-11h] BYREF
  PROPVARIANT pvar; // [rsp+60h] [rbp+7h] BYREF

  v6 = *((_QWORD *)a2 + 4);
  *a3 = 0;
  if ( !v6 )
  {
    memset(&pvar, 0, sizeof(pvar));
    v7 = (*(__int64 (__fastcall **)(CRationalRuleReader *, _QWORD, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)this + 64LL))(
           this,
           *((_QWORD *)a2 + 3),
           *((unsigned int *)a2 + 2),
           *((unsigned int *)a2 + 3),
           &pvar);
    updated = v7;
    if ( v7 >= 0 )
    {
      v13 = (char *)LocalAlloc(0x40u, 0x20u);
      if ( v13 )
      {
        v14 = *(_OWORD *)&pvar.vt;
        pData = pvar.bstrblobVal.pData;
        *(_QWORD *)v13 = &CReadResult::`vftable';
        *(_OWORD *)(v13 + 8) = v14;
        *((_QWORD *)v13 + 3) = pData;
        *a3 = (struct CReadResult *)v13;
        memset(&pvar, 0, sizeof(pvar));
        goto LABEL_4;
      }
      *a3 = 0;
      updated = -2147024882;
      if ( !g_doStackCaptures )
      {
LABEL_4:
        PropVariantClear(&pvar);
        if ( updated < 0 )
        {
          if ( g_doStackCaptures )
            DoStackCapture(updated);
        }
        return (unsigned int)updated;
      }
      v16 = -2147024882;
    }
    else
    {
      if ( !g_doStackCaptures )
        goto LABEL_4;
      v16 = v7;
    }
    DoStackCapture(v16);
    goto LABEL_4;
  }
  memset(&pvarDest, 0, sizeof(pvarDest));
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  if ( *(_DWORD *)(*((_QWORD *)this + 4) + 24LL) == 9
    || (v11 = (*(__int64 (__fastcall **)(CRationalRuleReader *, _QWORD, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)this + 64LL))(
                this,
                *((_QWORD *)a2 + 3),
                *((unsigned int *)a2 + 2),
                *((unsigned int *)a2 + 3),
                &pvarDest),
        v12 = v11,
        v11 >= 0) )
  {
    updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, PROPVARIANT *))(**((_QWORD **)this + 5) + 40LL))(
                *((_QWORD *)this + 5),
                *((_QWORD *)a2 + 4),
                &pvarSrc);
    if ( updated == -2003292352 && *(_DWORD *)(*((_QWORD *)this + 4) + 24LL) != 9 )
    {
      updated = 0;
    }
    else
    {
      v10 = *(_DWORD *)(*((_QWORD *)this + 4) + 24LL);
      if ( v10 == 9 )
      {
        if ( updated < 0 )
        {
          if ( !g_doStackCaptures )
            goto LABEL_39;
          goto LABEL_37;
        }
        v17 = SniffAndConvertToWideString(&pvarSrc, &pvarDest);
        updated = v17;
        if ( v17 < 0 && g_doStackCaptures )
        {
          DoStackCapture(v17);
          goto LABEL_39;
        }
        if ( v17 < 0 )
        {
LABEL_39:
          PropVariantClear(&pvarSrc);
          PropVariantClear(&pvarDest);
          return (unsigned int)updated;
        }
        goto LABEL_32;
      }
      if ( v10 != 5 && v10 != 6 )
      {
        memset(&pvar, 0, sizeof(pvar));
        if ( updated < 0 )
        {
          if ( !g_doStackCaptures )
          {
LABEL_25:
            PropVariantClear(&pvar);
            PropVariantClear(&pvarSrc);
            PropVariantClear(&pvarDest);
            return (unsigned int)updated;
          }
LABEL_42:
          DoStackCapture(updated);
          goto LABEL_25;
        }
        updated = SniffAndConvertToWideString(&pvarSrc, &pvar);
        if ( updated < 0 )
        {
          if ( !g_doStackCaptures )
            goto LABEL_25;
          goto LABEL_42;
        }
        updated = UpdateGPSRefValue(&pvarDest, &pvar);
        if ( updated < 0 && g_doStackCaptures )
          goto LABEL_42;
        if ( updated < 0 )
          goto LABEL_25;
        PropVariantClear(&pvar);
      }
    }
LABEL_32:
    v18 = (char *)LocalAlloc(0x40u, 0x20u);
    if ( !v18 )
    {
      *a3 = 0;
      updated = -2147024882;
      if ( !g_doStackCaptures )
        goto LABEL_39;
LABEL_37:
      DoStackCapture(updated);
      goto LABEL_39;
    }
    v19 = *(_OWORD *)&pvarDest.vt;
    v20 = pvarDest.bstrblobVal.pData;
    *(_QWORD *)v18 = &CReadResult::`vftable';
    *(_OWORD *)(v18 + 8) = v19;
    *((_QWORD *)v18 + 3) = v20;
    *a3 = (struct CReadResult *)v18;
    memset(&pvarDest, 0, sizeof(pvarDest));
    PropVariantClear(&pvarSrc);
    PropVariantClear(&pvarDest);
    return (unsigned int)updated;
  }
  if ( g_doStackCaptures )
    DoStackCapture(v11);
  PropVariantClear(&pvarSrc);
  PropVariantClear(&pvarDest);
  return v12;
}

```

## disassembly

```asm
0x180006890  push    rbp
0x180006892  push    rbx
0x180006893  push    rsi
0x180006894  push    rdi
0x180006895  push    r14
0x180006897  push    r15
0x180006899  lea     rbp, [rsp-2Fh]
0x18000689e  sub     rsp, 88h
0x1800068a5  mov     rdi, r8
0x1800068a8  mov     rbx, rdx
0x1800068ab  mov     rsi, rcx
0x1800068ae  mov     rax, [rdx+20h]
0x1800068b2  xor     r15d, r15d
0x1800068b5  mov     [r8], r15
0x1800068b8  xorps   xmm0, xmm0
0x1800068bb  test    rax, rax
0x1800068be  jnz     short loc_18000693F
0x1800068c0  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800068c4  mov     qword ptr [rbp+57h+pvar+10h], rax
0x1800068c8  mov     rax, [rcx]
0x1800068cb  lea     rcx, [rbp+57h+pvar]
0x1800068cf  mov     [rsp+0B0h+var_90], rcx
0x1800068d4  mov     r9d, [rdx+0Ch]
0x1800068d8  mov     r8d, [rdx+8]
0x1800068dc  mov     rdx, [rdx+18h]
0x1800068e0  mov     rcx, rsi
0x1800068e3  mov     rax, [rax+40h]
0x1800068e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ec  mov     ebx, eax
0x1800068ee  test    eax, eax
0x1800068f0  jns     loc_180006A46
0x1800068f6  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800068fd  jnz     loc_180006B04
0x180006903  test    eax, eax
0x180006905  jns     loc_180006A46
0x18000690b  lea     rcx, [rbp+57h+pvar]; pvar
0x18000690f  call    cs:__imp_PropVariantClear
0x180006916  nop     dword ptr [rax+rax+00h]
0x18000691b  test    ebx, ebx
0x18000691d  jns     short loc_18000692C
0x18000691f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006926  jnz     loc_180006B10
0x18000692c  mov     eax, ebx
0x18000692e  add     rsp, 88h
0x180006935  pop     r15
0x180006937  pop     r14
0x180006939  pop     rdi
0x18000693a  pop     rsi
0x18000693b  pop     rbx
0x18000693c  pop     rbp
0x18000693d  retn
0x18000693f  xor     eax, eax
0x180006941  movups  xmmword ptr [rbp+57h+pvarDest], xmm0
0x180006945  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x180006949  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x18000694d  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x180006951  mov     rax, [rcx+20h]
0x180006955  cmp     dword ptr [rax+18h], 9
0x180006959  jnz     short loc_1800069D5
0x18000695b  mov     rcx, [rsi+28h]
0x18000695f  mov     rax, [rcx]
0x180006962  lea     r8, [rbp+57h+pvarSrc]
0x180006966  mov     rdx, [rbx+20h]
0x18000696a  mov     rax, [rax+28h]
0x18000696e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006973  mov     ebx, eax
0x180006975  cmp     eax, 88982F40h
0x18000697a  jnz     short loc_18000698A
0x18000697c  mov     rax, [rsi+20h]
0x180006980  cmp     dword ptr [rax+18h], 9
0x180006984  jnz     loc_180006B1C
0x18000698a  mov     rax, [rsi+20h]
0x18000698e  mov     ecx, [rax+18h]
0x180006991  cmp     ecx, 9
0x180006994  jnz     loc_180006A9A
0x18000699a  test    ebx, ebx
0x18000699c  jns     loc_180006B21
0x1800069a2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800069a9  jnz     loc_180006BEB
0x1800069af  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x1800069b3  call    cs:__imp_PropVariantClear
0x1800069ba  nop     dword ptr [rax+rax+00h]
0x1800069bf  nop
0x1800069c0  lea     rcx, [rbp+57h+pvarDest]; pvar
0x1800069c4  call    cs:__imp_PropVariantClear
0x1800069cb  nop     dword ptr [rax+rax+00h]
0x1800069d0  jmp     loc_18000692C
0x1800069d5  mov     rax, [rcx]
0x1800069d8  lea     rcx, [rbp+57h+pvarDest]
0x1800069dc  mov     [rsp+0B0h+var_90], rcx
0x1800069e1  mov     r9d, [rdx+0Ch]
0x1800069e5  mov     r8d, [rdx+8]
0x1800069e9  mov     rdx, [rdx+18h]
0x1800069ed  mov     rcx, rsi
0x1800069f0  mov     rax, [rax+40h]
0x1800069f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f9  mov     r14d, eax
0x1800069fc  test    eax, eax
0x1800069fe  jns     loc_18000695B
0x180006a04  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006a0b  jnz     loc_180006C25
0x180006a11  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180006a15  call    cs:__imp_PropVariantClear
0x180006a1c  nop     dword ptr [rax+rax+00h]
0x180006a21  nop
0x180006a22  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180006a26  call    cs:__imp_PropVariantClear
0x180006a2d  nop     dword ptr [rax+rax+00h]
0x180006a32  mov     eax, r14d
0x180006a35  add     rsp, 88h
0x180006a3c  pop     r15
0x180006a3e  pop     r14
0x180006a40  pop     rdi
0x180006a41  pop     rsi
0x180006a42  pop     rbx
0x180006a43  pop     rbp
0x180006a44  retn
0x180006a46  mov     edx, 20h ; ' '; uBytes
0x180006a4b  mov     ecx, 40h ; '@'; uFlags
0x180006a50  call    cs:__imp_LocalAlloc
0x180006a57  nop     dword ptr [rax+rax+00h]
0x180006a5c  mov     [rbp+57h+arg_8], rax
0x180006a60  test    rax, rax
0x180006a63  jz      loc_180006BBA
0x180006a69  movups  xmm0, xmmword ptr [rbp+57h+pvar]
0x180006a6d  movsd   xmm1, qword ptr [rbp+57h+pvar+10h]
0x180006a72  lea     rcx, ??_7CReadResult@@6B@; const CReadResult::`vftable'
0x180006a79  mov     [rax], rcx
0x180006a7c  movups  xmmword ptr [rax+8], xmm0
0x180006a80  movsd   qword ptr [rax+18h], xmm1
0x180006a85  mov     [rdi], rax
0x180006a88  xorps   xmm0, xmm0
0x180006a8b  xor     eax, eax
0x180006a8d  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180006a91  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180006a95  jmp     loc_18000690B
0x180006a9a  cmp     ecx, 5
0x180006a9d  jz      loc_180006B49
0x180006aa3  cmp     ecx, 6
0x180006aa6  jz      loc_180006B49
0x180006aac  xorps   xmm0, xmm0
0x180006aaf  xor     eax, eax
0x180006ab1  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180006ab5  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180006ab9  test    ebx, ebx
0x180006abb  jns     loc_180006C32
0x180006ac1  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180006ac7  jnz     loc_180006C52
0x180006acd  lea     rcx, [rbp+57h+pvar]; pvar
0x180006ad1  call    cs:__imp_PropVariantClear
0x180006ad8  nop     dword ptr [rax+rax+00h]
0x180006add  nop
0x180006ade  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180006ae2  call    cs:__imp_PropVariantClear
0x180006ae9  nop     dword ptr [rax+rax+00h]
0x180006aee  nop
0x180006aef  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180006af3  call    cs:__imp_PropVariantClear
0x180006afa  nop     dword ptr [rax+rax+00h]
0x180006aff  jmp     loc_18000692C
0x180006b04  mov     ecx, eax; int
0x180006b06  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006b0b  jmp     loc_18000690B
0x180006b10  mov     ecx, ebx; int
0x180006b12  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006b17  jmp     loc_18000692C
0x180006b1c  mov     ebx, r15d
0x180006b1f  jmp     short loc_180006B49
0x180006b21  lea     rdx, [rbp+57h+pvarDest]; pvarDest
0x180006b25  lea     rcx, [rbp+57h+pvarSrc]; pvarSrc
0x180006b29  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180006b2e  mov     ebx, eax
0x180006b30  test    eax, eax
0x180006b32  jns     short loc_180006B41
0x180006b34  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006b3b  jnz     loc_180006BF7
0x180006b41  test    ebx, ebx
0x180006b43  js      loc_180006BFF
0x180006b49  mov     edx, 20h ; ' '; uBytes
0x180006b4e  mov     ecx, 40h ; '@'; uFlags
0x180006b53  call    cs:__imp_LocalAlloc
0x180006b5a  nop     dword ptr [rax+rax+00h]
0x180006b5f  mov     [rbp+57h+arg_8], rax
0x180006b63  test    rax, rax
0x180006b66  jz      short loc_180006BD6
0x180006b68  movups  xmm0, xmmword ptr [rbp+57h+pvarDest]
0x180006b6c  movsd   xmm1, qword ptr [rbp+57h+pvarDest+10h]
0x180006b71  lea     rcx, ??_7CReadResult@@6B@; const CReadResult::`vftable'
0x180006b78  mov     [rax], rcx
0x180006b7b  movups  xmmword ptr [rax+8], xmm0
0x180006b7f  movsd   qword ptr [rax+18h], xmm1
0x180006b84  mov     [rdi], rax
0x180006b87  xorps   xmm0, xmm0
0x180006b8a  xor     eax, eax
0x180006b8c  movups  xmmword ptr [rbp+57h+pvarDest], xmm0
0x180006b90  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x180006b94  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180006b98  call    cs:__imp_PropVariantClear
0x180006b9f  nop     dword ptr [rax+rax+00h]
0x180006ba4  nop
0x180006ba5  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180006ba9  call    cs:__imp_PropVariantClear
0x180006bb0  nop     dword ptr [rax+rax+00h]
0x180006bb5  jmp     loc_18000692C
0x180006bba  mov     [rdi], r15
0x180006bbd  mov     ebx, 8007000Eh
0x180006bc2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006bc9  jz      loc_18000690B
0x180006bcf  mov     ecx, ebx
0x180006bd1  jmp     loc_180006B06
0x180006bd6  mov     [rdi], r15
0x180006bd9  mov     ebx, 8007000Eh
0x180006bde  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006be5  jz      loc_1800069AF
0x180006beb  mov     ecx, ebx; int
0x180006bed  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006bf2  jmp     loc_1800069AF
0x180006bf7  mov     ecx, ebx; int
0x180006bf9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006bfe  nop
0x180006bff  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180006c03  call    cs:__imp_PropVariantClear
0x180006c0a  nop     dword ptr [rax+rax+00h]
0x180006c0f  nop
0x180006c10  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180006c14  call    cs:__imp_PropVariantClear
0x180006c1b  nop     dword ptr [rax+rax+00h]
0x180006c20  jmp     loc_18000692C
0x180006c25  mov     ecx, r14d; int
0x180006c28  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006c2d  jmp     loc_180006A11
0x180006c32  lea     rdx, [rbp+57h+pvar]; pvarDest
0x180006c36  lea     rcx, [rbp+57h+pvarSrc]; pvarSrc
0x180006c3a  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180006c3f  mov     ebx, eax
0x180006c41  test    eax, eax
0x180006c43  jns     short loc_180006C5E
0x180006c45  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006c4c  jz      loc_180006ACD
0x180006c52  mov     ecx, ebx; int
0x180006c54  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006c59  jmp     loc_180006ACD
0x180006c5e  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180006c62  lea     rcx, [rbp+57h+pvarDest]; struct tagPROPVARIANT *
0x180006c66  call    ?UpdateGPSRefValue@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; UpdateGPSRefValue(tagPROPVARIANT *,tagPROPVARIANT const *)
0x180006c6b  mov     ebx, eax
0x180006c6d  test    eax, eax
0x180006c6f  jns     short loc_180006C7A
0x180006c71  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006c78  jnz     short loc_180006C52
0x180006c7a  test    ebx, ebx
0x180006c7c  js      loc_180006ACD
0x180006c82  lea     rcx, [rbp+57h+pvar]; pvar
0x180006c86  call    cs:__imp_PropVariantClear
0x180006c8d  nop     dword ptr [rax+rax+00h]
0x180006c92  jmp     loc_180006B49
```
