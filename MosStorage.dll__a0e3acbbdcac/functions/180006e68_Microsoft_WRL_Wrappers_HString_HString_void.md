# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180006e68`
- end: `0x180006e87`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000ee56`
- `0x18000f02a`
- `0x18000f03c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006e74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006e74`

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
0x180006e68  push    rbx
0x180006e6a  sub     rsp, 20h
0x180006e6e  mov     rbx, rcx
0x180006e71  mov     rcx, [rcx]; string
0x180006e74  call    cs:__imp_WindowsDeleteString
0x180006e7a  mov     qword ptr [rbx], 0
0x180006e81  add     rsp, 20h
0x180006e85  pop     rbx
0x180006e86  retn
```
