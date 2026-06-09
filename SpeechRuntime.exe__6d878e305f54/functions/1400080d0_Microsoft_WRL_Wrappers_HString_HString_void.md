# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1400080d0`
- end: `0x1400080ef`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14002f5b1`
- `0x14002fb11`
- `0x14002fb47`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400080dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400080dc`

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
0x1400080d0  push    rbx
0x1400080d2  sub     rsp, 20h
0x1400080d6  mov     rbx, rcx
0x1400080d9  mov     rcx, [rcx]; string
0x1400080dc  call    cs:__imp_WindowsDeleteString
0x1400080e2  mov     qword ptr [rbx], 0
0x1400080e9  add     rsp, 20h
0x1400080ed  pop     rbx
0x1400080ee  retn
```
