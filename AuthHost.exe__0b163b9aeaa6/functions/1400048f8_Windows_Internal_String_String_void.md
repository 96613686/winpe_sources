# Windows::Internal::String::~String(void)

- ea: `0x1400048f8`
- end: `0x14000490f`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Windows::Internal::String *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1400047f4`
- `0x140005f18`
- `0x1400131e1`
- `0x1400131f7`
- `0x14001320d`
- `0x140013226`
- `0x14001323f`
- `0x140013258`
- `0x140013295`
- `0x1400132a7`
- `0x1400132b9`
- `0x1400132cb`

## callees

- `0x1400048f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140004904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140004904`

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
0x1400048f8  sub     rsp, 28h
0x1400048fc  mov     rcx, [rcx]; string
0x1400048ff  test    rcx, rcx
0x140004902  jz      short loc_14000490A
0x140004904  call    cs:__imp_WindowsDeleteString
0x14000490a  add     rsp, 28h
0x14000490e  retn
```
