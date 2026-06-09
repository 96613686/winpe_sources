# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18005c184`
- end: `0x18005c1ca`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18005c0bc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c19f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c19f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005c1c3`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set(HSTRING *this, const unsigned __int16 *a2, UINT32 a3)
{
  WindowsDeleteString(*this);
  *this = 0;
  return WindowsCreateString(a2, a3, this);
}

```

## disassembly

```asm
0x18005c184  mov     [rsp+arg_0], rbx
0x18005c189  mov     [rsp+arg_8], rsi
0x18005c18e  push    rdi
0x18005c18f  sub     rsp, 20h
0x18005c193  mov     rbx, rcx
0x18005c196  mov     edi, r8d
0x18005c199  mov     rcx, [rcx]; string
0x18005c19c  mov     rsi, rdx
0x18005c19f  call    cs:__imp_WindowsDeleteString
0x18005c1a5  mov     r8, rbx
0x18005c1a8  mov     qword ptr [rbx], 0
0x18005c1af  mov     edx, edi
0x18005c1b1  mov     rcx, rsi
0x18005c1b4  mov     rbx, [rsp+28h+arg_0]
0x18005c1b9  mov     rsi, [rsp+28h+arg_8]
0x18005c1be  add     rsp, 20h
0x18005c1c2  pop     rdi
0x18005c1c3  jmp     cs:__imp_WindowsCreateString
```
