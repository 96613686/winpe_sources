# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180036f1c`
- end: `0x180036f33`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_1`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18006bc69`
- `0x18006bc81`
- `0x18006bc99`
- `0x18006bca5`
- `0x18006bcb1`
- `0x18006bcbd`
- `0x18006bcc9`

## callees

- `0x180036f1c`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x180036f28`
- `MpClient!MpFreeMemory` at `0x180036f28`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *this)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)this;
  if ( v1 )
    MpFreeMemory(v1);
}

```

## disassembly

```asm
0x180036f1c  sub     rsp, 28h
0x180036f20  mov     rcx, [rcx]
0x180036f23  test    rcx, rcx
0x180036f26  jz      short loc_180036F2E
0x180036f28  call    cs:MpFreeMemory
0x180036f2e  add     rsp, 28h
0x180036f32  retn
```
