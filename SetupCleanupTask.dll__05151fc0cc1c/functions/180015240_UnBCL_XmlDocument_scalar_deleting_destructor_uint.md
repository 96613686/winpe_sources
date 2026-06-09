# UnBCL::XmlDocument::`scalar deleting destructor'(uint)

- ea: `0x180015240`
- end: `0x180015271`
- name: `??_GXmlDocument@UnBCL@@UEAAPEAXI@Z`
- size: `49`
- prototype: `UnBCL::XmlDocument *__fastcall(UnBCL::XmlDocument *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x180015240`

## import_xrefs

- `unbcl!??1XmlDocument@UnBCL@@UEAA@XZ` at `0x18001524f`
- `unbcl!??1XmlDocument@UnBCL@@UEAA@XZ` at `0x18001524f`
- `unbcl!??3Object@UnBCL@@SAXPEAX@Z` at `0x18001525d`
- `unbcl!??3Object@UnBCL@@SAXPEAX@Z` at `0x18001525d`

## pseudocode

```c
UnBCL::XmlDocument *__fastcall UnBCL::XmlDocument::`scalar deleting destructor'(UnBCL::XmlDocument *this, char a2)
{
  UnBCL::XmlDocument::~XmlDocument(this);
  if ( (a2 & 1) != 0 )
    UnBCL::Object::operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180015240  mov     [rsp+arg_0], rbx
0x180015245  push    rdi
0x180015246  sub     rsp, 20h
0x18001524a  mov     ebx, edx
0x18001524c  mov     rdi, rcx
0x18001524f  call    cs:__imp_??1XmlDocument@UnBCL@@UEAA@XZ; UnBCL::XmlDocument::~XmlDocument(void)
0x180015255  test    bl, 1
0x180015258  jz      short loc_180015263
0x18001525a  mov     rcx, rdi
0x18001525d  call    cs:__imp_??3Object@UnBCL@@SAXPEAX@Z; UnBCL::Object::operator delete(void *)
0x180015263  mov     rbx, [rsp+28h+arg_0]
0x180015268  mov     rax, rdi
0x18001526b  add     rsp, 20h
0x18001526f  pop     rdi
0x180015270  retn
```
