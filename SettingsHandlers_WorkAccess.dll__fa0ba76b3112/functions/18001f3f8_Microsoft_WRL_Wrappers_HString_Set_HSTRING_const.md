# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x18001f3f8`
- end: `0x18001f44b`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `83`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b108`

## callees

- `0x18001f3f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001f433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001f433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f41a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f41a`

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
0x18001f3f8  mov     [rsp+arg_0], rbx
0x18001f3fd  push    rdi
0x18001f3fe  sub     rsp, 20h
0x18001f402  mov     rbx, rcx
0x18001f405  mov     rdi, rdx
0x18001f408  mov     rcx, [rdx]
0x18001f40b  test    rcx, rcx
0x18001f40e  jz      short loc_18001F417
0x18001f410  xor     eax, eax
0x18001f412  cmp     rcx, [rbx]
0x18001f415  jz      short loc_18001F43F
0x18001f417  mov     rcx, [rbx]; string
0x18001f41a  call    cs:__imp_WindowsDeleteString
0x18001f421  nop     dword ptr [rax+rax+00h]
0x18001f426  mov     qword ptr [rbx], 0
0x18001f42d  mov     rdx, rbx; newString
0x18001f430  mov     rcx, [rdi]; string
0x18001f433  call    cs:__imp_WindowsDuplicateString
0x18001f43a  nop     dword ptr [rax+rax+00h]
0x18001f43f  mov     rbx, [rsp+28h+arg_0]
0x18001f444  add     rsp, 20h
0x18001f448  pop     rdi
0x18001f449  retn
```
