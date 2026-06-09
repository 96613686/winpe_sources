# FwAuthApp::Initialize(_tag_FW_PROFILE_TYPE,ushort const *)

- ea: `0x180002e3c`
- end: `0x18000301c`
- name: `?Initialize@FwAuthApp@@AEAAJW4_tag_FW_PROFILE_TYPE@@PEBG@Z`
- size: `480`
- prototype: `int __high(enum _tag_FW_PROFILE_TYPE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180002530`

## callees

- `0x180002e3c`
- `0x180003024`
- `0x180003520`
- `0x180009080`
- `0x18000b8c0`
- `0x18000c560`
- `0x1800277b0`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180002f4e`
- `fwbase!FwReportReturnError` at `0x180002f96`
- `fwbase!FwReportReturnError` at `0x180002f4e`
- `fwbase!FwReportReturnError` at `0x180002f96`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002fc0`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002fd2`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002fc0`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002fd2`
- `FWPolicyIOMgr!FwCopyRule` at `0x180002f35`
- `FWPolicyIOMgr!FwCopyRule` at `0x180002ff1`
- `FWPolicyIOMgr!FwCopyRule` at `0x180002f35`
- `FWPolicyIOMgr!FwCopyRule` at `0x180002ff1`

## pseudocode

```c
__int64 __fastcall FwAuthApp::Initialize(__int64 a1, int a2, const unsigned __int16 *a3)
{
  int v5; // eax
  signed int v6; // ebx
  int v7; // eax
  struct _tag_FW_RULE *MatchingAppRule; // rbx
  struct _tag_FW_RULE *v9; // rax
  struct _tag_FW_RULE *v10; // rsi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v16; // rcx
  unsigned int v17; // [rsp+30h] [rbp-20h] BYREF
  struct _tag_FW_RULE *v18; // [rsp+38h] [rbp-18h] BYREF
  void *v19; // [rsp+40h] [rbp-10h] BYREF

  *(_DWORD *)(a1 + 64) = a2;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v5 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, &v19);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_10;
  v7 = FWEnumFirewallRules((__int64)v19, 196608, *(_DWORD *)(a1 + 64), 7, (__int64)&v17, (__int64)&v18);
  v6 = v7;
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_10;
  MatchingAppRule = FwFindMatchingAppRule(v18, v17, a3, 6u);
  v9 = FwFindMatchingAppRule(v18, v17, a3, 0x11u);
  v10 = v9;
  if ( !MatchingAppRule )
  {
    if ( v9 )
    {
LABEL_18:
      v11 = FwCopyRule(v10, a1 + 80);
      v6 = v11;
      if ( v11 < 0 )
        goto LABEL_9;
      goto LABEL_19;
    }
    v6 = -2147024894;
LABEL_10:
    v14 = (unsigned int)v6;
    goto LABEL_11;
  }
  v11 = FwCopyRule(MatchingAppRule, a1 + 72);
  v6 = v11;
  if ( v11 < 0 )
  {
LABEL_9:
    v14 = (unsigned int)v11;
LABEL_11:
    FwReportReturnError("FwAuthApp::Initialize", v14);
    goto LABEL_12;
  }
  if ( v10 )
    goto LABEL_18;
LABEL_19:
  *(_DWORD *)(a1 + 88) = 1;
LABEL_12:
  FWFreeFirewallRules((__int64)v18, v12, v13);
  if ( v6 < 0 )
  {
    FwFreeWFRule(*(_QWORD *)(a1 + 72));
    v16 = *(_QWORD *)(a1 + 80);
    *(_QWORD *)(a1 + 72) = 0;
    FwFreeWFRule(v16);
    *(_QWORD *)(a1 + 80) = 0;
  }
  CloseLocalPolicyStore(v19);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::Initialize", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002e3c  mov     [rsp-18h+arg_8], rbx
0x180002e41  mov     [rsp-18h+arg_18], rsi
0x180002e46  push    rbp
0x180002e47  push    rdi
0x180002e48  push    r15
0x180002e4a  mov     rbp, rsp
0x180002e4d  sub     rsp, 50h
0x180002e51  mov     rax, cs:__security_cookie
0x180002e58  xor     rax, rsp
0x180002e5b  mov     [rbp+var_8], rax
0x180002e5f  mov     [rcx+40h], edx
0x180002e62  lea     rax, [rbp+var_10]
0x180002e66  xor     edx, edx
0x180002e68  mov     [rsp+50h+var_28], rax
0x180002e6d  mov     rsi, r8
0x180002e70  mov     [rbp+var_18], 0
0x180002e78  mov     rdi, rcx
0x180002e7b  mov     [rbp+var_20], 0
0x180002e82  mov     ecx, 221h
0x180002e87  mov     [rbp+var_10], 0
0x180002e8f  lea     r9d, [rdx+1]
0x180002e93  mov     dword ptr [rsp+50h+var_30], 0
0x180002e9b  lea     r8d, [rdx+2]
0x180002e9f  call    FWOpenPolicyStore
0x180002ea4  mov     ebx, eax
0x180002ea6  test    eax, eax
0x180002ea8  jg      loc_180002FA0
0x180002eae  lea     r15, aFwauthappIniti; "FwAuthApp::Initialize"
0x180002eb5  test    ebx, ebx
0x180002eb7  js      loc_180002F49
0x180002ebd  mov     r8d, [rdi+40h]
0x180002ec1  lea     rax, [rbp+var_18]
0x180002ec5  mov     rcx, [rbp+var_10]
0x180002ec9  mov     r9d, 7
0x180002ecf  mov     [rsp+50h+var_28], rax
0x180002ed4  mov     edx, 30000h
0x180002ed9  lea     rax, [rbp+var_20]
0x180002edd  mov     [rsp+50h+var_30], rax
0x180002ee2  call    FWEnumFirewallRules
0x180002ee7  mov     ebx, eax
0x180002ee9  test    eax, eax
0x180002eeb  jg      loc_180002FAE
0x180002ef1  test    ebx, ebx
0x180002ef3  js      short loc_180002F49
0x180002ef5  mov     edx, [rbp+var_20]; unsigned int
0x180002ef8  mov     r9d, 6; unsigned __int16
0x180002efe  mov     rcx, [rbp+var_18]; struct _tag_FW_RULE *
0x180002f02  mov     r8, rsi; unsigned __int16 *
0x180002f05  call    ?FwFindMatchingAppRule@@YAPEAU_tag_FW_RULE@@QEAU1@KPEBGG@Z; FwFindMatchingAppRule(_tag_FW_RULE * const,ulong,ushort const *,ushort)
0x180002f0a  mov     edx, [rbp+var_20]; unsigned int
0x180002f0d  mov     r9d, 11h; unsigned __int16
0x180002f13  mov     rcx, [rbp+var_18]; struct _tag_FW_RULE *
0x180002f17  mov     r8, rsi; unsigned __int16 *
0x180002f1a  mov     rbx, rax
0x180002f1d  call    ?FwFindMatchingAppRule@@YAPEAU_tag_FW_RULE@@QEAU1@KPEBGG@Z; FwFindMatchingAppRule(_tag_FW_RULE * const,ulong,ushort const *,ushort)
0x180002f22  mov     rsi, rax
0x180002f25  test    rbx, rbx
0x180002f28  jz      loc_18000300D
0x180002f2e  lea     rdx, [rdi+48h]
0x180002f32  mov     rcx, rbx
0x180002f35  call    cs:__imp_FwCopyRule
0x180002f3b  mov     ebx, eax
0x180002f3d  test    eax, eax
0x180002f3f  jns     loc_180002FE5
0x180002f45  mov     edx, eax
0x180002f47  jmp     short loc_180002F4B
0x180002f49  mov     edx, ebx
0x180002f4b  mov     rcx, r15
0x180002f4e  call    cs:__imp_FwReportReturnError
0x180002f54  mov     rcx, [rbp+var_18]
0x180002f58  call    FWFreeFirewallRules
0x180002f5d  test    ebx, ebx
0x180002f5f  js      short loc_180002FBC
0x180002f61  mov     rcx, [rbp+var_10]; void *
0x180002f65  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180002f6a  test    ebx, ebx
0x180002f6c  js      short loc_180002F91
0x180002f6e  mov     eax, ebx
0x180002f70  mov     rcx, [rbp+var_8]
0x180002f74  xor     rcx, rsp; StackCookie
0x180002f77  call    __security_check_cookie
0x180002f7c  lea     r11, [rsp+50h+var_s0]
0x180002f81  mov     rbx, [r11+28h]
0x180002f85  mov     rsi, [r11+38h]
0x180002f89  mov     rsp, r11
0x180002f8c  pop     r15
0x180002f8e  pop     rdi
0x180002f8f  pop     rbp
0x180002f90  retn
0x180002f91  mov     edx, ebx
0x180002f93  mov     rcx, r15
0x180002f96  call    cs:__imp_FwReportReturnError
0x180002f9c  mov     ebx, eax
0x180002f9e  jmp     short loc_180002F6E
0x180002fa0  movzx   ebx, ax
0x180002fa3  or      ebx, 80070000h
0x180002fa9  jmp     loc_180002EAE
0x180002fae  movzx   ebx, ax
0x180002fb1  or      ebx, 80070000h
0x180002fb7  jmp     loc_180002EF1
0x180002fbc  mov     rcx, [rdi+48h]
0x180002fc0  call    cs:__imp_FwFreeWFRule
0x180002fc6  mov     rcx, [rdi+50h]
0x180002fca  mov     qword ptr [rdi+48h], 0
0x180002fd2  call    cs:__imp_FwFreeWFRule
0x180002fd8  mov     qword ptr [rdi+50h], 0
0x180002fe0  jmp     loc_180002F61
0x180002fe5  test    rsi, rsi
0x180002fe8  jz      short loc_180003001
0x180002fea  lea     rdx, [rdi+50h]
0x180002fee  mov     rcx, rsi
0x180002ff1  call    cs:__imp_FwCopyRule
0x180002ff7  mov     ebx, eax
0x180002ff9  test    eax, eax
0x180002ffb  js      loc_180002F45
0x180003001  mov     dword ptr [rdi+58h], 1
0x180003008  jmp     loc_180002F54
0x18000300d  test    rsi, rsi
0x180003010  jnz     short loc_180002FEA
0x180003012  mov     ebx, 80070002h
0x180003017  jmp     loc_180002F49
```
