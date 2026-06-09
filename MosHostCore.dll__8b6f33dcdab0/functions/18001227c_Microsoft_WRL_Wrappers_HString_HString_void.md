# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18001227c`
- end: `0x18001229b`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180023f57`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012288`

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
0x18001227c  push    rbx
0x18001227e  sub     rsp, 20h
0x180012282  mov     rbx, rcx
0x180012285  mov     rcx, [rcx]; string
0x180012288  call    cs:__imp_WindowsDeleteString
0x18001228e  mov     qword ptr [rbx], 0
0x180012295  add     rsp, 20h
0x180012299  pop     rbx
0x18001229a  retn
```
