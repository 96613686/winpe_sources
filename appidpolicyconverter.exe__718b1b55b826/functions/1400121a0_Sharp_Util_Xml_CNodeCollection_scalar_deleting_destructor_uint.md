# Sharp::Util::Xml::CNodeCollection::`scalar deleting destructor'(uint)

- ea: `0x1400121a0`
- end: `0x1400121cf`
- name: `??_GCNodeCollection@Xml@Util@Sharp@@UEAAPEAXI@Z`
- size: `47`
- prototype: `Sharp::Util::Xml::CNodeCollection *__fastcall(Sharp::Util::Xml::CNodeCollection *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x14000157c`
- `0x1400121a0`
- `0x14001377c`

## pseudocode

```c
Sharp::Util::Xml::CNodeCollection *__fastcall Sharp::Util::Xml::CNodeCollection::`scalar deleting destructor'(
        Sharp::Util::Xml::CNodeCollection *this,
        char a2)
{
  Sharp::Util::Xml::CNodeCollection::~CNodeCollection(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400121a0  mov     [rsp+arg_0], rbx
0x1400121a5  push    rdi
0x1400121a6  sub     rsp, 20h
0x1400121aa  mov     ebx, edx
0x1400121ac  mov     rdi, rcx
0x1400121af  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x1400121b4  test    bl, 1
0x1400121b7  jz      short loc_1400121C1
0x1400121b9  mov     rcx, rdi; Block
0x1400121bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400121c1  mov     rbx, [rsp+28h+arg_0]
0x1400121c6  mov     rax, rdi
0x1400121c9  add     rsp, 20h
0x1400121cd  pop     rdi
0x1400121ce  retn
```
