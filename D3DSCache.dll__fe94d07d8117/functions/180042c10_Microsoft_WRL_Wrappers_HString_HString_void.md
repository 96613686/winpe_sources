# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180042c10`
- end: `0x180042c2f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800a6dfa`
- `0x1800a6ef0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042c1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042c1c`

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
0x180042c10  push    rbx
0x180042c12  sub     rsp, 20h
0x180042c16  mov     rbx, rcx
0x180042c19  mov     rcx, [rcx]; string
0x180042c1c  call    cs:__imp_WindowsDeleteString
0x180042c22  mov     qword ptr [rbx], 0
0x180042c29  add     rsp, 20h
0x180042c2d  pop     rbx
0x180042c2e  retn
```
