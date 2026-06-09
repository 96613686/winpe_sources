# FwAuthApp::SetRules(_tag_FW_RULE const *,_tag_FW_RULE const *)

- ea: `0x18000270c`
- end: `0x1800029e8`
- name: `?SetRules@FwAuthApp@@AEAAJPEBU_tag_FW_RULE@@0@Z`
- size: `732`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this, const struct _tag_FW_RULE *, const struct _tag_FW_RULE *)`
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800018d0`
- `0x180001b10`
- `0x180023c6c`
- `0x180040f40`
- `0x1800411e0`
- `0x180041490`

## callees

- `0x18000270c`
- `0x180003520`
- `0x180003b4c`
- `0x18000c560`
- `0x180014368`
- `0x180023d28`
- `0x1800277b0`
- `0x18002e484`
- `0x18003063c`
- `0x18003104c`

## import_xrefs

- `fwbase!FwBaseFree` at `0x180002828`
- `fwbase!FwBaseFree` at `0x180002889`
- `fwbase!FwBaseFree` at `0x1800029af`
- `fwbase!FwBaseFree` at `0x180002828`
- `fwbase!FwBaseFree` at `0x180002889`
- `fwbase!FwBaseFree` at `0x1800029af`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800028cc`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800028cc`
- `fwbase!FwReportReturnError` at `0x18000291a`
- `fwbase!FwReportReturnError` at `0x1800029c7`
- `fwbase!FwReportReturnError` at `0x18000291a`
- `fwbase!FwReportReturnError` at `0x1800029c7`
- `fwbase!FwStringCopy` at `0x18000283e`
- `fwbase!FwStringCopy` at `0x18000289f`
- `fwbase!FwStringCopy` at `0x18000283e`
- `fwbase!FwStringCopy` at `0x18000289f`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002924`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18000292e`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18000297b`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002985`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002924`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18000292e`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18000297b`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002985`
- `FWPolicyIOMgr!FwCopyRule` at `0x18000275f`
- `FWPolicyIOMgr!FwCopyRule` at `0x18000277d`
- `FWPolicyIOMgr!FwCopyRule` at `0x18000275f`
- `FWPolicyIOMgr!FwCopyRule` at `0x18000277d`

## pseudocode

```c
__int64 __fastcall FwAuthApp::SetRules(FwAuthApp *this, const struct _tag_FW_RULE *a2, const struct _tag_FW_RULE *a3)
{
  int ExpandedCanonicalLongPathName; // eax
  signed int v6; // ebx
  FwAuthApp *v7; // rcx
  FwAuthApp *v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  struct _tag_FW_RULE *v14; // [rsp+30h] [rbp-30h] BYREF
  struct _tag_FW_RULE *v15; // [rsp+38h] [rbp-28h] BYREF
  void *v16; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h] BYREF
  int v18; // [rsp+50h] [rbp-10h] BYREF

  v14 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  ExpandedCanonicalLongPathName = FwCopyRule(a2, &v14);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_23;
  ExpandedCanonicalLongPathName = FwCopyRule(a3, &v15);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_23;
  if ( !*((_DWORD *)this + 22) )
    goto LABEL_30;
  ExpandedCanonicalLongPathName = FwAuthApp::ValidateAuthAppRule(v7, v14);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_23;
  ExpandedCanonicalLongPathName = FwAuthApp::ValidateAuthAppRule(v8, v15);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_23;
  v9 = FWOpenPolicyStore(0x221u, 0, 2u, 2u, 0, &v16);
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( v6 >= 0 )
  {
    v11 = *((_QWORD *)this + 9);
    if ( (~*((_DWORD *)this + 16) & *(_DWORD *)(v11 + 40)) != 0 )
    {
      ExpandedCanonicalLongPathName = FwSplitRule(v16, (struct _tag_FW_RULE *)v11, *((_DWORD *)this + 16));
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_23;
      FwBaseFree(*((_QWORD *)v14 + 2));
      ExpandedCanonicalLongPathName = FwStringCopy(*(_QWORD *)(*((_QWORD *)this + 9) + 16LL), (char *)v14 + 16);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_23;
      *((_DWORD *)v14 + 10) = *(_DWORD *)(*((_QWORD *)this + 9) + 40LL);
    }
    v12 = *((_QWORD *)this + 10);
    if ( (~*((_DWORD *)this + 16) & *(_DWORD *)(v12 + 40)) == 0 )
    {
LABEL_18:
      ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(*((_QWORD *)v14 + 34), &v17, &v18);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_23;
      if ( v18 == 1 )
        DeleteAllMatchingAuthAppRules(v16, v17, *((unsigned int *)this + 16));
      ExpandedCanonicalLongPathName = SaveRule(v14, v16);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_23;
      ExpandedCanonicalLongPathName = SaveRule(v15, v16);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_23;
LABEL_30:
      FwFreeWFRule(*((_QWORD *)this + 9));
      FwFreeWFRule(*((_QWORD *)this + 10));
      *((_QWORD *)this + 9) = v14;
      *((_QWORD *)this + 10) = v15;
      v14 = 0;
      v15 = 0;
      goto LABEL_31;
    }
    ExpandedCanonicalLongPathName = FwSplitRule(v16, (struct _tag_FW_RULE *)v12, *((_DWORD *)this + 16));
    v6 = ExpandedCanonicalLongPathName;
    if ( ExpandedCanonicalLongPathName >= 0 )
    {
      FwBaseFree(*((_QWORD *)v15 + 2));
      ExpandedCanonicalLongPathName = FwStringCopy(*(_QWORD *)(*((_QWORD *)this + 10) + 16LL), (char *)v15 + 16);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName >= 0 )
      {
        *((_DWORD *)v15 + 10) = *(_DWORD *)(*((_QWORD *)this + 10) + 40LL);
        goto LABEL_18;
      }
    }
LABEL_23:
    v10 = (unsigned int)ExpandedCanonicalLongPathName;
    goto LABEL_24;
  }
  v10 = (unsigned int)v6;
LABEL_24:
  FwReportReturnError("FwAuthApp::SetRules", v10);
  FwFreeWFRule(v14);
  FwFreeWFRule(v15);
  if ( v6 == -2147024891 && (unsigned int)AccessDeniedShouldBeSuppressed() )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_91ff551a1acd3d9c8802511a4aa67041_Traceguids);
    v6 = 0;
  }
LABEL_31:
  FwBaseFree(v17);
  CloseLocalPolicyStore(v16);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::SetRules", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000270c  push    rbp
0x18000270e  push    rbx
0x18000270f  push    rsi
0x180002710  push    rdi
0x180002711  push    r15
0x180002713  mov     rbp, rsp
0x180002716  sub     rsp, 60h
0x18000271a  mov     rax, cs:__security_cookie
0x180002721  xor     rax, rsp
0x180002724  mov     [rbp+var_8], rax
0x180002728  mov     rax, rdx
0x18000272b  mov     [rbp+var_30], 0
0x180002733  mov     rdi, rcx
0x180002736  mov     [rbp+var_28], 0
0x18000273e  mov     rcx, rax
0x180002741  mov     [rbp+var_18], 0
0x180002749  lea     rdx, [rbp+var_30]
0x18000274d  mov     [rbp+var_10], 0
0x180002754  mov     rsi, r8
0x180002757  mov     [rbp+var_20], 0
0x18000275f  call    cs:__imp_FwCopyRule
0x180002765  lea     r15, aFwauthappSetru; "FwAuthApp::SetRules"
0x18000276c  mov     ebx, eax
0x18000276e  test    eax, eax
0x180002770  js      loc_180002915
0x180002776  lea     rdx, [rbp+var_28]
0x18000277a  mov     rcx, rsi
0x18000277d  call    cs:__imp_FwCopyRule
0x180002783  mov     ebx, eax
0x180002785  test    eax, eax
0x180002787  js      loc_180002915
0x18000278d  cmp     dword ptr [rdi+58h], 0
0x180002791  jz      loc_180002977
0x180002797  mov     rdx, [rbp+var_30]; struct _tag_FW_RULE *
0x18000279b  call    ?ValidateAuthAppRule@FwAuthApp@@AEAAJPEBU_tag_FW_RULE@@@Z; FwAuthApp::ValidateAuthAppRule(_tag_FW_RULE const *)
0x1800027a0  mov     ebx, eax
0x1800027a2  test    eax, eax
0x1800027a4  js      loc_180002915
0x1800027aa  mov     rdx, [rbp+var_28]; struct _tag_FW_RULE *
0x1800027ae  call    ?ValidateAuthAppRule@FwAuthApp@@AEAAJPEBU_tag_FW_RULE@@@Z; FwAuthApp::ValidateAuthAppRule(_tag_FW_RULE const *)
0x1800027b3  mov     ebx, eax
0x1800027b5  test    eax, eax
0x1800027b7  js      loc_180002915
0x1800027bd  xor     edx, edx
0x1800027bf  lea     rax, [rbp+var_20]
0x1800027c3  mov     [rsp+60h+var_38], rax
0x1800027c8  mov     ecx, 221h
0x1800027cd  mov     [rsp+60h+var_40], 0
0x1800027d5  lea     r9d, [rdx+2]
0x1800027d9  mov     r8d, r9d
0x1800027dc  call    FWOpenPolicyStore
0x1800027e1  mov     ebx, eax
0x1800027e3  test    eax, eax
0x1800027e5  jle     short loc_1800027F0
0x1800027e7  movzx   ebx, ax
0x1800027ea  or      ebx, 80070000h
0x1800027f0  test    ebx, ebx
0x1800027f2  jns     short loc_1800027FB
0x1800027f4  mov     edx, ebx
0x1800027f6  jmp     loc_180002917
0x1800027fb  mov     r8d, [rdi+40h]; unsigned int
0x1800027ff  mov     eax, r8d
0x180002802  mov     rdx, [rdi+48h]; struct _tag_FW_RULE *
0x180002806  not     eax
0x180002808  test    [rdx+28h], eax
0x18000280b  jz      short loc_18000285C
0x18000280d  mov     rcx, [rbp+var_20]; void *
0x180002811  call    ?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; FwSplitRule(void *,_tag_FW_RULE *,ulong)
0x180002816  mov     ebx, eax
0x180002818  test    eax, eax
0x18000281a  js      loc_180002915
0x180002820  mov     rcx, [rbp+var_30]
0x180002824  mov     rcx, [rcx+10h]
0x180002828  call    cs:__imp_FwBaseFree
0x18000282e  mov     rcx, [rdi+48h]
0x180002832  mov     rdx, [rbp+var_30]
0x180002836  add     rdx, 10h
0x18000283a  mov     rcx, [rcx+10h]
0x18000283e  call    cs:__imp_FwStringCopy
0x180002844  mov     ebx, eax
0x180002846  test    eax, eax
0x180002848  js      loc_180002915
0x18000284e  mov     rax, [rdi+48h]
0x180002852  mov     ecx, [rax+28h]
0x180002855  mov     rax, [rbp+var_30]
0x180002859  mov     [rax+28h], ecx
0x18000285c  mov     r8d, [rdi+40h]; unsigned int
0x180002860  mov     eax, r8d
0x180002863  mov     rdx, [rdi+50h]; struct _tag_FW_RULE *
0x180002867  not     eax
0x180002869  test    [rdx+28h], eax
0x18000286c  jz      short loc_1800028B9
0x18000286e  mov     rcx, [rbp+var_20]; void *
0x180002872  call    ?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; FwSplitRule(void *,_tag_FW_RULE *,ulong)
0x180002877  mov     ebx, eax
0x180002879  test    eax, eax
0x18000287b  js      loc_180002915
0x180002881  mov     rcx, [rbp+var_28]
0x180002885  mov     rcx, [rcx+10h]
0x180002889  call    cs:__imp_FwBaseFree
0x18000288f  mov     rcx, [rdi+50h]
0x180002893  mov     rdx, [rbp+var_28]
0x180002897  add     rdx, 10h
0x18000289b  mov     rcx, [rcx+10h]
0x18000289f  call    cs:__imp_FwStringCopy
0x1800028a5  mov     ebx, eax
0x1800028a7  test    eax, eax
0x1800028a9  js      short loc_180002915
0x1800028ab  mov     rax, [rdi+50h]
0x1800028af  mov     ecx, [rax+28h]
0x1800028b2  mov     rax, [rbp+var_28]
0x1800028b6  mov     [rax+28h], ecx
0x1800028b9  mov     rcx, [rbp+var_30]
0x1800028bd  lea     r8, [rbp+var_10]
0x1800028c1  lea     rdx, [rbp+var_18]
0x1800028c5  mov     rcx, [rcx+110h]
0x1800028cc  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x1800028d2  mov     ebx, eax
0x1800028d4  test    eax, eax
0x1800028d6  js      short loc_180002915
0x1800028d8  cmp     [rbp+var_10], 1
0x1800028dc  jnz     short loc_1800028EF
0x1800028de  mov     r8d, [rdi+40h]
0x1800028e2  mov     rdx, [rbp+var_18]
0x1800028e6  mov     rcx, [rbp+var_20]
0x1800028ea  call    ?DeleteAllMatchingAuthAppRules@@YAJPEAXPEAGW4_tag_FW_PROFILE_TYPE@@@Z; DeleteAllMatchingAuthAppRules(void *,ushort *,_tag_FW_PROFILE_TYPE)
0x1800028ef  mov     rdx, [rbp+var_20]; void *
0x1800028f3  mov     rcx, [rbp+var_30]; struct _tag_FW_RULE *
0x1800028f7  call    ?SaveRule@@YAJPEAU_tag_FW_RULE@@PEAX@Z; SaveRule(_tag_FW_RULE *,void *)
0x1800028fc  mov     ebx, eax
0x1800028fe  test    eax, eax
0x180002900  js      short loc_180002915
0x180002902  mov     rdx, [rbp+var_20]; void *
0x180002906  mov     rcx, [rbp+var_28]; struct _tag_FW_RULE *
0x18000290a  call    ?SaveRule@@YAJPEAU_tag_FW_RULE@@PEAX@Z; SaveRule(_tag_FW_RULE *,void *)
0x18000290f  mov     ebx, eax
0x180002911  test    eax, eax
0x180002913  jns     short loc_180002977
0x180002915  mov     edx, eax
0x180002917  mov     rcx, r15
0x18000291a  call    cs:__imp_FwReportReturnError
0x180002920  mov     rcx, [rbp+var_30]
0x180002924  call    cs:__imp_FwFreeWFRule
0x18000292a  mov     rcx, [rbp+var_28]
0x18000292e  call    cs:__imp_FwFreeWFRule
0x180002934  cmp     ebx, 80070005h
0x18000293a  jnz     short loc_1800029AB
0x18000293c  call    ?AccessDeniedShouldBeSuppressed@@YAHXZ; AccessDeniedShouldBeSuppressed(void)
0x180002941  test    eax, eax
0x180002943  jz      short loc_1800029AB
0x180002945  mov     rcx, cs:WPP_GLOBAL_Control
0x18000294c  lea     rax, WPP_GLOBAL_Control
0x180002953  cmp     rcx, rax
0x180002956  jz      short loc_180002973
0x180002958  test    byte ptr [rcx+1Ch], 2
0x18000295c  jz      short loc_180002973
0x18000295e  mov     rcx, [rcx+10h]
0x180002962  lea     r8, WPP_91ff551a1acd3d9c8802511a4aa67041_Traceguids
0x180002969  mov     edx, 0Ah
0x18000296e  call    WPP_SF_
0x180002973  xor     ebx, ebx
0x180002975  jmp     short loc_1800029AB
0x180002977  mov     rcx, [rdi+48h]
0x18000297b  call    cs:__imp_FwFreeWFRule
0x180002981  mov     rcx, [rdi+50h]
0x180002985  call    cs:__imp_FwFreeWFRule
0x18000298b  mov     rax, [rbp+var_30]
0x18000298f  mov     [rdi+48h], rax
0x180002993  mov     rax, [rbp+var_28]
0x180002997  mov     [rdi+50h], rax
0x18000299b  mov     [rbp+var_30], 0
0x1800029a3  mov     [rbp+var_28], 0
0x1800029ab  mov     rcx, [rbp+var_18]
0x1800029af  call    cs:__imp_FwBaseFree
0x1800029b5  mov     rcx, [rbp+var_20]; void *
0x1800029b9  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x1800029be  test    ebx, ebx
0x1800029c0  jns     short loc_1800029CF
0x1800029c2  mov     edx, ebx
0x1800029c4  mov     rcx, r15
0x1800029c7  call    cs:__imp_FwReportReturnError
0x1800029cd  mov     ebx, eax
0x1800029cf  mov     eax, ebx
0x1800029d1  mov     rcx, [rbp+var_8]
0x1800029d5  xor     rcx, rsp; StackCookie
0x1800029d8  call    __security_check_cookie
0x1800029dd  add     rsp, 60h
0x1800029e1  pop     r15
0x1800029e3  pop     rdi
0x1800029e4  pop     rsi
0x1800029e5  pop     rbx
0x1800029e6  pop     rbp
0x1800029e7  retn
```
