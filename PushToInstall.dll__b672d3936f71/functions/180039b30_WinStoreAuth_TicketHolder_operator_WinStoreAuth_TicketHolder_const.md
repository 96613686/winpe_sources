# WinStoreAuth::TicketHolder::operator=(WinStoreAuth::TicketHolder const &)

- ea: `0x180039b30`
- end: `0x180039bad`
- name: `??4TicketHolder@WinStoreAuth@@QEAAAEAU01@AEBU01@@Z`
- size: `125`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003c52c`
- `0x18003dcbc`

## callees

- `0x180039b30`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180039b6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180039b9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180039b6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180039b9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b87`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinStoreAuth::TicketHolder::operator=(__int64 a1, __int64 a2)
{
  HSTRING *v2; // rbx
  HSTRING v4; // rsi
  HSTRING v6; // rsi
  HSTRING *v7; // rbx

  v2 = (HSTRING *)(a1 + 8);
  *(_DWORD *)a1 = *(_DWORD *)a2;
  v4 = *(HSTRING *)(a2 + 8);
  if ( !v4 || v4 != *v2 )
  {
    WindowsDeleteString(*v2);
    *v2 = 0;
    WindowsDuplicateString(v4, v2);
  }
  v6 = *(HSTRING *)(a2 + 16);
  v7 = (HSTRING *)(a1 + 16);
  if ( !v6 || v6 != *v7 )
  {
    WindowsDeleteString(*v7);
    *v7 = 0;
    WindowsDuplicateString(v6, (HSTRING *)(a1 + 16));
  }
  return a1;
}

```

## disassembly

```asm
0x180039b30  push    rbx
0x180039b32  push    rsi
0x180039b33  push    rdi
0x180039b34  push    r14
0x180039b36  sub     rsp, 28h
0x180039b3a  mov     eax, [rdx]
0x180039b3c  lea     rbx, [rcx+8]
0x180039b40  mov     [rcx], eax
0x180039b42  mov     r14, rdx
0x180039b45  mov     rsi, [rdx+8]
0x180039b49  mov     rdi, rcx
0x180039b4c  test    rsi, rsi
0x180039b4f  jz      short loc_180039B56
0x180039b51  cmp     rsi, [rbx]
0x180039b54  jz      short loc_180039B72
0x180039b56  mov     rcx, [rbx]; string
0x180039b59  call    cs:__imp_WindowsDeleteString
0x180039b5f  mov     rdx, rbx; newString
0x180039b62  mov     qword ptr [rbx], 0
0x180039b69  mov     rcx, rsi; string
0x180039b6c  call    cs:__imp_WindowsDuplicateString
0x180039b72  mov     rsi, [r14+10h]
0x180039b76  lea     rbx, [rdi+10h]
0x180039b7a  test    rsi, rsi
0x180039b7d  jz      short loc_180039B84
0x180039b7f  cmp     rsi, [rbx]
0x180039b82  jz      short loc_180039BA0
0x180039b84  mov     rcx, [rbx]; string
0x180039b87  call    cs:__imp_WindowsDeleteString
0x180039b8d  mov     rdx, rbx; newString
0x180039b90  mov     qword ptr [rbx], 0
0x180039b97  mov     rcx, rsi; string
0x180039b9a  call    cs:__imp_WindowsDuplicateString
0x180039ba0  mov     rax, rdi
0x180039ba3  add     rsp, 28h
0x180039ba7  pop     r14
0x180039ba9  pop     rdi
0x180039baa  pop     rsi
0x180039bab  pop     rbx
0x180039bac  retn
```
