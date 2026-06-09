# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18000a688`
- end: `0x18000a69f`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_0`
- size: `23`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a67c`
- `0x18000bc00`

## callees

- `0x18000a688`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a694`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a694`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    CloseHandle(v1);
}

```

## disassembly

```asm
0x18000a688  sub     rsp, 28h
0x18000a68c  mov     rcx, [rcx]; hObject
0x18000a68f  test    rcx, rcx
0x18000a692  jz      short loc_18000A69A
0x18000a694  call    cs:CloseHandle
0x18000a69a  add     rsp, 28h
0x18000a69e  retn
```
