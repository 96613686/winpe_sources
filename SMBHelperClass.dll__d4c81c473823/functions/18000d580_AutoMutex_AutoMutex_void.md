# AutoMutex::~AutoMutex(void)

- ea: `0x18000d580`
- end: `0x18000d58a`
- name: `??1AutoMutex@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(AutoMutex *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180011124`
- `0x180011136`
- `0x18001117b`
- `0x180011223`
- `0x1800112bc`
- `0x1800112ce`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18000d583`

## pseudocode

```c
void __fastcall AutoMutex::~AutoMutex(HANDLE *this)
{
  ReleaseMutex(*this);
}

```

## disassembly

```asm
0x18000d580  mov     rcx, [rcx]
0x18000d583  jmp     cs:__imp_ReleaseMutex
```
