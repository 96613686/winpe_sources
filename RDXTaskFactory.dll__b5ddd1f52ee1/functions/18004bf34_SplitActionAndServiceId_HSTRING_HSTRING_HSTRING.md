# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x18004bf34`
- end: `0x18004c008`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18004c7a0`

## callees

- `0x18004bf34`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18004bf7d`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18004bf7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18004bfad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18004bfad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bf97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bfb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bfe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bfed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bf97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bfb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bfe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bfed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004bfc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004bfc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bf6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bf6d`

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
0x18004bf34  mov     [rsp-18h+arg_0], rbx
0x18004bf39  mov     [rsp-18h+arg_18], rsi
0x18004bf3e  mov     [rsp-18h+length], r8
0x18004bf43  push    rbp
0x18004bf44  push    rdi
0x18004bf45  push    r14
0x18004bf47  mov     rbp, rsp
0x18004bf4a  sub     rsp, 20h
0x18004bf4e  mov     rbx, rdx
0x18004bf51  mov     rsi, rcx
0x18004bf54  test    rdx, rdx
0x18004bf57  jz      short loc_18004BF60
0x18004bf59  mov     qword ptr [rdx], 0
0x18004bf60  xor     edi, edi
0x18004bf62  lea     rdx, [rbp+length]; length
0x18004bf66  mov     [rbp+string], rdi
0x18004bf6a  mov     dword ptr [rbp+length], edi
0x18004bf6d  call    cs:__imp_WindowsGetStringRawBuffer
0x18004bf73  mov     rcx, rax; String
0x18004bf76  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x18004bf7d  call    cs:__imp_wcscspn
0x18004bf83  mov     r14, rax
0x18004bf86  test    rbx, rbx
0x18004bf89  jz      short loc_18004BFE1
0x18004bf8b  mov     eax, dword ptr [rbp+length]
0x18004bf8e  mov     rcx, [rbp+string]; string
0x18004bf92  cmp     r14, rax
0x18004bf95  jnb     short loc_18004BFB5
0x18004bf97  call    cs:__imp_WindowsDeleteString
0x18004bf9d  mov     r8d, r14d; length
0x18004bfa0  mov     [rbp+string], rdi
0x18004bfa4  lea     r9, [rbp+string]; newString
0x18004bfa8  xor     edx, edx; startIndex
0x18004bfaa  mov     rcx, rsi; string
0x18004bfad  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x18004bfb3  jmp     short loc_18004BFCC
0x18004bfb5  call    cs:__imp_WindowsDeleteString
0x18004bfbb  lea     rdx, [rbp+string]; newString
0x18004bfbf  mov     [rbp+string], rdi
0x18004bfc3  mov     rcx, rsi; string
0x18004bfc6  call    cs:__imp_WindowsDuplicateString
0x18004bfcc  mov     edi, eax
0x18004bfce  test    eax, eax
0x18004bfd0  js      short loc_18004BFE1
0x18004bfd2  mov     rax, [rbp+string]
0x18004bfd6  mov     [rbx], rax
0x18004bfd9  mov     [rbp+string], 0
0x18004bfe1  xor     ecx, ecx; string
0x18004bfe3  call    cs:__imp_WindowsDeleteString
0x18004bfe9  mov     rcx, [rbp+string]; string
0x18004bfed  call    cs:__imp_WindowsDeleteString
0x18004bff3  mov     rbx, [rsp+20h+arg_0]
0x18004bff8  mov     eax, edi
0x18004bffa  mov     rsi, [rsp+20h+arg_18]
0x18004bfff  add     rsp, 20h
0x18004c003  pop     r14
0x18004c005  pop     rdi
0x18004c006  pop     rbp
0x18004c007  retn
```
