# CIntegerRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)

- ea: `0x18000ac10`
- end: `0x18000b0f2`
- name: `?ConvertDataFormatOnRead@CIntegerRuleReader@@UEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `1250`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000ac10`
- `0x18000b0f8`
- `0x18000b26c`
- `0x1800132dc`
- `0x18001f284`
- `0x18001f4b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000b046`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000b068`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000b046`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000b068`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000b002`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000b027`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000b002`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000b027`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18000ad16`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18000ad16`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000aceb`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000aee6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000afb5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000aceb`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000aee6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000afb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ad04`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ad88`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000adb6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ae83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000aed3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000afce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b085`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b0b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ad04`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ad88`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000adb6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ae83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000aed3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000afce`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b085`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b0b3`
- `PROPSYS!PropVariantChangeType` at `0x18000ad5e`
- `PROPSYS!PropVariantChangeType` at `0x18000ad5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIntegerRuleReader::ConvertDataFormatOnRead(__int64 a1, int a2, PROPVARIANT *a3)
{
  HRESULT v5; // ebx
  VARTYPE v6; // r9
  int vt; // eax
  __int64 v8; // rdx
  int v10; // r8d
  int v11; // r14d
  double v12; // xmm0_8
  double v13; // xmm1_8
  HRESULT v14; // eax
  double v15; // xmm1_8
  int v16; // eax
  SHORT v17; // ax
  PROPVARIANT pvarDest; // [rsp+30h] [rbp-20h] BYREF

  if ( a2 == 13 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v14 = ConstructIntegerPropvarFromXMPSeq(a3, *(_WORD *)(*(_QWORD *)(a1 + 32) + 52LL), &pvarDest);
    v5 = v14;
    if ( v14 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_35;
      goto LABEL_34;
    }
    PropVariantClear(a3);
    *a3 = pvarDest;
    memset(&pvarDest, 0, sizeof(pvarDest));
  }
  else if ( a2 == 16 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v14 = ConstructExifFlashValueFromXMPFlash(a3, &pvarDest.bVal);
    v5 = v14;
    if ( v14 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_35;
      goto LABEL_34;
    }
    pvarDest.vt = 17;
    PropVariantClear(a3);
    v14 = PropVariantCopy(a3, &pvarDest);
    v5 = v14;
    if ( v14 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_35;
      goto LABEL_34;
    }
  }
  else
  {
    if ( a3->vt == 19 )
    {
LABEL_4:
      v5 = 0;
      goto LABEL_9;
    }
    v5 = -2147418113;
    v11 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 52LL);
    switch ( a3->vt )
    {
      case 2u:
      case 3u:
      case 0x10u:
      case 0x11u:
      case 0x12u:
        goto LABEL_4;
      case 0x1Eu:
        memset(&pvarDest, 0, sizeof(pvarDest));
        v5 = PropVariantCopy(&pvarDest, a3);
        if ( v5 < 0 )
          goto LABEL_6;
        PropVariantClear(a3);
        switch ( v11 )
        {
          case 2:
            a3->vt = 2;
            v17 = strtol(pvarDest.pszVal, 0, 10);
            break;
          case 3:
            a3->vt = 3;
            a3->lVal = strtol(pvarDest.pszVal, 0, 10);
            goto LABEL_62;
          case 19:
            a3->vt = 19;
            a3->lVal = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))_o_strtoul)(
                         (LARGE_INTEGER)pvarDest.hVal.QuadPart,
                         0,
                         10);
            goto LABEL_62;
          default:
            a3->vt = 18;
            v17 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))_o_strtoul)(
                    (LARGE_INTEGER)pvarDest.hVal.QuadPart,
                    0,
                    10);
            break;
        }
        a3->iVal = v17;
        break;
      case 0x1Fu:
        memset(&pvarDest, 0, sizeof(pvarDest));
        v5 = PropVariantCopy(&pvarDest, a3);
        if ( v5 < 0 )
          goto LABEL_6;
        PropVariantClear(a3);
        v12 = ((double (__fastcall *)(_QWORD, _QWORD))_o_wcstod)((LARGE_INTEGER)pvarDest.hVal.QuadPart, 0);
        if ( v12 > 0.0 )
          v13 = DOUBLE_0_5;
        else
          v13 = DOUBLE_N0_5;
        v15 = v13 + v12;
        switch ( v11 )
        {
          case 3:
            a3->vt = 3;
            v16 = (int)v15;
LABEL_27:
            a3->lVal = v16;
            goto LABEL_62;
          case 2:
            a3->vt = 2;
            a3->iVal = (int)v15;
            break;
          case 19:
            a3->vt = 19;
            v16 = (int)fmax(0.0, v15);
            goto LABEL_27;
          default:
            a3->vt = 18;
            a3->iVal = (int)fmax(0.0, v15);
            break;
        }
        break;
      default:
LABEL_6:
        if ( g_doStackCaptures )
          DoStackCapture(v5);
        return (unsigned int)v5;
    }
  }
LABEL_62:
  PropVariantClear(&pvarDest);
LABEL_9:
  v6 = *(_WORD *)(*(_QWORD *)(a1 + 32) + 52LL);
  vt = a3->vt;
  if ( (_WORD)vt == v6 )
    goto LABEL_10;
  if ( vt == 3 || vt == 2 || vt == 16 || vt == 17 || (unsigned int)(vt - 18) < 2 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v14 = PropVariantChangeType(&pvarDest, a3, 0, v6);
    v5 = v14;
    if ( v14 >= 0 )
    {
      PropVariantClear(a3);
      *a3 = pvarDest;
      memset(&pvarDest, 0, sizeof(pvarDest));
      PropVariantClear(&pvarDest);
LABEL_10:
      v8 = *(_QWORD *)(a1 + 32);
      if ( *(_DWORD *)(v8 + 12) )
      {
        v10 = *(_DWORD *)(v8 + 48);
        if ( *(_DWORD *)(v8 + 16) )
          return (unsigned int)ClipToRange(a3, *(_DWORD *)(v8 + 44), v10, *(_WORD *)(v8 + 52), 0);
        else
          return (unsigned int)CheckRange(a3, *(_DWORD *)(v8 + 44), v10);
      }
      return (unsigned int)v5;
    }
    if ( !g_doStackCaptures )
      goto LABEL_35;
LABEL_34:
    DoStackCapture(v14);
LABEL_35:
    PropVariantClear(&pvarDest);
    return (unsigned int)v5;
  }
  v5 = -2003292274;
  if ( !g_doStackCaptures )
    return (unsigned int)v5;
  DoStackCapture(-2003292274);
  return 2291675022LL;
}

```

## disassembly

```asm
0x18000ac10  push    rbp
0x18000ac12  push    rbx
0x18000ac13  push    rsi
0x18000ac14  push    rdi
0x18000ac15  push    r14
0x18000ac17  mov     rbp, rsp
0x18000ac1a  sub     rsp, 50h
0x18000ac1e  mov     rdi, r8
0x18000ac21  mov     rsi, rcx
0x18000ac24  cmp     edx, 0Dh
0x18000ac27  jz      loc_18000AF12
0x18000ac2d  cmp     edx, 10h
0x18000ac30  jz      loc_18000AE9D
0x18000ac36  movzx   eax, word ptr [r8]
0x18000ac3a  cmp     eax, 13h
0x18000ac3d  jnz     short loc_18000AC43
0x18000ac3f  xor     ebx, ebx; jumptable 000000018000ACD1 cases 2,3,16-18
0x18000ac41  jmp     short loc_18000AC61
0x18000ac43  mov     ebx, 8000FFFFh
0x18000ac48  lea     ecx, [rax-2]; switch 30 cases
0x18000ac4b  cmp     ecx, 1Dh
0x18000ac4e  jbe     short loc_18000ACAC
0x18000ac50  cmp     cs:?g_doStackCaptures@@3HA, 0; jumptable 000000018000ACD1 default case, cases 4-15,19-29
0x18000ac57  jnz     loc_18000AE0D
0x18000ac5d  test    ebx, ebx
0x18000ac5f  js      short loc_18000AC81
0x18000ac61  mov     rax, [rsi+20h]
0x18000ac65  movzx   r9d, word ptr [rax+34h]; vt
0x18000ac6a  movzx   eax, word ptr [rdi]
0x18000ac6d  cmp     ax, r9w
0x18000ac71  jnz     loc_18000AD3C
0x18000ac77  mov     rdx, [rsi+20h]
0x18000ac7b  cmp     dword ptr [rdx+0Ch], 0
0x18000ac7f  jnz     short loc_18000AC8F
0x18000ac81  mov     eax, ebx
0x18000ac83  add     rsp, 50h
0x18000ac87  pop     r14
0x18000ac89  pop     rdi
0x18000ac8a  pop     rsi
0x18000ac8b  pop     rbx
0x18000ac8c  pop     rbp
0x18000ac8d  retn
0x18000ac8f  mov     r8d, [rdx+30h]; int
0x18000ac93  mov     rcx, rdi; pvarDest
0x18000ac96  cmp     dword ptr [rdx+10h], 0
0x18000ac9a  jnz     loc_18000ADC7
0x18000aca0  mov     edx, [rdx+2Ch]; int
0x18000aca3  call    ?CheckRange@@YAJPEBUtagPROPVARIANT@@HH@Z; CheckRange(tagPROPVARIANT const *,int,int)
0x18000aca8  mov     ebx, eax
0x18000acaa  jmp     short loc_18000AC81
0x18000acac  mov     rax, [rsi+20h]
0x18000acb0  movzx   r14d, word ptr [rax+34h]
0x18000acb5  movsxd  rax, ecx
0x18000acb8  lea     rdx, __ImageBase
0x18000acbf  movzx   eax, ds:(byte_18000B0D4 - 180000000h)[rdx+rax]
0x18000acc7  mov     ecx, ds:(jpt_18000ACD1 - 180000000h)[rdx+rax*4]
0x18000acce  add     rcx, rdx
0x18000acd1  jmp     rcx; switch jump
0x18000acd7  xorps   xmm0, xmm0; jumptable 000000018000ACD1 case 31
0x18000acda  xor     eax, eax
0x18000acdc  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000ace0  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000ace4  mov     rdx, rdi; pvarSrc
0x18000ace7  lea     rcx, [rbp+pvarDest]; pvarDest
0x18000aceb  call    cs:__imp_PropVariantCopy
0x18000acf2  nop     dword ptr [rax+rax+00h]
0x18000acf7  mov     ebx, eax
0x18000acf9  test    eax, eax
0x18000acfb  js      def_18000ACD1; jumptable 000000018000ACD1 default case, cases 4-15,19-29
0x18000ad01  mov     rcx, rdi; pvar
0x18000ad04  call    cs:__imp_PropVariantClear
0x18000ad0b  nop     dword ptr [rax+rax+00h]
0x18000ad10  xor     edx, edx
0x18000ad12  mov     rcx, qword ptr [rbp+pvarDest+8]
0x18000ad16  call    cs:__imp__o_wcstod
0x18000ad1d  nop     dword ptr [rax+rax+00h]
0x18000ad22  xorps   xmm2, xmm2
0x18000ad25  comisd  xmm0, xmm2
0x18000ad29  ja      loc_18000ADE4
0x18000ad2f  movsd   xmm1, cs:__real@bfe0000000000000
0x18000ad37  jmp     loc_18000ADEC
0x18000ad3c  mov     ecx, eax
0x18000ad3e  cmp     eax, 3
0x18000ad41  jnz     loc_18000AE19
0x18000ad47  xorps   xmm0, xmm0
0x18000ad4a  xor     eax, eax
0x18000ad4c  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000ad50  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000ad54  xor     r8d, r8d; flags
0x18000ad57  mov     rdx, rdi; propvarSrc
0x18000ad5a  lea     rcx, [rbp+pvarDest]; ppropvarDest
0x18000ad5e  call    cs:__imp_PropVariantChangeType
0x18000ad65  nop     dword ptr [rax+rax+00h]
0x18000ad6a  mov     ebx, eax
0x18000ad6c  test    eax, eax
0x18000ad6e  jns     short loc_18000AD85
0x18000ad70  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000ad77  jnz     loc_18000AE6D
0x18000ad7d  test    eax, eax
0x18000ad7f  js      loc_18000AE75
0x18000ad85  mov     rcx, rdi; pvar
0x18000ad88  call    cs:__imp_PropVariantClear
0x18000ad8f  nop     dword ptr [rax+rax+00h]
0x18000ad94  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x18000ad98  movups  xmmword ptr [rdi], xmm0
0x18000ad9b  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x18000ada0  movsd   qword ptr [rdi+10h], xmm1
0x18000ada5  xorps   xmm0, xmm0
0x18000ada8  xor     eax, eax
0x18000adaa  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000adae  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000adb2  lea     rcx, [rbp+pvarDest]; pvar
0x18000adb6  call    cs:__imp_PropVariantClear
0x18000adbd  nop     dword ptr [rax+rax+00h]
0x18000adc2  jmp     loc_18000AC77
0x18000adc7  mov     [rsp+50h+var_30], 0; bool *
0x18000add0  movzx   r9d, word ptr [rdx+34h]; unsigned __int16
0x18000add5  mov     edx, [rdx+2Ch]; int
0x18000add8  call    ?ClipToRange@@YAJPEAUtagPROPVARIANT@@HHGPEA_N@Z; ClipToRange(tagPROPVARIANT *,int,int,ushort,bool *)
0x18000addd  mov     ebx, eax
0x18000addf  jmp     loc_18000AC81
0x18000ade4  movsd   xmm1, cs:__real@3fe0000000000000
0x18000adec  addsd   xmm1, xmm0
0x18000adf0  mov     ecx, r14d
0x18000adf3  cmp     r14d, 3
0x18000adf7  jnz     loc_18000AF57
0x18000adfd  mov     [rdi], r14w
0x18000ae01  cvttsd2si eax, xmm1
0x18000ae05  mov     [rdi+8], eax
0x18000ae08  jmp     loc_18000B0AF
0x18000ae0d  mov     ecx, ebx; int
0x18000ae0f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ae14  jmp     loc_18000AC5D
0x18000ae19  sub     ecx, 2
0x18000ae1c  jz      loc_18000AD47
0x18000ae22  sub     ecx, 0Eh
0x18000ae25  jz      loc_18000AD47
0x18000ae2b  sub     ecx, 1
0x18000ae2e  jz      loc_18000AD47
0x18000ae34  sub     ecx, 1
0x18000ae37  jz      loc_18000AD47
0x18000ae3d  cmp     ecx, 1
0x18000ae40  jz      loc_18000AD47
0x18000ae46  mov     ebx, 88982F8Eh
0x18000ae4b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000ae52  jz      loc_18000AC81
0x18000ae58  mov     ecx, ebx; int
0x18000ae5a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ae5f  mov     eax, ebx
0x18000ae61  add     rsp, 50h
0x18000ae65  pop     r14
0x18000ae67  pop     rdi
0x18000ae68  pop     rsi
0x18000ae69  pop     rbx
0x18000ae6a  pop     rbp
0x18000ae6b  retn
0x18000ae6d  mov     ecx, eax; int
0x18000ae6f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ae74  nop
0x18000ae75  jmp     short loc_18000AE7F
0x18000ae77  mov     ecx, eax; int
0x18000ae79  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ae7e  nop
0x18000ae7f  lea     rcx, [rbp+pvarDest]; pvar
0x18000ae83  call    cs:__imp_PropVariantClear
0x18000ae8a  nop     dword ptr [rax+rax+00h]
0x18000ae8f  mov     eax, ebx
0x18000ae91  add     rsp, 50h
0x18000ae95  pop     r14
0x18000ae97  pop     rdi
0x18000ae98  pop     rsi
0x18000ae99  pop     rbx
0x18000ae9a  pop     rbp
0x18000ae9b  retn
0x18000ae9d  xorps   xmm0, xmm0
0x18000aea0  xor     eax, eax
0x18000aea2  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000aea6  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000aeaa  lea     rdx, [rbp+pvarDest+8]; unsigned __int8 *
0x18000aeae  mov     rcx, rdi; struct tagPROPVARIANT *
0x18000aeb1  call    ?ConstructExifFlashValueFromXMPFlash@@YAJPEBUtagPROPVARIANT@@PEAE@Z; ConstructExifFlashValueFromXMPFlash(tagPROPVARIANT const *,uchar *)
0x18000aeb6  mov     ebx, eax
0x18000aeb8  test    eax, eax
0x18000aeba  jns     short loc_18000AEC7
0x18000aebc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000aec3  jz      short loc_18000AE7F
0x18000aec5  jmp     short loc_18000AE77
0x18000aec7  mov     eax, 11h
0x18000aecc  mov     word ptr [rbp+pvarDest], ax
0x18000aed0  mov     rcx, rdi; pvar
0x18000aed3  call    cs:__imp_PropVariantClear
0x18000aeda  nop     dword ptr [rax+rax+00h]
0x18000aedf  lea     rdx, [rbp+pvarDest]; pvarSrc
0x18000aee3  mov     rcx, rdi; pvarDest
0x18000aee6  call    cs:__imp_PropVariantCopy
0x18000aeed  nop     dword ptr [rax+rax+00h]
0x18000aef2  mov     ebx, eax
0x18000aef4  test    eax, eax
0x18000aef6  jns     short loc_18000AF0D
0x18000aef8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000aeff  jnz     loc_18000AE77
0x18000af05  test    eax, eax
0x18000af07  js      loc_18000AE7F
0x18000af0d  jmp     loc_18000B0AF
0x18000af12  xorps   xmm0, xmm0
0x18000af15  xor     eax, eax
0x18000af17  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000af1b  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000af1f  mov     rdx, [rcx+20h]
0x18000af23  lea     r8, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18000af27  movzx   edx, word ptr [rdx+34h]; unsigned __int16
0x18000af2b  mov     rcx, rdi; struct tagPROPVARIANT *
0x18000af2e  call    ?ConstructIntegerPropvarFromXMPSeq@@YAJPEBUtagPROPVARIANT@@GPEAU1@@Z; ConstructIntegerPropvarFromXMPSeq(tagPROPVARIANT const *,ushort,tagPROPVARIANT *)
0x18000af33  mov     ebx, eax
0x18000af35  test    eax, eax
0x18000af37  jns     loc_18000B082
0x18000af3d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000af44  jz      loc_18000B07A
0x18000af4a  mov     ecx, eax; int
0x18000af4c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000af51  nop
0x18000af52  jmp     loc_18000AE7F
0x18000af57  sub     ecx, 2
0x18000af5a  jz      short loc_18000AF8F
0x18000af5c  sub     ecx, 10h
0x18000af5f  jz      short loc_18000AF79
0x18000af61  cmp     ecx, 1
0x18000af64  jnz     short loc_18000AF79
0x18000af66  mov     word ptr [rdi], 13h
0x18000af6b  maxsd   xmm2, xmm1
0x18000af6f  cvttsd2si rax, xmm2
0x18000af74  jmp     loc_18000AE05
0x18000af79  mov     word ptr [rdi], 12h
0x18000af7e  maxsd   xmm2, xmm1
0x18000af82  cvttsd2si eax, xmm2
0x18000af86  mov     [rdi+8], ax
0x18000af8a  jmp     loc_18000B0AF
0x18000af8f  mov     word ptr [rdi], 2
0x18000af94  cvttsd2si eax, xmm1
0x18000af98  mov     [rdi+8], ax
0x18000af9c  jmp     loc_18000B0AF
0x18000afa1  xorps   xmm0, xmm0; jumptable 000000018000ACD1 case 30
0x18000afa4  xor     eax, eax
0x18000afa6  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000afaa  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000afae  mov     rdx, rdi; pvarSrc
0x18000afb1  lea     rcx, [rbp+pvarDest]; pvarDest
0x18000afb5  call    cs:__imp_PropVariantCopy
0x18000afbc  nop     dword ptr [rax+rax+00h]
0x18000afc1  mov     ebx, eax
0x18000afc3  test    eax, eax
0x18000afc5  js      def_18000ACD1; jumptable 000000018000ACD1 default case, cases 4-15,19-29
0x18000afcb  mov     rcx, rdi; pvar
0x18000afce  call    cs:__imp_PropVariantClear
0x18000afd5  nop     dword ptr [rax+rax+00h]
0x18000afda  mov     ecx, r14d
0x18000afdd  sub     ecx, 2
0x18000afe0  jz      short loc_18000B057
0x18000afe2  sub     ecx, 1
0x18000afe5  jz      short loc_18000B035
0x18000afe7  sub     ecx, 0Fh
0x18000afea  jz      short loc_18000B016
0x18000afec  cmp     ecx, 1
0x18000afef  jnz     short loc_18000B016
0x18000aff1  mov     word ptr [rdi], 13h
0x18000aff6  xor     edx, edx
0x18000aff8  mov     r8d, 0Ah
0x18000affe  mov     rcx, qword ptr [rbp+pvarDest+8]
0x18000b002  call    cs:__imp__o_strtoul
0x18000b009  nop     dword ptr [rax+rax+00h]
0x18000b00e  mov     [rdi+8], eax
0x18000b011  jmp     loc_18000B0AF
0x18000b016  mov     word ptr [rdi], 12h
0x18000b01b  xor     edx, edx
0x18000b01d  mov     r8d, 0Ah
0x18000b023  mov     rcx, qword ptr [rbp+pvarDest+8]
0x18000b027  call    cs:__imp__o_strtoul
0x18000b02e  nop     dword ptr [rax+rax+00h]
0x18000b033  jmp     short loc_18000B074
0x18000b035  mov     word ptr [rdi], 3
0x18000b03a  xor     edx, edx; EndPtr
0x18000b03c  mov     r8d, 0Ah; Radix
0x18000b042  mov     rcx, qword ptr [rbp+pvarDest+8]; String
0x18000b046  call    cs:__imp_strtol
0x18000b04d  nop     dword ptr [rax+rax+00h]
0x18000b052  mov     [rdi+8], eax
0x18000b055  jmp     short loc_18000B0AF
0x18000b057  mov     word ptr [rdi], 2
0x18000b05c  xor     edx, edx; EndPtr
0x18000b05e  mov     r8d, 0Ah; Radix
0x18000b064  mov     rcx, qword ptr [rbp+pvarDest+8]; String
0x18000b068  call    cs:__imp_strtol
0x18000b06f  nop     dword ptr [rax+rax+00h]
0x18000b074  mov     [rdi+8], ax
0x18000b078  jmp     short loc_18000B0AF
0x18000b07a  test    eax, eax
0x18000b07c  js      loc_18000AF52
0x18000b082  mov     rcx, rdi; pvar
0x18000b085  call    cs:__imp_PropVariantClear
0x18000b08c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
