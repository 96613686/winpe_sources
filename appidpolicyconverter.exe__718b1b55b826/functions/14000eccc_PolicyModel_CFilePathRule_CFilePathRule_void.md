# PolicyModel::CFilePathRule::~CFilePathRule(void)

- ea: `0x14000eccc`
- end: `0x14000ed2a`
- name: `??1CFilePathRule@PolicyModel@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(PolicyModel::CFilePathRule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000ed40`

## callees

- `0x1400070e4`
- `0x140009efc`
- `0x14000eccc`

## pseudocode

```c
void __fastcall PolicyModel::CFilePathRule::~CFilePathRule(PolicyModel::CFilePathRule *this)
{
  *(_QWORD *)this = &PolicyModel::CFilePathRule::`vftable'{for `PolicyModel::CPolicyElement'};
  *((_QWORD *)this + 1) = &PolicyModel::CFilePathRule::`vftable'{for `PolicyModel::CXmlSerializer'};
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_89908cc3bea939df4386eaafc9a39ab3_Traceguids);
  PolicyModel::CRule::~CRule(this);
}

```

## disassembly

```asm
0x14000eccc  mov     [rsp+arg_0], rcx
0x14000ecd1  push    rbx
0x14000ecd2  sub     rsp, 20h
0x14000ecd6  mov     rbx, rcx
0x14000ecd9  lea     rax, ??_7CFilePathRule@PolicyModel@@6BCPolicyElement@1@@; const PolicyModel::CFilePathRule::`vftable'{for `PolicyModel::CPolicyElement'}
0x14000ece0  mov     [rcx], rax
0x14000ece3  lea     rax, ??_7CFilePathRule@PolicyModel@@6BCXmlSerializer@1@@; const PolicyModel::CFilePathRule::`vftable'{for `PolicyModel::CXmlSerializer'}
0x14000ecea  mov     [rcx+8], rax
0x14000ecee  lea     rax, WPP_GLOBAL_Control
0x14000ecf5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ecfc  cmp     rcx, rax
0x14000ecff  jz      short loc_14000ED1D
0x14000ed01  test    byte ptr [rcx+1Ch], 8
0x14000ed05  jz      short loc_14000ED1D
0x14000ed07  mov     edx, 0Ch
0x14000ed0c  lea     r8, WPP_89908cc3bea939df4386eaafc9a39ab3_Traceguids
0x14000ed13  mov     rcx, [rcx+10h]
0x14000ed17  call    WPP_SF_
0x14000ed1c  nop
0x14000ed1d  mov     rcx, rbx; this
0x14000ed20  add     rsp, 20h
0x14000ed24  pop     rbx
0x14000ed25  jmp     ??1CRule@PolicyModel@@UEAA@XZ; PolicyModel::CRule::~CRule(void)
```
