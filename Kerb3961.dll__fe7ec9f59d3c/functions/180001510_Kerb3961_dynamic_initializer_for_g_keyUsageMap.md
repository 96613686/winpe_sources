# Kerb3961::_dynamic_initializer_for__g_keyUsageMap__

- ea: `0x180001510`
- end: `0x180001653`
- name: `Kerb3961::_dynamic_initializer_for__g_keyUsageMap__`
- size: `323`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001510`
- `0x1800020fc`
- `0x1800029bc`
- `0x1800033f4`
- `0x18000e988`
- `0x18000eadc`

## string_xrefs

- `0x180001646`: `Allocation failure during initialization`

## pseudocode

```c
int __fastcall Kerb3961::_dynamic_initializer_for__g_keyUsageMap__(int a1, const struct std::nothrow_t *a2)
{
  __int64 *v2; // rdi
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  __int64 v6; // rcx
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF
  char v9; // [rsp+40h] [rbp-18h] BYREF
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  qword_180029280 = 0;
  qword_180029270 = (__int64)&Kerb3961::g_keyUsageMap;
  v2 = Kerb3961::KeyUsageMap::c_keyUsageData;
  qword_180029278 = (__int64)&Kerb3961::g_keyUsageMap;
  do
  {
    if ( (_UNKNOWN *)qword_180029278 == &Kerb3961::g_keyUsageMap )
    {
      v3 = operator new(0x28u, a2);
      v4 = v3;
      if ( !v3 )
        goto LABEL_11;
      v3[3] = *v2;
      *((_DWORD *)v3 + 8) = *((_DWORD *)v2 + 2);
      *((_BYTE *)v3 + 36) = *((_BYTE *)v2 + 12);
      *v3 = (char *)&Kerb3961::g_keyUsageMap + 1;
      v3[1] = &utl::_TreeSentinel;
      v3[2] = &utl::_TreeSentinel;
      ++qword_180029280;
      Kerb3961::g_keyUsageMap = v3;
      qword_180029270 = (__int64)v3;
      qword_180029278 = (__int64)v3;
    }
    else
    {
      v10 = 0;
      v8 = *(_OWORD *)utl::_Tree<enum Kerb3961::KeyUsage const,utl::pair<enum Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>,utl::less<enum Kerb3961::KeyUsage const>,utl::allocator<utl::pair<enum Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>>,0>::_FindInsertionPointUnique(
                        a1,
                        (unsigned int)&v9,
                        (unsigned int)&v10,
                        (_DWORD)v2,
                        (__int64)&Kerb3961::g_keyUsageMap);
      if ( v10 )
        goto LABEL_9;
      v5 = operator new(0x28u, a2);
      v4 = v5;
      if ( !v5 )
        goto LABEL_11;
      v5[3] = *v2;
      *((_DWORD *)v5 + 8) = *((_DWORD *)v2 + 2);
      *((_BYTE *)v5 + 36) = *((_BYTE *)v2 + 12);
      utl::_Tree<enum Kerb3961::KeyUsage const,utl::pair<enum Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>,utl::less<enum Kerb3961::KeyUsage const>,utl::allocator<utl::pair<enum Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>>,0>::_InsertAt(
        v6,
        &v8,
        v5);
    }
    if ( !v4 )
LABEL_11:
      Kerb3961::ConsistencyFail((Kerb3961 *)L"Allocation failure during initialization", (const unsigned __int16 *)a2);
LABEL_9:
    v2 += 2;
  }
  while ( v2 != (__int64 *)"static_cast<size_t>(string.length) <= static_cast<size_t>(unsigned(utl::numeric_limits<int32_t>::max()))" );
  return atexit((void (__cdecl *)())Kerb3961::_dynamic_atexit_destructor_for__g_keyUsageMap__);
}

```

## disassembly

```asm
0x180001510  mov     [rsp+arg_8], rbx
0x180001515  mov     [rsp+arg_10], rsi
0x18000151a  push    rdi
0x18000151b  sub     rsp, 50h
0x18000151f  lea     rsi, ?g_keyUsageMap@Kerb3961@@3UKeyUsageMap@1@A; Kerb3961::KeyUsageMap Kerb3961::g_keyUsageMap
0x180001526  mov     cs:qword_180029280, 0
0x180001531  mov     cs:qword_180029270, rsi
0x180001538  lea     rdi, ?c_keyUsageData@KeyUsageMap@Kerb3961@@2QBU?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@B; utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const> const near * const Kerb3961::KeyUsageMap::c_keyUsageData
0x18000153f  mov     cs:qword_180029278, rsi
0x180001546  cmp     cs:qword_180029278, rsi
0x18000154d  jnz     short loc_1800015AF
0x18000154f  mov     ecx, 28h ; '('; unsigned __int64
0x180001554  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001559  mov     rbx, rax
0x18000155c  test    rax, rax
0x18000155f  jz      loc_180001646
0x180001565  mov     rax, [rdi]
0x180001568  mov     [rbx+18h], rax
0x18000156c  mov     eax, [rdi+8]
0x18000156f  mov     [rbx+20h], eax
0x180001572  mov     al, [rdi+0Ch]
0x180001575  mov     [rbx+24h], al
0x180001578  mov     rax, rsi
0x18000157b  or      rax, 1
0x18000157f  mov     [rbx], rax
0x180001582  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180001589  mov     [rbx+8], rax
0x18000158d  mov     [rbx+10h], rax
0x180001591  inc     cs:qword_180029280
0x180001598  mov     cs:?g_keyUsageMap@Kerb3961@@3UKeyUsageMap@1@A, rbx; Kerb3961::KeyUsageMap Kerb3961::g_keyUsageMap
0x18000159f  mov     cs:qword_180029270, rbx
0x1800015a6  mov     cs:qword_180029278, rbx
0x1800015ad  jmp     short loc_180001612
0x1800015af  mov     r9, rdi
0x1800015b2  mov     [rsp+58h+arg_0], 0
0x1800015bb  lea     r8, [rsp+58h+arg_0]
0x1800015c0  mov     [rsp+58h+var_38], rsi
0x1800015c5  lea     rdx, [rsp+58h+var_18]
0x1800015ca  call    ?_FindInsertionPointUnique@?$_Tree@$$CBW4KeyUsage@Kerb3961@@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@U?$less@$$CBW4KeyUsage@Kerb3961@@@4@V?$allocator@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@4@$0A@@utl@@AEAA?AU?$pair@PEAU?$_TreeNode@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@utl@@_N@2@AEAPEAU?$_TreeNode@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@2@AEBW4KeyUsage@Kerb3961@@PEAU42@@Z; utl::_Tree<Kerb3961::KeyUsage const,utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>,utl::less<Kerb3961::KeyUsage const>,utl::allocator<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>>,0>::_FindInsertionPointUnique(utl::_TreeNode<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>> * &,Kerb3961::KeyUsage const &,utl::_TreeNode<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>> *)
0x1800015cf  mov     rbx, [rsp+58h+arg_0]
0x1800015d4  movups  xmm0, xmmword ptr [rax]
0x1800015d7  movdqu  [rsp+58h+var_28], xmm0
0x1800015dd  test    rbx, rbx
0x1800015e0  jnz     short loc_180001617
0x1800015e2  lea     ecx, [rbx+28h]; unsigned __int64
0x1800015e5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800015ea  mov     rbx, rax
0x1800015ed  test    rax, rax
0x1800015f0  jz      short loc_180001646
0x1800015f2  mov     rax, [rdi]
0x1800015f5  lea     rdx, [rsp+58h+var_28]
0x1800015fa  mov     [rbx+18h], rax
0x1800015fe  mov     r8, rbx
0x180001601  mov     eax, [rdi+8]
0x180001604  mov     [rbx+20h], eax
0x180001607  mov     al, [rdi+0Ch]
0x18000160a  mov     [rbx+24h], al
0x18000160d  call    ?_InsertAt@?$_Tree@$$CBW4KeyUsage@Kerb3961@@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@U?$less@$$CBW4KeyUsage@Kerb3961@@@4@V?$allocator@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@4@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@2@@Z; utl::_Tree<Kerb3961::KeyUsage const,utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>,utl::less<Kerb3961::KeyUsage const>,utl::allocator<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>> *,bool> const &,utl::_TreeNode<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>> *)
0x180001612  test    rbx, rbx
0x180001615  jz      short loc_180001646
0x180001617  add     rdi, 10h
0x18000161b  lea     rax, aStaticCastSize_5; "static_cast<size_t>(string.length) <= s"...
0x180001622  cmp     rdi, rax
0x180001625  jnz     loc_180001546
0x18000162b  lea     rcx, Kerb3961___dynamic_atexit_destructor_for__g_keyUsageMap__
0x180001632  mov     rbx, [rsp+58h+arg_8]
0x180001637  mov     rsi, [rsp+58h+arg_10]
0x18000163c  add     rsp, 50h
0x180001640  pop     rdi
0x180001641  jmp     atexit
0x180001646  lea     rcx, aAllocationFail; "Allocation failure during initializatio"...
0x18000164d  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
