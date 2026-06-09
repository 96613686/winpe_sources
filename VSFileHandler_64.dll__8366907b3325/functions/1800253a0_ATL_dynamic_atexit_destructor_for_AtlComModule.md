# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x1800253a0`
- end: `0x1800253b6`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800023a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  ATL::CAtlComModule::Term((ATL::CAtlComModule *)&ATL::_AtlComModule);
}

```

## disassembly

```asm
0x1800253a0  sub     rsp, 28h
0x1800253a4  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; this
0x1800253ab  call    ?Term@CAtlComModule@ATL@@QEAAXXZ; ATL::CAtlComModule::Term(void)
0x1800253b0  nop
0x1800253b1  add     rsp, 28h
0x1800253b5  retn
```
