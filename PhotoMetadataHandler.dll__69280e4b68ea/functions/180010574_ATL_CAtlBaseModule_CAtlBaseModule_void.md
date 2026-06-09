# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180010574`
- end: `0x18001059a`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800285c0`

## callees

- `0x1800105a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010581`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010581`

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
0x180010574  push    rbx
0x180010576  sub     rsp, 20h
0x18001057a  mov     rbx, rcx
0x18001057d  add     rcx, 28h ; '('; lpCriticalSection
0x180010581  call    cs:__imp_DeleteCriticalSection
0x180010588  nop     dword ptr [rax+rax+00h]
0x18001058d  mov     rcx, rbx; this
0x180010590  add     rsp, 20h
0x180010594  pop     rbx
0x180010595  jmp     ??1_ATL_BASE_MODULE70@ATL@@QEAA@XZ; ATL::_ATL_BASE_MODULE70::~_ATL_BASE_MODULE70(void)
```
