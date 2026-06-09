# _SetupRecoveryTaskHandler::Worker_::_1_::dtor$1

- ea: `0x18000cb34`
- end: `0x18000cb42`
- name: `_SetupRecoveryTaskHandler::Worker_::_1_::dtor$1`
- size: `14`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update`

## import_xrefs

- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000cb3b`

## pseudocode

```c
__int64 __fastcall SetupRecoveryTaskHandler::Worker_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a2 + 152);
}

```

## disassembly

```asm
0x18000cb34  lea     rcx, [rdx+98h]
0x18000cb3b  jmp     cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
```
