# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x180010c18`
- end: `0x180010c5e`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000af40`
- `0x18000cad0`
- `0x180015978`
- `0x180017e20`
- `0x1800197b8`
- `0x18001ac20`
- `0x1800219a0`

## callees

- `0x180010c18`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010c3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180010c4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180010c4d`

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
0x180010c18  mov     [rsp+arg_0], rbx
0x180010c1d  push    rdi
0x180010c1e  sub     rsp, 20h
0x180010c22  mov     rbx, rcx
0x180010c25  mov     rdi, rdx
0x180010c28  mov     rcx, [rdx]
0x180010c2b  test    rcx, rcx
0x180010c2e  jz      short loc_180010C37
0x180010c30  xor     eax, eax
0x180010c32  cmp     rcx, [rbx]
0x180010c35  jz      short loc_180010C53
0x180010c37  mov     rcx, [rbx]; string
0x180010c3a  call    cs:__imp_WindowsDeleteString
0x180010c40  mov     qword ptr [rbx], 0
0x180010c47  mov     rdx, rbx; newString
0x180010c4a  mov     rcx, [rdi]; string
0x180010c4d  call    cs:__imp_WindowsDuplicateString
0x180010c53  mov     rbx, [rsp+28h+arg_0]
0x180010c58  add     rsp, 20h
0x180010c5c  pop     rdi
0x180010c5d  retn
```
