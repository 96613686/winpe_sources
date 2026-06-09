# _SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::dtor$0

- ea: `0x18000ca06`
- end: `0x18000ca14`
- name: `_SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::dtor$0`
- size: `14`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update`

## import_xrefs

- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000ca0d`

## pseudocode

```c
__int64 __fastcall SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a2 + 216);
}

```

## disassembly

```asm
0x18000ca06  lea     rcx, [rdx+0D8h]
0x18000ca0d  jmp     cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
```
