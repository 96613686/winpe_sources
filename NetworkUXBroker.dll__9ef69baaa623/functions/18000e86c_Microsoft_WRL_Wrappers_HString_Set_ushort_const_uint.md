# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18000e86c`
- end: `0x18000e8b2`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000b43c`
- `0x180040dbc`
- `0x180041e58`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000e8ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e887`

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
0x18000e86c  mov     [rsp+arg_0], rbx
0x18000e871  mov     [rsp+arg_8], rsi
0x18000e876  push    rdi
0x18000e877  sub     rsp, 20h
0x18000e87b  mov     rbx, rcx
0x18000e87e  mov     edi, r8d
0x18000e881  mov     rcx, [rcx]; string
0x18000e884  mov     rsi, rdx
0x18000e887  call    cs:__imp_WindowsDeleteString
0x18000e88d  mov     r8, rbx
0x18000e890  mov     qword ptr [rbx], 0
0x18000e897  mov     edx, edi
0x18000e899  mov     rcx, rsi
0x18000e89c  mov     rbx, [rsp+28h+arg_0]
0x18000e8a1  mov     rsi, [rsp+28h+arg_8]
0x18000e8a6  add     rsp, 20h
0x18000e8aa  pop     rdi
0x18000e8ab  jmp     cs:__imp_WindowsCreateString
```
