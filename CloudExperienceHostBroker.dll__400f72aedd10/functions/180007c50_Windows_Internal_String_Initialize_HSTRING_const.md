# Windows::Internal::String::Initialize(HSTRING__ * const &)

- ea: `0x180007c50`
- end: `0x180007c9b`
- name: `?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(Windows::Internal::String *__hidden this, HSTRING *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180009010`
- `0x1800237d0`
- `0x180026130`
- `0x18002c390`
- `0x18002cb00`
- `0x18002f7a0`
- `0x18002f9a0`
- `0x18002fa60`
- `0x180034c10`
- `0x180034cd0`

## callees

- `0x180007c50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007c88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007c88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180007c71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180007c71`

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
0x180007c50  mov     [rsp+arg_8], rbx
0x180007c55  push    rdi
0x180007c56  sub     rsp, 20h
0x180007c5a  mov     rax, rdx
0x180007c5d  mov     [rsp+28h+newString], 0
0x180007c66  mov     rbx, rcx
0x180007c69  lea     rdx, [rsp+28h+newString]; newString
0x180007c6e  mov     rcx, [rax]; string
0x180007c71  call    cs:__imp_WindowsDuplicateString
0x180007c77  mov     edi, eax
0x180007c79  test    eax, eax
0x180007c7b  js      short loc_180007C8E
0x180007c7d  mov     rdx, [rsp+28h+newString]
0x180007c82  mov     rcx, [rbx]; string
0x180007c85  mov     [rbx], rdx
0x180007c88  call    cs:__imp_WindowsDeleteString
0x180007c8e  mov     rbx, [rsp+28h+arg_8]
0x180007c93  mov     eax, edi
0x180007c95  add     rsp, 20h
0x180007c99  pop     rdi
0x180007c9a  retn
```
