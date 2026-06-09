# DiagHubCommon::AutoCriticalSection::~AutoCriticalSection(void)

- ea: `0x14000463c`
- end: `0x140004646`
- name: `??1AutoCriticalSection@DiagHubCommon@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(LPCRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140014dab`
- `0x140014fa6`
- `0x140015024`
- `0x140015286`
- `0x1400158d4`
- `0x14001591c`
- `0x1400159ca`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000463f`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall DiagHubCommon::AutoCriticalSection::~AutoCriticalSection(LPCRITICAL_SECTION *this)
{
  LeaveCriticalSection(*this);
}

```

## disassembly

```asm
0x14000463c  mov     rcx, [rcx]
0x14000463f  jmp     cs:__imp_LeaveCriticalSection
```
