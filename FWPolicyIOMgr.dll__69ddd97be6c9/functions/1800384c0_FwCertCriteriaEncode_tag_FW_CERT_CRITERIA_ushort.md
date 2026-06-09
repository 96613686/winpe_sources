# FwCertCriteriaEncode(_tag_FW_CERT_CRITERIA *,ushort * *)

- ea: `0x1800384c0`
- end: `0x1800389d0`
- name: `?FwCertCriteriaEncode@@YAJPEAU_tag_FW_CERT_CRITERIA@@PEAPEAG@Z`
- size: `1296`
- prototype: `__int64 __fastcall(struct _tag_FW_CERT_CRITERIA *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180039634`

## callees

- `0x1800042c4`
- `0x180009260`
- `0x18000cff0`
- `0x18000e010`
- `0x18001e9ac`
- `0x18001f650`
- `0x1800384c0`
- `0x1800389d8`
- `0x180038a7c`

## import_xrefs

- `fwbase!FwFree` at `0x18003897e`
- `fwbase!FwFree` at `0x180038994`
- `fwbase!FwFree` at `0x1800389a4`
- `fwbase!FwFree` at `0x18003897e`
- `fwbase!FwFree` at `0x180038994`
- `fwbase!FwFree` at `0x1800389a4`
- `fwbase!FwAlloc` at `0x1800385e4`
- `fwbase!FwAlloc` at `0x180038780`
- `fwbase!FwAlloc` at `0x1800385e4`
- `fwbase!FwAlloc` at `0x180038780`
- `fwbase!FwSizeTMultiply` at `0x180038745`
- `fwbase!FwSizeTMultiply` at `0x180038745`
- `fwbase!FwStringCopyAtoWAlloc` at `0x180038651`
- `fwbase!FwStringCopyAtoWAlloc` at `0x180038651`

## pseudocode

```c
__int64 __fastcall FwCertCriteriaEncode(struct _tag_FW_CERT_CRITERIA *a1, unsigned __int16 **a2)
{
  wchar_t *v2; // r13
  __int64 v3; // r14
  int v5; // ecx
  unsigned __int16 **v6; // r12
  __int64 v7; // rax
  __int64 v8; // r15
  int v9; // eax
  __int64 v10; // rsi
  int StringFieldSize; // ebx
  LPCOLESTR v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 i; // rsi
  unsigned __int64 v16; // rsi
  unsigned int v17; // ecx
  __int64 v18; // rbx
  __int64 j; // rsi
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int64 v22; // [rsp+58h] [rbp-18h] BYREF
  __int64 v23; // [rsp+60h] [rbp-10h] BYREF

  v2 = 0;
  v22 = (unsigned __int64)a2;
  v3 = 0;
  *a2 = 0;
  LODWORD(pszDest) = 0;
  v5 = *((_DWORD *)a1 + 1);
  v6 = a2;
  v23 = 0;
  if ( v5 == 1 )
  {
    v7 = 21;
  }
  else if ( v5 == 2 )
  {
    v7 = 23;
  }
  else
  {
    v7 = 14;
    if ( !v5 )
      v7 = 19;
  }
  v8 = v7 + 26;
  v9 = *((_DWORD *)a1 + 2);
  if ( v9 )
  {
    switch ( v9 )
    {
      case 1:
      case 2:
        v10 = 14;
        break;
      case 3:
        v10 = 17;
        break;
      case 4:
      case 5:
        v10 = 13;
        break;
      case 6:
        v10 = 12;
        break;
      default:
        v10 = 10;
        if ( v9 == 7 )
          v10 = 13;
        break;
    }
    StringFieldSize = FwRuleGetStringFieldSize(6u, *((const unsigned __int16 **)a1 + 2), (unsigned int *)&pszDest);
    if ( StringFieldSize < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_76;
      v13 = 10;
      goto LABEL_24;
    }
    v8 += v10 + (unsigned int)pszDest + 2;
  }
  if ( *((_DWORD *)a1 + 6) )
  {
    v3 = FwAlloc(8LL * *((unsigned int *)a1 + 6));
    if ( v3 )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= *((_DWORD *)a1 + 6) )
        {
          v6 = (unsigned __int16 **)v22;
          goto LABEL_44;
        }
        StringFieldSize = FwStringCopyAtoWAlloc(*(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * i), 0, v3 + 8 * i);
        if ( StringFieldSize < 0 )
          break;
        StringFieldSize = FwRuleGetStringFieldSize(
                            5u,
                            *(const unsigned __int16 **)(v3 + 8 * i),
                            (unsigned int *)&pszDest);
        if ( StringFieldSize < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v13 = 13;
            goto LABEL_24;
          }
          goto LABEL_76;
        }
        v8 += (unsigned int)pszDest;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 12;
        goto LABEL_24;
      }
      goto LABEL_76;
    }
    v14 = 2147942414LL;
    StringFieldSize = -2147024882;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
    {
LABEL_76:
      FwFree(v2);
      goto LABEL_77;
    }
    v13 = 11;
LABEL_31:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_3d77b55d25ee3bd4e60182d5f5bc697d_Traceguids, v14);
    goto LABEL_76;
  }
LABEL_44:
  StringFieldSize = FwRuleGetStringFieldSize(6u, *((const unsigned __int16 **)a1 + 5), (unsigned int *)&pszDest);
  if ( StringFieldSize < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_76;
    v13 = 14;
    goto LABEL_24;
  }
  v22 = ((*((_BYTE *)a1 + 2) & 1) != 0 ? 23LL : 1LL) + v8 + (unsigned int)pszDest;
  v16 = v22;
  StringFieldSize = FwSizeTMultiply(v22, 2, &v23);
  if ( StringFieldSize < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_76;
    v13 = 15;
LABEL_24:
    v14 = (unsigned int)StringFieldSize;
    goto LABEL_31;
  }
  v2 = (wchar_t *)FwAlloc(v23);
  if ( !v2 )
  {
    v14 = 2147942414LL;
    StringFieldSize = -2147024882;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_76;
    v13 = 16;
    goto LABEL_31;
  }
  v17 = *(unsigned __int16 *)a1;
  pszDest = v2;
  if ( (int)StringCchPrintfExW(v2, v16, &pszDest, &v22, 0x800u, L"v%d.%d%s", v17 >> 8, (unsigned __int8)v17, L"|") < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (int)FwCertCriteriaSerializeCriteriaType(pszDest, v22, &pszDest, &v22, a1) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)a1 + 2) )
  {
    if ( (int)FwCertCriteriaSerializeNameType(pszDest, v22, &pszDest, &v22, a1) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (int)FwRuleSerializeStringField(pszDest, v22, &pszDest, &v22, L"Name=", *((const unsigned __int16 **)a1 + 2)) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( *((_DWORD *)a1 + 6) )
  {
    v18 = 0;
    do
    {
      if ( (int)FwRuleSerializeStringField(
                  pszDest,
                  v22,
                  &pszDest,
                  &v22,
                  L"Eku=",
                  *(const unsigned __int16 **)(v3 + 8 * v18)) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v18 = (unsigned int)(v18 + 1);
    }
    while ( (unsigned int)v18 < *((_DWORD *)a1 + 6) );
  }
  if ( (int)FwRuleSerializeStringField(pszDest, v22, &pszDest, &v22, L"Hash=", *((const unsigned __int16 **)a1 + 5)) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  StringFieldSize = 0;
  if ( (*((_BYTE *)a1 + 2) & 1) != 0 )
  {
    StringFieldSize = StringCchPrintfExW(
                        pszDest,
                        v22,
                        &pszDest,
                        &v22,
                        0x800u,
                        L"%s%s%s",
                        L"FollowRenewal=",
                        L"TRUE",
                        L"|");
    if ( StringFieldSize < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  *v6 = v2;
  if ( StringFieldSize < 0 )
    goto LABEL_76;
LABEL_77:
  if ( v3 )
  {
    for ( j = 0; (unsigned int)j < *((_DWORD *)a1 + 6); j = (unsigned int)(j + 1) )
      FwFree(*(_QWORD *)(v3 + 8 * j));
    FwFree(v3);
  }
  return (unsigned int)StringFieldSize;
}

```

## disassembly

```asm
0x1800384c0  mov     [rsp-38h+arg_10], rbx
0x1800384c5  push    rbp
0x1800384c6  push    rsi
0x1800384c7  push    rdi
0x1800384c8  push    r12
0x1800384ca  push    r13
0x1800384cc  push    r14
0x1800384ce  push    r15
0x1800384d0  mov     rbp, rsp
0x1800384d3  sub     rsp, 70h
0x1800384d7  mov     rax, cs:__security_cookie
0x1800384de  xor     rax, rsp
0x1800384e1  mov     [rbp+var_8], rax
0x1800384e5  xor     r13d, r13d
0x1800384e8  mov     [rbp+var_18], rdx
0x1800384ec  xor     r14d, r14d
0x1800384ef  mov     [rdx], r13
0x1800384f2  mov     rdi, rcx
0x1800384f5  mov     dword ptr [rbp+pszDest], 0
0x1800384fc  mov     ecx, [rcx+4]
0x1800384ff  mov     r12, rdx
0x180038502  mov     [rbp+var_10], r13
0x180038506  lea     edx, [r14+0Eh]
0x18003850a  cmp     ecx, 1
0x18003850d  jnz     short loc_180038514
0x18003850f  lea     eax, [rdx+7]
0x180038512  jmp     short loc_180038531
0x180038514  cmp     ecx, 2
0x180038517  jnz     short loc_18003851E
0x180038519  lea     eax, [rcx+15h]
0x18003851c  jmp     short loc_180038531
0x18003851e  mov     rax, rdx
0x180038521  test    ecx, ecx
0x180038523  mov     edx, 13h
0x180038528  cmovz   rax, rdx
0x18003852c  mov     edx, 0Eh
0x180038531  lea     r15, [rax+1Ah]
0x180038535  mov     ecx, 0Dh
0x18003853a  mov     eax, [rdi+8]
0x18003853d  test    eax, eax
0x18003853f  jz      loc_1800385D3
0x180038545  cmp     eax, 1
0x180038548  jz      short loc_18003854F
0x18003854a  cmp     eax, 2
0x18003854d  jnz     short loc_180038554
0x18003854f  mov     rsi, rdx
0x180038552  jmp     short loc_180038583
0x180038554  cmp     eax, 3
0x180038557  jnz     short loc_18003855E
0x180038559  lea     esi, [rax+0Eh]
0x18003855c  jmp     short loc_180038583
0x18003855e  cmp     eax, 4
0x180038561  jz      short loc_180038568
0x180038563  cmp     eax, 5
0x180038566  jnz     short loc_18003856D
0x180038568  mov     rsi, rcx
0x18003856b  jmp     short loc_180038583
0x18003856d  cmp     eax, 6
0x180038570  jnz     short loc_180038577
0x180038572  lea     esi, [rax+6]
0x180038575  jmp     short loc_180038583
0x180038577  cmp     eax, 7
0x18003857a  mov     esi, 0Ah
0x18003857f  cmovz   rsi, rcx
0x180038583  mov     rdx, [rdi+10h]; unsigned __int16 *
0x180038587  lea     r8, [rbp+pszDest]; unsigned int *
0x18003858b  mov     ecx, 6; unsigned int
0x180038590  call    ?FwRuleGetStringFieldSize@@YAJKPEBGPEAK@Z; FwRuleGetStringFieldSize(ulong,ushort const *,ulong *)
0x180038595  mov     ebx, eax
0x180038597  test    eax, eax
0x180038599  jns     short loc_1800385C6
0x18003859b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385a2  lea     rax, WPP_GLOBAL_Control
0x1800385a9  cmp     rcx, rax
0x1800385ac  jz      loc_18003897B
0x1800385b2  test    byte ptr [rcx+1Ch], 1
0x1800385b6  jz      loc_18003897B
0x1800385bc  mov     edx, 0Ah
0x1800385c1  mov     r9d, ebx
0x1800385c4  jmp     short loc_180038620
0x1800385c6  mov     eax, dword ptr [rbp+pszDest]
0x1800385c9  add     r15, 2
0x1800385cd  add     rax, rsi
0x1800385d0  add     r15, rax
0x1800385d3  cmp     [rdi+18h], r13d
0x1800385d7  jbe     loc_1800386D9
0x1800385dd  mov     ecx, [rdi+18h]
0x1800385e0  shl     rcx, 3
0x1800385e4  call    cs:__imp_FwAlloc
0x1800385ea  mov     r14, rax
0x1800385ed  test    rax, rax
0x1800385f0  jnz     short loc_180038635
0x1800385f2  mov     r9d, 8007000Eh
0x1800385f8  mov     ebx, r9d
0x1800385fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180038602  lea     rax, WPP_GLOBAL_Control
0x180038609  cmp     rcx, rax
0x18003860c  jz      loc_18003897B
0x180038612  test    byte ptr [rcx+1Ch], 1
0x180038616  jz      loc_18003897B
0x18003861c  lea     edx, [r14+0Bh]
0x180038620  mov     rcx, [rcx+10h]
0x180038624  lea     r8, WPP_3d77b55d25ee3bd4e60182d5f5bc697d_Traceguids
0x18003862b  call    WPP_SF_d
0x180038630  jmp     loc_18003897B
0x180038635  xor     esi, esi
0x180038637  cmp     esi, [rdi+18h]
0x18003863a  jnb     loc_1800386D5
0x180038640  mov     rcx, [rdi+20h]
0x180038644  lea     r12, [r14+rsi*8]
0x180038648  mov     r8, r12
0x18003864b  xor     edx, edx
0x18003864d  mov     rcx, [rcx+rsi*8]
0x180038651  call    cs:__imp_FwStringCopyAtoWAlloc
0x180038657  mov     ebx, eax
0x180038659  test    eax, eax
0x18003865b  js      short loc_1800386AA
0x18003865d  mov     rdx, [r12]; unsigned __int16 *
0x180038661  lea     r8, [rbp+pszDest]; unsigned int *
0x180038665  mov     ecx, 5; unsigned int
0x18003866a  call    ?FwRuleGetStringFieldSize@@YAJKPEBGPEAK@Z; FwRuleGetStringFieldSize(ulong,ushort const *,ulong *)
0x18003866f  mov     ebx, eax
0x180038671  test    eax, eax
0x180038673  js      short loc_18003867F
0x180038675  mov     eax, dword ptr [rbp+pszDest]
0x180038678  add     r15, rax
0x18003867b  inc     esi
0x18003867d  jmp     short loc_180038637
0x18003867f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038686  lea     rax, WPP_GLOBAL_Control
0x18003868d  cmp     rcx, rax
0x180038690  jz      loc_18003897B
0x180038696  test    byte ptr [rcx+1Ch], 1
0x18003869a  jz      loc_18003897B
0x1800386a0  mov     edx, 0Dh
0x1800386a5  jmp     loc_1800385C1
0x1800386aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386b1  lea     rax, WPP_GLOBAL_Control
0x1800386b8  cmp     rcx, rax
0x1800386bb  jz      loc_18003897B
0x1800386c1  test    byte ptr [rcx+1Ch], 1
0x1800386c5  jz      loc_18003897B
0x1800386cb  mov     edx, 0Ch
0x1800386d0  jmp     loc_1800385C1
0x1800386d5  mov     r12, [rbp+var_18]
0x1800386d9  mov     rdx, [rdi+28h]; unsigned __int16 *
0x1800386dd  lea     r8, [rbp+pszDest]; unsigned int *
0x1800386e1  mov     ecx, 6; unsigned int
0x1800386e6  call    ?FwRuleGetStringFieldSize@@YAJKPEBGPEAK@Z; FwRuleGetStringFieldSize(ulong,ushort const *,ulong *)
0x1800386eb  mov     ebx, eax
0x1800386ed  test    eax, eax
0x1800386ef  jns     short loc_18003871C
0x1800386f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386f8  lea     rax, WPP_GLOBAL_Control
0x1800386ff  cmp     rcx, rax
0x180038702  jz      loc_18003897B
0x180038708  test    byte ptr [rcx+1Ch], 1
0x18003870c  jz      loc_18003897B
0x180038712  mov     edx, 0Eh
0x180038717  jmp     loc_1800385C1
0x18003871c  mov     al, [rdi+2]
0x18003871f  lea     r8, [rbp+var_10]
0x180038723  mov     esi, dword ptr [rbp+pszDest]
0x180038726  and     al, 1
0x180038728  neg     al
0x18003872a  mov     edx, 2
0x18003872f  sbb     rcx, rcx
0x180038732  add     rsi, r15
0x180038735  and     ecx, 16h
0x180038738  inc     rcx
0x18003873b  add     rsi, rcx
0x18003873e  mov     rcx, rsi
0x180038741  mov     [rbp+var_18], rsi
0x180038745  call    cs:__imp_FwSizeTMultiply
0x18003874b  mov     ebx, eax
0x18003874d  test    eax, eax
0x18003874f  jns     short loc_18003877C
0x180038751  mov     rcx, cs:WPP_GLOBAL_Control
0x180038758  lea     rax, WPP_GLOBAL_Control
0x18003875f  cmp     rcx, rax
0x180038762  jz      loc_18003897B
0x180038768  test    byte ptr [rcx+1Ch], 1
0x18003876c  jz      loc_18003897B
0x180038772  mov     edx, 0Fh
0x180038777  jmp     loc_1800385C1
0x18003877c  mov     rcx, [rbp+var_10]
0x180038780  call    cs:__imp_FwAlloc
0x180038786  mov     r13, rax
0x180038789  test    rax, rax
0x18003878c  jnz     short loc_1800387C1
0x18003878e  mov     r9d, 8007000Eh
0x180038794  mov     ebx, r9d
0x180038797  mov     rcx, cs:WPP_GLOBAL_Control
0x18003879e  lea     rax, WPP_GLOBAL_Control
0x1800387a5  cmp     rcx, rax
0x1800387a8  jz      loc_18003897B
0x1800387ae  test    byte ptr [rcx+1Ch], 1
0x1800387b2  jz      loc_18003897B
0x1800387b8  lea     edx, [r13+10h]
0x1800387bc  jmp     loc_180038620
0x1800387c1  movzx   ecx, word ptr [rdi]
0x1800387c4  lea     rdx, asc_18003D4F8; "|"
0x1800387cb  mov     [rsp+70h+var_30], rdx
0x1800387d0  lea     r9, [rbp+var_18]; unsigned __int64 *
0x1800387d4  movzx   eax, cl
0x1800387d7  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800387db  mov     dword ptr [rsp+70h+var_38], eax
0x1800387df  mov     r15d, 800h
0x1800387e5  shr     ecx, 8
0x1800387e8  lea     rax, aVDDS; "v%d.%d%s"
0x1800387ef  mov     dword ptr [rsp+70h+var_40], ecx
0x1800387f3  mov     rdx, rsi; unsigned __int64
0x1800387f6  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x1800387fb  mov     rcx, r13; pszDest
0x1800387fe  mov     dword ptr [rsp+70h+var_50], r15d; unsigned int
0x180038803  mov     [rbp+pszDest], r13
0x180038807  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18003880c  test    eax, eax
0x18003880e  jns     short loc_180038815
0x180038810  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180038815  mov     rdx, [rbp+var_18]; unsigned __int64
0x180038819  lea     r9, [rbp+var_18]; unsigned __int64 *
0x18003881d  mov     rcx, [rbp+pszDest]; unsigned __int16 *
0x180038821  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x180038825  mov     [rsp+70h+var_50], rdi; struct _tag_FW_CERT_CRITERIA *
0x18003882a  call    ?FwCertCriteriaSerializeCriteriaType@@YAJPEAG_KPEAPEAGPEA_KPEAU_tag_FW_CERT_CRITERIA@@@Z; FwCertCriteriaSerializeCriteriaType(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,_tag_FW_CERT_CRITERIA *)
0x18003882f  test    eax, eax
0x180038831  jns     short loc_180038838
0x180038833  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180038838  cmp     dword ptr [rdi+8], 0
0x18003883c  jz      short loc_180038894
0x18003883e  mov     rdx, [rbp+var_18]; unsigned __int64
0x180038842  lea     r9, [rbp+var_18]; unsigned __int64 *
0x180038846  mov     rcx, [rbp+pszDest]; unsigned __int16 *
0x18003884a  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x18003884e  mov     [rsp+70h+var_50], rdi; struct _tag_FW_CERT_CRITERIA *
0x180038853  call    ?FwCertCriteriaSerializeNameType@@YAJPEAG_KPEAPEAGPEA_KPEAU_tag_FW_CERT_CRITERIA@@@Z; FwCertCriteriaSerializeNameType(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,_tag_FW_CERT_CRITERIA *)
0x180038858  test    eax, eax
0x18003885a  jns     short loc_180038861
0x18003885c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180038861  mov     rax, [rdi+10h]
0x180038865  lea     r9, [rbp+var_18]; unsigned __int64 *
0x180038869  mov     rdx, [rbp+var_18]; unsigned __int64
0x18003886d  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x180038871  mov     rcx, [rbp+pszDest]; unsigned __int16 *
0x180038875  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x18003887a  lea     rax, aName_0; "Name="
0x180038881  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x180038886  call    ?FwRuleSerializeStringField@@YAJPEAG_KPEAPEAGPEA_KPEBG4@Z; FwRuleSerializeStringField(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ushort const *,ushort const *)
0x18003888b  test    eax, eax
0x18003888d  jns     short loc_180038894
0x18003888f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180038894  cmp     dword ptr [rdi+18h], 0
0x180038898  jbe     short loc_1800388D6
0x18003889a  xor     ebx, ebx
0x18003889c  mov     rcx, [r14+rbx*8]
0x1800388a0  lea     rax, aEku; "Eku="
0x1800388a7  mov     rdx, [rbp+var_18]; unsigned __int64
0x1800388ab  lea     r9, [rbp+var_18]; unsigned __int64 *
0x1800388af  mov     [rsp+70h+var_48], rcx; unsigned __int16 *
0x1800388b4  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800388b8  mov     rcx, [rbp+pszDest]; unsigned __int16 *
0x1800388bc  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x1800388c1  call    ?FwRuleSerializeStringField@@YAJPEAG_KPEAPEAGPEA_KPEBG4@Z; FwRuleSerializeStringField(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ushort const *,ushort const *)
0x1800388c6  test    eax, eax
0x1800388c8  jns     short loc_1800388CF
0x1800388ca  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800388cf  inc     ebx
0x1800388d1  cmp     ebx, [rdi+18h]
0x1800388d4  jb      short loc_18003889C
0x1800388d6  mov     rax, [rdi+28h]
0x1800388da  lea     r9, [rbp+var_18]; unsigned __int64 *
0x1800388de  mov     rdx, [rbp+var_18]; unsigned __int64
0x1800388e2  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800388e6  mov     rcx, [rbp+pszDest]; unsigned __int16 *
0x1800388ea  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x1800388ef  lea     rax, aHash; "Hash="
0x1800388f6  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x1800388fb  call    ?FwRuleSerializeStringField@@YAJPEAG_KPEAPEAGPEA_KPEBG4@Z; FwRuleSerializeStringField(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ushort const *,ushort const *)
0x180038900  test    eax, eax
0x180038902  jns     short loc_180038909
0x180038904  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180038909  mov     rcx, [rbp+pszDest]; pszDest
0x18003890d  xor     ebx, ebx
0x18003890f  test    byte ptr [rdi+2], 1
0x180038913  mov     rdx, [rbp+var_18]; unsigned __int64
0x180038917  mov     [rbp+pszDest], rcx
0x18003891b  mov     [rbp+var_18], rdx
0x18003891f  jz      short loc_180038973
0x180038921  lea     rax, asc_18003D4F8; "|"
0x180038928  mov     [rsp+70h+var_30], rax
0x18003892d  lea     r9, [rbp+var_18]; unsigned __int64 *
0x180038931  lea     rax, String2; "TRUE"
0x180038938  mov     [rsp+70h+var_38], rax
0x18003893d  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x180038941  lea     rax, aFollowrenewal; "FollowRenewal="
0x180038948  mov     [rsp+70h+var_40], rax
0x18003894d  lea     rax, aSSS_2; "%s%s%s"
0x180038954  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x180038959  mov     dword ptr [rsp+70h+var_50], r15d; unsigned int
  ... truncated ...
```
