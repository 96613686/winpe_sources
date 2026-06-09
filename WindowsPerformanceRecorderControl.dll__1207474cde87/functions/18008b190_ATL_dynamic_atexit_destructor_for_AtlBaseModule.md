# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x18008b190`
- end: `0x18008b1b1`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180048700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b19b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008b19b`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_1800BE928);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)&ATL::_AtlBaseModule);
}

```

## disassembly

```asm
0x18008b190  sub     rsp, 28h
0x18008b194  lea     rcx, stru_1800BE928; lpCriticalSection
0x18008b19b  call    cs:__imp_DeleteCriticalSection
0x18008b1a1  lea     rcx, ?_AtlBaseModule@ATL@@3VCAtlBaseModule@1@A; this
0x18008b1a8  add     rsp, 28h
0x18008b1ac  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
