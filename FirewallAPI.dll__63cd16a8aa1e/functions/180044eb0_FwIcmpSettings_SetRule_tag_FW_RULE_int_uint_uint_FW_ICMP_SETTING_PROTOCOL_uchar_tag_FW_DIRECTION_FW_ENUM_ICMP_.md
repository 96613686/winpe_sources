# FwIcmpSettings::SetRule(_tag_FW_RULE * *,int,uint,uint,FW_ICMP_SETTING_PROTOCOL_,uchar,_tag_FW_DIRECTION,FW_ENUM_ICMP_SETTING_)

- ea: `0x180044eb0`
- end: `0x1800450bd`
- name: `?SetRule@FwIcmpSettings@@AEAAJPEAPEAU_tag_FW_RULE@@HIIW4FW_ICMP_SETTING_PROTOCOL_@@EW4_tag_FW_DIRECTION@@W4FW_ENUM_ICMP_SETTING_@@@Z`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044ba4`

## callees

- `0x180003520`
- `0x18000b34c`
- `0x1800140b0`
- `0x180014690`
- `0x1800277b0`
- `0x18003063c`
- `0x180044eb0`

## import_xrefs

- `fwbase!FwBuildIndirectString` at `0x180045024`
- `fwbase!FwBuildIndirectString` at `0x18004503f`
- `fwbase!FwBuildIndirectString` at `0x180045024`
- `fwbase!FwBuildIndirectString` at `0x18004503f`
- `fwbase!FwReportReturnError` at `0x18004507e`
- `fwbase!FwReportReturnError` at `0x180045097`
- `fwbase!FwReportReturnError` at `0x18004507e`
- `fwbase!FwReportReturnError` at `0x180045097`
- `fwbase!FwStringCopy` at `0x18004500d`
- `fwbase!FwStringCopy` at `0x18004500d`
- `FWPolicyIOMgr!CreateDefaultIcmpRule` at `0x180044f72`
- `FWPolicyIOMgr!CreateDefaultIcmpRule` at `0x180044f72`

## string_xrefs

- `0x180045006`: `@FirewallAPI.dll,-28502`

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
      v19 = FWSetFirewallRule((unsigned __int16 *)v25, (_OWORD *)v9);
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
0x180044eb0  push    rbx
0x180044eb2  push    rbp
0x180044eb3  push    rsi
0x180044eb4  push    rdi
0x180044eb5  push    r12
0x180044eb7  push    r14
0x180044eb9  push    r15
0x180044ebb  sub     rsp, 30h
0x180044ebf  mov     rax, cs:__security_cookie
0x180044ec6  xor     rax, rsp
0x180044ec9  mov     [rsp+68h+var_40], rax
0x180044ece  mov     rdi, [rdx]
0x180044ed1  mov     rsi, rdx
0x180044ed4  mov     rbp, rcx
0x180044ed7  mov     [rsp+68h+var_48], 0
0x180044ee0  lea     rdx, [rsp+68h+var_48]
0x180044ee5  mov     ecx, 2
0x180044eea  mov     r15d, r9d
0x180044eed  mov     r14d, r8d
0x180044ef0  call    ?OpenLocalPolicyStore@@YAJW4_tag_FW_POLICY_ACCESS_RIGHT@@PEAPEAX@Z; OpenLocalPolicyStore(_tag_FW_POLICY_ACCESS_RIGHT,void * *)
0x180044ef5  lea     r12, aFwicmpsettings_5; "FwIcmpSettings::SetRule"
0x180044efc  mov     ebx, eax
0x180044efe  test    eax, eax
0x180044f00  jns     short loc_180044F09
0x180044f02  mov     edx, eax
0x180044f04  jmp     loc_18004507B
0x180044f09  test    rdi, rdi
0x180044f0c  jz      short loc_180044F6C
0x180044f0e  mov     r8d, [rbp+18h]; unsigned int
0x180044f12  mov     eax, r8d
0x180044f15  not     eax
0x180044f17  test    [rdi+28h], eax
0x180044f1a  jz      short loc_180044F2F
0x180044f1c  mov     rcx, [rsp+68h+var_48]; void *
0x180044f21  mov     rdx, rdi; struct _tag_FW_RULE *
0x180044f24  call    ?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; FwSplitRule(void *,_tag_FW_RULE *,ulong)
0x180044f29  mov     ebx, eax
0x180044f2b  test    eax, eax
0x180044f2d  js      short loc_180044F02
0x180044f2f  movzx   eax, word ptr [rdi+124h]
0x180044f36  test    r14d, r14d
0x180044f39  jz      short loc_180044F4B
0x180044f3b  mov     dword ptr [rdi+120h], 3
0x180044f45  or      ax, 1
0x180044f49  jmp     short loc_180044F53
0x180044f4b  mov     ecx, 0FFFEh
0x180044f50  and     ax, cx
0x180044f53  mov     [rdi+124h], ax
0x180044f5a  mov     rdx, rdi; Src
0x180044f5d  mov     rcx, [rsp+68h+var_48]; __int64
0x180044f62  call    FWSetFirewallRule
0x180044f67  jmp     loc_180045066
0x180044f6c  mov     edx, [rbp+18h]
0x180044f6f  mov     rcx, rsi
0x180044f72  call    cs:__imp_?CreateDefaultIcmpRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultIcmpRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x180044f78  mov     ebx, eax
0x180044f7a  test    eax, eax
0x180044f7c  js      short loc_180044F02
0x180044f7e  mov     ecx, [rsp+68h+arg_28]
0x180044f85  mov     rdi, [rsi]
0x180044f88  test    ecx, ecx
0x180044f8a  jz      short loc_180044FA8
0x180044f8c  cmp     ecx, 1
0x180044f8f  jz      short loc_180044F9B
0x180044f91  mov     ebx, 8000FFFFh
0x180044f96  jmp     loc_180045079
0x180044f9b  mov     word ptr [rdi+30h], 3Ah ; ':'
0x180044fa1  mov     edx, 1
0x180044fa6  jmp     short loc_180044FB1
0x180044fa8  mov     edx, 1
0x180044fad  mov     [rdi+30h], dx
0x180044fb1  mov     rcx, [rdi+40h]
0x180044fb5  mov     al, [rsp+68h+arg_30]
0x180044fbc  mov     [rdi+38h], edx
0x180044fbf  mov     [rcx], al
0x180044fc1  mov     rax, [rdi+40h]
0x180044fc5  mov     word ptr [rax+2], 100h
0x180044fcb  movzx   eax, word ptr [rdi+124h]
0x180044fd2  test    r14d, r14d
0x180044fd5  jz      short loc_180044FE6
0x180044fd7  mov     dword ptr [rdi+120h], 3
0x180044fe1  or      ax, dx
0x180044fe4  jmp     short loc_180044FEE
0x180044fe6  mov     ecx, 0FFFEh
0x180044feb  and     ax, cx
0x180044fee  cmp     [rsp+68h+arg_40], 2
0x180044ff6  mov     [rdi+124h], ax
0x180044ffd  jnz     short loc_18004501D
0x180044fff  lea     rdx, [rdi+138h]
0x180045006  lea     rcx, aFirewallapiDll_9; "@FirewallAPI.dll,-28502"
0x18004500d  call    cs:__imp_FwStringCopy
0x180045013  mov     ebx, eax
0x180045015  test    eax, eax
0x180045017  js      loc_180044F02
0x18004501d  lea     rdx, [rdi+18h]
0x180045021  mov     ecx, r15d
0x180045024  call    cs:__imp_FwBuildIndirectString
0x18004502a  mov     ebx, eax
0x18004502c  test    eax, eax
0x18004502e  js      loc_180044F02
0x180045034  mov     ecx, [rsp+68h+arg_20]
0x18004503b  lea     rdx, [rdi+20h]
0x18004503f  call    cs:__imp_FwBuildIndirectString
0x180045045  mov     ebx, eax
0x180045047  test    eax, eax
0x180045049  js      loc_180044F02
0x18004504f  mov     eax, [rsp+68h+arg_38]
0x180045056  mov     rdx, rdi; Src
0x180045059  mov     [rdi+2Ch], eax
0x18004505c  mov     rcx, [rsp+68h+var_48]; __int64
0x180045061  call    FWAddFirewallRule
0x180045066  mov     ebx, eax
0x180045068  test    eax, eax
0x18004506a  jle     short loc_180045075
0x18004506c  movzx   ebx, ax
0x18004506f  or      ebx, 80070000h
0x180045075  test    ebx, ebx
0x180045077  jns     short loc_180045084
0x180045079  mov     edx, ebx
0x18004507b  mov     rcx, r12
0x18004507e  call    cs:__imp_FwReportReturnError
0x180045084  mov     rcx, [rsp+68h+var_48]; void *
0x180045089  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x18004508e  test    ebx, ebx
0x180045090  jns     short loc_18004509F
0x180045092  mov     edx, ebx
0x180045094  mov     rcx, r12
0x180045097  call    cs:__imp_FwReportReturnError
0x18004509d  mov     ebx, eax
0x18004509f  mov     eax, ebx
0x1800450a1  mov     rcx, [rsp+68h+var_40]
0x1800450a6  xor     rcx, rsp; StackCookie
0x1800450a9  call    __security_check_cookie
0x1800450ae  add     rsp, 30h
0x1800450b2  pop     r15
0x1800450b4  pop     r14
0x1800450b6  pop     r12
0x1800450b8  pop     rdi
0x1800450b9  pop     rsi
0x1800450ba  pop     rbp
0x1800450bb  pop     rbx
0x1800450bc  retn
```
