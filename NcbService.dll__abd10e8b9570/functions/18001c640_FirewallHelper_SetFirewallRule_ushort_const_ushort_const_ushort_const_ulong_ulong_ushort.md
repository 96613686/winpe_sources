# FirewallHelper::SetFirewallRule(ushort const *,ushort const *,ushort const *,ulong,ulong,ushort)

- ea: `0x18001c640`
- end: `0x18001c8fc`
- name: `?SetFirewallRule@FirewallHelper@@YAKPEBG00KKG@Z`
- size: `700`
- prototype: `__int64 __fastcall(FirewallHelper *this, struct _tag_FW_RULE *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001c5a0`

## callees

- `0x180014e40`
- `0x18001b630`
- `0x18001c080`
- `0x18001c640`
- `0x18001d0dc`
- `0x18001d8e0`
- `0x18001e368`
- `0x18002be2c`

## import_xrefs

- `FirewallAPI!FWAddFirewallRule` at `0x18001c864`
- `FirewallAPI!FWAddFirewallRule` at `0x18001c864`
- `FirewallAPI!FWOpenPolicyStore` at `0x18001c697`
- `FirewallAPI!FWOpenPolicyStore` at `0x18001c697`
- `FirewallAPI!FWSetFirewallRule` at `0x18001c7ff`
- `FirewallAPI!FWSetFirewallRule` at `0x18001c7ff`
- `FirewallAPI!FWFreeFirewallRules` at `0x18001c82a`
- `FirewallAPI!FWFreeFirewallRules` at `0x18001c852`
- `FirewallAPI!FWFreeFirewallRules` at `0x18001c82a`
- `FirewallAPI!FWFreeFirewallRules` at `0x18001c852`
- `FirewallAPI!FWClosePolicyStore` at `0x18001c842`
- `FirewallAPI!FWClosePolicyStore` at `0x18001c89d`
- `FirewallAPI!FWClosePolicyStore` at `0x18001c8ce`
- `FirewallAPI!FWClosePolicyStore` at `0x18001c842`
- `FirewallAPI!FWClosePolicyStore` at `0x18001c89d`
- `FirewallAPI!FWClosePolicyStore` at `0x18001c8ce`

## pseudocode

```c
__int64 __fastcall FirewallHelper::SetFirewallRule(
        FirewallHelper *this,
        struct _tag_FW_RULE *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        __int16 a6)
{
  int v6; // edi
  unsigned int v10; // eax
  FirewallHelper *v12; // rbx
  const unsigned __int16 *v13; // r8
  _QWORD *v14; // rdx
  struct _tag_FW_RULE *RuleById; // rax
  struct _tag_FW_RULE *v16; // rsi
  unsigned int v17; // eax
  unsigned int v18; // edi
  unsigned int v19; // eax
  unsigned int v20; // edi
  unsigned __int16 v21[4]; // [rsp+30h] [rbp-278h] BYREF
  FirewallHelper *v22[2]; // [rsp+38h] [rbp-270h] BYREF
  char v23; // [rsp+48h] [rbp-260h]
  void *v24; // [rsp+50h] [rbp-258h] BYREF
  __int16 v25; // [rsp+58h] [rbp-250h]
  _QWORD *v26; // [rsp+60h] [rbp-248h]
  _QWORD *v27; // [rsp+68h] [rbp-240h]
  _QWORD *v28; // [rsp+70h] [rbp-238h]
  int v29; // [rsp+78h] [rbp-230h]
  int v30; // [rsp+7Ch] [rbp-22Ch]
  __int16 v31; // [rsp+80h] [rbp-228h]
  unsigned int v32; // [rsp+158h] [rbp-150h]
  int v33; // [rsp+170h] [rbp-138h]
  __int16 v34; // [rsp+174h] [rbp-134h]
  const unsigned __int16 *v35; // [rsp+188h] [rbp-120h]
  int v36; // [rsp+1A0h] [rbp-108h]
  FirewallHelper *v37; // [rsp+1D0h] [rbp-D8h]
  struct _tag_FW_RULE *v38; // [rsp+240h] [rbp-68h]
  _QWORD Src[4]; // [rsp+250h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v6 = (int)a4;
  v22[0] = 0;
  v10 = FWOpenPolicyStore(545, 0, 8, 2);
  if ( v10 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x9D,
             (int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
             (const char *)v10);
  v12 = v22[0];
  v22[1] = v22[0];
  v23 = 1;
  memset_0(&v24, 0, 0x1F8u);
  v33 = 2;
  v30 = v6;
  v32 = a5;
  v29 = 0x7FFFFFFF;
  v36 = 0x10000;
  v34 = a6;
  v31 = 256;
  v25 = 545;
  v35 = a3;
  v37 = this;
  v38 = a2;
  *(_DWORD *)v21 = a5;
  FirewallHelper::GenerateFirewallRuleId(Src, (__int64)v21, 0);
  if ( Src[3] > 7u )
  {
    v14 = (_QWORD *)Src[0];
    v27 = (_QWORD *)Src[0];
    v28 = (_QWORD *)Src[0];
    v26 = (_QWORD *)Src[0];
  }
  else
  {
    v27 = Src;
    v28 = Src;
    v26 = Src;
    v14 = Src;
  }
  RuleById = FirewallHelper::FindRuleById(v22[0], v14, v13);
  v16 = RuleById;
  if ( RuleById )
  {
    if ( *((_WORD *)RuleById + 146) != a6 )
    {
      *((_WORD *)RuleById + 146) = a6;
      v17 = FWSetFirewallRule(v22[0], RuleById);
      if ( v17 )
      {
        v18 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xCA,
                (int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
                (const char *)v17);
        FWFreeFirewallRules(v16);
        std::wstring::_Tidy_deallocate(Src);
        FWClosePolicyStore(v12);
        return v18;
      }
    }
    FWFreeFirewallRules(v16);
  }
  else
  {
    v19 = FWAddFirewallRule(v22[0], &v24);
    if ( v19 )
    {
      v20 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xD1,
              (int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
              (const char *)v19);
      std::wstring::_Tidy_deallocate(Src);
      FWClosePolicyStore(v12);
      return v20;
    }
  }
  FirewallHelper::RemovePfnBlockRulesWithRemoteNameFlags(
    (FirewallHelper *)v22,
    &v24,
    a2,
    (const unsigned __int16 *)this);
  std::wstring::_Tidy_deallocate(Src);
  FWClosePolicyStore(v12);
  return 0;
}

```

## disassembly

```asm
0x18001c640  push    rbx
0x18001c642  push    rsi
0x18001c643  push    rdi
0x18001c644  push    r14
0x18001c646  push    r15
0x18001c648  sub     rsp, 280h
0x18001c64f  mov     rax, cs:__security_cookie
0x18001c656  xor     rax, rsp
0x18001c659  mov     [rsp+2A8h+var_38], rax
0x18001c661  mov     edi, r9d
0x18001c664  mov     rsi, r8
0x18001c667  mov     r15, rdx
0x18001c66a  mov     r14, rcx
0x18001c66d  mov     [rsp+2A8h+var_270], 0
0x18001c676  mov     ecx, 221h
0x18001c67b  lea     rax, [rsp+2A8h+var_270]
0x18001c680  mov     [rsp+2A8h+var_280], rax
0x18001c685  mov     dword ptr [rsp+2A8h+var_288], 0; unsigned int
0x18001c68d  xor     edx, edx
0x18001c68f  lea     r9d, [rdx+2]
0x18001c693  lea     r8d, [rdx+8]
0x18001c697  call    cs:__imp_FWOpenPolicyStore
0x18001c69d  test    eax, eax
0x18001c69f  jz      short loc_18001C6C2
0x18001c6a1  mov     rcx, [rsp+2A8h]; this
0x18001c6a9  mov     r9d, eax; char *
0x18001c6ac  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18001c6b3  mov     edx, 9Dh; void *
0x18001c6b8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c6bd  jmp     loc_18001C8DC
0x18001c6c2  mov     rbx, [rsp+2A8h+var_270]
0x18001c6c7  mov     [rsp+2A8h+var_268], rbx
0x18001c6cc  mov     [rsp+2A8h+var_260], 1
0x18001c6d1  xor     edx, edx; Val
0x18001c6d3  mov     r8d, 1F8h; Size
0x18001c6d9  lea     rcx, [rsp+2A8h+var_258]; void *
0x18001c6de  call    memset_0
0x18001c6e3  mov     [rsp+2A8h+var_138], 2
0x18001c6ee  mov     [rsp+2A8h+var_22C], edi
0x18001c6f2  mov     eax, [rsp+2A8h+arg_20]
0x18001c6f9  mov     [rsp+2A8h+var_150], eax
0x18001c700  mov     [rsp+2A8h+var_230], 7FFFFFFFh
0x18001c708  mov     [rsp+2A8h+var_108], 10000h
0x18001c713  movzx   edi, word ptr [rsp+2A8h+arg_28]
0x18001c71b  mov     [rsp+2A8h+var_134], di
0x18001c723  mov     ecx, 100h
0x18001c728  mov     [rsp+2A8h+var_228], cx
0x18001c730  mov     ecx, 221h
0x18001c735  mov     [rsp+2A8h+var_250], cx
0x18001c73a  mov     [rsp+2A8h+var_120], rsi
0x18001c742  mov     [rsp+2A8h+var_D8], r14
0x18001c74a  mov     [rsp+2A8h+var_68], r15
0x18001c752  mov     dword ptr [rsp+2A8h+var_278], eax
0x18001c756  mov     [rsp+2A8h+var_280], 0; __int64
0x18001c75f  lea     rax, [rsp+2A8h+var_278]
0x18001c764  mov     [rsp+2A8h+var_288], rax; unsigned __int16 *
0x18001c769  lea     r9, [rsp+2A8h+var_22C]
0x18001c76e  mov     r8, r14
0x18001c771  mov     rdx, r15
0x18001c774  lea     rcx, [rsp+2A8h+Src]; Src
0x18001c77c  call    FirewallHelper__GenerateFirewallRuleId
0x18001c781  nop
0x18001c782  cmp     [rsp+2A8h+var_40], 7
0x18001c78b  ja      short loc_18001C7BE
0x18001c78d  lea     rax, [rsp+2A8h+Src]
0x18001c795  mov     [rsp+2A8h+var_240], rax
0x18001c79a  lea     rax, [rsp+2A8h+Src]
0x18001c7a2  mov     [rsp+2A8h+var_238], rax
0x18001c7a7  lea     rax, [rsp+2A8h+Src]
0x18001c7af  mov     [rsp+2A8h+var_248], rax
0x18001c7b4  lea     rdx, [rsp+2A8h+Src]
0x18001c7bc  jmp     short loc_18001C7D5
0x18001c7be  mov     rdx, [rsp+2A8h+Src]; void *
0x18001c7c6  mov     [rsp+2A8h+var_240], rdx
0x18001c7cb  mov     [rsp+2A8h+var_238], rdx
0x18001c7d0  mov     [rsp+2A8h+var_248], rdx
0x18001c7d5  mov     rcx, [rsp+2A8h+var_270]; this
0x18001c7da  call    ?FindRuleById@FirewallHelper@@YAPEAU_tag_FW_RULE@@PEAXPEBG@Z; FirewallHelper::FindRuleById(void *,ushort const *)
0x18001c7df  mov     rsi, rax
0x18001c7e2  test    rax, rax
0x18001c7e5  jz      short loc_18001C85A
0x18001c7e7  cmp     [rax+124h], di
0x18001c7ee  jz      short loc_18001C84F
0x18001c7f0  mov     [rax+124h], di
0x18001c7f7  mov     rdx, rax
0x18001c7fa  mov     rcx, [rsp+2A8h+var_270]
0x18001c7ff  call    cs:__imp_FWSetFirewallRule
0x18001c805  test    eax, eax
0x18001c807  jz      short loc_18001C84F
0x18001c809  mov     rcx, [rsp+2A8h]; this
0x18001c811  mov     r9d, eax; char *
0x18001c814  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18001c81b  mov     edx, 0CAh; void *
0x18001c820  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c825  mov     edi, eax
0x18001c827  mov     rcx, rsi
0x18001c82a  call    cs:__imp_FWFreeFirewallRules
0x18001c830  nop
0x18001c831  lea     rcx, [rsp+2A8h+Src]
0x18001c839  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c83e  nop
0x18001c83f  mov     rcx, rbx
0x18001c842  call    cs:__imp_FWClosePolicyStore
0x18001c848  mov     eax, edi
0x18001c84a  jmp     loc_18001C8DC
0x18001c84f  mov     rcx, rsi
0x18001c852  call    cs:__imp_FWFreeFirewallRules
0x18001c858  jmp     short loc_18001C8A7
0x18001c85a  lea     rdx, [rsp+2A8h+var_258]
0x18001c85f  mov     rcx, [rsp+2A8h+var_270]
0x18001c864  call    cs:__imp_FWAddFirewallRule
0x18001c86a  test    eax, eax
0x18001c86c  jz      short loc_18001C8A7
0x18001c86e  mov     rcx, [rsp+2A8h]; this
0x18001c876  mov     r9d, eax; char *
0x18001c879  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18001c880  mov     edx, 0D1h; void *
0x18001c885  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c88a  mov     edi, eax
0x18001c88c  lea     rcx, [rsp+2A8h+Src]
0x18001c894  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c899  nop
0x18001c89a  mov     rcx, rbx
0x18001c89d  call    cs:__imp_FWClosePolicyStore
0x18001c8a3  mov     eax, edi
0x18001c8a5  jmp     short loc_18001C8DC
0x18001c8a7  mov     r9, r14; unsigned __int16 *
0x18001c8aa  mov     r8, r15; struct _tag_FW_RULE *
0x18001c8ad  lea     rdx, [rsp+2A8h+var_258]; void **
0x18001c8b2  lea     rcx, [rsp+2A8h+var_270]; this
0x18001c8b7  call    ?RemovePfnBlockRulesWithRemoteNameFlags@FirewallHelper@@YAXAEBQEAXAEBU_tag_FW_RULE@@PEBG2@Z; FirewallHelper::RemovePfnBlockRulesWithRemoteNameFlags(void * const &,_tag_FW_RULE const &,ushort const *,ushort const *)
0x18001c8bc  nop
0x18001c8bd  lea     rcx, [rsp+2A8h+Src]
0x18001c8c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c8ca  nop
0x18001c8cb  mov     rcx, rbx
0x18001c8ce  call    cs:__imp_FWClosePolicyStore
0x18001c8d4  xor     eax, eax
0x18001c8d6  jmp     short loc_18001C8DC
0x18001c8d8  mov     eax, dword ptr [rsp+2A8h+var_278]
0x18001c8dc  mov     rcx, [rsp+2A8h+var_38]
0x18001c8e4  xor     rcx, rsp; StackCookie
0x18001c8e7  call    __security_check_cookie
0x18001c8ec  add     rsp, 280h
0x18001c8f3  pop     r15
0x18001c8f5  pop     r14
0x18001c8f7  pop     rdi
0x18001c8f8  pop     rsi
0x18001c8f9  pop     rbx
0x18001c8fa  retn
```
