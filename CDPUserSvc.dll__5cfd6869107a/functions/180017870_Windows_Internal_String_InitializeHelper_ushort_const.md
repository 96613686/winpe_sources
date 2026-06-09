# Windows::Internal::String::_InitializeHelper(ushort const *)

- ea: `0x180017870`
- end: `0x1800178e1`
- name: `?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z`
- size: `113`
- prototype: `int(Windows::Internal::String *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180017618`
- `0x180017810`

## callees

- `0x180017870`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800178c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800178c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800178ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800178ab`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::_InitializeHelper(HSTRING *this, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rdx
  HRESULT v5; // ebx
  HSTRING v6; // rcx
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  string = 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( v3 > 0xFFFFFFFF )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    v5 = WindowsCreateString(a2, v3, &string);
    if ( v5 >= 0 )
    {
      v6 = *this;
      *this = string;
      WindowsDeleteString(v6);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017870  mov     [rsp+arg_0], rbx
0x180017875  mov     [rsp+arg_8], rsi
0x18001787a  push    rdi
0x18001787b  sub     rsp, 20h
0x18001787f  xor     esi, esi
0x180017881  mov     rax, rdx
0x180017884  mov     [rsp+28h+string], rsi
0x180017889  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001788d  mov     rdi, rcx
0x180017890  inc     rdx; length
0x180017893  cmp     [rax+rdx*2], si
0x180017897  jnz     short loc_180017890
0x180017899  mov     ecx, 0FFFFFFFFh
0x18001789e  cmp     rdx, rcx
0x1800178a1  ja      short loc_1800178CA
0x1800178a3  lea     r8, [rsp+28h+string]; string
0x1800178a8  mov     rcx, rax; sourceString
0x1800178ab  call    cs:__imp_WindowsCreateString
0x1800178b1  mov     ebx, eax
0x1800178b3  test    eax, eax
0x1800178b5  js      short loc_1800178CF
0x1800178b7  mov     rax, [rsp+28h+string]
0x1800178bc  mov     rcx, [rdi]; string
0x1800178bf  mov     [rdi], rax
0x1800178c2  call    cs:__imp_WindowsDeleteString
0x1800178c8  jmp     short loc_1800178CF
0x1800178ca  mov     ebx, 80070216h
0x1800178cf  mov     rsi, [rsp+28h+arg_8]
0x1800178d4  mov     eax, ebx
0x1800178d6  mov     rbx, [rsp+28h+arg_0]
0x1800178db  add     rsp, 20h
0x1800178df  pop     rdi
0x1800178e0  retn
```
