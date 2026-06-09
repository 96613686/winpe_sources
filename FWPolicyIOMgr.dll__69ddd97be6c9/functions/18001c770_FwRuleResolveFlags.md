# FwRuleResolveFlags

- ea: `0x18001c770`
- end: `0x18001cdfb`
- name: `FwRuleResolveFlags`
- size: `1675`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001a290`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x180006f50`
- `0x1800086a4`
- `0x1800087b0`
- `0x18001c770`
- `0x18001e2c0`
- `0x18001e770`
- `0x18001e9ac`
- `0x18001f650`
- `0x180023d80`
- `0x18002e460`
- `0x180031080`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cbfa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cbfa`
- `fwbase!FwFree` at `0x18001cbc6`
- `fwbase!FwFree` at `0x18001cbc6`
- `fwbase!FwResolveIndirectString` at `0x18001c831`
- `fwbase!FwResolveIndirectString` at `0x18001c8c5`
- `fwbase!FwResolveIndirectString` at `0x18001c962`
- `fwbase!FwResolveIndirectString` at `0x18001c9ff`
- `fwbase!FwResolveIndirectString` at `0x18001caa4`
- `fwbase!FwResolveIndirectString` at `0x18001cb22`
- `fwbase!FwResolveIndirectString` at `0x18001c831`
- `fwbase!FwResolveIndirectString` at `0x18001c8c5`
- `fwbase!FwResolveIndirectString` at `0x18001c962`
- `fwbase!FwResolveIndirectString` at `0x18001c9ff`
- `fwbase!FwResolveIndirectString` at `0x18001caa4`
- `fwbase!FwResolveIndirectString` at `0x18001cb22`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x18001cbad`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x18001cbad`

## pseudocode

```c
__int64 __fastcall FwRuleResolveFlags(void **a1, unsigned int a2, char a3, int a4, _DWORD *a5)
{
  unsigned int ExpandedCanonicalLongPathName; // r14d
  char v9; // bp
  char *v10; // rbx
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  char *v19; // rcx
  int v20; // eax
  LPCOLESTR v21; // r10
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // r10
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v30; // r10
  __int64 v31; // rdx
  char *v32; // rcx
  int v33; // eax
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rdx
  __int64 v41; // [rsp+38h] [rbp-50h] BYREF
  int v42; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  ExpandedCanonicalLongPathName = 0;
  v9 = a3 & 0xFB;
  if ( !a2 )
    v9 = a3;
  v10 = (char *)*a1;
  if ( !*a1 )
    return ExpandedCanonicalLongPathName;
  do
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl'::`2'::impl) )
    {
      if ( !a2 )
      {
        if ( (v9 & 1) == 0 || (*((_WORD *)v10 + 212) & 0x1000) != 0 )
        {
LABEL_21:
          if ( (v9 & 2) == 0 || (*((_WORD *)v10 + 212) & 0x2000) != 0 )
            goto LABEL_83;
          v15 = FwResolveIndirectString(v10 + 32);
          if ( v15 == -2147467259 )
          {
            if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
              goto LABEL_32;
            v16 = RuleTypeToString(0);
            v18 = 29;
          }
          else
          {
            if ( v15 >= 0 || WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_32;
            v16 = RuleTypeToString(0);
            v18 = 30;
          }
          WPP_SF_s(*(_QWORD *)(v17 + 16), v18, v17, v16);
LABEL_32:
          *((_WORD *)v10 + 212) |= 0x2000u;
          goto LABEL_83;
        }
        v11 = FwResolveIndirectString(v10 + 24);
        if ( v11 == -2147467259 )
        {
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_20;
          v12 = RuleTypeToString(0);
          v14 = 27;
        }
        else
        {
          if ( v11 >= 0 || WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_20;
          v12 = RuleTypeToString(0);
          v14 = 28;
        }
        WPP_SF_s(*(_QWORD *)(v13 + 16), v14, v13, v12);
LABEL_20:
        *((_WORD *)v10 + 212) |= 0x1000u;
        goto LABEL_21;
      }
      if ( (v9 & 1) == 0 )
        goto LABEL_47;
      if ( a2 == 1 || a2 == 2 || (v19 = v10 + 24, a2 != 3) )
        v19 = v10;
      v20 = FwResolveIndirectString(v19 + 24);
      if ( v20 == -2147467259 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          v22 = RuleTypeToString(a2);
          v25 = 31;
LABEL_46:
          WPP_SF_s(*(_QWORD *)(v24 + 16), v25, v23, v22);
          goto LABEL_47;
        }
      }
      else
      {
        if ( v20 >= 0 )
        {
LABEL_47:
          v21 = WPP_GLOBAL_Control;
          goto LABEL_48;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v22 = RuleTypeToString(a2);
          v25 = 32;
          goto LABEL_46;
        }
      }
LABEL_48:
      if ( (v9 & 2) == 0 )
        goto LABEL_84;
      if ( a2 == 1 || a2 == 2 )
      {
        v26 = 32;
      }
      else
      {
        v26 = 24;
        if ( a2 == 3 )
          v26 = 56;
      }
      v27 = FwResolveIndirectString(&v10[v26]);
      if ( v27 == -2147467259 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          v28 = RuleTypeToString(a2);
          v31 = 33;
          goto LABEL_58;
        }
      }
      else
      {
        if ( v27 >= 0 )
          goto LABEL_83;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v28 = RuleTypeToString(a2);
          v31 = 34;
LABEL_58:
          WPP_SF_s(*(_QWORD *)(v30 + 16), v31, v29, v28);
LABEL_83:
          v21 = WPP_GLOBAL_Control;
          goto LABEL_84;
        }
      }
      goto LABEL_84;
    }
    if ( (v9 & 1) != 0 )
    {
      if ( a2 <= 2 || (v32 = v10 + 24, a2 != 3) )
        v32 = v10;
      v33 = FwResolveIndirectString(v32 + 24);
      ExpandedCanonicalLongPathName = v33;
      if ( v33 == -2147467259 )
      {
        ExpandedCanonicalLongPathName = 0;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_73;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
      }
      else if ( v33 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
          return ExpandedCanonicalLongPathName;
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_134;
        v38 = 36;
        goto LABEL_125;
      }
    }
    v21 = WPP_GLOBAL_Control;
LABEL_73:
    if ( (v9 & 2) == 0 )
      goto LABEL_84;
    if ( a2 > 2 )
    {
      v34 = 24;
      if ( a2 == 3 )
        v34 = 56;
    }
    else
    {
      v34 = 32;
    }
    v35 = FwResolveIndirectString(&v10[v34]);
    ExpandedCanonicalLongPathName = v35;
    if ( v35 != -2147467259 )
    {
      if ( v35 >= 0 )
        goto LABEL_83;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
        return ExpandedCanonicalLongPathName;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_134;
      v38 = 38;
LABEL_125:
      WPP_SF_(*((_QWORD *)v21 + 2), v38, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
      goto LABEL_126;
    }
    ExpandedCanonicalLongPathName = 0;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
      goto LABEL_83;
    }
LABEL_84:
    if ( (v9 & 4) == 0 )
      goto LABEL_99;
    if ( a2 )
      goto LABEL_101;
    v36 = *((_QWORD *)v10 + 34);
    if ( !v36 )
      goto LABEL_100;
    v41 = 0;
    v42 = 0;
    ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(v36, &v41, &v42);
    if ( v42 == 1 )
    {
      FwFree(*((_QWORD *)v10 + 34));
      *((_QWORD *)v10 + 34) = v41;
LABEL_97:
      v21 = WPP_GLOBAL_Control;
      goto LABEL_98;
    }
    if ( CompareStringW(0x7Fu, 1u, L"System", -1, *((PCNZWCH *)v10 + 34), -1) == 2 )
    {
      v21 = WPP_GLOBAL_Control;
      ExpandedCanonicalLongPathName = 0;
LABEL_100:
      v37 = *((_DWORD *)v10 + 84);
      goto LABEL_106;
    }
    if ( (int)(ExpandedCanonicalLongPathName + 0x80000000) >= 0 && ExpandedCanonicalLongPathName != -2147024882 )
      ExpandedCanonicalLongPathName = 0;
    *((_DWORD *)v10 + 84) = 524300;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
      goto LABEL_97;
    }
LABEL_98:
    if ( (ExpandedCanonicalLongPathName & 0x80000000) != 0 )
    {
      if ( v21 == (LPCOLESTR)&WPP_GLOBAL_Control )
        return ExpandedCanonicalLongPathName;
      if ( (v21[14] & 1) == 0 )
        goto LABEL_134;
      WPP_SF_d(*((_QWORD *)v21 + 2), 40, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, ExpandedCanonicalLongPathName);
LABEL_126:
      v21 = WPP_GLOBAL_Control;
      goto LABEL_134;
    }
LABEL_99:
    if ( !a2 )
      goto LABEL_100;
LABEL_101:
    if ( a2 == 1 )
    {
      v37 = *((_DWORD *)v10 + 96);
    }
    else if ( a2 == 2 )
    {
      v37 = *((_DWORD *)v10 + 64);
    }
    else
    {
      v37 = *((_DWORD *)v10 + 29);
    }
LABEL_106:
    if ( (v37 & a4) != 0 )
    {
      a1 = (void **)v10;
    }
    else
    {
      *a1 = *(void **)v10;
      if ( a2 )
      {
        switch ( a2 )
        {
          case 1u:
            FwCSRuleFree(v10);
            break;
          case 2u:
            FwMMRuleFree(v10);
            break;
          case 3u:
            FwAppContainerFree(v10);
            break;
          default:
            FwFreeHyperVRulesBySchemaVersion(v10);
            break;
        }
      }
      else
      {
        FwFreeWFRule(v10);
      }
      if ( !*a5 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      --*a5;
      v21 = WPP_GLOBAL_Control;
    }
    v10 = (char *)*a1;
  }
  while ( *a1 );
  if ( (ExpandedCanonicalLongPathName & 0x80000000) == 0 )
    return ExpandedCanonicalLongPathName;
LABEL_134:
  if ( v21 != (LPCOLESTR)&WPP_GLOBAL_Control && (v21[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v21 + 2), 41, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, ExpandedCanonicalLongPathName);
  return ExpandedCanonicalLongPathName;
}

```

## disassembly

```asm
0x18001c770  mov     [rsp+arg_10], rbx
0x18001c775  push    rbp
0x18001c776  push    rsi
0x18001c777  push    rdi
0x18001c778  push    r12
0x18001c77a  push    r13
0x18001c77c  push    r14
0x18001c77e  push    r15
0x18001c780  sub     rsp, 50h
0x18001c784  mov     rax, cs:__security_cookie
0x18001c78b  xor     rax, rsp
0x18001c78e  mov     [rsp+88h+var_40], rax
0x18001c793  mov     r13, [rsp+88h+arg_20]
0x18001c79b  mov     ebx, r8d
0x18001c79e  mov     [rsp+88h+var_58], r9d
0x18001c7a3  mov     esi, edx
0x18001c7a5  mov     r12, rcx
0x18001c7a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7af  lea     rax, WPP_GLOBAL_Control
0x18001c7b6  cmp     rcx, rax
0x18001c7b9  jz      short loc_18001C7D6
0x18001c7bb  test    byte ptr [rcx+1Ch], 8
0x18001c7bf  jz      short loc_18001C7D6
0x18001c7c1  mov     rcx, [rcx+10h]
0x18001c7c5  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001c7cc  mov     edx, 1Ah
0x18001c7d1  call    WPP_SF_
0x18001c7d6  mov     ebp, ebx
0x18001c7d8  xor     r14d, r14d
0x18001c7db  and     ebp, 0FFFFFFFBh
0x18001c7de  test    esi, esi
0x18001c7e0  cmovz   ebp, ebx
0x18001c7e3  mov     rbx, [r12]
0x18001c7e7  test    rbx, rbx
0x18001c7ea  jz      loc_18001CDD3
0x18001c7f0  mov     r15d, ebp
0x18001c7f3  lea     edi, [r14+1]
0x18001c7f7  and     r15d, edi
0x18001c7fa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load> `wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl(void)'::`2'::impl
0x18001c801  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(void)
0x18001c806  test    al, al
0x18001c808  jz      loc_18001CA82
0x18001c80e  test    esi, esi
0x18001c810  jnz     loc_18001C940
0x18001c816  test    r15d, r15d
0x18001c819  jz      loc_18001C8A5
0x18001c81f  mov     eax, 1000h
0x18001c824  test    [rbx+1A8h], ax
0x18001c82b  jnz     short loc_18001C8A5
0x18001c82d  lea     rcx, [rbx+18h]
0x18001c831  call    cs:__imp_FwResolveIndirectString
0x18001c837  cmp     eax, 80004005h
0x18001c83c  jnz     short loc_18001C864
0x18001c83e  mov     r8, cs:WPP_GLOBAL_Control
0x18001c845  lea     rax, WPP_GLOBAL_Control
0x18001c84c  cmp     r8, rax
0x18001c84f  jz      short loc_18001C899
0x18001c851  test    byte ptr [r8+1Ch], 4
0x18001c856  jz      short loc_18001C899
0x18001c858  xor     ecx, ecx
0x18001c85a  call    RuleTypeToString
0x18001c85f  lea     edx, [rsi+1Bh]
0x18001c862  jmp     short loc_18001C88D
0x18001c864  test    eax, eax
0x18001c866  jns     short loc_18001C899
0x18001c868  mov     r8, cs:WPP_GLOBAL_Control
0x18001c86f  lea     rax, WPP_GLOBAL_Control
0x18001c876  cmp     r8, rax
0x18001c879  jz      short loc_18001C899
0x18001c87b  test    [r8+1Ch], dil
0x18001c87f  jz      short loc_18001C899
0x18001c881  xor     ecx, ecx
0x18001c883  call    RuleTypeToString
0x18001c888  mov     edx, 1Ch
0x18001c88d  mov     rcx, [r8+10h]
0x18001c891  mov     r9, rax
0x18001c894  call    WPP_SF_s
0x18001c899  mov     eax, 1000h
0x18001c89e  or      [rbx+1A8h], ax
0x18001c8a5  test    bpl, 2
0x18001c8a9  jz      loc_18001CB6D
0x18001c8af  mov     eax, 2000h
0x18001c8b4  test    [rbx+1A8h], ax
0x18001c8bb  jnz     loc_18001CB6D
0x18001c8c1  lea     rcx, [rbx+20h]
0x18001c8c5  call    cs:__imp_FwResolveIndirectString
0x18001c8cb  cmp     eax, 80004005h
0x18001c8d0  jnz     short loc_18001C8FA
0x18001c8d2  mov     r8, cs:WPP_GLOBAL_Control
0x18001c8d9  lea     rax, WPP_GLOBAL_Control
0x18001c8e0  cmp     r8, rax
0x18001c8e3  jz      short loc_18001C92F
0x18001c8e5  test    byte ptr [r8+1Ch], 4
0x18001c8ea  jz      short loc_18001C92F
0x18001c8ec  xor     ecx, ecx
0x18001c8ee  call    RuleTypeToString
0x18001c8f3  mov     edx, 1Dh
0x18001c8f8  jmp     short loc_18001C923
0x18001c8fa  test    eax, eax
0x18001c8fc  jns     short loc_18001C92F
0x18001c8fe  mov     r8, cs:WPP_GLOBAL_Control
0x18001c905  lea     rax, WPP_GLOBAL_Control
0x18001c90c  cmp     r8, rax
0x18001c90f  jz      short loc_18001C92F
0x18001c911  test    [r8+1Ch], dil
0x18001c915  jz      short loc_18001C92F
0x18001c917  xor     ecx, ecx
0x18001c919  call    RuleTypeToString
0x18001c91e  mov     edx, 1Eh
0x18001c923  mov     rcx, [r8+10h]
0x18001c927  mov     r9, rax
0x18001c92a  call    WPP_SF_s
0x18001c92f  mov     eax, 2000h
0x18001c934  or      [rbx+1A8h], ax
0x18001c93b  jmp     loc_18001CB6D
0x18001c940  test    r15d, r15d
0x18001c943  jz      loc_18001C9CC
0x18001c949  cmp     esi, edi
0x18001c94b  jz      short loc_18001C95B
0x18001c94d  cmp     esi, 2
0x18001c950  jz      short loc_18001C95B
0x18001c952  lea     rcx, [rbx+18h]
0x18001c956  cmp     esi, 3
0x18001c959  jz      short loc_18001C95E
0x18001c95b  mov     rcx, rbx
0x18001c95e  add     rcx, 18h
0x18001c962  call    cs:__imp_FwResolveIndirectString
0x18001c968  cmp     eax, 80004005h
0x18001c96d  jnz     short loc_18001C997
0x18001c96f  mov     r10, cs:WPP_GLOBAL_Control
0x18001c976  lea     rax, WPP_GLOBAL_Control
0x18001c97d  cmp     r10, rax
0x18001c980  jz      short loc_18001C9D3
0x18001c982  test    byte ptr [r10+1Ch], 4
0x18001c987  jz      short loc_18001C9D3
0x18001c989  mov     ecx, esi
0x18001c98b  call    RuleTypeToString
0x18001c990  mov     edx, 1Fh
0x18001c995  jmp     short loc_18001C9C0
0x18001c997  test    eax, eax
0x18001c999  jns     short loc_18001C9CC
0x18001c99b  mov     r10, cs:WPP_GLOBAL_Control
0x18001c9a2  lea     rax, WPP_GLOBAL_Control
0x18001c9a9  cmp     r10, rax
0x18001c9ac  jz      short loc_18001C9D3
0x18001c9ae  test    [r10+1Ch], dil
0x18001c9b2  jz      short loc_18001C9D3
0x18001c9b4  mov     ecx, esi
0x18001c9b6  call    RuleTypeToString
0x18001c9bb  mov     edx, 20h ; ' '
0x18001c9c0  mov     rcx, [r10+10h]
0x18001c9c4  mov     r9, rax
0x18001c9c7  call    WPP_SF_s
0x18001c9cc  mov     r10, cs:WPP_GLOBAL_Control
0x18001c9d3  test    bpl, 2
0x18001c9d7  jz      loc_18001CB74
0x18001c9dd  cmp     esi, edi
0x18001c9df  jz      short loc_18001C9E6
0x18001c9e1  cmp     esi, 2
0x18001c9e4  jnz     short loc_18001C9ED
0x18001c9e6  mov     eax, 20h ; ' '
0x18001c9eb  jmp     short loc_18001C9FB
0x18001c9ed  mov     eax, 18h
0x18001c9f2  cmp     esi, 3
0x18001c9f5  lea     ecx, [rax+20h]
0x18001c9f8  cmovz   eax, ecx
0x18001c9fb  lea     rcx, [rax+rbx]
0x18001c9ff  call    cs:__imp_FwResolveIndirectString
0x18001ca05  cmp     eax, 80004005h
0x18001ca0a  jnz     short loc_18001CA4B
0x18001ca0c  mov     r10, cs:WPP_GLOBAL_Control
0x18001ca13  lea     rax, WPP_GLOBAL_Control
0x18001ca1a  cmp     r10, rax
0x18001ca1d  jz      loc_18001CB74
0x18001ca23  test    byte ptr [r10+1Ch], 4
0x18001ca28  jz      loc_18001CB74
0x18001ca2e  mov     ecx, esi
0x18001ca30  call    RuleTypeToString
0x18001ca35  mov     edx, 21h ; '!'
0x18001ca3a  mov     rcx, [r10+10h]
0x18001ca3e  mov     r9, rax
0x18001ca41  call    WPP_SF_s
0x18001ca46  jmp     loc_18001CB6D
0x18001ca4b  test    eax, eax
0x18001ca4d  jns     loc_18001CB6D
0x18001ca53  mov     r10, cs:WPP_GLOBAL_Control
0x18001ca5a  lea     rax, WPP_GLOBAL_Control
0x18001ca61  cmp     r10, rax
0x18001ca64  jz      loc_18001CB74
0x18001ca6a  test    [r10+1Ch], dil
0x18001ca6e  jz      loc_18001CB74
0x18001ca74  mov     ecx, esi
0x18001ca76  call    RuleTypeToString
0x18001ca7b  mov     edx, 22h ; '"'
0x18001ca80  jmp     short loc_18001CA3A
0x18001ca82  test    r15d, r15d
0x18001ca85  jz      short loc_18001CAEF
0x18001ca87  test    esi, esi
0x18001ca89  jz      short loc_18001CA9D
0x18001ca8b  cmp     esi, edi
0x18001ca8d  jz      short loc_18001CA9D
0x18001ca8f  cmp     esi, 2
0x18001ca92  jz      short loc_18001CA9D
0x18001ca94  lea     rcx, [rbx+18h]
0x18001ca98  cmp     esi, 3
0x18001ca9b  jz      short loc_18001CAA0
0x18001ca9d  mov     rcx, rbx
0x18001caa0  add     rcx, 18h
0x18001caa4  call    cs:__imp_FwResolveIndirectString
0x18001caaa  mov     r14d, eax
0x18001caad  cmp     eax, 80004005h
0x18001cab2  jnz     short loc_18001CAE7
0x18001cab4  xor     r14d, r14d
0x18001cab7  mov     r10, cs:WPP_GLOBAL_Control
0x18001cabe  lea     rax, WPP_GLOBAL_Control
0x18001cac5  cmp     r10, rax
0x18001cac8  jz      short loc_18001CAF6
0x18001caca  test    byte ptr [r10+1Ch], 4
0x18001cacf  jz      short loc_18001CAF6
0x18001cad1  mov     rcx, [r10+10h]
0x18001cad5  lea     edx, [r14+23h]
0x18001cad9  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001cae0  call    WPP_SF_
0x18001cae5  jmp     short loc_18001CAEF
0x18001cae7  test    eax, eax
0x18001cae9  js      loc_18001CD1F
0x18001caef  mov     r10, cs:WPP_GLOBAL_Control
0x18001caf6  test    bpl, 2
0x18001cafa  jz      short loc_18001CB74
0x18001cafc  test    esi, esi
0x18001cafe  jz      short loc_18001CB09
0x18001cb00  cmp     esi, edi
0x18001cb02  jz      short loc_18001CB09
0x18001cb04  cmp     esi, 2
0x18001cb07  jnz     short loc_18001CB10
0x18001cb09  mov     eax, 20h ; ' '
0x18001cb0e  jmp     short loc_18001CB1E
0x18001cb10  mov     eax, 18h
0x18001cb15  cmp     esi, 3
0x18001cb18  lea     ecx, [rax+20h]
0x18001cb1b  cmovz   eax, ecx
0x18001cb1e  lea     rcx, [rax+rbx]
0x18001cb22  call    cs:__imp_FwResolveIndirectString
0x18001cb28  mov     r14d, eax
0x18001cb2b  cmp     eax, 80004005h
0x18001cb30  jnz     short loc_18001CB65
0x18001cb32  xor     r14d, r14d
0x18001cb35  mov     r10, cs:WPP_GLOBAL_Control
0x18001cb3c  lea     rax, WPP_GLOBAL_Control
0x18001cb43  cmp     r10, rax
0x18001cb46  jz      short loc_18001CB74
0x18001cb48  test    byte ptr [r10+1Ch], 4
0x18001cb4d  jz      short loc_18001CB74
0x18001cb4f  mov     rcx, [r10+10h]
0x18001cb53  lea     edx, [r14+25h]
0x18001cb57  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001cb5e  call    WPP_SF_
0x18001cb63  jmp     short loc_18001CB6D
0x18001cb65  test    eax, eax
0x18001cb67  js      loc_18001CD5A
0x18001cb6d  mov     r10, cs:WPP_GLOBAL_Control
0x18001cb74  test    bpl, 4
0x18001cb78  jz      loc_18001CC7B
0x18001cb7e  test    esi, esi
0x18001cb80  jnz     loc_18001CC87
0x18001cb86  mov     rcx, [rbx+110h]
0x18001cb8d  test    rcx, rcx
0x18001cb90  jz      loc_18001CC7F
0x18001cb96  lea     r8, [rsp+88h+var_48]
0x18001cb9b  mov     [rsp+88h+var_50], 0
0x18001cba4  lea     rdx, [rsp+88h+var_50]
0x18001cba9  mov     [rsp+88h+var_48], esi
0x18001cbad  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x18001cbb3  mov     r14d, eax
0x18001cbb6  mov     rax, [rbx+110h]
0x18001cbbd  cmp     [rsp+88h+var_48], edi
0x18001cbc1  jnz     short loc_18001CBDD
0x18001cbc3  mov     rcx, rax
0x18001cbc6  call    cs:__imp_FwFree
0x18001cbcc  mov     rax, [rsp+88h+var_50]
0x18001cbd1  mov     [rbx+110h], rax
0x18001cbd8  jmp     loc_18001CC64
0x18001cbdd  or      ecx, 0FFFFFFFFh
0x18001cbe0  lea     r8, String1; "System"
0x18001cbe7  mov     [rsp+88h+cchCount2], ecx; cchCount2
0x18001cbeb  mov     r9d, ecx; cchCount1
0x18001cbee  mov     ecx, 7Fh; Locale
0x18001cbf3  mov     [rsp+88h+lpString2], rax; lpString2
0x18001cbf8  mov     edx, edi; dwCmpFlags
0x18001cbfa  call    cs:__imp_CompareStringW
0x18001cc00  cmp     eax, 2
0x18001cc03  jnz     short loc_18001CC11
0x18001cc05  mov     r10, cs:WPP_GLOBAL_Control
0x18001cc0c  xor     r14d, r14d
0x18001cc0f  jmp     short loc_18001CC7F
0x18001cc11  mov     ecx, 80000000h
0x18001cc16  lea     eax, [r14+rcx]
0x18001cc1a  test    ecx, eax
0x18001cc1c  jnz     short loc_18001CC2B
0x18001cc1e  xor     eax, eax
  ... truncated ...
```
