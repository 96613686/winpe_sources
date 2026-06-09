# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18004c7c4`
- end: `0x18004c7db`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_0`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18013f524`
- `0x18013f530`
- `0x18013f53c`

## callees

- `0x18004c7c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c7d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c7d0`

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
0x18004c7c4  sub     rsp, 28h
0x18004c7c8  mov     rcx, [rcx]; pv
0x18004c7cb  test    rcx, rcx
0x18004c7ce  jz      short loc_18004C7D6
0x18004c7d0  call    cs:CoTaskMemFree
0x18004c7d6  add     rsp, 28h
0x18004c7da  retn
```
