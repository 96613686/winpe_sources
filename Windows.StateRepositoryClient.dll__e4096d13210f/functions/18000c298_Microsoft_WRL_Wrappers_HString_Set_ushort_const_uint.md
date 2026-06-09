# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18000c298`
- end: `0x18000c2de`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000c790`
- `0x18001e288`
- `0x180026110`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000c2d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c2b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c2b3`

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
0x18000c298  mov     [rsp+arg_0], rbx
0x18000c29d  mov     [rsp+arg_8], rsi
0x18000c2a2  push    rdi
0x18000c2a3  sub     rsp, 20h
0x18000c2a7  mov     rbx, rcx
0x18000c2aa  mov     edi, r8d
0x18000c2ad  mov     rcx, [rcx]; string
0x18000c2b0  mov     rsi, rdx
0x18000c2b3  call    cs:__imp_WindowsDeleteString
0x18000c2b9  mov     r8, rbx
0x18000c2bc  mov     qword ptr [rbx], 0
0x18000c2c3  mov     edx, edi
0x18000c2c5  mov     rcx, rsi
0x18000c2c8  mov     rbx, [rsp+28h+arg_0]
0x18000c2cd  mov     rsi, [rsp+28h+arg_8]
0x18000c2d2  add     rsp, 20h
0x18000c2d6  pop     rdi
0x18000c2d7  jmp     cs:__imp_WindowsCreateString
```
