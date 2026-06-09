# Windows::Internal::String::~String(void)

- ea: `0x1800253bc`
- end: `0x1800253d3`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Windows::Internal::String *__hidden this)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180025a08`
- `0x1800262dc`
- `0x1800338a8`
- `0x180037f80`
- `0x180038890`
- `0x180039d10`
- `0x18003c4d0`
- `0x18003cb50`
- `0x18003d550`
- `0x18003f890`
- `0x180054d84`
- `0x180054f6c`
- `0x180055134`
- `0x1800583b1`
- `0x18005841d`
- `0x180058d0a`
- `0x18005909d`
- `0x1800590c1`
- `0x1800590d3`
- `0x180059151`
- `0x18005953e`

## callees

- `0x1800253bc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253c8`

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
0x1800253bc  sub     rsp, 28h
0x1800253c0  mov     rcx, [rcx]; string
0x1800253c3  test    rcx, rcx
0x1800253c6  jz      short loc_1800253CE
0x1800253c8  call    cs:__imp_WindowsDeleteString
0x1800253ce  add     rsp, 28h
0x1800253d2  retn
```
