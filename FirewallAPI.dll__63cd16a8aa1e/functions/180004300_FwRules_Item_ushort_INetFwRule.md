# FwRules::Item(ushort *,INetFwRule * *)

- ea: `0x180004300`
- end: `0x180004618`
- name: `?Item@FwRules@@UEAAJPEAGPEAPEAUINetFwRule@@@Z`
- size: `792`
- prototype: `int(FwRules *__hidden this, unsigned __int16 *, struct INetFwRule **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180004300`
- `0x180004620`
- `0x18000470c`
- `0x180004cd0`
- `0x180009080`
- `0x18000b8c0`
- `0x180010dc4`
- `0x18001c4dc`
- `0x1800277b0`
- `0x18003104c`
- `0x180037c6c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x1800045e5`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x1800045e5`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x1800045ee`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x1800045ee`
- `OLEAUT32!__imp_SysStringLen` at `0x18000436a`
- `OLEAUT32!__imp_SysStringLen` at `0x18000436a`
- `fwbase!FwBaseFree` at `0x180004430`
- `fwbase!FwBaseFree` at `0x180004430`
- `fwbase!FwLoadIndirectString` at `0x180004389`
- `fwbase!FwLoadIndirectString` at `0x180004389`
- `fwbase!FwReportReturnError` at `0x180004426`
- `fwbase!FwReportReturnError` at `0x18000449a`
- `fwbase!FwReportReturnError` at `0x180004570`
- `fwbase!FwReportReturnError` at `0x18000460b`
- `fwbase!FwReportReturnError` at `0x180004426`
- `fwbase!FwReportReturnError` at `0x18000449a`
- `fwbase!FwReportReturnError` at `0x180004570`
- `fwbase!FwReportReturnError` at `0x18000460b`
- `fwbase!FwStringCopy` at `0x180004481`
- `fwbase!FwStringCopy` at `0x180004481`

## pseudocode

```c
__int64 __fastcall FwRules::Item(FwRules *this, unsigned __int16 *a2, struct INetFwRule **a3)
{
  struct _tag_FW_RULE *v3; // rsi
  FwPolicy2 *v7; // rcx
  int PolicyStoreHandle; // eax
  signed int v9; // ebx
  int v10; // eax
  struct _tag_FW_RULE *MatchingRuleWithRuleName; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  int v18; // eax
  int v19; // eax
  __int64 MatchingRuleWithLocRuleName; // rax
  int v21; // eax
  LANGID ThreadUILanguage; // bx
  __int64 v23; // rdx
  __int64 v24; // r8
  void *v25; // [rsp+30h] [rbp-40h] BYREF
  struct _tag_FW_RULE *v26; // [rsp+38h] [rbp-38h] BYREF
  struct INetFwRule *v27; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v28; // [rsp+48h] [rbp-28h] BYREF
  __int64 v29; // [rsp+50h] [rbp-20h] BYREF
  __int64 v30; // [rsp+58h] [rbp-18h] BYREF

  v3 = 0;
  v29 = 0;
  v26 = 0;
  v28 = 0;
  v25 = 0;
  v27 = 0;
  v30 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)v7 + 2), 17, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids, a2);
  }
  if ( !a3 )
  {
    v9 = -2147467261;
    goto LABEL_22;
  }
  if ( !SysStringLen(a2) )
  {
    v9 = -2147024809;
    goto LABEL_22;
  }
  if ( *a2 != 64 || (int)FwLoadIndirectString(a2, &v30) < 0 )
  {
    v18 = FwStringCopy(a2, &v30);
    v9 = v18;
    if ( v18 < 0 )
    {
      FwReportReturnError("FwTryResolveString", (unsigned int)v18);
LABEL_22:
      v12 = (unsigned int)v9;
      goto LABEL_13;
    }
  }
  *a3 = 0;
  PolicyStoreHandle = FwRules::GetPolicyStoreHandle(this, &v25);
  v9 = PolicyStoreHandle;
  if ( PolicyStoreHandle < 0 )
  {
LABEL_12:
    v12 = (unsigned int)PolicyStoreHandle;
LABEL_13:
    FwReportReturnError("FwRules::Item", v12);
    goto LABEL_14;
  }
  v10 = FWEnumFirewallRules((__int64)v25, 196608, 0x7FFFFFFF, 7, (__int64)&v28, (__int64)&v29);
  v9 = v10;
  if ( v10 > 0 )
    v9 = (unsigned __int16)v10 | 0x80070000;
  if ( v9 < 0 )
    goto LABEL_22;
  MatchingRuleWithRuleName = (struct _tag_FW_RULE *)FwRule::FwFindMatchingRuleWithRuleName(
                                                      v29,
                                                      v28,
                                                      v30,
                                                      *((unsigned int *)this + 6));
  if ( !MatchingRuleWithRuleName )
  {
    ThreadUILanguage = GetThreadUILanguage();
    if ( GetSystemDefaultLangID() == ThreadUILanguage )
      goto LABEL_21;
    FWFreeFirewallRules(v29, v23, v24);
    v29 = 0;
    v19 = FWEnumFirewallRules((__int64)v25, 196608, 0x7FFFFFFF, 0, (__int64)&v28, (__int64)&v29);
    v9 = v19;
    if ( v19 > 0 )
      v9 = (unsigned __int16)v19 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_22;
    MatchingRuleWithLocRuleName = FwRule::FwFindMatchingRuleWithRuleName(v29, v28, a2, *((unsigned int *)this + 6));
    if ( !MatchingRuleWithLocRuleName )
    {
      MatchingRuleWithLocRuleName = FwRule::FwFindMatchingRuleWithLocRuleName(v29, v28, a2, *((unsigned int *)this + 6));
      if ( !MatchingRuleWithLocRuleName )
        goto LABEL_21;
    }
    v21 = FwRuleLookup(v25, *(const unsigned __int16 **)(MatchingRuleWithLocRuleName + 16), 0, &v26);
    v9 = v21;
    if ( v21 < 0 )
    {
      FwReportReturnError("FwRules::Item", (unsigned int)v21);
      v3 = v26;
      goto LABEL_14;
    }
    v3 = v26;
    MatchingRuleWithRuleName = v26;
    if ( !v26 )
    {
LABEL_21:
      v9 = -2147024894;
      goto LABEL_22;
    }
  }
  PolicyStoreHandle = FwRule::CreateInstance(*((unsigned int *)this + 6), MatchingRuleWithRuleName, &v27);
  v9 = PolicyStoreHandle;
  if ( PolicyStoreHandle < 0 )
    goto LABEL_12;
  *a3 = v27;
LABEL_14:
  FwBaseFree(v30);
  FWFreeFirewallRules(v29, v13, v14);
  FWFreeFirewallRules((__int64)v3, v15, v16);
  if ( v9 < 0 )
    return (unsigned int)FwReportReturnError("FwRules::Item", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004300  mov     [rsp-28h+arg_18], rbx
0x180004305  push    rbp
0x180004306  push    rsi
0x180004307  push    rdi
0x180004308  push    r14
0x18000430a  push    r15
0x18000430c  mov     rbp, rsp
0x18000430f  sub     rsp, 70h
0x180004313  mov     rax, cs:__security_cookie
0x18000431a  xor     rax, rsp
0x18000431d  mov     [rbp+var_10], rax
0x180004321  xor     esi, esi
0x180004323  mov     [rbp+var_20], 0
0x18000432b  mov     [rbp+var_38], rsi
0x18000432f  mov     r15, r8
0x180004332  mov     [rbp+var_28], esi
0x180004335  mov     rdi, rdx
0x180004338  mov     [rbp+var_40], rsi
0x18000433c  mov     r14, rcx
0x18000433f  mov     [rbp+var_30], rsi
0x180004343  mov     [rbp+var_18], rsi
0x180004347  mov     rcx, cs:WPP_GLOBAL_Control
0x18000434e  lea     rbx, WPP_GLOBAL_Control
0x180004355  cmp     rcx, rbx
0x180004358  jnz     loc_18000457F
0x18000435e  test    r15, r15
0x180004361  jz      loc_1800045D1
0x180004367  mov     rcx, rdi; pbstr
0x18000436a  call    cs:__imp_SysStringLen
0x180004370  test    eax, eax
0x180004372  jz      loc_1800045DB
0x180004378  cmp     word ptr [rdi], 40h ; '@'
0x18000437c  jnz     loc_18000447A
0x180004382  lea     rdx, [rbp+var_18]
0x180004386  mov     rcx, rdi
0x180004389  call    cs:__imp_FwLoadIndirectString
0x18000438f  test    eax, eax
0x180004391  js      loc_18000447A
0x180004397  lea     rdx, [rbp+var_40]; void **
0x18000439b  mov     [r15], rsi
0x18000439e  mov     rcx, r14; this
0x1800043a1  call    ?GetPolicyStoreHandle@FwRules@@AEAAJPEAPEAX@Z; FwRules::GetPolicyStoreHandle(void * *)
0x1800043a6  mov     ebx, eax
0x1800043a8  test    eax, eax
0x1800043aa  js      short loc_18000441D
0x1800043ac  mov     rcx, [rbp+var_40]
0x1800043b0  lea     rax, [rbp+var_20]
0x1800043b4  mov     [rsp+70h+var_48], rax
0x1800043b9  mov     r9d, 7
0x1800043bf  lea     rax, [rbp+var_28]
0x1800043c3  mov     edx, 30000h
0x1800043c8  mov     r8d, 7FFFFFFFh
0x1800043ce  mov     [rsp+70h+var_50], rax
0x1800043d3  call    FWEnumFirewallRules
0x1800043d8  mov     ebx, eax
0x1800043da  test    eax, eax
0x1800043dc  jg      loc_1800044A2
0x1800043e2  test    ebx, ebx
0x1800043e4  js      loc_1800044C5
0x1800043ea  mov     r9d, [r14+18h]
0x1800043ee  mov     r8, [rbp+var_18]
0x1800043f2  mov     edx, [rbp+var_28]
0x1800043f5  mov     rcx, [rbp+var_20]
0x1800043f9  call    ?FwFindMatchingRuleWithRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x1800043fe  test    rax, rax
0x180004401  jz      loc_1800045E5
0x180004407  mov     ecx, [r14+18h]
0x18000440b  lea     r8, [rbp+var_30]
0x18000440f  mov     rdx, rax
0x180004412  call    ?CreateInstance@FwRule@@SAJW4FwPolicyViewFlags@@PEAU_tag_FW_RULE@@PEAPEAV1@@Z; FwRule::CreateInstance(FwPolicyViewFlags,_tag_FW_RULE *,FwRule * *)
0x180004417  mov     ebx, eax
0x180004419  test    eax, eax
0x18000441b  jns     short loc_180004471
0x18000441d  mov     edx, eax
0x18000441f  lea     rcx, aFwrulesItem; "FwRules::Item"
0x180004426  call    cs:__imp_FwReportReturnError
0x18000442c  mov     rcx, [rbp+var_18]
0x180004430  call    cs:__imp_FwBaseFree
0x180004436  mov     rcx, [rbp+var_20]
0x18000443a  call    FWFreeFirewallRules
0x18000443f  mov     rcx, rsi
0x180004442  call    FWFreeFirewallRules
0x180004447  test    ebx, ebx
0x180004449  js      loc_180004602
0x18000444f  mov     eax, ebx
0x180004451  mov     rcx, [rbp+var_10]
0x180004455  xor     rcx, rsp; StackCookie
0x180004458  call    __security_check_cookie
0x18000445d  mov     rbx, [rsp+70h+arg_18]
0x180004465  add     rsp, 70h
0x180004469  pop     r15
0x18000446b  pop     r14
0x18000446d  pop     rdi
0x18000446e  pop     rsi
0x18000446f  pop     rbp
0x180004470  retn
0x180004471  mov     rax, [rbp+var_30]
0x180004475  mov     [r15], rax
0x180004478  jmp     short loc_18000442C
0x18000447a  lea     rdx, [rbp+var_18]
0x18000447e  mov     rcx, rdi
0x180004481  call    cs:__imp_FwStringCopy
0x180004487  mov     ebx, eax
0x180004489  test    eax, eax
0x18000448b  jns     loc_180004397
0x180004491  mov     edx, eax
0x180004493  lea     rcx, aFwtryresolvest; "FwTryResolveString"
0x18000449a  call    cs:__imp_FwReportReturnError
0x1800044a0  jmp     short loc_1800044C5
0x1800044a2  movzx   ebx, ax
0x1800044a5  or      ebx, 80070000h
0x1800044ab  jmp     loc_1800043E2
0x1800044b0  mov     rsi, [rbp+var_38]
0x1800044b4  mov     rax, rsi
0x1800044b7  test    rsi, rsi
0x1800044ba  jnz     loc_180004407
0x1800044c0  mov     ebx, 80070002h
0x1800044c5  mov     edx, ebx
0x1800044c7  jmp     loc_18000441F
0x1800044cc  mov     rcx, [rbp+var_20]
0x1800044d0  call    FWFreeFirewallRules
0x1800044d5  mov     rcx, [rbp+var_40]
0x1800044d9  lea     rax, [rbp+var_20]
0x1800044dd  mov     [rsp+70h+var_48], rax
0x1800044e2  xor     r9d, r9d
0x1800044e5  lea     rax, [rbp+var_28]
0x1800044e9  mov     [rbp+var_20], rsi
0x1800044ed  mov     edx, 30000h
0x1800044f2  mov     [rsp+70h+var_50], rax
0x1800044f7  mov     r8d, 7FFFFFFFh
0x1800044fd  call    FWEnumFirewallRules
0x180004502  mov     ebx, eax
0x180004504  test    eax, eax
0x180004506  jle     short loc_180004511
0x180004508  movzx   ebx, ax
0x18000450b  or      ebx, 80070000h
0x180004511  test    ebx, ebx
0x180004513  js      short loc_1800044C5
0x180004515  mov     r9d, [r14+18h]
0x180004519  mov     r8, rdi
0x18000451c  mov     edx, [rbp+var_28]
0x18000451f  mov     rcx, [rbp+var_20]
0x180004523  call    ?FwFindMatchingRuleWithRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x180004528  test    rax, rax
0x18000452b  jnz     short loc_180004549
0x18000452d  mov     r9d, [r14+18h]
0x180004531  mov     r8, rdi
0x180004534  mov     edx, [rbp+var_28]
0x180004537  mov     rcx, [rbp+var_20]
0x18000453b  call    ?FwFindMatchingRuleWithLocRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithLocRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x180004540  test    rax, rax
0x180004543  jz      loc_1800044C0
0x180004549  mov     rdx, [rax+10h]; unsigned __int16 *
0x18000454d  lea     r9, [rbp+var_38]; struct _tag_FW_RULE **
0x180004551  mov     rcx, [rbp+var_40]; void *
0x180004555  xor     r8d, r8d; int
0x180004558  call    ?FwRuleLookup@@YAJPEAXPEBGHPEAPEAU_tag_FW_RULE@@@Z; FwRuleLookup(void *,ushort const *,int,_tag_FW_RULE * *)
0x18000455d  mov     ebx, eax
0x18000455f  test    eax, eax
0x180004561  jns     loc_1800044B0
0x180004567  mov     edx, eax
0x180004569  lea     rcx, aFwrulesItem; "FwRules::Item"
0x180004570  call    cs:__imp_FwReportReturnError
0x180004576  mov     rsi, [rbp+var_38]
0x18000457a  jmp     loc_18000442C
0x18000457f  test    byte ptr [rcx+1Ch], 8
0x180004583  jz      short loc_1800045A1
0x180004585  mov     rcx, [rcx+10h]
0x180004589  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x180004590  mov     edx, 10h
0x180004595  call    WPP_SF_
0x18000459a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045a1  cmp     rcx, rbx
0x1800045a4  jz      loc_18000435E
0x1800045aa  test    byte ptr [rcx+1Ch], 4
0x1800045ae  jz      loc_18000435E
0x1800045b4  mov     rcx, [rcx+10h]
0x1800045b8  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x1800045bf  mov     edx, 11h
0x1800045c4  mov     r9, rdi
0x1800045c7  call    WPP_SF_S
0x1800045cc  jmp     loc_18000435E
0x1800045d1  mov     ebx, 80004003h
0x1800045d6  jmp     loc_1800044C5
0x1800045db  mov     ebx, 80070057h
0x1800045e0  jmp     loc_1800044C5
0x1800045e5  call    cs:__imp_GetThreadUILanguage
0x1800045eb  movzx   ebx, ax
0x1800045ee  call    cs:__imp_GetSystemDefaultLangID
0x1800045f4  cmp     ax, bx
0x1800045f7  jz      loc_1800044C0
0x1800045fd  jmp     loc_1800044CC
0x180004602  mov     edx, ebx
0x180004604  lea     rcx, aFwrulesItem; "FwRules::Item"
0x18000460b  call    cs:__imp_FwReportReturnError
0x180004611  mov     ebx, eax
0x180004613  jmp     loc_18000444F
```
