# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x18002e2b0`
- end: `0x18002e2f6`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002f25c`
- `0x180030ec8`
- `0x180032d04`
- `0x1800374f0`
- `0x1800462a0`
- `0x18004640c`
- `0x1800483dc`
- `0x1800485c8`
- `0x180048b00`
- `0x180048ee8`

## callees

- `0x18002e2b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002e2e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002e2e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e2d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e2d2`

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
0x18002e2b0  mov     [rsp+arg_0], rbx
0x18002e2b5  push    rdi
0x18002e2b6  sub     rsp, 20h
0x18002e2ba  mov     rbx, rcx
0x18002e2bd  mov     rdi, rdx
0x18002e2c0  mov     rcx, [rdx]
0x18002e2c3  test    rcx, rcx
0x18002e2c6  jz      short loc_18002E2CF
0x18002e2c8  xor     eax, eax
0x18002e2ca  cmp     rcx, [rbx]
0x18002e2cd  jz      short loc_18002E2EB
0x18002e2cf  mov     rcx, [rbx]; string
0x18002e2d2  call    cs:__imp_WindowsDeleteString
0x18002e2d8  mov     qword ptr [rbx], 0
0x18002e2df  mov     rdx, rbx; newString
0x18002e2e2  mov     rcx, [rdi]; string
0x18002e2e5  call    cs:__imp_WindowsDuplicateString
0x18002e2eb  mov     rbx, [rsp+28h+arg_0]
0x18002e2f0  add     rsp, 20h
0x18002e2f4  pop     rdi
0x18002e2f5  retn
```
