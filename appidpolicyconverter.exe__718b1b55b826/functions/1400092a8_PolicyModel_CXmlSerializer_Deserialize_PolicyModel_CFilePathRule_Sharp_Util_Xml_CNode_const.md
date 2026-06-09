# PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFilePathRule>(Sharp::Util::Xml::CNode const &)

- ea: `0x1400092a8`
- end: `0x140009356`
- name: `??$Deserialize@VCFilePathRule@PolicyModel@@@CXmlSerializer@PolicyModel@@KAPEAVCFilePathRule@1@AEBVCNode@Xml@Util@Sharp@@@Z`
- size: `174`
- prototype: `PolicyModel::CRule *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000a9ac`

## callees

- `0x140001530`
- `0x1400070e4`
- `0x1400092a8`
- `0x140009a1c`
- `0x140009d94`
- `0x140016010`

## pseudocode

```c
PolicyModel::CRule *__fastcall PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFilePathRule>(__int64 a1)
{
  PolicyModel::CRule *v2; // rax
  PolicyModel::CRule *v3; // rbx
  PolicyModel::CRule *v5; // [rsp+38h] [rbp+10h] BYREF

  v2 = (PolicyModel::CRule *)operator new(0xB0u);
  v3 = v2;
  v5 = v2;
  if ( v2 )
  {
    PolicyModel::CRule::CRule(v2);
    *(_QWORD *)v3 = &PolicyModel::CFilePathRule::`vftable'{for `PolicyModel::CPolicyElement'};
    *((_QWORD *)v3 + 1) = &PolicyModel::CFilePathRule::`vftable'{for `PolicyModel::CXmlSerializer'};
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_89908cc3bea939df4386eaafc9a39ab3_Traceguids);
  }
  else
  {
    v3 = 0;
  }
  v5 = v3;
  (*(void (__fastcall **)(_QWORD *, __int64))(*((_QWORD *)v3 + 1) + 16LL))((_QWORD *)v3 + 1, a1);
  v5 = 0;
  Sharp::Util::CScopedPtr<PolicyModel::CFilePathRule>::~CScopedPtr<PolicyModel::CFilePathRule>(&v5);
  return v3;
}

```

## disassembly

```asm
0x1400092a8  mov     [rsp+arg_0], rbx
0x1400092ad  push    rdi
0x1400092ae  sub     rsp, 20h
0x1400092b2  mov     rdi, rcx
0x1400092b5  mov     ecx, 0B0h; Size
0x1400092ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400092bf  mov     rbx, rax
0x1400092c2  mov     [rsp+28h+arg_8], rax
0x1400092c7  test    rax, rax
0x1400092ca  jz      short loc_14000931B
0x1400092cc  mov     rcx, rax; this
0x1400092cf  call    ??0CRule@PolicyModel@@IEAA@XZ; PolicyModel::CRule::CRule(void)
0x1400092d4  nop
0x1400092d5  lea     rax, ??_7CFilePathRule@PolicyModel@@6BCPolicyElement@1@@; const PolicyModel::CFilePathRule::`vftable'{for `PolicyModel::CPolicyElement'}
0x1400092dc  mov     [rbx], rax
0x1400092df  lea     rax, ??_7CFilePathRule@PolicyModel@@6BCXmlSerializer@1@@; const PolicyModel::CFilePathRule::`vftable'{for `PolicyModel::CXmlSerializer'}
0x1400092e6  mov     [rbx+8], rax
0x1400092ea  lea     rax, WPP_GLOBAL_Control
0x1400092f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400092f8  cmp     rcx, rax
0x1400092fb  jz      short loc_140009319
0x1400092fd  test    byte ptr [rcx+1Ch], 8
0x140009301  jz      short loc_140009319
0x140009303  mov     edx, 0Ah
0x140009308  lea     r8, WPP_89908cc3bea939df4386eaafc9a39ab3_Traceguids
0x14000930f  mov     rcx, [rcx+10h]
0x140009313  call    WPP_SF_
0x140009318  nop
0x140009319  jmp     short loc_14000931D
0x14000931b  xor     ebx, ebx
0x14000931d  mov     [rsp+28h+arg_8], rbx
0x140009322  lea     rcx, [rbx+8]
0x140009326  mov     rdx, [rcx]
0x140009329  mov     rax, [rdx+10h]
0x14000932d  mov     rdx, rdi
0x140009330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009335  mov     [rsp+28h+arg_8], 0
0x14000933e  lea     rcx, [rsp+28h+arg_8]
0x140009343  call    ??1?$CScopedPtr@VCFilePathRule@PolicyModel@@@Util@Sharp@@QEAA@XZ; Sharp::Util::CScopedPtr<PolicyModel::CFilePathRule>::~CScopedPtr<PolicyModel::CFilePathRule>(void)
0x140009348  mov     rax, rbx
0x14000934b  mov     rbx, [rsp+28h+arg_0]
0x140009350  add     rsp, 20h
0x140009354  pop     rdi
0x140009355  retn
```
