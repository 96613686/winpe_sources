# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18001a0cc`
- end: `0x18001a0e3`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002eef6`
- `0x18002ef1c`

## callees

- `0x18001a0cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0d8`

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
0x18001a0cc  sub     rsp, 28h
0x18001a0d0  mov     rcx, [rcx]; pv
0x18001a0d3  test    rcx, rcx
0x18001a0d6  jz      short loc_18001A0DE
0x18001a0d8  call    cs:CoTaskMemFree
0x18001a0de  add     rsp, 28h
0x18001a0e2  retn
```
