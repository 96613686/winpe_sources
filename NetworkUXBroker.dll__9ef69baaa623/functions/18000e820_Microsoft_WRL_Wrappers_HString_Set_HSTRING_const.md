# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x18000e820`
- end: `0x18000e866`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f6c0`
- `0x18000f730`
- `0x18001f650`
- `0x18001f7b0`
- `0x18001f970`
- `0x18001fa2c`
- `0x18001fbd8`

## callees

- `0x18000e820`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000e855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000e855`

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
0x18000e820  mov     [rsp+arg_0], rbx
0x18000e825  push    rdi
0x18000e826  sub     rsp, 20h
0x18000e82a  mov     rbx, rcx
0x18000e82d  mov     rdi, rdx
0x18000e830  mov     rcx, [rdx]
0x18000e833  test    rcx, rcx
0x18000e836  jz      short loc_18000E83F
0x18000e838  xor     eax, eax
0x18000e83a  cmp     rcx, [rbx]
0x18000e83d  jz      short loc_18000E85B
0x18000e83f  mov     rcx, [rbx]; string
0x18000e842  call    cs:__imp_WindowsDeleteString
0x18000e848  mov     qword ptr [rbx], 0
0x18000e84f  mov     rdx, rbx; newString
0x18000e852  mov     rcx, [rdi]; string
0x18000e855  call    cs:__imp_WindowsDuplicateString
0x18000e85b  mov     rbx, [rsp+28h+arg_0]
0x18000e860  add     rsp, 20h
0x18000e864  pop     rdi
0x18000e865  retn
```
