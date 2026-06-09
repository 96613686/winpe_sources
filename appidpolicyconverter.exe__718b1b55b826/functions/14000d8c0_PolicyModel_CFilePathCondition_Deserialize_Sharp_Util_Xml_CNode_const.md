# PolicyModel::CFilePathCondition::Deserialize(Sharp::Util::Xml::CNode const &)

- ea: `0x14000d8c0`
- end: `0x14000d91b`
- name: `?Deserialize@CFilePathCondition@PolicyModel@@MEAAXAEBVCNode@Xml@Util@Sharp@@@Z`
- size: `91`
- prototype: `void __fastcall(PolicyModel::CFilePathCondition *__hidden this, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x14000d8c0`
- `0x140016010`

## pseudocode

```c
void __fastcall PolicyModel::CFilePathCondition::Deserialize(
        PolicyModel::CFilePathCondition *this,
        const struct Sharp::Util::Xml::CNode *a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids);
  (*(void (__fastcall **)(char *, const struct Sharp::Util::Xml::CNode *))(*((_QWORD *)this + 2) + 16LL))(
    (char *)this + 16,
    a2);
}

```

## disassembly

```asm
0x14000d8c0  mov     [rsp+arg_0], rbx
0x14000d8c5  push    rdi
0x14000d8c6  sub     rsp, 20h
0x14000d8ca  mov     rbx, rdx
0x14000d8cd  mov     rdi, rcx
0x14000d8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d8d7  lea     rax, WPP_GLOBAL_Control
0x14000d8de  cmp     rcx, rax
0x14000d8e1  jz      short loc_14000D8FE
0x14000d8e3  test    byte ptr [rcx+1Ch], 8
0x14000d8e7  jz      short loc_14000D8FE
0x14000d8e9  mov     rcx, [rcx+10h]
0x14000d8ed  lea     r8, WPP_a1a8c93a76de3b7ee012ad1e7d3a4a88_Traceguids
0x14000d8f4  mov     edx, 0Dh
0x14000d8f9  call    WPP_SF_
0x14000d8fe  lea     rcx, [rdi+10h]
0x14000d902  mov     rdx, rbx
0x14000d905  mov     rax, [rcx]
0x14000d908  mov     rax, [rax+10h]
0x14000d90c  mov     rbx, [rsp+28h+arg_0]
0x14000d911  add     rsp, 20h
0x14000d915  pop     rdi
0x14000d916  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
