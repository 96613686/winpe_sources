# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180036f4c`
- end: `0x180036f63`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_3`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18006b132`
- `0x18006bc75`
- `0x18006bc8d`

## callees

- `0x180036f4c`

## import_xrefs

- `MpClient!MpConfigClose` at `0x180036f58`
- `MpClient!MpConfigClose` at `0x180036f58`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *this)
{
  if ( *(_QWORD *)this )
    MpConfigClose();
}

```

## disassembly

```asm
0x180036f4c  sub     rsp, 28h
0x180036f50  mov     rcx, [rcx]
0x180036f53  test    rcx, rcx
0x180036f56  jz      short loc_180036F5E
0x180036f58  call    cs:MpConfigClose
0x180036f5e  add     rsp, 28h
0x180036f62  retn
```
