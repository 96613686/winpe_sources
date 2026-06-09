# CSpDynamicString::~CSpDynamicString(void)

- ea: `0x180006e18`
- end: `0x180006e22`
- name: `??1CSpDynamicString@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(CSpDynamicString *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019dce`
- `0x180019df2`
- `0x180019ee4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e1b`

## pseudocode

```c
void __fastcall CSpDynamicString::~CSpDynamicString(LPVOID *this)
{
  CoTaskMemFree(*this);
}

```

## disassembly

```asm
0x180006e18  mov     rcx, [rcx]
0x180006e1b  jmp     cs:__imp_CoTaskMemFree
```
