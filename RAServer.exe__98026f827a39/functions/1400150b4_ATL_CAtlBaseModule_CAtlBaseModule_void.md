# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1400150b4`
- end: `0x1400150d4`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140016130`

## callees

- `0x140015108`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400150c1`
- `KERNEL32!DeleteCriticalSection` at `0x1400150c1`

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
0x1400150b4  push    rbx
0x1400150b6  sub     rsp, 20h
0x1400150ba  mov     rbx, rcx
0x1400150bd  add     rcx, 28h ; '('; lpCriticalSection
0x1400150c1  call    cs:__imp_DeleteCriticalSection
0x1400150c7  mov     rcx, rbx; this
0x1400150ca  add     rsp, 20h
0x1400150ce  pop     rbx
0x1400150cf  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
