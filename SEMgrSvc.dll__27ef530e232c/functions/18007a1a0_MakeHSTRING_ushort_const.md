# MakeHSTRING(ushort const *)

- ea: `0x18007a1a0`
- end: `0x18007a236`
- name: `?MakeHSTRING@@YAPEAUHSTRING__@@PEBG@Z`
- size: `150`
- prototype: `HSTRING __fastcall(PCNZWCH sourceString)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003226c`
- `0x180033900`
- `0x18003f990`

## callees

- `0x18002daa4`
- `0x18007a1a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a1d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a1d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007a20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007a1ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007a1ed`

## string_xrefs

- `0x18007a224`: `onecoreuap\ds\nfc\shared\nfccommon\lib\winrttypescopiers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING __fastcall MakeHSTRING(PCNZWCH sourceString)
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
      (void *)0x20,
      (unsigned int)"onecoreuap\\ds\\nfc\\shared\\nfccommon\\lib\\winrttypescopiers.cpp",
      (const char *)(unsigned int)v5,
      v6);
  string = 0;
  WindowsDeleteString(0);
  return v3;
}

```

## disassembly

```asm
0x18007a1a0  push    rbx
0x18007a1a2  push    rbp
0x18007a1a3  push    rsi
0x18007a1a4  push    rdi
0x18007a1a5  sub     rsp, 28h
0x18007a1a9  mov     rdi, rcx
0x18007a1ac  xor     ebp, ebp
0x18007a1ae  test    rcx, rcx
0x18007a1b1  jnz     short loc_18007A1B7
0x18007a1b3  xor     eax, eax
0x18007a1b5  jmp     short loc_18007A218
0x18007a1b7  mov     rsi, rbp
0x18007a1ba  mov     [rsp+48h+string], rbp
0x18007a1bf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007a1c3  inc     rbx
0x18007a1c6  cmp     [rcx+rbx*2], bp
0x18007a1ca  jnz     short loc_18007A1C3
0x18007a1cc  mov     eax, 0FFFFFFFFh
0x18007a1d1  cmp     rbx, rax
0x18007a1d4  ja      short loc_18007A1FA
0x18007a1d6  xor     ecx, ecx; string
0x18007a1d8  call    cs:__imp_WindowsDeleteString
0x18007a1de  mov     [rsp+48h+string], rbp
0x18007a1e3  mov     edx, ebx; length
0x18007a1e5  lea     r8, [rsp+48h+string]; string
0x18007a1ea  mov     rcx, rdi; sourceString
0x18007a1ed  call    cs:__imp_WindowsCreateString
0x18007a1f3  mov     rsi, [rsp+48h+string]
0x18007a1f8  jmp     short loc_18007A1FF
0x18007a1fa  mov     eax, 80070216h
0x18007a1ff  mov     rcx, [rsp+48h]; this
0x18007a204  test    eax, eax
0x18007a206  js      short loc_18007A221
0x18007a208  mov     [rsp+48h+string], rbp
0x18007a20d  xor     ecx, ecx; string
0x18007a20f  call    cs:__imp_WindowsDeleteString
0x18007a215  mov     rax, rsi
0x18007a218  add     rsp, 28h
0x18007a21c  pop     rdi
0x18007a21d  pop     rsi
0x18007a21e  pop     rbp
0x18007a21f  pop     rbx
0x18007a220  retn
0x18007a221  mov     r9d, eax; char *
0x18007a224  lea     r8, aOnecoreuapDsNf_7; "onecoreuap\\ds\\nfc\\shared\\nfccommon"...
0x18007a22b  mov     edx, 20h ; ' '; void *
0x18007a230  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
