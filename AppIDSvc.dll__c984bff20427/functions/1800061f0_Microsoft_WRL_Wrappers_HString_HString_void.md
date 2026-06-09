# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1800061f0`
- end: `0x18000620f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000c852`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800061fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800061fc`

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
0x1800061f0  push    rbx
0x1800061f2  sub     rsp, 20h
0x1800061f6  mov     rbx, rcx
0x1800061f9  mov     rcx, [rcx]; string
0x1800061fc  call    cs:__imp_WindowsDeleteString
0x180006202  mov     qword ptr [rbx], 0
0x180006209  add     rsp, 20h
0x18000620d  pop     rbx
0x18000620e  retn
```
