# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180010c64`
- end: `0x180010caa`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180009264`
- `0x18001bc7c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010c7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010c7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180010ca3`

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
0x180010c64  mov     [rsp+arg_0], rbx
0x180010c69  mov     [rsp+arg_8], rsi
0x180010c6e  push    rdi
0x180010c6f  sub     rsp, 20h
0x180010c73  mov     rbx, rcx
0x180010c76  mov     edi, r8d
0x180010c79  mov     rcx, [rcx]; string
0x180010c7c  mov     rsi, rdx
0x180010c7f  call    cs:__imp_WindowsDeleteString
0x180010c85  mov     r8, rbx
0x180010c88  mov     qword ptr [rbx], 0
0x180010c8f  mov     edx, edi
0x180010c91  mov     rcx, rsi
0x180010c94  mov     rbx, [rsp+28h+arg_0]
0x180010c99  mov     rsi, [rsp+28h+arg_8]
0x180010c9e  add     rsp, 20h
0x180010ca2  pop     rdi
0x180010ca3  jmp     cs:__imp_WindowsCreateString
```
