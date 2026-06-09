# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18003e0d4`
- end: `0x18003e0eb`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_3`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800d7c96`
- `0x1800d7d01`
- `0x1800d7f61`
- `0x1800d7f6d`
- `0x1800d8159`
- `0x1800d9b05`
- `0x1800d9b1d`

## callees

- `0x18003e0d4`

## import_xrefs

- `MpClient!MpConfigClose` at `0x18003e0e0`
- `MpClient!MpConfigClose` at `0x18003e0e0`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *this)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)this;
  if ( v1 )
    MpConfigClose(v1);
}

```

## disassembly

```asm
0x18003e0d4  sub     rsp, 28h
0x18003e0d8  mov     rcx, [rcx]
0x18003e0db  test    rcx, rcx
0x18003e0de  jz      short loc_18003E0E6
0x18003e0e0  call    cs:MpConfigClose
0x18003e0e6  add     rsp, 28h
0x18003e0ea  retn
```
