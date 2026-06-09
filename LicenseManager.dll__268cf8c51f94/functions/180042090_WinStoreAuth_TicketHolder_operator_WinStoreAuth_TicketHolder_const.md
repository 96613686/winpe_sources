# WinStoreAuth::TicketHolder::operator=(WinStoreAuth::TicketHolder const &)

- ea: `0x180042090`
- end: `0x18004210d`
- name: `??4TicketHolder@WinStoreAuth@@QEAAAEAU01@AEBU01@@Z`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800620e8`
- `0x18006a520`

## callees

- `0x180042090`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800420cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800420fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800420cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800420fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800420b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800420e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800420b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800420e7`

## pseudocode

```c
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
0x180042090  push    rbx
0x180042092  push    rsi
0x180042093  push    rdi
0x180042094  push    r14
0x180042096  sub     rsp, 28h
0x18004209a  mov     eax, [rdx]
0x18004209c  lea     rbx, [rcx+8]
0x1800420a0  mov     [rcx], eax
0x1800420a2  mov     r14, rdx
0x1800420a5  mov     rsi, [rdx+8]
0x1800420a9  mov     rdi, rcx
0x1800420ac  test    rsi, rsi
0x1800420af  jz      short loc_1800420B6
0x1800420b1  cmp     rsi, [rbx]
0x1800420b4  jz      short loc_1800420D2
0x1800420b6  mov     rcx, [rbx]; string
0x1800420b9  call    cs:__imp_WindowsDeleteString
0x1800420bf  mov     rdx, rbx; newString
0x1800420c2  mov     qword ptr [rbx], 0
0x1800420c9  mov     rcx, rsi; string
0x1800420cc  call    cs:__imp_WindowsDuplicateString
0x1800420d2  mov     rsi, [r14+10h]
0x1800420d6  lea     rbx, [rdi+10h]
0x1800420da  test    rsi, rsi
0x1800420dd  jz      short loc_1800420E4
0x1800420df  cmp     rsi, [rbx]
0x1800420e2  jz      short loc_180042100
0x1800420e4  mov     rcx, [rbx]; string
0x1800420e7  call    cs:__imp_WindowsDeleteString
0x1800420ed  mov     rdx, rbx; newString
0x1800420f0  mov     qword ptr [rbx], 0
0x1800420f7  mov     rcx, rsi; string
0x1800420fa  call    cs:__imp_WindowsDuplicateString
0x180042100  mov     rax, rdi
0x180042103  add     rsp, 28h
0x180042107  pop     r14
0x180042109  pop     rdi
0x18004210a  pop     rsi
0x18004210b  pop     rbx
0x18004210c  retn
```
