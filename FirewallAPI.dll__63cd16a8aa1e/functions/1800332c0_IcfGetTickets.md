# IcfGetTickets

- ea: `0x1800332c0`
- end: `0x180033595`
- name: `IcfGetTickets`
- size: `725`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180009080`
- `0x18000b8c0`
- `0x18000c130`
- `0x18000c560`
- `0x1800197a4`
- `0x1800277b0`
- `0x18003104c`
- `0x180031160`
- `0x1800324d8`
- `0x180032990`
- `0x1800332c0`

## import_xrefs

- `fwbase!FwBaseAlloc` at `0x1800333b6`
- `fwbase!FwBaseAlloc` at `0x180033443`
- `fwbase!FwBaseAlloc` at `0x1800333b6`
- `fwbase!FwBaseAlloc` at `0x180033443`
- `fwbase!FwSizeTMultiply` at `0x18003342e`
- `fwbase!FwSizeTMultiply` at `0x18003342e`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x1800333f3`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180033487`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x1800333f3`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180033487`
- `fwbase!FwHResultToWindowsError` at `0x180033576`
- `fwbase!FwHResultToWindowsError` at `0x180033576`
- `fwbase!FwReportErrorAsWinError` at `0x18003336b`
- `fwbase!FwReportErrorAsWinError` at `0x18003336b`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x1800333dd`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180033469`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x1800333dd`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180033469`

## string_xrefs

- `0x18003335a`: `FWOpenPolicyStore`
- `0x180033529`: `CopySubnetRestrictions`
- `0x18003351d`: `CopyAddrRanges`

## pseudocode

```c
__int64 __fastcall IcfGetTickets(__int64 a1, _QWORD *a2)
{
  unsigned int v3; // eax
  const char *v4; // rdx
  __int64 v5; // r8
  int v6; // ebx
  unsigned int *v7; // rdi
  struct _tag_FW_RULE *i; // rbx
  __int64 v9; // rdx
  __int64 v11; // rax
  struct _tag_FW_RULE *v12; // rbx
  __int64 v13; // r14
  __int64 v14; // rsi
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  struct _tag_FW_RULE *v16; // [rsp+38h] [rbp-30h] BYREF
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF
  __int64 v18; // [rsp+48h] [rbp-20h] BYREF
  int v19; // [rsp+50h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  v17 = 0;
  v16 = 0;
  v19 = 0;
  v15 = 0;
  v3 = FWOpenPolicyStore(0x221u, 0, 5u, 1u, 0, &v17);
  if ( !v3 )
  {
    v3 = FWEnumFirewallRules(v17, 0x10000, 0x80000000, 9, (__int64)&v19, (__int64)&v16);
    if ( v3 )
    {
      v4 = "FWEnumFirewallRules";
      goto LABEL_6;
    }
    v15 = FwBaseAlloc(16);
    v7 = (unsigned int *)v15;
    if ( !v15 )
    {
LABEL_11:
      v5 = 8;
      v4 = "FwAlloc";
      goto LABEL_7;
    }
    for ( i = v16; i; i = *(struct _tag_FW_RULE **)i )
    {
      if ( (unsigned int)IsRuleOpenPortOrAuthApp(i)
        && (*((_BYTE *)i + 292) & 1) != 0
        && (unsigned int)IsRuleOldGlobalOpenPort(i)
        && *((_DWORD *)i + 85) != 3
        && *((_DWORD *)i + 72) == 3 )
      {
        ++*v7;
      }
    }
    if ( *v7 )
    {
      v9 = *v7;
      v18 = 0;
      if ( (int)FwSizeTMultiply(96, v9, &v18) < 0 )
        return 8;
      v11 = FwBaseAlloc(v18);
      *((_QWORD *)v7 + 1) = v11;
      if ( !v11 )
        goto LABEL_11;
      v12 = v16;
      v13 = 0;
      while ( v12 )
      {
        if ( (unsigned int)IsRuleOpenPortOrAuthApp(v12)
          && (*((_BYTE *)v12 + 292) & 1) != 0
          && (unsigned int)IsRuleOldGlobalOpenPort(v12)
          && *((_DWORD *)v12 + 85) != 3
          && *((_DWORD *)v12 + 72) == 3 )
        {
          v14 = 96 * v13;
          *(_DWORD *)(v14 + *((_QWORD *)v7 + 1)) = 2;
          *(_WORD *)(v14 + *((_QWORD *)v7 + 1) + 8) = **((_WORD **)v12 + 9);
          *(_DWORD *)(v14 + *((_QWORD *)v7 + 1) + 4) = *((unsigned __int16 *)v12 + 24);
          v3 = CopySubnetRestrictions(
                 v12,
                 (struct ICF_SUBNETS_ *)(96 * v13 + *((_QWORD *)v7 + 1) + 16LL),
                 (struct ICF_SUBNETS6_ *)(96 * v13 + *((_QWORD *)v7 + 1) + 40LL));
          if ( v3 )
          {
            v4 = "CopySubnetRestrictions";
            goto LABEL_6;
          }
          v3 = CopyAddrRanges(
                 v12,
                 (struct ICF_RANGES_ *)(v14 + *((_QWORD *)v7 + 1) + 64LL),
                 (struct ICF_RANGES6_ *)(v14 + *((_QWORD *)v7 + 1) + 80LL));
          if ( v3 )
          {
            v4 = "CopyAddrRanges";
            goto LABEL_6;
          }
          v13 = (unsigned int)(v13 + 1);
        }
        v12 = *(struct _tag_FW_RULE **)v12;
      }
    }
    v6 = 0;
    *a2 = v7;
    goto LABEL_39;
  }
  v4 = "FWOpenPolicyStore";
LABEL_6:
  v5 = v3;
LABEL_7:
  v6 = FwReportErrorAsWinError("IcfGetTickets", v4, v5);
LABEL_39:
  if ( v17 )
    FWClosePolicyStore();
  if ( v16 )
    FWFreeFirewallRules(v16);
  if ( v6 < 0 )
    IcfFreeTickets(&v15);
  if ( (unsigned int)IsRpcError(v6) )
    v6 = -2147023174;
  return FwHResultToWindowsError((unsigned int)v6);
}

```

## disassembly

```asm
0x1800332c0  push    rbp
0x1800332c2  push    rbx
0x1800332c3  push    rsi
0x1800332c4  push    rdi
0x1800332c5  push    r14
0x1800332c7  push    r15
0x1800332c9  mov     rbp, rsp
0x1800332cc  sub     rsp, 68h
0x1800332d0  mov     rax, cs:__security_cookie
0x1800332d7  xor     rax, rsp
0x1800332da  mov     [rbp+var_10], rax
0x1800332de  mov     r15, rdx
0x1800332e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800332e8  lea     rax, WPP_GLOBAL_Control
0x1800332ef  mov     esi, 8
0x1800332f4  cmp     rcx, rax
0x1800332f7  jz      short loc_180033312
0x1800332f9  test    [rcx+1Ch], sil
0x1800332fd  jz      short loc_180033312
0x1800332ff  mov     rcx, [rcx+10h]
0x180033303  lea     edx, [rsi+20h]
0x180033306  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18003330d  call    WPP_SF_
0x180033312  xor     edx, edx
0x180033314  mov     [rbp+var_28], 0
0x18003331c  lea     rax, [rbp+var_28]
0x180033320  mov     [rbp+var_30], 0
0x180033328  mov     [rsp+68h+var_40], rax
0x18003332d  mov     ecx, 221h
0x180033332  mov     [rbp+var_18], 0
0x180033339  lea     r9d, [rdx+1]
0x18003333d  mov     [rbp+var_38], 0
0x180033345  lea     r8d, [rdx+5]
0x180033349  mov     dword ptr [rsp+68h+var_48], 0
0x180033351  call    FWOpenPolicyStore
0x180033356  test    eax, eax
0x180033358  jz      short loc_180033378
0x18003335a  lea     rdx, aFwopenpolicyst_1; "FWOpenPolicyStore"
0x180033361  mov     r8d, eax
0x180033364  lea     rcx, aIcfgettickets_0; "IcfGetTickets"
0x18003336b  call    cs:__imp_FwReportErrorAsWinError
0x180033371  mov     ebx, eax
0x180033373  jmp     loc_18003353A
0x180033378  mov     rcx, [rbp+var_28]
0x18003337c  lea     rax, [rbp+var_30]
0x180033380  mov     [rsp+68h+var_40], rax
0x180033385  mov     r9d, 9
0x18003338b  lea     rax, [rbp+var_18]
0x18003338f  mov     edx, 10000h
0x180033394  mov     r8d, 80000000h
0x18003339a  mov     [rsp+68h+var_48], rax
0x18003339f  call    FWEnumFirewallRules
0x1800333a4  test    eax, eax
0x1800333a6  jz      short loc_1800333B1
0x1800333a8  lea     rdx, aFwenumfirewall_0; "FWEnumFirewallRules"
0x1800333af  jmp     short loc_180033361
0x1800333b1  mov     ecx, 10h
0x1800333b6  call    cs:__imp_FwBaseAlloc
0x1800333bc  mov     [rbp+var_38], rax
0x1800333c0  mov     rdi, rax
0x1800333c3  test    rax, rax
0x1800333c6  jnz     short loc_1800333D4
0x1800333c8  mov     r8d, esi
0x1800333cb  lea     rdx, aFwalloc_0; "FwAlloc"
0x1800333d2  jmp     short loc_180033364
0x1800333d4  mov     rbx, [rbp+var_30]
0x1800333d8  jmp     short loc_180033414
0x1800333da  mov     rcx, rbx
0x1800333dd  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x1800333e3  test    eax, eax
0x1800333e5  jz      short loc_180033411
0x1800333e7  test    byte ptr [rbx+124h], 1
0x1800333ee  jz      short loc_180033411
0x1800333f0  mov     rcx, rbx
0x1800333f3  call    cs:__imp_IsRuleOldGlobalOpenPort
0x1800333f9  test    eax, eax
0x1800333fb  jz      short loc_180033411
0x1800333fd  cmp     dword ptr [rbx+154h], 3
0x180033404  jz      short loc_180033411
0x180033406  cmp     dword ptr [rbx+120h], 3
0x18003340d  jnz     short loc_180033411
0x18003340f  inc     dword ptr [rdi]
0x180033411  mov     rbx, [rbx]
0x180033414  test    rbx, rbx
0x180033417  jnz     short loc_1800333DA
0x180033419  cmp     [rdi], ebx
0x18003341b  jz      loc_180033535
0x180033421  mov     edx, [rdi]
0x180033423  lea     r8, [rbp+var_20]
0x180033427  lea     ecx, [rbx+60h]
0x18003342a  mov     [rbp+var_20], rbx
0x18003342e  call    cs:__imp_FwSizeTMultiply
0x180033434  test    eax, eax
0x180033436  jns     short loc_18003343F
0x180033438  mov     eax, esi
0x18003343a  jmp     loc_18003357C
0x18003343f  mov     rcx, [rbp+var_20]
0x180033443  call    cs:__imp_FwBaseAlloc
0x180033449  mov     [rdi+8], rax
0x18003344d  test    rax, rax
0x180033450  jz      loc_1800333C8
0x180033456  mov     rbx, [rbp+var_30]
0x18003345a  xor     r14d, r14d
0x18003345d  test    rbx, rbx
0x180033460  jz      loc_180033535
0x180033466  mov     rcx, rbx
0x180033469  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x18003346f  test    eax, eax
0x180033471  jz      loc_180033515
0x180033477  test    byte ptr [rbx+124h], 1
0x18003347e  jz      loc_180033515
0x180033484  mov     rcx, rbx
0x180033487  call    cs:__imp_IsRuleOldGlobalOpenPort
0x18003348d  test    eax, eax
0x18003348f  jz      loc_180033515
0x180033495  cmp     dword ptr [rbx+154h], 3
0x18003349c  jz      short loc_180033515
0x18003349e  cmp     dword ptr [rbx+120h], 3
0x1800334a5  jnz     short loc_180033515
0x1800334a7  mov     rax, [rdi+8]
0x1800334ab  lea     rsi, [r14+r14*2]
0x1800334af  shl     rsi, 5
0x1800334b3  mov     dword ptr [rsi+rax], 2
0x1800334ba  mov     rax, [rbx+48h]
0x1800334be  mov     rcx, [rdi+8]
0x1800334c2  movzx   eax, word ptr [rax]
0x1800334c5  mov     [rsi+rcx+8], ax
0x1800334ca  mov     rax, [rdi+8]
0x1800334ce  movzx   ecx, word ptr [rbx+30h]
0x1800334d2  mov     [rsi+rax+4], ecx
0x1800334d6  mov     rcx, rbx; struct _tag_FW_RULE *
0x1800334d9  mov     rax, [rdi+8]
0x1800334dd  lea     r8, [rax+28h]
0x1800334e1  lea     rdx, [rax+10h]
0x1800334e5  add     r8, rsi; struct ICF_SUBNETS6_ *
0x1800334e8  add     rdx, rsi; struct ICF_SUBNETS_ *
0x1800334eb  call    ?CopySubnetRestrictions@@YAKPEBU_tag_FW_RULE@@PEAUICF_SUBNETS_@@PEAUICF_SUBNETS6_@@@Z; CopySubnetRestrictions(_tag_FW_RULE const *,ICF_SUBNETS_ *,ICF_SUBNETS6_ *)
0x1800334f0  test    eax, eax
0x1800334f2  jnz     short loc_180033529
0x1800334f4  mov     rax, [rdi+8]
0x1800334f8  mov     rcx, rbx; struct _tag_FW_RULE *
0x1800334fb  lea     r8, [rax+50h]
0x1800334ff  lea     rdx, [rax+40h]
0x180033503  add     r8, rsi; struct ICF_RANGES6_ *
0x180033506  add     rdx, rsi; struct ICF_RANGES_ *
0x180033509  call    ?CopyAddrRanges@@YAKPEBU_tag_FW_RULE@@PEAUICF_RANGES_@@PEAUICF_RANGES6_@@@Z; CopyAddrRanges(_tag_FW_RULE const *,ICF_RANGES_ *,ICF_RANGES6_ *)
0x18003350e  test    eax, eax
0x180033510  jnz     short loc_18003351D
0x180033512  inc     r14d
0x180033515  mov     rbx, [rbx]
0x180033518  jmp     loc_18003345D
0x18003351d  lea     rdx, aCopyaddrranges; "CopyAddrRanges"
0x180033524  jmp     loc_180033361
0x180033529  lea     rdx, aCopysubnetrest; "CopySubnetRestrictions"
0x180033530  jmp     loc_180033361
0x180033535  xor     ebx, ebx
0x180033537  mov     [r15], rdi
0x18003353a  mov     rcx, [rbp+var_28]
0x18003353e  test    rcx, rcx
0x180033541  jz      short loc_180033548
0x180033543  call    FWClosePolicyStore
0x180033548  mov     rcx, [rbp+var_30]
0x18003354c  test    rcx, rcx
0x18003354f  jz      short loc_180033556
0x180033551  call    FWFreeFirewallRules
0x180033556  test    ebx, ebx
0x180033558  jns     short loc_180033563
0x18003355a  lea     rcx, [rbp+var_38]
0x18003355e  call    IcfFreeTickets
0x180033563  mov     ecx, ebx; int
0x180033565  call    ?IsRpcError@@YAHJ@Z; IsRpcError(long)
0x18003356a  mov     ecx, 800706BAh
0x18003356f  test    eax, eax
0x180033571  cmovnz  ebx, ecx
0x180033574  mov     ecx, ebx
0x180033576  call    cs:__imp_FwHResultToWindowsError
0x18003357c  mov     rcx, [rbp+var_10]
0x180033580  xor     rcx, rsp; StackCookie
0x180033583  call    __security_check_cookie
0x180033588  add     rsp, 68h
0x18003358c  pop     r15
0x18003358e  pop     r14
0x180033590  pop     rdi
0x180033591  pop     rsi
0x180033592  pop     rbx
0x180033593  pop     rbp
0x180033594  retn
```
