# Microsoft::WRL::Wrappers::HString::GetAddressOf(void)

- ea: `0x140007118`
- end: `0x14000713a`
- name: `?GetAddressOf@HString@Wrappers@WRL@Microsoft@@QEAAPEAPEAUHSTRING__@@XZ`
- size: `34`
- prototype: `HSTRING *__fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007dcc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140007124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140007124`

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
0x140007118  push    rbx
0x14000711a  sub     rsp, 20h
0x14000711e  mov     rbx, rcx
0x140007121  mov     rcx, [rcx]; string
0x140007124  call    cs:__imp_WindowsDeleteString
0x14000712a  mov     rax, rbx
0x14000712d  mov     qword ptr [rbx], 0
0x140007134  add     rsp, 20h
0x140007138  pop     rbx
0x140007139  retn
```
