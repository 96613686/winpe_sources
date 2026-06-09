# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x1800841e0`
- end: `0x1800841f7`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_4`
- size: `23`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18008501c`

## callees

- `0x1800841e0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800841ec`
- `ole32!CoTaskMemFree` at `0x1800841ec`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x1800841e0  sub     rsp, 28h
0x1800841e4  mov     rcx, [rcx]; pv
0x1800841e7  test    rcx, rcx
0x1800841ea  jz      short loc_1800841F2
0x1800841ec  call    cs:CoTaskMemFree
0x1800841f2  add     rsp, 28h
0x1800841f6  retn
```
