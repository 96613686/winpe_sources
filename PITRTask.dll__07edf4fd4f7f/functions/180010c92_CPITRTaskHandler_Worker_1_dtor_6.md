# _CPITRTaskHandler::Worker_::_1_::dtor$6

- ea: `0x180010c92`
- end: `0x180010ca0`
- name: `_CPITRTaskHandler::Worker_::_1_::dtor$6`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## import_xrefs

- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180010c99`

## pseudocode

```c
void __fastcall CPITRTaskHandler::Worker_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  UnBCL::String::~String((UnBCL::String *)(a2 + 296));
}

```

## disassembly

```asm
0x180010c92  lea     rcx, [rdx+128h]
0x180010c99  jmp     cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
```
