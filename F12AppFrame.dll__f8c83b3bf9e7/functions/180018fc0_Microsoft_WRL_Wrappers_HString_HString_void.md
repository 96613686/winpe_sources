# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180018fc0`
- end: `0x180018fdf`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180033634`
- `0x1800336d6`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018fcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018fcc`

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
0x180018fc0  push    rbx
0x180018fc2  sub     rsp, 20h
0x180018fc6  mov     rbx, rcx
0x180018fc9  mov     rcx, [rcx]; string
0x180018fcc  call    cs:__imp_WindowsDeleteString
0x180018fd2  mov     qword ptr [rbx], 0
0x180018fd9  add     rsp, 20h
0x180018fdd  pop     rbx
0x180018fde  retn
```
