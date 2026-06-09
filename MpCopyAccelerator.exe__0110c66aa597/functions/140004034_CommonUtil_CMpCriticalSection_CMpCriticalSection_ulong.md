# CommonUtil::CMpCriticalSection::CMpCriticalSection(ulong)

- ea: `0x140004034`
- end: `0x14000404c`
- name: `??0CMpCriticalSection@CommonUtil@@QEAA@K@Z`
- size: `24`
- prototype: `__int64 __fastcall(CommonUtil::CMpCriticalSection *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002b9c`
- `0x14001cdb0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14000403d`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14000403d`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall CommonUtil::CMpCriticalSection::CMpCriticalSection(
        struct _RTL_CRITICAL_SECTION *this,
        DWORD a2)
{
  InitializeCriticalSectionAndSpinCount(this, a2);
  return this;
}

```

## disassembly

```asm
0x140004034  push    rbx
0x140004036  sub     rsp, 20h
0x14000403a  mov     rbx, rcx
0x14000403d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140004043  mov     rax, rbx
0x140004046  add     rsp, 20h
0x14000404a  pop     rbx
0x14000404b  retn
```
