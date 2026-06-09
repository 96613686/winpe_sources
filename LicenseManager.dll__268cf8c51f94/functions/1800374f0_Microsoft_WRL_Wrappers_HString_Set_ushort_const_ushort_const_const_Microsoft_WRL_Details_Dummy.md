# Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x1800374f0`
- end: `0x18003755b`
- name: `??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z`
- size: `107`
- prototype: `__int64 __fastcall(HSTRING *string)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d928`

## callees

- `0x1800374f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180037531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180037531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037520`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003754a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037520`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003754a`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(HSTRING *string, const WCHAR **a2)
{
  const WCHAR *v2; // rsi
  unsigned __int64 v4; // rbx
  UINT32 v5; // edx
  const WCHAR *v6; // rcx

  v2 = *a2;
  if ( !*a2 )
  {
    WindowsDeleteString(*string);
    v5 = 0;
    v6 = &LocaleName;
    goto LABEL_6;
  }
  v4 = -1;
  do
    ++v4;
  while ( v2[v4] );
  if ( v4 <= 0xFFFFFFFF )
  {
    WindowsDeleteString(*string);
    v5 = v4;
    v6 = v2;
LABEL_6:
    *string = 0;
    return WindowsCreateString(v6, v5, string);
  }
  return -2147024362;
}

```

## disassembly

```asm
0x1800374f0  push    rbx
0x1800374f2  push    rbp
0x1800374f3  push    rsi
0x1800374f4  push    rdi
0x1800374f5  sub     rsp, 28h
0x1800374f9  mov     rsi, [rdx]
0x1800374fc  xor     ebp, ebp
0x1800374fe  mov     rdi, rcx
0x180037501  test    rsi, rsi
0x180037504  jz      short loc_180037547
0x180037506  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003750a  inc     rbx
0x18003750d  cmp     [rsi+rbx*2], bp
0x180037511  jnz     short loc_18003750A
0x180037513  mov     eax, 0FFFFFFFFh
0x180037518  cmp     rbx, rax
0x18003751b  ja      short loc_180037540
0x18003751d  mov     rcx, [rcx]; string
0x180037520  call    cs:__imp_WindowsDeleteString
0x180037526  mov     edx, ebx; length
0x180037528  mov     rcx, rsi; sourceString
0x18003752b  mov     r8, rdi; string
0x18003752e  mov     [rdi], rbp
0x180037531  call    cs:__imp_WindowsCreateString
0x180037537  add     rsp, 28h
0x18003753b  pop     rdi
0x18003753c  pop     rsi
0x18003753d  pop     rbp
0x18003753e  pop     rbx
0x18003753f  retn
0x180037540  mov     eax, 80070216h
0x180037545  jmp     short loc_180037537
0x180037547  mov     rcx, [rcx]; string
0x18003754a  call    cs:__imp_WindowsDeleteString
0x180037550  xor     edx, edx
0x180037552  lea     rcx, LocaleName
0x180037559  jmp     short loc_18003752B
```
