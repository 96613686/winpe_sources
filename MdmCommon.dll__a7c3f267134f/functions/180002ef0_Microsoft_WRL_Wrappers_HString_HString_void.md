# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180002ef0`
- end: `0x180002f16`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `12`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001dd8c`
- `0x18001df5d`
- `0x18001dfa5`
- `0x18001dfed`
- `0x18001e035`
- `0x18001e07d`
- `0x18001e0c5`
- `0x18001e10d`
- `0x18001e155`
- `0x18001e20a`
- `0x18001e2ad`
- `0x18001e33e`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002efc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002efc`

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
0x180002ef0  push    rbx
0x180002ef2  sub     rsp, 20h
0x180002ef6  mov     rbx, rcx
0x180002ef9  mov     rcx, [rcx]; string
0x180002efc  call    cs:__imp_WindowsDeleteString
0x180002f03  nop     dword ptr [rax+rax+00h]
0x180002f08  mov     qword ptr [rbx], 0
0x180002f0f  add     rsp, 20h
0x180002f13  pop     rbx
0x180002f14  retn
```
