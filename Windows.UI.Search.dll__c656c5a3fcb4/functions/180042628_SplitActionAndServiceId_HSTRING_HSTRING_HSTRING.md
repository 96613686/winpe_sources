# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180042628`
- end: `0x1800426fb`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `211`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180042e90`

## callees

- `0x180003402`
- `0x180042628`

## import_xrefs

- `msvcrt!wcscspn` at `0x180042671`
- `msvcrt!wcscspn` at `0x180042671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004268b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800426a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800426d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800426e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004268b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800426a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800426d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800426e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800426b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800426b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042661`

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
      v8 = _Platform_WindowsSubstringWithSpecifiedLength(string, 0, v7, &stringa);
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
0x180042628  mov     [rsp-18h+arg_0], rbx
0x18004262d  mov     [rsp-18h+arg_18], rsi
0x180042632  mov     [rsp-18h+length], r8
0x180042637  push    rbp
0x180042638  push    rdi
0x180042639  push    r14
0x18004263b  mov     rbp, rsp
0x18004263e  sub     rsp, 20h
0x180042642  mov     rbx, rdx
0x180042645  mov     rsi, rcx
0x180042648  test    rdx, rdx
0x18004264b  jz      short loc_180042654
0x18004264d  mov     qword ptr [rdx], 0
0x180042654  xor     edi, edi
0x180042656  lea     rdx, [rbp+length]; length
0x18004265a  mov     [rbp+string], rdi
0x18004265e  mov     dword ptr [rbp+length], edi
0x180042661  call    cs:__imp_WindowsGetStringRawBuffer
0x180042667  mov     rcx, rax; String
0x18004266a  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; Control
0x180042671  call    cs:__imp_wcscspn
0x180042677  mov     r14, rax
0x18004267a  test    rbx, rbx
0x18004267d  jz      short loc_1800426D4
0x18004267f  mov     eax, dword ptr [rbp+length]
0x180042682  mov     rcx, [rbp+string]; string
0x180042686  cmp     r14, rax
0x180042689  jnb     short loc_1800426A8
0x18004268b  call    cs:__imp_WindowsDeleteString
0x180042691  mov     r8d, r14d; length
0x180042694  mov     [rbp+string], rdi
0x180042698  lea     r9, [rbp+string]; newString
0x18004269c  xor     edx, edx; startIndex
0x18004269e  mov     rcx, rsi; string
0x1800426a1  call    __Platform_WindowsSubstringWithSpecifiedLength
0x1800426a6  jmp     short loc_1800426BF
0x1800426a8  call    cs:__imp_WindowsDeleteString
0x1800426ae  lea     rdx, [rbp+string]; newString
0x1800426b2  mov     [rbp+string], rdi
0x1800426b6  mov     rcx, rsi; string
0x1800426b9  call    cs:__imp_WindowsDuplicateString
0x1800426bf  mov     edi, eax
0x1800426c1  test    eax, eax
0x1800426c3  js      short loc_1800426D4
0x1800426c5  mov     rax, [rbp+string]
0x1800426c9  mov     [rbx], rax
0x1800426cc  mov     [rbp+string], 0
0x1800426d4  xor     ecx, ecx; string
0x1800426d6  call    cs:__imp_WindowsDeleteString
0x1800426dc  mov     rcx, [rbp+string]; string
0x1800426e0  call    cs:__imp_WindowsDeleteString
0x1800426e6  mov     rbx, [rsp+20h+arg_0]
0x1800426eb  mov     eax, edi
0x1800426ed  mov     rsi, [rsp+20h+arg_18]
0x1800426f2  add     rsp, 20h
0x1800426f6  pop     r14
0x1800426f8  pop     rdi
0x1800426f9  pop     rbp
0x1800426fa  retn
```
