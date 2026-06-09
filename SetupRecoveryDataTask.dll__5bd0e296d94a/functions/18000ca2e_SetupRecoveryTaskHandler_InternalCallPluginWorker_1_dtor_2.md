# _SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::dtor$2

- ea: `0x18000ca2e`
- end: `0x18000ca3c`
- name: `_SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::dtor$2`
- size: `14`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update`

## import_xrefs

- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000ca35`

## pseudocode

```c
__int64 __fastcall SetupRecoveryTaskHandler::InternalCallPluginWorker_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a2 + 128);
}

```

## disassembly

```asm
0x18000ca2e  lea     rcx, [rdx+80h]
0x18000ca35  jmp     cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
```
