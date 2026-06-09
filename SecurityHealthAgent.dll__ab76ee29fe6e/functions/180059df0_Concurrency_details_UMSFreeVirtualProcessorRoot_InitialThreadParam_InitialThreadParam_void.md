# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180059df0`
- end: `0x180059e07`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_3`
- size: `23`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180069e70`
- `0x18008703c`
- `0x1800b28be`
- `0x1800b2f47`

## callees

- `0x180059df0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059dfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059dfc`

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
0x180059df0  sub     rsp, 28h
0x180059df4  mov     rcx, [rcx]; string
0x180059df7  test    rcx, rcx
0x180059dfa  jz      short loc_180059E02
0x180059dfc  call    cs:WindowsDeleteString
0x180059e02  add     rsp, 28h
0x180059e06  retn
```
