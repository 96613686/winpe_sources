# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180055738`
- end: `0x180055758`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005db00`

## callees

- `0x18005578c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055745`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055745`

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
0x180055738  push    rbx
0x18005573a  sub     rsp, 20h
0x18005573e  mov     rbx, rcx
0x180055741  add     rcx, 28h ; '('; lpCriticalSection
0x180055745  call    cs:__imp_DeleteCriticalSection
0x18005574b  mov     rcx, rbx; this
0x18005574e  add     rsp, 20h
0x180055752  pop     rbx
0x180055753  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
