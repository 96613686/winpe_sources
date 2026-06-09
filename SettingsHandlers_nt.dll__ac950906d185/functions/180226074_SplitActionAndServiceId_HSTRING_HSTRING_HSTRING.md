# SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180226074`
- end: `0x180226179`
- name: `?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `261`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180226910`

## callees

- `0x180226074`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1802260c3`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x1802260c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180226124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180226124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802260e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022610d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180226147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180226157`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802260e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022610d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180226147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180226157`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802260ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802260ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1802260ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1802260ff`

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
0x180226074  mov     [rsp-18h+arg_0], rbx
0x180226079  mov     [rsp-18h+arg_18], rsi
0x18022607e  mov     [rsp-18h+length], r8
0x180226083  push    rbp
0x180226084  push    rdi
0x180226085  push    r14
0x180226087  mov     rbp, rsp
0x18022608a  sub     rsp, 20h
0x18022608e  mov     rbx, rdx
0x180226091  mov     rsi, rcx
0x180226094  test    rdx, rdx
0x180226097  jz      short loc_1802260A0
0x180226099  mov     qword ptr [rdx], 0
0x1802260a0  xor     edi, edi
0x1802260a2  lea     rdx, [rbp+length]; length
0x1802260a6  mov     [rbp+string], rdi
0x1802260aa  mov     dword ptr [rbp+length], edi
0x1802260ad  call    cs:__imp_WindowsGetStringRawBuffer
0x1802260b4  nop     dword ptr [rax+rax+00h]
0x1802260b9  mov     rcx, rax; String
0x1802260bc  lea     rdx, ?c_szActionServiceDelimiter@@3QBGB; "+"
0x1802260c3  call    cs:__imp_wcscspn
0x1802260ca  nop     dword ptr [rax+rax+00h]
0x1802260cf  mov     r14, rax
0x1802260d2  test    rbx, rbx
0x1802260d5  jz      short loc_180226145
0x1802260d7  mov     eax, dword ptr [rbp+length]
0x1802260da  mov     rcx, [rbp+string]; string
0x1802260de  cmp     r14, rax
0x1802260e1  jnb     short loc_18022610D
0x1802260e3  call    cs:__imp_WindowsDeleteString
0x1802260ea  nop     dword ptr [rax+rax+00h]
0x1802260ef  mov     r8d, r14d; length
0x1802260f2  mov     [rbp+string], rdi
0x1802260f6  lea     r9, [rbp+string]; newString
0x1802260fa  xor     edx, edx; startIndex
0x1802260fc  mov     rcx, rsi; string
0x1802260ff  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x180226106  nop     dword ptr [rax+rax+00h]
0x18022610b  jmp     short loc_180226130
0x18022610d  call    cs:__imp_WindowsDeleteString
0x180226114  nop     dword ptr [rax+rax+00h]
0x180226119  lea     rdx, [rbp+string]; newString
0x18022611d  mov     [rbp+string], rdi
0x180226121  mov     rcx, rsi; string
0x180226124  call    cs:__imp_WindowsDuplicateString
0x18022612b  nop     dword ptr [rax+rax+00h]
0x180226130  mov     edi, eax
0x180226132  test    eax, eax
0x180226134  js      short loc_180226145
0x180226136  mov     rax, [rbp+string]
0x18022613a  mov     [rbx], rax
0x18022613d  mov     [rbp+string], 0
0x180226145  xor     ecx, ecx; string
0x180226147  call    cs:__imp_WindowsDeleteString
0x18022614e  nop     dword ptr [rax+rax+00h]
0x180226153  mov     rcx, [rbp+string]; string
0x180226157  call    cs:__imp_WindowsDeleteString
0x18022615e  nop     dword ptr [rax+rax+00h]
0x180226163  mov     rbx, [rsp+20h+arg_0]
0x180226168  mov     eax, edi
0x18022616a  mov     rsi, [rsp+20h+arg_18]
0x18022616f  add     rsp, 20h
0x180226173  pop     r14
0x180226175  pop     rdi
0x180226176  pop     rbp
0x180226177  retn
```
