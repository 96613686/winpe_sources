# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1801ccc10`
- end: `0x1801ccd15`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `261`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1801cc070`
- `0x18037bc70`

## callees

- `0x1801ccc10`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1801ccc5f`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1801ccc5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ccc7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ccca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ccce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cccf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ccc7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ccca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ccce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cccf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801cccc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1801cccc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ccc49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ccc49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1801ccc9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1801ccc9b`

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
  v7 = wcscspn(StringRawBuffer, &c_szActionServiceDelimiter);
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
0x1801ccc10  mov     [rsp-18h+arg_0], rbx
0x1801ccc15  mov     [rsp-18h+arg_18], rsi
0x1801ccc1a  mov     [rsp-18h+length], r8
0x1801ccc1f  push    rbp
0x1801ccc20  push    rdi
0x1801ccc21  push    r14
0x1801ccc23  mov     rbp, rsp
0x1801ccc26  sub     rsp, 20h
0x1801ccc2a  mov     rbx, rdx
0x1801ccc2d  mov     rsi, rcx
0x1801ccc30  test    rdx, rdx
0x1801ccc33  jz      short loc_1801CCC3C
0x1801ccc35  mov     qword ptr [rdx], 0
0x1801ccc3c  xor     edi, edi
0x1801ccc3e  lea     rdx, [rbp+length]; length
0x1801ccc42  mov     [rbp+string], rdi
0x1801ccc46  mov     dword ptr [rbp+length], edi
0x1801ccc49  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ccc50  nop     dword ptr [rax+rax+00h]
0x1801ccc55  mov     rcx, rax; String
0x1801ccc58  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; Control
0x1801ccc5f  call    cs:__imp_wcscspn
0x1801ccc66  nop     dword ptr [rax+rax+00h]
0x1801ccc6b  mov     r14, rax
0x1801ccc6e  test    rbx, rbx
0x1801ccc71  jz      short loc_1801CCCE1
0x1801ccc73  mov     eax, dword ptr [rbp+length]
0x1801ccc76  mov     rcx, [rbp+string]; string
0x1801ccc7a  cmp     r14, rax
0x1801ccc7d  jnb     short loc_1801CCCA9
0x1801ccc7f  call    cs:__imp_WindowsDeleteString
0x1801ccc86  nop     dword ptr [rax+rax+00h]
0x1801ccc8b  mov     r8d, r14d; length
0x1801ccc8e  mov     [rbp+string], rdi
0x1801ccc92  lea     r9, [rbp+string]; newString
0x1801ccc96  xor     edx, edx; startIndex
0x1801ccc98  mov     rcx, rsi; string
0x1801ccc9b  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1801ccca2  nop     dword ptr [rax+rax+00h]
0x1801ccca7  jmp     short loc_1801CCCCC
0x1801ccca9  call    cs:__imp_WindowsDeleteString
0x1801cccb0  nop     dword ptr [rax+rax+00h]
0x1801cccb5  lea     rdx, [rbp+string]; newString
0x1801cccb9  mov     [rbp+string], rdi
0x1801cccbd  mov     rcx, rsi; string
0x1801cccc0  call    cs:__imp_WindowsDuplicateString
0x1801cccc7  nop     dword ptr [rax+rax+00h]
0x1801ccccc  mov     edi, eax
0x1801cccce  test    eax, eax
0x1801cccd0  js      short loc_1801CCCE1
0x1801cccd2  mov     rax, [rbp+string]
0x1801cccd6  mov     [rbx], rax
0x1801cccd9  mov     [rbp+string], 0
0x1801ccce1  xor     ecx, ecx; string
0x1801ccce3  call    cs:__imp_WindowsDeleteString
0x1801cccea  nop     dword ptr [rax+rax+00h]
0x1801cccef  mov     rcx, [rbp+string]; string
0x1801cccf3  call    cs:__imp_WindowsDeleteString
0x1801cccfa  nop     dword ptr [rax+rax+00h]
0x1801cccff  mov     rbx, [rsp+20h+arg_0]
0x1801ccd04  mov     eax, edi
0x1801ccd06  mov     rsi, [rsp+20h+arg_18]
0x1801ccd0b  add     rsp, 20h
0x1801ccd0f  pop     r14
0x1801ccd11  pop     rdi
0x1801ccd12  pop     rbp
0x1801ccd13  retn
```
