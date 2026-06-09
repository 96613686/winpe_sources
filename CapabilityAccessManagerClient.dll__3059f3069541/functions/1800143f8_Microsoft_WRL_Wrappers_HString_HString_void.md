# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1800143f8`
- end: `0x180014417`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180036a98`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014404`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014404`

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
0x1800143f8  push    rbx
0x1800143fa  sub     rsp, 20h
0x1800143fe  mov     rbx, rcx
0x180014401  mov     rcx, [rcx]; string
0x180014404  call    cs:__imp_WindowsDeleteString
0x18001440a  mov     qword ptr [rbx], 0
0x180014411  add     rsp, 20h
0x180014415  pop     rbx
0x180014416  retn
```
