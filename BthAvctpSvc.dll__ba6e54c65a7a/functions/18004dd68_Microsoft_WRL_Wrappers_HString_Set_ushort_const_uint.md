# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18004dd68`
- end: `0x18004ddae`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18004cc94`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004dda7`

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
0x18004dd68  mov     [rsp+arg_0], rbx
0x18004dd6d  mov     [rsp+arg_8], rsi
0x18004dd72  push    rdi
0x18004dd73  sub     rsp, 20h
0x18004dd77  mov     rbx, rcx
0x18004dd7a  mov     edi, r8d
0x18004dd7d  mov     rcx, [rcx]; string
0x18004dd80  mov     rsi, rdx
0x18004dd83  call    cs:__imp_WindowsDeleteString
0x18004dd89  mov     r8, rbx
0x18004dd8c  mov     qword ptr [rbx], 0
0x18004dd93  mov     edx, edi
0x18004dd95  mov     rcx, rsi
0x18004dd98  mov     rbx, [rsp+28h+arg_0]
0x18004dd9d  mov     rsi, [rsp+28h+arg_8]
0x18004dda2  add     rsp, 20h
0x18004dda6  pop     rdi
0x18004dda7  jmp     cs:__imp_WindowsCreateString
```
