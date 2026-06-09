# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x18000e4c0`
- end: `0x18000e4e1`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `33`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e4e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e4cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e4cb`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_180026B38);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)&ATL::_AtlBaseModule);
}

```

## disassembly

```asm
0x18000e4c0  sub     rsp, 28h
0x18000e4c4  lea     rcx, stru_180026B38; lpCriticalSection
0x18000e4cb  call    cs:__imp_DeleteCriticalSection
0x18000e4d1  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x18000e4d8  add     rsp, 28h
0x18000e4dc  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
