# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x1800165e4`
- end: `0x18001662a`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `21`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015b70`
- `0x18001667c`
- `0x18001b630`
- `0x18001b6c0`
- `0x18001b7b0`
- `0x180037ce8`
- `0x180037eec`
- `0x18003be64`
- `0x18003bfbc`
- `0x18003c084`
- `0x18003c160`
- `0x18003dd94`
- `0x18003f160`
- `0x180040384`
- `0x18004a9e0`
- `0x180051774`
- `0x180056450`
- `0x180056570`
- `0x1800640f8`
- `0x180066c70`
- `0x180066d4c`

## callees

- `0x1800165e4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180016619`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180016619`

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
0x1800165e4  mov     [rsp+arg_0], rbx
0x1800165e9  push    rdi
0x1800165ea  sub     rsp, 20h
0x1800165ee  mov     rbx, rcx
0x1800165f1  mov     rdi, rdx
0x1800165f4  mov     rcx, [rdx]
0x1800165f7  test    rcx, rcx
0x1800165fa  jz      short loc_180016603
0x1800165fc  xor     eax, eax
0x1800165fe  cmp     rcx, [rbx]
0x180016601  jz      short loc_18001661F
0x180016603  mov     rcx, [rbx]; string
0x180016606  call    cs:__imp_WindowsDeleteString
0x18001660c  mov     qword ptr [rbx], 0
0x180016613  mov     rdx, rbx; newString
0x180016616  mov     rcx, [rdi]; string
0x180016619  call    cs:__imp_WindowsDuplicateString
0x18001661f  mov     rbx, [rsp+28h+arg_0]
0x180016624  add     rsp, 20h
0x180016628  pop     rdi
0x180016629  retn
```
