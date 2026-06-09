# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x180018598`
- end: `0x1800185de`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800154f4`
- `0x180019870`

## callees

- `0x180018598`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800185cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800185cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185ba`

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
0x180018598  mov     [rsp+arg_0], rbx
0x18001859d  push    rdi
0x18001859e  sub     rsp, 20h
0x1800185a2  mov     rbx, rcx
0x1800185a5  mov     rdi, rdx
0x1800185a8  mov     rcx, [rdx]
0x1800185ab  test    rcx, rcx
0x1800185ae  jz      short loc_1800185B7
0x1800185b0  xor     eax, eax
0x1800185b2  cmp     rcx, [rbx]
0x1800185b5  jz      short loc_1800185D3
0x1800185b7  mov     rcx, [rbx]; string
0x1800185ba  call    cs:__imp_WindowsDeleteString
0x1800185c0  mov     qword ptr [rbx], 0
0x1800185c7  mov     rdx, rbx; newString
0x1800185ca  mov     rcx, [rdi]; string
0x1800185cd  call    cs:__imp_WindowsDuplicateString
0x1800185d3  mov     rbx, [rsp+28h+arg_0]
0x1800185d8  add     rsp, 20h
0x1800185dc  pop     rdi
0x1800185dd  retn
```
