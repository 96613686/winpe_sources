# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18001041c`
- end: `0x180010442`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18004ef7d`
- `0x18004ef8f`
- `0x18004f094`
- `0x18004f5d4`
- `0x18004f65e`
- `0x18004faa2`
- `0x18004fab4`
- `0x18004fb68`
- `0x18004fb7a`
- `0x18004fc7a`
- `0x180050a5e`
- `0x180050d12`
- `0x180050dd8`
- `0x180050e20`
- `0x180050e32`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010428`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010428`

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
0x18001041c  push    rbx
0x18001041e  sub     rsp, 20h
0x180010422  mov     rbx, rcx
0x180010425  mov     rcx, [rcx]; string
0x180010428  call    cs:__imp_WindowsDeleteString
0x18001042f  nop     dword ptr [rax+rax+00h]
0x180010434  mov     qword ptr [rbx], 0
0x18001043b  add     rsp, 20h
0x18001043f  pop     rbx
0x180010440  retn
```
