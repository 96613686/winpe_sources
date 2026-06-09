# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180010628`
- end: `0x180010647`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002b42a`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010634`

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
0x180010628  push    rbx
0x18001062a  sub     rsp, 20h
0x18001062e  mov     rbx, rcx
0x180010631  mov     rcx, [rcx]; string
0x180010634  call    cs:__imp_WindowsDeleteString
0x18001063a  mov     qword ptr [rbx], 0
0x180010641  add     rsp, 20h
0x180010645  pop     rbx
0x180010646  retn
```
