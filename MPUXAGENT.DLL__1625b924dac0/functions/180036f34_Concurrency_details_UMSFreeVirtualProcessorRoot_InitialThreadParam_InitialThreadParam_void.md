# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180036f34`
- end: `0x180036f4b`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_2`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180069eff`
- `0x180069f47`

## callees

- `0x180036f34`

## import_xrefs

- `MpClient!MpHandleClose` at `0x180036f40`
- `MpClient!MpHandleClose` at `0x180036f40`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *this)
{
  if ( *(_QWORD *)this )
    MpHandleClose();
}

```

## disassembly

```asm
0x180036f34  sub     rsp, 28h
0x180036f38  mov     rcx, [rcx]
0x180036f3b  test    rcx, rcx
0x180036f3e  jz      short loc_180036F46
0x180036f40  call    cs:MpHandleClose
0x180036f46  add     rsp, 28h
0x180036f4a  retn
```
