# CRationalRuleReader::ReadRulePath(RULE_PATH_INFO const *,CReadResult * *)

- ea: `0x180007de0`
- end: `0x18000818c`
- name: `?ReadRulePath@CRationalRuleReader@@UEAAJPEBURULE_PATH_INFO@@PEAPEAVCReadResult@@@Z`
- size: `940`
- prototype: `__int64 __fastcall(CRationalRuleReader *__hidden this, const struct RULE_PATH_INFO *, struct CReadResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007de0`
- `0x1800084a0`
- `0x180008984`
- `0x1800129d8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007f80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000806b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007f80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000806b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e5f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007efc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f52`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f5d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ffb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008006`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008011`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800080aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800080b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008109`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008114`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008180`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e5f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007efc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f52`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f5d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ffb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008006`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008011`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800080aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800080b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008109`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008114`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008180`

## pseudocode

```c
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
0x180007de0  push    rbp
0x180007de2  push    rbx
0x180007de3  push    rsi
0x180007de4  push    rdi
0x180007de5  push    r14
0x180007de7  push    r15
0x180007de9  lea     rbp, [rsp-2Fh]
0x180007dee  sub     rsp, 88h
0x180007df5  mov     rdi, r8
0x180007df8  mov     rbx, rdx
0x180007dfb  mov     rsi, rcx
0x180007dfe  mov     rax, [rdx+20h]
0x180007e02  xor     r15d, r15d
0x180007e05  mov     [r8], r15
0x180007e08  xorps   xmm0, xmm0
0x180007e0b  test    rax, rax
0x180007e0e  jnz     short loc_180007E88
0x180007e10  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180007e14  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180007e18  mov     rax, [rcx]
0x180007e1b  lea     rcx, [rbp+57h+pvar]
0x180007e1f  mov     [rsp+0B0h+var_90], rcx
0x180007e24  mov     r9d, [rdx+0Ch]
0x180007e28  mov     r8d, [rdx+8]
0x180007e2c  mov     rdx, [rdx+18h]
0x180007e30  mov     rcx, rsi
0x180007e33  mov     rax, [rax+40h]
0x180007e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e3c  mov     ebx, eax
0x180007e3e  test    eax, eax
0x180007e40  jns     loc_180007F76
0x180007e46  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180007e4d  jnz     loc_18000801C
0x180007e53  test    eax, eax
0x180007e55  jns     loc_180007F76
0x180007e5b  lea     rcx, [rbp+57h+pvar]; pvar
0x180007e5f  call    cs:__imp_PropVariantClear
0x180007e65  test    ebx, ebx
0x180007e67  jns     short loc_180007E76
0x180007e69  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007e70  jnz     loc_180008028
0x180007e76  mov     eax, ebx
0x180007e78  add     rsp, 88h
0x180007e7f  pop     r15
0x180007e81  pop     r14
0x180007e83  pop     rdi
0x180007e84  pop     rsi
0x180007e85  pop     rbx
0x180007e86  pop     rbp
0x180007e87  retn
0x180007e88  xor     eax, eax
0x180007e8a  movups  xmmword ptr [rbp+57h+pvarDest], xmm0
0x180007e8e  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x180007e92  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x180007e96  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x180007e9a  mov     rax, [rcx+20h]
0x180007e9e  cmp     dword ptr [rax+18h], 9
0x180007ea2  jnz     short loc_180007F12
0x180007ea4  mov     rcx, [rsi+28h]
0x180007ea8  mov     rax, [rcx]
0x180007eab  lea     r8, [rbp+57h+pvarSrc]
0x180007eaf  mov     rdx, [rbx+20h]
0x180007eb3  mov     rax, [rax+28h]
0x180007eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ebc  mov     ebx, eax
0x180007ebe  cmp     eax, 88982F40h
0x180007ec3  jnz     short loc_180007ED3
0x180007ec5  mov     rax, [rsi+20h]
0x180007ec9  cmp     dword ptr [rax+18h], 9
0x180007ecd  jnz     loc_180008034
0x180007ed3  mov     rax, [rsi+20h]
0x180007ed7  mov     ecx, [rax+18h]
0x180007eda  cmp     ecx, 9
0x180007edd  jnz     loc_180007FC4
0x180007ee3  test    ebx, ebx
0x180007ee5  jns     loc_180008039
0x180007eeb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007ef2  jnz     loc_1800080F1
0x180007ef8  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180007efc  call    cs:__imp_PropVariantClear
0x180007f02  nop
0x180007f03  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180007f07  call    cs:__imp_PropVariantClear
0x180007f0d  jmp     loc_180007E76
0x180007f12  mov     rax, [rcx]
0x180007f15  lea     rcx, [rbp+57h+pvarDest]
0x180007f19  mov     [rsp+0B0h+var_90], rcx
0x180007f1e  mov     r9d, [rdx+0Ch]
0x180007f22  mov     r8d, [rdx+8]
0x180007f26  mov     rdx, [rdx+18h]
0x180007f2a  mov     rcx, rsi
0x180007f2d  mov     rax, [rax+40h]
0x180007f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f36  mov     r14d, eax
0x180007f39  test    eax, eax
0x180007f3b  jns     loc_180007EA4
0x180007f41  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007f48  jnz     loc_18000811F
0x180007f4e  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180007f52  call    cs:__imp_PropVariantClear
0x180007f58  nop
0x180007f59  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180007f5d  call    cs:__imp_PropVariantClear
0x180007f63  mov     eax, r14d
0x180007f66  add     rsp, 88h
0x180007f6d  pop     r15
0x180007f6f  pop     r14
0x180007f71  pop     rdi
0x180007f72  pop     rsi
0x180007f73  pop     rbx
0x180007f74  pop     rbp
0x180007f75  retn
0x180007f76  mov     edx, 20h ; ' '; uBytes
0x180007f7b  mov     ecx, 40h ; '@'; uFlags
0x180007f80  call    cs:__imp_LocalAlloc
0x180007f86  mov     [rbp+57h+arg_8], rax
0x180007f8a  test    rax, rax
0x180007f8d  jz      loc_1800080C0
0x180007f93  movups  xmm0, xmmword ptr [rbp+57h+pvar]
0x180007f97  movsd   xmm1, qword ptr [rbp+57h+pvar+10h]
0x180007f9c  lea     rcx, ??_7CReadResult@@6B@; const CReadResult::`vftable'
0x180007fa3  mov     [rax], rcx
0x180007fa6  movups  xmmword ptr [rax+8], xmm0
0x180007faa  movsd   qword ptr [rax+18h], xmm1
0x180007faf  mov     [rdi], rax
0x180007fb2  xorps   xmm0, xmm0
0x180007fb5  xor     eax, eax
0x180007fb7  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180007fbb  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180007fbf  jmp     loc_180007E5B
0x180007fc4  cmp     ecx, 5
0x180007fc7  jz      loc_180008061
0x180007fcd  cmp     ecx, 6
0x180007fd0  jz      loc_180008061
0x180007fd6  xorps   xmm0, xmm0
0x180007fd9  xor     eax, eax
0x180007fdb  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180007fdf  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180007fe3  test    ebx, ebx
0x180007fe5  jns     loc_18000812C
0x180007feb  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180007ff1  jnz     loc_18000814C
0x180007ff7  lea     rcx, [rbp+57h+pvar]; pvar
0x180007ffb  call    cs:__imp_PropVariantClear
0x180008001  nop
0x180008002  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180008006  call    cs:__imp_PropVariantClear
0x18000800c  nop
0x18000800d  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180008011  call    cs:__imp_PropVariantClear
0x180008017  jmp     loc_180007E76
0x18000801c  mov     ecx, eax; int
0x18000801e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008023  jmp     loc_180007E5B
0x180008028  mov     ecx, ebx; int
0x18000802a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000802f  jmp     loc_180007E76
0x180008034  mov     ebx, r15d
0x180008037  jmp     short loc_180008061
0x180008039  lea     rdx, [rbp+57h+pvarDest]; pvarDest
0x18000803d  lea     rcx, [rbp+57h+pvarSrc]; pvarSrc
0x180008041  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180008046  mov     ebx, eax
0x180008048  test    eax, eax
0x18000804a  jns     short loc_180008059
0x18000804c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180008053  jnz     loc_1800080FD
0x180008059  test    ebx, ebx
0x18000805b  js      loc_180008105
0x180008061  mov     edx, 20h ; ' '; uBytes
0x180008066  mov     ecx, 40h ; '@'; uFlags
0x18000806b  call    cs:__imp_LocalAlloc
0x180008071  mov     [rbp+57h+arg_8], rax
0x180008075  test    rax, rax
0x180008078  jz      short loc_1800080DC
0x18000807a  movups  xmm0, xmmword ptr [rbp+57h+pvarDest]
0x18000807e  movsd   xmm1, qword ptr [rbp+57h+pvarDest+10h]
0x180008083  lea     rcx, ??_7CReadResult@@6B@; const CReadResult::`vftable'
0x18000808a  mov     [rax], rcx
0x18000808d  movups  xmmword ptr [rax+8], xmm0
0x180008091  movsd   qword ptr [rax+18h], xmm1
0x180008096  mov     [rdi], rax
0x180008099  xorps   xmm0, xmm0
0x18000809c  xor     eax, eax
0x18000809e  movups  xmmword ptr [rbp+57h+pvarDest], xmm0
0x1800080a2  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x1800080a6  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x1800080aa  call    cs:__imp_PropVariantClear
0x1800080b0  nop
0x1800080b1  lea     rcx, [rbp+57h+pvarDest]; pvar
0x1800080b5  call    cs:__imp_PropVariantClear
0x1800080bb  jmp     loc_180007E76
0x1800080c0  mov     [rdi], r15
0x1800080c3  mov     ebx, 8007000Eh
0x1800080c8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800080cf  jz      loc_180007E5B
0x1800080d5  mov     ecx, ebx
0x1800080d7  jmp     loc_18000801E
0x1800080dc  mov     [rdi], r15
0x1800080df  mov     ebx, 8007000Eh
0x1800080e4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800080eb  jz      loc_180007EF8
0x1800080f1  mov     ecx, ebx; int
0x1800080f3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800080f8  jmp     loc_180007EF8
0x1800080fd  mov     ecx, ebx; int
0x1800080ff  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008104  nop
0x180008105  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180008109  call    cs:__imp_PropVariantClear
0x18000810f  nop
0x180008110  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180008114  call    cs:__imp_PropVariantClear
0x18000811a  jmp     loc_180007E76
0x18000811f  mov     ecx, r14d; int
0x180008122  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008127  jmp     loc_180007F4E
0x18000812c  lea     rdx, [rbp+57h+pvar]; pvarDest
0x180008130  lea     rcx, [rbp+57h+pvarSrc]; pvarSrc
0x180008134  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180008139  mov     ebx, eax
0x18000813b  test    eax, eax
0x18000813d  jns     short loc_180008158
0x18000813f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180008146  jz      loc_180007FF7
0x18000814c  mov     ecx, ebx; int
0x18000814e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008153  jmp     loc_180007FF7
0x180008158  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18000815c  lea     rcx, [rbp+57h+pvarDest]; struct tagPROPVARIANT *
0x180008160  call    ?UpdateGPSRefValue@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; UpdateGPSRefValue(tagPROPVARIANT *,tagPROPVARIANT const *)
0x180008165  mov     ebx, eax
0x180008167  test    eax, eax
0x180008169  jns     short loc_180008174
0x18000816b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180008172  jnz     short loc_18000814C
0x180008174  test    ebx, ebx
0x180008176  js      loc_180007FF7
0x18000817c  lea     rcx, [rbp+57h+pvar]; pvar
0x180008180  call    cs:__imp_PropVariantClear
0x180008186  jmp     loc_180008061
```
