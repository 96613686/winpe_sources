# PolicyModel::CFilePathCondition::CFilePathCondition(PolicyModel::CFilePath const &)

- ea: `0x14000d6f4`
- end: `0x14000d7a2`
- name: `??0CFilePathCondition@PolicyModel@@QEAA@AEBVCFilePath@1@@Z`
- size: `174`
- prototype: `PolicyModel::CFilePathCondition *__fastcall(PolicyModel::CFilePathCondition *this, const struct PolicyModel::CFilePath *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140009520`

## callees

- `0x1400070e4`
- `0x14000997c`
- `0x14000d6f4`
- `0x14000f810`

## pseudocode

```c
PolicyModel::CFilePathCondition *__fastcall PolicyModel::CFilePathCondition::CFilePathCondition(
        PolicyModel::CFilePathCondition *this,
        const struct PolicyModel::CFilePath *a2)
{
  PolicyModel::CRuleCondition::CRuleCondition(this);
  *(_QWORD *)this = &PolicyModel::CFilePathCondition::`vftable'{for `PolicyModel::CPolicyElement'};
  *((_QWORD *)this + 1) = &PolicyModel::CFilePathCondition::`vftable'{for `PolicyModel::CXmlSerializer'};
  *((_QWORD *)this + 2) = &PolicyModel::CPolicyElement::`vftable';
  *((_QWORD *)this + 3) = &PolicyModel::CXmlSerializer::`vftable';
  *((_QWORD *)this + 2) = &PolicyModel::CFilePath::`vftable'{for `PolicyModel::CPolicyElement'};
  *((_QWORD *)this + 3) = &PolicyModel::CFilePath::`vftable'{for `PolicyModel::CXmlSerializer'};
  std::wstring::wstring((__int64)this + 32, (__int64)a2 + 16);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids);
  return this;
}

```

## disassembly

```asm
0x14000d6f4  mov     [rsp+arg_10], rbx
0x14000d6f9  mov     [rsp+arg_0], rcx
0x14000d6fe  push    rdi
0x14000d6ff  sub     rsp, 20h
0x14000d703  mov     rbx, rdx
0x14000d706  mov     rdi, rcx
0x14000d709  call    ??0CRuleCondition@PolicyModel@@IEAA@XZ; PolicyModel::CRuleCondition::CRuleCondition(void)
0x14000d70e  nop
0x14000d70f  lea     rax, ??_7CFilePathCondition@PolicyModel@@6BCPolicyElement@1@@; const PolicyModel::CFilePathCondition::`vftable'{for `PolicyModel::CPolicyElement'}
0x14000d716  mov     [rdi], rax
0x14000d719  lea     rax, ??_7CFilePathCondition@PolicyModel@@6BCXmlSerializer@1@@; const PolicyModel::CFilePathCondition::`vftable'{for `PolicyModel::CXmlSerializer'}
0x14000d720  mov     [rdi+8], rax
0x14000d724  lea     rcx, [rdi+10h]
0x14000d728  mov     [rsp+28h+arg_8], rcx
0x14000d72d  lea     rax, ??_7CPolicyElement@PolicyModel@@6B@; const PolicyModel::CPolicyElement::`vftable'
0x14000d734  mov     [rcx], rax
0x14000d737  lea     rax, ??_7CXmlSerializer@PolicyModel@@6B@; const PolicyModel::CXmlSerializer::`vftable'
0x14000d73e  mov     [rcx+8], rax
0x14000d742  lea     rax, ??_7CFilePath@PolicyModel@@6BCPolicyElement@1@@; const PolicyModel::CFilePath::`vftable'{for `PolicyModel::CPolicyElement'}
0x14000d749  mov     [rcx], rax
0x14000d74c  lea     rax, ??_7CFilePath@PolicyModel@@6BCXmlSerializer@1@@; const PolicyModel::CFilePath::`vftable'{for `PolicyModel::CXmlSerializer'}
0x14000d753  mov     [rcx+8], rax
0x14000d757  lea     rdx, [rbx+10h]
0x14000d75b  add     rcx, 10h
0x14000d75f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000d764  nop
0x14000d765  lea     rax, WPP_GLOBAL_Control
0x14000d76c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d773  cmp     rcx, rax
0x14000d776  jz      short loc_14000D794
0x14000d778  test    byte ptr [rcx+1Ch], 8
0x14000d77c  jz      short loc_14000D794
0x14000d77e  mov     edx, 0Ah
0x14000d783  lea     r8, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids
0x14000d78a  mov     rcx, [rcx+10h]
0x14000d78e  call    WPP_SF_
0x14000d793  nop
0x14000d794  mov     rax, rdi
0x14000d797  mov     rbx, [rsp+28h+arg_10]
0x14000d79c  add     rsp, 20h
0x14000d7a0  pop     rdi
0x14000d7a1  retn
```
