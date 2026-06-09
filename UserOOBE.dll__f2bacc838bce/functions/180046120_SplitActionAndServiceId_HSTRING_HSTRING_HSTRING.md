# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180046120`
- end: `0x1800461f4`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800469c0`

## callees

- `0x180046120`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180046169`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180046169`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046159`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046159`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800461a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800461cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800461d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800461a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800461cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800461d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800461b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800461b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180046199`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180046199`

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
0x180046120  mov     [rsp-18h+arg_0], rbx
0x180046125  mov     [rsp-18h+arg_18], rsi
0x18004612a  mov     [rsp-18h+length], r8
0x18004612f  push    rbp
0x180046130  push    rdi
0x180046131  push    r14
0x180046133  mov     rbp, rsp
0x180046136  sub     rsp, 20h
0x18004613a  mov     rbx, rdx
0x18004613d  mov     rsi, rcx
0x180046140  test    rdx, rdx
0x180046143  jz      short loc_18004614C
0x180046145  mov     qword ptr [rdx], 0
0x18004614c  xor     edi, edi
0x18004614e  lea     rdx, [rbp+length]; length
0x180046152  mov     [rbp+string], rdi
0x180046156  mov     dword ptr [rbp+length], edi
0x180046159  call    cs:__imp_WindowsGetStringRawBuffer
0x18004615f  mov     rcx, rax; String
0x180046162  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; Control
0x180046169  call    cs:__imp_wcscspn
0x18004616f  mov     r14, rax
0x180046172  test    rbx, rbx
0x180046175  jz      short loc_1800461CD
0x180046177  mov     eax, dword ptr [rbp+length]
0x18004617a  mov     rcx, [rbp+string]; string
0x18004617e  cmp     r14, rax
0x180046181  jnb     short loc_1800461A1
0x180046183  call    cs:__imp_WindowsDeleteString
0x180046189  mov     r8d, r14d; length
0x18004618c  mov     [rbp+string], rdi
0x180046190  lea     r9, [rbp+string]; newString
0x180046194  xor     edx, edx; startIndex
0x180046196  mov     rcx, rsi; string
0x180046199  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x18004619f  jmp     short loc_1800461B8
0x1800461a1  call    cs:__imp_WindowsDeleteString
0x1800461a7  lea     rdx, [rbp+string]; newString
0x1800461ab  mov     [rbp+string], rdi
0x1800461af  mov     rcx, rsi; string
0x1800461b2  call    cs:__imp_WindowsDuplicateString
0x1800461b8  mov     edi, eax
0x1800461ba  test    eax, eax
0x1800461bc  js      short loc_1800461CD
0x1800461be  mov     rax, [rbp+string]
0x1800461c2  mov     [rbx], rax
0x1800461c5  mov     [rbp+string], 0
0x1800461cd  xor     ecx, ecx; string
0x1800461cf  call    cs:__imp_WindowsDeleteString
0x1800461d5  mov     rcx, [rbp+string]; string
0x1800461d9  call    cs:__imp_WindowsDeleteString
0x1800461df  mov     rbx, [rsp+20h+arg_0]
0x1800461e4  mov     eax, edi
0x1800461e6  mov     rsi, [rsp+20h+arg_18]
0x1800461eb  add     rsp, 20h
0x1800461ef  pop     r14
0x1800461f1  pop     rdi
0x1800461f2  pop     rbp
0x1800461f3  retn
```
