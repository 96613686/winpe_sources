# wil::critical_section::~critical_section(void)

- ea: `0x180065d44`
- end: `0x180065d5d`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800ad6e2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180065d51`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180065d51`

## pseudocode

```c
void __fastcall wil::critical_section::~critical_section(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180065d44  sub     rsp, 38h
0x180065d48  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180065d51  call    cs:__imp_DeleteCriticalSection
0x180065d57  nop
0x180065d58  add     rsp, 38h
0x180065d5c  retn
```
