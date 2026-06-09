# MakeHString(ushort const *)

- ea: `0x180086c78`
- end: `0x180086d0e`
- name: `?MakeHString@@YAPEAUHSTRING__@@PEBG@Z`
- size: `150`
- prototype: `HSTRING __fastcall(PCNZWCH sourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18007df64`
- `0x180083308`

## callees

- `0x18002daa4`
- `0x180086c78`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180086cb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180086ce7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180086cb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180086ce7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180086cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180086cc5`

## string_xrefs

- `0x180086cfc`: `onecoreuap\ds\nfc\product\payment\service\lib\paymentservicetypescopiers.cpp`

## pseudocode

```c
HSTRING __fastcall MakeHString(PCNZWCH sourceString)
{
  HSTRING v3; // rsi
  unsigned __int64 v4; // rbx
  HRESULT v5; // eax
  int v6; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF

  if ( !sourceString )
    return 0;
  v3 = 0;
  string = 0;
  v4 = -1;
  do
    ++v4;
  while ( sourceString[v4] );
  if ( v4 > 0xFFFFFFFF )
  {
    v5 = -2147024362;
  }
  else
  {
    WindowsDeleteString(0);
    string = 0;
    v5 = WindowsCreateString(sourceString, v4, &string);
    v3 = string;
  }
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\paymentservicetypescopiers.cpp",
      (const char *)(unsigned int)v5,
      v6);
  string = 0;
  WindowsDeleteString(0);
  return v3;
}

```

## disassembly

```asm
0x180086c78  push    rbx
0x180086c7a  push    rbp
0x180086c7b  push    rsi
0x180086c7c  push    rdi
0x180086c7d  sub     rsp, 28h
0x180086c81  mov     rdi, rcx
0x180086c84  xor     ebp, ebp
0x180086c86  test    rcx, rcx
0x180086c89  jnz     short loc_180086C8F
0x180086c8b  xor     eax, eax
0x180086c8d  jmp     short loc_180086CF0
0x180086c8f  mov     rsi, rbp
0x180086c92  mov     [rsp+48h+string], rbp
0x180086c97  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180086c9b  inc     rbx
0x180086c9e  cmp     [rcx+rbx*2], bp
0x180086ca2  jnz     short loc_180086C9B
0x180086ca4  mov     eax, 0FFFFFFFFh
0x180086ca9  cmp     rbx, rax
0x180086cac  ja      short loc_180086CD2
0x180086cae  xor     ecx, ecx; string
0x180086cb0  call    cs:__imp_WindowsDeleteString
0x180086cb6  mov     [rsp+48h+string], rbp
0x180086cbb  mov     edx, ebx; length
0x180086cbd  lea     r8, [rsp+48h+string]; string
0x180086cc2  mov     rcx, rdi; sourceString
0x180086cc5  call    cs:__imp_WindowsCreateString
0x180086ccb  mov     rsi, [rsp+48h+string]
0x180086cd0  jmp     short loc_180086CD7
0x180086cd2  mov     eax, 80070216h
0x180086cd7  mov     rcx, [rsp+48h]; this
0x180086cdc  test    eax, eax
0x180086cde  js      short loc_180086CF9
0x180086ce0  mov     [rsp+48h+string], rbp
0x180086ce5  xor     ecx, ecx; string
0x180086ce7  call    cs:__imp_WindowsDeleteString
0x180086ced  mov     rax, rsi
0x180086cf0  add     rsp, 28h
0x180086cf4  pop     rdi
0x180086cf5  pop     rsi
0x180086cf6  pop     rbp
0x180086cf7  pop     rbx
0x180086cf8  retn
0x180086cf9  mov     r9d, eax; char *
0x180086cfc  lea     r8, aOnecoreuapDsNf_41; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180086d03  mov     edx, 34h ; '4'; void *
0x180086d08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
