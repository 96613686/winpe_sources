# _CPITRTaskHandler::Worker_::_1_::dtor$2

- ea: `0x180010c6a`
- end: `0x180010c78`
- name: `_CPITRTaskHandler::Worker_::_1_::dtor$2`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## import_xrefs

- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180010c71`

## pseudocode

```c
void __fastcall CPITRTaskHandler::Worker_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  UnBCL::String::~String((UnBCL::String *)(a2 + 104));
}

```

## disassembly

```asm
0x180010c6a  lea     rcx, [rdx+68h]
0x180010c71  jmp     cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
```
