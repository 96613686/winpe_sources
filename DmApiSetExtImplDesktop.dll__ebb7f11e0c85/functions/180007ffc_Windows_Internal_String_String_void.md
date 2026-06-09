# Windows::Internal::String::~String(void)

- ea: `0x180007ffc`
- end: `0x18000801a`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(Windows::Internal::String *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083c0`
- `0x180008980`

## callees

- `0x180007ffc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008008`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008008`

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
0x180007ffc  sub     rsp, 28h
0x180008000  mov     rcx, [rcx]; string
0x180008003  test    rcx, rcx
0x180008006  jz      short loc_180008014
0x180008008  call    cs:__imp_WindowsDeleteString
0x18000800f  nop     dword ptr [rax+rax+00h]
0x180008014  add     rsp, 28h
0x180008018  retn
```
