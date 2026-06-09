# ConnectedStorage::LoadMetaData

- ea: `0x180064e88`
- end: `0x180064efa`
- name: `ConnectedStorage::LoadMetaData`
- size: `114`
- prototype: `__int64 __fastcall(ConnectedStorage::File *this, HSTRING *newString)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180064d14`

## callees

- `0x180012ed8`
- `0x180064f00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064ebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064ee9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064ebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064ee9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall ConnectedStorage::LoadMetaData(void **this, HSTRING *newString)
{
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  ConnectedStorage::LoadStringW(&string, this, 0xFFFFu);
  ConnectedStorage::SimpleHStringWrapper::operator=(newString);
  WindowsDeleteString(string);
  ConnectedStorage::LoadStringW(&string, this, 0x82u);
  ConnectedStorage::SimpleHStringWrapper::operator=(newString + 1);
  return WindowsDeleteString(string);
}

```

## disassembly

```asm
0x180064e88  mov     [rsp+arg_0], rbx
0x180064e8d  push    rdi
0x180064e8e  sub     rsp, 20h
0x180064e92  mov     rdi, rdx
0x180064e95  mov     rbx, rcx
0x180064e98  mov     r8d, 0FFFFh
0x180064e9e  mov     rdx, rcx; this
0x180064ea1  lea     rcx, [rsp+28h+string]; string
0x180064ea6  call    ConnectedStorage__LoadStringW
0x180064eab  nop
0x180064eac  mov     rdx, rax
0x180064eaf  mov     rcx, rdi; newString
0x180064eb2  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180064eb7  nop
0x180064eb8  mov     rcx, [rsp+28h+string]; string
0x180064ebd  call    cs:__imp_WindowsDeleteString
0x180064ec3  mov     r8d, 82h
0x180064ec9  mov     rdx, rbx; this
0x180064ecc  lea     rcx, [rsp+28h+string]; string
0x180064ed1  call    ConnectedStorage__LoadStringW
0x180064ed6  nop
0x180064ed7  lea     rcx, [rdi+8]; newString
0x180064edb  mov     rdx, rax
0x180064ede  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x180064ee3  nop
0x180064ee4  mov     rcx, [rsp+28h+string]; string
0x180064ee9  call    cs:__imp_WindowsDeleteString
0x180064eef  mov     rbx, [rsp+28h+arg_0]
0x180064ef4  add     rsp, 20h
0x180064ef8  pop     rdi
0x180064ef9  retn
```
