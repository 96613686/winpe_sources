# CRationalRuleReader::ConvertDiskFormatOnRead(DiskFormats,tagPROPVARIANT *)

- ea: `0x180008550`
- end: `0x180008800`
- name: `?ConvertDiskFormatOnRead@CRationalRuleReader@@UEAAJW4DiskFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `688`
- prototype: `int __high(enum DiskFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180008098`
- `0x180008550`
- `0x180008810`
- `0x180009140`
- `0x1800096f0`
- `0x18000f004`
- `0x1800127e4`
- `0x1800132dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800085e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800085fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000860b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000861c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000862d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800085e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800085fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000860b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000861c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000862d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRationalRuleReader::ConvertDiskFormatOnRead(__int64 a1, int a2, struct tagPROPVARIANT *a3)
{
  unsigned int v5; // ebx
  int v6; // ecx
  int v7; // eax
  PROPVARIANT *p_pvar; // rdx
  PROPVARIANT pvar; // [rsp+30h] [rbp-49h] BYREF
  PROPVARIANT v11; // [rsp+48h] [rbp-31h] BYREF
  PROPVARIANT v12; // [rsp+60h] [rbp-19h] BYREF
  PROPVARIANT v13; // [rsp+78h] [rbp-1h] BYREF
  PROPVARIANT v14; // [rsp+90h] [rbp+17h] BYREF

  v5 = 0;
  memset(&v14, 0, sizeof(v14));
  memset(&v13, 0, sizeof(v13));
  memset(&v12, 0, sizeof(v12));
  memset(&v11, 0, sizeof(v11));
  memset(&pvar, 0, sizeof(pvar));
  v6 = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL);
  if ( v6 == 7 )
  {
    if ( a2 == 10 && (v7 = ConvertRationalUI8ToXMP(a3), v5 = v7, v7 < 0) )
    {
      if ( g_doStackCaptures )
LABEL_16:
        DoStackCapture(v7);
    }
    else
    {
LABEL_32:
      switch ( *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL) )
      {
        case 1:
        case 4:
          p_pvar = &v12;
          goto LABEL_36;
        case 2:
        case 5:
          p_pvar = &v11;
          goto LABEL_36;
        case 3:
        case 6:
          p_pvar = &pvar;
LABEL_36:
          TransferPropVariant(a3, p_pvar);
          break;
        default:
          break;
      }
    }
  }
  else
  {
    switch ( v6 )
    {
      case 1:
      case 2:
      case 3:
        if ( a2 == 10 )
        {
          v7 = ConvertRationalUI8ToXMP(a3);
          v5 = v7;
          if ( v7 < 0 )
            goto LABEL_15;
        }
        v7 = ConvertRationalText(a3, &v11, &pvar, &v12, &v13, 0);
        v5 = v7;
        if ( v7 >= 0 )
          goto LABEL_32;
        if ( !g_doStackCaptures )
          break;
        goto LABEL_16;
      case 4:
      case 5:
      case 6:
        if ( a2 == 10 && (v7 = ConvertGpsCoordUI8ToXMP(a3), v5 = v7, v7 < 0) )
        {
LABEL_15:
          if ( !g_doStackCaptures )
            break;
        }
        else
        {
          v7 = ConvertGPSCoordinateTextToVector(a3, &v11, &pvar, &v12, &v13);
LABEL_11:
          v5 = v7;
          if ( v7 >= 0 )
            goto LABEL_32;
          if ( !g_doStackCaptures )
            break;
        }
        goto LABEL_16;
      case 8:
        if ( a2 != 10 )
          goto LABEL_32;
        v7 = ConvertGpsCoordUI8ToXMP(a3);
        goto LABEL_11;
      case 9:
        if ( a2 != 3 )
          goto LABEL_32;
        v7 = ExtractRefFromGPSCoord(a3, &v14);
        v5 = v7;
        if ( v7 >= 0 )
        {
          TransferPropVariant(a3, &v14);
          goto LABEL_32;
        }
        if ( g_doStackCaptures )
          goto LABEL_16;
        break;
      default:
        goto LABEL_32;
    }
  }
  PropVariantClear(&pvar);
  PropVariantClear(&v11);
  PropVariantClear(&v12);
  PropVariantClear(&v13);
  PropVariantClear(&v14);
  return v5;
}

```

## disassembly

```asm
0x180008550  push    rbp
0x180008552  push    rbx
0x180008553  push    rsi
0x180008554  push    rdi
0x180008555  push    r14
0x180008557  lea     rbp, [rsp-37h]
0x18000855c  sub     rsp, 0B0h
0x180008563  mov     rsi, r8
0x180008566  mov     rdi, rcx
0x180008569  xor     ebx, ebx
0x18000856b  xorps   xmm0, xmm0
0x18000856e  xor     eax, eax
0x180008570  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180008574  mov     qword ptr [rbp+57h+var_40+10h], rax
0x180008578  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18000857c  mov     qword ptr [rbp+57h+var_58+10h], rax
0x180008580  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180008584  mov     qword ptr [rbp+57h+var_70+10h], rax
0x180008588  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18000858c  mov     qword ptr [rbp+57h+var_88+10h], rax
0x180008590  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180008594  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180008598  mov     rax, [rcx+20h]
0x18000859c  mov     ecx, [rax+18h]
0x18000859f  lea     r14, __ImageBase
0x1800085a6  cmp     ecx, 7
0x1800085a9  jnz     loc_18000864A
0x1800085af  cmp     edx, 0Ah
0x1800085b2  jnz     short def_18000865F; jumptable 000000018000865F default case, case 7
0x1800085b4  mov     rcx, r8; pvar
0x1800085b7  call    ?ConvertRationalUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertRationalUI8ToXMP(tagPROPVARIANT *)
0x1800085bc  mov     ebx, eax
0x1800085be  test    eax, eax
0x1800085c0  jns     short def_18000865F; jumptable 000000018000865F default case, case 7
0x1800085c2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800085c9  jnz     loc_1800086C1
0x1800085cf  test    eax, eax
0x1800085d1  js      short def_18000879E; jumptable 000000018000879E default case
0x1800085d3  mov     rax, [rdi+20h]; jumptable 000000018000865F default case, case 7
0x1800085d7  mov     ecx, [rax+18h]
0x1800085da  dec     ecx; switch 6 cases
0x1800085dc  cmp     ecx, 5
0x1800085df  jbe     loc_180008790
0x1800085e5  lea     rcx, [rbp+57h+pvar]; jumptable 000000018000879E default case
0x1800085e9  call    cs:__imp_PropVariantClear
0x1800085f0  nop     dword ptr [rax+rax+00h]
0x1800085f5  nop
0x1800085f6  lea     rcx, [rbp+57h+var_88]; pvar
0x1800085fa  call    cs:__imp_PropVariantClear
0x180008601  nop     dword ptr [rax+rax+00h]
0x180008606  nop
0x180008607  lea     rcx, [rbp+57h+var_70]; pvar
0x18000860b  call    cs:__imp_PropVariantClear
0x180008612  nop     dword ptr [rax+rax+00h]
0x180008617  nop
0x180008618  lea     rcx, [rbp+57h+var_58]; pvar
0x18000861c  call    cs:__imp_PropVariantClear
0x180008623  nop     dword ptr [rax+rax+00h]
0x180008628  nop
0x180008629  lea     rcx, [rbp+57h+var_40]; pvar
0x18000862d  call    cs:__imp_PropVariantClear
0x180008634  nop     dword ptr [rax+rax+00h]
0x180008639  mov     eax, ebx
0x18000863b  add     rsp, 0B0h
0x180008642  pop     r14
0x180008644  pop     rdi
0x180008645  pop     rsi
0x180008646  pop     rbx
0x180008647  pop     rbp
0x180008648  retn
0x18000864a  dec     ecx; switch 9 cases
0x18000864c  cmp     ecx, 8
0x18000864f  ja      short def_18000865F; jumptable 000000018000865F default case, case 7
0x180008651  movsxd  rax, ecx
0x180008654  mov     ecx, ds:(jpt_18000865F - 180000000h)[r14+rax*4]
0x18000865c  add     rcx, r14
0x18000865f  jmp     rcx; switch jump
0x180008665  cmp     edx, 0Ah; jumptable 000000018000865F case 8
0x180008668  jnz     def_18000865F; jumptable 000000018000865F default case, case 7
0x18000866e  mov     rcx, rsi; pvar
0x180008671  call    ?ConvertGpsCoordUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertGpsCoordUI8ToXMP(tagPROPVARIANT *)
0x180008676  mov     ebx, eax
0x180008678  test    eax, eax
0x18000867a  jns     def_18000865F; jumptable 000000018000865F default case, case 7
0x180008680  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180008687  jnz     short loc_180008696
0x180008689  test    eax, eax
0x18000868b  js      def_18000879E; jumptable 000000018000879E default case
0x180008691  jmp     def_18000865F; jumptable 000000018000865F default case, case 7
0x180008696  mov     ecx, eax; int
0x180008698  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000869d  jmp     def_18000879E; jumptable 000000018000879E default case
0x1800086a2  mov     rcx, rsi; pvar
0x1800086a5  call    ?ConvertGpsCoordUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertGpsCoordUI8ToXMP(tagPROPVARIANT *)
0x1800086aa  mov     ebx, eax
0x1800086ac  test    eax, eax
0x1800086ae  jns     loc_180008760
0x1800086b4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800086bb  jz      def_18000879E; jumptable 000000018000879E default case
0x1800086c1  mov     ecx, eax; int
0x1800086c3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800086c8  jmp     def_18000879E; jumptable 000000018000879E default case
0x1800086cd  mov     [rsp+0D0h+var_A8], 0; bool
0x1800086d2  lea     rax, [rbp+57h+var_58]
0x1800086d6  mov     [rsp+0D0h+var_B0], rax; struct tagPROPVARIANT *
0x1800086db  lea     r9, [rbp+57h+var_70]; struct tagPROPVARIANT *
0x1800086df  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x1800086e3  lea     rdx, [rbp+57h+var_88]; struct tagPROPVARIANT *
0x1800086e7  mov     rcx, rsi; struct tagPROPVARIANT *
0x1800086ea  call    ?ConvertRationalText@@YAJPEBUtagPROPVARIANT@@PEAU1@111_N@Z; ConvertRationalText(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,bool)
0x1800086ef  mov     ebx, eax
0x1800086f1  test    eax, eax
0x1800086f3  jns     def_18000865F; jumptable 000000018000865F default case, case 7
0x1800086f9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180008700  jnz     short loc_1800086C1
0x180008702  jmp     short loc_180008689
0x180008704  lea     rdx, [rbp+57h+var_40]; struct tagPROPVARIANT *
0x180008708  mov     rcx, rsi; pvar
0x18000870b  call    ?ExtractRefFromGPSCoord@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; ExtractRefFromGPSCoord(tagPROPVARIANT *,tagPROPVARIANT const *)
0x180008710  mov     ebx, eax
0x180008712  test    eax, eax
0x180008714  jns     short loc_180008727
0x180008716  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000871d  jnz     short loc_1800086C1
0x18000871f  test    eax, eax
0x180008721  js      def_18000879E; jumptable 000000018000879E default case
0x180008727  lea     rdx, [rbp+57h+var_40]; struct tagPROPVARIANT *
0x18000872b  mov     rcx, rsi; struct tagPROPVARIANT *
0x18000872e  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x180008733  jmp     def_18000865F; jumptable 000000018000865F default case, case 7
0x180008738  mov     rcx, rsi; pvar
0x18000873b  call    ?ConvertRationalUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertRationalUI8ToXMP(tagPROPVARIANT *)
0x180008740  mov     ebx, eax
0x180008742  test    eax, eax
0x180008744  js      loc_1800086B4
0x18000874a  jmp     short loc_1800086CD
0x18000874c  cmp     edx, 0Ah; jumptable 000000018000865F cases 1-3
0x18000874f  jnz     loc_1800086CD
0x180008755  jmp     short loc_180008738
0x180008757  cmp     edx, 0Ah; jumptable 000000018000865F cases 4-6
0x18000875a  jz      loc_1800086A2
0x180008760  lea     rax, [rbp+57h+var_58]
0x180008764  mov     [rsp+0D0h+var_B0], rax; PROPVARIANT *
0x180008769  lea     r9, [rbp+57h+var_70]; PROPVARIANT *
0x18000876d  lea     r8, [rbp+57h+pvar]; PROPVARIANT *
0x180008771  lea     rdx, [rbp+57h+var_88]; pvar
0x180008775  mov     rcx, rsi; pvarSrc
0x180008778  call    ?ConvertGPSCoordinateTextToVector@@YAJPEBUtagPROPVARIANT@@PEAU1@111@Z; ConvertGPSCoordinateTextToVector(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x18000877d  jmp     loc_180008676
0x180008782  cmp     edx, 3; jumptable 000000018000865F case 9
0x180008785  jnz     def_18000865F; jumptable 000000018000865F default case, case 7
0x18000878b  jmp     loc_180008704
0x180008790  movsxd  rax, ecx
0x180008793  mov     ecx, ds:(jpt_18000879E - 180000000h)[r14+rax*4]
0x18000879b  add     rcx, r14
0x18000879e  jmp     rcx; switch jump
0x1800087a4  lea     rdx, [rbp+57h+var_70]; jumptable 000000018000879E cases 1,4
0x1800087a8  jmp     short loc_1800087B4
0x1800087aa  lea     rdx, [rbp+57h+pvar]; jumptable 000000018000879E cases 3,6
0x1800087ae  jmp     short loc_1800087B4
0x1800087b0  lea     rdx, [rbp+57h+var_88]; jumptable 000000018000879E cases 2,5
0x1800087b4  mov     rcx, rsi; struct tagPROPVARIANT *
0x1800087b7  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x1800087bc  jmp     def_18000879E; jumptable 000000018000879E default case
```
