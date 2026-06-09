# TLock<ATL::CComAutoCriticalSection>::~TLock<ATL::CComAutoCriticalSection>(void)

- ea: `0x180002488`
- end: `0x180002492`
- name: `??1?$TLock@VCComAutoCriticalSection@ATL@@@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000be18`
- `0x18000bef0`
- `0x18000c040`
- `0x18000c0e6`
- `0x18000c124`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000248b`

## pseudocode

```c
void __fastcall TLock<ATL::CComAutoCriticalSection>::~TLock<ATL::CComAutoCriticalSection>(LPCRITICAL_SECTION *a1)
{
  LeaveCriticalSection(*a1);
}

```

## disassembly

```asm
0x180002488  mov     rcx, [rcx]
0x18000248b  jmp     cs:__imp_LeaveCriticalSection
```
