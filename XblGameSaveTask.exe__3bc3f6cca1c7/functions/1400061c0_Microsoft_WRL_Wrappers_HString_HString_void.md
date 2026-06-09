# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1400061c0`
- end: `0x1400061df`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000664e`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400061cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400061cc`

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
0x1400061c0  push    rbx
0x1400061c2  sub     rsp, 20h
0x1400061c6  mov     rbx, rcx
0x1400061c9  mov     rcx, [rcx]; string
0x1400061cc  call    cs:__imp_WindowsDeleteString
0x1400061d2  mov     qword ptr [rbx], 0
0x1400061d9  add     rsp, 20h
0x1400061dd  pop     rbx
0x1400061de  retn
```
