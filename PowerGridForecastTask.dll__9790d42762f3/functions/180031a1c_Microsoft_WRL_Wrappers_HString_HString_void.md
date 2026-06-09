# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180031a1c`
- end: `0x180031a3b`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180036117`
- `0x1800361ef`
- `0x180036213`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031a28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031a28`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HString::~HString(HSTRING *this)
{
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x180031a1c  push    rbx
0x180031a1e  sub     rsp, 20h
0x180031a22  mov     rbx, rcx
0x180031a25  mov     rcx, [rcx]; string
0x180031a28  call    cs:__imp_WindowsDeleteString
0x180031a2e  mov     qword ptr [rbx], 0
0x180031a35  add     rsp, 20h
0x180031a39  pop     rbx
0x180031a3a  retn
```
