# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18000a150`
- end: `0x18000a16f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180026472`
- `0x180026488`
- `0x18002649e`
- `0x1800264b4`
- `0x1800264cd`
- `0x1800264df`
- `0x1800264f1`
- `0x180026503`
- `0x180026515`
- `0x18002655d`
- `0x18002656f`
- `0x180026670`
- `0x180026682`
- `0x180026694`
- `0x1800267a2`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a15c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a15c`

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
0x18000a150  push    rbx
0x18000a152  sub     rsp, 20h
0x18000a156  mov     rbx, rcx
0x18000a159  mov     rcx, [rcx]; string
0x18000a15c  call    cs:__imp_WindowsDeleteString
0x18000a162  mov     qword ptr [rbx], 0
0x18000a169  add     rsp, 20h
0x18000a16d  pop     rbx
0x18000a16e  retn
```
