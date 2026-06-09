# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18002dd4c`
- end: `0x18002dd72`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003197c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dd58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dd58`

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
0x18002dd4c  push    rbx
0x18002dd4e  sub     rsp, 20h
0x18002dd52  mov     rbx, rcx
0x18002dd55  mov     rcx, [rcx]; string
0x18002dd58  call    cs:__imp_WindowsDeleteString
0x18002dd5f  nop     dword ptr [rax+rax+00h]
0x18002dd64  mov     qword ptr [rbx], 0
0x18002dd6b  add     rsp, 20h
0x18002dd6f  pop     rbx
0x18002dd70  retn
```
