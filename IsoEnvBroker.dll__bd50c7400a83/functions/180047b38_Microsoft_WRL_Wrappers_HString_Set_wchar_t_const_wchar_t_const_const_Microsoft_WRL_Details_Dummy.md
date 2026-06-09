# Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180047b38`
- end: `0x180047ba3`
- name: `??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z`
- size: `107`
- prototype: `HRESULT __fastcall(HSTRING *string, const WCHAR **)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003c79c`
- `0x180047e00`
- `0x180048000`
- `0x18004bd10`
- `0x180055450`
- `0x18005ebf0`
- `0x18005ed84`

## callees

- `0x180047b38`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047b7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047b7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180047b94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180047b94`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(HSTRING *string, const WCHAR **a2)
{
  const WCHAR *v2; // rsi
  unsigned __int64 v4; // rbx
  UINT32 v5; // edx
  const WCHAR *v6; // rcx

  v2 = *a2;
  if ( *a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( v2[v4] );
    if ( v4 > 0xFFFFFFFF )
      return -2147024362;
    WindowsDeleteString(*string);
    v5 = v4;
    v6 = v2;
  }
  else
  {
    WindowsDeleteString(*string);
    v5 = 0;
    v6 = &word_180096C4C;
  }
  *string = 0;
  return WindowsCreateString(v6, v5, string);
}

```

## disassembly

```asm
0x180047b38  push    rbx
0x180047b3a  push    rbp
0x180047b3b  push    rsi
0x180047b3c  push    rdi
0x180047b3d  sub     rsp, 28h
0x180047b41  mov     rsi, [rdx]
0x180047b44  xor     ebp, ebp
0x180047b46  mov     rdi, rcx
0x180047b49  test    rsi, rsi
0x180047b4c  jz      short loc_180047B7C
0x180047b4e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180047b52  inc     rbx
0x180047b55  cmp     [rsi+rbx*2], bp
0x180047b59  jnz     short loc_180047B52
0x180047b5b  mov     eax, 0FFFFFFFFh
0x180047b60  cmp     rbx, rax
0x180047b63  ja      short loc_180047B75
0x180047b65  mov     rcx, [rcx]; string
0x180047b68  call    cs:__imp_WindowsDeleteString
0x180047b6e  mov     edx, ebx
0x180047b70  mov     rcx, rsi
0x180047b73  jmp     short loc_180047B8E
0x180047b75  mov     eax, 80070216h
0x180047b7a  jmp     short loc_180047B9A
0x180047b7c  mov     rcx, [rcx]; string
0x180047b7f  call    cs:__imp_WindowsDeleteString
0x180047b85  xor     edx, edx; length
0x180047b87  lea     rcx, word_180096C4C; sourceString
0x180047b8e  mov     r8, rdi; string
0x180047b91  mov     [rdi], rbp
0x180047b94  call    cs:__imp_WindowsCreateString
0x180047b9a  add     rsp, 28h
0x180047b9e  pop     rdi
0x180047b9f  pop     rsi
0x180047ba0  pop     rbp
0x180047ba1  pop     rbx
0x180047ba2  retn
```
