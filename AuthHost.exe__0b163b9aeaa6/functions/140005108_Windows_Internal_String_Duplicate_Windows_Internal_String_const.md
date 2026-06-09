# Windows::Internal::String::Duplicate(Windows::Internal::String const &)

- ea: `0x140005108`
- end: `0x140005153`
- name: `?Duplicate@String@Internal@Windows@@QEAAJAEBV123@@Z`
- size: `75`
- prototype: `__int64 __fastcall(Windows::Internal::String *__hidden this, const struct Windows::Internal::String *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005dbc`

## callees

- `0x140005108`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140005140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140005140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x140005129`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x140005129`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Duplicate(HSTRING *this, HSTRING *a2)
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
0x140005108  mov     [rsp+arg_8], rbx
0x14000510d  push    rdi
0x14000510e  sub     rsp, 20h
0x140005112  mov     rax, rdx
0x140005115  mov     [rsp+28h+newString], 0
0x14000511e  mov     rbx, rcx
0x140005121  lea     rdx, [rsp+28h+newString]; newString
0x140005126  mov     rcx, [rax]; string
0x140005129  call    cs:__imp_WindowsDuplicateString
0x14000512f  mov     edi, eax
0x140005131  test    eax, eax
0x140005133  js      short loc_140005146
0x140005135  mov     rdx, [rsp+28h+newString]
0x14000513a  mov     rcx, [rbx]; string
0x14000513d  mov     [rbx], rdx
0x140005140  call    cs:__imp_WindowsDeleteString
0x140005146  mov     rbx, [rsp+28h+arg_8]
0x14000514b  mov     eax, edi
0x14000514d  add     rsp, 20h
0x140005151  pop     rdi
0x140005152  retn
```
