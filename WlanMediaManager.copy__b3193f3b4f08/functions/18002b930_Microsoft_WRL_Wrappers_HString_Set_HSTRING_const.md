# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x18002b930`
- end: `0x18002b976`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002b980`
- `0x18002bab0`
- `0x18002bb00`
- `0x180036d60`
- `0x180046774`
- `0x18004d20c`
- `0x180059290`
- `0x180067890`
- `0x180069fac`

## callees

- `0x18002b930`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002b965`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002b965`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b952`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set(HSTRING *newString, HSTRING *a2)
{
  HRESULT result; // eax

  if ( !*a2 || (result = 0, *a2 != *newString) )
  {
    WindowsDeleteString(*newString);
    *newString = 0;
    return WindowsDuplicateString(*a2, newString);
  }
  return result;
}

```

## disassembly

```asm
0x18002b930  mov     [rsp+arg_0], rbx
0x18002b935  push    rdi
0x18002b936  sub     rsp, 20h
0x18002b93a  mov     rbx, rcx
0x18002b93d  mov     rdi, rdx
0x18002b940  mov     rcx, [rdx]
0x18002b943  test    rcx, rcx
0x18002b946  jz      short loc_18002B94F
0x18002b948  xor     eax, eax
0x18002b94a  cmp     rcx, [rbx]
0x18002b94d  jz      short loc_18002B96B
0x18002b94f  mov     rcx, [rbx]; string
0x18002b952  call    cs:__imp_WindowsDeleteString
0x18002b958  mov     qword ptr [rbx], 0
0x18002b95f  mov     rdx, rbx; newString
0x18002b962  mov     rcx, [rdi]; string
0x18002b965  call    cs:__imp_WindowsDuplicateString
0x18002b96b  mov     rbx, [rsp+28h+arg_0]
0x18002b970  add     rsp, 20h
0x18002b974  pop     rdi
0x18002b975  retn
```
