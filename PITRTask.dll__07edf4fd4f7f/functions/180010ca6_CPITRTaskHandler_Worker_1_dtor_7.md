# _CPITRTaskHandler::Worker_::_1_::dtor$7

- ea: `0x180010ca6`
- end: `0x180010cb4`
- name: `_CPITRTaskHandler::Worker_::_1_::dtor$7`
- size: `14`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## import_xrefs

- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180010cad`

## pseudocode

```c
__int64 __fastcall CPITRTaskHandler::Worker_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(a2 + 208);
}

```

## disassembly

```asm
0x180010ca6  lea     rcx, [rdx+0D0h]
0x180010cad  jmp     cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
```
