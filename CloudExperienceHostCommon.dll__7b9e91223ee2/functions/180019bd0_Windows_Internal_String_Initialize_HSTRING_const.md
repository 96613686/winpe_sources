# Windows::Internal::String::Initialize(HSTRING__ * const &)

- ea: `0x180019bd0`
- end: `0x180019c1b`
- name: `?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(Windows::Internal::String *__hidden this, HSTRING *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180014a50`
- `0x180019a90`
- `0x1800b78c0`

## callees

- `0x180019bd0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180019bf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180019bf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019c08`

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
0x180019bd0  mov     [rsp+arg_8], rbx
0x180019bd5  push    rdi
0x180019bd6  sub     rsp, 20h
0x180019bda  mov     rax, rdx
0x180019bdd  mov     [rsp+28h+newString], 0
0x180019be6  mov     rbx, rcx
0x180019be9  lea     rdx, [rsp+28h+newString]; newString
0x180019bee  mov     rcx, [rax]; string
0x180019bf1  call    cs:__imp_WindowsDuplicateString
0x180019bf7  mov     edi, eax
0x180019bf9  test    eax, eax
0x180019bfb  js      short loc_180019C0E
0x180019bfd  mov     rdx, [rsp+28h+newString]
0x180019c02  mov     rcx, [rbx]; string
0x180019c05  mov     [rbx], rdx
0x180019c08  call    cs:__imp_WindowsDeleteString
0x180019c0e  mov     rbx, [rsp+28h+arg_8]
0x180019c13  mov     eax, edi
0x180019c15  add     rsp, 20h
0x180019c19  pop     rdi
0x180019c1a  retn
```
