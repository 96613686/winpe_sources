# _SetupRecoveryTaskHandler::Worker_::_1_::dtor$0

- ea: `0x18000cb20`
- end: `0x18000cb2e`
- name: `_SetupRecoveryTaskHandler::Worker_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update`

## import_xrefs

- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000cb27`

## pseudocode

```c
void __fastcall SetupRecoveryTaskHandler::Worker_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  UnBCL::String::~String((UnBCL::String *)(a2 + 104));
}

```

## disassembly

```asm
0x18000cb20  lea     rcx, [rdx+68h]
0x18000cb27  jmp     cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
```
