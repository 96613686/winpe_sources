# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x14003cf70`
- end: `0x14003cf8f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14004fde4`
- `0x14004ff5e`
- `0x14004ff70`
- `0x14004ff82`
- `0x140050048`
- `0x14005007e`
- `0x140050090`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003cf7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003cf7c`

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
0x14003cf70  push    rbx
0x14003cf72  sub     rsp, 20h
0x14003cf76  mov     rbx, rcx
0x14003cf79  mov     rcx, [rcx]; string
0x14003cf7c  call    cs:__imp_WindowsDeleteString
0x14003cf82  mov     qword ptr [rbx], 0
0x14003cf89  add     rsp, 20h
0x14003cf8d  pop     rbx
0x14003cf8e  retn
```
