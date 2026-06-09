# _SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::dtor$1

- ea: `0x18000ca1a`
- end: `0x18000ca28`
- name: `_SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::dtor$1`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update`

## import_xrefs

- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18000ca21`

## pseudocode

```c
void __fastcall SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  UnBCL::String::~String((UnBCL::String *)(a2 + 176));
}

```

## disassembly

```asm
0x18000ca1a  lea     rcx, [rdx+0B0h]
0x18000ca21  jmp     cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
```
