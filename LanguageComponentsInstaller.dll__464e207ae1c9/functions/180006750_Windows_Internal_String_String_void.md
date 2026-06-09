# Windows::Internal::String::~String(void)

- ea: `0x180006750`
- end: `0x180006767`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180028093`
- `0x180028d14`

## callees

- `0x180006750`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000675c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000675c`

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
0x180006750  sub     rsp, 28h
0x180006754  mov     rcx, [rcx]; string
0x180006757  test    rcx, rcx
0x18000675a  jz      short loc_180006762
0x18000675c  call    cs:__imp_WindowsDeleteString
0x180006762  add     rsp, 28h
0x180006766  retn
```
