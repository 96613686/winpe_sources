# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18000fce4`
- end: `0x18000fd03`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800293c9`
- `0x180029651`
- `0x180029c77`
- `0x180029d0b`
- `0x180029d1d`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fcf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fcf0`

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
0x18000fce4  push    rbx
0x18000fce6  sub     rsp, 20h
0x18000fcea  mov     rbx, rcx
0x18000fced  mov     rcx, [rcx]; string
0x18000fcf0  call    cs:__imp_WindowsDeleteString
0x18000fcf6  mov     qword ptr [rbx], 0
0x18000fcfd  add     rsp, 20h
0x18000fd01  pop     rbx
0x18000fd02  retn
```
