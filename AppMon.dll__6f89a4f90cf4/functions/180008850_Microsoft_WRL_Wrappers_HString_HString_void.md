# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180008850`
- end: `0x18000886f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000f78b`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000885c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000885c`

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
0x180008850  push    rbx
0x180008852  sub     rsp, 20h
0x180008856  mov     rbx, rcx
0x180008859  mov     rcx, [rcx]; string
0x18000885c  call    cs:__imp_WindowsDeleteString
0x180008862  mov     qword ptr [rbx], 0
0x180008869  add     rsp, 20h
0x18000886d  pop     rbx
0x18000886e  retn
```
