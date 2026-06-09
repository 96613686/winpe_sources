# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18002a610`
- end: `0x18002a630`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800318c0`

## callees

- `0x18002a678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a61d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a61d`

## pseudocode

```c
void __fastcall ATL::CAtlBaseModule::~CAtlBaseModule(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this + 1);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)this);
}

```

## disassembly

```asm
0x18002a610  push    rbx
0x18002a612  sub     rsp, 20h
0x18002a616  mov     rbx, rcx
0x18002a619  add     rcx, 28h ; '('; lpCriticalSection
0x18002a61d  call    cs:__imp_DeleteCriticalSection
0x18002a623  mov     rcx, rbx; this
0x18002a626  add     rsp, 20h
0x18002a62a  pop     rbx
0x18002a62b  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
