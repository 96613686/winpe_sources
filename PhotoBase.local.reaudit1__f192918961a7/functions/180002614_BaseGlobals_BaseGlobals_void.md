# BaseGlobals::~BaseGlobals(void)

- ea: `0x180002614`
- end: `0x180002636`
- name: `??1BaseGlobals@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(BaseGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180007a30`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002621`
- `KERNEL32!DeleteCriticalSection` at `0x180002621`
- `KERNEL32!DeleteCriticalSection` at `0x18000262f`

## pseudocode

```c
void __fastcall BaseGlobals::~BaseGlobals(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this + 1);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180002614  push    rbx
0x180002616  sub     rsp, 20h
0x18000261a  mov     rbx, rcx
0x18000261d  add     rcx, 28h ; '('; lpCriticalSection
0x180002621  call    cs:__imp_DeleteCriticalSection
0x180002627  mov     rcx, rbx
0x18000262a  add     rsp, 20h
0x18000262e  pop     rbx
0x18000262f  jmp     cs:__imp_DeleteCriticalSection
```
