# ATL::CComAutoCriticalSection::~CComAutoCriticalSection(void)

- ea: `0x180007938`
- end: `0x18000793f`
- name: `??1CComAutoCriticalSection@ATL@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800111f9`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007938`

## pseudocode

```c
// attributes: thunk
void __stdcall ATL::CComAutoCriticalSection::~CComAutoCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180007938  jmp     cs:__imp_DeleteCriticalSection
```
