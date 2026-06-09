# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x14000a374`
- end: `0x14000a393`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `13`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400114a8`
- `0x140011531`
- `0x140011608`
- `0x14001161a`
- `0x14001163e`
- `0x140011650`
- `0x140011674`
- `0x1400116ce`
- `0x140011927`
- `0x1400119a5`
- `0x1400119b7`
- `0x140011a24`
- `0x140011a36`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000a380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000a380`

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
0x14000a374  push    rbx
0x14000a376  sub     rsp, 20h
0x14000a37a  mov     rbx, rcx
0x14000a37d  mov     rcx, [rcx]; string
0x14000a380  call    cs:__imp_WindowsDeleteString
0x14000a386  mov     qword ptr [rbx], 0
0x14000a38d  add     rsp, 20h
0x14000a391  pop     rbx
0x14000a392  retn
```
