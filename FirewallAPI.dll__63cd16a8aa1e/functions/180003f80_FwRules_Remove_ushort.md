# FwRules::Remove(ushort *)

- ea: `0x180003f80`
- end: `0x1800042f5`
- name: `?Remove@FwRules@@UEAAJPEAG@Z`
- size: `885`
- prototype: `int(FwRules *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callees

- `0x180003f80`
- `0x180004620`
- `0x18000470c`
- `0x1800051c0`
- `0x180009080`
- `0x18000b8c0`
- `0x180010dc4`
- `0x18001c4dc`
- `0x1800277b0`
- `0x18003104c`
- `0x180037c6c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180004169`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180004169`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x180004172`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x180004172`
- `OLEAUT32!__imp_SysStringLen` at `0x180003fde`
- `OLEAUT32!__imp_SysStringLen` at `0x180003fde`
- `fwbase!FwBaseFree` at `0x18000410b`
- `fwbase!FwBaseFree` at `0x18000410b`
- `fwbase!FwResolveIndirectString` at `0x18000400e`
- `fwbase!FwResolveIndirectString` at `0x18000400e`
- `fwbase!FwReportReturnError` at `0x180004103`
- `fwbase!FwReportReturnError` at `0x1800042c4`
- `fwbase!FwReportReturnError` at `0x1800042e8`
- `fwbase!FwReportReturnError` at `0x180004103`
- `fwbase!FwReportReturnError` at `0x1800042c4`
- `fwbase!FwReportReturnError` at `0x1800042e8`
- `fwbase!FwStringCopy` at `0x180003ffa`
- `fwbase!FwStringCopy` at `0x180003ffa`

## string_xrefs

- `0x180003fe4`: `FwRules::Remove`
- `0x1800041fe`: `FwRules::Remove`
- `0x1800042bd`: `FwRules::Remove`
- `0x1800042d3`: `FwRules::Remove`
- `0x1800042e1`: `FwRules::Remove`

## pseudocode

```c
__int64 __fastcall FwRules::Remove(FwRules *this, unsigned __int16 *a2)
{
  struct _tag_FW_RULE *v2; // rsi
  FwPolicy2 *v5; // rcx
  int PolicyStoreHandle; // eax
  signed int v7; // edi
  int v8; // eax
  struct _tag_FW_RULE *MatchingRuleWithRuleName; // rax
  int v10; // eax
  __int64 v11; // rdx
  LANGID ThreadUILanguage; // bx
  int v14; // eax
  __int64 MatchingRuleWithLocRuleName; // rbx
  int v16; // eax
  void *v17; // [rsp+30h] [rbp-30h] BYREF
  struct _tag_FW_RULE *v18; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v19; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+48h] [rbp-18h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h] BYREF

  v2 = 0;
  v20 = 0;
  v18 = 0;
  v21 = 0;
  v17 = 0;
  v19 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)v5 + 2), 13, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids, a2);
  }
  if ( !SysStringLen(a2) )
  {
    v7 = -2147024809;
    goto LABEL_13;
  }
  PolicyStoreHandle = FwStringCopy(a2, &v21);
  v7 = PolicyStoreHandle;
  if ( PolicyStoreHandle < 0
    || (PolicyStoreHandle = FwResolveIndirectString(&v21), v7 = PolicyStoreHandle, PolicyStoreHandle < 0)
    || (PolicyStoreHandle = FwRules::GetPolicyStoreHandle(this, &v17), v7 = PolicyStoreHandle, PolicyStoreHandle < 0) )
  {
    v11 = (unsigned int)PolicyStoreHandle;
    goto LABEL_21;
  }
  v8 = FWEnumFirewallRules((_DWORD)v17, 196608, 0x7FFFFFFF, 7, (__int64)&v19, (__int64)&v20);
  v7 = v8;
  if ( v8 > 0 )
    v7 = (unsigned __int16)v8 | 0x80070000;
  if ( v7 < 0 )
  {
LABEL_13:
    v11 = (unsigned int)v7;
LABEL_21:
    FwReportReturnError("FwRules::Remove", v11);
    goto LABEL_15;
  }
  MatchingRuleWithRuleName = (struct _tag_FW_RULE *)FwRule::FwFindMatchingRuleWithRuleName(
                                                      v20,
                                                      v19,
                                                      v21,
                                                      *((unsigned int *)this + 6));
  if ( !MatchingRuleWithRuleName )
  {
    ThreadUILanguage = GetThreadUILanguage();
    if ( GetSystemDefaultLangID() == ThreadUILanguage )
      goto LABEL_15;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids, v21);
    FWFreeFirewallRules(v20);
    v20 = 0;
    v14 = FWEnumFirewallRules((_DWORD)v17, 196608, 0x7FFFFFFF, 0, (__int64)&v19, (__int64)&v20);
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( v7 < 0 )
    {
      v11 = (unsigned int)v7;
      goto LABEL_21;
    }
    MatchingRuleWithLocRuleName = FwRule::FwFindMatchingRuleWithRuleName(v20, v19, a2, *((unsigned int *)this + 6));
    if ( !MatchingRuleWithLocRuleName )
    {
      MatchingRuleWithLocRuleName = FwRule::FwFindMatchingRuleWithLocRuleName(v20, v19, a2, *((unsigned int *)this + 6));
      if ( !MatchingRuleWithLocRuleName )
        goto LABEL_15;
    }
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids);
    v16 = FwRuleLookup(v17, *(const unsigned __int16 **)(MatchingRuleWithLocRuleName + 16), 0, &v18);
    v7 = v16;
    if ( v16 < 0 )
    {
      FwReportReturnError("FwRules::Remove", (unsigned int)v16);
      v2 = v18;
      goto LABEL_15;
    }
    v2 = v18;
    MatchingRuleWithRuleName = v18;
    if ( !v18 )
      goto LABEL_15;
  }
  v10 = FWDeleteFirewallRule(v17, *((_QWORD *)MatchingRuleWithRuleName + 2));
  v7 = v10;
  if ( v10 > 0 )
    v7 = (unsigned __int16)v10 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_13;
LABEL_15:
  if ( v21 )
    FwBaseFree(v21);
  FWFreeFirewallRules(v20);
  FWFreeFirewallRules(v2);
  if ( v7 < 0 )
    return (unsigned int)FwReportReturnError("FwRules::Remove", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003f80  mov     [rsp-28h+arg_10], rbx
0x180003f85  push    rbp
0x180003f86  push    rsi
0x180003f87  push    rdi
0x180003f88  push    r13
0x180003f8a  push    r14
0x180003f8c  mov     rbp, rsp
0x180003f8f  sub     rsp, 60h
0x180003f93  mov     rax, cs:__security_cookie
0x180003f9a  xor     rax, rsp
0x180003f9d  mov     [rbp+var_8], rax
0x180003fa1  xor     esi, esi
0x180003fa3  mov     [rbp+var_18], 0
0x180003fab  mov     [rbp+var_28], rsi
0x180003faf  mov     r14, rdx
0x180003fb2  mov     [rbp+var_10], rsi
0x180003fb6  mov     r13, rcx
0x180003fb9  mov     [rbp+var_30], rsi
0x180003fbd  mov     [rbp+var_20], 0
0x180003fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fcb  lea     rbx, WPP_GLOBAL_Control
0x180003fd2  cmp     rcx, rbx
0x180003fd5  jnz     loc_180004121
0x180003fdb  mov     rcx, r14; pbstr
0x180003fde  call    cs:__imp_SysStringLen
0x180003fe4  lea     rbx, aFwrulesRemove; "FwRules::Remove"
0x180003feb  test    eax, eax
0x180003fed  jz      loc_18000422B
0x180003ff3  lea     rdx, [rbp+var_10]
0x180003ff7  mov     rcx, r14
0x180003ffa  call    cs:__imp_FwStringCopy
0x180004000  mov     edi, eax
0x180004002  test    eax, eax
0x180004004  js      loc_1800040FE
0x18000400a  lea     rcx, [rbp+var_10]
0x18000400e  call    cs:__imp_FwResolveIndirectString
0x180004014  mov     edi, eax
0x180004016  test    eax, eax
0x180004018  js      loc_1800040FE
0x18000401e  lea     rdx, [rbp+var_30]; void **
0x180004022  mov     rcx, r13; this
0x180004025  call    ?GetPolicyStoreHandle@FwRules@@AEAAJPEAPEAX@Z; FwRules::GetPolicyStoreHandle(void * *)
0x18000402a  mov     edi, eax
0x18000402c  test    eax, eax
0x18000402e  js      loc_1800040FE
0x180004034  mov     rcx, [rbp+var_30]
0x180004038  lea     rax, [rbp+var_18]
0x18000403c  mov     [rsp+60h+var_38], rax
0x180004041  mov     r9d, 7
0x180004047  lea     rax, [rbp+var_20]
0x18000404b  mov     edx, 30000h
0x180004050  mov     r8d, 7FFFFFFFh
0x180004056  mov     [rsp+60h+var_40], rax
0x18000405b  call    FWEnumFirewallRules
0x180004060  mov     edi, eax
0x180004062  test    eax, eax
0x180004064  jg      loc_180004113
0x18000406a  test    edi, edi
0x18000406c  js      short loc_1800040A6
0x18000406e  mov     r9d, [r13+18h]
0x180004072  mov     r8, [rbp+var_10]
0x180004076  mov     edx, [rbp+var_20]
0x180004079  mov     rcx, [rbp+var_18]
0x18000407d  call    ?FwFindMatchingRuleWithRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x180004082  test    rax, rax
0x180004085  jz      loc_180004169
0x18000408b  mov     rdx, [rax+10h]
0x18000408f  mov     rcx, [rbp+var_30]
0x180004093  call    FWDeleteFirewallRule
0x180004098  mov     edi, eax
0x18000409a  test    eax, eax
0x18000409c  jg      loc_18000415B
0x1800040a2  test    edi, edi
0x1800040a4  jns     short loc_1800040BA
0x1800040a6  mov     edx, edi
0x1800040a8  jmp     short loc_180004100
0x1800040aa  mov     rsi, [rbp+var_28]
0x1800040ae  mov     rax, rsi
0x1800040b1  test    rsi, rsi
0x1800040b4  jnz     loc_1800042D3
0x1800040ba  mov     rcx, [rbp+var_10]
0x1800040be  test    rcx, rcx
0x1800040c1  jnz     short loc_18000410B
0x1800040c3  mov     rcx, [rbp+var_18]
0x1800040c7  call    FWFreeFirewallRules
0x1800040cc  mov     rcx, rsi
0x1800040cf  call    FWFreeFirewallRules
0x1800040d4  test    edi, edi
0x1800040d6  js      loc_1800042DF
0x1800040dc  mov     eax, edi
0x1800040de  mov     rcx, [rbp+var_8]
0x1800040e2  xor     rcx, rsp; StackCookie
0x1800040e5  call    __security_check_cookie
0x1800040ea  mov     rbx, [rsp+60h+arg_10]
0x1800040f2  add     rsp, 60h
0x1800040f6  pop     r14
0x1800040f8  pop     r13
0x1800040fa  pop     rdi
0x1800040fb  pop     rsi
0x1800040fc  pop     rbp
0x1800040fd  retn
0x1800040fe  mov     edx, eax
0x180004100  mov     rcx, rbx
0x180004103  call    cs:__imp_FwReportReturnError
0x180004109  jmp     short loc_1800040BA
0x18000410b  call    cs:__imp_FwBaseFree
0x180004111  jmp     short loc_1800040C3
0x180004113  movzx   edi, ax
0x180004116  or      edi, 80070000h
0x18000411c  jmp     loc_18000406A
0x180004121  test    byte ptr [rcx+1Ch], 8
0x180004125  jnz     loc_18000420A
0x18000412b  cmp     rcx, rbx
0x18000412e  jz      loc_180003FDB
0x180004134  test    byte ptr [rcx+1Ch], 4
0x180004138  jz      loc_180003FDB
0x18000413e  mov     rcx, [rcx+10h]
0x180004142  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x180004149  mov     edx, 0Dh
0x18000414e  mov     r9, r14
0x180004151  call    WPP_SF_S
0x180004156  jmp     loc_180003FDB
0x18000415b  movzx   edi, ax
0x18000415e  or      edi, 80070000h
0x180004164  jmp     loc_1800040A2
0x180004169  call    cs:__imp_GetThreadUILanguage
0x18000416f  movzx   ebx, ax
0x180004172  call    cs:__imp_GetSystemDefaultLangID
0x180004178  cmp     ax, bx
0x18000417b  jz      loc_1800040BA
0x180004181  mov     rcx, cs:WPP_GLOBAL_Control
0x180004188  lea     rax, WPP_GLOBAL_Control
0x18000418f  cmp     rcx, rax
0x180004192  jz      short loc_1800041B3
0x180004194  test    byte ptr [rcx+1Ch], 4
0x180004198  jz      short loc_1800041B3
0x18000419a  mov     r9, [rbp+var_10]
0x18000419e  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x1800041a5  mov     rcx, [rcx+10h]
0x1800041a9  mov     edx, 0Eh
0x1800041ae  call    WPP_SF_S
0x1800041b3  mov     rcx, [rbp+var_18]
0x1800041b7  call    FWFreeFirewallRules
0x1800041bc  mov     rcx, [rbp+var_30]
0x1800041c0  lea     rax, [rbp+var_18]
0x1800041c4  mov     [rsp+60h+var_38], rax
0x1800041c9  xor     r9d, r9d
0x1800041cc  lea     rax, [rbp+var_20]
0x1800041d0  mov     [rbp+var_18], rsi
0x1800041d4  mov     edx, 30000h
0x1800041d9  mov     [rsp+60h+var_40], rax
0x1800041de  mov     r8d, 7FFFFFFFh
0x1800041e4  call    FWEnumFirewallRules
0x1800041e9  mov     edi, eax
0x1800041eb  test    eax, eax
0x1800041ed  jle     short loc_1800041F8
0x1800041ef  movzx   edi, ax
0x1800041f2  or      edi, 80070000h
0x1800041f8  test    edi, edi
0x1800041fa  jns     short loc_180004235
0x1800041fc  mov     edx, edi
0x1800041fe  lea     rcx, aFwrulesRemove; "FwRules::Remove"
0x180004205  jmp     loc_180004103
0x18000420a  mov     rcx, [rcx+10h]
0x18000420e  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x180004215  mov     edx, 0Ch
0x18000421a  call    WPP_SF_
0x18000421f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004226  jmp     loc_18000412B
0x18000422b  mov     edi, 80070057h
0x180004230  jmp     loc_1800040A6
0x180004235  mov     r9d, [r13+18h]
0x180004239  mov     r8, r14
0x18000423c  mov     edx, [rbp+var_20]
0x18000423f  mov     rcx, [rbp+var_18]
0x180004243  call    ?FwFindMatchingRuleWithRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x180004248  mov     rbx, rax
0x18000424b  test    rax, rax
0x18000424e  jnz     short loc_18000426F
0x180004250  mov     r9d, [r13+18h]
0x180004254  mov     r8, r14
0x180004257  mov     edx, [rbp+var_20]
0x18000425a  mov     rcx, [rbp+var_18]
0x18000425e  call    ?FwFindMatchingRuleWithLocRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithLocRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x180004263  mov     rbx, rax
0x180004266  test    rax, rax
0x180004269  jz      loc_1800040BA
0x18000426f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004276  lea     rax, WPP_GLOBAL_Control
0x18000427d  cmp     rcx, rax
0x180004280  jz      short loc_18000429D
0x180004282  test    byte ptr [rcx+1Ch], 4
0x180004286  jz      short loc_18000429D
0x180004288  mov     rcx, [rcx+10h]
0x18000428c  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x180004293  mov     edx, 0Fh
0x180004298  call    WPP_SF_
0x18000429d  mov     rdx, [rbx+10h]; unsigned __int16 *
0x1800042a1  lea     r9, [rbp+var_28]; struct _tag_FW_RULE **
0x1800042a5  mov     rcx, [rbp+var_30]; void *
0x1800042a9  xor     r8d, r8d; int
0x1800042ac  call    ?FwRuleLookup@@YAJPEAXPEBGHPEAPEAU_tag_FW_RULE@@@Z; FwRuleLookup(void *,ushort const *,int,_tag_FW_RULE * *)
0x1800042b1  mov     edi, eax
0x1800042b3  test    eax, eax
0x1800042b5  jns     loc_1800040AA
0x1800042bb  mov     edx, eax
0x1800042bd  lea     rcx, aFwrulesRemove; "FwRules::Remove"
0x1800042c4  call    cs:__imp_FwReportReturnError
0x1800042ca  mov     rsi, [rbp+var_28]
0x1800042ce  jmp     loc_1800040BA
0x1800042d3  lea     rbx, aFwrulesRemove; "FwRules::Remove"
0x1800042da  jmp     loc_18000408B
0x1800042df  mov     edx, edi
0x1800042e1  lea     rcx, aFwrulesRemove; "FwRules::Remove"
0x1800042e8  call    cs:__imp_FwReportReturnError
0x1800042ee  mov     edi, eax
0x1800042f0  jmp     loc_1800040DC
```
