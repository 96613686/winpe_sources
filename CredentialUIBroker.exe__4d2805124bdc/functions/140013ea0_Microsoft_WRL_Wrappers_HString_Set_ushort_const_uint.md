# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x140013ea0`
- end: `0x140013ee6`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140006f10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140013ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140013ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140013edf`

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
0x140013ea0  mov     [rsp+arg_0], rbx
0x140013ea5  mov     [rsp+arg_8], rsi
0x140013eaa  push    rdi
0x140013eab  sub     rsp, 20h
0x140013eaf  mov     rbx, rcx
0x140013eb2  mov     edi, r8d
0x140013eb5  mov     rcx, [rcx]; string
0x140013eb8  mov     rsi, rdx
0x140013ebb  call    cs:__imp_WindowsDeleteString
0x140013ec1  mov     r8, rbx
0x140013ec4  mov     qword ptr [rbx], 0
0x140013ecb  mov     edx, edi
0x140013ecd  mov     rcx, rsi
0x140013ed0  mov     rbx, [rsp+28h+arg_0]
0x140013ed5  mov     rsi, [rsp+28h+arg_8]
0x140013eda  add     rsp, 20h
0x140013ede  pop     rdi
0x140013edf  jmp     cs:__imp_WindowsCreateString
```
