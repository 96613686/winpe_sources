# ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(void)

- ea: `0x1800313e4`
- end: `0x180031415`
- name: `??1ContainerIndexMetaData@ConnectedStorage@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(ConnectedStorage::ContainerIndexMetaData *__hidden this)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18003373c`
- `0x1800555f0`
- `0x180056474`
- `0x18005cab4`
- `0x180063888`
- `0x180063bbc`
- `0x180065da8`
- `0x180066044`
- `0x180088270`
- `0x18008aaeb`
- `0x18008b762`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800313f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800313f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031402`

## pseudocode

```c
void __fastcall ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(HSTRING *this)
{
  WindowsDeleteString(this[1]);
  this[1] = 0;
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x1800313e4  push    rbx
0x1800313e6  sub     rsp, 20h
0x1800313ea  mov     rbx, rcx
0x1800313ed  mov     rcx, [rcx+8]; string
0x1800313f1  call    cs:__imp_WindowsDeleteString
0x1800313f7  mov     qword ptr [rbx+8], 0
0x1800313ff  mov     rcx, [rbx]; string
0x180031402  call    cs:__imp_WindowsDeleteString
0x180031408  mov     qword ptr [rbx], 0
0x18003140f  add     rsp, 20h
0x180031413  pop     rbx
0x180031414  retn
```
