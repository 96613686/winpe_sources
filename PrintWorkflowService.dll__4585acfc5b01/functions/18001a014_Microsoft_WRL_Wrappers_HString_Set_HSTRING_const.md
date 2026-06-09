# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x18001a014`
- end: `0x18001a05a`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019ec8`

## callees

- `0x18001a014`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001a049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001a049`

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
0x18001a014  mov     [rsp+arg_0], rbx
0x18001a019  push    rdi
0x18001a01a  sub     rsp, 20h
0x18001a01e  mov     rbx, rcx
0x18001a021  mov     rdi, rdx
0x18001a024  mov     rcx, [rdx]
0x18001a027  test    rcx, rcx
0x18001a02a  jz      short loc_18001A033
0x18001a02c  xor     eax, eax
0x18001a02e  cmp     rcx, [rbx]
0x18001a031  jz      short loc_18001A04F
0x18001a033  mov     rcx, [rbx]; string
0x18001a036  call    cs:__imp_WindowsDeleteString
0x18001a03c  mov     qword ptr [rbx], 0
0x18001a043  mov     rdx, rbx; newString
0x18001a046  mov     rcx, [rdi]; string
0x18001a049  call    cs:__imp_WindowsDuplicateString
0x18001a04f  mov     rbx, [rsp+28h+arg_0]
0x18001a054  add     rsp, 20h
0x18001a058  pop     rdi
0x18001a059  retn
```
