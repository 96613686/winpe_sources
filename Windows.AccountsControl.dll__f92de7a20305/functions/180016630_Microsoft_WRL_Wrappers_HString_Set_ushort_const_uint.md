# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180016630`
- end: `0x180016676`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a084`
- `0x180032f80`
- `0x180037930`
- `0x180040384`
- `0x180062ac4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001664b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001664b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001666f`

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
0x180016630  mov     [rsp+arg_0], rbx
0x180016635  mov     [rsp+arg_8], rsi
0x18001663a  push    rdi
0x18001663b  sub     rsp, 20h
0x18001663f  mov     rbx, rcx
0x180016642  mov     edi, r8d
0x180016645  mov     rcx, [rcx]; string
0x180016648  mov     rsi, rdx
0x18001664b  call    cs:__imp_WindowsDeleteString
0x180016651  mov     r8, rbx
0x180016654  mov     qword ptr [rbx], 0
0x18001665b  mov     edx, edi
0x18001665d  mov     rcx, rsi
0x180016660  mov     rbx, [rsp+28h+arg_0]
0x180016665  mov     rsi, [rsp+28h+arg_8]
0x18001666a  add     rsp, 20h
0x18001666e  pop     rdi
0x18001666f  jmp     cs:__imp_WindowsCreateString
```
