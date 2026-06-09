# Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18002b860`
- end: `0x18002b8ef`
- name: `??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z`
- size: `143`
- prototype: `__int64 __fastcall(HSTRING *string)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027d50`

## callees

- `0x18002b860`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b8bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b8bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002b8ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002b8d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002b8ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002b8d2`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(HSTRING *string, const WCHAR **a2)
{
  const WCHAR *v2; // rdi
  unsigned __int64 v4; // rbx

  v2 = *a2;
  if ( *a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( v2[v4] );
    if ( v4 > 0xFFFFFFFF )
    {
      return -2147024362;
    }
    else
    {
      WindowsDeleteString(*string);
      *string = 0;
      return WindowsCreateString(v2, v4, string);
    }
  }
  else
  {
    WindowsDeleteString(*string);
    *string = 0;
    return WindowsCreateString(&Src, 0, string);
  }
}

```

## disassembly

```asm
0x18002b860  mov     [rsp+arg_8], rsi
0x18002b865  push    rdi
0x18002b866  sub     rsp, 20h
0x18002b86a  mov     rdi, [rdx]
0x18002b86d  mov     rsi, rcx
0x18002b870  test    rdi, rdi
0x18002b873  jz      short loc_18002B8B8
0x18002b875  mov     [rsp+28h+arg_0], rbx
0x18002b87a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002b881  inc     rbx
0x18002b884  cmp     word ptr [rdi+rbx*2], 0
0x18002b889  jnz     short loc_18002B881
0x18002b88b  mov     eax, 0FFFFFFFFh
0x18002b890  cmp     rbx, rax
0x18002b893  ja      short loc_18002B8E3
0x18002b895  mov     rcx, [rcx]; string
0x18002b898  call    cs:__imp_WindowsDeleteString
0x18002b89e  xor     eax, eax
0x18002b8a0  mov     edx, ebx; length
0x18002b8a2  mov     r8, rsi; string
0x18002b8a5  mov     [rsi], rax
0x18002b8a8  mov     rcx, rdi; sourceString
0x18002b8ab  call    cs:__imp_WindowsCreateString
0x18002b8b1  mov     rbx, [rsp+28h+arg_0]
0x18002b8b6  jmp     short loc_18002B8D8
0x18002b8b8  mov     rcx, [rcx]; string
0x18002b8bb  call    cs:__imp_WindowsDeleteString
0x18002b8c1  xor     eax, eax
0x18002b8c3  lea     rcx, Src; sourceString
0x18002b8ca  mov     r8, rsi; string
0x18002b8cd  mov     [rsi], rax
0x18002b8d0  xor     edx, edx; length
0x18002b8d2  call    cs:__imp_WindowsCreateString
0x18002b8d8  mov     rsi, [rsp+28h+arg_8]
0x18002b8dd  add     rsp, 20h
0x18002b8e1  pop     rdi
0x18002b8e2  retn
0x18002b8e3  mov     rbx, [rsp+28h+arg_0]
0x18002b8e8  mov     eax, 80070216h
0x18002b8ed  jmp     short loc_18002B8D8
```
