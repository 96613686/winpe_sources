# PolicyModel::CXmlSerializer::`scalar deleting destructor'(uint)

- ea: `0x14000bb90`
- end: `0x14000bbbf`
- name: `??_GCXmlSerializer@PolicyModel@@MEAAPEAXI@Z`
- size: `47`
- prototype: `PolicyModel::CXmlSerializer *__fastcall(PolicyModel::CXmlSerializer *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x14000157c`
- `0x14000bb48`
- `0x14000bb90`

## pseudocode

```c
PolicyModel::CXmlSerializer *__fastcall PolicyModel::CXmlSerializer::`scalar deleting destructor'(
        PolicyModel::CXmlSerializer *this,
        char a2)
{
  PolicyModel::CXmlSerializer::~CXmlSerializer(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000bb90  mov     [rsp+arg_0], rbx
0x14000bb95  push    rdi
0x14000bb96  sub     rsp, 20h
0x14000bb9a  mov     ebx, edx
0x14000bb9c  mov     rdi, rcx
0x14000bb9f  call    ??1CXmlSerializer@PolicyModel@@MEAA@XZ; PolicyModel::CXmlSerializer::~CXmlSerializer(void)
0x14000bba4  test    bl, 1
0x14000bba7  jz      short loc_14000BBB1
0x14000bba9  mov     rcx, rdi; Block
0x14000bbac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000bbb1  mov     rbx, [rsp+28h+arg_0]
0x14000bbb6  mov     rax, rdi
0x14000bbb9  add     rsp, 20h
0x14000bbbd  pop     rdi
0x14000bbbe  retn
```
