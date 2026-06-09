# Windows::Internal::String::~String(void)

- ea: `0x180024150`
- end: `0x180024167`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180024170`
- `0x1800251e8`

## callees

- `0x180024150`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002415c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002415c`

## pseudocode

```c
void __fastcall Windows::Internal::String::~String(HSTRING *this)
{
  HSTRING v1; // rcx

  v1 = *this;
  if ( v1 )
    WindowsDeleteString(v1);
}

```

## disassembly

```asm
0x180024150  sub     rsp, 28h
0x180024154  mov     rcx, [rcx]; string
0x180024157  test    rcx, rcx
0x18002415a  jz      short loc_180024162
0x18002415c  call    cs:__imp_WindowsDeleteString
0x180024162  add     rsp, 28h
0x180024166  retn
```
