# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180018014`
- end: `0x180018033`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180055f00`
- `0x1800560c3`
- `0x180056279`
- `0x180057288`
- `0x1800577f9`
- `0x180057926`
- `0x18005799e`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018020`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018020`

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
0x180018014  push    rbx
0x180018016  sub     rsp, 20h
0x18001801a  mov     rbx, rcx
0x18001801d  mov     rcx, [rcx]; string
0x180018020  call    cs:__imp_WindowsDeleteString
0x180018026  mov     qword ptr [rbx], 0
0x18001802d  add     rsp, 20h
0x180018031  pop     rbx
0x180018032  retn
```
