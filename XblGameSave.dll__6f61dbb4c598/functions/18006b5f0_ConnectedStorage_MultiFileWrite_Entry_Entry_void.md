# ConnectedStorage::MultiFileWrite::Entry::~Entry(void)

- ea: `0x18006b5f0`
- end: `0x18006b63c`
- name: `??1Entry@MultiFileWrite@ConnectedStorage@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(ConnectedStorage::MultiFileWrite::Entry *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18006b224`
- `0x18006b934`
- `0x18008bc73`

## callees

- `0x1800124b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b618`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b618`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b629`

## pseudocode

```c
void __fastcall ConnectedStorage::MultiFileWrite::Entry::~Entry(HSTRING *this)
{
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(this + 3);
  WindowsDeleteString(this[2]);
  this[2] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x18006b5f0  push    rbx
0x18006b5f2  sub     rsp, 20h
0x18006b5f6  mov     rbx, rcx
0x18006b5f9  add     rcx, 18h
0x18006b5fd  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x18006b602  mov     rcx, [rbx+10h]; string
0x18006b606  call    cs:__imp_WindowsDeleteString
0x18006b60c  mov     qword ptr [rbx+10h], 0
0x18006b614  mov     rcx, [rbx+8]; string
0x18006b618  call    cs:__imp_WindowsDeleteString
0x18006b61e  mov     qword ptr [rbx+8], 0
0x18006b626  mov     rcx, [rbx]; string
0x18006b629  call    cs:__imp_WindowsDeleteString
0x18006b62f  mov     qword ptr [rbx], 0
0x18006b636  add     rsp, 20h
0x18006b63a  pop     rbx
0x18006b63b  retn
```
