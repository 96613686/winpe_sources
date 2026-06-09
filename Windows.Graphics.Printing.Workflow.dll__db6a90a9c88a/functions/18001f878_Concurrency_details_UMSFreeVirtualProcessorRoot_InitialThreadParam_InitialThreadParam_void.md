# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18001f878`
- end: `0x18001f88f`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_3`
- size: `23`
- prototype: `void __fastcall(void **this)`
- caller_count: `15`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f7f8`
- `0x18002554c`
- `0x180033c64`
- `0x18008fa40`
- `0x180091b20`
- `0x1800936d0`
- `0x18009b848`
- `0x1800a63f0`
- `0x1800a73f0`
- `0x1800bbd2c`
- `0x1800c6990`
- `0x1800ca3fc`
- `0x1800ca5d4`
- `0x1800cf150`
- `0x1800e4bb8`

## callees

- `0x18001f878`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f884`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f884`

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
0x18001f878  sub     rsp, 28h
0x18001f87c  mov     rcx, [rcx]; pv
0x18001f87f  test    rcx, rcx
0x18001f882  jz      short loc_18001F88A
0x18001f884  call    cs:CoTaskMemFree
0x18001f88a  add     rsp, 28h
0x18001f88e  retn
```
