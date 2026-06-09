# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180012958`
- end: `0x180012977`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180059f10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012964`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012964`

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
0x180012958  push    rbx
0x18001295a  sub     rsp, 20h
0x18001295e  mov     rbx, rcx
0x180012961  mov     rcx, [rcx]; string
0x180012964  call    cs:__imp_WindowsDeleteString
0x18001296a  mov     qword ptr [rbx], 0
0x180012971  add     rsp, 20h
0x180012975  pop     rbx
0x180012976  retn
```
