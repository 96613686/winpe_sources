# PolicyModel::CFilePathCondition::~CFilePathCondition(void)

- ea: `0x14000d7a8`
- end: `0x14000d810`
- name: `??1CFilePathCondition@PolicyModel@@UEAA@XZ`
- size: `104`
- prototype: `void __fastcall(PolicyModel::CFilePathCondition *this, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000d880`

## callees

- `0x1400070e4`
- `0x14000d7a8`
- `0x14000db9c`
- `0x14000f88c`

## pseudocode

```c
void __fastcall PolicyModel::CFilePathCondition::~CFilePathCondition(PolicyModel::CFilePathCondition *this, __int64 a2)
{
  *(_QWORD *)this = &PolicyModel::CFilePathCondition::`vftable'{for `PolicyModel::CPolicyElement'};
  *((_QWORD *)this + 1) = &PolicyModel::CFilePathCondition::`vftable'{for `PolicyModel::CXmlSerializer'};
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids);
  PolicyModel::CFilePath::~CFilePath((PolicyModel::CFilePathCondition *)((char *)this + 16), a2);
  PolicyModel::CRuleCondition::~CRuleCondition(this);
}

```

## disassembly

```asm
0x14000d7a8  mov     [rsp+arg_0], rcx
0x14000d7ad  push    rbx
0x14000d7ae  sub     rsp, 20h
0x14000d7b2  mov     rbx, rcx
0x14000d7b5  lea     rax, ??_7CFilePathCondition@PolicyModel@@6BCPolicyElement@1@@; const PolicyModel::CFilePathCondition::`vftable'{for `PolicyModel::CPolicyElement'}
0x14000d7bc  mov     [rcx], rax
0x14000d7bf  lea     rax, ??_7CFilePathCondition@PolicyModel@@6BCXmlSerializer@1@@; const PolicyModel::CFilePathCondition::`vftable'{for `PolicyModel::CXmlSerializer'}
0x14000d7c6  mov     [rcx+8], rax
0x14000d7ca  lea     rax, WPP_GLOBAL_Control
0x14000d7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d7d8  cmp     rcx, rax
0x14000d7db  jz      short loc_14000D7F9
0x14000d7dd  test    byte ptr [rcx+1Ch], 8
0x14000d7e1  jz      short loc_14000D7F9
0x14000d7e3  mov     edx, 0Bh
0x14000d7e8  lea     r8, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids
0x14000d7ef  mov     rcx, [rcx+10h]
0x14000d7f3  call    WPP_SF_
0x14000d7f8  nop
0x14000d7f9  lea     rcx, [rbx+10h]; this
0x14000d7fd  call    ??1CFilePath@PolicyModel@@UEAA@XZ; PolicyModel::CFilePath::~CFilePath(void)
0x14000d802  nop
0x14000d803  mov     rcx, rbx; this
0x14000d806  add     rsp, 20h
0x14000d80a  pop     rbx
0x14000d80b  jmp     ??1CRuleCondition@PolicyModel@@UEAA@XZ; PolicyModel::CRuleCondition::~CRuleCondition(void)
```
