# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18000d744`
- end: `0x18000d763`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `13`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800409fb`
- `0x180040a99`
- `0x180040d2b`
- `0x180040db1`
- `0x180041185`
- `0x180041437`
- `0x180041449`
- `0x1800419fa`
- `0x180041ca0`
- `0x180041dbc`
- `0x180042057`
- `0x18004443b`
- `0x1800445fe`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d750`

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
0x18000d744  push    rbx
0x18000d746  sub     rsp, 20h
0x18000d74a  mov     rbx, rcx
0x18000d74d  mov     rcx, [rcx]; string
0x18000d750  call    cs:__imp_WindowsDeleteString
0x18000d756  mov     qword ptr [rbx], 0
0x18000d75d  add     rsp, 20h
0x18000d761  pop     rbx
0x18000d762  retn
```
