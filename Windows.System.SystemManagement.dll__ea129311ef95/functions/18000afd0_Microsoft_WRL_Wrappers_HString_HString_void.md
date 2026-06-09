# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18000afd0`
- end: `0x18000afef`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180029252`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000afdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000afdc`

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
0x18000afd0  push    rbx
0x18000afd2  sub     rsp, 20h
0x18000afd6  mov     rbx, rcx
0x18000afd9  mov     rcx, [rcx]; string
0x18000afdc  call    cs:__imp_WindowsDeleteString
0x18000afe2  mov     qword ptr [rbx], 0
0x18000afe9  add     rsp, 20h
0x18000afed  pop     rbx
0x18000afee  retn
```
