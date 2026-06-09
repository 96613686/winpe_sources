# Kerb3961::_dynamic_initializer_for__g_keyUsageMap__

- ea: `0x180001170`
- end: `0x1800012b5`
- name: `Kerb3961::_dynamic_initializer_for__g_keyUsageMap__`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001170`
- `0x180003a38`
- `0x18000a80c`
- `0x18000a96c`
- `0x180011ab8`
- `0x180011d64`

## string_xrefs

- `0x1800012a8`: `Allocation failure during initialization`
- `0x18000127b`: `m_components.emplace_back(utl::move(buffer))`

## pseudocode

```c
int __fastcall Kerb3961::_dynamic_initializer_for__g_keyUsageMap__(int a1, const struct std::nothrow_t *a2)
{
  const char *v2; // rdi
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  __int64 v6; // rcx
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF
  char v9; // [rsp+40h] [rbp-18h] BYREF
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  qword_18001A330 = 0;
  qword_18001A320 = (__int64)&Kerb3961::g_keyUsageMap;
  v2 = (const char *)&Kerb3961::KeyUsageMap::c_keyUsageData;
  qword_18001A328 = (__int64)&Kerb3961::g_keyUsageMap;
  do
  {
    if ( (_UNKNOWN *)qword_18001A328 == &Kerb3961::g_keyUsageMap )
    {
      v3 = operator new[](0x28u, a2);
      v4 = v3;
      if ( !v3 )
        goto LABEL_11;
      v3[3] = *(_QWORD *)v2;
      *((_DWORD *)v3 + 8) = *((_DWORD *)v2 + 2);
      *((_BYTE *)v3 + 36) = v2[12];
      *v3 = (char *)&Kerb3961::g_keyUsageMap + 1;
      v3[1] = &utl::_TreeSentinel;
      v3[2] = &utl::_TreeSentinel;
      ++qword_18001A330;
      Kerb3961::g_keyUsageMap = v3;
      qword_18001A320 = (__int64)v3;
      qword_18001A328 = (__int64)v3;
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
      v5 = operator new[](0x28u, a2);
      v4 = v5;
      if ( !v5 )
        goto LABEL_11;
      v5[3] = *(_QWORD *)v2;
      *((_DWORD *)v5 + 8) = *((_DWORD *)v2 + 2);
      *((_BYTE *)v5 + 36) = v2[12];
      utl::_Tree<enum Kerb3961::KeyUsage const,utl::pair<enum Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>,utl::less<enum Kerb3961::KeyUsage const>,utl::allocator<utl::pair<enum Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>>,0>::_InsertAt(
        v6,
        &v8,
        v5);
    }
    if ( !v4 )
LABEL_11:
      Kerb3961::ConsistencyFail((Kerb3961 *)L"Allocation failure during initialization", (const unsigned __int16 *)a2);
LABEL_9:
    v2 += 16;
  }
  while ( v2 != "m_components.emplace_back(utl::move(buffer))" );
  return atexit(Kerb3961::_dynamic_atexit_destructor_for__g_keyUsageMap__);
}

```

## disassembly

```asm
0x180001170  mov     [rsp+arg_8], rbx
0x180001175  mov     [rsp+arg_10], rsi
0x18000117a  push    rdi
0x18000117b  sub     rsp, 50h
0x18000117f  lea     rsi, ?g_keyUsageMap@Kerb3961@@3UKeyUsageMap@1@A; Kerb3961::KeyUsageMap Kerb3961::g_keyUsageMap
0x180001186  mov     cs:qword_18001A330, 0
0x180001191  mov     cs:qword_18001A320, rsi
0x180001198  lea     rdi, ?c_keyUsageData@KeyUsageMap@Kerb3961@@2QBU?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@B; utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const> const near * const Kerb3961::KeyUsageMap::c_keyUsageData
0x18000119f  mov     cs:qword_18001A328, rsi
0x1800011a6  cmp     cs:qword_18001A328, rsi
0x1800011ad  jnz     short loc_18000120F
0x1800011af  mov     ecx, 28h ; '('; unsigned __int64
0x1800011b4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800011b9  mov     rbx, rax
0x1800011bc  test    rax, rax
0x1800011bf  jz      loc_1800012A8
0x1800011c5  mov     rax, [rdi]
0x1800011c8  mov     [rbx+18h], rax
0x1800011cc  mov     eax, [rdi+8]
0x1800011cf  mov     [rbx+20h], eax
0x1800011d2  mov     al, [rdi+0Ch]
0x1800011d5  mov     [rbx+24h], al
0x1800011d8  mov     rax, rsi
0x1800011db  or      rax, 1
0x1800011df  mov     [rbx], rax
0x1800011e2  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800011e9  mov     [rbx+8], rax
0x1800011ed  mov     [rbx+10h], rax
0x1800011f1  inc     cs:qword_18001A330
0x1800011f8  mov     cs:?g_keyUsageMap@Kerb3961@@3UKeyUsageMap@1@A, rbx; Kerb3961::KeyUsageMap Kerb3961::g_keyUsageMap
0x1800011ff  mov     cs:qword_18001A320, rbx
0x180001206  mov     cs:qword_18001A328, rbx
0x18000120d  jmp     short loc_180001272
0x18000120f  mov     r9, rdi
0x180001212  mov     [rsp+58h+arg_0], 0
0x18000121b  lea     r8, [rsp+58h+arg_0]
0x180001220  mov     [rsp+58h+var_38], rsi
0x180001225  lea     rdx, [rsp+58h+var_18]
0x18000122a  call    ?_FindInsertionPointUnique@?$_Tree@$$CBW4KeyUsage@Kerb3961@@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@U?$less@$$CBW4KeyUsage@Kerb3961@@@4@V?$allocator@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@4@$0A@@utl@@AEAA?AU?$pair@PEAU?$_TreeNode@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@utl@@_N@2@AEAPEAU?$_TreeNode@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@2@AEBW4KeyUsage@Kerb3961@@PEAU42@@Z; utl::_Tree<Kerb3961::KeyUsage const,utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>,utl::less<Kerb3961::KeyUsage const>,utl::allocator<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>>,0>::_FindInsertionPointUnique(utl::_TreeNode<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>> * &,Kerb3961::KeyUsage const &,utl::_TreeNode<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>> *)
0x18000122f  mov     rbx, [rsp+58h+arg_0]
0x180001234  movups  xmm0, xmmword ptr [rax]
0x180001237  movdqu  [rsp+58h+var_28], xmm0
0x18000123d  test    rbx, rbx
0x180001240  jnz     short loc_180001277
0x180001242  lea     ecx, [rbx+28h]; unsigned __int64
0x180001245  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000124a  mov     rbx, rax
0x18000124d  test    rax, rax
0x180001250  jz      short loc_1800012A8
0x180001252  mov     rax, [rdi]
0x180001255  lea     rdx, [rsp+58h+var_28]
0x18000125a  mov     [rbx+18h], rax
0x18000125e  mov     r8, rbx
0x180001261  mov     eax, [rdi+8]
0x180001264  mov     [rbx+20h], eax
0x180001267  mov     al, [rdi+0Ch]
0x18000126a  mov     [rbx+24h], al
0x18000126d  call    ?_InsertAt@?$_Tree@$$CBW4KeyUsage@Kerb3961@@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@U?$less@$$CBW4KeyUsage@Kerb3961@@@4@V?$allocator@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@4@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBW4KeyUsage@Kerb3961@@$$CBUKeyPolicyScenario@2@@utl@@@2@@Z; utl::_Tree<Kerb3961::KeyUsage const,utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>,utl::less<Kerb3961::KeyUsage const>,utl::allocator<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>> *,bool> const &,utl::_TreeNode<utl::pair<Kerb3961::KeyUsage const,Kerb3961::KeyPolicyScenario const>> *)
0x180001272  test    rbx, rbx
0x180001275  jz      short loc_1800012A8
0x180001277  add     rdi, 10h
0x18000127b  lea     rax, aMComponentsEmp; "m_components.emplace_back(utl::move(buf"...
0x180001282  cmp     rdi, rax
0x180001285  jnz     loc_1800011A6
0x18000128b  lea     rcx, Kerb3961___dynamic_atexit_destructor_for__g_keyUsageMap__; void (__cdecl *)()
0x180001292  call    atexit
0x180001297  mov     rbx, [rsp+58h+arg_8]
0x18000129c  mov     rsi, [rsp+58h+arg_10]
0x1800012a1  add     rsp, 50h
0x1800012a5  pop     rdi
0x1800012a6  retn
0x1800012a8  lea     rcx, aAllocationFail; "Allocation failure during initializatio"...
0x1800012af  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
