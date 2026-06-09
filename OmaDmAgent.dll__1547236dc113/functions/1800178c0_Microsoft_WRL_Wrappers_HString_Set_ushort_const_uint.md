# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x1800178c0`
- end: `0x180017911`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `81`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180014fc4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800178db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800178db`

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
0x1800178c0  mov     [rsp+arg_0], rbx
0x1800178c5  mov     [rsp+arg_8], rsi
0x1800178ca  push    rdi
0x1800178cb  sub     rsp, 20h
0x1800178cf  mov     rbx, rcx
0x1800178d2  mov     edi, r8d
0x1800178d5  mov     rcx, [rcx]; string
0x1800178d8  mov     rsi, rdx
0x1800178db  call    cs:__imp_WindowsDeleteString
0x1800178e2  nop     dword ptr [rax+rax+00h]
0x1800178e7  mov     r8, rbx
0x1800178ea  mov     qword ptr [rbx], 0
0x1800178f1  mov     edx, edi
0x1800178f3  mov     rcx, rsi
0x1800178f6  mov     rbx, [rsp+28h+arg_0]
0x1800178fb  mov     rsi, [rsp+28h+arg_8]
0x180017900  add     rsp, 20h
0x180017904  pop     rdi
0x180017905  jmp     cs:__imp_WindowsCreateString
```
