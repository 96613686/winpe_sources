# PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFilePublisherRule>(Sharp::Util::Xml::CNode const &)

- ea: `0x14000935c`
- end: `0x14000940a`
- name: `??$Deserialize@VCFilePublisherRule@PolicyModel@@@CXmlSerializer@PolicyModel@@KAPEAVCFilePublisherRule@1@AEBVCNode@Xml@Util@Sharp@@@Z`
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
- `0x14000935c`
- `0x140009a1c`
- `0x140009d94`
- `0x140016010`

## pseudocode

```c
PolicyModel::CRule *__fastcall PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFilePublisherRule>(__int64 a1)
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
    *(_QWORD *)v3 = &PolicyModel::CFilePublisherRule::`vftable'{for `PolicyModel::CPolicyElement'};
    *((_QWORD *)v3 + 1) = &PolicyModel::CFilePublisherRule::`vftable'{for `PolicyModel::CXmlSerializer'};
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_66277d6f64ee3c41faa92a6d43bd2707_Traceguids);
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
0x14000935c  mov     [rsp+arg_0], rbx
0x140009361  push    rdi
0x140009362  sub     rsp, 20h
0x140009366  mov     rdi, rcx
0x140009369  mov     ecx, 0B0h; Size
0x14000936e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009373  mov     rbx, rax
0x140009376  mov     [rsp+28h+arg_8], rax
0x14000937b  test    rax, rax
0x14000937e  jz      short loc_1400093CF
0x140009380  mov     rcx, rax; this
0x140009383  call    ??0CRule@PolicyModel@@IEAA@XZ; PolicyModel::CRule::CRule(void)
0x140009388  nop
0x140009389  lea     rax, ??_7CFilePublisherRule@PolicyModel@@6BCPolicyElement@1@@; const PolicyModel::CFilePublisherRule::`vftable'{for `PolicyModel::CPolicyElement'}
0x140009390  mov     [rbx], rax
0x140009393  lea     rax, ??_7CFilePublisherRule@PolicyModel@@6BCXmlSerializer@1@@; const PolicyModel::CFilePublisherRule::`vftable'{for `PolicyModel::CXmlSerializer'}
0x14000939a  mov     [rbx+8], rax
0x14000939e  lea     rax, WPP_GLOBAL_Control
0x1400093a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400093ac  cmp     rcx, rax
0x1400093af  jz      short loc_1400093CD
0x1400093b1  test    byte ptr [rcx+1Ch], 8
0x1400093b5  jz      short loc_1400093CD
0x1400093b7  mov     edx, 0Ah
0x1400093bc  lea     r8, WPP_66277d6f64ee3c41faa92a6d43bd2707_Traceguids
0x1400093c3  mov     rcx, [rcx+10h]
0x1400093c7  call    WPP_SF_
0x1400093cc  nop
0x1400093cd  jmp     short loc_1400093D1
0x1400093cf  xor     ebx, ebx
0x1400093d1  mov     [rsp+28h+arg_8], rbx
0x1400093d6  lea     rcx, [rbx+8]
0x1400093da  mov     rdx, [rcx]
0x1400093dd  mov     rax, [rdx+10h]
0x1400093e1  mov     rdx, rdi
0x1400093e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093e9  mov     [rsp+28h+arg_8], 0
0x1400093f2  lea     rcx, [rsp+28h+arg_8]
0x1400093f7  call    ??1?$CScopedPtr@VCFilePathRule@PolicyModel@@@Util@Sharp@@QEAA@XZ; Sharp::Util::CScopedPtr<PolicyModel::CFilePathRule>::~CScopedPtr<PolicyModel::CFilePathRule>(void)
0x1400093fc  mov     rax, rbx
0x1400093ff  mov     rbx, [rsp+28h+arg_0]
0x140009404  add     rsp, 20h
0x140009408  pop     rdi
0x140009409  retn
```
