# FwOpenPort::Initialize(_tag_FW_PROFILE_TYPE,ushort,NET_FW_IP_PROTOCOL_,_tag_FW_RULE * const)

- ea: `0x180039168`
- end: `0x1800392ba`
- name: `?Initialize@FwOpenPort@@AEAAJW4_tag_FW_PROFILE_TYPE@@GW4NET_FW_IP_PROTOCOL_@@QEAU_tag_FW_RULE@@@Z`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800390a0`

## callees

- `0x180003520`
- `0x180009080`
- `0x18000b34c`
- `0x18000b8c0`
- `0x1800277b0`
- `0x180039168`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18003920d`
- `fwbase!FwReportReturnError` at `0x180039249`
- `fwbase!FwReportReturnError` at `0x18003920d`
- `fwbase!FwReportReturnError` at `0x180039249`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800391fa`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800391fa`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x1800392a4`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x1800392a4`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800391cb`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800391cb`

## string_xrefs

- `0x18003918a`: `FwOpenPort::Initialize`

## pseudocode

```c
__int64 __fastcall FwOpenPort::Initialize(__int64 a1, int a2, unsigned __int16 a3, unsigned int a4, __int64 a5)
{
  __int64 MatchingOpenPortRule; // rax
  unsigned int v6; // esi
  int v9; // eax
  signed int v10; // ebx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h] BYREF
  void *v16; // [rsp+40h] [rbp-38h] BYREF

  MatchingOpenPortRule = a5;
  v6 = a3;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  *(_DWORD *)(a1 + 64) = a2;
  if ( a5 )
  {
    *(_DWORD *)(a1 + 80) = 1;
    goto LABEL_3;
  }
  v9 = OpenLocalPolicyStore(1, &v16);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v13 = FWEnumFirewallRules((_DWORD)v16, 196608, *(_DWORD *)(a1 + 64), 7, (__int64)&v14, (__int64)&v15);
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    if ( v10 >= 0 )
    {
      MatchingOpenPortRule = FwFindMatchingOpenPortRule(v15, v14, v6, a4);
      if ( MatchingOpenPortRule )
      {
LABEL_3:
        v9 = FwCopyRule(MatchingOpenPortRule, a1 + 72);
        v10 = v9;
        if ( v9 >= 0 )
        {
          *(_DWORD *)(a1 + 84) = 1;
          goto LABEL_5;
        }
        goto LABEL_9;
      }
      v10 = -2147024894;
    }
    v12 = (unsigned int)v10;
    goto LABEL_10;
  }
LABEL_9:
  v12 = (unsigned int)v9;
LABEL_10:
  FwReportReturnError("FwOpenPort::Initialize", v12);
LABEL_5:
  FWFreeFirewallRules(v15);
  CloseLocalPolicyStore(v16);
  if ( v10 < 0 )
  {
    FwFreeWFRule(*(_QWORD *)(a1 + 72));
    *(_QWORD *)(a1 + 72) = 0;
    return (unsigned int)FwReportReturnError("FwOpenPort::Initialize", (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180039168  push    rbx
0x18003916a  push    rbp
0x18003916b  push    rsi
0x18003916c  push    rdi
0x18003916d  push    r15
0x18003916f  sub     rsp, 50h
0x180039173  mov     rax, cs:__security_cookie
0x18003917a  xor     rax, rsp
0x18003917d  mov     [rsp+78h+var_30], rax
0x180039182  mov     rax, [rsp+78h+arg_20]
0x18003918a  lea     r15, aFwopenportInit; "FwOpenPort::Initialize"
0x180039191  movzx   esi, r8w
0x180039195  mov     ebp, r9d
0x180039198  mov     [rsp+78h+var_40], 0
0x1800391a1  mov     rdi, rcx
0x1800391a4  mov     [rsp+78h+var_48], 0
0x1800391ac  mov     [rsp+78h+var_38], 0
0x1800391b5  mov     [rcx+40h], edx
0x1800391b8  test    rax, rax
0x1800391bb  jz      short loc_18003922F
0x1800391bd  mov     dword ptr [rcx+50h], 1
0x1800391c4  lea     rdx, [rdi+48h]
0x1800391c8  mov     rcx, rax
0x1800391cb  call    cs:__imp_FwCopyRule
0x1800391d1  mov     ebx, eax
0x1800391d3  test    eax, eax
0x1800391d5  js      short loc_180039244
0x1800391d7  mov     dword ptr [rdi+54h], 1
0x1800391de  mov     rcx, [rsp+78h+var_40]
0x1800391e3  call    FWFreeFirewallRules
0x1800391e8  mov     rcx, [rsp+78h+var_38]; void *
0x1800391ed  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x1800391f2  test    ebx, ebx
0x1800391f4  jns     short loc_180039215
0x1800391f6  mov     rcx, [rdi+48h]
0x1800391fa  call    cs:__imp_FwFreeWFRule
0x180039200  mov     edx, ebx
0x180039202  mov     qword ptr [rdi+48h], 0
0x18003920a  mov     rcx, r15
0x18003920d  call    cs:__imp_FwReportReturnError
0x180039213  mov     ebx, eax
0x180039215  mov     eax, ebx
0x180039217  mov     rcx, [rsp+78h+var_30]
0x18003921c  xor     rcx, rsp; StackCookie
0x18003921f  call    __security_check_cookie
0x180039224  add     rsp, 50h
0x180039228  pop     r15
0x18003922a  pop     rdi
0x18003922b  pop     rsi
0x18003922c  pop     rbp
0x18003922d  pop     rbx
0x18003922e  retn
0x18003922f  lea     rdx, [rsp+78h+var_38]
0x180039234  mov     ecx, 1
0x180039239  call    ?OpenLocalPolicyStore@@YAJW4_tag_FW_POLICY_ACCESS_RIGHT@@PEAPEAX@Z; OpenLocalPolicyStore(_tag_FW_POLICY_ACCESS_RIGHT,void * *)
0x18003923e  mov     ebx, eax
0x180039240  test    eax, eax
0x180039242  jns     short loc_180039251
0x180039244  mov     edx, eax
0x180039246  mov     rcx, r15
0x180039249  call    cs:__imp_FwReportReturnError
0x18003924f  jmp     short loc_1800391DE
0x180039251  mov     r8d, [rdi+40h]
0x180039255  lea     rax, [rsp+78h+var_40]
0x18003925a  mov     rcx, [rsp+78h+var_38]
0x18003925f  mov     r9d, 7
0x180039265  mov     [rsp+78h+var_50], rax
0x18003926a  mov     edx, 30000h
0x18003926f  lea     rax, [rsp+78h+var_48]
0x180039274  mov     [rsp+78h+var_58], rax
0x180039279  call    FWEnumFirewallRules
0x18003927e  mov     ebx, eax
0x180039280  test    eax, eax
0x180039282  jle     short loc_18003928D
0x180039284  movzx   ebx, ax
0x180039287  or      ebx, 80070000h
0x18003928d  test    ebx, ebx
0x18003928f  jns     short loc_180039295
0x180039291  mov     edx, ebx
0x180039293  jmp     short loc_180039246
0x180039295  mov     edx, [rsp+78h+var_48]
0x180039299  mov     r8d, esi
0x18003929c  mov     rcx, [rsp+78h+var_40]
0x1800392a1  mov     r9d, ebp
0x1800392a4  call    cs:__imp_FwFindMatchingOpenPortRule
0x1800392aa  test    rax, rax
0x1800392ad  jnz     loc_1800391C4
0x1800392b3  mov     ebx, 80070002h
0x1800392b8  jmp     short loc_180039291
```
