# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x180035ee8`
- end: `0x180035f2e`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18005537c`

## callees

- `0x180035ee8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180035f1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180035f1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035f0a`

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
0x180035ee8  mov     [rsp+arg_0], rbx
0x180035eed  push    rdi
0x180035eee  sub     rsp, 20h
0x180035ef2  mov     rbx, rcx
0x180035ef5  mov     rdi, rdx
0x180035ef8  mov     rcx, [rdx]
0x180035efb  test    rcx, rcx
0x180035efe  jz      short loc_180035F07
0x180035f00  xor     eax, eax
0x180035f02  cmp     rcx, [rbx]
0x180035f05  jz      short loc_180035F23
0x180035f07  mov     rcx, [rbx]; string
0x180035f0a  call    cs:__imp_WindowsDeleteString
0x180035f10  mov     qword ptr [rbx], 0
0x180035f17  mov     rdx, rbx; newString
0x180035f1a  mov     rcx, [rdi]; string
0x180035f1d  call    cs:__imp_WindowsDuplicateString
0x180035f23  mov     rbx, [rsp+28h+arg_0]
0x180035f28  add     rsp, 20h
0x180035f2c  pop     rdi
0x180035f2d  retn
```
