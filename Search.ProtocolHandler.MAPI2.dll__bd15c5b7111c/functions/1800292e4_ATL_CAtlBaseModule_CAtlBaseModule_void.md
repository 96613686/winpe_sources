# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800292e4`
- end: `0x180029304`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003e3c0`

## callees

- `0x18002934c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800292f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800292f1`

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
0x1800292e4  push    rbx
0x1800292e6  sub     rsp, 20h
0x1800292ea  mov     rbx, rcx
0x1800292ed  add     rcx, 28h ; '('; lpCriticalSection
0x1800292f1  call    cs:__imp_DeleteCriticalSection
0x1800292f7  mov     rcx, rbx; this
0x1800292fa  add     rsp, 20h
0x1800292fe  pop     rbx
0x1800292ff  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
