# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180031228`
- end: `0x18003123f`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800692f3`

## callees

- `0x180031228`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180031234`
- `KERNEL32!LocalFree` at `0x180031234`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    LocalFree(v1);
}

```

## disassembly

```asm
0x180031228  sub     rsp, 28h
0x18003122c  mov     rcx, [rcx]; hMem
0x18003122f  test    rcx, rcx
0x180031232  jz      short loc_18003123A
0x180031234  call    cs:__imp_LocalFree
0x18003123a  add     rsp, 28h
0x18003123e  retn
```
