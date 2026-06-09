# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1800111ac`
- end: `0x1800111cb`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180057fa0`
- `0x180058368`
- `0x18005851b`
- `0x180058677`
- `0x180058b13`
- `0x180058bd6`
- `0x180059166`
- `0x18005943c`
- `0x180059bef`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800111b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800111b8`

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
0x1800111ac  push    rbx
0x1800111ae  sub     rsp, 20h
0x1800111b2  mov     rbx, rcx
0x1800111b5  mov     rcx, [rcx]; string
0x1800111b8  call    cs:__imp_WindowsDeleteString
0x1800111be  mov     qword ptr [rbx], 0
0x1800111c5  add     rsp, 20h
0x1800111c9  pop     rbx
0x1800111ca  retn
```
