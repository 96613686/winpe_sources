# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x140004b84`
- end: `0x140004ba3`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001bd8a`
- `0x14001c39c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140004b90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140004b90`

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
0x140004b84  push    rbx
0x140004b86  sub     rsp, 20h
0x140004b8a  mov     rbx, rcx
0x140004b8d  mov     rcx, [rcx]; string
0x140004b90  call    cs:__imp_WindowsDeleteString
0x140004b96  mov     qword ptr [rbx], 0
0x140004b9d  add     rsp, 20h
0x140004ba1  pop     rbx
0x140004ba2  retn
```
