# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180012050`
- end: `0x180012067`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_3`
- size: `23`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013b40`

## callees

- `0x180012050`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001205c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001205c`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        HSTRING *this)
{
  HSTRING v1; // rcx

  v1 = *this;
  if ( v1 )
    WindowsDeleteString(v1);
}

```

## disassembly

```asm
0x180012050  sub     rsp, 28h
0x180012054  mov     rcx, [rcx]; string
0x180012057  test    rcx, rcx
0x18001205a  jz      short loc_180012062
0x18001205c  call    cs:WindowsDeleteString
0x180012062  add     rsp, 28h
0x180012066  retn
```
