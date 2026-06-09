# CRemoteTextTextUpdatingEventArgs::get_NewText(HSTRING__ * *)

- ea: `0x1800303b0`
- end: `0x18003041f`
- name: `?get_NewText@CRemoteTextTextUpdatingEventArgs@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(CRemoteTextTextUpdatingEventArgs *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800303b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800303d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003040c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800303d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003040c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800303ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800303ea`

## pseudocode

```c
__int64 __fastcall CRemoteTextTextUpdatingEventArgs::get_NewText(CRemoteTextTextUpdatingEventArgs *this, HSTRING *a2)
{
  HSTRING v3; // rbx
  HRESULT v4; // ebx
  HSTRING v5; // rdx
  HSTRING v6; // rcx
  HSTRING newString; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = (HSTRING)*((_QWORD *)this + 11);
  newString = 0;
  WindowsDeleteString(0);
  newString = 0;
  v4 = WindowsDuplicateString(v3, &newString);
  if ( v4 < 0 )
  {
    v6 = newString;
  }
  else
  {
    v5 = newString;
    v6 = 0;
    newString = 0;
    *a2 = v5;
  }
  WindowsDeleteString(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800303b0  mov     [rsp+arg_8], rbx
0x1800303b5  push    rdi
0x1800303b6  sub     rsp, 20h
0x1800303ba  mov     qword ptr [rdx], 0
0x1800303c1  mov     rdi, rdx
0x1800303c4  mov     rbx, [rcx+58h]
0x1800303c8  xor     ecx, ecx; string
0x1800303ca  mov     [rsp+28h+newString], 0
0x1800303d3  call    cs:__imp_WindowsDeleteString
0x1800303d9  lea     rdx, [rsp+28h+newString]; newString
0x1800303de  mov     [rsp+28h+newString], 0
0x1800303e7  mov     rcx, rbx; string
0x1800303ea  call    cs:__imp_WindowsDuplicateString
0x1800303f0  mov     ebx, eax
0x1800303f2  test    eax, eax
0x1800303f4  js      short loc_180030407
0x1800303f6  mov     rdx, [rsp+28h+newString]
0x1800303fb  xor     ecx, ecx
0x1800303fd  mov     [rsp+28h+newString], rcx
0x180030402  mov     [rdi], rdx
0x180030405  jmp     short loc_18003040C
0x180030407  mov     rcx, [rsp+28h+newString]; string
0x18003040c  call    cs:__imp_WindowsDeleteString
0x180030412  mov     eax, ebx
0x180030414  mov     rbx, [rsp+28h+arg_8]
0x180030419  add     rsp, 20h
0x18003041d  pop     rdi
0x18003041e  retn
```
