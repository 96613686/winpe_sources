# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18001eea8`
- end: `0x18001eece`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002a418`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eeb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eeb4`

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
0x18001eea8  push    rbx
0x18001eeaa  sub     rsp, 20h
0x18001eeae  mov     rbx, rcx
0x18001eeb1  mov     rcx, [rcx]; string
0x18001eeb4  call    cs:__imp_WindowsDeleteString
0x18001eebb  nop     dword ptr [rax+rax+00h]
0x18001eec0  mov     qword ptr [rbx], 0
0x18001eec7  add     rsp, 20h
0x18001eecb  pop     rbx
0x18001eecc  retn
```
