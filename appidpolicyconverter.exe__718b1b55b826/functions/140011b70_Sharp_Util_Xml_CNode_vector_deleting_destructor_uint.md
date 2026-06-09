# Sharp::Util::Xml::CNode::`vector deleting destructor'(uint)

- ea: `0x140011b70`
- end: `0x140011b9f`
- name: `??_ECNode@Xml@Util@Sharp@@UEAAPEAXI@Z`
- size: `47`
- prototype: `Sharp::Util::Xml::CNode *__fastcall(Sharp::Util::Xml::CNode *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x14000157c`
- `0x140011b70`
- `0x140012138`

## pseudocode

```c
Sharp::Util::Xml::CNode *__fastcall Sharp::Util::Xml::CNode::`vector deleting destructor'(
        Sharp::Util::Xml::CNode *this,
        char a2)
{
  Sharp::Util::Xml::CNode::~CNode(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140011b70  mov     [rsp+arg_0], rbx
0x140011b75  push    rdi
0x140011b76  sub     rsp, 20h
0x140011b7a  mov     ebx, edx
0x140011b7c  mov     rdi, rcx
0x140011b7f  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x140011b84  test    bl, 1
0x140011b87  jz      short loc_140011B91
0x140011b89  mov     rcx, rdi; Block
0x140011b8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011b91  mov     rbx, [rsp+28h+arg_0]
0x140011b96  mov     rax, rdi
0x140011b99  add     rsp, 20h
0x140011b9d  pop     rdi
0x140011b9e  retn
```
