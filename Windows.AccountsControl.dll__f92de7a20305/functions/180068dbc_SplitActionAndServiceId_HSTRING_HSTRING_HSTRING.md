# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180068dbc`
- end: `0x180068e90`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `212`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180069360`

## callees

- `0x180068dbc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068df5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068df5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180068e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x180068e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180068e4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180068e4e`
- `msvcrt!wcscspn` at `0x180068e05`
- `msvcrt!wcscspn` at `0x180068e05`

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
0x180068dbc  mov     [rsp-18h+arg_0], rbx
0x180068dc1  mov     [rsp-18h+arg_18], rsi
0x180068dc6  mov     [rsp-18h+length], r8
0x180068dcb  push    rbp
0x180068dcc  push    rdi
0x180068dcd  push    r14
0x180068dcf  mov     rbp, rsp
0x180068dd2  sub     rsp, 20h
0x180068dd6  mov     rbx, rdx
0x180068dd9  mov     rsi, rcx
0x180068ddc  test    rdx, rdx
0x180068ddf  jz      short loc_180068DE8
0x180068de1  mov     qword ptr [rdx], 0
0x180068de8  xor     edi, edi
0x180068dea  lea     rdx, [rbp+length]; length
0x180068dee  mov     [rbp+string], rdi
0x180068df2  mov     dword ptr [rbp+length], edi
0x180068df5  call    cs:__imp_WindowsGetStringRawBuffer
0x180068dfb  mov     rcx, rax; String
0x180068dfe  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x180068e05  call    cs:__imp_wcscspn
0x180068e0b  mov     r14, rax
0x180068e0e  test    rbx, rbx
0x180068e11  jz      short loc_180068E69
0x180068e13  mov     eax, dword ptr [rbp+length]
0x180068e16  mov     rcx, [rbp+string]; string
0x180068e1a  cmp     r14, rax
0x180068e1d  jnb     short loc_180068E3D
0x180068e1f  call    cs:__imp_WindowsDeleteString
0x180068e25  mov     r8d, r14d; length
0x180068e28  mov     [rbp+string], rdi
0x180068e2c  lea     r9, [rbp+string]; newString
0x180068e30  xor     edx, edx; startIndex
0x180068e32  mov     rcx, rsi; string
0x180068e35  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x180068e3b  jmp     short loc_180068E54
0x180068e3d  call    cs:__imp_WindowsDeleteString
0x180068e43  lea     rdx, [rbp+string]; newString
0x180068e47  mov     [rbp+string], rdi
0x180068e4b  mov     rcx, rsi; string
0x180068e4e  call    cs:__imp_WindowsDuplicateString
0x180068e54  mov     edi, eax
0x180068e56  test    eax, eax
0x180068e58  js      short loc_180068E69
0x180068e5a  mov     rax, [rbp+string]
0x180068e5e  mov     [rbx], rax
0x180068e61  mov     [rbp+string], 0
0x180068e69  xor     ecx, ecx; string
0x180068e6b  call    cs:__imp_WindowsDeleteString
0x180068e71  mov     rcx, [rbp+string]; string
0x180068e75  call    cs:__imp_WindowsDeleteString
0x180068e7b  mov     rbx, [rsp+20h+arg_0]
0x180068e80  mov     eax, edi
0x180068e82  mov     rsi, [rsp+20h+arg_18]
0x180068e87  add     rsp, 20h
0x180068e8b  pop     r14
0x180068e8d  pop     rdi
0x180068e8e  pop     rbp
0x180068e8f  retn
```
