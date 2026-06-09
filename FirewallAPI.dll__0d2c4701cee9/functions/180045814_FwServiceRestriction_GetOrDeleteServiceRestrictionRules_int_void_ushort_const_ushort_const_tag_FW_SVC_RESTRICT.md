# FwServiceRestriction::GetOrDeleteServiceRestrictionRules(int,void *,ushort const *,ushort const *,_tag_FW_SVC_RESTRICTION *)

- ea: `0x180045814`
- end: `0x180045aee`
- name: `?GetOrDeleteServiceRestrictionRules@FwServiceRestriction@@AEAAJHPEAXPEBG1PEAU_tag_FW_SVC_RESTRICTION@@@Z`
- size: `730`
- prototype: `int(FwServiceRestriction *__hidden this, int, void *, const unsigned __int16 *, const unsigned __int16 *, struct _tag_FW_SVC_RESTRICTION *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045f40`
- `0x180046320`

## callees

- `0x180005630`
- `0x180005e0c`
- `0x180009780`
- `0x18000c3f0`
- `0x1800294b0`
- `0x18003336c`
- `0x180045814`
- `0x180045c88`
- `0x180046618`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800459a2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800459cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800459a2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800459cf`
- `fwbase!FwBaseFree` at `0x180045a76`
- `fwbase!FwBaseFree` at `0x180045a76`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x18004589d`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x18004589d`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180045a8e`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180045aa3`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180045a8e`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180045aa3`

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
0x180045814  mov     [rsp-38h+arg_0], rbx
0x180045819  push    rbp
0x18004581a  push    rsi
0x18004581b  push    rdi
0x18004581c  push    r12
0x18004581e  push    r13
0x180045820  push    r14
0x180045822  push    r15
0x180045824  mov     rbp, rsp
0x180045827  sub     rsp, 50h
0x18004582b  mov     rax, cs:__security_cookie
0x180045832  xor     rax, rsp
0x180045835  mov     [rbp+var_8], rax
0x180045839  mov     rdi, [rbp+arg_28]
0x18004583d  mov     r13, r9
0x180045840  mov     r14, [rbp+arg_20]
0x180045844  mov     r12, r8
0x180045847  mov     r15d, edx
0x18004584a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045851  lea     rax, WPP_GLOBAL_Control
0x180045858  cmp     rcx, rax
0x18004585b  jz      short loc_180045878
0x18004585d  test    byte ptr [rcx+1Ch], 8
0x180045861  jz      short loc_180045878
0x180045863  mov     rcx, [rcx+10h]
0x180045867  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x18004586e  mov     edx, 36h ; '6'
0x180045873  call    WPP_SF_
0x180045878  xor     esi, esi
0x18004587a  lea     r8, [rbp+var_10]
0x18004587e  xorps   xmm0, xmm0
0x180045881  mov     [rbp+var_18], rsi
0x180045885  movups  xmmword ptr [rdi], xmm0
0x180045888  lea     rdx, [rbp+var_20]
0x18004588c  mov     [rbp+var_C], esi
0x18004588f  mov     rcx, r14
0x180045892  mov     [rbp+var_20], rsi
0x180045896  movups  xmmword ptr [rdi+10h], xmm0
0x18004589a  mov     [rbp+var_10], esi
0x18004589d  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x1800458a4  nop     dword ptr [rax+rax+00h]
0x1800458a9  mov     ebx, eax
0x1800458ab  test    eax, eax
0x1800458ad  jns     short loc_1800458D8
0x1800458af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800458b6  lea     rax, WPP_GLOBAL_Control
0x1800458bd  cmp     rcx, rax
0x1800458c0  jz      loc_180045A72
0x1800458c6  test    byte ptr [rcx+1Ch], 1
0x1800458ca  jz      loc_180045A72
0x1800458d0  lea     edx, [rsi+37h]
0x1800458d3  jmp     loc_180045A5F
0x1800458d8  cmp     [rbp+var_10], esi
0x1800458db  lea     rax, [rbp+var_18]
0x1800458df  mov     qword ptr [rsp+50h+cchCount2], rax
0x1800458e4  mov     r9d, 7
0x1800458ea  cmovnz  r14, [rbp+var_20]
0x1800458ef  lea     rax, [rbp+var_C]
0x1800458f3  mov     edx, 30000h
0x1800458f8  mov     [rsp+50h+lpString2], rax
0x1800458fd  mov     r8d, 7FFFFFFFh
0x180045903  mov     rcx, r12
0x180045906  call    FWEnumFirewallRules
0x18004590b  mov     ebx, eax
0x18004590d  test    eax, eax
0x18004590f  jle     short loc_18004591A
0x180045911  movzx   ebx, ax
0x180045914  or      ebx, 80070000h
0x18004591a  test    ebx, ebx
0x18004591c  jns     short loc_180045949
0x18004591e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045925  lea     rax, WPP_GLOBAL_Control
0x18004592c  cmp     rcx, rax
0x18004592f  jz      loc_180045A72
0x180045935  test    byte ptr [rcx+1Ch], 1
0x180045939  jz      loc_180045A72
0x18004593f  mov     edx, 38h ; '8'
0x180045944  jmp     loc_180045A5F
0x180045949  mov     ebx, esi
0x18004594b  mov     rsi, [rbp+var_18]
0x18004594f  jmp     loc_180045A34
0x180045954  test    r15d, r15d
0x180045957  jnz     short loc_180045976
0x180045959  cmp     qword ptr [rdi], 0
0x18004595d  jz      short loc_180045976
0x18004595f  cmp     [rdi+8], r15d
0x180045963  jz      short loc_180045976
0x180045965  cmp     qword ptr [rdi+10h], 0
0x18004596a  jz      short loc_180045976
0x18004596c  cmp     [rdi+18h], r15d
0x180045970  jnz     loc_180045A3D
0x180045976  mov     rdx, rsi; struct _tag_FW_RULE *
0x180045979  call    ?IsRestrictedServiceRule@FwServiceRestriction@@AEAAHPEAU_tag_FW_RULE@@@Z; FwServiceRestriction::IsRestrictedServiceRule(_tag_FW_RULE *)
0x18004597e  test    eax, eax
0x180045980  jz      loc_180045A31
0x180045986  mov     r8, [rsi+110h]; lpString1
0x18004598d  or      eax, 0FFFFFFFFh
0x180045990  mov     [rsp+50h+cchCount2], eax; cchCount2
0x180045994  mov     r9d, eax; cchCount1
0x180045997  mov     [rsp+50h+lpString2], r14; lpString2
0x18004599c  lea     edx, [rax+2]; dwCmpFlags
0x18004599f  lea     ecx, [rdx+7Eh]; Locale
0x1800459a2  call    cs:__imp_CompareStringW
0x1800459a9  nop     dword ptr [rax+rax+00h]
0x1800459ae  cmp     eax, 2
0x1800459b1  jnz     short loc_180045A31
0x1800459b3  mov     r8, [rsi+118h]; lpString1
0x1800459ba  or      eax, 0FFFFFFFFh
0x1800459bd  mov     [rsp+50h+cchCount2], eax; cchCount2
0x1800459c1  mov     r9d, eax; cchCount1
0x1800459c4  mov     [rsp+50h+lpString2], r13; lpString2
0x1800459c9  lea     edx, [rax+2]; dwCmpFlags
0x1800459cc  lea     ecx, [rdx+7Eh]; Locale
0x1800459cf  call    cs:__imp_CompareStringW
0x1800459d6  nop     dword ptr [rax+rax+00h]
0x1800459db  cmp     eax, 2
0x1800459de  jnz     short loc_180045A31
0x1800459e0  test    r15d, r15d
0x1800459e3  jz      short loc_180045A02
0x1800459e5  mov     rdx, [rsi+10h]
0x1800459e9  mov     rcx, r12
0x1800459ec  call    FWDeleteFirewallRule
0x1800459f1  test    eax, eax
0x1800459f3  jz      short loc_180045A31
0x1800459f5  jle     short loc_180045A1D
0x1800459f7  movzx   ebx, ax
0x1800459fa  or      ebx, 80070000h
0x180045a00  jmp     short loc_180045A31
0x180045a02  cmp     dword ptr [rsi+2Ch], 1
0x180045a06  mov     r9, rdi
0x180045a09  mov     rdx, rsi
0x180045a0c  jnz     short loc_180045A21
0x180045a0e  mov     r8d, 1
0x180045a14  call    ?StoreSvcRestrictionRule@FwServiceRestriction@@AEAAJPEAU_tag_FW_RULE@@W4_tag_FW_DIRECTION@@PEAU_tag_FW_SVC_RESTRICTION@@@Z; FwServiceRestriction::StoreSvcRestrictionRule(_tag_FW_RULE *,_tag_FW_DIRECTION,_tag_FW_SVC_RESTRICTION *)
0x180045a19  test    eax, eax
0x180045a1b  jns     short loc_180045A31
0x180045a1d  mov     ebx, eax
0x180045a1f  jmp     short loc_180045A31
0x180045a21  mov     r8d, 2
0x180045a27  call    ?StoreSvcRestrictionRule@FwServiceRestriction@@AEAAJPEAU_tag_FW_RULE@@W4_tag_FW_DIRECTION@@PEAU_tag_FW_SVC_RESTRICTION@@@Z; FwServiceRestriction::StoreSvcRestrictionRule(_tag_FW_RULE *,_tag_FW_DIRECTION,_tag_FW_SVC_RESTRICTION *)
0x180045a2c  test    eax, eax
0x180045a2e  cmovs   ebx, eax
0x180045a31  mov     rsi, [rsi]
0x180045a34  test    rsi, rsi
0x180045a37  jnz     loc_180045954
0x180045a3d  test    ebx, ebx
0x180045a3f  jns     short loc_180045A72
0x180045a41  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a48  lea     rax, WPP_GLOBAL_Control
0x180045a4f  cmp     rcx, rax
0x180045a52  jz      short loc_180045A72
0x180045a54  test    byte ptr [rcx+1Ch], 1
0x180045a58  jz      short loc_180045A72
0x180045a5a  mov     edx, 39h ; '9'
0x180045a5f  mov     rcx, [rcx+10h]
0x180045a63  lea     r8, WPP_e61a6c09d8063f8aab058e2fdf152486_Traceguids
0x180045a6a  mov     r9d, ebx
0x180045a6d  call    WPP_SF_d
0x180045a72  mov     rcx, [rbp+var_20]
0x180045a76  call    cs:__imp_FwBaseFree
0x180045a7d  nop     dword ptr [rax+rax+00h]
0x180045a82  test    ebx, ebx
0x180045a84  jns     short loc_180045AB9
0x180045a86  mov     rcx, [rdi]
0x180045a89  test    rcx, rcx
0x180045a8c  jz      short loc_180045A9A
0x180045a8e  call    cs:__imp_FwFreeWFRule
0x180045a95  nop     dword ptr [rax+rax+00h]
0x180045a9a  mov     rcx, [rdi+10h]
0x180045a9e  test    rcx, rcx
0x180045aa1  jz      short loc_180045AAF
0x180045aa3  call    cs:__imp_FwFreeWFRule
0x180045aaa  nop     dword ptr [rax+rax+00h]
0x180045aaf  xorps   xmm0, xmm0
0x180045ab2  movups  xmmword ptr [rdi], xmm0
0x180045ab5  movups  xmmword ptr [rdi+10h], xmm0
0x180045ab9  mov     rcx, [rbp+var_18]
0x180045abd  test    rcx, rcx
0x180045ac0  jz      short loc_180045AC7
0x180045ac2  call    FWFreeFirewallRules
0x180045ac7  mov     eax, ebx
0x180045ac9  mov     rcx, [rbp+var_8]
0x180045acd  xor     rcx, rsp; StackCookie
0x180045ad0  call    __security_check_cookie
0x180045ad5  mov     rbx, [rsp+50h+arg_0]
0x180045add  add     rsp, 50h
0x180045ae1  pop     r15
0x180045ae3  pop     r14
0x180045ae5  pop     r13
0x180045ae7  pop     r12
0x180045ae9  pop     rdi
0x180045aea  pop     rsi
0x180045aeb  pop     rbp
0x180045aec  retn
```
