# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1800087e4`
- end: `0x180008803`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800103fb`
- `0x18001041f`
- `0x180010431`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800087f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800087f0`

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
0x1800087e4  push    rbx
0x1800087e6  sub     rsp, 20h
0x1800087ea  mov     rbx, rcx
0x1800087ed  mov     rcx, [rcx]; string
0x1800087f0  call    cs:__imp_WindowsDeleteString
0x1800087f6  mov     qword ptr [rbx], 0
0x1800087fd  add     rsp, 20h
0x180008801  pop     rbx
0x180008802  retn
```
