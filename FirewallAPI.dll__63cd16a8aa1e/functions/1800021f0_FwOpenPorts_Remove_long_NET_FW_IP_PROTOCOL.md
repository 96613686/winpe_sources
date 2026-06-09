# FwOpenPorts::Remove(long,NET_FW_IP_PROTOCOL_)

- ea: `0x1800021f0`
- end: `0x18000238a`
- name: `?Remove@FwOpenPorts@@UEAAJJW4NET_FW_IP_PROTOCOL_@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(FwOpenPorts *__hidden this, int, enum NET_FW_IP_PROTOCOL_)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800021f0`
- `0x180003520`
- `0x1800051c0`
- `0x180009080`
- `0x18000b8c0`
- `0x18000c560`
- `0x1800277b0`
- `0x18003063c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18000233f`
- `fwbase!FwReportReturnError` at `0x180002360`
- `fwbase!FwReportReturnError` at `0x18000233f`
- `fwbase!FwReportReturnError` at `0x180002360`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x1800022de`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x1800022de`

## string_xrefs

- `0x180002231`: `FwOpenPorts::Remove`

## pseudocode

```c
__int64 __fastcall FwOpenPorts::Remove(FwOpenPorts *this, unsigned int a2, unsigned int a3)
{
  int v6; // eax
  signed int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  __int64 MatchingOpenPortRule; // rdi
  __int64 v12; // r8
  int v13; // eax
  int v14; // eax
  unsigned int v16; // [rsp+30h] [rbp-20h] BYREF
  void *v17; // [rsp+38h] [rbp-18h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h] BYREF

  v18 = 0;
  v16 = 0;
  v17 = 0;
  if ( a2 > 0xFFFF || a3 != 6 && a3 != 17 )
  {
    v8 = 2147942487LL;
    v7 = -2147024809;
    goto LABEL_20;
  }
  v6 = FWOpenPolicyStore(0x221u, 0, 2u, 2u, 0, &v17);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_7;
  v9 = FWEnumFirewallRules((__int64)v17, 196608, *((_DWORD *)this + 6), 7, (__int64)&v16, (__int64)&v18);
  v7 = v9;
  if ( v9 > 0 )
    v7 = (unsigned __int16)v9 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_7;
  MatchingOpenPortRule = FwFindMatchingOpenPortRule(v18, v16, a2, a3);
  if ( !MatchingOpenPortRule )
    goto LABEL_21;
  if ( (~*((_DWORD *)this + 6) & *(_DWORD *)(MatchingOpenPortRule + 40)) != 0 )
  {
    v13 = FwSplitRule((unsigned __int16 *)v17, (struct _tag_FW_RULE *)MatchingOpenPortRule, *((_DWORD *)this + 6));
    v7 = v13;
    if ( v13 < 0 )
    {
      v8 = (unsigned int)v13;
      goto LABEL_20;
    }
  }
  v14 = FWDeleteFirewallRule((__int64)v17, *(_QWORD *)(MatchingOpenPortRule + 16));
  v7 = v14;
  if ( v14 > 0 )
    v7 = (unsigned __int16)v14 | 0x80070000;
  if ( v7 < 0 )
  {
LABEL_7:
    v8 = (unsigned int)v7;
LABEL_20:
    FwReportReturnError("FwOpenPorts::Remove", v8);
  }
LABEL_21:
  FWFreeFirewallRules(v18, v10, v12);
  CloseLocalPolicyStore(v17);
  if ( v7 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPorts::Remove", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800021f0  mov     [rsp-28h+arg_18], rbx
0x1800021f5  push    rbp
0x1800021f6  push    rsi
0x1800021f7  push    rdi
0x1800021f8  push    r12
0x1800021fa  push    r14
0x1800021fc  mov     rbp, rsp
0x1800021ff  sub     rsp, 50h
0x180002203  mov     rax, cs:__security_cookie
0x18000220a  xor     rax, rsp
0x18000220d  mov     [rbp+var_8], rax
0x180002211  mov     [rbp+var_10], 0
0x180002219  mov     edi, r8d
0x18000221c  mov     [rbp+var_20], 0
0x180002223  mov     r14d, edx
0x180002226  mov     [rbp+var_18], 0
0x18000222e  mov     rsi, rcx
0x180002231  lea     r12, aFwopenportsRem; "FwOpenPorts::Remove"
0x180002238  cmp     edx, 0FFFFh
0x18000223e  ja      loc_180002335
0x180002244  cmp     r8d, 6
0x180002248  jz      short loc_180002254
0x18000224a  cmp     r8d, 11h
0x18000224e  jnz     loc_180002335
0x180002254  lea     rax, [rbp+var_18]
0x180002258  mov     r8d, 2
0x18000225e  mov     [rsp+50h+var_28], rax
0x180002263  mov     r9d, r8d
0x180002266  mov     ecx, 221h
0x18000226b  mov     dword ptr [rsp+50h+var_30], 0
0x180002273  xor     edx, edx
0x180002275  call    FWOpenPolicyStore
0x18000227a  mov     ebx, eax
0x18000227c  test    eax, eax
0x18000227e  jle     short loc_180002289
0x180002280  movzx   ebx, ax
0x180002283  or      ebx, 80070000h
0x180002289  test    ebx, ebx
0x18000228b  jns     short loc_180002294
0x18000228d  mov     edx, ebx
0x18000228f  jmp     loc_18000233C
0x180002294  mov     r8d, [rsi+18h]
0x180002298  lea     rax, [rbp+var_10]
0x18000229c  mov     rcx, [rbp+var_18]
0x1800022a0  mov     r9d, 7
0x1800022a6  mov     [rsp+50h+var_28], rax
0x1800022ab  mov     edx, 30000h
0x1800022b0  lea     rax, [rbp+var_20]
0x1800022b4  mov     [rsp+50h+var_30], rax
0x1800022b9  call    FWEnumFirewallRules
0x1800022be  mov     ebx, eax
0x1800022c0  test    eax, eax
0x1800022c2  jle     short loc_1800022CD
0x1800022c4  movzx   ebx, ax
0x1800022c7  or      ebx, 80070000h
0x1800022cd  test    ebx, ebx
0x1800022cf  js      short loc_18000228D
0x1800022d1  mov     edx, [rbp+var_20]
0x1800022d4  mov     r9d, edi
0x1800022d7  mov     rcx, [rbp+var_10]
0x1800022db  mov     r8d, r14d
0x1800022de  call    cs:__imp_FwFindMatchingOpenPortRule
0x1800022e4  mov     rdi, rax
0x1800022e7  test    rax, rax
0x1800022ea  jz      short loc_180002345
0x1800022ec  mov     r8d, [rsi+18h]; unsigned int
0x1800022f0  mov     eax, r8d
0x1800022f3  not     eax
0x1800022f5  test    [rdi+28h], eax
0x1800022f8  jz      short loc_180002310
0x1800022fa  mov     rcx, [rbp+var_18]; void *
0x1800022fe  mov     rdx, rdi; struct _tag_FW_RULE *
0x180002301  call    ?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; FwSplitRule(void *,_tag_FW_RULE *,ulong)
0x180002306  mov     ebx, eax
0x180002308  test    eax, eax
0x18000230a  jns     short loc_180002310
0x18000230c  mov     edx, eax
0x18000230e  jmp     short loc_18000233C
0x180002310  mov     rdx, [rdi+10h]
0x180002314  mov     rcx, [rbp+var_18]
0x180002318  call    FWDeleteFirewallRule
0x18000231d  mov     ebx, eax
0x18000231f  test    eax, eax
0x180002321  jle     short loc_18000232C
0x180002323  movzx   ebx, ax
0x180002326  or      ebx, 80070000h
0x18000232c  test    ebx, ebx
0x18000232e  jns     short loc_180002345
0x180002330  jmp     loc_18000228D
0x180002335  mov     edx, 80070057h
0x18000233a  mov     ebx, edx
0x18000233c  mov     rcx, r12
0x18000233f  call    cs:__imp_FwReportReturnError
0x180002345  mov     rcx, [rbp+var_10]
0x180002349  call    FWFreeFirewallRules
0x18000234e  mov     rcx, [rbp+var_18]; void *
0x180002352  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180002357  test    ebx, ebx
0x180002359  jns     short loc_180002368
0x18000235b  mov     edx, ebx
0x18000235d  mov     rcx, r12
0x180002360  call    cs:__imp_FwReportReturnError
0x180002366  mov     ebx, eax
0x180002368  mov     eax, ebx
0x18000236a  mov     rcx, [rbp+var_8]
0x18000236e  xor     rcx, rsp; StackCookie
0x180002371  call    __security_check_cookie
0x180002376  mov     rbx, [rsp+50h+arg_18]
0x18000237e  add     rsp, 50h
0x180002382  pop     r14
0x180002384  pop     r12
0x180002386  pop     rdi
0x180002387  pop     rsi
0x180002388  pop     rbp
0x180002389  retn
```
