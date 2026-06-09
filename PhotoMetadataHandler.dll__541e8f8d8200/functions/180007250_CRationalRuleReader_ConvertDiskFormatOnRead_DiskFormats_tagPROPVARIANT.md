# CRationalRuleReader::ConvertDiskFormatOnRead(DiskFormats,tagPROPVARIANT *)

- ea: `0x180007250`
- end: `0x1800074d0`
- name: `?ConvertDiskFormatOnRead@CRationalRuleReader@@UEAAJW4DiskFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `640`
- prototype: `int __high(enum DiskFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180006da4`
- `0x180007250`
- `0x1800074e0`
- `0x180008de0`
- `0x180009010`
- `0x18000e90c`
- `0x180011f44`
- `0x1800129d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800072e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800072f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800072fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007306`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007311`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800072e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800072f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800072fb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007306`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007311`

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
0x180007250  push    rbp
0x180007252  push    rbx
0x180007253  push    rsi
0x180007254  push    rdi
0x180007255  push    r14
0x180007257  lea     rbp, [rsp-37h]
0x18000725c  sub     rsp, 0B0h
0x180007263  mov     rsi, r8
0x180007266  mov     rdi, rcx
0x180007269  xor     ebx, ebx
0x18000726b  xorps   xmm0, xmm0
0x18000726e  xor     eax, eax
0x180007270  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180007274  mov     qword ptr [rbp+57h+var_40+10h], rax
0x180007278  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18000727c  mov     qword ptr [rbp+57h+var_58+10h], rax
0x180007280  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180007284  mov     qword ptr [rbp+57h+var_70+10h], rax
0x180007288  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18000728c  mov     qword ptr [rbp+57h+var_88+10h], rax
0x180007290  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180007294  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180007298  mov     rax, [rcx+20h]
0x18000729c  mov     ecx, [rax+18h]
0x18000729f  lea     r14, __ImageBase
0x1800072a6  cmp     ecx, 7
0x1800072a9  jnz     short loc_180007327
0x1800072ab  cmp     edx, 0Ah
0x1800072ae  jnz     short def_18000733C; jumptable 000000018000733C default case, case 7
0x1800072b0  mov     rcx, r8; pvar
0x1800072b3  call    ?ConvertRationalUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertRationalUI8ToXMP(tagPROPVARIANT *)
0x1800072b8  mov     ebx, eax
0x1800072ba  test    eax, eax
0x1800072bc  jns     short def_18000733C; jumptable 000000018000733C default case, case 7
0x1800072be  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800072c5  jnz     loc_180007396
0x1800072cb  test    eax, eax
0x1800072cd  js      short def_180007473; jumptable 0000000180007473 default case
0x1800072cf  mov     rax, [rdi+20h]; jumptable 000000018000733C default case, case 7
0x1800072d3  mov     ecx, [rax+18h]
0x1800072d6  dec     ecx; switch 6 cases
0x1800072d8  cmp     ecx, 5
0x1800072db  jbe     loc_180007465
0x1800072e1  lea     rcx, [rbp+57h+pvar]; jumptable 0000000180007473 default case
0x1800072e5  call    cs:__imp_PropVariantClear
0x1800072eb  nop
0x1800072ec  lea     rcx, [rbp+57h+var_88]; pvar
0x1800072f0  call    cs:__imp_PropVariantClear
0x1800072f6  nop
0x1800072f7  lea     rcx, [rbp+57h+var_70]; pvar
0x1800072fb  call    cs:__imp_PropVariantClear
0x180007301  nop
0x180007302  lea     rcx, [rbp+57h+var_58]; pvar
0x180007306  call    cs:__imp_PropVariantClear
0x18000730c  nop
0x18000730d  lea     rcx, [rbp+57h+var_40]; pvar
0x180007311  call    cs:__imp_PropVariantClear
0x180007317  mov     eax, ebx
0x180007319  add     rsp, 0B0h
0x180007320  pop     r14
0x180007322  pop     rdi
0x180007323  pop     rsi
0x180007324  pop     rbx
0x180007325  pop     rbp
0x180007326  retn
0x180007327  dec     ecx; switch 9 cases
0x180007329  cmp     ecx, 8
0x18000732c  ja      short def_18000733C; jumptable 000000018000733C default case, case 7
0x18000732e  movsxd  rax, ecx
0x180007331  mov     ecx, ds:(jpt_18000733C - 180000000h)[r14+rax*4]
0x180007339  add     rcx, r14
0x18000733c  jmp     rcx; switch jump
0x18000733e  cmp     edx, 0Ah; jumptable 000000018000733C case 8
0x180007341  jnz     short def_18000733C; jumptable 000000018000733C default case, case 7
0x180007343  mov     rcx, rsi; pvar
0x180007346  call    ?ConvertGpsCoordUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertGpsCoordUI8ToXMP(tagPROPVARIANT *)
0x18000734b  mov     ebx, eax
0x18000734d  test    eax, eax
0x18000734f  jns     def_18000733C; jumptable 000000018000733C default case, case 7
0x180007355  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000735c  jnz     short loc_18000736B
0x18000735e  test    eax, eax
0x180007360  js      def_180007473; jumptable 0000000180007473 default case
0x180007366  jmp     def_18000733C; jumptable 000000018000733C default case, case 7
0x18000736b  mov     ecx, eax; int
0x18000736d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007372  jmp     def_180007473; jumptable 0000000180007473 default case
0x180007377  mov     rcx, rsi; pvar
0x18000737a  call    ?ConvertGpsCoordUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertGpsCoordUI8ToXMP(tagPROPVARIANT *)
0x18000737f  mov     ebx, eax
0x180007381  test    eax, eax
0x180007383  jns     loc_180007435
0x180007389  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007390  jz      def_180007473; jumptable 0000000180007473 default case
0x180007396  mov     ecx, eax; int
0x180007398  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000739d  jmp     def_180007473; jumptable 0000000180007473 default case
0x1800073a2  mov     [rsp+0D0h+var_A8], 0; bool
0x1800073a7  lea     rax, [rbp+57h+var_58]
0x1800073ab  mov     [rsp+0D0h+var_B0], rax; struct tagPROPVARIANT *
0x1800073b0  lea     r9, [rbp+57h+var_70]; struct tagPROPVARIANT *
0x1800073b4  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x1800073b8  lea     rdx, [rbp+57h+var_88]; struct tagPROPVARIANT *
0x1800073bc  mov     rcx, rsi; struct tagPROPVARIANT *
0x1800073bf  call    ?ConvertRationalText@@YAJPEBUtagPROPVARIANT@@PEAU1@111_N@Z; ConvertRationalText(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,bool)
0x1800073c4  mov     ebx, eax
0x1800073c6  test    eax, eax
0x1800073c8  jns     def_18000733C; jumptable 000000018000733C default case, case 7
0x1800073ce  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800073d5  jnz     short loc_180007396
0x1800073d7  jmp     short loc_18000735E
0x1800073d9  lea     rdx, [rbp+57h+var_40]; struct tagPROPVARIANT *
0x1800073dd  mov     rcx, rsi; pvar
0x1800073e0  call    ?ExtractRefFromGPSCoord@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z; ExtractRefFromGPSCoord(tagPROPVARIANT *,tagPROPVARIANT const *)
0x1800073e5  mov     ebx, eax
0x1800073e7  test    eax, eax
0x1800073e9  jns     short loc_1800073FC
0x1800073eb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800073f2  jnz     short loc_180007396
0x1800073f4  test    eax, eax
0x1800073f6  js      def_180007473; jumptable 0000000180007473 default case
0x1800073fc  lea     rdx, [rbp+57h+var_40]; struct tagPROPVARIANT *
0x180007400  mov     rcx, rsi; struct tagPROPVARIANT *
0x180007403  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x180007408  jmp     def_18000733C; jumptable 000000018000733C default case, case 7
0x18000740d  mov     rcx, rsi; pvar
0x180007410  call    ?ConvertRationalUI8ToXMP@@YAJPEAUtagPROPVARIANT@@@Z; ConvertRationalUI8ToXMP(tagPROPVARIANT *)
0x180007415  mov     ebx, eax
0x180007417  test    eax, eax
0x180007419  js      loc_180007389
0x18000741f  jmp     short loc_1800073A2
0x180007421  cmp     edx, 0Ah; jumptable 000000018000733C cases 1-3
0x180007424  jnz     loc_1800073A2
0x18000742a  jmp     short loc_18000740D
0x18000742c  cmp     edx, 0Ah; jumptable 000000018000733C cases 4-6
0x18000742f  jz      loc_180007377
0x180007435  lea     rax, [rbp+57h+var_58]
0x180007439  mov     [rsp+0D0h+var_B0], rax; PROPVARIANT *
0x18000743e  lea     r9, [rbp+57h+var_70]; PROPVARIANT *
0x180007442  lea     r8, [rbp+57h+pvar]; PROPVARIANT *
0x180007446  lea     rdx, [rbp+57h+var_88]; pvar
0x18000744a  mov     rcx, rsi; pvarSrc
0x18000744d  call    ?ConvertGPSCoordinateTextToVector@@YAJPEBUtagPROPVARIANT@@PEAU1@111@Z; ConvertGPSCoordinateTextToVector(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180007452  jmp     loc_18000734B
0x180007457  cmp     edx, 3; jumptable 000000018000733C case 9
0x18000745a  jnz     def_18000733C; jumptable 000000018000733C default case, case 7
0x180007460  jmp     loc_1800073D9
0x180007465  movsxd  rax, ecx
0x180007468  mov     ecx, ds:(jpt_180007473 - 180000000h)[r14+rax*4]
0x180007470  add     rcx, r14
0x180007473  jmp     rcx; switch jump
0x180007475  lea     rdx, [rbp+57h+var_70]; jumptable 0000000180007473 cases 1,4
0x180007479  jmp     short loc_180007485
0x18000747b  lea     rdx, [rbp+57h+pvar]; jumptable 0000000180007473 cases 3,6
0x18000747f  jmp     short loc_180007485
0x180007481  lea     rdx, [rbp+57h+var_88]; jumptable 0000000180007473 cases 2,5
0x180007485  mov     rcx, rsi; struct tagPROPVARIANT *
0x180007488  call    ?TransferPropVariant@@YAXPEAUtagPROPVARIANT@@0@Z; TransferPropVariant(tagPROPVARIANT *,tagPROPVARIANT *)
0x18000748d  jmp     def_180007473; jumptable 0000000180007473 default case
```
