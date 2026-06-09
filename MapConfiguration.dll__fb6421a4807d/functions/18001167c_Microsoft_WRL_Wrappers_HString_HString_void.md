# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18001167c`
- end: `0x18001169b`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003c9c7`
- `0x18003ca21`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011688`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011688`

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
0x18001167c  push    rbx
0x18001167e  sub     rsp, 20h
0x180011682  mov     rbx, rcx
0x180011685  mov     rcx, [rcx]; string
0x180011688  call    cs:__imp_WindowsDeleteString
0x18001168e  mov     qword ptr [rbx], 0
0x180011695  add     rsp, 20h
0x180011699  pop     rbx
0x18001169a  retn
```
