# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1800118ec`
- end: `0x18001190b`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180023f59`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800118f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800118f8`

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
0x1800118ec  push    rbx
0x1800118ee  sub     rsp, 20h
0x1800118f2  mov     rbx, rcx
0x1800118f5  mov     rcx, [rcx]; string
0x1800118f8  call    cs:__imp_WindowsDeleteString
0x1800118fe  mov     qword ptr [rbx], 0
0x180011905  add     rsp, 20h
0x180011909  pop     rbx
0x18001190a  retn
```
