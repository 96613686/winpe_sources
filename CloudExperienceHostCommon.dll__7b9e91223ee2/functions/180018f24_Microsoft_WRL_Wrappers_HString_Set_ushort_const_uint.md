# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180018f24`
- end: `0x180018f6a`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018ecc`
- `0x180028f50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018f3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018f3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018f63`

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
0x180018f24  mov     [rsp+arg_0], rbx
0x180018f29  mov     [rsp+arg_8], rsi
0x180018f2e  push    rdi
0x180018f2f  sub     rsp, 20h
0x180018f33  mov     rbx, rcx
0x180018f36  mov     edi, r8d
0x180018f39  mov     rcx, [rcx]; string
0x180018f3c  mov     rsi, rdx
0x180018f3f  call    cs:__imp_WindowsDeleteString
0x180018f45  mov     r8, rbx
0x180018f48  mov     qword ptr [rbx], 0
0x180018f4f  mov     edx, edi
0x180018f51  mov     rcx, rsi
0x180018f54  mov     rbx, [rsp+28h+arg_0]
0x180018f59  mov     rsi, [rsp+28h+arg_8]
0x180018f5e  add     rsp, 20h
0x180018f62  pop     rdi
0x180018f63  jmp     cs:__imp_WindowsCreateString
```
