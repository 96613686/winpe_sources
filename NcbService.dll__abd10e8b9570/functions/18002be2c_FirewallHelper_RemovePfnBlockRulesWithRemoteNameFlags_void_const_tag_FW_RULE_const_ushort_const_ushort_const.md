# FirewallHelper::RemovePfnBlockRulesWithRemoteNameFlags(void * const &,_tag_FW_RULE const &,ushort const *,ushort const *)

- ea: `0x18002be2c`
- end: `0x18002bf33`
- name: `?RemovePfnBlockRulesWithRemoteNameFlags@FirewallHelper@@YAXAEBQEAXAEBU_tag_FW_RULE@@PEBG2@Z`
- size: `263`
- prototype: `void __fastcall(FirewallHelper *this, void *const *, const struct _tag_FW_RULE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001c640`

## callees

- `0x18001b630`
- `0x18001c3f0`
- `0x18001d0dc`
- `0x18001d8e0`

## import_xrefs

- `FirewallAPI!FWDeleteFirewallRule` at `0x18002bea4`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18002bf07`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18002bea4`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18002bf07`

## pseudocode

```c
void __fastcall FirewallHelper::RemovePfnBlockRulesWithRemoteNameFlags(
        FirewallHelper *this,
        void *const *a2,
        const struct _tag_FW_RULE *a3,
        const unsigned __int16 *a4)
{
  _QWORD *v6; // rdx
  __int64 FirewallRuleId; // rax
  _QWORD *v8; // rdx
  _WORD v9[2]; // [rsp+30h] [rbp-29h] BYREF
  int v10; // [rsp+34h] [rbp-25h] BYREF
  _QWORD v11[3]; // [rsp+38h] [rbp-21h] BYREF
  unsigned __int64 v12; // [rsp+50h] [rbp-9h]
  _BYTE Src[32]; // [rsp+58h] [rbp-1h] BYREF

  v9[0] = 16;
  v10 = *((_DWORD *)a2 + 66);
  FirewallHelper::GenerateFirewallRuleId(v11, (__int64)&v10, (__int64)v9);
  v6 = v11;
  if ( v12 > 7 )
    v6 = (_QWORD *)v11[0];
  FWDeleteFirewallRule(*(_QWORD *)this, v6);
  v9[0] = 48;
  v10 = *((_DWORD *)a2 + 66);
  FirewallRuleId = FirewallHelper::GenerateFirewallRuleId(Src, (__int64)&v10, (__int64)v9);
  std::wstring::operator=(v11, FirewallRuleId);
  std::wstring::_Tidy_deallocate(Src);
  v8 = v11;
  if ( v12 > 7 )
    v8 = (_QWORD *)v11[0];
  FWDeleteFirewallRule(*(_QWORD *)this, v8);
  std::wstring::_Tidy_deallocate(v11);
}

```

## disassembly

```asm
0x18002be2c  push    rbp
0x18002be2e  push    rbx
0x18002be2f  push    rsi
0x18002be30  push    rdi
0x18002be31  push    r14
0x18002be33  push    r15
0x18002be35  lea     rbp, [rsp-2Fh]
0x18002be3a  sub     rsp, 88h
0x18002be41  mov     rax, cs:__security_cookie
0x18002be48  xor     rax, rsp
0x18002be4b  mov     [rbp+57h+var_38], rax
0x18002be4f  mov     r14, r9
0x18002be52  mov     rsi, r8
0x18002be55  mov     rdi, rdx
0x18002be58  mov     r15, rcx
0x18002be5b  mov     eax, 10h
0x18002be60  mov     word ptr [rbp+57h+var_80], ax
0x18002be64  mov     eax, [rdx+108h]
0x18002be6a  mov     dword ptr [rbp+57h+var_80+4], eax
0x18002be6d  lea     rax, [rbp+57h+var_80]
0x18002be71  mov     [rsp+0B0h+var_88], rax; __int64
0x18002be76  lea     rax, [rbp+57h+var_80+4]
0x18002be7a  mov     [rsp+0B0h+var_90], rax; __int64
0x18002be7f  lea     r9, [rdx+2Ch]
0x18002be83  mov     r8, r14
0x18002be86  mov     rdx, rsi
0x18002be89  lea     rcx, [rbp+57h+var_78]; Src
0x18002be8d  call    FirewallHelper__GenerateFirewallRuleId
0x18002be92  nop
0x18002be93  lea     rdx, [rbp+57h+var_78]
0x18002be97  cmp     [rbp+57h+var_60], 7
0x18002be9c  cmova   rdx, [rbp+57h+var_78]
0x18002bea1  mov     rcx, [r15]
0x18002bea4  call    cs:__imp_FWDeleteFirewallRule
0x18002beaa  mov     eax, 30h ; '0'
0x18002beaf  mov     word ptr [rbp+57h+var_80], ax
0x18002beb3  mov     eax, [rdi+108h]
0x18002beb9  mov     dword ptr [rbp+57h+var_80+4], eax
0x18002bebc  lea     rax, [rbp+57h+var_80]
0x18002bec0  mov     [rsp+0B0h+var_88], rax; __int64
0x18002bec5  lea     rax, [rbp+57h+var_80+4]
0x18002bec9  mov     [rsp+0B0h+var_90], rax; __int64
0x18002bece  lea     r9, [rdi+2Ch]
0x18002bed2  mov     r8, r14
0x18002bed5  mov     rdx, rsi
0x18002bed8  lea     rcx, [rbp+57h+Src]; Src
0x18002bedc  call    FirewallHelper__GenerateFirewallRuleId
0x18002bee1  mov     rdx, rax
0x18002bee4  lea     rcx, [rbp+57h+var_78]
0x18002bee8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002beed  lea     rcx, [rbp+57h+Src]
0x18002bef1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bef6  lea     rdx, [rbp+57h+var_78]
0x18002befa  cmp     [rbp+57h+var_60], 7
0x18002beff  cmova   rdx, [rbp+57h+var_78]
0x18002bf04  mov     rcx, [r15]
0x18002bf07  call    cs:__imp_FWDeleteFirewallRule
0x18002bf0d  nop
0x18002bf0e  lea     rcx, [rbp+57h+var_78]
0x18002bf12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bf17  mov     rcx, [rbp+57h+var_38]
0x18002bf1b  xor     rcx, rsp; StackCookie
0x18002bf1e  call    __security_check_cookie
0x18002bf23  add     rsp, 88h
0x18002bf2a  pop     r15
0x18002bf2c  pop     r14
0x18002bf2e  pop     rdi
0x18002bf2f  pop     rsi
0x18002bf30  pop     rbx
0x18002bf31  pop     rbp
0x18002bf32  retn
```
