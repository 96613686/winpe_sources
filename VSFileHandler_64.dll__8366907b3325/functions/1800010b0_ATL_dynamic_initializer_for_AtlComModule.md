# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800010b0`
- end: `0x1800010d0`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002324`
- `0x180007a78`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  ATL::CAtlComModule::CAtlComModule((ATL::CAtlComModule *)&ATL::_AtlComModule);
  return atexit((void (__cdecl *)())ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800010b0  sub     rsp, 28h
0x1800010b4  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; this
0x1800010bb  call    ??0CAtlComModule@ATL@@QEAA@XZ; ATL::CAtlComModule::CAtlComModule(void)
0x1800010c0  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x1800010c7  add     rsp, 28h
0x1800010cb  jmp     atexit
```
