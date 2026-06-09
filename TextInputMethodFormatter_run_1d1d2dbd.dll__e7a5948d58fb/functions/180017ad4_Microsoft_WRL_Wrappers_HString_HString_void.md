# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180017ad4`
- end: `0x180017af3`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180057593`
- `0x1800575a5`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017ae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017ae0`

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
0x180017ad4  push    rbx
0x180017ad6  sub     rsp, 20h
0x180017ada  mov     rbx, rcx
0x180017add  mov     rcx, [rcx]; string
0x180017ae0  call    cs:__imp_WindowsDeleteString
0x180017ae6  mov     qword ptr [rbx], 0
0x180017aed  add     rsp, 20h
0x180017af1  pop     rbx
0x180017af2  retn
```
