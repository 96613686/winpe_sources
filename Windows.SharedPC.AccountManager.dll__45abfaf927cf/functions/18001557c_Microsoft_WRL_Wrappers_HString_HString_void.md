# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18001557c`
- end: `0x18001559b`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002498a`
- `0x180025580`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015588`

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
0x18001557c  push    rbx
0x18001557e  sub     rsp, 20h
0x180015582  mov     rbx, rcx
0x180015585  mov     rcx, [rcx]; string
0x180015588  call    cs:__imp_WindowsDeleteString
0x18001558e  mov     qword ptr [rbx], 0
0x180015595  add     rsp, 20h
0x180015599  pop     rbx
0x18001559a  retn
```
