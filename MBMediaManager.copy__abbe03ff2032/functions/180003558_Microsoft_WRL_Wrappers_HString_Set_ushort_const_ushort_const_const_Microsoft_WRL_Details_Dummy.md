# Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180003558`
- end: `0x1800035c3`
- name: `??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z`
- size: `107`
- prototype: `__int64 __fastcall(HSTRING *string)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800028f8`
- `0x180027b08`
- `0x18003b290`
- `0x18003b4a0`
- `0x18003b54c`

## callees

- `0x180003558`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000359f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000359f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800035b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800035b4`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(HSTRING *string, const WCHAR **a2)
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
    v6 = &sourceString;
  }
  *string = 0;
  return WindowsCreateString(v6, v5, string);
}

```

## disassembly

```asm
0x180003558  push    rbx
0x18000355a  push    rbp
0x18000355b  push    rsi
0x18000355c  push    rdi
0x18000355d  sub     rsp, 28h
0x180003561  mov     rsi, [rdx]
0x180003564  xor     ebp, ebp
0x180003566  mov     rdi, rcx
0x180003569  test    rsi, rsi
0x18000356c  jz      short loc_18000359C
0x18000356e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003572  inc     rbx
0x180003575  cmp     [rsi+rbx*2], bp
0x180003579  jnz     short loc_180003572
0x18000357b  mov     eax, 0FFFFFFFFh
0x180003580  cmp     rbx, rax
0x180003583  ja      short loc_180003595
0x180003585  mov     rcx, [rcx]; string
0x180003588  call    cs:__imp_WindowsDeleteString
0x18000358e  mov     edx, ebx
0x180003590  mov     rcx, rsi
0x180003593  jmp     short loc_1800035AE
0x180003595  mov     eax, 80070216h
0x18000359a  jmp     short loc_1800035BA
0x18000359c  mov     rcx, [rcx]; string
0x18000359f  call    cs:__imp_WindowsDeleteString
0x1800035a5  xor     edx, edx; length
0x1800035a7  lea     rcx, sourceString; sourceString
0x1800035ae  mov     r8, rdi; string
0x1800035b1  mov     [rdi], rbp
0x1800035b4  call    cs:__imp_WindowsCreateString
0x1800035ba  add     rsp, 28h
0x1800035be  pop     rdi
0x1800035bf  pop     rsi
0x1800035c0  pop     rbp
0x1800035c1  pop     rbx
0x1800035c2  retn
```
