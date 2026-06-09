# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180013718`
- end: `0x180013738`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014ca0`

## callees

- `0x18001376c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013725`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013725`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlBaseModule::~CAtlBaseModule(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this + 1);
  ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70((ATL::_ATL_BASE_MODULE70 *)this);
}

```

## disassembly

```asm
0x180013718  push    rbx
0x18001371a  sub     rsp, 20h
0x18001371e  mov     rbx, rcx
0x180013721  add     rcx, 28h ; '('; lpCriticalSection
0x180013725  call    cs:__imp_DeleteCriticalSection
0x18001372b  mov     rcx, rbx; this
0x18001372e  add     rsp, 20h
0x180013732  pop     rbx
0x180013733  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
