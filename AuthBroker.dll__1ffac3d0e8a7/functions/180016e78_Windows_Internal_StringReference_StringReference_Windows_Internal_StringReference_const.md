# Windows::Internal::StringReference::StringReference(Windows::Internal::StringReference const &)

- ea: `0x180016e78`
- end: `0x180016ebe`
- name: `??0StringReference@Internal@Windows@@QEAA@AEBV012@@Z`
- size: `70`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const Windows::Internal::StringReference *other)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800054bc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016e9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016e9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016eaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016eaf`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const Windows::Internal::StringReference *other)
{
  const wchar_t *StringRawBuffer; // rax
  unsigned int length; // [rsp+30h] [rbp+8h] BYREF

  this->_hstring = 0;
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(other->_hstring, &length);
  WindowsCreateStringReference(StringRawBuffer, length, &this->_header, &this->_hstring);
}

```

## disassembly

```asm
0x180016e78  push    rbx
0x180016e7a  sub     rsp, 20h
0x180016e7e  mov     rax, other
0x180016e81  mov     qword ptr [this], 0
0x180016e88  mov     rbx, this
0x180016e8b  mov     [rsp+28h+length], 0
0x180016e93  lea     other, [rsp+28h+length]; length
0x180016e98  mov     this, [rax]; string
0x180016e9b  call    cs:__imp_WindowsGetStringRawBuffer
0x180016ea1  mov     edx, [rsp+28h+length]; length
0x180016ea5  lea     r8, [rbx+8]; hstringHeader
0x180016ea9  mov     this, rax; sourceString
0x180016eac  mov     r9, rbx; string
0x180016eaf  call    cs:__imp_WindowsCreateStringReference
0x180016eb5  mov     rax, rbx
0x180016eb8  add     rsp, 20h
0x180016ebc  pop     rbx
0x180016ebd  retn
```
