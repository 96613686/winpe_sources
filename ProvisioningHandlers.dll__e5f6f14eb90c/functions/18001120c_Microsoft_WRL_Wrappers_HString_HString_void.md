# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18001120c`
- end: `0x180011232`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002999f`
- `0x1800299b1`
- `0x180029c21`
- `0x180029d8f`
- `0x18002a74c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011218`

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
0x18001120c  push    rbx
0x18001120e  sub     rsp, 20h
0x180011212  mov     rbx, rcx
0x180011215  mov     rcx, [rcx]; string
0x180011218  call    cs:__imp_WindowsDeleteString
0x18001121f  nop     dword ptr [rax+rax+00h]
0x180011224  mov     qword ptr [rbx], 0
0x18001122b  add     rsp, 20h
0x18001122f  pop     rbx
0x180011230  retn
```
