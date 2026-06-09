# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18000f8e8`
- end: `0x18000f907`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180019daa`
- `0x180019dbc`
- `0x180019de0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f8f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f8f4`

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
0x18000f8e8  push    rbx
0x18000f8ea  sub     rsp, 20h
0x18000f8ee  mov     rbx, rcx
0x18000f8f1  mov     rcx, [rcx]; string
0x18000f8f4  call    cs:__imp_WindowsDeleteString
0x18000f8fa  mov     qword ptr [rbx], 0
0x18000f901  add     rsp, 20h
0x18000f905  pop     rbx
0x18000f906  retn
```
