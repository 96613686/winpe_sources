# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180089054`
- end: `0x18008909a`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180088680`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008906f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008906f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180089093`

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
0x180089054  mov     [rsp+arg_0], rbx
0x180089059  mov     [rsp+arg_8], rsi
0x18008905e  push    rdi
0x18008905f  sub     rsp, 20h
0x180089063  mov     rbx, rcx
0x180089066  mov     edi, r8d
0x180089069  mov     rcx, [rcx]; string
0x18008906c  mov     rsi, rdx
0x18008906f  call    cs:__imp_WindowsDeleteString
0x180089075  mov     r8, rbx
0x180089078  mov     qword ptr [rbx], 0
0x18008907f  mov     edx, edi
0x180089081  mov     rcx, rsi
0x180089084  mov     rbx, [rsp+28h+arg_0]
0x180089089  mov     rsi, [rsp+28h+arg_8]
0x18008908e  add     rsp, 20h
0x180089092  pop     rdi
0x180089093  jmp     cs:__imp_WindowsCreateString
```
