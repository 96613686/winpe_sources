# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18001e630`
- end: `0x18001e64f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002912e`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e63c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e63c`

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
0x18001e630  push    rbx
0x18001e632  sub     rsp, 20h
0x18001e636  mov     rbx, rcx
0x18001e639  mov     rcx, [rcx]; string
0x18001e63c  call    cs:__imp_WindowsDeleteString
0x18001e642  mov     qword ptr [rbx], 0
0x18001e649  add     rsp, 20h
0x18001e64d  pop     rbx
0x18001e64e  retn
```
