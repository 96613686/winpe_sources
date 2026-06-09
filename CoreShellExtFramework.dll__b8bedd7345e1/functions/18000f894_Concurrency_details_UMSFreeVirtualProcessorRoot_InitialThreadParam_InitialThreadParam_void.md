# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18000f894`
- end: `0x18000f8ab`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_2`
- size: `23`
- prototype: `void __fastcall(void **this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f864`
- `0x180010480`
- `0x1800105b8`

## callees

- `0x18000f894`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f8a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f8a0`

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
0x18000f894  sub     rsp, 28h
0x18000f898  mov     rcx, [rcx]; pv
0x18000f89b  test    rcx, rcx
0x18000f89e  jz      short loc_18000F8A6
0x18000f8a0  call    cs:__imp_CoTaskMemFree
0x18000f8a6  add     rsp, 28h
0x18000f8aa  retn
```
