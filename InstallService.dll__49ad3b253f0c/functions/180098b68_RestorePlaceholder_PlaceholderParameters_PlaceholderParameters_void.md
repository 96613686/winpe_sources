# RestorePlaceholder::PlaceholderParameters::~PlaceholderParameters(void)

- ea: `0x180098b68`
- end: `0x180098c6a`
- name: `??1PlaceholderParameters@RestorePlaceholder@@QEAA@XZ`
- size: `258`
- prototype: `void __fastcall(RestorePlaceholder::PlaceholderParameters *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800b8010`
- `0x180200d5e`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098b7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098b92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098ba6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098bce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098be2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098b7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098b92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098ba6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098bce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098be2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098c55`

## pseudocode

```c
void __fastcall RestorePlaceholder::PlaceholderParameters::~PlaceholderParameters(HSTRING *this)
{
  WindowsDeleteString(this[27]);
  this[27] = 0;
  WindowsDeleteString(this[25]);
  this[25] = 0;
  WindowsDeleteString(this[23]);
  this[23] = 0;
  WindowsDeleteString(this[21]);
  this[21] = 0;
  WindowsDeleteString(this[19]);
  this[19] = 0;
  WindowsDeleteString(this[17]);
  this[17] = 0;
  WindowsDeleteString(this[15]);
  this[15] = 0;
  WindowsDeleteString(this[13]);
  this[13] = 0;
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
}

```

## disassembly

```asm
0x180098b68  mov     [rsp+arg_0], rbx
0x180098b6d  push    rdi
0x180098b6e  sub     rsp, 20h
0x180098b72  mov     rbx, rcx
0x180098b75  mov     rcx, [rcx+0D8h]; string
0x180098b7c  call    cs:__imp_WindowsDeleteString
0x180098b82  xor     edi, edi
0x180098b84  mov     [rbx+0D8h], rdi
0x180098b8b  mov     rcx, [rbx+0C8h]; string
0x180098b92  call    cs:__imp_WindowsDeleteString
0x180098b98  mov     [rbx+0C8h], rdi
0x180098b9f  mov     rcx, [rbx+0B8h]; string
0x180098ba6  call    cs:__imp_WindowsDeleteString
0x180098bac  mov     [rbx+0B8h], rdi
0x180098bb3  mov     rcx, [rbx+0A8h]; string
0x180098bba  call    cs:__imp_WindowsDeleteString
0x180098bc0  mov     [rbx+0A8h], rdi
0x180098bc7  mov     rcx, [rbx+98h]; string
0x180098bce  call    cs:__imp_WindowsDeleteString
0x180098bd4  mov     [rbx+98h], rdi
0x180098bdb  mov     rcx, [rbx+88h]; string
0x180098be2  call    cs:__imp_WindowsDeleteString
0x180098be8  mov     [rbx+88h], rdi
0x180098bef  mov     rcx, [rbx+78h]; string
0x180098bf3  call    cs:__imp_WindowsDeleteString
0x180098bf9  mov     [rbx+78h], rdi
0x180098bfd  mov     rcx, [rbx+68h]; string
0x180098c01  call    cs:__imp_WindowsDeleteString
0x180098c07  mov     [rbx+68h], rdi
0x180098c0b  mov     rcx, [rbx+58h]; string
0x180098c0f  call    cs:__imp_WindowsDeleteString
0x180098c15  mov     [rbx+58h], rdi
0x180098c19  mov     rcx, [rbx+48h]; string
0x180098c1d  call    cs:__imp_WindowsDeleteString
0x180098c23  mov     [rbx+48h], rdi
0x180098c27  mov     rcx, [rbx+38h]; string
0x180098c2b  call    cs:__imp_WindowsDeleteString
0x180098c31  mov     [rbx+38h], rdi
0x180098c35  mov     rcx, [rbx+28h]; string
0x180098c39  call    cs:__imp_WindowsDeleteString
0x180098c3f  mov     [rbx+28h], rdi
0x180098c43  mov     rcx, [rbx+18h]; string
0x180098c47  call    cs:__imp_WindowsDeleteString
0x180098c4d  mov     [rbx+18h], rdi
0x180098c51  mov     rcx, [rbx+8]; string
0x180098c55  call    cs:__imp_WindowsDeleteString
0x180098c5b  mov     [rbx+8], rdi
0x180098c5f  mov     rbx, [rsp+28h+arg_0]
0x180098c64  add     rsp, 20h
0x180098c68  pop     rdi
0x180098c69  retn
```
