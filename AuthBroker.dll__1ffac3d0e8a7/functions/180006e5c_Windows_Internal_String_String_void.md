# Windows::Internal::String::~String(void)

- ea: `0x180006e5c`
- end: `0x180006e73`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Windows::Internal::String *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a2c4`
- `0x18000f568`
- `0x180012660`
- `0x180012bd0`
- `0x180012d80`
- `0x18001449c`
- `0x180015820`
- `0x180015890`
- `0x1800170ec`
- `0x180017150`
- `0x180017770`
- `0x1800188a0`
- `0x18001bb90`

## callees

- `0x180006e5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006e68`

## pseudocode

```c
void __fastcall Windows::Internal::String::~String(Windows::Internal::String *this)
{
  HSTRING__ *hstring; // rcx

  hstring = this->_hstring;
  if ( hstring )
    WindowsDeleteString(hstring);
}

```

## disassembly

```asm
0x180006e5c  sub     rsp, 28h
0x180006e60  mov     this, [this]; string
0x180006e63  test    this, this
0x180006e66  jz      short loc_180006E6E
0x180006e68  call    cs:__imp_WindowsDeleteString
0x180006e6e  add     rsp, 28h
0x180006e72  retn
```
