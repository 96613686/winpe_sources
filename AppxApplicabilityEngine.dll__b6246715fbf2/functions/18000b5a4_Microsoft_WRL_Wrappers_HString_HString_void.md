# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18000b5a4`
- end: `0x18000b5c3`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002344d`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b5b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b5b0`

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
0x18000b5a4  push    rbx
0x18000b5a6  sub     rsp, 20h
0x18000b5aa  mov     rbx, rcx
0x18000b5ad  mov     rcx, [rcx]; string
0x18000b5b0  call    cs:__imp_WindowsDeleteString
0x18000b5b6  mov     qword ptr [rbx], 0
0x18000b5bd  add     rsp, 20h
0x18000b5c1  pop     rbx
0x18000b5c2  retn
```
