# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180012784`
- end: `0x1800127a3`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180029b99`
- `0x180029c18`
- `0x180029c2a`
- `0x180029c4e`
- `0x180029d12`
- `0x18002a452`
- `0x18002a4ce`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012790`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012790`

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
0x180012784  push    rbx
0x180012786  sub     rsp, 20h
0x18001278a  mov     rbx, rcx
0x18001278d  mov     rcx, [rcx]; string
0x180012790  call    cs:__imp_WindowsDeleteString
0x180012796  mov     qword ptr [rbx], 0
0x18001279d  add     rsp, 20h
0x1800127a1  pop     rbx
0x1800127a2  retn
```
