# CDateRuleReader::ReadRulePath(RULE_PATH_INFO const *,CReadResult * *)

- ea: `0x18000c8e0`
- end: `0x18000cb8c`
- name: `?ReadRulePath@CDateRuleReader@@UEAAJPEBURULE_PATH_INFO@@PEAPEAVCReadResult@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(CDateRuleReader *__hidden this, const struct RULE_PATH_INFO *, struct CReadResult **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000c8e0`
- `0x18000cb94`
- `0x18000cde0`
- `0x1800132dc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ca30`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cb07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ca30`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cb07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c96f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c9e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c9f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ca07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c96f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c9e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000c9f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ca07`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDateRuleReader::ReadRulePath(
        CDateRuleReader *this,
        const struct RULE_PATH_INFO *a2,
        struct CReadResult **a3)
{
  int v6; // eax
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  char *v11; // rax
  __int128 v12; // xmm0
  BYTE *v13; // xmm1_8
  int v14; // ecx
  int v15; // ecx
  __int64 v16; // rdx
  char *v17; // rax
  __int128 v18; // xmm0
  BYTE *pData; // xmm1_8
  PROPVARIANT v20; // [rsp+30h] [rbp-29h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-11h] BYREF
  PROPVARIANT v22; // [rsp+60h] [rbp+7h] BYREF

  memset(&v22, 0, sizeof(v22));
  *a3 = 0;
  v6 = *((_DWORD *)a2 + 3);
  if ( v6 == 4 || v6 == 9 )
  {
    memset(&pvar, 0, sizeof(pvar));
    memset(&v20, 0, sizeof(v20));
    v9 = (*(__int64 (__fastcall **)(CDateRuleReader *, _QWORD, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)this + 64LL))(
           this,
           *((_QWORD *)a2 + 3),
           *((unsigned int *)a2 + 2),
           0,
           &pvar);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( !g_doStackCaptures )
      {
LABEL_10:
        PropVariantClear(&v20);
        PropVariantClear(&pvar);
        goto LABEL_11;
      }
      goto LABEL_16;
    }
    v16 = *((_QWORD *)a2 + 4);
    if ( v16 )
      (*(void (__fastcall **)(CDateRuleReader *, __int64, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)this + 64LL))(
        this,
        v16,
        *((unsigned int *)a2 + 2),
        0,
        &v20);
    if ( *((_DWORD *)a2 + 3) == 9 )
    {
      v9 = ConvertIPTCDateTimeStringsOnRead(&pvar, &v20, &v22);
      v8 = v9;
      if ( v9 < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_10;
        goto LABEL_16;
      }
    }
    else
    {
      v9 = ConvertExifDateStringsOnRead(&pvar, &v20, &v22);
      v8 = v9;
      if ( v9 < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_10;
LABEL_16:
        v15 = v9;
LABEL_17:
        DoStackCapture(v15);
        goto LABEL_10;
      }
    }
    v17 = (char *)LocalAlloc(0x40u, 0x20u);
    if ( v17 )
    {
      v18 = *(_OWORD *)&v22.vt;
      pData = v22.bstrblobVal.pData;
      *(_QWORD *)v17 = &CReadResult::`vftable';
      *(_OWORD *)(v17 + 8) = v18;
      *((_QWORD *)v17 + 3) = pData;
      *a3 = (struct CReadResult *)v17;
      memset(&v22, 0, sizeof(v22));
      goto LABEL_10;
    }
    *a3 = 0;
    v8 = -2147024882;
    if ( !g_doStackCaptures )
      goto LABEL_10;
    v15 = -2147024882;
    goto LABEL_17;
  }
  memset(&pvar, 0, sizeof(pvar));
  v7 = (*(__int64 (__fastcall **)(CDateRuleReader *, _QWORD, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)this + 64LL))(
         this,
         *((_QWORD *)a2 + 3),
         *((unsigned int *)a2 + 2),
         *((unsigned int *)a2 + 3),
         &pvar);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v11 = (char *)LocalAlloc(0x40u, 0x20u);
    if ( v11 )
    {
      v12 = *(_OWORD *)&pvar.vt;
      v13 = pvar.bstrblobVal.pData;
      *(_QWORD *)v11 = &CReadResult::`vftable';
      *(_OWORD *)(v11 + 8) = v12;
      *((_QWORD *)v11 + 3) = v13;
      *a3 = (struct CReadResult *)v11;
      memset(&pvar, 0, sizeof(pvar));
      goto LABEL_5;
    }
    *a3 = 0;
    v8 = -2147024882;
    if ( !g_doStackCaptures )
      goto LABEL_5;
    v14 = -2147024882;
LABEL_15:
    DoStackCapture(v14);
    goto LABEL_5;
  }
  if ( g_doStackCaptures )
  {
    v14 = v7;
    goto LABEL_15;
  }
LABEL_5:
  PropVariantClear(&pvar);
  if ( v8 < 0 && g_doStackCaptures )
    DoStackCapture(v8);
LABEL_11:
  PropVariantClear(&v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c8e0  push    rbp
0x18000c8e2  push    rbx
0x18000c8e3  push    rsi
0x18000c8e4  push    rdi
0x18000c8e5  push    r14
0x18000c8e7  push    r15
0x18000c8e9  lea     rbp, [rsp-2Fh]
0x18000c8ee  sub     rsp, 88h
0x18000c8f5  mov     rsi, r8
0x18000c8f8  mov     rdi, rdx
0x18000c8fb  mov     r14, rcx
0x18000c8fe  xorps   xmm0, xmm0
0x18000c901  xor     eax, eax
0x18000c903  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18000c907  mov     qword ptr [rbp+57h+var_50+10h], rax
0x18000c90b  xor     r15d, r15d
0x18000c90e  mov     [r8], r15
0x18000c911  mov     eax, [rdx+0Ch]
0x18000c914  cmp     eax, 4
0x18000c917  jz      short loc_18000C995
0x18000c919  cmp     eax, 9
0x18000c91c  jz      short loc_18000C995
0x18000c91e  xor     eax, eax
0x18000c920  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000c924  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18000c928  mov     rax, [rcx]
0x18000c92b  lea     rcx, [rbp+57h+pvar]
0x18000c92f  mov     [rsp+0B0h+var_90], rcx
0x18000c934  mov     r9d, [rdx+0Ch]
0x18000c938  mov     r8d, [rdx+8]
0x18000c93c  mov     rdx, [rdx+18h]
0x18000c940  mov     rcx, r14
0x18000c943  mov     rax, [rax+40h]
0x18000c947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c94c  mov     ebx, eax
0x18000c94e  test    eax, eax
0x18000c950  jns     loc_18000CA26
0x18000c956  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000c95d  jnz     loc_18000CA76
0x18000c963  test    eax, eax
0x18000c965  jns     loc_18000CA26
0x18000c96b  lea     rcx, [rbp+57h+pvar]; pvar
0x18000c96f  call    cs:__imp_PropVariantClear
0x18000c976  nop     dword ptr [rax+rax+00h]
0x18000c97b  test    ebx, ebx
0x18000c97d  jns     loc_18000CA03
0x18000c983  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c98a  jz      short loc_18000CA03
0x18000c98c  mov     ecx, ebx; int
0x18000c98e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c993  jmp     short loc_18000CA03
0x18000c995  xor     eax, eax
0x18000c997  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000c99b  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18000c99f  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18000c9a3  mov     qword ptr [rbp+57h+var_80+10h], rax
0x18000c9a7  mov     rax, [rcx]
0x18000c9aa  lea     rcx, [rbp+57h+pvar]
0x18000c9ae  mov     [rsp+0B0h+var_90], rcx
0x18000c9b3  xor     r9d, r9d
0x18000c9b6  mov     r8d, [rdx+8]
0x18000c9ba  mov     rdx, [rdx+18h]
0x18000c9be  mov     rcx, r14
0x18000c9c1  mov     rax, [rax+40h]
0x18000c9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9ca  mov     ebx, eax
0x18000c9cc  test    eax, eax
0x18000c9ce  jns     loc_18000CAA7
0x18000c9d4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c9db  jnz     loc_18000CA82
0x18000c9e1  lea     rcx, [rbp+57h+var_80]; pvar
0x18000c9e5  call    cs:__imp_PropVariantClear
0x18000c9ec  nop     dword ptr [rax+rax+00h]
0x18000c9f1  nop
0x18000c9f2  lea     rcx, [rbp+57h+pvar]; pvar
0x18000c9f6  call    cs:__imp_PropVariantClear
0x18000c9fd  nop     dword ptr [rax+rax+00h]
0x18000ca02  nop
0x18000ca03  lea     rcx, [rbp+57h+var_50]; pvar
0x18000ca07  call    cs:__imp_PropVariantClear
0x18000ca0e  nop     dword ptr [rax+rax+00h]
0x18000ca13  mov     eax, ebx
0x18000ca15  add     rsp, 88h
0x18000ca1c  pop     r15
0x18000ca1e  pop     r14
0x18000ca20  pop     rdi
0x18000ca21  pop     rsi
0x18000ca22  pop     rbx
0x18000ca23  pop     rbp
0x18000ca24  retn
0x18000ca26  mov     edx, 20h ; ' '; uBytes
0x18000ca2b  mov     ecx, 40h ; '@'; uFlags
0x18000ca30  call    cs:__imp_LocalAlloc
0x18000ca37  nop     dword ptr [rax+rax+00h]
0x18000ca3c  mov     [rbp+57h+arg_8], rax
0x18000ca40  test    rax, rax
0x18000ca43  jz      short loc_18000CA8E
0x18000ca45  movups  xmm0, xmmword ptr [rbp+57h+pvar]
0x18000ca49  movsd   xmm1, qword ptr [rbp+57h+pvar+10h]
0x18000ca4e  lea     rcx, ??_7CReadResult@@6B@; const CReadResult::`vftable'
0x18000ca55  mov     [rax], rcx
0x18000ca58  movups  xmmword ptr [rax+8], xmm0
0x18000ca5c  movsd   qword ptr [rax+18h], xmm1
0x18000ca61  mov     [rsi], rax
0x18000ca64  xorps   xmm0, xmm0
0x18000ca67  xor     eax, eax
0x18000ca69  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000ca6d  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18000ca71  jmp     loc_18000C96B
0x18000ca76  mov     ecx, eax; int
0x18000ca78  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ca7d  jmp     loc_18000C96B
0x18000ca82  mov     ecx, eax; int
0x18000ca84  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ca89  jmp     loc_18000C9E1
0x18000ca8e  mov     [rsi], r15
0x18000ca91  mov     ebx, 8007000Eh
0x18000ca96  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000ca9d  jz      loc_18000C96B
0x18000caa3  mov     ecx, ebx
0x18000caa5  jmp     short loc_18000CA78
0x18000caa7  mov     rdx, [rdi+20h]
0x18000caab  test    rdx, rdx
0x18000caae  jz      short loc_18000CACF
0x18000cab0  mov     rax, [r14]
0x18000cab3  lea     rcx, [rbp+57h+var_80]
0x18000cab7  mov     [rsp+0B0h+var_90], rcx
0x18000cabc  xor     r9d, r9d
0x18000cabf  mov     r8d, [rdi+8]
0x18000cac3  mov     rcx, r14
0x18000cac6  mov     rax, [rax+40h]
0x18000caca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cacf  lea     r8, [rbp+57h+var_50]; struct tagPROPVARIANT *
0x18000cad3  lea     rdx, [rbp+57h+var_80]; struct tagPROPVARIANT *
0x18000cad7  lea     rcx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18000cadb  cmp     dword ptr [rdi+0Ch], 9
0x18000cadf  jnz     short loc_18000CB4D
0x18000cae1  call    ?ConvertIPTCDateTimeStringsOnRead@@YAJPEBUtagPROPVARIANT@@0PEAU1@@Z; ConvertIPTCDateTimeStringsOnRead(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000cae6  mov     ebx, eax
0x18000cae8  test    eax, eax
0x18000caea  jns     short loc_18000CAFD
0x18000caec  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000caf3  jnz     short loc_18000CA82
0x18000caf5  test    eax, eax
0x18000caf7  js      loc_18000C9E1
0x18000cafd  mov     edx, 20h ; ' '; uBytes
0x18000cb02  mov     ecx, 40h ; '@'; uFlags
0x18000cb07  call    cs:__imp_LocalAlloc
0x18000cb0e  nop     dword ptr [rax+rax+00h]
0x18000cb13  mov     [rbp+57h+arg_8], rax
0x18000cb17  test    rax, rax
0x18000cb1a  jz      short loc_18000CB6F
0x18000cb1c  movups  xmm0, xmmword ptr [rbp+57h+var_50]
0x18000cb20  movsd   xmm1, qword ptr [rbp+57h+var_50+10h]
0x18000cb25  lea     rcx, ??_7CReadResult@@6B@; const CReadResult::`vftable'
0x18000cb2c  mov     [rax], rcx
0x18000cb2f  movups  xmmword ptr [rax+8], xmm0
0x18000cb33  movsd   qword ptr [rax+18h], xmm1
0x18000cb38  mov     [rsi], rax
0x18000cb3b  xorps   xmm0, xmm0
0x18000cb3e  xor     eax, eax
0x18000cb40  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18000cb44  mov     qword ptr [rbp+57h+var_50+10h], rax
0x18000cb48  jmp     loc_18000C9E1
0x18000cb4d  call    ?ConvertExifDateStringsOnRead@@YAJPEBUtagPROPVARIANT@@0PEAU1@@Z; ConvertExifDateStringsOnRead(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT *)
0x18000cb52  mov     ebx, eax
0x18000cb54  test    eax, eax
0x18000cb56  jns     short loc_18000CAFD
0x18000cb58  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000cb5f  jnz     loc_18000CA82
0x18000cb65  test    eax, eax
0x18000cb67  js      loc_18000C9E1
0x18000cb6d  jmp     short loc_18000CAFD
0x18000cb6f  mov     [rsi], r15
0x18000cb72  mov     ebx, 8007000Eh
0x18000cb77  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000cb7e  jz      loc_18000C9E1
0x18000cb84  mov     ecx, ebx
0x18000cb86  jmp     loc_18000CA84
```
