# FwIcmpSettings::SetRule(_tag_FW_RULE * *,int,uint,uint,FW_ICMP_SETTING_PROTOCOL_,uchar,_tag_FW_DIRECTION,FW_ENUM_ICMP_SETTING_)

- ea: `0x1800484dc`
- end: `0x180048712`
- name: `?SetRule@FwIcmpSettings@@AEAAJPEAPEAU_tag_FW_RULE@@HIIW4FW_ICMP_SETTING_PROTOCOL_@@EW4_tag_FW_DIRECTION@@W4FW_ENUM_ICMP_SETTING_@@@Z`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800481a8`

## callees

- `0x1800037dc`
- `0x18000be5c`
- `0x180014110`
- `0x180014720`
- `0x1800294b0`
- `0x180032840`
- `0x1800484dc`

## import_xrefs

- `fwbase!FwBuildIndirectString` at `0x180048660`
- `fwbase!FwBuildIndirectString` at `0x180048681`
- `fwbase!FwBuildIndirectString` at `0x180048660`
- `fwbase!FwBuildIndirectString` at `0x180048681`
- `fwbase!FwReportReturnError` at `0x1800486c6`
- `fwbase!FwReportReturnError` at `0x1800486e5`
- `fwbase!FwReportReturnError` at `0x1800486c6`
- `fwbase!FwReportReturnError` at `0x1800486e5`
- `fwbase!FwStringCopy` at `0x180048643`
- `fwbase!FwStringCopy` at `0x180048643`
- `FWPolicyIOMgr!CreateDefaultIcmpRule` at `0x18004859e`
- `FWPolicyIOMgr!CreateDefaultIcmpRule` at `0x18004859e`

## string_xrefs

- `0x18004863c`: `@FirewallAPI.dll,-28502`

## pseudocode

```c
__int64 __fastcall FwIcmpSettings::SetRule(
        __int64 a1,
        __int64 *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        char a7,
        int a8,
        int a9)
{
  __int64 v9; // rdi
  int DefaultIcmpRule; // eax
  signed int v15; // ebx
  __int64 v16; // rdx
  __int16 v17; // ax
  __int16 v18; // ax
  int v19; // eax
  __int64 v20; // rdi
  _BYTE *v21; // rcx
  __int16 v22; // ax
  __int16 v23; // ax
  void *v25; // [rsp+20h] [rbp-48h] BYREF

  v9 = *a2;
  v25 = 0;
  DefaultIcmpRule = OpenLocalPolicyStore(2, &v25);
  v15 = DefaultIcmpRule;
  if ( DefaultIcmpRule < 0 )
    goto LABEL_2;
  if ( v9 )
  {
    if ( (~*(_DWORD *)(a1 + 24) & *(_DWORD *)(v9 + 40)) == 0
      || (DefaultIcmpRule = FwSplitRule(v25, (struct _tag_FW_RULE *)v9, *(_DWORD *)(a1 + 24)),
          v15 = DefaultIcmpRule,
          DefaultIcmpRule >= 0) )
    {
      v17 = *(_WORD *)(v9 + 292);
      if ( a3 )
      {
        *(_DWORD *)(v9 + 288) = 3;
        v18 = v17 | 1;
      }
      else
      {
        v18 = v17 & 0xFFFE;
      }
      *(_WORD *)(v9 + 292) = v18;
      v19 = FWSetFirewallRule((__int64)v25, (void *)v9);
      goto LABEL_24;
    }
LABEL_2:
    v16 = (unsigned int)DefaultIcmpRule;
LABEL_28:
    FwReportReturnError("FwIcmpSettings::SetRule", v16);
    goto LABEL_29;
  }
  DefaultIcmpRule = CreateDefaultIcmpRule(a2, *(unsigned int *)(a1 + 24));
  v15 = DefaultIcmpRule;
  if ( DefaultIcmpRule < 0 )
    goto LABEL_2;
  v20 = *a2;
  if ( a6 )
  {
    if ( a6 != 1 )
    {
      v15 = -2147418113;
LABEL_27:
      v16 = (unsigned int)v15;
      goto LABEL_28;
    }
    *(_WORD *)(v20 + 48) = 58;
  }
  else
  {
    *(_WORD *)(v20 + 48) = 1;
  }
  v21 = *(_BYTE **)(v20 + 64);
  *(_DWORD *)(v20 + 56) = 1;
  *v21 = a7;
  *(_WORD *)(*(_QWORD *)(v20 + 64) + 2LL) = 256;
  v22 = *(_WORD *)(v20 + 292);
  if ( a3 )
  {
    *(_DWORD *)(v20 + 288) = 3;
    v23 = v22 | 1;
  }
  else
  {
    v23 = v22 & 0xFFFE;
  }
  *(_WORD *)(v20 + 292) = v23;
  if ( a9 == 2 )
  {
    DefaultIcmpRule = FwStringCopy(L"@FirewallAPI.dll,-28502", v20 + 312);
    v15 = DefaultIcmpRule;
    if ( DefaultIcmpRule < 0 )
      goto LABEL_2;
  }
  DefaultIcmpRule = FwBuildIndirectString(a4, v20 + 24);
  v15 = DefaultIcmpRule;
  if ( DefaultIcmpRule < 0 )
    goto LABEL_2;
  DefaultIcmpRule = FwBuildIndirectString(a5, v20 + 32);
  v15 = DefaultIcmpRule;
  if ( DefaultIcmpRule < 0 )
    goto LABEL_2;
  *(_DWORD *)(v20 + 44) = a8;
  v19 = FWAddFirewallRule((__int64)v25, (void *)v20);
LABEL_24:
  v15 = v19;
  if ( v19 > 0 )
    v15 = (unsigned __int16)v19 | 0x80070000;
  if ( v15 < 0 )
    goto LABEL_27;
LABEL_29:
  CloseLocalPolicyStore(v25);
  if ( v15 < 0 )
    return (unsigned int)FwReportReturnError("FwIcmpSettings::SetRule", (unsigned int)v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800484dc  push    rbx
0x1800484de  push    rbp
0x1800484df  push    rsi
0x1800484e0  push    rdi
0x1800484e1  push    r12
0x1800484e3  push    r14
0x1800484e5  push    r15
0x1800484e7  sub     rsp, 30h
0x1800484eb  mov     rax, cs:__security_cookie
0x1800484f2  xor     rax, rsp
0x1800484f5  mov     [rsp+68h+var_40], rax
0x1800484fa  mov     rdi, [rdx]
0x1800484fd  mov     rsi, rdx
0x180048500  mov     rbp, rcx
0x180048503  mov     [rsp+68h+var_48], 0
0x18004850c  lea     rdx, [rsp+68h+var_48]
0x180048511  mov     ecx, 2
0x180048516  mov     r15d, r9d
0x180048519  mov     r14d, r8d
0x18004851c  call    ?OpenLocalPolicyStore@@YAJW4_tag_FW_POLICY_ACCESS_RIGHT@@PEAPEAX@Z; OpenLocalPolicyStore(_tag_FW_POLICY_ACCESS_RIGHT,void * *)
0x180048521  lea     r12, aFwicmpsettings_5; "FwIcmpSettings::SetRule"
0x180048528  mov     ebx, eax
0x18004852a  test    eax, eax
0x18004852c  jns     short loc_180048535
0x18004852e  mov     edx, eax
0x180048530  jmp     loc_1800486C3
0x180048535  test    rdi, rdi
0x180048538  jz      short loc_180048598
0x18004853a  mov     r8d, [rbp+18h]; unsigned int
0x18004853e  mov     eax, r8d
0x180048541  not     eax
0x180048543  test    [rdi+28h], eax
0x180048546  jz      short loc_18004855B
0x180048548  mov     rcx, [rsp+68h+var_48]; void *
0x18004854d  mov     rdx, rdi; struct _tag_FW_RULE *
0x180048550  call    ?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; FwSplitRule(void *,_tag_FW_RULE *,ulong)
0x180048555  mov     ebx, eax
0x180048557  test    eax, eax
0x180048559  js      short loc_18004852E
0x18004855b  movzx   eax, word ptr [rdi+124h]
0x180048562  test    r14d, r14d
0x180048565  jz      short loc_180048577
0x180048567  mov     dword ptr [rdi+120h], 3
0x180048571  or      ax, 1
0x180048575  jmp     short loc_18004857F
0x180048577  mov     ecx, 0FFFEh
0x18004857c  and     ax, cx
0x18004857f  mov     [rdi+124h], ax
0x180048586  mov     rdx, rdi; Src
0x180048589  mov     rcx, [rsp+68h+var_48]; __int64
0x18004858e  call    FWSetFirewallRule
0x180048593  jmp     loc_1800486AE
0x180048598  mov     edx, [rbp+18h]
0x18004859b  mov     rcx, rsi
0x18004859e  call    cs:__imp_?CreateDefaultIcmpRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultIcmpRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x1800485a5  nop     dword ptr [rax+rax+00h]
0x1800485aa  mov     ebx, eax
0x1800485ac  test    eax, eax
0x1800485ae  js      loc_18004852E
0x1800485b4  mov     ecx, [rsp+68h+arg_28]
0x1800485bb  mov     rdi, [rsi]
0x1800485be  test    ecx, ecx
0x1800485c0  jz      short loc_1800485DE
0x1800485c2  cmp     ecx, 1
0x1800485c5  jz      short loc_1800485D1
0x1800485c7  mov     ebx, 8000FFFFh
0x1800485cc  jmp     loc_1800486C1
0x1800485d1  mov     word ptr [rdi+30h], 3Ah ; ':'
0x1800485d7  mov     edx, 1
0x1800485dc  jmp     short loc_1800485E7
0x1800485de  mov     edx, 1
0x1800485e3  mov     [rdi+30h], dx
0x1800485e7  mov     rcx, [rdi+40h]
0x1800485eb  mov     al, [rsp+68h+arg_30]
0x1800485f2  mov     [rdi+38h], edx
0x1800485f5  mov     [rcx], al
0x1800485f7  mov     rax, [rdi+40h]
0x1800485fb  mov     word ptr [rax+2], 100h
0x180048601  movzx   eax, word ptr [rdi+124h]
0x180048608  test    r14d, r14d
0x18004860b  jz      short loc_18004861C
0x18004860d  mov     dword ptr [rdi+120h], 3
0x180048617  or      ax, dx
0x18004861a  jmp     short loc_180048624
0x18004861c  mov     ecx, 0FFFEh
0x180048621  and     ax, cx
0x180048624  cmp     [rsp+68h+arg_40], 2
0x18004862c  mov     [rdi+124h], ax
0x180048633  jnz     short loc_180048659
0x180048635  lea     rdx, [rdi+138h]
0x18004863c  lea     rcx, aFirewallapiDll_9; "@FirewallAPI.dll,-28502"
0x180048643  call    cs:__imp_FwStringCopy
0x18004864a  nop     dword ptr [rax+rax+00h]
0x18004864f  mov     ebx, eax
0x180048651  test    eax, eax
0x180048653  js      loc_18004852E
0x180048659  lea     rdx, [rdi+18h]
0x18004865d  mov     ecx, r15d
0x180048660  call    cs:__imp_FwBuildIndirectString
0x180048667  nop     dword ptr [rax+rax+00h]
0x18004866c  mov     ebx, eax
0x18004866e  test    eax, eax
0x180048670  js      loc_18004852E
0x180048676  mov     ecx, [rsp+68h+arg_20]
0x18004867d  lea     rdx, [rdi+20h]
0x180048681  call    cs:__imp_FwBuildIndirectString
0x180048688  nop     dword ptr [rax+rax+00h]
0x18004868d  mov     ebx, eax
0x18004868f  test    eax, eax
0x180048691  js      loc_18004852E
0x180048697  mov     eax, [rsp+68h+arg_38]
0x18004869e  mov     rdx, rdi; Src
0x1800486a1  mov     [rdi+2Ch], eax
0x1800486a4  mov     rcx, [rsp+68h+var_48]; __int64
0x1800486a9  call    FWAddFirewallRule
0x1800486ae  mov     ebx, eax
0x1800486b0  test    eax, eax
0x1800486b2  jle     short loc_1800486BD
0x1800486b4  movzx   ebx, ax
0x1800486b7  or      ebx, 80070000h
0x1800486bd  test    ebx, ebx
0x1800486bf  jns     short loc_1800486D2
0x1800486c1  mov     edx, ebx
0x1800486c3  mov     rcx, r12
0x1800486c6  call    cs:__imp_FwReportReturnError
0x1800486cd  nop     dword ptr [rax+rax+00h]
0x1800486d2  mov     rcx, [rsp+68h+var_48]; void *
0x1800486d7  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x1800486dc  test    ebx, ebx
0x1800486de  jns     short loc_1800486F3
0x1800486e0  mov     edx, ebx
0x1800486e2  mov     rcx, r12
0x1800486e5  call    cs:__imp_FwReportReturnError
0x1800486ec  nop     dword ptr [rax+rax+00h]
0x1800486f1  mov     ebx, eax
0x1800486f3  mov     eax, ebx
0x1800486f5  mov     rcx, [rsp+68h+var_40]
0x1800486fa  xor     rcx, rsp; StackCookie
0x1800486fd  call    __security_check_cookie
0x180048702  add     rsp, 30h
0x180048706  pop     r15
0x180048708  pop     r14
0x18004870a  pop     r12
0x18004870c  pop     rdi
0x18004870d  pop     rsi
0x18004870e  pop     rbp
0x18004870f  pop     rbx
0x180048710  retn
```
