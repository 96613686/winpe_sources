# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180013260`
- end: `0x18001327f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180028f40`
- `0x180028f7e`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001326c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001326c`

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
0x180013260  push    rbx
0x180013262  sub     rsp, 20h
0x180013266  mov     rbx, rcx
0x180013269  mov     rcx, [rcx]; string
0x18001326c  call    cs:__imp_WindowsDeleteString
0x180013272  mov     qword ptr [rbx], 0
0x180013279  add     rsp, 20h
0x18001327d  pop     rbx
0x18001327e  retn
```
