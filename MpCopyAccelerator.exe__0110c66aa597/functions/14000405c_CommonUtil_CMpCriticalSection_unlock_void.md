# CommonUtil::CMpCriticalSection::unlock(void)

- ea: `0x14000405c`
- end: `0x140004063`
- name: `?unlock@CMpCriticalSection@CommonUtil@@QEBAXXZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002c2c`
- `0x14001e9dc`
- `0x14001efa4`
- `0x14001f304`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000405c`

## pseudocode

```c
// attributes: thunk
void __stdcall CommonUtil::CMpCriticalSection::unlock(LPCRITICAL_SECTION lpCriticalSection)
{
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x14000405c  jmp     cs:__imp_LeaveCriticalSection
```
