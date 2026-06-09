# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180015040`
- end: `0x180015066`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180020713`
- `0x180020725`
- `0x180020791`
- `0x18002088d`
- `0x18002089f`
- `0x1800208d5`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001504c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001504c`

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
0x180015040  push    rbx
0x180015042  sub     rsp, 20h
0x180015046  mov     rbx, rcx
0x180015049  mov     rcx, [rcx]; string
0x18001504c  call    cs:__imp_WindowsDeleteString
0x180015053  nop     dword ptr [rax+rax+00h]
0x180015058  mov     qword ptr [rbx], 0
0x18001505f  add     rsp, 20h
0x180015063  pop     rbx
0x180015064  retn
```
