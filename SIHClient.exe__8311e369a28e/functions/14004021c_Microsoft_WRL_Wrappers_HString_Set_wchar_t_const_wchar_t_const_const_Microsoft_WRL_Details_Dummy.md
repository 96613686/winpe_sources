# Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x14004021c`
- end: `0x14004029e`
- name: `??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z`
- size: `130`
- prototype: `HRESULT __fastcall(HSTRING *string, const WCHAR **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14003f96c`

## callees

- `0x14004021c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140040283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140040283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140040257`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14004026e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140040257`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14004026e`

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
    v6 = &OutputString;
  }
  *string = 0;
  return WindowsCreateString(v6, v5, string);
}

```

## disassembly

```asm
0x14004021c  mov     [rsp+arg_0], rbx
0x140040221  mov     [rsp+arg_8], rbp
0x140040226  mov     [rsp+arg_10], rsi
0x14004022b  push    rdi
0x14004022c  sub     rsp, 20h
0x140040230  mov     rsi, [rdx]
0x140040233  xor     ebp, ebp
0x140040235  mov     rdi, rcx
0x140040238  test    rsi, rsi
0x14004023b  jz      short loc_14004026B
0x14004023d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140040241  inc     rbx
0x140040244  cmp     [rsi+rbx*2], bp
0x140040248  jnz     short loc_140040241
0x14004024a  mov     eax, 0FFFFFFFFh
0x14004024f  cmp     rbx, rax
0x140040252  ja      short loc_140040264
0x140040254  mov     rcx, [rcx]; string
0x140040257  call    cs:__imp_WindowsDeleteString
0x14004025d  mov     edx, ebx
0x14004025f  mov     rcx, rsi
0x140040262  jmp     short loc_14004027D
0x140040264  mov     eax, 80070216h
0x140040269  jmp     short loc_140040289
0x14004026b  mov     rcx, [rcx]; string
0x14004026e  call    cs:__imp_WindowsDeleteString
0x140040274  xor     edx, edx; length
0x140040276  lea     rcx, OutputString; sourceString
0x14004027d  mov     r8, rdi; string
0x140040280  mov     [rdi], rbp
0x140040283  call    cs:__imp_WindowsCreateString
0x140040289  mov     rbx, [rsp+28h+arg_0]
0x14004028e  mov     rbp, [rsp+28h+arg_8]
0x140040293  mov     rsi, [rsp+28h+arg_10]
0x140040298  add     rsp, 20h
0x14004029c  pop     rdi
0x14004029d  retn
```
