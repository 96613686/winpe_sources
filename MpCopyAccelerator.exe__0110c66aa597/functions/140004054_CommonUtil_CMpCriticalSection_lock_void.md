# CommonUtil::CMpCriticalSection::lock(void)

- ea: `0x140004054`
- end: `0x14000405b`
- name: `?lock@CMpCriticalSection@CommonUtil@@QEBAXXZ`
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

- `KERNEL32!EnterCriticalSection` at `0x140004054`

## pseudocode

```c
// attributes: thunk
void __stdcall CommonUtil::CMpCriticalSection::lock(LPCRITICAL_SECTION lpCriticalSection)
{
  EnterCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x140004054  jmp     cs:__imp_EnterCriticalSection
```
