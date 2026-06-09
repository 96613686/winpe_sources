# CheckUserPrefMergeForProfileType(winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes)

- ea: `0x180027498`
- end: `0x180027615`
- name: `?CheckUserPrefMergeForProfileType@@YA_NW4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@@Z`
- size: `381`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022ecc`

## callees

- `0x1800148d0`
- `0x180027498`
- `0x18002937c`

## import_xrefs

- `FirewallAPI!FWClosePolicyStore` at `0x180027566`
- `FirewallAPI!FWClosePolicyStore` at `0x1800275b6`
- `FirewallAPI!FWClosePolicyStore` at `0x1800275c5`
- `FirewallAPI!FWClosePolicyStore` at `0x180027566`
- `FirewallAPI!FWClosePolicyStore` at `0x1800275b6`
- `FirewallAPI!FWClosePolicyStore` at `0x1800275c5`
- `FirewallAPI!FwIsGroupPolicyEnforced` at `0x1800274b1`
- `FirewallAPI!FwIsGroupPolicyEnforced` at `0x1800274b1`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800274f9`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800274f9`
- `FirewallAPI!FWGetConfig` at `0x180027542`
- `FirewallAPI!FWGetConfig` at `0x180027596`
- `FirewallAPI!FWGetConfig` at `0x180027542`
- `FirewallAPI!FWGetConfig` at `0x180027596`

## string_xrefs

- `0x1800275da`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

## pseudocode

```c
bool __fastcall CheckUserPrefMergeForProfileType(unsigned int a1)
{
  int IsGroupPolicyEnforced; // eax
  unsigned int v3; // eax
  unsigned int v4; // r8d
  unsigned int v5; // eax
  unsigned int v6; // r8d
  unsigned int v8; // eax
  unsigned int v9; // r8d
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v12; // [rsp+58h] [rbp+10h] BYREF
  int v13; // [rsp+60h] [rbp+18h] BYREF
  int v14; // [rsp+68h] [rbp+20h]

  v13 = 0;
  IsGroupPolicyEnforced = FwIsGroupPolicyEnforced(0, a1, &v13);
  if ( IsGroupPolicyEnforced < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5B,
      (int)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
      (const char *)(unsigned int)IsGroupPolicyEnforced,
      v10);
  if ( !v13 )
    return 1;
  v3 = FWOpenPolicyStore(545, 0, 5, 1);
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x66, v4, (const char *)v3, 0);
  v12 = 0;
  v14 = 4;
  v5 = FWGetConfig(0, 11, a1);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x72, v6, (const char *)v5, (unsigned int)&v12);
  if ( !v12 )
    return 0;
  v8 = FWGetConfig(0, 13, a1);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x80, v9, (const char *)v8, (unsigned int)&v12);
  return v12 != 0;
}

```

## disassembly

```asm
0x180027498  push    rbx
0x18002749a  sub     rsp, 40h
0x18002749e  mov     ebx, ecx
0x1800274a0  mov     [rsp+48h+arg_10], 0
0x1800274a8  lea     r8, [rsp+48h+arg_10]
0x1800274ad  mov     edx, ecx
0x1800274af  xor     ecx, ecx
0x1800274b1  call    cs:__imp_FwIsGroupPolicyEnforced
0x1800274b7  mov     rcx, [rsp+48h]; this
0x1800274bc  test    eax, eax
0x1800274be  js      loc_1800275D7
0x1800274c4  cmp     [rsp+48h+arg_10], 0
0x1800274c9  jz      loc_1800275CB
0x1800274cf  mov     [rsp+48h+var_18], 0
0x1800274d8  mov     ecx, 221h
0x1800274dd  lea     rax, [rsp+48h+var_18]
0x1800274e2  mov     [rsp+48h+var_20], rax
0x1800274e7  mov     [rsp+48h+var_28], 0; unsigned int
0x1800274ef  xor     edx, edx
0x1800274f1  lea     r9d, [rdx+1]
0x1800274f5  lea     r8d, [rdx+5]
0x1800274f9  call    cs:__imp_FWOpenPolicyStore
0x1800274ff  mov     rcx, [rsp+48h]; this
0x180027504  test    eax, eax
0x180027506  jnz     loc_1800275EC
0x18002750c  mov     [rsp+48h+arg_8], 0
0x180027514  mov     [rsp+48h+arg_18], 4
0x18002751c  lea     rax, [rsp+48h+arg_18]
0x180027521  mov     [rsp+48h+var_20], rax
0x180027526  lea     rax, [rsp+48h+arg_8]
0x18002752b  mov     qword ptr [rsp+48h+var_28], rax; unsigned int
0x180027530  mov     r9d, 1
0x180027536  mov     r8d, ebx
0x180027539  lea     edx, [r9+0Ah]
0x18002753d  mov     rcx, [rsp+48h+var_18]
0x180027542  call    cs:__imp_FWGetConfig
0x180027548  mov     rcx, [rsp+48h]; this
0x18002754d  test    eax, eax
0x18002754f  jnz     loc_1800275F9
0x180027555  cmp     [rsp+48h+arg_8], 0
0x18002755a  jnz     short loc_180027570
0x18002755c  mov     rcx, [rsp+48h+var_18]
0x180027561  test    rcx, rcx
0x180027564  jz      short loc_18002756C
0x180027566  call    cs:__imp_FWClosePolicyStore
0x18002756c  xor     al, al
0x18002756e  jmp     short loc_1800275D1
0x180027570  lea     rax, [rsp+48h+arg_18]
0x180027575  mov     [rsp+48h+var_20], rax
0x18002757a  lea     rax, [rsp+48h+arg_8]
0x18002757f  mov     qword ptr [rsp+48h+var_28], rax; unsigned int
0x180027584  mov     r9d, 1
0x18002758a  mov     r8d, ebx
0x18002758d  lea     edx, [r9+0Ch]
0x180027591  mov     rcx, [rsp+48h+var_18]
0x180027596  call    cs:__imp_FWGetConfig
0x18002759c  mov     rcx, [rsp+48h]; this
0x1800275a1  test    eax, eax
0x1800275a3  jnz     short loc_180027606
0x1800275a5  mov     rcx, [rsp+48h+var_18]
0x1800275aa  cmp     [rsp+48h+arg_8], 0
0x1800275af  jnz     short loc_1800275C0
0x1800275b1  test    rcx, rcx
0x1800275b4  jz      short loc_1800275BC
0x1800275b6  call    cs:__imp_FWClosePolicyStore
0x1800275bc  xor     al, al
0x1800275be  jmp     short loc_1800275D1
0x1800275c0  test    rcx, rcx
0x1800275c3  jz      short loc_1800275CB
0x1800275c5  call    cs:__imp_FWClosePolicyStore
0x1800275cb  mov     al, 1
0x1800275cd  jmp     short loc_1800275D1
0x1800275cf  xor     al, al
0x1800275d1  add     rsp, 40h
0x1800275d5  pop     rbx
0x1800275d6  retn
0x1800275d7  mov     r9d, eax; char *
0x1800275da  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x1800275e1  mov     edx, 5Bh ; '['; void *
0x1800275e6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800275ec  mov     r9d, eax; char *
0x1800275ef  mov     edx, 66h ; 'f'; void *
0x1800275f4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800275f9  mov     r9d, eax; char *
0x1800275fc  mov     edx, 72h ; 'r'; void *
0x180027601  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180027606  mov     r9d, eax; char *
0x180027609  mov     edx, 80h; void *
0x18002760e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
