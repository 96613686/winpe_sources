# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1800037e4`
- end: `0x18000380a`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a147`
- `0x18000a221`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800037f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800037f0`

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
0x1800037e4  push    rbx
0x1800037e6  sub     rsp, 20h
0x1800037ea  mov     rbx, rcx
0x1800037ed  mov     rcx, [rcx]; string
0x1800037f0  call    cs:__imp_WindowsDeleteString
0x1800037f7  nop     dword ptr [rax+rax+00h]
0x1800037fc  mov     qword ptr [rbx], 0
0x180003803  add     rsp, 20h
0x180003807  pop     rbx
0x180003808  retn
```
