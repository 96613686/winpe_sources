# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x140016170`
- end: `0x140016190`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400082b0`
- `0x14000da50`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  ATL::CAtlComModule::Term((ATL::CAtlComModule *)&ATL::_AtlComModule);
  return wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(&ATL::_AtlComModule);
}

```

## disassembly

```asm
0x140016170  sub     rsp, 28h
0x140016174  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; this
0x14001617b  call    ?Term@CAtlComModule@ATL@@QEAAXXZ; ATL::CAtlComModule::Term(void)
0x140016180  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x140016187  add     rsp, 28h
0x14001618b  jmp     ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
```
