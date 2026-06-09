# Microsoft::WRL::Wrappers::HString::GetAddressOf(void)

- ea: `0x18003b75c`
- end: `0x18003b785`
- name: `?GetAddressOf@HString@Wrappers@WRL@Microsoft@@QEAAPEAPEAUHSTRING__@@XZ`
- size: `41`
- prototype: `HSTRING *__fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003197c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b768`

## pseudocode

```c
HSTRING *__fastcall Microsoft::WRL::Wrappers::HString::GetAddressOf(HSTRING *this)
{
  HSTRING *result; // rax

  WindowsDeleteString(*this);
  result = this;
  *this = 0;
  return result;
}

```

## disassembly

```asm
0x18003b75c  push    rbx
0x18003b75e  sub     rsp, 20h
0x18003b762  mov     rbx, rcx
0x18003b765  mov     rcx, [rcx]; string
0x18003b768  call    cs:__imp_WindowsDeleteString
0x18003b76f  nop     dword ptr [rax+rax+00h]
0x18003b774  mov     rax, rbx
0x18003b777  mov     qword ptr [rbx], 0
0x18003b77e  add     rsp, 20h
0x18003b782  pop     rbx
0x18003b783  retn
```
