# HString::~HString(void)

- ea: `0x1800041c4`
- end: `0x1800041ef`
- name: `??1HString@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(HString *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003197c`

## callees

- `0x1800041c4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800041d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800041d5`

## pseudocode

```c
void __fastcall HString::~HString(HSTRING *this)
{
  HSTRING v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    WindowsDeleteString(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x1800041c4  push    rbx
0x1800041c6  sub     rsp, 20h
0x1800041ca  mov     rbx, rcx
0x1800041cd  mov     rcx, [rcx]; string
0x1800041d0  test    rcx, rcx
0x1800041d3  jz      short loc_1800041E8
0x1800041d5  call    cs:__imp_WindowsDeleteString
0x1800041dc  nop     dword ptr [rax+rax+00h]
0x1800041e1  mov     qword ptr [rbx], 0
0x1800041e8  add     rsp, 20h
0x1800041ec  pop     rbx
0x1800041ed  retn
```
