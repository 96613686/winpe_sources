# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x1800280c0`
- end: `0x180028106`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800171a4`
- `0x1800171d0`
- `0x18001f7c0`
- `0x18001fd70`
- `0x180021970`
- `0x180022700`
- `0x18002d8a0`
- `0x18002fe90`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800280ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800280db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800280db`

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
0x1800280c0  mov     [rsp+arg_0], rbx
0x1800280c5  mov     [rsp+arg_8], rsi
0x1800280ca  push    rdi
0x1800280cb  sub     rsp, 20h
0x1800280cf  mov     rbx, rcx
0x1800280d2  mov     edi, r8d
0x1800280d5  mov     rcx, [rcx]; string
0x1800280d8  mov     rsi, rdx
0x1800280db  call    cs:__imp_WindowsDeleteString
0x1800280e1  mov     r8, rbx
0x1800280e4  mov     qword ptr [rbx], 0
0x1800280eb  mov     edx, edi
0x1800280ed  mov     rcx, rsi
0x1800280f0  mov     rbx, [rsp+28h+arg_0]
0x1800280f5  mov     rsi, [rsp+28h+arg_8]
0x1800280fa  add     rsp, 20h
0x1800280fe  pop     rdi
0x1800280ff  jmp     cs:__imp_WindowsCreateString
```
