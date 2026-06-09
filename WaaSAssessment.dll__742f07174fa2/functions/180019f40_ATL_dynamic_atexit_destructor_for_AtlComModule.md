# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x180019f40`
- end: `0x180019f4c`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006d10`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  ATL::CAtlComModule::~CAtlComModule((ATL::CAtlComModule *)&ATL::_AtlComModule);
}

```

## disassembly

```asm
0x180019f40  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; this
0x180019f47  jmp     ??1CAtlComModule@ATL@@QEAA@XZ; ATL::CAtlComModule::~CAtlComModule(void)
```
