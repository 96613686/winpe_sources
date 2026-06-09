# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180011af8`
- end: `0x180011b18`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013ef0`

## callees

- `0x180011b4c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011b05`
- `KERNEL32!DeleteCriticalSection` at `0x180011b05`

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
0x180011af8  push    rbx
0x180011afa  sub     rsp, 20h
0x180011afe  mov     rbx, rcx
0x180011b01  add     rcx, 28h ; '('; lpCriticalSection
0x180011b05  call    cs:__imp_DeleteCriticalSection
0x180011b0b  mov     rcx, rbx; this
0x180011b0e  add     rsp, 20h
0x180011b12  pop     rbx
0x180011b13  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
