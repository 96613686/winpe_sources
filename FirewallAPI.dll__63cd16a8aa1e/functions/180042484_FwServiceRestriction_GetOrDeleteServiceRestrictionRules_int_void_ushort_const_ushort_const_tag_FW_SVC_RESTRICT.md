# FwServiceRestriction::GetOrDeleteServiceRestrictionRules(int,void *,ushort const *,ushort const *,_tag_FW_SVC_RESTRICTION *)

- ea: `0x180042484`
- end: `0x180042739`
- name: `?GetOrDeleteServiceRestrictionRules@FwServiceRestriction@@AEAAJHPEAXPEBG1PEAU_tag_FW_SVC_RESTRICTION@@@Z`
- size: `693`
- prototype: `int(FwServiceRestriction *__hidden this, int, void *, const unsigned __int16 *, const unsigned __int16 *, struct _tag_FW_SVC_RESTRICTION *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042b70`
- `0x180042f30`

## callees

- `0x1800051c0`
- `0x180005954`
- `0x180009080`
- `0x18000b8c0`
- `0x1800277b0`
- `0x18003104c`
- `0x180042484`
- `0x1800428c8`
- `0x180043210`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004260c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180042633`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004260c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180042633`
- `fwbase!FwBaseFree` at `0x1800426d4`
- `fwbase!FwBaseFree` at `0x1800426d4`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x18004250d`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x18004250d`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800426e6`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800426f5`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800426e6`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800426f5`

## pseudocode

```c
__int64 __fastcall FwServiceRestriction::GetOrDeleteServiceRestrictionRules(
        FwServiceRestriction *this,
        int a2,
        void *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct _tag_FW_SVC_RESTRICTION *a6)
{
  const WCHAR *lpString2; // r14
  signed int ExpandedCanonicalLongPathName; // ebx
  FwPolicy2 *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  FwServiceRestriction *v14; // rcx
  struct _tag_FW_RULE *i; // rsi
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  PCNZWCH v20; // [rsp+30h] [rbp-20h] BYREF
  struct _tag_FW_RULE *v21; // [rsp+38h] [rbp-18h] BYREF
  int v22; // [rsp+40h] [rbp-10h] BYREF
  int v23; // [rsp+44h] [rbp-Ch] BYREF

  lpString2 = a5;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids);
  v21 = 0;
  *(_OWORD *)a6 = 0;
  v23 = 0;
  v20 = 0;
  *((_OWORD *)a6 + 1) = 0;
  v22 = 0;
  ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(a5, &v20, &v22);
  if ( ExpandedCanonicalLongPathName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 55;
      goto LABEL_40;
    }
    goto LABEL_41;
  }
  if ( v22 )
    lpString2 = v20;
  v13 = FWEnumFirewallRules((_DWORD)a3, 196608, 0x7FFFFFFF, 7, (__int64)&v23, (__int64)&v21);
  ExpandedCanonicalLongPathName = v13;
  if ( v13 > 0 )
    ExpandedCanonicalLongPathName = (unsigned __int16)v13 | 0x80070000;
  if ( ExpandedCanonicalLongPathName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 56;
      goto LABEL_40;
    }
    goto LABEL_41;
  }
  ExpandedCanonicalLongPathName = 0;
  for ( i = v21;
        i && (a2 || !*(_QWORD *)a6 || !*((_DWORD *)a6 + 2) || !*((_QWORD *)a6 + 2) || !*((_DWORD *)a6 + 6));
        i = *(struct _tag_FW_RULE **)i )
  {
    if ( (unsigned int)FwServiceRestriction::IsRestrictedServiceRule(v14, i)
      && CompareStringW(0x7Fu, 1u, *((PCNZWCH *)i + 34), -1, lpString2, -1) == 2
      && CompareStringW(0x7Fu, 1u, *((PCNZWCH *)i + 35), -1, a4, -1) == 2 )
    {
      if ( a2 )
      {
        v16 = FWDeleteFirewallRule(a3, *((_QWORD *)i + 2));
        if ( !v16 )
          continue;
        if ( v16 > 0 )
        {
          ExpandedCanonicalLongPathName = (unsigned __int16)v16 | 0x80070000;
          continue;
        }
LABEL_31:
        ExpandedCanonicalLongPathName = v16;
        continue;
      }
      if ( *((_DWORD *)i + 11) == 1 )
      {
        v16 = FwServiceRestriction::StoreSvcRestrictionRule(v14, i, 1, a6);
        if ( v16 >= 0 )
          continue;
        goto LABEL_31;
      }
      v17 = FwServiceRestriction::StoreSvcRestrictionRule(v14, i, 2, a6);
      if ( v17 < 0 )
        ExpandedCanonicalLongPathName = v17;
    }
  }
  if ( ExpandedCanonicalLongPathName < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 57;
LABEL_40:
      WPP_SF_d(
        *((_QWORD *)v11 + 2),
        v12,
        WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids,
        (unsigned int)ExpandedCanonicalLongPathName);
    }
  }
LABEL_41:
  FwBaseFree(v20);
  if ( ExpandedCanonicalLongPathName < 0 )
  {
    if ( *(_QWORD *)a6 )
      FwFreeWFRule(*(_QWORD *)a6);
    v18 = *((_QWORD *)a6 + 2);
    if ( v18 )
      FwFreeWFRule(v18);
    *(_OWORD *)a6 = 0;
    *((_OWORD *)a6 + 1) = 0;
  }
  if ( v21 )
    FWFreeFirewallRules(v21);
  return (unsigned int)ExpandedCanonicalLongPathName;
}

```

## disassembly

```asm
0x180042484  mov     [rsp-38h+arg_0], rbx
0x180042489  push    rbp
0x18004248a  push    rsi
0x18004248b  push    rdi
0x18004248c  push    r12
0x18004248e  push    r13
0x180042490  push    r14
0x180042492  push    r15
0x180042494  mov     rbp, rsp
0x180042497  sub     rsp, 50h
0x18004249b  mov     rax, cs:__security_cookie
0x1800424a2  xor     rax, rsp
0x1800424a5  mov     [rbp+var_8], rax
0x1800424a9  mov     rdi, [rbp+arg_28]
0x1800424ad  mov     r13, r9
0x1800424b0  mov     r14, [rbp+arg_20]
0x1800424b4  mov     r12, r8
0x1800424b7  mov     r15d, edx
0x1800424ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800424c1  lea     rax, WPP_GLOBAL_Control
0x1800424c8  cmp     rcx, rax
0x1800424cb  jz      short loc_1800424E8
0x1800424cd  test    byte ptr [rcx+1Ch], 8
0x1800424d1  jz      short loc_1800424E8
0x1800424d3  mov     rcx, [rcx+10h]
0x1800424d7  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x1800424de  mov     edx, 36h ; '6'
0x1800424e3  call    WPP_SF_
0x1800424e8  xor     esi, esi
0x1800424ea  lea     r8, [rbp+var_10]
0x1800424ee  xorps   xmm0, xmm0
0x1800424f1  mov     [rbp+var_18], rsi
0x1800424f5  movups  xmmword ptr [rdi], xmm0
0x1800424f8  lea     rdx, [rbp+var_20]
0x1800424fc  mov     [rbp+var_C], esi
0x1800424ff  mov     rcx, r14
0x180042502  mov     [rbp+var_20], rsi
0x180042506  movups  xmmword ptr [rdi+10h], xmm0
0x18004250a  mov     [rbp+var_10], esi
0x18004250d  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x180042513  mov     ebx, eax
0x180042515  test    eax, eax
0x180042517  jns     short loc_180042542
0x180042519  mov     rcx, cs:WPP_GLOBAL_Control
0x180042520  lea     rax, WPP_GLOBAL_Control
0x180042527  cmp     rcx, rax
0x18004252a  jz      loc_1800426D0
0x180042530  test    byte ptr [rcx+1Ch], 1
0x180042534  jz      loc_1800426D0
0x18004253a  lea     edx, [rsi+37h]
0x18004253d  jmp     loc_1800426BD
0x180042542  cmp     [rbp+var_10], esi
0x180042545  lea     rax, [rbp+var_18]
0x180042549  mov     qword ptr [rsp+50h+cchCount2], rax
0x18004254e  mov     r9d, 7
0x180042554  cmovnz  r14, [rbp+var_20]
0x180042559  lea     rax, [rbp+var_C]
0x18004255d  mov     edx, 30000h
0x180042562  mov     [rsp+50h+lpString2], rax
0x180042567  mov     r8d, 7FFFFFFFh
0x18004256d  mov     rcx, r12
0x180042570  call    FWEnumFirewallRules
0x180042575  mov     ebx, eax
0x180042577  test    eax, eax
0x180042579  jle     short loc_180042584
0x18004257b  movzx   ebx, ax
0x18004257e  or      ebx, 80070000h
0x180042584  test    ebx, ebx
0x180042586  jns     short loc_1800425B3
0x180042588  mov     rcx, cs:WPP_GLOBAL_Control
0x18004258f  lea     rax, WPP_GLOBAL_Control
0x180042596  cmp     rcx, rax
0x180042599  jz      loc_1800426D0
0x18004259f  test    byte ptr [rcx+1Ch], 1
0x1800425a3  jz      loc_1800426D0
0x1800425a9  mov     edx, 38h ; '8'
0x1800425ae  jmp     loc_1800426BD
0x1800425b3  mov     ebx, esi
0x1800425b5  mov     rsi, [rbp+var_18]
0x1800425b9  jmp     loc_180042692
0x1800425be  test    r15d, r15d
0x1800425c1  jnz     short loc_1800425E0
0x1800425c3  cmp     qword ptr [rdi], 0
0x1800425c7  jz      short loc_1800425E0
0x1800425c9  cmp     [rdi+8], r15d
0x1800425cd  jz      short loc_1800425E0
0x1800425cf  cmp     qword ptr [rdi+10h], 0
0x1800425d4  jz      short loc_1800425E0
0x1800425d6  cmp     [rdi+18h], r15d
0x1800425da  jnz     loc_18004269B
0x1800425e0  mov     rdx, rsi; struct _tag_FW_RULE *
0x1800425e3  call    ?IsRestrictedServiceRule@FwServiceRestriction@@AEAAHPEAU_tag_FW_RULE@@@Z; FwServiceRestriction::IsRestrictedServiceRule(_tag_FW_RULE *)
0x1800425e8  test    eax, eax
0x1800425ea  jz      loc_18004268F
0x1800425f0  mov     r8, [rsi+110h]; lpString1
0x1800425f7  or      eax, 0FFFFFFFFh
0x1800425fa  mov     [rsp+50h+cchCount2], eax; cchCount2
0x1800425fe  mov     r9d, eax; cchCount1
0x180042601  mov     [rsp+50h+lpString2], r14; lpString2
0x180042606  lea     edx, [rax+2]; dwCmpFlags
0x180042609  lea     ecx, [rdx+7Eh]; Locale
0x18004260c  call    cs:__imp_CompareStringW
0x180042612  cmp     eax, 2
0x180042615  jnz     short loc_18004268F
0x180042617  mov     r8, [rsi+118h]; lpString1
0x18004261e  or      eax, 0FFFFFFFFh
0x180042621  mov     [rsp+50h+cchCount2], eax; cchCount2
0x180042625  mov     r9d, eax; cchCount1
0x180042628  mov     [rsp+50h+lpString2], r13; lpString2
0x18004262d  lea     edx, [rax+2]; dwCmpFlags
0x180042630  lea     ecx, [rdx+7Eh]; Locale
0x180042633  call    cs:__imp_CompareStringW
0x180042639  cmp     eax, 2
0x18004263c  jnz     short loc_18004268F
0x18004263e  test    r15d, r15d
0x180042641  jz      short loc_180042660
0x180042643  mov     rdx, [rsi+10h]
0x180042647  mov     rcx, r12
0x18004264a  call    FWDeleteFirewallRule
0x18004264f  test    eax, eax
0x180042651  jz      short loc_18004268F
0x180042653  jle     short loc_18004267B
0x180042655  movzx   ebx, ax
0x180042658  or      ebx, 80070000h
0x18004265e  jmp     short loc_18004268F
0x180042660  cmp     dword ptr [rsi+2Ch], 1
0x180042664  mov     r9, rdi
0x180042667  mov     rdx, rsi
0x18004266a  jnz     short loc_18004267F
0x18004266c  mov     r8d, 1
0x180042672  call    ?StoreSvcRestrictionRule@FwServiceRestriction@@AEAAJPEAU_tag_FW_RULE@@W4_tag_FW_DIRECTION@@PEAU_tag_FW_SVC_RESTRICTION@@@Z; FwServiceRestriction::StoreSvcRestrictionRule(_tag_FW_RULE *,_tag_FW_DIRECTION,_tag_FW_SVC_RESTRICTION *)
0x180042677  test    eax, eax
0x180042679  jns     short loc_18004268F
0x18004267b  mov     ebx, eax
0x18004267d  jmp     short loc_18004268F
0x18004267f  mov     r8d, 2
0x180042685  call    ?StoreSvcRestrictionRule@FwServiceRestriction@@AEAAJPEAU_tag_FW_RULE@@W4_tag_FW_DIRECTION@@PEAU_tag_FW_SVC_RESTRICTION@@@Z; FwServiceRestriction::StoreSvcRestrictionRule(_tag_FW_RULE *,_tag_FW_DIRECTION,_tag_FW_SVC_RESTRICTION *)
0x18004268a  test    eax, eax
0x18004268c  cmovs   ebx, eax
0x18004268f  mov     rsi, [rsi]
0x180042692  test    rsi, rsi
0x180042695  jnz     loc_1800425BE
0x18004269b  test    ebx, ebx
0x18004269d  jns     short loc_1800426D0
0x18004269f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800426a6  lea     rax, WPP_GLOBAL_Control
0x1800426ad  cmp     rcx, rax
0x1800426b0  jz      short loc_1800426D0
0x1800426b2  test    byte ptr [rcx+1Ch], 1
0x1800426b6  jz      short loc_1800426D0
0x1800426b8  mov     edx, 39h ; '9'
0x1800426bd  mov     rcx, [rcx+10h]
0x1800426c1  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x1800426c8  mov     r9d, ebx
0x1800426cb  call    WPP_SF_d
0x1800426d0  mov     rcx, [rbp+var_20]
0x1800426d4  call    cs:__imp_FwBaseFree
0x1800426da  test    ebx, ebx
0x1800426dc  jns     short loc_180042705
0x1800426de  mov     rcx, [rdi]
0x1800426e1  test    rcx, rcx
0x1800426e4  jz      short loc_1800426EC
0x1800426e6  call    cs:__imp_FwFreeWFRule
0x1800426ec  mov     rcx, [rdi+10h]
0x1800426f0  test    rcx, rcx
0x1800426f3  jz      short loc_1800426FB
0x1800426f5  call    cs:__imp_FwFreeWFRule
0x1800426fb  xorps   xmm0, xmm0
0x1800426fe  movups  xmmword ptr [rdi], xmm0
0x180042701  movups  xmmword ptr [rdi+10h], xmm0
0x180042705  mov     rcx, [rbp+var_18]
0x180042709  test    rcx, rcx
0x18004270c  jz      short loc_180042713
0x18004270e  call    FWFreeFirewallRules
0x180042713  mov     eax, ebx
0x180042715  mov     rcx, [rbp+var_8]
0x180042719  xor     rcx, rsp; StackCookie
0x18004271c  call    __security_check_cookie
0x180042721  mov     rbx, [rsp+50h+arg_0]
0x180042729  add     rsp, 50h
0x18004272d  pop     r15
0x18004272f  pop     r14
0x180042731  pop     r13
0x180042733  pop     r12
0x180042735  pop     rdi
0x180042736  pop     rsi
0x180042737  pop     rbp
0x180042738  retn
```
