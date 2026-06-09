# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x180007e90`
- end: `0x180007ea9`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `25`
- prototype: `int __fastcall(ATL::CAtlComModule *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007eb0`
- `0x18000faa4`

## pseudocode

```c
int __fastcall ATL::_dynamic_initializer_for___AtlComModule__(ATL::CAtlComModule *a1)
{
  ATL::CAtlComModule::CAtlComModule(a1);
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x180007e90  sub     rsp, 28h
0x180007e94  call    ??0CAtlComModule@ATL@@QEAA@XZ; ATL::CAtlComModule::CAtlComModule(void)
0x180007e99  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180007ea0  add     rsp, 28h
0x180007ea4  jmp     atexit
```
