# Windows::Internal::String::Initialize(HSTRING__ * const &)

- ea: `0x18004c884`
- end: `0x18004c8cf`
- name: `?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(Windows::Internal::String *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004cce8`

## callees

- `0x18004c884`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c8bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c8bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004c8a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004c8a5`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize(HSTRING *this, HSTRING *a2)
{
  HRESULT v3; // edi
  HSTRING v4; // rcx
  HSTRING newString; // [rsp+30h] [rbp+8h] BYREF

  newString = 0;
  v3 = WindowsDuplicateString(*a2, &newString);
  if ( v3 >= 0 )
  {
    v4 = *this;
    *this = newString;
    WindowsDeleteString(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004c884  mov     [rsp+arg_8], rbx
0x18004c889  push    rdi
0x18004c88a  sub     rsp, 20h
0x18004c88e  mov     rax, rdx
0x18004c891  mov     [rsp+28h+newString], 0
0x18004c89a  mov     rbx, rcx
0x18004c89d  lea     rdx, [rsp+28h+newString]; newString
0x18004c8a2  mov     rcx, [rax]; string
0x18004c8a5  call    cs:__imp_WindowsDuplicateString
0x18004c8ab  mov     edi, eax
0x18004c8ad  test    eax, eax
0x18004c8af  js      short loc_18004C8C2
0x18004c8b1  mov     rdx, [rsp+28h+newString]
0x18004c8b6  mov     rcx, [rbx]; string
0x18004c8b9  mov     [rbx], rdx
0x18004c8bc  call    cs:__imp_WindowsDeleteString
0x18004c8c2  mov     rbx, [rsp+28h+arg_8]
0x18004c8c7  mov     eax, edi
0x18004c8c9  add     rsp, 20h
0x18004c8cd  pop     rdi
0x18004c8ce  retn
```
