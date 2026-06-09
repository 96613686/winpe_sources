# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x18004d020`
- end: `0x18004d066`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001385c`
- `0x180013d50`
- `0x18004b760`
- `0x18004ff00`
- `0x180051988`
- `0x1800529ac`
- `0x180054430`

## callees

- `0x18004d020`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004d055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004d055`

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
0x18004d020  mov     [rsp+arg_0], rbx
0x18004d025  push    rdi
0x18004d026  sub     rsp, 20h
0x18004d02a  mov     rbx, rcx
0x18004d02d  mov     rdi, rdx
0x18004d030  mov     rcx, [rdx]
0x18004d033  test    rcx, rcx
0x18004d036  jz      short loc_18004D03F
0x18004d038  xor     eax, eax
0x18004d03a  cmp     rcx, [rbx]
0x18004d03d  jz      short loc_18004D05B
0x18004d03f  mov     rcx, [rbx]; string
0x18004d042  call    cs:__imp_WindowsDeleteString
0x18004d048  mov     qword ptr [rbx], 0
0x18004d04f  mov     rdx, rbx; newString
0x18004d052  mov     rcx, [rdi]; string
0x18004d055  call    cs:__imp_WindowsDuplicateString
0x18004d05b  mov     rbx, [rsp+28h+arg_0]
0x18004d060  add     rsp, 20h
0x18004d064  pop     rdi
0x18004d065  retn
```
