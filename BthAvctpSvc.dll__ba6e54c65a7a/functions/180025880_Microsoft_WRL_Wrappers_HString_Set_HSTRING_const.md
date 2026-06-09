# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x180025880`
- end: `0x1800258c6`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180025380`
- `0x1800255c4`

## callees

- `0x180025880`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800258a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800258a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800258b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800258b5`

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
0x180025880  mov     [rsp+arg_0], rbx
0x180025885  push    rdi
0x180025886  sub     rsp, 20h
0x18002588a  mov     rbx, rcx
0x18002588d  mov     rdi, rdx
0x180025890  mov     rcx, [rdx]
0x180025893  test    rcx, rcx
0x180025896  jz      short loc_18002589F
0x180025898  xor     eax, eax
0x18002589a  cmp     rcx, [rbx]
0x18002589d  jz      short loc_1800258BB
0x18002589f  mov     rcx, [rbx]; string
0x1800258a2  call    cs:__imp_WindowsDeleteString
0x1800258a8  mov     qword ptr [rbx], 0
0x1800258af  mov     rdx, rbx; newString
0x1800258b2  mov     rcx, [rdi]; string
0x1800258b5  call    cs:__imp_WindowsDuplicateString
0x1800258bb  mov     rbx, [rsp+28h+arg_0]
0x1800258c0  add     rsp, 20h
0x1800258c4  pop     rdi
0x1800258c5  retn
```
