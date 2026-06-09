# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x1800272a0`
- end: `0x1800272c1`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000fdd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800272ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800272ab`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_180098FC8);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)&ATL::_AtlBaseModule);
}

```

## disassembly

```asm
0x1800272a0  sub     rsp, 28h
0x1800272a4  lea     rcx, stru_180098FC8; lpCriticalSection
0x1800272ab  call    cs:__imp_DeleteCriticalSection
0x1800272b1  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x1800272b8  add     rsp, 28h
0x1800272bc  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
