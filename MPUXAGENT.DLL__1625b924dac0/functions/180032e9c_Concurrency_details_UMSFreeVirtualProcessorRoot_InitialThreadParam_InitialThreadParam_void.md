# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180032e9c`
- end: `0x180032eb3`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_0`
- size: `23`
- prototype: `void __fastcall(HMODULE *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800691b0`
- `0x180069352`
- `0x18006935e`
- `0x180069b24`

## callees

- `0x180032e9c`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180032ea8`
- `KERNEL32!FreeLibrary` at `0x180032ea8`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        HMODULE *this)
{
  HMODULE v1; // rcx

  v1 = *this;
  if ( v1 )
    FreeLibrary(v1);
}

```

## disassembly

```asm
0x180032e9c  sub     rsp, 28h
0x180032ea0  mov     rcx, [rcx]; hLibModule
0x180032ea3  test    rcx, rcx
0x180032ea6  jz      short loc_180032EAE
0x180032ea8  call    cs:FreeLibrary
0x180032eae  add     rsp, 28h
0x180032eb2  retn
```
