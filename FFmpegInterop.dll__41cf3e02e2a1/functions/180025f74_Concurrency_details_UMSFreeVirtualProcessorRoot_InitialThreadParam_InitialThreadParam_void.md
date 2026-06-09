# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180025f74`
- end: `0x180025f8b`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_0`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180025f74`

## import_xrefs

- `swscale_ms!sws_freeContext` at `0x180025f80`
- `swscale_ms!sws_freeContext` at `0x180025f80`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *this)
{
  if ( *(_QWORD *)this )
    sws_freeContext();
}

```

## disassembly

```asm
0x180025f74  sub     rsp, 28h
0x180025f78  mov     rcx, [rcx]
0x180025f7b  test    rcx, rcx
0x180025f7e  jz      short loc_180025F86
0x180025f80  call    cs:sws_freeContext
0x180025f86  add     rsp, 28h
0x180025f8a  retn
```
