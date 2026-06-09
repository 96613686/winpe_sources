# Windows::Internal::String::~String(void)

- ea: `0x180006f34`
- end: `0x180006f4b`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Windows::Internal::String *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ec4`
- `0x1800074c4`
- `0x180009a20`
- `0x180009f2c`

## callees

- `0x180006f34`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006f40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006f40`

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
0x180006f34  sub     rsp, 28h
0x180006f38  mov     rcx, [rcx]; string
0x180006f3b  test    rcx, rcx
0x180006f3e  jz      short loc_180006F46
0x180006f40  call    cs:__imp_WindowsDeleteString
0x180006f46  add     rsp, 28h
0x180006f4a  retn
```
