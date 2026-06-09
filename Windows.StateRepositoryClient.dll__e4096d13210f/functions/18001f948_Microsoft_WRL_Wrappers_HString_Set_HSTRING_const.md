# Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)

- ea: `0x18001f948`
- end: `0x18001f98e`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HSTRING *newString, HSTRING *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a02c`
- `0x18001a6ac`
- `0x18001f890`
- `0x180020db0`

## callees

- `0x18001f948`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f96a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f96a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001f97d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001f97d`

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
0x18001f948  mov     [rsp+arg_0], rbx
0x18001f94d  push    rdi
0x18001f94e  sub     rsp, 20h
0x18001f952  mov     rbx, rcx
0x18001f955  mov     rdi, rdx
0x18001f958  mov     rcx, [rdx]
0x18001f95b  test    rcx, rcx
0x18001f95e  jz      short loc_18001F967
0x18001f960  xor     eax, eax
0x18001f962  cmp     rcx, [rbx]
0x18001f965  jz      short loc_18001F983
0x18001f967  mov     rcx, [rbx]; string
0x18001f96a  call    cs:__imp_WindowsDeleteString
0x18001f970  mov     qword ptr [rbx], 0
0x18001f977  mov     rdx, rbx; newString
0x18001f97a  mov     rcx, [rdi]; string
0x18001f97d  call    cs:__imp_WindowsDuplicateString
0x18001f983  mov     rbx, [rsp+28h+arg_0]
0x18001f988  add     rsp, 20h
0x18001f98c  pop     rdi
0x18001f98d  retn
```
