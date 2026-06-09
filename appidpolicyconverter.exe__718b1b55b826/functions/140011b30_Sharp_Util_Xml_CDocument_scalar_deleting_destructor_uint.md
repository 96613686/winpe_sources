# Sharp::Util::Xml::CDocument::`scalar deleting destructor'(uint)

- ea: `0x140011b30`
- end: `0x140011b5f`
- name: `??_GCDocument@Xml@Util@Sharp@@UEAAPEAXI@Z`
- size: `47`
- prototype: `Sharp::Util::Xml::CDocument *__fastcall(Sharp::Util::Xml::CDocument *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x14000157c`
- `0x140011aa8`
- `0x140011b30`

## pseudocode

```c
Sharp::Util::Xml::CDocument *__fastcall Sharp::Util::Xml::CDocument::`scalar deleting destructor'(
        Sharp::Util::Xml::CDocument *this,
        char a2)
{
  Sharp::Util::Xml::CDocument::~CDocument(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140011b30  mov     [rsp+arg_0], rbx
0x140011b35  push    rdi
0x140011b36  sub     rsp, 20h
0x140011b3a  mov     ebx, edx
0x140011b3c  mov     rdi, rcx
0x140011b3f  call    ??1CDocument@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CDocument::~CDocument(void)
0x140011b44  test    bl, 1
0x140011b47  jz      short loc_140011B51
0x140011b49  mov     rcx, rdi; Block
0x140011b4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011b51  mov     rbx, [rsp+28h+arg_0]
0x140011b56  mov     rax, rdi
0x140011b59  add     rsp, 20h
0x140011b5d  pop     rdi
0x140011b5e  retn
```
