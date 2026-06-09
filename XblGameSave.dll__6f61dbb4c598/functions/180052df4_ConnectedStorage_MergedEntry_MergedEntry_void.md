# ConnectedStorage::MergedEntry::~MergedEntry(void)

- ea: `0x180052df4`
- end: `0x180052e37`
- name: `??1MergedEntry@ConnectedStorage@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(ConnectedStorage::MergedEntry *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180054af8`
- `0x1800632fc`
- `0x180065134`
- `0x1800661cc`
- `0x18008a9fe`
- `0x18008b73e`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052e01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052e13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052e24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052e01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052e13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052e24`

## pseudocode

```c
void __fastcall ConnectedStorage::MergedEntry::~MergedEntry(HSTRING *this)
{
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x180052df4  push    rbx
0x180052df6  sub     rsp, 20h
0x180052dfa  mov     rbx, rcx
0x180052dfd  mov     rcx, [rcx+18h]; string
0x180052e01  call    cs:__imp_WindowsDeleteString
0x180052e07  mov     qword ptr [rbx+18h], 0
0x180052e0f  mov     rcx, [rbx+8]; string
0x180052e13  call    cs:__imp_WindowsDeleteString
0x180052e19  mov     qword ptr [rbx+8], 0
0x180052e21  mov     rcx, [rbx]; string
0x180052e24  call    cs:__imp_WindowsDeleteString
0x180052e2a  mov     qword ptr [rbx], 0
0x180052e31  add     rsp, 20h
0x180052e35  pop     rbx
0x180052e36  retn
```
