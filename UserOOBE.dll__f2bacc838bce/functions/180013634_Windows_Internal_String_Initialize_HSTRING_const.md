# Windows::Internal::String::Initialize(HSTRING__ * const &)

- ea: `0x180013634`
- end: `0x18001367f`
- name: `?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(Windows::Internal::String *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014604`
- `0x180046eb8`

## callees

- `0x180013634`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001366c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001366c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180013655`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180013655`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize(HSTRING *this, HSTRING *a2)
{
  HRESULT v3; // edi
  HSTRING v4; // rcx
  HSTRING newString; // [rsp+30h] [rbp+8h] BYREF

  newString = 0;
  v3 = WindowsDuplicateString(*a2, &newString);
  if ( v3 >= 0 )
  {
    v4 = *this;
    *this = newString;
    WindowsDeleteString(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013634  mov     [rsp+arg_8], rbx
0x180013639  push    rdi
0x18001363a  sub     rsp, 20h
0x18001363e  mov     rax, rdx
0x180013641  mov     [rsp+28h+newString], 0
0x18001364a  mov     rbx, rcx
0x18001364d  lea     rdx, [rsp+28h+newString]; newString
0x180013652  mov     rcx, [rax]; string
0x180013655  call    cs:__imp_WindowsDuplicateString
0x18001365b  mov     edi, eax
0x18001365d  test    eax, eax
0x18001365f  js      short loc_180013672
0x180013661  mov     rdx, [rsp+28h+newString]
0x180013666  mov     rcx, [rbx]; string
0x180013669  mov     [rbx], rdx
0x18001366c  call    cs:__imp_WindowsDeleteString
0x180013672  mov     rbx, [rsp+28h+arg_8]
0x180013677  mov     eax, edi
0x180013679  add     rsp, 20h
0x18001367d  pop     rdi
0x18001367e  retn
```
