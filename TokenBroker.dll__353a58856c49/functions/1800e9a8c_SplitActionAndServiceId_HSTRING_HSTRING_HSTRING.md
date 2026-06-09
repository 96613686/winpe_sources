# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800e9a8c`
- end: `0x1800e9b60`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800ea0a0`

## callees

- `0x1800e9a8c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1800e9ad5`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1800e9ad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800e9b1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800e9b1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e9ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e9ac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9b0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9b3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9b45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9b0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9b3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e9b45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800e9b05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800e9b05`

## pseudocode

```c
__int64 __fastcall SplitActionAndServiceId(HSTRING string, HSTRING *a2, HSTRING *a3)
{
  unsigned int v5; // edi
  const wchar_t *StringRawBuffer; // rax
  size_t v7; // r14
  HRESULT v8; // eax
  HSTRING stringa; // [rsp+48h] [rbp+28h] BYREF
  HSTRING *length; // [rsp+50h] [rbp+30h] BYREF

  length = a3;
  if ( a2 )
    *a2 = 0;
  v5 = 0;
  stringa = 0;
  LODWORD(length) = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, (UINT32 *)&length);
  v7 = wcscspn(StringRawBuffer, L"+");
  if ( a2 )
  {
    if ( v7 >= (unsigned int)length )
    {
      WindowsDeleteString(stringa);
      stringa = 0;
      v8 = WindowsDuplicateString(string, &stringa);
    }
    else
    {
      WindowsDeleteString(stringa);
      stringa = 0;
      v8 = WindowsSubstringWithSpecifiedLength(string, 0, v7, &stringa);
    }
    v5 = v8;
    if ( v8 >= 0 )
    {
      *a2 = stringa;
      stringa = 0;
    }
  }
  WindowsDeleteString(0);
  WindowsDeleteString(stringa);
  return v5;
}

```

## disassembly

```asm
0x1800e9a8c  mov     [rsp-18h+arg_0], rbx
0x1800e9a91  mov     [rsp-18h+arg_18], rsi
0x1800e9a96  mov     [rsp-18h+length], r8
0x1800e9a9b  push    rbp
0x1800e9a9c  push    rdi
0x1800e9a9d  push    r14
0x1800e9a9f  mov     rbp, rsp
0x1800e9aa2  sub     rsp, 20h
0x1800e9aa6  mov     rbx, rdx
0x1800e9aa9  mov     rsi, rcx
0x1800e9aac  test    rdx, rdx
0x1800e9aaf  jz      short loc_1800E9AB8
0x1800e9ab1  mov     qword ptr [rdx], 0
0x1800e9ab8  xor     edi, edi
0x1800e9aba  lea     rdx, [rbp+length]; length
0x1800e9abe  mov     [rbp+string], rdi
0x1800e9ac2  mov     dword ptr [rbp+length], edi
0x1800e9ac5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e9acb  mov     rcx, rax; String
0x1800e9ace  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x1800e9ad5  call    cs:__imp_wcscspn
0x1800e9adb  mov     r14, rax
0x1800e9ade  test    rbx, rbx
0x1800e9ae1  jz      short loc_1800E9B39
0x1800e9ae3  mov     eax, dword ptr [rbp+length]
0x1800e9ae6  mov     rcx, [rbp+string]; string
0x1800e9aea  cmp     r14, rax
0x1800e9aed  jnb     short loc_1800E9B0D
0x1800e9aef  call    cs:__imp_WindowsDeleteString
0x1800e9af5  mov     r8d, r14d; length
0x1800e9af8  mov     [rbp+string], rdi
0x1800e9afc  lea     r9, [rbp+string]; newString
0x1800e9b00  xor     edx, edx; startIndex
0x1800e9b02  mov     rcx, rsi; string
0x1800e9b05  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1800e9b0b  jmp     short loc_1800E9B24
0x1800e9b0d  call    cs:__imp_WindowsDeleteString
0x1800e9b13  lea     rdx, [rbp+string]; newString
0x1800e9b17  mov     [rbp+string], rdi
0x1800e9b1b  mov     rcx, rsi; string
0x1800e9b1e  call    cs:__imp_WindowsDuplicateString
0x1800e9b24  mov     edi, eax
0x1800e9b26  test    eax, eax
0x1800e9b28  js      short loc_1800E9B39
0x1800e9b2a  mov     rax, [rbp+string]
0x1800e9b2e  mov     [rbx], rax
0x1800e9b31  mov     [rbp+string], 0
0x1800e9b39  xor     ecx, ecx; string
0x1800e9b3b  call    cs:__imp_WindowsDeleteString
0x1800e9b41  mov     rcx, [rbp+string]; string
0x1800e9b45  call    cs:__imp_WindowsDeleteString
0x1800e9b4b  mov     rbx, [rsp+20h+arg_0]
0x1800e9b50  mov     eax, edi
0x1800e9b52  mov     rsi, [rsp+20h+arg_18]
0x1800e9b57  add     rsp, 20h
0x1800e9b5b  pop     r14
0x1800e9b5d  pop     rdi
0x1800e9b5e  pop     rbp
0x1800e9b5f  retn
```
