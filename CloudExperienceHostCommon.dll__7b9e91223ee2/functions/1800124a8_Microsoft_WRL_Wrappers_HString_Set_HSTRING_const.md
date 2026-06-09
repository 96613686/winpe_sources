# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x1800124a8`
- end: `0x1800124ee`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800109c8`
- `0x180011640`
- `0x180078608`
- `0x180079e78`
- `0x180099ee0`
- `0x18009f404`
- `0x18009f6dc`
- `0x1800c7be0`

## callees

- `0x1800124a8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800124dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800124dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124ca`

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
0x1800124a8  mov     [rsp+arg_0], rbx
0x1800124ad  push    rdi
0x1800124ae  sub     rsp, 20h
0x1800124b2  mov     rbx, rcx
0x1800124b5  mov     rdi, rdx
0x1800124b8  mov     rcx, [rdx]
0x1800124bb  test    rcx, rcx
0x1800124be  jz      short loc_1800124C7
0x1800124c0  xor     eax, eax
0x1800124c2  cmp     rcx, [rbx]
0x1800124c5  jz      short loc_1800124E3
0x1800124c7  mov     rcx, [rbx]; string
0x1800124ca  call    cs:__imp_WindowsDeleteString
0x1800124d0  mov     qword ptr [rbx], 0
0x1800124d7  mov     rdx, rbx; newString
0x1800124da  mov     rcx, [rdi]; string
0x1800124dd  call    cs:__imp_WindowsDuplicateString
0x1800124e3  mov     rbx, [rsp+28h+arg_0]
0x1800124e8  add     rsp, 20h
0x1800124ec  pop     rdi
0x1800124ed  retn
```
