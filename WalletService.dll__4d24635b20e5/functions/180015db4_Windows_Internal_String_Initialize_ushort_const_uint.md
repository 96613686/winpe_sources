# Windows::Internal::String::Initialize(ushort const *,uint)

- ea: `0x180015db4`
- end: `0x180015e04`
- name: `?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z`
- size: `80`
- prototype: `int(Windows::Internal::String *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014d28`

## callees

- `0x180015db4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015df1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015df1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180015dda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180015dda`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize(HSTRING *this, const unsigned __int16 *a2, UINT32 a3)
{
  HRESULT v4; // edi
  HSTRING v5; // rcx
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  string = 0;
  v4 = WindowsCreateString(a2, a3, &string);
  if ( v4 >= 0 )
  {
    v5 = *this;
    *this = string;
    WindowsDeleteString(v5);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015db4  mov     [rsp+arg_8], rbx
0x180015db9  push    rdi
0x180015dba  sub     rsp, 20h
0x180015dbe  mov     eax, r8d
0x180015dc1  mov     [rsp+28h+string], 0
0x180015dca  mov     r9, rdx
0x180015dcd  lea     r8, [rsp+28h+string]; string
0x180015dd2  mov     rbx, rcx
0x180015dd5  mov     edx, eax; length
0x180015dd7  mov     rcx, r9; sourceString
0x180015dda  call    cs:__imp_WindowsCreateString
0x180015de0  mov     edi, eax
0x180015de2  test    eax, eax
0x180015de4  js      short loc_180015DF7
0x180015de6  mov     rdx, [rsp+28h+string]
0x180015deb  mov     rcx, [rbx]; string
0x180015dee  mov     [rbx], rdx
0x180015df1  call    cs:__imp_WindowsDeleteString
0x180015df7  mov     rbx, [rsp+28h+arg_8]
0x180015dfc  mov     eax, edi
0x180015dfe  add     rsp, 20h
0x180015e02  pop     rdi
0x180015e03  retn
```
