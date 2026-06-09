# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x14000e848`
- end: `0x14000e88e`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140009f70`
- `0x1400152cc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000e863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000e887`

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
0x14000e848  mov     [rsp+arg_0], rbx
0x14000e84d  mov     [rsp+arg_8], rsi
0x14000e852  push    rdi
0x14000e853  sub     rsp, 20h
0x14000e857  mov     rbx, rcx
0x14000e85a  mov     edi, r8d
0x14000e85d  mov     rcx, [rcx]; string
0x14000e860  mov     rsi, rdx
0x14000e863  call    cs:__imp_WindowsDeleteString
0x14000e869  mov     r8, rbx
0x14000e86c  mov     qword ptr [rbx], 0
0x14000e873  mov     edx, edi
0x14000e875  mov     rcx, rsi
0x14000e878  mov     rbx, [rsp+28h+arg_0]
0x14000e87d  mov     rsi, [rsp+28h+arg_8]
0x14000e882  add     rsp, 20h
0x14000e886  pop     rdi
0x14000e887  jmp     cs:__imp_WindowsCreateString
```
