# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180002eec`
- end: `0x180002f0b`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `12`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001d6ac`
- `0x18001d87d`
- `0x18001d8c5`
- `0x18001d90d`
- `0x18001d955`
- `0x18001d99d`
- `0x18001d9e5`
- `0x18001da2d`
- `0x18001da75`
- `0x18001db2a`
- `0x18001dbcd`
- `0x18001dc5e`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002ef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002ef8`

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
0x180002eec  push    rbx
0x180002eee  sub     rsp, 20h
0x180002ef2  mov     rbx, rcx
0x180002ef5  mov     rcx, [rcx]; string
0x180002ef8  call    cs:__imp_WindowsDeleteString
0x180002efe  mov     qword ptr [rbx], 0
0x180002f05  add     rsp, 20h
0x180002f09  pop     rbx
0x180002f0a  retn
```
