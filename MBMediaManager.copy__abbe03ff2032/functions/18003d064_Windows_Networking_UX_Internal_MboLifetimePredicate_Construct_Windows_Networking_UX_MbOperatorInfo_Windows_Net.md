# Windows::Networking::UX::Internal::MboLifetimePredicate::Construct(Windows::Networking::UX::MbOperatorInfo *,Windows::Networking::UX::MbOperatorInfo)

- ea: `0x18003d064`
- end: `0x18003d0fd`
- name: `?Construct@MboLifetimePredicate@Internal@UX@Networking@Windows@@SAJPEAUMbOperatorInfo@345@U6345@@Z`
- size: `153`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18003871c`
- `0x18003d560`
- `0x18003dbe0`
- `0x1800405a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d0a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d0c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d0e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d0a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d0c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d0e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d0b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d0d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d0b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d0d3`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MboLifetimePredicate::Construct(__int64 a1, __int64 a2)
{
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v5; // rax
  const WCHAR *v6; // rax

  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)a1 = *(_DWORD *)a2;
  *(_DWORD *)(a1 + 4) = *(_DWORD *)(a2 + 4);
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 8), 0);
  WindowsCreateString(StringRawBuffer, 0x15u, (HSTRING *)(a1 + 8));
  v5 = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 16), 0);
  WindowsCreateString(v5, 7u, (HSTRING *)(a1 + 16));
  v6 = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 24), 0);
  WindowsCreateString(v6, 3u, (HSTRING *)(a1 + 24));
  return 0;
}

```

## disassembly

```asm
0x18003d064  mov     [rsp+arg_0], rbx
0x18003d069  mov     [rsp+arg_8], rsi
0x18003d06e  push    rdi
0x18003d06f  sub     rsp, 20h
0x18003d073  xor     eax, eax
0x18003d075  mov     rsi, rdx
0x18003d078  mov     [rcx+8], rax
0x18003d07c  mov     rdi, rcx
0x18003d07f  mov     [rcx+10h], rax
0x18003d083  mov     [rcx+18h], rax
0x18003d087  mov     eax, [rdx]
0x18003d089  mov     [rcx], eax
0x18003d08b  mov     eax, [rdx+4]
0x18003d08e  xor     edx, edx; length
0x18003d090  mov     [rcx+4], eax
0x18003d093  mov     rcx, [rsi+8]; string
0x18003d097  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d09d  lea     r8, [rdi+8]; string
0x18003d0a1  mov     edx, 15h; length
0x18003d0a6  mov     rcx, rax; sourceString
0x18003d0a9  call    cs:__imp_WindowsCreateString
0x18003d0af  mov     rcx, [rsi+10h]; string
0x18003d0b3  xor     edx, edx; length
0x18003d0b5  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d0bb  lea     r8, [rdi+10h]; string
0x18003d0bf  mov     edx, 7; length
0x18003d0c4  mov     rcx, rax; sourceString
0x18003d0c7  call    cs:__imp_WindowsCreateString
0x18003d0cd  mov     rcx, [rsi+18h]; string
0x18003d0d1  xor     edx, edx; length
0x18003d0d3  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d0d9  lea     r8, [rdi+18h]; string
0x18003d0dd  mov     edx, 3; length
0x18003d0e2  mov     rcx, rax; sourceString
0x18003d0e5  call    cs:__imp_WindowsCreateString
0x18003d0eb  mov     rbx, [rsp+28h+arg_0]
0x18003d0f0  xor     eax, eax
0x18003d0f2  mov     rsi, [rsp+28h+arg_8]
0x18003d0f7  add     rsp, 20h
0x18003d0fb  pop     rdi
0x18003d0fc  retn
```
