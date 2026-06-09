# Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)

- ea: `0x1800211e4`
- end: `0x180021279`
- name: `??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025080`

## callees

- `0x1800176bc`
- `0x1800211e4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180021236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180021236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021253`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize<unsigned short const *>(HSTRING *a1, __int64 *a2, char a3)
{
  __int64 v3; // r9
  unsigned __int64 v5; // rcx
  HRESULT v6; // ebx
  const WCHAR *v7; // r9
  HSTRING v8; // rcx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF
  UINT32 length; // [rsp+40h] [rbp+18h] BYREF

  LOBYTE(length) = a3;
  v3 = *a2;
  if ( *a2 )
  {
    length = 0;
    v5 = -1;
    string = 0;
    do
      ++v5;
    while ( *(_WORD *)(v3 + 2 * v5) );
    v6 = ULongLongToUInt(v5, &length);
    if ( v6 >= 0 )
    {
      v6 = WindowsCreateString(v7, length, &string);
      if ( v6 >= 0 )
      {
        v8 = *a1;
        *a1 = string;
        WindowsDeleteString(v8);
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800211e4  mov     rax, rsp
0x1800211e7  mov     [rax+8], rbx
0x1800211eb  mov     [rax+20h], rsi
0x1800211ef  mov     [rax+18h], r8b
0x1800211f3  push    rdi
0x1800211f4  sub     rsp, 20h
0x1800211f8  mov     r9, [rdx]
0x1800211fb  xor     esi, esi
0x1800211fd  mov     rdi, rcx
0x180021200  test    r9, r9
0x180021203  jz      short loc_180021261
0x180021205  mov     [rax+18h], esi
0x180021208  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002120c  mov     [rax+10h], rsi
0x180021210  inc     rcx; unsigned __int64
0x180021213  cmp     [r9+rcx*2], si
0x180021218  jnz     short loc_180021210
0x18002121a  lea     rdx, [rsp+28h+length]; unsigned int *
0x18002121f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180021224  mov     ebx, eax
0x180021226  test    eax, eax
0x180021228  js      short loc_180021266
0x18002122a  mov     edx, [rsp+28h+length]; length
0x18002122e  lea     r8, [rsp+28h+string]; string
0x180021233  mov     rcx, r9; sourceString
0x180021236  call    cs:__imp_WindowsCreateString
0x18002123d  nop     dword ptr [rax+rax+00h]
0x180021242  mov     ebx, eax
0x180021244  test    eax, eax
0x180021246  js      short loc_180021266
0x180021248  mov     rax, [rsp+28h+string]
0x18002124d  mov     rcx, [rdi]; string
0x180021250  mov     [rdi], rax
0x180021253  call    cs:__imp_WindowsDeleteString
0x18002125a  nop     dword ptr [rax+rax+00h]
0x18002125f  jmp     short loc_180021266
0x180021261  mov     ebx, 80004003h
0x180021266  mov     rsi, [rsp+28h+arg_18]
0x18002126b  mov     eax, ebx
0x18002126d  mov     rbx, [rsp+28h+arg_0]
0x180021272  add     rsp, 20h
0x180021276  pop     rdi
0x180021277  retn
```
