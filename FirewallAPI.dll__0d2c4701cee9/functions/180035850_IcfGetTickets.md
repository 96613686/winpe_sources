# IcfGetTickets

- ea: `0x180035850`
- end: `0x180035b5c`
- name: `IcfGetTickets`
- size: `780`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180009780`
- `0x18000c3f0`
- `0x18000cc80`
- `0x18000d0f0`
- `0x180019b34`
- `0x1800294b0`
- `0x18003336c`
- `0x180033488`
- `0x1800348ec`
- `0x180034e90`
- `0x180035850`

## import_xrefs

- `fwbase!FwBaseAlloc` at `0x18003594c`
- `fwbase!FwBaseAlloc` at `0x1800359f1`
- `fwbase!FwBaseAlloc` at `0x18003594c`
- `fwbase!FwBaseAlloc` at `0x1800359f1`
- `fwbase!FwSizeTMultiply` at `0x1800359d6`
- `fwbase!FwSizeTMultiply` at `0x1800359d6`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180035995`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180035a41`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180035995`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180035a41`
- `fwbase!FwHResultToWindowsError` at `0x180035b36`
- `fwbase!FwHResultToWindowsError` at `0x180035b36`
- `fwbase!FwReportErrorAsWinError` at `0x1800358fb`
- `fwbase!FwReportErrorAsWinError` at `0x1800358fb`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180035979`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180035a1d`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180035979`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180035a1d`

## string_xrefs

- `0x1800358ea`: `FWOpenPolicyStore`
- `0x180035ae9`: `CopySubnetRestrictions`
- `0x180035add`: `CopyAddrRanges`

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
  v3 = FWOpenPolicyStore(545, 0, 5, 1, 0, (__int64)&v17);
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
0x180035850  push    rbp
0x180035852  push    rbx
0x180035853  push    rsi
0x180035854  push    rdi
0x180035855  push    r14
0x180035857  push    r15
0x180035859  mov     rbp, rsp
0x18003585c  sub     rsp, 68h
0x180035860  mov     rax, cs:__security_cookie
0x180035867  xor     rax, rsp
0x18003586a  mov     [rbp+var_10], rax
0x18003586e  mov     r15, rdx
0x180035871  mov     rcx, cs:WPP_GLOBAL_Control
0x180035878  lea     rax, WPP_GLOBAL_Control
0x18003587f  mov     esi, 8
0x180035884  cmp     rcx, rax
0x180035887  jz      short loc_1800358A2
0x180035889  test    [rcx+1Ch], sil
0x18003588d  jz      short loc_1800358A2
0x18003588f  mov     rcx, [rcx+10h]
0x180035893  lea     edx, [rsi+20h]
0x180035896  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18003589d  call    WPP_SF_
0x1800358a2  xor     edx, edx
0x1800358a4  mov     [rbp+var_28], 0
0x1800358ac  lea     rax, [rbp+var_28]
0x1800358b0  mov     [rbp+var_30], 0
0x1800358b8  mov     [rsp+68h+var_40], rax
0x1800358bd  mov     ecx, 221h
0x1800358c2  mov     [rbp+var_18], 0
0x1800358c9  lea     r9d, [rdx+1]
0x1800358cd  mov     [rbp+var_38], 0
0x1800358d5  lea     r8d, [rdx+5]
0x1800358d9  mov     dword ptr [rsp+68h+var_48], 0
0x1800358e1  call    FWOpenPolicyStore
0x1800358e6  test    eax, eax
0x1800358e8  jz      short loc_18003590E
0x1800358ea  lea     rdx, aFwopenpolicyst_1; "FWOpenPolicyStore"
0x1800358f1  mov     r8d, eax
0x1800358f4  lea     rcx, aIcfgettickets_0; "IcfGetTickets"
0x1800358fb  call    cs:__imp_FwReportErrorAsWinError
0x180035902  nop     dword ptr [rax+rax+00h]
0x180035907  mov     ebx, eax
0x180035909  jmp     loc_180035AFA
0x18003590e  mov     rcx, [rbp+var_28]
0x180035912  lea     rax, [rbp+var_30]
0x180035916  mov     [rsp+68h+var_40], rax
0x18003591b  mov     r9d, 9
0x180035921  lea     rax, [rbp+var_18]
0x180035925  mov     edx, 10000h
0x18003592a  mov     r8d, 80000000h
0x180035930  mov     [rsp+68h+var_48], rax
0x180035935  call    FWEnumFirewallRules
0x18003593a  test    eax, eax
0x18003593c  jz      short loc_180035947
0x18003593e  lea     rdx, aFwenumfirewall_0; "FWEnumFirewallRules"
0x180035945  jmp     short loc_1800358F1
0x180035947  mov     ecx, 10h
0x18003594c  call    cs:__imp_FwBaseAlloc
0x180035953  nop     dword ptr [rax+rax+00h]
0x180035958  mov     [rbp+var_38], rax
0x18003595c  mov     rdi, rax
0x18003595f  test    rax, rax
0x180035962  jnz     short loc_180035970
0x180035964  mov     r8d, esi
0x180035967  lea     rdx, aFwalloc_0; "FwAlloc"
0x18003596e  jmp     short loc_1800358F4
0x180035970  mov     rbx, [rbp+var_30]
0x180035974  jmp     short loc_1800359BC
0x180035976  mov     rcx, rbx
0x180035979  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180035980  nop     dword ptr [rax+rax+00h]
0x180035985  test    eax, eax
0x180035987  jz      short loc_1800359B9
0x180035989  test    byte ptr [rbx+124h], 1
0x180035990  jz      short loc_1800359B9
0x180035992  mov     rcx, rbx
0x180035995  call    cs:__imp_IsRuleOldGlobalOpenPort
0x18003599c  nop     dword ptr [rax+rax+00h]
0x1800359a1  test    eax, eax
0x1800359a3  jz      short loc_1800359B9
0x1800359a5  cmp     dword ptr [rbx+154h], 3
0x1800359ac  jz      short loc_1800359B9
0x1800359ae  cmp     dword ptr [rbx+120h], 3
0x1800359b5  jnz     short loc_1800359B9
0x1800359b7  inc     dword ptr [rdi]
0x1800359b9  mov     rbx, [rbx]
0x1800359bc  test    rbx, rbx
0x1800359bf  jnz     short loc_180035976
0x1800359c1  cmp     [rdi], ebx
0x1800359c3  jz      loc_180035AF5
0x1800359c9  mov     edx, [rdi]
0x1800359cb  lea     r8, [rbp+var_20]
0x1800359cf  lea     ecx, [rbx+60h]
0x1800359d2  mov     [rbp+var_20], rbx
0x1800359d6  call    cs:__imp_FwSizeTMultiply
0x1800359dd  nop     dword ptr [rax+rax+00h]
0x1800359e2  test    eax, eax
0x1800359e4  jns     short loc_1800359ED
0x1800359e6  mov     eax, esi
0x1800359e8  jmp     loc_180035B42
0x1800359ed  mov     rcx, [rbp+var_20]
0x1800359f1  call    cs:__imp_FwBaseAlloc
0x1800359f8  nop     dword ptr [rax+rax+00h]
0x1800359fd  mov     [rdi+8], rax
0x180035a01  test    rax, rax
0x180035a04  jz      loc_180035964
0x180035a0a  mov     rbx, [rbp+var_30]
0x180035a0e  xor     r14d, r14d
0x180035a11  test    rbx, rbx
0x180035a14  jz      loc_180035AF5
0x180035a1a  mov     rcx, rbx
0x180035a1d  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180035a24  nop     dword ptr [rax+rax+00h]
0x180035a29  test    eax, eax
0x180035a2b  jz      loc_180035AD5
0x180035a31  test    byte ptr [rbx+124h], 1
0x180035a38  jz      loc_180035AD5
0x180035a3e  mov     rcx, rbx
0x180035a41  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180035a48  nop     dword ptr [rax+rax+00h]
0x180035a4d  test    eax, eax
0x180035a4f  jz      loc_180035AD5
0x180035a55  cmp     dword ptr [rbx+154h], 3
0x180035a5c  jz      short loc_180035AD5
0x180035a5e  cmp     dword ptr [rbx+120h], 3
0x180035a65  jnz     short loc_180035AD5
0x180035a67  mov     rax, [rdi+8]
0x180035a6b  lea     rsi, [r14+r14*2]
0x180035a6f  shl     rsi, 5
0x180035a73  mov     dword ptr [rsi+rax], 2
0x180035a7a  mov     rax, [rbx+48h]
0x180035a7e  mov     rcx, [rdi+8]
0x180035a82  movzx   eax, word ptr [rax]
0x180035a85  mov     [rsi+rcx+8], ax
0x180035a8a  mov     rax, [rdi+8]
0x180035a8e  movzx   ecx, word ptr [rbx+30h]
0x180035a92  mov     [rsi+rax+4], ecx
0x180035a96  mov     rcx, rbx; struct _tag_FW_RULE *
0x180035a99  mov     rax, [rdi+8]
0x180035a9d  lea     r8, [rax+28h]
0x180035aa1  lea     rdx, [rax+10h]
0x180035aa5  add     r8, rsi; struct ICF_SUBNETS6_ *
0x180035aa8  add     rdx, rsi; struct ICF_SUBNETS_ *
0x180035aab  call    ?CopySubnetRestrictions@@YAKPEBU_tag_FW_RULE@@PEAUICF_SUBNETS_@@PEAUICF_SUBNETS6_@@@Z; CopySubnetRestrictions(_tag_FW_RULE const *,ICF_SUBNETS_ *,ICF_SUBNETS6_ *)
0x180035ab0  test    eax, eax
0x180035ab2  jnz     short loc_180035AE9
0x180035ab4  mov     rax, [rdi+8]
0x180035ab8  mov     rcx, rbx; struct _tag_FW_RULE *
0x180035abb  lea     r8, [rax+50h]
0x180035abf  lea     rdx, [rax+40h]
0x180035ac3  add     r8, rsi; struct ICF_RANGES6_ *
0x180035ac6  add     rdx, rsi; struct ICF_RANGES_ *
0x180035ac9  call    ?CopyAddrRanges@@YAKPEBU_tag_FW_RULE@@PEAUICF_RANGES_@@PEAUICF_RANGES6_@@@Z; CopyAddrRanges(_tag_FW_RULE const *,ICF_RANGES_ *,ICF_RANGES6_ *)
0x180035ace  test    eax, eax
0x180035ad0  jnz     short loc_180035ADD
0x180035ad2  inc     r14d
0x180035ad5  mov     rbx, [rbx]
0x180035ad8  jmp     loc_180035A11
0x180035add  lea     rdx, aCopyaddrranges; "CopyAddrRanges"
0x180035ae4  jmp     loc_1800358F1
0x180035ae9  lea     rdx, aCopysubnetrest; "CopySubnetRestrictions"
0x180035af0  jmp     loc_1800358F1
0x180035af5  xor     ebx, ebx
0x180035af7  mov     [r15], rdi
0x180035afa  mov     rcx, [rbp+var_28]
0x180035afe  test    rcx, rcx
0x180035b01  jz      short loc_180035B08
0x180035b03  call    FWClosePolicyStore
0x180035b08  mov     rcx, [rbp+var_30]
0x180035b0c  test    rcx, rcx
0x180035b0f  jz      short loc_180035B16
0x180035b11  call    FWFreeFirewallRules
0x180035b16  test    ebx, ebx
0x180035b18  jns     short loc_180035B23
0x180035b1a  lea     rcx, [rbp+var_38]
0x180035b1e  call    IcfFreeTickets
0x180035b23  mov     ecx, ebx; int
0x180035b25  call    ?IsRpcError@@YAHJ@Z; IsRpcError(long)
0x180035b2a  mov     ecx, 800706BAh
0x180035b2f  test    eax, eax
0x180035b31  cmovnz  ebx, ecx
0x180035b34  mov     ecx, ebx
0x180035b36  call    cs:__imp_FwHResultToWindowsError
0x180035b3d  nop     dword ptr [rax+rax+00h]
0x180035b42  mov     rcx, [rbp+var_10]
0x180035b46  xor     rcx, rsp; StackCookie
0x180035b49  call    __security_check_cookie
0x180035b4e  add     rsp, 68h
0x180035b52  pop     r15
0x180035b54  pop     r14
0x180035b56  pop     rdi
0x180035b57  pop     rsi
0x180035b58  pop     rbx
0x180035b59  pop     rbp
0x180035b5a  retn
```
