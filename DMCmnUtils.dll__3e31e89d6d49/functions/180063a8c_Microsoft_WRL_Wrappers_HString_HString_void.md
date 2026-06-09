# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180063a8c`
- end: `0x180063ab2`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800b7f50`
- `0x1800b7f62`
- `0x1800b7ff2`
- `0x1800b8004`
- `0x1800b8016`
- `0x1800b8814`
- `0x1800b8892`
- `0x1800b88a4`
- `0x1800b8a67`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063a98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063a98`

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
0x180063a8c  push    rbx
0x180063a8e  sub     rsp, 20h
0x180063a92  mov     rbx, rcx
0x180063a95  mov     rcx, [rcx]; string
0x180063a98  call    cs:__imp_WindowsDeleteString
0x180063a9f  nop     dword ptr [rax+rax+00h]
0x180063aa4  mov     qword ptr [rbx], 0
0x180063aab  add     rsp, 20h
0x180063aaf  pop     rbx
0x180063ab0  retn
```
