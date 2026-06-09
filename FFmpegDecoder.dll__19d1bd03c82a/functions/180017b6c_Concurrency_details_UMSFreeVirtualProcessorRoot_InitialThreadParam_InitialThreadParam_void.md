# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180017b6c`
- end: `0x180017b83`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f1b7`

## callees

- `0x180017b6c`

## import_xrefs

- `swscale_ms!sws_freeContext` at `0x180017b78`
- `swscale_ms!sws_freeContext` at `0x180017b78`

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
0x180017b6c  sub     rsp, 28h
0x180017b70  mov     rcx, [rcx]
0x180017b73  test    rcx, rcx
0x180017b76  jz      short loc_180017B7E
0x180017b78  call    cs:sws_freeContext
0x180017b7e  add     rsp, 28h
0x180017b82  retn
```
