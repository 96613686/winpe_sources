# FwOpenPorts::Remove(long,NET_FW_IP_PROTOCOL_)

- ea: `0x1800022c0`
- end: `0x18000246d`
- name: `?Remove@FwOpenPorts@@UEAAJJW4NET_FW_IP_PROTOCOL_@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(FwOpenPorts *__hidden this, int, enum NET_FW_IP_PROTOCOL_)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800022c0`
- `0x1800037dc`
- `0x180005630`
- `0x180009780`
- `0x18000c3f0`
- `0x18000d0f0`
- `0x1800294b0`
- `0x180032840`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180002415`
- `fwbase!FwReportReturnError` at `0x18000243c`
- `fwbase!FwReportReturnError` at `0x180002415`
- `fwbase!FwReportReturnError` at `0x18000243c`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x1800023ae`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x1800023ae`

## string_xrefs

- `0x180002301`: `FwOpenPorts::Remove`

## pseudocode

```c
__int64 __fastcall FwOpenPorts::Remove(FwOpenPorts *this, unsigned int a2, unsigned int a3)
{
  int v6; // eax
  signed int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  __int64 MatchingOpenPortRule; // rdi
  int v11; // eax
  int v12; // eax
  unsigned int v14; // [rsp+30h] [rbp-20h] BYREF
  void *v15; // [rsp+38h] [rbp-18h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h] BYREF

  v16 = 0;
  v14 = 0;
  v15 = 0;
  if ( a2 > 0xFFFF || a3 != 6 && a3 != 17 )
  {
    v8 = 2147942487LL;
    v7 = -2147024809;
    goto LABEL_20;
  }
  v6 = FWOpenPolicyStore(0x221u, 0, 2u, 2u, 0, &v15);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_7;
  v9 = FWEnumFirewallRules((__int64)v15, 196608, *((_DWORD *)this + 6), 7, (__int64)&v14, (__int64)&v16);
  v7 = v9;
  if ( v9 > 0 )
    v7 = (unsigned __int16)v9 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_7;
  MatchingOpenPortRule = FwFindMatchingOpenPortRule(v16, v14, a2, a3);
  if ( !MatchingOpenPortRule )
    goto LABEL_21;
  if ( (~*((_DWORD *)this + 6) & *(_DWORD *)(MatchingOpenPortRule + 40)) != 0 )
  {
    v11 = FwSplitRule((__int64)v15, (struct _tag_FW_RULE *)MatchingOpenPortRule, *((_DWORD *)this + 6));
    v7 = v11;
    if ( v11 < 0 )
    {
      v8 = (unsigned int)v11;
      goto LABEL_20;
    }
  }
  v12 = FWDeleteFirewallRule((__int64)v15, *(_QWORD *)(MatchingOpenPortRule + 16));
  v7 = v12;
  if ( v12 > 0 )
    v7 = (unsigned __int16)v12 | 0x80070000;
  if ( v7 < 0 )
  {
LABEL_7:
    v8 = (unsigned int)v7;
LABEL_20:
    FwReportReturnError("FwOpenPorts::Remove", v8);
  }
LABEL_21:
  FWFreeFirewallRules(v16);
  CloseLocalPolicyStore(v15);
  if ( v7 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPorts::Remove", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800022c0  mov     [rsp-28h+arg_18], rbx
0x1800022c5  push    rbp
0x1800022c6  push    rsi
0x1800022c7  push    rdi
0x1800022c8  push    r12
0x1800022ca  push    r14
0x1800022cc  mov     rbp, rsp
0x1800022cf  sub     rsp, 50h
0x1800022d3  mov     rax, cs:__security_cookie
0x1800022da  xor     rax, rsp
0x1800022dd  mov     [rbp+var_8], rax
0x1800022e1  mov     [rbp+var_10], 0
0x1800022e9  mov     edi, r8d
0x1800022ec  mov     [rbp+var_20], 0
0x1800022f3  mov     r14d, edx
0x1800022f6  mov     [rbp+var_18], 0
0x1800022fe  mov     rsi, rcx
0x180002301  lea     r12, aFwopenportsRem; "FwOpenPorts::Remove"
0x180002308  cmp     edx, 0FFFFh
0x18000230e  ja      loc_18000240B
0x180002314  cmp     r8d, 6
0x180002318  jz      short loc_180002324
0x18000231a  cmp     r8d, 11h
0x18000231e  jnz     loc_18000240B
0x180002324  lea     rax, [rbp+var_18]
0x180002328  mov     r8d, 2
0x18000232e  mov     [rsp+50h+var_28], rax
0x180002333  mov     r9d, r8d
0x180002336  mov     ecx, 221h
0x18000233b  mov     dword ptr [rsp+50h+var_30], 0
0x180002343  xor     edx, edx
0x180002345  call    FWOpenPolicyStore
0x18000234a  mov     ebx, eax
0x18000234c  test    eax, eax
0x18000234e  jle     short loc_180002359
0x180002350  movzx   ebx, ax
0x180002353  or      ebx, 80070000h
0x180002359  test    ebx, ebx
0x18000235b  jns     short loc_180002364
0x18000235d  mov     edx, ebx
0x18000235f  jmp     loc_180002412
0x180002364  mov     r8d, [rsi+18h]
0x180002368  lea     rax, [rbp+var_10]
0x18000236c  mov     rcx, [rbp+var_18]
0x180002370  mov     r9d, 7
0x180002376  mov     [rsp+50h+var_28], rax
0x18000237b  mov     edx, 30000h
0x180002380  lea     rax, [rbp+var_20]
0x180002384  mov     [rsp+50h+var_30], rax
0x180002389  call    FWEnumFirewallRules
0x18000238e  mov     ebx, eax
0x180002390  test    eax, eax
0x180002392  jle     short loc_18000239D
0x180002394  movzx   ebx, ax
0x180002397  or      ebx, 80070000h
0x18000239d  test    ebx, ebx
0x18000239f  js      short loc_18000235D
0x1800023a1  mov     edx, [rbp+var_20]
0x1800023a4  mov     r9d, edi
0x1800023a7  mov     rcx, [rbp+var_10]
0x1800023ab  mov     r8d, r14d
0x1800023ae  call    cs:__imp_FwFindMatchingOpenPortRule
0x1800023b5  nop     dword ptr [rax+rax+00h]
0x1800023ba  mov     rdi, rax
0x1800023bd  test    rax, rax
0x1800023c0  jz      short loc_180002421
0x1800023c2  mov     r8d, [rsi+18h]; unsigned int
0x1800023c6  mov     eax, r8d
0x1800023c9  not     eax
0x1800023cb  test    [rdi+28h], eax
0x1800023ce  jz      short loc_1800023E6
0x1800023d0  mov     rcx, [rbp+var_18]; void *
0x1800023d4  mov     rdx, rdi; struct _tag_FW_RULE *
0x1800023d7  call    ?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; FwSplitRule(void *,_tag_FW_RULE *,ulong)
0x1800023dc  mov     ebx, eax
0x1800023de  test    eax, eax
0x1800023e0  jns     short loc_1800023E6
0x1800023e2  mov     edx, eax
0x1800023e4  jmp     short loc_180002412
0x1800023e6  mov     rdx, [rdi+10h]
0x1800023ea  mov     rcx, [rbp+var_18]
0x1800023ee  call    FWDeleteFirewallRule
0x1800023f3  mov     ebx, eax
0x1800023f5  test    eax, eax
0x1800023f7  jle     short loc_180002402
0x1800023f9  movzx   ebx, ax
0x1800023fc  or      ebx, 80070000h
0x180002402  test    ebx, ebx
0x180002404  jns     short loc_180002421
0x180002406  jmp     loc_18000235D
0x18000240b  mov     edx, 80070057h
0x180002410  mov     ebx, edx
0x180002412  mov     rcx, r12
0x180002415  call    cs:__imp_FwReportReturnError
0x18000241c  nop     dword ptr [rax+rax+00h]
0x180002421  mov     rcx, [rbp+var_10]
0x180002425  call    FWFreeFirewallRules
0x18000242a  mov     rcx, [rbp+var_18]; void *
0x18000242e  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180002433  test    ebx, ebx
0x180002435  jns     short loc_18000244A
0x180002437  mov     edx, ebx
0x180002439  mov     rcx, r12
0x18000243c  call    cs:__imp_FwReportReturnError
0x180002443  nop     dword ptr [rax+rax+00h]
0x180002448  mov     ebx, eax
0x18000244a  mov     eax, ebx
0x18000244c  mov     rcx, [rbp+var_8]
0x180002450  xor     rcx, rsp; StackCookie
0x180002453  call    __security_check_cookie
0x180002458  mov     rbx, [rsp+50h+arg_18]
0x180002460  add     rsp, 50h
0x180002464  pop     r14
0x180002466  pop     r12
0x180002468  pop     rdi
0x180002469  pop     rsi
0x18000246a  pop     rbp
0x18000246b  retn
```
