# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180024498`
- end: `0x1800244de`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001f37c`
- `0x1800242f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800244b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800244b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800244d7`

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
0x180024498  mov     [rsp+arg_0], rbx
0x18002449d  mov     [rsp+arg_8], rsi
0x1800244a2  push    rdi
0x1800244a3  sub     rsp, 20h
0x1800244a7  mov     rbx, rcx
0x1800244aa  mov     edi, r8d
0x1800244ad  mov     rcx, [rcx]; string
0x1800244b0  mov     rsi, rdx
0x1800244b3  call    cs:__imp_WindowsDeleteString
0x1800244b9  mov     r8, rbx
0x1800244bc  mov     qword ptr [rbx], 0
0x1800244c3  mov     edx, edi
0x1800244c5  mov     rcx, rsi
0x1800244c8  mov     rbx, [rsp+28h+arg_0]
0x1800244cd  mov     rsi, [rsp+28h+arg_8]
0x1800244d2  add     rsp, 20h
0x1800244d6  pop     rdi
0x1800244d7  jmp     cs:__imp_WindowsCreateString
```
