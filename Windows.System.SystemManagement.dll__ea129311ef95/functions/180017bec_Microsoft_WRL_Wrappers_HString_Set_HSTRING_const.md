# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x180017bec`
- end: `0x180017c32`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017df0`
- `0x18001b854`

## callees

- `0x180017bec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180017c21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180017c21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017c0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017c0e`

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
0x180017bec  mov     [rsp+arg_0], rbx
0x180017bf1  push    rdi
0x180017bf2  sub     rsp, 20h
0x180017bf6  mov     rbx, rcx
0x180017bf9  mov     rdi, rdx
0x180017bfc  mov     rcx, [rdx]
0x180017bff  test    rcx, rcx
0x180017c02  jz      short loc_180017C0B
0x180017c04  xor     eax, eax
0x180017c06  cmp     rcx, [rbx]
0x180017c09  jz      short loc_180017C27
0x180017c0b  mov     rcx, [rbx]; string
0x180017c0e  call    cs:__imp_WindowsDeleteString
0x180017c14  mov     qword ptr [rbx], 0
0x180017c1b  mov     rdx, rbx; newString
0x180017c1e  mov     rcx, [rdi]; string
0x180017c21  call    cs:__imp_WindowsDuplicateString
0x180017c27  mov     rbx, [rsp+28h+arg_0]
0x180017c2c  add     rsp, 20h
0x180017c30  pop     rdi
0x180017c31  retn
```
