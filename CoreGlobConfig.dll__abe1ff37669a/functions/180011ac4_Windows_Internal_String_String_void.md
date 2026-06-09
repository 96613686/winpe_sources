# Windows::Internal::String::~String(void)

- ea: `0x180011ac4`
- end: `0x180011adb`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180015030`
- `0x180015714`
- `0x180015ea8`
- `0x180019454`
- `0x1800195b0`
- `0x180023d0b`
- `0x180023d1d`
- `0x180023d2f`
- `0x180023d65`
- `0x180023e9e`

## callees

- `0x180011ac4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ad0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011ad0`

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
0x180011ac4  sub     rsp, 28h
0x180011ac8  mov     rcx, [rcx]; string
0x180011acb  test    rcx, rcx
0x180011ace  jz      short loc_180011AD6
0x180011ad0  call    cs:__imp_WindowsDeleteString
0x180011ad6  add     rsp, 28h
0x180011ada  retn
```
