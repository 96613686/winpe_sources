# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180054f18`
- end: `0x180054fec`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180055520`

## callees

- `0x180054f18`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180054f61`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180054f61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054f51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054f51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054fc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054fd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054fc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054fd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180054faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180054faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180054f91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180054f91`

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
0x180054f18  mov     [rsp-18h+arg_0], rbx
0x180054f1d  mov     [rsp-18h+arg_18], rsi
0x180054f22  mov     [rsp-18h+length], r8
0x180054f27  push    rbp
0x180054f28  push    rdi
0x180054f29  push    r14
0x180054f2b  mov     rbp, rsp
0x180054f2e  sub     rsp, 20h
0x180054f32  mov     rbx, rdx
0x180054f35  mov     rsi, rcx
0x180054f38  test    rdx, rdx
0x180054f3b  jz      short loc_180054F44
0x180054f3d  mov     qword ptr [rdx], 0
0x180054f44  xor     edi, edi
0x180054f46  lea     rdx, [rbp+length]; length
0x180054f4a  mov     [rbp+string], rdi
0x180054f4e  mov     dword ptr [rbp+length], edi
0x180054f51  call    cs:__imp_WindowsGetStringRawBuffer
0x180054f57  mov     rcx, rax; String
0x180054f5a  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; Control
0x180054f61  call    cs:__imp_wcscspn
0x180054f67  mov     r14, rax
0x180054f6a  test    rbx, rbx
0x180054f6d  jz      short loc_180054FC5
0x180054f6f  mov     eax, dword ptr [rbp+length]
0x180054f72  mov     rcx, [rbp+string]; string
0x180054f76  cmp     r14, rax
0x180054f79  jnb     short loc_180054F99
0x180054f7b  call    cs:__imp_WindowsDeleteString
0x180054f81  mov     r8d, r14d; length
0x180054f84  mov     [rbp+string], rdi
0x180054f88  lea     r9, [rbp+string]; newString
0x180054f8c  xor     edx, edx; startIndex
0x180054f8e  mov     rcx, rsi; string
0x180054f91  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x180054f97  jmp     short loc_180054FB0
0x180054f99  call    cs:__imp_WindowsDeleteString
0x180054f9f  lea     rdx, [rbp+string]; newString
0x180054fa3  mov     [rbp+string], rdi
0x180054fa7  mov     rcx, rsi; string
0x180054faa  call    cs:__imp_WindowsDuplicateString
0x180054fb0  mov     edi, eax
0x180054fb2  test    eax, eax
0x180054fb4  js      short loc_180054FC5
0x180054fb6  mov     rax, [rbp+string]
0x180054fba  mov     [rbx], rax
0x180054fbd  mov     [rbp+string], 0
0x180054fc5  xor     ecx, ecx; string
0x180054fc7  call    cs:__imp_WindowsDeleteString
0x180054fcd  mov     rcx, [rbp+string]; string
0x180054fd1  call    cs:__imp_WindowsDeleteString
0x180054fd7  mov     rbx, [rsp+20h+arg_0]
0x180054fdc  mov     eax, edi
0x180054fde  mov     rsi, [rsp+20h+arg_18]
0x180054fe3  add     rsp, 20h
0x180054fe7  pop     r14
0x180054fe9  pop     rdi
0x180054fea  pop     rbp
0x180054feb  retn
```
