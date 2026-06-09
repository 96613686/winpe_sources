# CRationalRuleWriter::ConvertDiskFormatOnWrite(DiskFormats,tagPROPVARIANT *)

- ea: `0x180012440`
- end: `0x180012611`
- name: `?ConvertDiskFormatOnWrite@CRationalRuleWriter@@MEAAJW4DiskFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `465`
- prototype: `int __high(enum DiskFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180006da4`
- `0x1800074e0`
- `0x180007c94`
- `0x180008de0`
- `0x180009010`
- `0x18000e90c`
- `0x180012440`
- `0x1800129d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001251e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012529`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012534`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001253f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001251e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012529`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012534`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001253f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRationalRuleWriter::ConvertDiskFormatOnWrite(__int64 a1, int a2, struct tagPROPVARIANT *a3)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // eax
  PROPVARIANT pvarDest; // [rsp+30h] [rbp-9h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp+Fh] BYREF
  PROPVARIANT v10; // [rsp+60h] [rbp+27h] BYREF
  PROPVARIANT v11; // [rsp+78h] [rbp+3Fh] BYREF

  v4 = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  memset(&v11, 0, sizeof(v11));
  memset(&v10, 0, sizeof(v10));
  memset(&pvar, 0, sizeof(pvar));
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) != 2 && *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) != 3 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) == 5 || *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) == 6 )
    {
LABEL_7:
      if ( a3->vt != 31 )
      {
        if ( (unsigned int)a3->vt - 4116 >= 2 )
          goto LABEL_9;
        if ( a2 == 3 )
        {
          v6 = ConvertGpsCoordUI8ToXMP(a3);
        }
        else
        {
          if ( a3->lVal != 4 )
            goto LABEL_19;
          v6 = StripGPSCoordinateReferenceDataFromGPSCoordVector(a3);
        }
        goto LABEL_15;
      }
      if ( a2 != 10 )
        goto LABEL_19;
      v6 = ConvertGPSCoordinateTextToVector(a3, &v11, &v10, &pvar, &pvarDest);
      v4 = v6;
      if ( v6 < 0 )
      {
LABEL_16:
        if ( !g_doStackCaptures )
          goto LABEL_19;
LABEL_17:
        v5 = v6;
        goto LABEL_18;
      }
      v6 = StripGPSCoordinateReferenceDataFromGPSCoordVector(&pvarDest);
LABEL_23:
      v4 = v6;
      if ( v6 >= 0 )
      {
        TransferPropVariant(a3, &pvarDest);
        goto LABEL_19;
      }
      if ( !g_doStackCaptures )
        goto LABEL_19;
      goto LABEL_17;
    }
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) != 7 )
    {
      if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) - 8) > 1 )
        goto LABEL_19;
      goto LABEL_7;
    }
  }
  if ( a3->vt == 20 || a3->vt == 21 )
  {
    if ( a2 != 3 )
      goto LABEL_19;
    v6 = ConvertRationalUI8ToXMP(a3);
LABEL_15:
    v4 = v6;
    if ( v6 >= 0 )
      goto LABEL_19;
    goto LABEL_16;
  }
  if ( a3->vt == 31 )
  {
    if ( a2 != 10 )
      goto LABEL_19;
    v6 = ConvertRationalText(a3, 0, 0, 0, &pvarDest, 0);
    goto LABEL_23;
  }
LABEL_9:
  v4 = -2147024809;
  if ( g_doStackCaptures )
  {
    v5 = -2147024809;
LABEL_18:
    DoStackCapture(v5);
  }
LABEL_19:
  PropVariantClear(&pvar);
  PropVariantClear(&v10);
  PropVariantClear(&v11);
  PropVariantClear(&pvarDest);
  return v4;
}

```

## disassembly

```asm
0x180012440  mov     [rsp-8+arg_0], rbx
0x180012445  mov     [rsp-8+arg_8], rdi
0x18001244a  push    rbp
0x18001244b  lea     rbp, [rsp-57h]
0x180012450  sub     rsp, 90h
0x180012457  mov     rdi, r8
0x18001245a  mov     r8d, edx
0x18001245d  xor     ebx, ebx
0x18001245f  xorps   xmm0, xmm0
0x180012462  xor     eax, eax
0x180012464  movups  xmmword ptr [rbp+57h+pvarDest], xmm0
0x180012468  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x18001246c  movups  xmmword ptr [rbp+57h+var_18], xmm0
0x180012470  mov     qword ptr [rbp+57h+var_18+10h], rax
0x180012474  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x180012478  mov     qword ptr [rbp+57h+var_30+10h], rax
0x18001247c  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180012480  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180012484  mov     rcx, [rcx+20h]
0x180012488  mov     edx, [rcx+18h]
0x18001248b  sub     edx, 2
0x18001248e  jz      loc_1800125BA
0x180012494  sub     edx, 1
0x180012497  jz      loc_1800125BA
0x18001249d  sub     edx, 2
0x1800124a0  jz      short loc_1800124BA
0x1800124a2  sub     edx, 1
0x1800124a5  jz      short loc_1800124BA
0x1800124a7  sub     edx, 1
0x1800124aa  jz      loc_1800125BA
0x1800124b0  sub     edx, 1
0x1800124b3  jz      short loc_1800124BA
0x1800124b5  cmp     edx, 1
0x1800124b8  jnz     short loc_18001251A
0x1800124ba  movzx   ecx, word ptr [rdi]
0x1800124bd  sub     ecx, 1Fh
0x1800124c0  jz      loc_18001255C
0x1800124c6  sub     ecx, 0FF5h
0x1800124cc  jz      short loc_1800124E5
0x1800124ce  cmp     ecx, 1
0x1800124d1  jz      short loc_1800124E5
0x1800124d3  mov     ebx, 80070057h
0x1800124d8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800124df  jz      short loc_18001251A
0x1800124e1  mov     ecx, ebx
0x1800124e3  jmp     short loc_180012514
0x1800124e5  cmp     r8d, 3
0x1800124e9  jnz     short loc_1800124F5
0x1800124eb  mov     rcx, rdi; pvar
0x1800124ee  call    ?ConvertGpsCoordUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertGpsCoordUI8ToXMP(tagPROPVARIANT *)
0x1800124f3  jmp     short loc_180012503
0x1800124f5  cmp     dword ptr [rdi+8], 4
0x1800124f9  jnz     short loc_18001251A
0x1800124fb  mov     rcx, rdi; pvarDest
0x1800124fe  call    ?StripGPSCoordinateReferenceDataFromGPSCoordVector@@YAJPEAUtagPROPVARIANT@@@Z; StripGPSCoordinateReferenceDataFromGPSCoordVector(tagPROPVARIANT *)
0x180012503  mov     ebx, eax
0x180012505  test    eax, eax
0x180012507  jns     short loc_18001251A
0x180012509  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012510  jz      short loc_18001251A
0x180012512  mov     ecx, eax; int
0x180012514  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012519  nop
0x18001251a  lea     rcx, [rbp+57h+pvar]; pvar
0x18001251e  call    cs:__imp_PropVariantClear
0x180012524  nop
0x180012525  lea     rcx, [rbp+57h+var_30]; pvar
0x180012529  call    cs:__imp_PropVariantClear
0x18001252f  nop
0x180012530  lea     rcx, [rbp+57h+var_18]; pvar
0x180012534  call    cs:__imp_PropVariantClear
0x18001253a  nop
0x18001253b  lea     rcx, [rbp+57h+pvarDest]; pvar
0x18001253f  call    cs:__imp_PropVariantClear
0x180012545  mov     eax, ebx
0x180012547  lea     r11, [rsp+90h+var_s0]
0x18001254f  mov     rbx, [r11+10h]
0x180012553  mov     rdi, [r11+18h]
0x180012557  mov     rsp, r11
0x18001255a  pop     rbp
0x18001255b  retn
0x18001255c  cmp     r8d, 0Ah
0x180012560  jnz     short loc_18001251A
0x180012562  lea     rax, [rbp+57h+pvarDest]
0x180012566  mov     [rsp+90h+var_70], rax; PROPVARIANT *
0x18001256b  lea     r9, [rbp+57h+pvar]; PROPVARIANT *
0x18001256f  lea     r8, [rbp+57h+var_30]; PROPVARIANT *
0x180012573  lea     rdx, [rbp+57h+var_18]; pvar
0x180012577  mov     rcx, rdi; pvarSrc
0x18001257a  call    ?ConvertGPSCoordinateTextToVector@@YAJPEBUtagPROPVARIANT@@PEAU1@111@Z; ConvertGPSCoordinateTextToVector(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x18001257f  mov     ebx, eax
0x180012581  test    eax, eax
0x180012583  js      short loc_180012509
0x180012585  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x180012589  call    ?StripGPSCoordinateReferenceDataFromGPSCoordVector@@YAJPEAUtagPROPVARIANT@@@Z; StripGPSCoordinateReferenceDataFromGPSCoordVector(tagPROPVARIANT *)
0x18001258e  test    eax, eax
0x180012590  mov     ebx, eax
0x180012592  jns     short loc_1800125A9
0x180012594  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001259b  jnz     loc_180012512
0x1800125a1  test    eax, eax
0x1800125a3  js      loc_18001251A
0x1800125a9  lea     rdx, [rbp+57h+pvarDest]; struct tagPROPVARIANT *
0x1800125ad  mov     rcx, rdi; struct tagPROPVARIANT *
0x1800125b0  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x1800125b5  jmp     loc_18001251A
0x1800125ba  movzx   ecx, word ptr [rdi]
0x1800125bd  sub     ecx, 14h
0x1800125c0  jz      short loc_1800125F9
0x1800125c2  sub     ecx, 1
0x1800125c5  jz      short loc_1800125F9
0x1800125c7  cmp     ecx, 0Ah
0x1800125ca  jnz     loc_1800124D3
0x1800125d0  cmp     r8d, ecx
0x1800125d3  jnz     loc_18001251A
0x1800125d9  mov     [rsp+90h+var_68], 0; bool
0x1800125de  lea     rax, [rbp+57h+pvarDest]
0x1800125e2  mov     [rsp+90h+var_70], rax; struct tagPROPVARIANT *
0x1800125e7  xor     r9d, r9d; struct tagPROPVARIANT *
0x1800125ea  xor     r8d, r8d; struct tagPROPVARIANT *
0x1800125ed  xor     edx, edx; struct tagPROPVARIANT *
0x1800125ef  mov     rcx, rdi; struct tagPROPVARIANT *
0x1800125f2  call    ?ConvertRationalText@@YAJPEBUtagPROPVARIANT@@PEAU1@111_N@Z; ConvertRationalText(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,bool)
0x1800125f7  jmp     short loc_18001258E
0x1800125f9  cmp     r8d, 3
0x1800125fd  jnz     loc_18001251A
0x180012603  mov     rcx, rdi; pvar
0x180012606  call    ?ConvertRationalUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertRationalUI8ToXMP(tagPROPVARIANT *)
0x18001260b  jmp     loc_180012503
```
