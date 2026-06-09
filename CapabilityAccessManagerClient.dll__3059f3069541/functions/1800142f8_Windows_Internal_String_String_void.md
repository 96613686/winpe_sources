# Windows::Internal::String::~String(void)

- ea: `0x1800142f8`
- end: `0x18001430f`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Windows::Internal::String *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800142bc`
- `0x18001a224`
- `0x18001f014`
- `0x18001f424`
- `0x1800225a0`
- `0x180037126`

## callees

- `0x1800142f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014304`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014304`

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
0x1800142f8  sub     rsp, 28h
0x1800142fc  mov     rcx, [rcx]; string
0x1800142ff  test    rcx, rcx
0x180014302  jz      short loc_18001430A
0x180014304  call    cs:__imp_WindowsDeleteString
0x18001430a  add     rsp, 28h
0x18001430e  retn
```
