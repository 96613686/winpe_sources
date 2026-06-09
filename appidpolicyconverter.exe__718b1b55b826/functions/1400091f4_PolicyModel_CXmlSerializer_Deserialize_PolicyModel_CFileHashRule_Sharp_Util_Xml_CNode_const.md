# PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFileHashRule>(Sharp::Util::Xml::CNode const &)

- ea: `0x1400091f4`
- end: `0x1400092a2`
- name: `??$Deserialize@VCFileHashRule@PolicyModel@@@CXmlSerializer@PolicyModel@@KAPEAVCFileHashRule@1@AEBVCNode@Xml@Util@Sharp@@@Z`
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
- `0x1400091f4`
- `0x140009a1c`
- `0x140009d94`
- `0x140016010`

## pseudocode

```c
PolicyModel::CRule *__fastcall PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFileHashRule>(__int64 a1)
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
    *(_QWORD *)v3 = &PolicyModel::CFileHashRule::`vftable'{for `PolicyModel::CPolicyElement'};
    *((_QWORD *)v3 + 1) = &PolicyModel::CFileHashRule::`vftable'{for `PolicyModel::CXmlSerializer'};
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4525850acc9d3991abe82a9f77fe7d31_Traceguids);
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
0x1400091f4  mov     [rsp+arg_0], rbx
0x1400091f9  push    rdi
0x1400091fa  sub     rsp, 20h
0x1400091fe  mov     rdi, rcx
0x140009201  mov     ecx, 0B0h; Size
0x140009206  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000920b  mov     rbx, rax
0x14000920e  mov     [rsp+28h+arg_8], rax
0x140009213  test    rax, rax
0x140009216  jz      short loc_140009267
0x140009218  mov     rcx, rax; this
0x14000921b  call    ??0CRule@PolicyModel@@IEAA@XZ; PolicyModel::CRule::CRule(void)
0x140009220  nop
0x140009221  lea     rax, ??_7CFileHashRule@PolicyModel@@6BCPolicyElement@1@@; const PolicyModel::CFileHashRule::`vftable'{for `PolicyModel::CPolicyElement'}
0x140009228  mov     [rbx], rax
0x14000922b  lea     rax, ??_7CFileHashRule@PolicyModel@@6BCXmlSerializer@1@@; const PolicyModel::CFileHashRule::`vftable'{for `PolicyModel::CXmlSerializer'}
0x140009232  mov     [rbx+8], rax
0x140009236  lea     rax, WPP_GLOBAL_Control
0x14000923d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009244  cmp     rcx, rax
0x140009247  jz      short loc_140009265
0x140009249  test    byte ptr [rcx+1Ch], 8
0x14000924d  jz      short loc_140009265
0x14000924f  mov     edx, 0Ah
0x140009254  lea     r8, WPP_4525850acc9d3991abe82a9f77fe7d31_Traceguids
0x14000925b  mov     rcx, [rcx+10h]
0x14000925f  call    WPP_SF_
0x140009264  nop
0x140009265  jmp     short loc_140009269
0x140009267  xor     ebx, ebx
0x140009269  mov     [rsp+28h+arg_8], rbx
0x14000926e  lea     rcx, [rbx+8]
0x140009272  mov     rdx, [rcx]
0x140009275  mov     rax, [rdx+10h]
0x140009279  mov     rdx, rdi
0x14000927c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009281  mov     [rsp+28h+arg_8], 0
0x14000928a  lea     rcx, [rsp+28h+arg_8]
0x14000928f  call    ??1?$CScopedPtr@VCFilePathRule@PolicyModel@@@Util@Sharp@@QEAA@XZ; Sharp::Util::CScopedPtr<PolicyModel::CFilePathRule>::~CScopedPtr<PolicyModel::CFilePathRule>(void)
0x140009294  mov     rax, rbx
0x140009297  mov     rbx, [rsp+28h+arg_0]
0x14000929c  add     rsp, 20h
0x1400092a0  pop     rdi
0x1400092a1  retn
```
