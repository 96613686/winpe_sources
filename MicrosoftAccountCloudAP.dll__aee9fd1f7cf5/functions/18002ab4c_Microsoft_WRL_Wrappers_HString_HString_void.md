# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18002ab4c`
- end: `0x18002ab6b`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800314ce`
- `0x1800314f6`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ab58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ab58`

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
0x18002ab4c  push    rbx
0x18002ab4e  sub     rsp, 20h
0x18002ab52  mov     rbx, rcx
0x18002ab55  mov     rcx, [rcx]; string
0x18002ab58  call    cs:__imp_WindowsDeleteString
0x18002ab5e  mov     qword ptr [rbx], 0
0x18002ab65  add     rsp, 20h
0x18002ab69  pop     rbx
0x18002ab6a  retn
```
