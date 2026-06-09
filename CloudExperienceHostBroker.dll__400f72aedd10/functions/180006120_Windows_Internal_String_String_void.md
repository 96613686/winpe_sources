# Windows::Internal::String::~String(void)

- ea: `0x180006120`
- end: `0x180006139`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(Windows::Internal::String *__hidden this)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x180009010`
- `0x180009194`
- `0x180021ce8`
- `0x180021d18`
- `0x1800237d0`
- `0x180026130`
- `0x180026f34`
- `0x180029eb8`
- `0x18002a650`
- `0x18002a694`
- `0x18002c390`
- `0x18002cb00`
- `0x18002f7a0`
- `0x18002f9a0`
- `0x18002fa60`
- `0x180033788`
- `0x180034c10`
- `0x180034cd0`
- `0x180036e29`

## callees

- `0x180006120`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006131`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006131`

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
0x180006120  sub     rsp, 28h
0x180006124  mov     rcx, [rcx]; string
0x180006127  test    rcx, rcx
0x18000612a  jnz     short loc_180006131
0x18000612c  add     rsp, 28h
0x180006130  retn
0x180006131  call    cs:__imp_WindowsDeleteString
0x180006137  jmp     short loc_18000612C
```
